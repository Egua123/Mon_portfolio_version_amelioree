# 📚 TP2 – INF5081  
## CBIR – Système de recherche d’images par contenu (Deep Learning + K-Means)

Ce projet est une implémentation complète d'un système de recherche d'images par contenu (CBIR) à l'aide de modèles de réseaux de neurones pré-entraînés (VGG16, ResNet50, InceptionV3) et de clustering K-Means.

---

## 🏗️ Structure du projet

```
INF5081_FINAL/
├── app/                  # Interface utilisateur Streamlit
├── data/                 # Dossier contenant les images d'entrée
├── models/               # Fichiers .pkl et .npy (base de données offline)
├── src/                  # Code source : extraction, clustering, distance
├── offline_pipeline.py   # Script de lancement de la phase offline
├── README.md             # Ce fichier
└── env310/               # Environnement virtuel Python (à ignorer)
```

---

## ⚙️ Installation locale sans `requirements.txt`

### ✅ macOS (via Homebrew + Python 3.10)

```bash
# Aller dans le dossier du projet
cd ~/Documents/INF5081_FINAL

# Installer Python 3.10 (si non déjà fait)
brew install python@3.10

# Créer l’environnement virtuel
/opt/homebrew/opt/python@3.10/bin/python3.10 -m venv env310

# Activer l’environnement
source env310/bin/activate

# Mettre à jour pip
pip install --upgrade pip

# Installer les dépendances une à une
pip install tensorflow
pip install keras
pip install scikit-learn
pip install scipy
pip install Pillow
pip install streamlit
pip install matplotlib
pip install notebook
```

---

### ✅ Windows (via PowerShell ou CMD)

```powershell
# Aller dans le dossier du projet
cd C:\Users\TonNom\Documents\INF5081_FINAL

# Créer l’environnement virtuel
python -m venv env310

# Activer l’environnement
.\env310\Scripts\activate     # PowerShell
# ou
.\env310\Scripts\activate.bat # CMD

# Mettre à jour pip
python -m pip install --upgrade pip

# Installer les dépendances
pip install tensorflow
pip install keras
pip install scikit-learn
pip install scipy
pip install Pillow
pip install streamlit
pip install matplotlib
pip install notebook
```

---

## 🔁 Génération de la base de données (Phase Offline)

Avant d’utiliser l’interface, il faut extraire les vecteurs de caractéristiques et appliquer K-Means sur les images du dossier `data/`.

```bash
python offline_pipeline.py
```

Cela crée, pour chaque modèle (VGG16, ResNet50, InceptionV3), un fichier `.pkl` et un fichier `.npy` dans le dossier `models/`.

---

## 🌐 Lancement de l'interface web (Phase Online)

```bash
# macOS / Linux
PYTHONPATH=. streamlit run app/interface.py

# Windows (PowerShell)
$env:PYTHONPATH = "."; streamlit run app/interface.py

# Windows (CMD)
set PYTHONPATH=. && streamlit run app/interface.py
```

---

## 🧪 Fonctionnalités

- 📥 Téléversement d'une image requête
- 🧠 Choix du modèle de descripteur (VGG16, ResNet50, InceptionV3)
- 📏 Choix de la métrique de distance (Euclidean, Manhattan, Chebyshev, Canberra)
- 🖼️ Affichage des images les plus proches
- 📊 Visualisation d’un histogramme des labels parmi les résultats

---

## 🗃️ Exemples de résultats

> Images retournées avec leur distance et leur label de cluster, accompagnées d’un histogramme de distribution des labels.

---

## 📝 Auteurs

- Edmond AWOUSSI 
- Mario ... 
- INF5081 — Analyse et gestion de données  
- Université du Québec à Montréal — 2025

---

## ❗ À ne pas versionner (contenu recommandé pour `.gitignore`) (Ne s'applique pas; on n'utilise pas git)

```gitignore
env310/
__pycache__/
*.pyc
*.pkl
*.npy
.DS_Store
data/
.ipynb_checkpoints/
temp_query.*
```

---

