# Breast Cancer Classification — Machine Learning Project

Projet réalisé dans le cadre du module **Machine Learning & Data Mining**.

## Description

Ce projet compare plusieurs algorithmes de classification supervisée afin de prédire si une tumeur est **maligne** ou **bénigne** à partir du dataset **Breast Cancer Wisconsin (Diagnostic)**.

L'objectif est d'évaluer les performances de différents modèles et d'identifier celui offrant la meilleure précision pour ce problème de classification binaire.

## Dataset

* Dataset : Breast Cancer Wisconsin (Diagnostic)
* Source : `sklearn.datasets.load_breast_cancer()`
* 569 observations
* 30 variables numériques
* 2 classes : Maligne / Bénigne
* Répartition : 80 % entraînement, 20 % test

## Prétraitement

* Division des données avec stratification
* Normalisation des variables avec `StandardScaler`
* Validation croisée à 5 folds pour évaluer la robustesse des modèles

## Algorithmes évalués

* Decision Tree
* Random Forest
* Logistic Regression
* K-Nearest Neighbors (KNN)
* Support Vector Machine (SVM)
* AdaBoost

## Résultats

| Algorithme          | Accuracy |
| ------------------- | -------- |
| Logistic Regression | 98.25 %  |
| SVM Linéaire        | 97.37 %  |
| Random Forest       | 95.61 %  |
| AdaBoost            | 95.61 %  |
| KNN                 | 95.61 %  |
| Decision Tree       | 92.11 %  |

### Meilleur modèle

**Logistic Regression** obtient la meilleure performance avec une précision de **98.25 %** sur l'ensemble de test.

Les résultats montrent qu'un modèle linéaire est particulièrement adapté à ce dataset, les classes étant presque linéairement séparables après normalisation.

## Analyse des Features

L'analyse de l'importance des variables avec Random Forest met en évidence :

* Worst Radius
* Worst Perimeter
* Worst Area

comme les caractéristiques les plus influentes dans la prédiction.

## Technologies utilisées

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn

## Exécution

Le projet a été exécuté directement sur **Google Colab**.

Aucune installation supplémentaire n'est nécessaire.

## Auteur

**Bayane TOUKI**

**Encadrant : Prof. Fahd Kalloubi**
