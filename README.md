# Cours Débutant : Machine Learning avec Python et Jupyter Notebook

## Introduction

Le **Machine Learning (ML)** est une branche de l'intelligence artificielle qui permet à une machine d'apprendre à partir des données afin d'effectuer des prédictions ou prendre des décisions sans être explicitement programmée.

### Exemples d'applications

* Prédiction du prix d'une maison
* Détection des emails spam
* Reconnaissance faciale
* Recommandation de produits
* Analyse de fraude bancaire

---

# Chapitre 1 : Installation de Python

## Vérifier si Python est installé

Ouvrez PowerShell :

```powershell
python --version
```

Résultat attendu :

```text
Python 3.13.13
```

Si Python n'est pas installé :

1. Télécharger Python depuis :
   https://www.python.org/downloads/

2. Pendant l'installation, cocher :

```text
Add Python to PATH
```

---

# Chapitre 2 : Installation de UV

## Qu'est-ce que UV ?

UV est un gestionnaire de paquets Python moderne et très rapide qui remplace avantageusement `pip`.

### Installation

```powershell
pip install uv
```

### Vérification

```powershell
uv --version
```

---

# Chapitre 3 : Création d'un environnement virtuel

## Pourquoi utiliser un environnement virtuel ?

Chaque projet Python possède ses propres bibliothèques.

Cela permet :

* d'éviter les conflits de versions
* d'isoler les dépendances
* de faciliter le déploiement

### Création

```powershell
python -m venv myVenv
```

Structure créée :

```text
myVenv/
├── Scripts/
├── Lib/
├── Include/
```

---

# Chapitre 4 : Activation de l'environnement

Sous Windows PowerShell :

```powershell
.\myVenv\Scripts\Activate.ps1
```

Résultat :

```powershell
(myVenv) PS C:\joe>
```

L'apparition de `(myVenv)` indique que l'environnement est actif.

### Vérification

```powershell
python -V
```

Résultat :

```text
Python 3.13.13
```

---

# Chapitre 5 : Installation de Jupyter Notebook

## Qu'est-ce que Jupyter ?

Jupyter Notebook permet :

* d'écrire du code Python
* d'exécuter les cellules indépendamment
* de documenter son travail
* d'afficher des graphiques
* de réaliser des projets de Data Science et Machine Learning

### Installation

```powershell
uv pip install jupyter
```

### Erreur rencontrée

```text
invalid peer certificate: UnknownIssuer
```

### Cause

Le certificat SSL du système n'était pas reconnu.

### Solution

```powershell
uv pip install jupyter --system-certs
```

Installation réussie :

```text
Installed 97 packages
```

Parmi les packages installés :

* jupyter
* notebook
* jupyterlab
* ipykernel
* ipython

---

# Chapitre 6 : Vérification de Jupyter

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

Cela confirme que Jupyter est correctement installé.

---

# Chapitre 7 : Lancer Jupyter Notebook

```powershell
jupyter notebook
```

Résultat :

```text
http://localhost:8888/tree
```

Le navigateur s'ouvre automatiquement.

---

# Chapitre 8 : Création d'un Notebook

Dans l'interface Jupyter :

```text
New
↓
Python 3
```

Un fichier apparaît :

```text
Untitled.ipynb
```

Renommez-le :

```text
premier_notebook.ipynb
```

---

# Chapitre 9 : Premier Programme Python

Créer une cellule :

```python
print("Bonjour Machine Learning")
```

Exécuter :

```text
Shift + Enter
```

Résultat :

```text
Bonjour Machine Learning
```

---

# Chapitre 10 : Les Variables

```python
nom = "Joel"
age = 25

print(nom)
print(age)
```

Résultat :

```text
Joel
25
```

---

# Chapitre 11 : Calculs Simples

```python
a = 10
b = 20

print(a + b)
print(a * b)
print(a / b)
```

Résultat :

```text
30
200
0.5
```

---

# Chapitre 12 : Installation des Bibliothèques Data Science

```powershell
uv pip install numpy pandas matplotlib scikit-learn
```

Bibliothèques installées :

| Bibliothèque | Utilité                 |
| ------------ | ----------------------- |
| NumPy        | Calcul scientifique     |
| Pandas       | Manipulation de données |
| Matplotlib   | Visualisation           |
| Scikit-Learn | Machine Learning        |

---

# Chapitre 13 : NumPy

## Création d'un tableau

```python
import numpy as np

tableau = np.array([1, 2, 3, 4, 5])

print(tableau)
```

Résultat :

```text
[1 2 3 4 5]
```

---

# Chapitre 14 : Pandas

```python
import pandas as pd

data = {
    "Nom": ["Joel", "Marie", "Paul"],
    "Age": [25, 30, 35]
}

df = pd.DataFrame(data)

df
```

Résultat :

| Nom   | Age |
| ----- | --- |
| Joel  | 25  |
| Marie | 30  |
| Paul  | 35  |

---

# Chapitre 15 : Matplotlib

## Premier graphique

```python
import matplotlib.pyplot as plt

x = [1,2,3,4]
y = [2,4,6,8]

plt.plot(x, y)
plt.show()
```

Résultat :

Un graphique est affiché.

---

# Chapitre 16 : Introduction au Machine Learning

Le Machine Learning consiste à apprendre automatiquement à partir des données.

Schéma :

```text
Données (X)
      ↓
Algorithme
      ↓
Prédictions (Y)
```

Exemple :

| Surface | Prix   |
| ------- | ------ |
| 50      | 50000  |
| 100     | 100000 |
| 150     | 150000 |

Le modèle apprend la relation :

```text
Prix = f(Surface)
```

---

# Chapitre 17 : Régression Linéaire

La régression linéaire est l'un des algorithmes les plus simples.

Formule :

```text
y = ax + b
```

Où :

* x = variable d'entrée
* y = résultat à prédire
* a = pente
* b = intercept

---

# Chapitre 18 : Premier Modèle de Machine Learning

```python
from sklearn.linear_model import LinearRegression
import numpy as np

X = np.array([[1],[2],[3],[4],[5]])
Y = np.array([2,4,6,8,10])

model = LinearRegression()

model.fit(X, Y)

prediction = model.predict([[6]])

print(prediction)
```

Résultat :

```text
[12.]
```

Le modèle a appris :

```text
Y = 2X
```

---

# Chapitre 19 : Visualisation de la Régression

```python
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
import numpy as np

X = np.array([[1],[2],[3],[4],[5]])
Y = np.array([2,4,6,8,10])

model = LinearRegression()
model.fit(X, Y)

predictions = model.predict(X)

plt.scatter(X, Y)
plt.plot(X, predictions)

plt.show()
```

---

# Chapitre 20 : Projet Pratique

## Prédiction du prix d'une maison

```python
import numpy as np
from sklearn.linear_model import LinearRegression

surface = np.array([[50],[100],[150],[200]])
prix = np.array([50000,100000,150000,200000])

model = LinearRegression()

model.fit(surface, prix)

prediction = model.predict([[120]])

print(prediction)
```

Résultat :

```text
120000
```

---

# Cycle Complet d'un Projet Machine Learning

```text
1. Collecte des données
        ↓
2. Nettoyage des données
        ↓
3. Analyse des données
        ↓
4. Entraînement du modèle
        ↓
5. Évaluation
        ↓
6. Prédiction
        ↓
7. Déploiement
```

---

# Exercices

## Exercice 1

Créer une variable :

```python
nom = "Joel"
```

Afficher :

```python
print(nom)
```

## Exercice 2

Créer un tableau NumPy :

```python
[10,20,30,40,50]
```

## Exercice 3

Créer un DataFrame :

| Nom   | Salaire |
| ----- | ------- |
| Joel  | 1000    |
| Marie | 1200    |
| Paul  | 1500    |

## Exercice 4

Tracer un graphique :

```python
x = [1,2,3,4,5]
y = [5,10,15,20,25]
```

## Exercice 5

Créer un modèle de régression qui apprend :

```text
Y = 3X
```

Puis prédire :

```text
X = 10
```

---

# Conclusion

Vous savez maintenant :

* Installer Python
* Créer un environnement virtuel
* Installer Jupyter Notebook
* Utiliser NumPy
* Utiliser Pandas
* Créer des graphiques
* Comprendre le Machine Learning
* Réaliser une régression linéaire
* Effectuer des prédictions

## Prochaines étapes

1. Régression multiple
2. Classification
3. KNN
4. Arbres de décision
5. Random Forest
6. Deep Learning
7. TensorFlow
8. PyTorch
9. Déploiement avec FastAPI
10. Intégration avec Next.js

```
```
