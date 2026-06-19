# Cours Débutant : Machine Learning avec Python et Jupyter Notebook

## Introduction

Le **Machine Learning (ML)** est une branche de l'intelligence artificielle qui permet à une machine d'apprendre à partir des données afin d'effectuer des prédictions ou prendre des décisions sans être explicitement programmée.

### Exemples d'applications

* Prédiction du prix d'une maison
* Détection des emails spam
* Reconnaissance faciale
* Recommandation de produits
* Analyse de fraude bancaire

# Formation Complète : Machine Learning avec Python et Jupyter Notebook

## Objectif du cours

À la fin de cette formation, vous serez capable de :

- Installer Python
- Configurer un environnement de développement
- Utiliser PowerShell
- Créer des environnements virtuels
- Installer des bibliothèques Python
- Utiliser Jupyter Notebook
- Comprendre les bases du Machine Learning
- Réaliser vos premières prédictions avec Scikit-Learn

---

# Partie 1 : Préparation de l'environnement

## Pourquoi préparer un environnement ?

Avant de créer des modèles d'intelligence artificielle, nous devons préparer un environnement de travail propre.

Sans cela :

- Les bibliothèques peuvent entrer en conflit
- Les projets deviennent difficiles à maintenir
- Les erreurs sont plus fréquentes

---

# Étape 1 : Vérifier l'installation de Python

Ouvrez PowerShell :

```powershell
Win + X
→ Terminal (Admin)
```

Vérifiez la présence de Python :

```powershell
python --version
```

ou

```powershell
python -V
```

Résultat attendu :

```powershell
Python 3.13.13
```

### Explication

Cette commande demande à Python d'afficher sa version.

Si vous obtenez :

```powershell
python n'est pas reconnu
```

cela signifie que Python n'est pas installé ou n'est pas dans le PATH Windows.

---

# Étape 2 : Vérifier PIP

PIP est le gestionnaire de paquets officiel de Python.

Il permet d'installer :

- NumPy
- Pandas
- TensorFlow
- Scikit-Learn
- Jupyter

Commande :

```powershell
pip --version
```

Résultat :

```powershell
pip 26.0.1
```

---

# Étape 3 : Installation de UV

## Pourquoi UV ?

UV est :

- Plus rapide que PIP
- Plus moderne
- Plus efficace pour gérer les dépendances

Installation :

```powershell
pip install uv
```

Résultat :

```powershell
Successfully installed uv
```

Vérification :

```powershell
uv --version
```

---

# Partie 2 : Création de l'environnement virtuel

## Pourquoi un environnement virtuel ?

Imaginons :

Projet A :

```text
TensorFlow 2.12
```

Projet B :

```text
TensorFlow 2.18
```

Sans environnement virtuel :

❌ Conflits

Avec environnement virtuel :

✅ Chaque projet possède ses propres bibliothèques

---

# Étape 4 : Créer l'environnement

Créer un dossier de travail :

```powershell
mkdir MachineLearning
```

Entrer dans le dossier :

```powershell
cd MachineLearning
```

Créer l'environnement :

```powershell
python -m venv myVenv
```

### Explication

- python : lance Python
- -m : exécute un module
- venv : module de virtualisation
- myVenv : nom de l'environnement

Arborescence créée :

```text
MachineLearning/
│
├── myVenv/
│   ├── Scripts/
│   ├── Include/
│   └── Lib/
```

---

# Étape 5 : Activer l'environnement

```powershell
.\myVenv\Scripts\Activate.ps1
```

Résultat :

```powershell
(myVenv) PS C:\MachineLearning>
```

### Explication

Lorsque vous voyez :

```text
(myVenv)
```

Python utilise maintenant cet environnement.

Toutes les bibliothèques seront installées ici.

---

# Étape 6 : Vérifier le Python utilisé

```powershell
where python
```

Résultat :

```text
C:\MachineLearning\myVenv\Scripts\python.exe
```

Cela confirme que Python utilise l'environnement virtuel.

---

# Partie 3 : Installation de Jupyter

## Qu'est-ce que Jupyter Notebook ?

Jupyter Notebook est l'outil le plus utilisé en :

- Data Science
- Machine Learning
- Intelligence Artificielle

Il permet :

- d'écrire du code
- d'exécuter du code cellule par cellule
- d'afficher des graphiques
- d'écrire de la documentation

---

# Étape 7 : Installer Jupyter

Commande :

```powershell
uv pip install jupyter
```

Vous avez rencontré l'erreur :

```text
invalid peer certificate: UnknownIssuer
```

### Explication

UV ne faisait pas confiance au certificat SSL utilisé pour accéder à PyPI.

---

# Étape 8 : Corriger l'erreur SSL

Installation avec les certificats système :

```powershell
uv pip install jupyter --system-certs
```

### Explication

Option :

```powershell
--system-certs
```

Demande à UV d'utiliser les certificats Windows.

---

# Étape 9 : Vérifier Jupyter

```powershell
jupyter
```

Résultat :

```text
Available subcommands:
 notebook
 lab
 server
```

---

# Étape 10 : Démarrer Jupyter Notebook

```powershell
jupyter notebook
```

Résultat :

```text
http://localhost:8888/tree
```

### Explication

- localhost = votre ordinateur
- 8888 = port réseau utilisé par Jupyter

Le navigateur s'ouvre automatiquement.

---

# Partie 4 : Installation des bibliothèques de Machine Learning

## NumPy

Manipulation des tableaux numériques.

Installation :

```powershell
uv pip install numpy
```

---

## Pandas

Manipulation des données.

Installation :

```powershell
uv pip install pandas
```

---

## Matplotlib

Création de graphiques.

Installation :

```powershell
uv pip install matplotlib
```

---

## Scikit-Learn

Bibliothèque principale de Machine Learning.

Installation :

```powershell
uv pip install scikit-learn
```

---

# Installation complète en une seule commande

```powershell
uv pip install numpy pandas matplotlib scikit-learn seaborn
```

---

# Partie 5 : Premier Notebook

Créer un notebook :

```text
New
↓
Python 3
```

---

# Premier programme

```python
print("Bonjour Machine Learning")
```

Résultat :

```text
Bonjour Machine Learning
```

---

# Partie 6 : Premier modèle IA

## Importation

```python
import numpy as np
from sklearn.linear_model import LinearRegression
```

---

## Création des données

```python
X = np.array([[1],[2],[3],[4],[5]])
Y = np.array([2,4,6,8,10])
```

Ces données représentent :

| X | Y |
|---|---|
| 1 | 2 |
| 2 | 4 |
| 3 | 6 |
| 4 | 8 |
| 5 | 10 |

---

## Création du modèle

```python
model = LinearRegression()
```

---

## Entraînement

```python
model.fit(X, Y)
```

### Ce que fait fit()

Le modèle cherche la meilleure équation :

```text
Y = aX + b
```

---

## Prédiction

```python
prediction = model.predict([[6]])
```

Affichage :

```python
print(prediction)
```

Résultat :

```text
[12.]
```

Le modèle a compris :

```text
Y = 2X
```

---

# Architecture d'un projet Machine Learning

```text
Données
   ↓
Nettoyage
   ↓
Analyse
   ↓
Entraînement
   ↓
Évaluation
   ↓
Prédiction
   ↓
Déploiement
```

---

# Commandes à retenir

Créer un projet :

```powershell
mkdir MachineLearning
```

Créer un environnement :

```powershell
python -m venv myVenv
```

Activer :

```powershell
.\myVenv\Scripts\Activate.ps1
```

Installer Jupyter :

```powershell
uv pip install jupyter --system-certs
```

Lancer Jupyter :

```powershell
jupyter notebook
```

Installer les bibliothèques ML :

```powershell
uv pip install numpy pandas matplotlib scikit-learn
```

Désactiver l'environnement :

```powershell
deactivate
```
