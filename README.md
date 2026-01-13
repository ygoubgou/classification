# Prédiction du Défaut de Paiement (UCI Credit Card)

Ce projet de Machine Learning a été réalisé dans le cadre du cours **Applied Statistical Learning** à l'**ENSAE Paris**. Il vise à analyser et modéliser le risque de défaut de paiement pour les porteurs de cartes de crédit, un enjeu critique pour la stabilité financière des banques.

## 📊 Présentation du Projet
L'étude s'appuie sur un échantillon de **30 000 clients** d'une banque taïwanaise (données d'octobre 2005). Le jeu de données présente un déséquilibre de classe important :
* **77,88%** de clients sans défaut.
* **22,12%** (5 529 individus) en situation de défaut.

Le projet compare 4 modèles de Machine Learning pour identifier le plus performant à détecter les profils à risque.

##  Méthodologie
### 1. Analyse et Prétraitement
* **Variables :** 23 prédicteurs incluant le plafond de crédit, l'historique des paiements (avril à septembre), le montant des factures et les données démographiques.
* **Encodage :** Application du *one-hot encoding* pour les variables catégorielles (Sexe, Éducation, État civil).
* **Standardisation :** Les variables numériques ont été centrées-réduites pour stabiliser les algorithmes et assurer la convergence.
* **Séparation :** Division stricte en ensembles d'entraînement (80%) et de test (20%) pour éviter le surapprentissage.

### 2. Métrique de Performance
Le déséquilibre des classes rend l'Accuracy peu informative. L'évaluation privilégie donc le **Rappel (Recall)** afin de maximiser la détection des clients réellement en défaut, ce qui est l'objectif métier prioritaire pour une banque.

##  Résultats et Modélisation
Quatre modèles ont été implémentés : Régression Logistique, XGBoost, Forêt Aléatoire et Réseau de Neurones. La **Forêt Aléatoire** a été sélectionnée comme le modèle final après optimisation par *Grid Search* et validation croisée.

| Modèle | Accuracy | Rappel (Défaut) | Précision (Défaut) |
| :--- | :--- | :--- | :--- |
| **Forêt Aléatoire** | **0.813** | **0.365** | **0.632** |
| XGBoost | 0.817 | 0.359 | 0.660 |
| Réseau de Neurones | 0.794 | 0.344 | 0.555 |
| Régression Logistique | 0.809 | 0.244 | 0.692 |



##  Facteurs Clés de Prédiction
L'analyse de l'importance des variables (Gain d'information) montre que les facteurs financiers priment largement sur les données socio-démographiques :
1. **Statut de paiement (septembre) :** Le prédicteur le plus puissant. Plus un individu accuse de retards ce mois-ci, plus sa probabilité de défaut en octobre est élevée.
2. **Âge et Plafond de crédit :** Jouent un rôle prédominant dans la décision du modèle.
3. **Variables démographiques :** Le genre, l'éducation et l'état civil ne contribuent que marginalement à la prédiction.



## 🎓 Auteurs
* **BRILLET Gurvann** & **GOUBGOU Yamba Arsène**
* **Superviseur :** Prof. DALALYAN Arnak
* **Institution :** ENSAE Paris - Institut Polytechnique de Paris
* **Date :** 9 Janvier 2026