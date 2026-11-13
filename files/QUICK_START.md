# ⚡ QUICK START - COMMENCEZ MAINTENANT (15 MINUTES)

## 🎯 OBJECTIF
Avoir une **structure de projet complète et fonctionnelle** en **15 minutes maximum**.

---

## 🚀 ÉTAPE 1: Préparez votre système (3 min)

### Vérifier que Python est installé:
```bash
python --version
pip --version
```

**Résultat attendu:** Python 3.9+ et pip

Si vous n'avez pas Python: [Télécharger Python](https://www.python.org/downloads/)

---

## 📁 ÉTAPE 2: Créer la structure du projet (5 min)

### Copier-coller ces commandes:

```bash
# 1. Aller dans votre dossier
cd "C:\Users\Pc-Samar\OneDrive - EPISousse\Bureau\projects\GreenRoute"

# 2. Créer les dossiers
mkdir src src\data src\models src\api src\frontend src\utils src\monitoring
mkdir scripts notebooks tests config deployment logs data docs
mkdir data\raw data\processed data\external
mkdir models\baseline models\advanced
mkdir .github
mkdir deployment\k8s deployment\monitoring

# 3. Créer les fichiers __init__.py
echo. > src\__init__.py
echo. > src\data\__init__.py
echo. > src\models\__init__.py
echo. > src\api\__init__.py
echo. > src\frontend\__init__.py
echo. > src\utils\__init__.py
echo. > src\monitoring\__init__.py
echo. > tests\__init__.py
echo. > tests\conftest.py

# 4. Créer les fichiers de configuration
type nul > requirements.txt
type nul > .env.example
type nul > .gitignore
type nul > Dockerfile
type nul > setup.py
```

---

## 📄 ÉTAPE 3: Remplir les fichiers importants (5 min)

### A) Créer `requirements.txt`

Copier-coller dans le fichier:
```
# Data Science
numpy==1.24.0
pandas==2.0.0
scikit-learn==1.3.0

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
```

### B) Créer `.env.example`

Copier-coller:
```
# Environment
ENVIRONMENT=development
DEBUG=True

# API
API_HOST=0.0.0.0
API_PORT=8000

# Model paths
MODEL_PATH=models/advanced/model_v1.pkl
BASELINE_MODEL_PATH=models/baseline/model_v1.pkl

# Database (si needed)
DATABASE_URL=postgresql://user:password@localhost/greenroute
```

### C) Créer `.gitignore`

Copier-coller:
```
# Environment
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

# Data & Models
data/raw/
data/processed/
models/*/model_*.*
*.csv

# Logs & Build
logs/
build/
dist/
*.egg-info/

# Tests
.pytest_cache/
.coverage

# OS
.DS_Store
Thumbs.db
```

### D) Créer `README.md`

Copier-coller:
```markdown
# 🌿 GreenRoute - AI-Powered Project

## 📋 Description
[À remplir avec la description de votre projet]

## 🚀 Quick Start

### Installation
\`\`\`bash
# 1. Créer l'environnement virtuel
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 2. Installer les dépendances
pip install -r requirements.txt

# 3. Créer le fichier .env
cp .env.example .env
\`\`\`

### Lancer l'application
\`\`\`bash
# API
uvicorn src.api.main:app --reload

# Frontend
streamlit run src/frontend/app.py
\`\`\`

## 📁 Structure du projet
Voir `PROJECT_STRUCTURE.md` pour la structure complète.

## 📚 Documentation
- [Planning détaillé](PLANNING_DETAILLE.md)
- [Checklist de suivi](CHECKLIST_SUIVI.md)
- [Architecture](docs/ARCHITECTURE.md)

## 🤝 Contributing
Voir `CONTRIBUTING.md`

## 📄 License
MIT License
```

### E) Créer `.github/workflows/ci.yml`

Créer le fichier `ci.yml`:
```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.9'
      - name: Install dependencies
        run: |
          pip install -r requirements.txt
          pip install pytest pytest-cov
      - name: Run tests
        run: pytest tests/ --cov=src
```

---

## 🔧 ÉTAPE 4: Initialiser Git (2 min)

```bash
# 1. Initialiser git
git init

# 2. Créer le premier commit
git add .
git commit -m "Initial project setup with structure and documentation"

# 3. Ajouter le remote (optionnel - si vous avez GitHub)
git remote add origin https://github.com/YOUR_USERNAME/greenroute.git
git branch -M main
git push -u origin main
```

---

## ✅ VÉRIFICATION FINALE

Vérifier que tout fonctionne:

```bash
# 1. Créer l'environnement virtuel
python -m venv venv

# Windows
venv\Scripts\activate

# MacOS/Linux
source venv/bin/activate

# 2. Installer les dépendances
pip install -r requirements.txt

# 3. Vérifier les imports
python -c "import pandas; import numpy; import fastapi; print('✓ All imports OK!')"

# 4. Vérifier la structure
python -c "from src import *; print('✓ Package structure OK!')"
```

**Résultat attendu:**
```
✓ All imports OK!
✓ Package structure OK!
```

---

## 🎯 CE QUE VOUS AVEZ ACCOMPLI EN 15 MIN

✅ **Structure de projet complète** prête pour 4 semaines de développement
✅ **Fichiers de configuration** (requirements, .env, .gitignore)
✅ **Documentation de base** (README, planning, checklist)
✅ **Git repository** initialisé
✅ **GitHub Actions** configuré
✅ **Dépendances** listées et testées

---

## 🚨 PROCHAINE ÉTAPE IMMÉDIATE

### MAINTENANT (dans les 30 prochaines minutes):

1. **Lire les documents du projet** (GreenRoute_planning.docx, GreenRoute_projet_IA.docx)
   ```bash
   # Ouvrir avec votre lecteur PDF/Word
   start "C:\Users\Pc-Samar\Downloads\GreenRoute_planning.docx"
   start "C:\Users\Pc-Samar\Downloads\GreenRoute_projet_IA.docx"
   ```

2. **Documenter les cas d'usage IA** dans `docs/ARCHITECTURE.md`
   ```markdown
   # Architecture GreenRoute
   
   ## Cas d'usage principaux
   1. [À remplir après lecture]
   2. [À remplir après lecture]
   
   ## Architecture globale
   [Dessiner avec draw.io]
   ```

3. **Créer votre premier script** de test:
   ```python
   # scripts/test_setup.py
   import pandas as pd
   import numpy as np
   
   print("✓ Setup réussi!")
   ```

---

## 💡 COMMANDES UTILES POUR LA SUITE

```bash
# Activer l'environnement virtuel (faire ça à chaque fois!)
venv\Scripts\activate  # Windows
source venv/bin/activate  # MacOS/Linux

# Installer une dépendance supplémentaire
pip install pandas==2.0.0

# Lancer les tests
pytest tests/

# Formater le code
black src/

# Lancer l'API
uvicorn src.api.main:app --reload --port 8000

# Lancer le frontend
streamlit run src/frontend/app.py
```

---

## 🆘 SI VOUS ÊTES BLOQUÉ

### "Python not found"
```bash
# Télécharger Python: https://www.python.org/downloads/
# Puis refaire les tests
```

### "Permission denied"
```bash
# Windows PowerShell:
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# Puis relancer
```

### "Module not found"
```bash
# Vérifier que venv est activé:
# Windows: (venv) devrait apparaître dans le terminal

# Puis réinstaller:
pip install -r requirements.txt
```

---

## 📞 BESOIN D'AIDE?

**Avant de continuer, vérifiez:**
- [ ] Tous les dossiers ont été créés ✅
- [ ] Tous les fichiers de config sont présents ✅
- [ ] Git est initialisé ✅
- [ ] L'environnement Python fonctionne ✅
- [ ] Les imports Python fonctionnent ✅

**Si quelque chose ne fonctionne pas:**
1. Relire ces instructions
2. Vérifier les chemins (paths)
3. Vérifier les permissions
4. Redémarrer le terminal

---

## 🎉 FÉLICITATIONS!

Vous êtes maintenant **PRÊT À COMMENCER LE VRAI TRAVAIL!**

### Prochaines étapes:
- 👉 Ouvrir `PLANNING_DETAILLE.md` et commencer **Jour 1: Discovery & Architecture**
- 👉 Commencer par lire les documents du projet
- 👉 Remplir le checklist dans `CHECKLIST_SUIVI.md`

**Bonne chance! 🚀 Vous allez réussir ce projet en 2-4 semaines! 💪**

