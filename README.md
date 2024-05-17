# Analyse de la Satisfaction des Passagers Aériens

Ce projet a pour objectif d'analyser les facteurs influençant la satisfaction des passagers aériens en utilisant l'analyse de variance (ANOVA). Nous nous concentrons sur plusieurs variables telles que le genre, le type de client, le type de voyage et la classe de vol.

## Questions de Recherche
1. Y a-t-il une différence significative de la satisfaction des passagers en fonction du genre ?
2. Existe-t-il une variation significative de la satisfaction des passagers en fonction du type de client (client fidèle ou client déloyal) ?
3. La satisfaction des passagers varie-t-elle en fonction du type de voyage (voyage d'affaires ou de loisirs) ? Y a-t-il une différence significative de la satisfaction des passagers en fonction de la classe de vol (économique ou affaires) ?
4. Existe-t-il une variation significative de la satisfaction des passagers en fonction de la compagnie aérienne (peut-être à partir de l'ID) ?

## Prétraitement des Données
Les étapes suivantes ont été suivies pour le prétraitement des données :
1. Importation des bibliothèques nécessaires.
2. Chargement des données à partir du fichier CSV.
3. Vérification et imputation des valeurs manquantes.
4. Suppression des colonnes non nécessaires.

## Installation

1. Clonez ce dépôt :
    bash
    git clone https://github.com/votre-utilisateur/votre-depot.git
    
2. Installez les dépendances :
    bash
    pip install -r requirements.txt
    

## Utilisation

1. Placez le fichier de données test.csv dans le même répertoire que le notebook ou le script Python.
2. Exécutez le notebook analyse_satisfaction.ipynb pour reproduire l'analyse.

## Exemple de Code
Voici un extrait de code pour charger et prétraiter les données :

```python
import pandas as pd
import numpy as np
from sklearn.impute import SimpleImputer

# Chargement des données
data = pd.read_csv("test.csv")

# Vérification des valeurs manquantes
print(data.isnull().sum())

# Imputation des valeurs manquantes avec la moyenne
mean_arrival_delay = data['Arrival Delay in Minutes'].mean()
data['Arrival Delay in Minutes'].fillna(mean_arrival_delay, inplace=True)

# Suppression des colonnes non nécessaires
data.drop("Unnamed: 0", axis=1, inplace=True)
