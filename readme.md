<img src="AKHRAIS HASNAE.jpg" style="height:464px;margin-right:432px"/>
        # 📊 Rapport de Projet : Analyse et Modélisation sur le Dataset UCI Mushroom
# 📊 Rapport de Projet — Modélisation & Analyse de Données

## Projet 3 — Hasnae Akhrais

---

## 1. Introduction

### 🎯 Contexte

Ce projet s’inscrit dans le cadre d’un travail de modélisation prédictive visant à analyser un jeu de données dont l’objectif principal est de construire un modèle performant capable de prédire une variable cible à partir de données numériques et catégorielles.

L’analyse est orientée machine learning et comprend exploration, nettoyage, traitement, entraînement et évaluation de plusieurs modèles.

### ❓ Problématique

Comment transformer un dataset brut, contenant des valeurs manquantes, des variables de types différents et potentiellement du bruit, en un modèle prédictif fiable et généralisable ?

### 🎯 Objectifs

* Comprendre la structure du dataset via une **analyse exploratoire (EDA)**.
* Appliquer un **prétraitement rigoureux** : imputation, encodage, standardisation.
* Comparer différents **algorithmes de machine learning**.
* Évaluer les performances via des **métriques adaptées** (Accuracy, F1-score, ROC-AUC, RMSE).
* Identifier les **erreurs** du modèle et discuter de ses limites.

---

## 2. Méthodologie

### 🧼 2.1 Nettoyage & Prétraitement

✔ **Imputation KNN**
Le choix du `KNNImputer` pour les variables numériques se justifie par sa capacité à reconstruire les valeurs manquantes en se basant sur la similarité des observations. Contrairement à une moyenne ou médiane, KNN préserve mieux la structure multivariée.

✔ **Encodage des variables catégorielles**
Les modèles nécessitant des entrées numériques, un encodage (One-Hot Encoding ou équivalent) a été appliqué.
Ce choix garantit que les relations non ordinales entre catégories ne sont pas mal interprétées.

✔ **Standardisation**
La normalisation des variables numériques a été appliquée afin d’améliorer les performances de modèles sensibles à l’échelle (KNN, SVM, régression logistique…).

---

### 🤖 2.2 Choix des Algorithmes

Plusieurs modèles ont été testés pour comparer différents comportements :

* **Régression Logistique** → baseline robuste, interprétable, adaptée aux problèmes linéaires.
* **Random Forest / XGBoost** → modèles plus puissants, capables de gérer des relations non linéaires.
* **KNN** → benchmark simple basé sur la proximité.
* **SVM** → performant sur les datasets propres et bien standardisés.

Le choix final du modèle se base sur la validation croisée, l’analyse des métriques et la capacité du modèle à généraliser.

---

### 🧪 2.3 Validation & Optimisation

* Utilisation de **KFold** pour réduire la variance de l’évaluation.
* Recherche d’hyperparamètres via **GridSearchCV**.
* Séparation standard en **train/test** pour mesurer la performance finale.

---

## 3. Résultats & Discussion

### 📈 3.1 Métriques de performance

Selon les résultats obtenus dans le notebook, les métriques principales incluent :

* **Accuracy** : mesure globale de bonnes prédictions.
* **F1-Score** : pertinent en cas de classes déséquilibrées.
* **ROC-AUC** : évalue la capacité discriminative du modèle.
* **RMSE** (si applicable à un modèle de régression).

Les modèles d’ensemble (Random Forest, XGBoost) tendent généralement à obtenir les meilleurs scores grâce à leur robustesse et leur capacité à capturer des relations complexes.

---

### 🧩 3.2 Analyse des erreurs

L’analyse de la **matrice de confusion** met en évidence :

* Les types d’erreurs les plus fréquents (faux positifs / faux négatifs).
* Les classes que le modèle a du mal à distinguer.

Cela permet d’identifier :

* Les caractéristiques mal apprises.
* La nécessité potentielle d’un rééquilibrage (SMOTE, pénalisation…).
* Des pistes d’amélioration de la qualité des données.

---

## 4. Conclusion

### ✔️ Limites du Modèle

* Sensibilité possible aux valeurs aberrantes malgré l’imputation.
* Performances dépendantes de la qualité du preprocessing.
* Difficulté à généraliser si les données sont déséquilibrées ou insuffisantes.
* Risque de surapprentissage avec certains modèles complexes (Random Forest, XGBoost).

### 🚀 Pistes d’Amélioration

* Tester d’autres techniques d’équilibrage de classes.
* Ajouter une sélection ou extraction de features (PCA, tests statistiques).
* Collecter davantage de données ou enrichir les variables.
* Tester des modèles plus récents (LightGBM, CatBoost).
* Optimiser plus finement les hyperparamètres.

---

## 🖋️ Auteur

Projet réalisé par **Hasnae Akhrais** dans le cadre du Projet 3.


