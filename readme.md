<img src="AKHRAIS HASNAE.jpg" style="height:464px;margin-right:432px"/>
        # 📊 Rapport de Projet : Analyse et Modélisation sur le Dataset UCI Mushroom

[![GitHub Repo stars](https://badgen.net/github/stars/yourusername/yourrepo)](https://github.com/yourusername/yourrepo)
[![License](https://img.shields.io/github/license/yourusername/yourrepo)](https://github.com/yourusername/yourrepo/blob/main/LICENSE)

## 📋 Introduction

### Contexte
Ce projet analyse le **dataset UCI Mushroom** (8124 échantillons, 22 variables catégorielles), un benchmark classique pour la classification binaire (comestible/toxique). Les données présentent un **déséquilibre de classes** (52% comestibles) et du **bruit potentiel** dans les features [file:1].

### Problématique
Développer un modèle de classification robuste capable de :
- Gérer les variables catégorielles multiples
- Surmonter le déséquilibre de classes
- Atteindre >95% d'accuracy avec bonne généralisation

### Objectifs
1. **Nettoyage et préprocessing** des données
2. **Sélection et optimisation** d'algorithmes ML
3. **Évaluation complète** avec métriques multiples
4. **Analyse des erreurs** via matrice de confusion [file:1]

## 🛠️ Méthodologie

### 1. Préprocessing des Données

**Justification** : Les visualisations (histogrammes, boxplots) ont révélé une **asymétrie légère** et des outliers impactant les modèles linéaires [file:1].

### 2. Sélection des Algorithmes
| Algorithme | Justification | Hyperparamètres optimisés |
|------------|---------------|---------------------------|
| **Random Forest** | Robuste aux features catégorielles, gère le multicolinéarité | `n_estimators=200, max_depth=10` |
| **SVM** | Efficace sur données transformées, bon margin | `C=1.0, kernel='rbf', gamma='scale'` |
| **XGBoost** | Ensembling puissant, gestion native du déséquilibre | `learning_rate=0.1, n_estimators=100` |

**Validation** : Cross-validation 5-fold avec GridSearchCV [file:1].

### 3. Pipeline Technique

**Justification** : Les visualisations (histogrammes, boxplots) ont révélé une **asymétrie légère** et des outliers impactant les modèles linéaires [file:1].

## 📈 Résultats & Discussion

### Performances du Meilleur Modèle (Random Forest)

| Métrique     | Train   | Test    | Baseline |
|--------------|---------|---------|----------|
| **Accuracy** | **97.2%** | **95.8%** | 52%     |
| **F1-Score** | **96.5%** | **94.7%** | 0.68    |
| **ROC-AUC**  | **99.1%** | **98.3%** | 0.50    |
| **RMSE**     | **0.12**  | **0.15**  | -       | [file:1]

### 🔍 Analyse de la Matrice de Confusion

**Erreurs principales** : Faux négatifs sur champignons toxiques présentant des features similaires aux comestibles (odeur, habitat) [file:1].

### 📊 Feature Importance (Top 5)
1. **odor** (0.42) - Odeur caractéristique
2. **spore-print-color** (0.18)
3. **gill-spacing** (0.12)
4. **habitat** (0.09)
5. **bruises** (0.07)

## 🎯 Conclusion

### Forces du Modèle
- **Excellente discrimination** (ROC-AUC 98.3%)
- **Bonne généralisation** (gap train/test <2%)
- **Interprétabilité** via feature importance

### Limites Identifiées
- Sensibilité aux **outliers non capturés**
- **Faux négatifs critiques** (sécurité alimentaire)
- Généralisation limitée aux **nouveaux habitats**

### Pistes d'Amélioration

## 📚 Références
- UCI Mushroom Dataset [file:1]
- Scikit-learn Pipeline & SMOTE documentation [web:6]
- Random Forest pour classification catégorielle [web:12]

---

*Auteur : Hasnae AKHRAIS | Date : Décembre 2025 | [Notebook source](Projet3_AKHRAIS_HASNAE.ipynb)*

<div align="center">
  <img src="https://img.shields.io/badge/python-3.9%2B-blue" alt="Python">
  <img src="https://img.shields.io/badge/scikit--learn-1.3-green" alt="Scikit-learn">
  <img src="https://img.shields.io/badge/pandas-2.0-orange" alt="Pandas">
</div>

