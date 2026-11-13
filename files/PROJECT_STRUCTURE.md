# 📁 STRUCTURE DE PROJET RECOMMANDÉE - GREENROUTE

## Structure Complète du Dossier

```
greenroute/
│
├── 📄 README.md                          ← Documentation principale
├── 📄 PLANNING_DETAILLE.md               ← Ce planning!
├── 📄 CHECKLIST_SUIVI.md                 ← Suivi quotidien
├── 📄 PROJECT_STRUCTURE.md               ← Ce fichier
├── 📄 requirements.txt                   ← Dépendances Python
├── 📄 requirements_template.txt           ← Template pour requirements
├── 📄 .env.example                       ← Variables d'environnement (exemple)
├── 📄 .env                               ← Variables d'environnement (à gitignore)
├── 📄 .gitignore                         ← Git ignore
├── 📄 Dockerfile                         ← Containerization
├── 📄 docker-compose.yml                 ← Docker compose
├── 📄 setup.py                           ← Package setup
│
├── 📁 src/                               ← Code source principal
│   ├── __init__.py
│   ├── config.py                         ← Configuration globale
│   ├── logger.py                         ← Logging setup
│   ├── constants.py                      ← Constantes
│   │
│   ├── 📁 data/
│   │   ├── __init__.py
│   │   ├── loader.py                     ← Chargement des données
│   │   ├── preprocessor.py               ← Nettoyage/préparation
│   │   ├── splitter.py                   ← Train/val/test split
│   │   └── augmentation.py               ← Data augmentation (si needed)
│   │
│   ├── 📁 models/
│   │   ├── __init__.py
│   │   ├── base.py                       ← Base model class
│   │   ├── baseline.py                   ← Baseline model
│   │   ├── advanced.py                   ← Advanced model (DL, ensemble, etc)
│   │   └── utils.py                      ← Model utilities
│   │
│   ├── 📁 api/
│   │   ├── __init__.py
│   │   ├── main.py                       ← FastAPI app
│   │   ├── routes.py                     ← API endpoints
│   │   ├── schemas.py                    ← Pydantic schemas
│   │   └── middleware.py                 ← Middleware (auth, logging)
│   │
│   ├── 📁 frontend/                      ← Frontend (Streamlit/Dash)
│   │   ├── __init__.py
│   │   ├── app.py                        ← Main Streamlit app
│   │   ├── pages/
│   │   │   ├── home.py
│   │   │   ├── predict.py
│   │   │   └── about.py
│   │   └── components.py                 ← Reusable components
│   │
│   ├── 📁 utils/
│   │   ├── __init__.py
│   │   ├── helpers.py                    ← Fonctions utilitaires
│   │   ├── validators.py                 ← Validation logic
│   │   └── decorators.py                 ← Decorators personnalisés
│   │
│   └── 📁 monitoring/
│       ├── __init__.py
│       ├── metrics.py                    ← Métriques custom
│       └── profiler.py                   ← Profiling
│
├── 📁 scripts/                           ← Scripts d'exécution
│   ├── 01_eda.ipynb                      ← Exploration des données
│   ├── 02_data_preprocessing.py          ← Préparation des données
│   ├── 03_data_split.py                  ← Split données
│   ├── 04_train_baseline.py              ← Train baseline
│   ├── 05_train_advanced.py              ← Train advanced model
│   ├── 06_evaluate.py                    ← Évaluation
│   ├── 07_tune_hyperparams.py            ← Hyperparameter tuning
│   └── 08_inference.py                   ← Inference en batch
│
├── 📁 models/                            ← Modèles sauvegardés
│   ├── baseline/
│   │   ├── model_v1.pkl
│   │   └── metadata.json
│   ├── advanced/
│   │   ├── model_v1.h5
│   │   └── metadata.json
│   └── model_registry.json               ← Registre de modèles
│
├── 📁 data/                              ← Données
│   ├── 📁 raw/
│   │   ├── dataset.csv
│   │   └── README_DATA.md
│   ├── 📁 processed/
│   │   ├── train.csv
│   │   ├── val.csv
│   │   └── test.csv
│   ├── 📁 external/                      ← Données externes
│   └── data_processing_log.txt
│
├── 📁 notebooks/                         ← Jupyter notebooks
│   ├── 00_exploratory.ipynb
│   ├── 01_baseline_model.ipynb
│   ├── 02_advanced_model.ipynb
│   └── 03_analysis.ipynb
│
├── 📁 tests/                             ← Tests unitaires
│   ├── __init__.py
│   ├── conftest.py                       ← Pytest config
│   ├── test_data.py
│   ├── test_models.py
│   ├── test_api.py
│   ├── test_pipeline.py
│   └── test_utils.py
│
├── 📁 config/                            ← Fichiers de configuration
│   ├── dev.yaml
│   ├── prod.yaml
│   └── test.yaml
│
├── 📁 deployment/                        ← Déploiement
│   ├── docker-entrypoint.sh
│   ├── k8s/                              ← Kubernetes (optionnel)
│   │   └── deployment.yaml
│   └── monitoring/
│       ├── prometheus.yml
│       └── grafana-config.json
│
├── 📁 docs/                              ← Documentation
│   ├── API.md                            ← Documentation API
│   ├── ARCHITECTURE.md                   ← Architecture
│   ├── DEPLOYMENT.md                     ← Guide déploiement
│   ├── DEVELOPMENT.md                    ← Guide développement
│   ├── MONITORING.md                     ← Monitoring & alerts
│   ├── TROUBLESHOOTING.md                ← Dépannage
│   └── images/
│       ├── architecture.png
│       └── workflow.png
│
├── 📁 logs/                              ← Logs
│   └── .gitkeep
│
├── 📁 .github/                           ← GitHub specific
│   ├── workflows/
│   │   ├── ci.yml                        ← CI/CD pipeline
│   │   └── deploy.yml
│   └── templates/
│       └── pull_request_template.md
│
├── 📄 CONTRIBUTING.md                    ← Guide contribution
├── 📄 CHANGELOG.md                       ← Historique des versions
├── 📄 LICENSE                            ← Licence
└── 📄 SECURITY.md                        ← Politique sécurité
```

---

## 📋 DÉTAIL DE CHAQUE DOSSIER

### `/src/data/`
Tout ce qui concerne les données:
```python
# loader.py - Charger données
def load_raw_data(path):
    return pd.read_csv(path)

# preprocessor.py - Nettoyer
def preprocess_data(df):
    # Nettoyer, normaliser, etc
    return df

# splitter.py - Diviser
def split_data(df, train_size=0.7, val_size=0.15):
    # Diviser en train/val/test
    return train_df, val_df, test_df
```

### `/src/models/`
Modèles ML/IA:
```python
# base.py - Classe de base
class BaseModel:
    def __init__(self, config):
        self.config = config
    
    def train(self, X, y):
        pass
    
    def predict(self, X):
        pass

# baseline.py - Baseline
class BaselineModel(BaseModel):
    def __init__(self, config):
        super().__init__(config)
        self.model = LogisticRegression()

# advanced.py - Modèle avancé
class AdvancedModel(BaseModel):
    def __init__(self, config):
        super().__init__(config)
        self.model = build_neural_network()
```

### `/src/api/`
API FastAPI:
```python
# main.py
from fastapi import FastAPI
app = FastAPI(title="GreenRoute API")

# routes.py
@app.post("/predict")
async def predict(data: InputSchema):
    return {"prediction": model.predict(data)}

@app.get("/health")
async def health():
    return {"status": "OK"}
```

### `/src/frontend/`
Interface utilisateur Streamlit:
```python
# app.py
import streamlit as st

st.title("🌿 GreenRoute")
st.write("Bienvenue!")

# pages/predict.py
def show_predict_page():
    input_data = st.text_input("Entrez vos données")
    if st.button("Prédire"):
        prediction = requests.post(API_URL, json=input_data)
        st.write(prediction.json())
```

### `/scripts/`
Scripts d'exécution:
```
01_eda.ipynb              - Exploration des données (notebook interactif)
02_data_preprocessing.py  - Préparation automatisée
03_data_split.py         - Créer les splits train/val/test
04_train_baseline.py     - Entraîner baseline
05_train_advanced.py     - Entraîner le modèle avancé
06_evaluate.py           - Évaluer tous les modèles
07_tune_hyperparams.py   - Tuning hyperparamètres
08_inference.py          - Inférence en batch
```

### `/models/`
Modèles sauvegardés:
```
baseline/
├── model_v1.pkl
└── metadata.json
{
  "version": "1.0",
  "accuracy": 0.85,
  "f1": 0.82,
  "created_at": "2024-11-13",
  "training_time": 120
}

advanced/
├── model_v1.h5
└── metadata.json
```

### `/data/`
Structure des données:
```
raw/           - Données brutes téléchargées
processed/     - Données nettoyées et préprocessées
external/      - Données externes (vocabulaires, mappings, etc)
```

### `/tests/`
Tests unitaires et d'intégration:
```python
# test_data.py
def test_data_loading():
    data = load_raw_data("test_file.csv")
    assert len(data) > 0

# test_models.py
def test_model_prediction():
    model = load_model("baseline")
    pred = model.predict(test_data)
    assert pred.shape[0] == test_data.shape[0]

# test_api.py
def test_predict_endpoint():
    response = client.post("/predict", json={"input": "test"})
    assert response.status_code == 200
```

### `/docs/`
Documentation:
- **API.md** - Endpoints et usage
- **ARCHITECTURE.md** - Design du système
- **DEPLOYMENT.md** - Comment déployer
- **MONITORING.md** - Métriques et alertes

### `/deployment/`
Fichiers de déploiement:
```dockerfile
# Dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "-m", "uvicorn", "src.api.main:app", "--host", "0.0.0.0"]
```

---

## 🚀 CRÉATION DE LA STRUCTURE

### Commandes à exécuter (Day 1):

```bash
# 1. Aller dans le dossier du projet
cd greenroute

# 2. Créer la structure
mkdir -p src/{data,models,api,frontend,utils,monitoring}
mkdir -p scripts notebooks tests config deployment/k8s deployment/monitoring
mkdir -p models/{baseline,advanced}
mkdir -p data/{raw,processed,external}
mkdir -p docs logs .github/workflows

# 3. Créer les fichiers __init__.py
touch src/__init__.py
touch src/data/__init__.py
touch src/models/__init__.py
touch src/api/__init__.py
touch src/frontend/__init__.py
touch src/utils/__init__.py
touch src/monitoring/__init__.py
touch tests/__init__.py
touch tests/conftest.py

# 4. Créer les fichiers de base
touch src/config.py
touch src/logger.py
touch src/constants.py
touch requirements.txt
touch .env.example
touch setup.py
touch Dockerfile
touch docker-compose.yml
```

### Fichiers à créer (Day 1):

**requirements.txt** (dépendances de base):
```
# Data science
numpy==1.24.0
pandas==2.0.0
scikit-learn==1.3.0

# Deep Learning (choisir l'un ou l'autre)
# tensorflow==2.13.0
# torch==2.0.0

# API
fastapi==0.104.0
uvicorn==0.24.0
pydantic==2.5.0

# Frontend
streamlit==1.28.0

# Monitoring
prometheus-client==0.18.0

# Utilities
python-dotenv==1.0.0
requests==2.31.0
pyyaml==6.0
click==8.1.7

# Development
jupyter==1.0.0
pytest==7.4.0
black==23.12.0
flake8==6.1.0
mypy==1.7.0
```

**.env.example**:
```
# Environment
ENVIRONMENT=development
DEBUG=True

# Database (si needed)
DATABASE_URL=postgresql://user:password@localhost/greenroute

# API
API_HOST=0.0.0.0
API_PORT=8000

# Model paths
MODEL_PATH=models/advanced/model_v1.h5
BASELINE_MODEL_PATH=models/baseline/model_v1.pkl

# Monitoring
SENTRY_DSN=
MLFLOW_TRACKING_URI=http://localhost:5000

# External APIs (si needed)
HUGGINGFACE_API_KEY=
OPENAI_API_KEY=
```

**.gitignore**:
```
# Environnement
venv/
env/
.env
*.pyc
__pycache__/
*.pyo

# IDE
.vscode/
.idea/
*.swp
*.swo

# Data
data/raw/
data/processed/
*.csv
*.xlsx

# Modèles
models/*/model_*.pkl
models/*/model_*.h5
*.pt
*.pth

# Logs
logs/
*.log

# Build
build/
dist/
*.egg-info/

# OS
.DS_Store
Thumbs.db

# Tests
.pytest_cache/
.coverage
htmlcov/

# Jupyter
.ipynb_checkpoints/
```

---

## 📊 ARBORESCENCE PENDANT LE DÉVELOPPEMENT

### Après Day 7 (Fin Semaine 1):
```
✅ Setup terminé
✅ Données collectées et nettoyées
✅ Baseline entraîné
✅ Pipeline configurée
```

### Après Day 14 (Fin Semaine 2):
```
✅ Modèle avancé entraîné
✅ API avec endpoints
✅ Frontend basique
✅ Tests écrits
```

### Après Day 21 (Fin Semaine 3):
```
✅ Production-ready
✅ Monitoring en place
✅ Documentation complète
✅ Déploiement staging
```

### Après Day 28 (Fin Semaine 4):
```
✅ En production
✅ Support operationnel
✅ MLOps automatisé
```

---

## 💡 BEST PRACTICES

### 1. **Structure de modèles**
```
models/
├── v1/
│   ├── model.pkl
│   ├── metadata.json
│   └── performance.json
├── v2/
│   ├── model.pkl
│   ├── metadata.json
│   └── performance.json
└── current → v2  (symlink to best model)
```

### 2. **Versioning des données**
```
data/
├── raw/
│   └── dataset_v1.csv  (original)
├── processed/
│   └── dataset_v1_processed.csv  (versioned)
└── versions.json  (metadata)
```

### 3. **Configuration management**
```python
# config/prod.yaml
model:
  type: "advanced"
  version: "v1"
  batch_size: 32
  
api:
  host: "0.0.0.0"
  port: 8000
  timeout: 30
```

### 4. **Logging cohérent**
```python
# src/logger.py
import logging
logger = logging.getLogger(__name__)
logger.info("Model loaded")
logger.error("Error occurred", exc_info=True)
```

---

## ✨ BONNES PRATIQUES GIT

```bash
# Commits significatifs
git commit -m "feat: Add baseline model training"
git commit -m "fix: Fix data preprocessing bug"
git commit -m "docs: Add API documentation"

# Branches
main/                 - Production code
develop/              - Development branch
feature/ml-model      - Feature branches
bugfix/issue-123      - Bug fix branches

# Tags pour versions
git tag v0.1.0  ← After first milestone
git tag v0.2.0  ← After second milestone
```

---

## 🎯 CHECKLIST STRUCTURE

- [ ] Tous les dossiers créés
- [ ] Fichiers de base présents
- [ ] .gitignore correct
- [ ] requirements.txt complet
- [ ] README.md basique écrit
- [ ] Git initialisé
- [ ] Premier commit fait
- [ ] Structure testée (import src fonctionne)

**Temps estimé pour la structure:** 30-45 minutes

