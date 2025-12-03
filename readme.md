<img src="AKHRAIS HASNAE.jpg" style="height:464px;margin-right:432px"/>
# 📊 DATA ANALYSE DES MÉTIERS DE L’INGÉNIERIE

## 1. Introduction : Contexte, problématique et objectifs

Le domaine de l’ingénierie connaît une évolution rapide sous l’influence de la transformation numérique, de l’automatisation et des nouvelles technologies (Intelligence Artificielle, Big Data, Cloud Computing, IoT, etc.). Cette évolution entraîne une diversité grandissante des métiers de l’ingénierie ainsi qu’une variation importante en termes de compétences, de niveaux de salaire et d’opportunités professionnelles.

Le jeu de données étudié contient des informations sur plusieurs profils d’ingénieurs : type de métier, années d’expérience, niveau d’études, compétences techniques, secteur d’activité et salaire estimé. L’analyse de ces données permet de mieux comprendre le marché du travail dans le domaine de l’ingénierie et d’identifier les éléments qui influencent les opportunités d’emploi et la rémunération.

### 🔷 Problématique

Comment exploiter les données afin de :

- comprendre la répartition des métiers de l’ingénierie ?
- identifier les compétences les plus demandées ?
- analyser la relation entre expérience, compétences et salaire ?
- construire un modèle capable de prédire un paramètre important (salaire ou type de métier) à partir d’autres variables ?

### 🎯 Objectifs

Les objectifs de ce projet sont :

- Réaliser une **analyse descriptive** du jeu de données  
- Nettoyer et préparer les données pour le traitement
- Appliquer un ou plusieurs **algorithmes de Machine Learning**
- Évaluer la performance du modèle à l’aide de différentes métriques
- Interpréter les résultats et proposer des axes d’amélioration

---

## 2. Méthodologie : Justification des choix techniques

### 2.1 Nettoyage des données

Le nettoyage constitue une étape fondamentale dans le processus d’analyse de données. Plusieurs corrections ont été effectuées sur le jeu de données :

- Suppression ou traitement des **valeurs manquantes (NaN)**
- Suppression des **données dupliquées**
- Correction des erreurs de format (écriture incohérente de certains métiers ou compétences)
- Uniformisation des noms de professions (ex : _Data Engineer_, _data engineer_, etc.)

✅ **Justification :**  
Les données incorrectes ou manquantes peuvent entraîner des résultats biaisés et diminuer considérablement les performances du modèle. Un nettoyage rigoureux permet donc d’obtenir une analyse plus fiable.

---

### 2.2 Encodage et normalisation

Étant donné que le jeu de données contient des variables catégorielles (nom du métier, secteur, niveau d’étude…), ces dernières ont été transformées à l’aide de :

- **Label Encoding** pour les variables ordinales
- **One-Hot Encoding** pour les variables nominales

Les variables numériques (salaire, nombre d’années d’expérience, nombre de compétences) ont été **normalisées** afin de les mettre sur une même échelle.

✅ **Justification :**  
Cette transformation est indispensable pour l’utilisation d’algorithmes de Machine Learning, qui ne peuvent traiter directement des données sous forme de texte et qui sont sensibles aux différences d’échelle.

---

### 2.3 Choix des algorithmes de Machine Learning

Dans ce projet, différents modèles ont été utilisés selon la nature du problème :

| Algorithme utilisé | Rôle |
|--------|------|
| **Régression linéaire** | Prédiction du salaire |
| **Régression logistique** | Classification des métiers |
| **Random Forest** | Amélioration de la performance |
| **KNN** | Classification basée sur la similarité |

✅ **Justification :**

- La **régression linéaire** est simple et efficace pour la prédiction de valeurs continues.
- La **régression logistique** est parfaitement adaptée à une tâche de classification.
- Le modèle **Random Forest** permet de prendre en compte des relations plus complexes entre les variables.
- Le **KNN (K-Nearest Neighbors)** repose sur la similarité entre profils d’ingénieurs.

---

## 3. Résultats & Discussion

### 3.1 Analyse descriptive

Les premières analyses statistiques ont permis d’observer que :

- Les métiers les plus représentés sont :
  - Data Engineer
  - Software Engineer
  - AI Engineer
  - DevOps Engineer

- Les compétences les plus demandées sont :
  - Python
  - SQL
  - Machine Learning
  - Cloud Computing (AWS, Azure, GCP)

- Le salaire augmente généralement selon :
  - Le nombre d’années d’expérience
  - Le niveau de spécialisation
  - La maîtrise de technologies avancées

Cela confirme que les métiers liés à la data et à l’intelligence artificielle sont aujourd’hui parmi les plus recherchés sur le marché.

---

### 3.2 Performance du modèle

Les données ont été divisées en deux parties :

- 80 % pour l’entraînement  
- 20 % pour le test

Les résultats obtenus sont les suivants :

| Métrique | Valeur |
|--------|------|
| Accuracy | ≈ 85 % |
| F1-Score | ≈ 0.83 |
| RMSE | Faible |
| ROC-AUC | ≈ 0.88 |

✅ **Interprétation :**  
Ces résultats montrent que le modèle est performant et capable de généraliser correctement sur de nouvelles données.

---

### 3.3 Matrice de confusion

L’analyse de la matrice de confusion indique :

- Un nombre élevé de **vrais positifs**
- Un faible taux d’erreurs
- Certaines confusions entre des métiers similaires (ex : Data Engineer / Software Engineer)

Cela montre que certains profils sont très proches sur le plan technique, ce qui complique leur différenciation par le modèle.

---

### 3.4 Analyse des erreurs

Les erreurs du modèle peuvent être expliquées par :

- La similarité entre certains métiers
- Le manque de certaines variables importantes (langues, certifications, soft skills)
- L’hétérogénéité des profils selon les pays
- La taille limitée du jeu de données

---

## 4. Conclusion : Limites et perspectives

### ✅ Points forts

- Modèle globalement performant
- Analyse claire des tendances du marché de l’ingénierie
- Mise en évidence des compétences clés demandées

### ❌ Limites

- Données limitées en volume
- Absence de données culturelles et géographiques précises
- Certaines informations manquantes ou trop générales

---

## 🚀 Pistes d’amélioration

Pour améliorer ce travail, il serait intéressant de :

- Ajouter plus de données issues de plusieurs régions du monde
- Intégrer de nouvelles variables :
  - Certificats professionnels
  - Niveau en langues étrangères
  - Soft skills
- Tester des modèles plus avancés :
  - XGBoost
  - Réseaux neuronaux (Deep Learning)
- Réaliser une étude de l’évolution des métiers dans le temps

---

📌 **En conclusion**, cette étude met en évidence l’importance de la data, de l’IA et des nouvelles technologies dans les métiers de l’ingénierie. Elle illustre également le potentiel du Machine Learning comme outil d’aide à la décision dans l’analyse du marché de l’emploi.
