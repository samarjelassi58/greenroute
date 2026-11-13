# 🔧 COMMANDES GIT & SETUP - QUICK REFERENCE

## 🚀 COMMENCEZ TOUT DE SUITE

### 1️⃣ Vérifier Git est installé
```bash
git --version
```

Si vous n'avez pas Git: [Télécharger Git](https://git-scm.com/download/win)

---

## 📁 INITIALISER LE REPOSITORY

### Première fois (dans le dossier GreenRoute):

```bash
# 1. Initialiser Git
git init

# 2. Ajouter tous les fichiers
git add .

# 3. Premier commit
git commit -m "Initial: Project setup with planning and structure"

# 4. (OPTIONNEL) Ajouter le remote GitHub
git remote add origin https://github.com/YOUR_USERNAME/greenroute.git

# 5. (OPTIONNEL) Pousser sur GitHub
git branch -M main
git push -u origin main
```

---

## 📝 WORKFLOW QUOTIDIEN

### À chaque session de travail:

```bash
# 1. Aller dans le dossier du projet
cd "C:\Users\Pc-Samar\OneDrive - EPISousse\Bureau\projects\GreenRoute"

# 2. Voir le statut
git status

# 3. Ajouter les changements
git add .
# OU ajouter fichiers spécifiques:
git add src/models/advanced.py
git add tests/test_api.py

# 4. Commiter avec un message clair
git commit -m "feat: Implement advanced ML model training pipeline"

# 5. Pousser sur GitHub (si configuré)
git push origin main
```

---

## 💡 BONNES PRATIQUES DE COMMITS

### Format de commit recommandé:

```bash
# Features
git commit -m "feat: Add new feature description"

# Bug fixes
git commit -m "fix: Fix critical bug description"

# Documentation
git commit -m "docs: Update API documentation"

# Code cleanup
git commit -m "refactor: Simplify data preprocessing logic"

# Tests
git commit -m "test: Add unit tests for model validation"

# Configuration
git commit -m "chore: Update requirements.txt dependencies"
```

### Exemples concrets:

```bash
# Jour 1 - Discovery
git commit -m "feat: Add project architecture diagram"
git commit -m "docs: Add initial project documentation"

# Jour 2 - Environment
git commit -m "chore: Setup Python virtual environment"
git commit -m "chore: Add requirements.txt with dependencies"

# Jour 3-4 - Data
git commit -m "feat: Implement data loading and exploration"
git commit -m "feat: Add data preprocessing pipeline"

# Jour 5 - Baseline
git commit -m "feat: Train and evaluate baseline model"
git commit -m "test: Add baseline model tests"

# Jour 8 - Advanced Model
git commit -m "feat: Implement advanced ML model"
git commit -m "feat: Add model hyperparameter tuning"

# Jour 12 - API
git commit -m "feat: Create FastAPI endpoints for predictions"
git commit -m "docs: Add API documentation and swagger"

# Jour 13 - Frontend
git commit -m "feat: Implement Streamlit dashboard"
git commit -m "feat: Add frontend integration with API"
```

---

## 🔀 TRAVAILLER AVEC DES BRANCHES (Optionnel)

### Si vous voulez être avancé:

```bash
# Créer une branche pour chaque feature
git checkout -b feature/data-preprocessing

# Travailler sur la branche
# ... faire des modifications ...

# Commiter
git add .
git commit -m "feat: Complete data preprocessing pipeline"

# Revenir à main
git checkout main

# Fusionner la branche
git merge feature/data-preprocessing

# Supprimer la branche
git branch -d feature/data-preprocessing

# Pousser sur GitHub
git push origin main
```

---

## 📊 VOIR L'HISTORIQUE

```bash
# Voir tous les commits
git log

# Voir les derniers 5 commits
git log -5

# Format lisible
git log --oneline

# Voir les changements d'un fichier
git log -p src/models/baseline.py

# Voir les diffs
git diff
```

---

## 🔍 COMMANDES DE VÉRIFICATION

```bash
# Voir le statut actuel
git status

# Voir les changements non commités
git diff

# Voir les changements staged
git diff --staged

# Voir les branches
git branch

# Voir la branche courante
git branch --show-current
```

---

## ⚠️ ANNULER DES CHANGEMENTS

```bash
# Annuler les changements non commités d'un fichier
git restore src/models/baseline.py

# Annuler TOUS les changements non commités
git restore .

# Annuler un commit (garder les changements)
git reset --soft HEAD~1

# Annuler un commit (supprimer les changements)
git reset --hard HEAD~1

# Annuler un push (créer un nouveau commit)
git revert HEAD
```

---

## 🚨 ERREURS COURANTES & SOLUTIONS

### "fatal: not a git repository"
```bash
# Vous n'êtes pas dans le bon dossier
cd "C:\Users\Pc-Samar\OneDrive - EPISousse\Bureau\projects\GreenRoute"

# Vérifier la présence du dossier .git
dir /A:.git  # Windows
ls -la .git  # MacOS/Linux
```

### "nothing to commit"
```bash
# Pas de changements à commiter
# Faites des modifications d'abord!
```

### "Please tell me who you are"
```bash
# Configurer Git
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"

# Vérifier la config
git config --global user.name
git config --global user.email
```

### "Your branch is ahead of origin/main"
```bash
# Vous avez des commits non pushés
git push origin main
```

### "Merge conflict"
```bash
# Éditer le fichier en conflit, puis:
git add .
git commit -m "fix: Resolve merge conflict"
```

---

## 🎯 CHECKLIST GIT QUOTIDIENNE

À la fin de CHAQUE jour de travail:

```bash
# ✅ Checklist:
# 1. Voir le statut
git status

# 2. Ajouter tous les changements
git add .

# 3. Commiter avec un bon message
git commit -m "feat: [Description du travail d'aujourd'hui]"

# 4. Pousser sur GitHub (si configuré)
git push origin main

# 5. Vérifier que tout est bon
git log -1
git status
```

**Le résultat attendu:** `On branch main` / `nothing to commit` ✅

---

## 📈 TEMPLATE COMMIT MESSAGE

Utilisez ce template pour des messages cohérents:

```bash
git commit -m "feat: Brief description of what was done

- Detailed point 1
- Detailed point 2
- Detailed point 3

Fixes: #123 (optional: if fixing a GitHub issue)"
```

**Exemple:**
```bash
git commit -m "feat: Implement data preprocessing pipeline

- Added data loader for CSV files
- Implemented feature normalization
- Added handling for missing values

Fixes: #12"
```

---

## 🔑 GITHUB SETUP (Optionnel mais recommandé)

### Si vous voulez utiliser GitHub:

```bash
# 1. Créer un compte GitHub (gratuit): https://github.com/signup

# 2. Créer un nouveau repository sur GitHub
#    (sans README, .gitignore, ou license)

# 3. Dans votre terminal:
git remote add origin https://github.com/YOUR_USERNAME/greenroute.git
git branch -M main
git push -u origin main

# 4. Vérifier la connexion
git remote -v
```

### SSH Setup (Plus sûr):

```bash
# 1. Générer une clé SSH
ssh-keygen -t ed25519 -C "your.email@example.com"

# 2. Ajouter la clé à GitHub
# Copier le contenu de: C:\Users\Pc-Samar\.ssh\id_ed25519.pub
# Aller sur: https://github.com/settings/keys
# Cliquer "New SSH key" et coller

# 3. Tester la connexion
ssh -T git@github.com

# 4. Configurer le remote avec SSH
git remote set-url origin git@github.com:YOUR_USERNAME/greenroute.git
```

---

## 📊 GARDER LES COMMITS PROPRES

### Bonnes pratiques:

```bash
# ✅ BIEN:
git commit -m "feat: Add model evaluation metrics"
git commit -m "fix: Fix data loading bug"
git commit -m "test: Add unit tests for API"

# ❌ ÉVITER:
git commit -m "update"
git commit -m "fix stuff"
git commit -m "asdf"
git commit -m "work in progress"
```

---

## 🎯 COMMITS À FAIRE PENDANT LE PROJET

### Jour 1: Discovery & Architecture
```bash
git commit -m "initial: Project structure setup"
git commit -m "docs: Add planning and documentation"
git commit -m "feat: Add architecture diagram"
```

### Jours 3-4: Data
```bash
git commit -m "feat: Add data loading pipeline"
git commit -m "feat: Implement data preprocessing"
git commit -m "feat: Add data splitting functionality"
```

### Jour 5: Baseline
```bash
git commit -m "feat: Implement baseline model training"
git commit -m "test: Add baseline model tests"
```

### Jours 8-11: Advanced Model
```bash
git commit -m "feat: Implement advanced ML model"
git commit -m "feat: Add hyperparameter tuning"
git commit -m "feat: Optimize model performance"
```

### Jour 12: API
```bash
git commit -m "feat: Create FastAPI application"
git commit -m "feat: Add prediction endpoints"
git commit -m "docs: Add API documentation"
```

### Jour 13: Frontend
```bash
git commit -m "feat: Implement Streamlit dashboard"
git commit -m "feat: Add frontend integration"
```

### Jour 14: Tests
```bash
git commit -m "test: Add comprehensive test suite"
git commit -m "test: Reach 80% code coverage"
```

---

## 📞 RESSOURCES UTILES

```bash
# Aide Git
git help commit
git help branch
git help push

# Documentation:
# - https://git-scm.com/doc
# - https://github.com/git-tips/tips
# - https://guides.github.com/
```

---

## ✅ VÉRIFICATION FINALE

Avant de continuer avec le projet:

```bash
# 1. Vérifier Git est opérationnel
git --version
git status

# 2. Vérifier la config
git config --global --list

# 3. Vérifier le dossier .git existe
dir .git  # Windows
ls -la .git  # MacOS/Linux

# 4. Voir le dernier commit
git log -1

# Résultat attendu: Tous les `git` commandes fonctionnent! ✅
```

---

## 🎉 VOUS ÊTES PRÊT!

Vous pouvez maintenant:
- ✅ Initialiser Git
- ✅ Faire des commits quotidiens
- ✅ Gérer votre version control
- ✅ Collaborer via GitHub (si voulu)

**Prochaine étape:** Ouvrir `QUICK_START.md` et commencer! 🚀

