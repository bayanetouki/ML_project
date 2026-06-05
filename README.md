# Breast Cancer Classification — Machine Learning Project

**Projet de fin de semestre** — Module : Machine Learning & Data Mining  
**Réalisé par :** Bayane TOUKI | **Encadré par :** Prof. Fahd Kalloubi

---

## Description

Ce projet applique et compare 6 algorithmes de classification supervisée sur le dataset **Breast Cancer Wisconsin** afin de prédire si une tumeur est maligne ou bénigne. L'objectif est d'identifier le modèle le plus performant pour ce problème de diagnostic médical binaire.

---

## Dataset

**Breast Cancer Wisconsin (Diagnostic)**

- Source : `sklearn.datasets.load_breast_cancer()`
- 569 exemples — 30 features numériques
- 2 classes : Maligne (0) / Bénigne (1)
- Split : 80% entraînement (455 exemples) / 20% test (114 exemples) avec stratification

---

## Prétraitement

| Etape         | Détail                                                                                               |
| ------------- | ---------------------------------------------------------------------------------------------------- |
| Séparation    | `train_test_split` avec `stratify=y` (80/20)                                                         |
| Normalisation | `StandardScaler` (moyenne=0, écart-type=1) — fit uniquement sur le train pour éviter le data leakage |

---

## Algorithmes implémentés

| #   | Algorithme          | Paramètres clés                         |
| --- | ------------------- | --------------------------------------- |
| 1   | Decision Tree       | `max_depth=5`, critère Gini             |
| 2   | Random Forest       | `n_estimators=100`, bagging             |
| 3   | Logistic Regression | `max_iter=10000`, log-loss              |
| 4   | KNN                 | `k=5`, distance Euclidienne             |
| 5   | SVM Linéaire        | `kernel='linear'`                       |
| 6   | AdaBoost            | `n_estimators=100`, boosting séquentiel |

---

## Résultats

| Rang | Algorithme          | Accuracy (Test) | Cross-Val 5-fold |
| ---- | ------------------- | :-------------: | :--------------: |
| 1    | Logistic Regression |     98.25%      |      98.02%      |
| 2    | SVM Linéaire        |     97.37%      |      96.70%      |
| 3    | Random Forest       |     95.61%      |      95.38%      |
| 3    | AdaBoost            |     95.61%      |      97.36%      |
| 3    | KNN (k=5)           |     95.61%      |      96.70%      |
| 4    | Decision Tree       |     92.11%      |      93.19%      |

**Meilleur modèle : Logistic Regression (98.25%)**

La Régression Logistique atteint la meilleure performance, confirmant l'adéquation d'un modèle linéaire pour ce dataset bien normalisé. Le SVM Linéaire tire profit de la séparabilité quasi-linéaire des classes dans l'espace de 30 dimensions.

---

## Importance des Features (Random Forest)

Les variables les plus discriminantes sont les worst values des caractéristiques géométriques : `worst radius`, `worst perimeter` et `worst area`. Ces résultats sont médicalement cohérents : les tumeurs malignes tendent à présenter des cellules de grande taille aux contours irréguliers.

---

## Utilisation

Le notebook est conçu pour **Google Colab**. Aucune installation locale n'est nécessaire.
Toutes les bibliothèques utilisées (`numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`) sont disponibles par défaut dans Google Colab.
