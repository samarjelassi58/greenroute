# GreenRoute · Cadrage

Version 0.1 · 15 novembre 2026

## 1. Vision & Objectif

**GreenRoute** mesure le coût énergétique, carbone et environnemental de chaque réponse d'IA.

Une question posée → réponse rapide + rapport d'énergie et CO₂e consommés.

**Objectifs** :
- Rendre transparent le coût écologique des requêtes IA
- Permettre aux utilisateurs de faire des choix conscients (utiliser un petit modèle ou attendre ?)
- Logger toutes les mesures pour benchmarker et optimiser

## 2. Contexte & Contraintes

| Critère | Choix | Raison |
|---|---|---|
| **Déploiement** | Local + API gratuite (Gemini) | Pas de coût opérationnel, pas de carte bancaire |
| **Performance** | Réponse immédiate (`/chat` < 1s en cache) | L'utilisateur n'attend pas |
| **Données** | Logs en DuckDB | Rien à installer, rien à maintenir |
| **Calcul carbone** | RTE + CodeCarbon | Données libres, France-centré |

## 3. Utilisateurs Cibles

- 👨‍💻 **Développeurs** qui veulent mesurer leur consommation IA
- 🌱 **Entreprises écologiques** conscientes de leur empreinte numérique
- 📊 **Chercheurs** en efficacité énergétique des LLM
- 🎓 **Étudiants** (portfolio, démonstration technique)

## 4. Résultats Attendus

Pour chaque requête :
- ✅ **Réponse** (texte du modèle)
- ✅ **Énergie** (Wh)
- ✅ **CO₂e** (grammes)
- ✅ **Eau** (litres, estimation)
- ✅ **Coût** (€ ou $)
- ✅ **Temps** (secondes)
- ✅ **Modèle utilisé** (llama3.2, gpt-oss, Gemini, etc.)

## 5. Périmètre - Ce qu'on fait

- ✅ Classifier les questions (simple/moyen/difficile)
- ✅ Choisir le modèle adapté
- ✅ Mesurer l'énergie réelle/estimée
- ✅ Logger tout dans DuckDB
- ✅ Dashboard React pour explorer les logs
- ✅ Cache sémantique (même question = pas de calcul)

## 6. Hors périmètre - Ce qu'on ne fait pas (v0.1)

- ❌ Fine-tuning de modèles (coûteux en énergie)
- ❌ Streaming de réponses
- ❌ API payante
- ❌ Multi-langue
- ❌ Export PDF/Excel des rapports

---

**Voir aussi** : [01_architecture.md](./01_architecture.md) pour les détails techniques, modules et choix d'implémentation.
