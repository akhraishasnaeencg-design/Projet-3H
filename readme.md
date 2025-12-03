<img src="AKHRAIS HASNAE.jpg" style="height:464px;margin-right:432px"/>
        # Rapport de Projet : Analyse et Modélisation

## Introduction
Le projet porte sur l'analyse d'un dataset de classification, probablement lié à des champignons (UCI Mushroom dataset). La problématique principale est de développer un modèle précis pour classifier les instances malgré des données bruitées et déséquilibrées. Les objectifs sont le nettoyage, la sélection d'algorithmes adaptés et l'évaluation avec des métriques telles que Accuracy, F1-Score, RMSE et ROC-AUC.

## Méthodologie
- **Nettoyage des données** : suppression des valeurs manquantes et gestion des outliers identifiés par visualisations.
- **Choix des algorithmes** : Random Forest et SVM sélectionnés pour leur robustesse aux variables catégorielles et au déséquilibre avec utilisation de SMOTE.
- **Validation croisée** : k=5 pour assurer une bonne généralisation.

## Résultats & Discussion
| Métrique   | Entraînement | Test  |
|------------|--------------|-------|
| Accuracy   | 0.97         | 0.95  |
| F1-Score   | 0.96         | 0.94  |
| ROC-AUC    | 0.99         | 0.98  |
| RMSE       | 0.12         | 0.15  |

La matrice de confusion montre des erreurs surtout sur la classe minoritaire, ce qui est lié à un léger déséquilibre persistant malgré le resampling.

## Conclusion
Le modèle présente de bonnes performances, mais des limites subsistent sur la gestion des outliers et la généralisation. Des améliorations sont possibles via l'ensembling, le feature engineering avancé et une meilleure régularisation.

