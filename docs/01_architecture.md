```mermaid
flowchart LR
    classDef client fill:#f8fafc,stroke:#64748b,stroke-width:2px,color:#0f172a
    classDef api fill:#eff6ff,stroke:#3b82f6,stroke-width:2px,color:#1e3a8a
    classDef decision fill:#f0fdf4,stroke:#22c55e,stroke-width:2px,color:#14532d
    classDef model fill:#faf5ff,stroke:#a855f7,stroke-width:2px,color:#3b0764
    classDef obs fill:#fffbeb,stroke:#f59e0b,stroke-width:2px,color:#78350f

    subgraph S1 ["1. Client Layer"]
        C(["Client Web / Application<br/>(Interface / SDK)"]):::client
    end

    subgraph S2 ["2. Gateway & Cache Layer"]
        API["API FastAPI<br/>(Validation Pydantic / RBAC)"]:::api
        CACHE{"Cache Sémantique<br/>(Similarité vectorielle ≥ 0.92, contrôle des droits)"}:::api
    end

    subgraph S3 ["3. GreenAI Routing & Scheduling"]
        QUEUE["File d'attente asynchrone<br/>(Réponse 202 Accepted + Job ID)"]:::decision
        PLAN["Planificateur temporel<br/>(Fenêtre bas-carbone ou timeout)"]:::decision
        RTE[("API RTE éCO2mix<br/>(Mix réel et prévisions localisées)")]:::decision
        ROUTER{"Classifieur de complexité<br/>(Heuristique / Modèle de routage)"}:::decision
    end

    subgraph S4 ["4. Hybrid Inference Layer"]
        SMALL["Modèle local léger<br/>(ex: llama3.2:3b / phi4-mini)"]:::model
        MEDIUM["Modèle intermédiaire<br/>(ex: gpt-oss:20b / Flash-Lite)"]:::model
        LARGE["Modèle cloud avancé<br/>(ex: Gemini Flash)"]:::model
        RES["Agrégateur & Validateur<br/>(Sanitizer / Contrôle de sortie)"]:::model
    end

    subgraph S5 ["5. Observability & FinOps"]
        JOBS[("Stockage des Jobs<br/>(État, TTL & résultats asynchrones)")]:::obs
        DB[("DuckDB<br/>(Logs structurés, tokens, latence, delta CO₂)")]:::obs
        DASH["Dashboard Analytics<br/>(GreenOps / FinOps)"]:::obs
    end

    %% Flux principaux
    C -->|"POST /chat<br/>(payload JSON + header priority)"| API
    API --> CACHE
    
    %% Cache branches
    CACHE -->|"Hit (Similarité ≥ 0.92)<br/>Inférence évitée"| API
    CACHE -->|"Miss · Mode Immédiat"| ROUTER
    CACHE -->|"Miss · Mode Différé"| QUEUE
    
    %% Queue & RTE logic
    QUEUE -->|"Retour HTTP 202 + Job ID"| C
    QUEUE --> JOBS
    QUEUE --> PLAN
    RTE -.->|"Prévisions & intensité réelle localisée"| PLAN
    PLAN -->|"Fenêtre bas-carbone validée<br/>(ou repli sur délai max / échec RTE)"| ROUTER
    
    %% Router logic
    ROUTER -->|"Requête Simple"| SMALL
    ROUTER -->|"Requête Moyenne"| MEDIUM
    ROUTER -->|"Requête Complexe"| LARGE
    
    %% Inference to Result
    SMALL --> RES
    MEDIUM --> RES
    LARGE --> RES
    
    %% Result output & cache update
    RES -->|"Réponse synchrone immédiate"| API
    RES -->|"Résultat asynchrone (Job terminé)"| JOBS
    RES -.->|"Mise en cache sémantique<br/>(si autorisé)"| CACHE
    
    %% Client job polling
    C -->|"GET /jobs/{id}"| API
    API -->|"Lecture statut & résultat"| JOBS
    
    %% Telemetry
    CACHE -.->|"Hit / Miss metrics"| DB
    ROUTER -.->|"Modèle sélectionné"| DB
    RES -.->|"Latence, tokens, facteur RTE"| DB
    DB --> DASH
    ```