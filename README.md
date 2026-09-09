# ⚡ StreamlitTurbo - Template Pro

> **Template moderne pour développeurs Streamlit** 🎯  
> **Économise 4h de setup sur chaque projet** ⏱️

Template professionnel utilisant **uv** et **pyproject.toml** pour un développement moderne et efficace.

---

## 🎬 **Démarrage Rapide en 3 minutes**

### Prérequis
- Python 3.11+
- [uv](https://github.com/astral-sh/uv) installé (`pip install uv`)
- [just](https://github.com/casey/just) installé (optionnel mais recommandé)
- [Copier](https://copier.readthedocs.io/) installé

#### Installation de Just

**Linux :**
```bash
# Avec le script d'installation (recommandé)
curl --proto '=https' --tlsv1.2 -sSf https://just.systems/install.sh | bash -s -- --to ~/bin

# Avec un package manager
# Debian/Ubuntu
sudo apt install just

# Arch Linux
sudo pacman -S just

# Fedora
sudo dnf install just
```

**Windows :**
```powershell
# Avec Scoop (recommandé)
scoop install just

# Avec Chocolatey
choco install just

# Avec Winget
winget install --id Casey.Just
```

**macOS :**
```bash
# Avec Homebrew
brew install just
```

Pour plus d'options d'installation, consultez la [documentation officielle](https://github.com/casey/just#installation).

### Installation Express

```bash
# 1. Installer Copier
pip install copier
# ou avec uv
uv tool install copier

# 2. Générer votre projet depuis le template
copier copy https://github.com/gpenessot/StreamlitTurbo.git mon-app-streamlit

# 3. Entrer dans le projet
cd mon-app-streamlit

# 4. Setup automatique complet (avec just)
just setup

# 5. Lancer l'application
just run
```

**Alternative sans just :**
```bash
# Avec uv
uv sync
uv run streamlit run main.py

# Ou avec pip
pip install -r requirements.txt
streamlit run main.py
```

---

## 🏗️ **Structure du Projet**

```
mon-app/
├── 📄 main.py                 # Point d'entrée
├── 📄 pyproject.toml          # Gestion des dépendances avec uv
├── 📄 justfile                # Automatisation des tâches
├── 📄 requirements.txt        # Dépendances figées (Streamlit Cloud)
├── 📁 src/mon_app/           # Code source
│   ├── 📁 pages/             # Pages Streamlit
│   ├── 📁 components/        # Composants réutilisables
│   └── 📁 utils/             # Utilitaires
├── 📁 .streamlit/           # Config Streamlit
├── 📁 data/                 # Données d'exemple
└── 📁 tests/                # Tests unitaires
```

---

## ⚡ **Commandes Just**

Le template inclut un `justfile` pour automatiser toutes les tâches courantes :

### Commandes principales
```bash
just setup          # Setup complet du projet
just run            # Lancer l'application
just dev            # Lancer en mode développement
just help           # Voir toutes les commandes
```

### Gestion des dépendances
```bash
just add pandas     # Ajouter une dépendance
just add-dev pytest # Ajouter une dépendance de dev
just sync           # Synchroniser les dépendances
just requirements   # Générer requirements.txt pour déploiement
```

### Maintenance
```bash
just clean          # Nettoyer l'environnement
just reset          # Réinstallation complète
just test           # Lancer les tests
just info           # Infos sur le projet
```

---

## 📦 **Gestion des Dépendances**

### Workflow moderne avec pyproject.toml

Le template utilise **pyproject.toml** comme source de vérité pour les dépendances :

```bash
# Ajouter une nouvelle dépendance
just add plotly

# Ou manuellement avec uv
uv add plotly

# Synchroniser les dépendances
just sync
```

### Déploiement sur Streamlit Cloud

Streamlit Cloud nécessite un **requirements.txt**. Générez-le facilement :

```bash
just requirements
```

Cette commande régénère `requirements.txt` à partir de votre `pyproject.toml`
(`uv export --no-dev --no-hashes --no-emit-project`). Un `requirements.txt`
fonctionnel est déjà livré : la commande sert après chaque ajout de dépendance.

**Important :** 
- ✅ Modifiez toujours `pyproject.toml` (pas `requirements.txt`)
- ✅ Régénérez `requirements.txt` avant chaque déploiement
- ✅ Committez les deux fichiers dans Git

---

## 🎨 **Ce que vous obtenez instantanément**

### ✨ **Architecture Professionnelle**
- ✅ Structure modulaire claire
- ✅ Séparation des préoccupations
- ✅ Composants réutilisables
- ✅ Configuration centralisée

### 📊 **Exemples Fonctionnels**
- ✅ Dashboard Analytics avec KPI
- ✅ Page Paramètres complète
- ✅ Sidebar optionnelle prête à l'emploi
- ✅ Composants charts Plotly
- ✅ 20+ fonctions utilitaires

### 🔧 **Outils Modernes**
- ✅ **uv** pour la gestion des dépendances
- ✅ **pyproject.toml** comme standard
- ✅ **just** pour l'automatisation
- ✅ Configuration Streamlit optimisée (thèmes, polices custom)
- ✅ **ruff** pour le format et le lint
- ✅ **pytest** avec une suite de tests d'exemple

---

## 🚀 **Déploiement**

### Sur Streamlit Community Cloud

1. **Préparez votre repo GitHub**
```bash
# Générez requirements.txt pour le déploiement
just requirements

# Committez tout
git add .
git commit -m "Ready for deployment"
git push
```

2. **Déployez sur Streamlit Cloud**
   - Allez sur [share.streamlit.io](https://share.streamlit.io)
   - Connectez votre repo GitHub
   - Sélectionnez le fichier `main.py`
   - Cliquez sur **Deploy** !

### Sur d'autres plateformes

Le template fonctionne sur toutes les plateformes supportant Python :
- Heroku
- Railway
- Render
- AWS / GCP / Azure

---

## 🎯 **Différences avec la version Pro**

| Fonctionnalité | Version Gratuite 🎭 | **StreamlitTurbo Pro** 🚀 |
|---|---|---|
| **Architecture** | Structure de base | Architecture enterprise |
| **Authentification** | ❌ Non incluse | ✅ Système complet |
| **Déploiement** | ❌ Manuel | ✅ 1-click deploy |
| **Tests** | ⚠️ Exemples de base | ✅ Suite complète |
| **CI/CD** | ❌ Non inclus | ✅ GitHub Actions |
| **Base de données** | ❌ Non incluse | ✅ Connecteurs DB |
| **Monitoring** | ❌ Non inclus | ✅ Analytics intégrés |

**[🔥 Découvrir Streamlit Unleashed](https://www.mes-formations-data.fr/formation/streamlit-unleashed)** - Formation complète avec templates premium

---

## 📚 **Ressources**

- 📖 [Documentation Streamlit](https://docs.streamlit.io)
- 🎨 [Galerie Streamlit](https://streamlit.io/gallery)
- 💬 [Forum Communauté](https://discuss.streamlit.io)
- 🚀 [uv - Gestionnaire Python moderne](https://github.com/astral-sh/uv)
- ⚡ [just - Command runner](https://github.com/casey/just)

---

## 📞 **Support & Contact**

- 📧 **Email** : gael.penessot@gmail.com
- 💼 **LinkedIn** : [Gaël Penessot](https://www.linkedin.com/in/gael-penessot/)
- 🐛 **Issues** : [GitHub Issues](https://github.com/gpenessot/StreamlitTurbo/issues)

---

## 📝 **Licence**

MIT License - Libre d'utilisation et de modification

**Créé avec ❤️ par [Gaël Penessot](https://www.mes-formations-data.fr)**

---

⭐ **Ce template vous aide ?** Donnez-lui une étoile sur GitHub !
