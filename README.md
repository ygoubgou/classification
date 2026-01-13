# Prédiction du Défaut de Paiement (UCI Credit Card)

[cite_start]Ce projet de Machine Learning a été réalisé dans le cadre du cours **Applied Statistical Learning** à l'**ENSAE Paris**[cite: 1, 8]. [cite_start]Il vise à analyser et modéliser le risque de défaut de paiement pour les porteurs de cartes de crédit, un enjeu critique pour la stabilité financière des banques[cite: 12].

## 📊 Présentation du Projet
[cite_start]L'étude s'appuie sur un échantillon de **30 000 clients** d'une banque taïwanaise (données de 2005)[cite: 13]. Le jeu de données présente un déséquilibre de classe important :
* **77,88%** de clients sans défaut.
* [cite_start]**22,12%** (5 529 individus) en situation de défaut[cite: 14].

[cite_start]Le projet compare 4 modèles pour identifier le plus performant à détecter les profils à risque[cite: 114].

## Méthodologie
### 1. Analyse et Prétraitement
* [cite_start]**Variables :** 23 prédicteurs incluant le plafond de crédit, l'historique des paiements, le montant des factures et les données démographiques[cite: 18, 19].
* [cite_start]**Encodage :** Application du *one-hot encoding* pour les variables catégorielles[cite: 102].
* [cite_start]**Standardisation :** Les variables numériques ont été centrées-réduites pour stabiliser les algorithmes[cite: 102].
* [cite_start]**Séparation :** Division en ensembles d'entraînement (80%) et de test (20%)[cite: 101].

### 2. Métrique de Performance
[cite_start]Compte tenu du déséquilibre des classes, l'**Accuracy** est jugée peu informative[cite: 105]. [cite_start]L'évaluation privilégie le **Rappel (Recall)** afin de maximiser la détection des clients réellement en défaut, même au détriment de la précision globale[cite: 104, 107].

## Résultats et Modélisation
[cite_start]La **Forêt Aléatoire** a été sélectionnée comme le modèle final suite à une optimisation par *Grid Search* et validation croisée[cite: 181, 183, 189].

| Modèle | Accuracy | Rappel (Défaut) | Précision (Défaut) |
| :--- | :--- | :--- | :--- |
| **Forêt Aléatoire** | **0.813** | **0.365** | **0.632** |
| XGBoost | 0.817 | 0.359 | 0.660 |
| Réseau de Neurones | 0.794 | 0.344 | 0.555 |
| Régression Logistique | 0.809 | 0.244 | 0.692 |

[cite_start][cite: 117]

## 🔍 Facteurs Clés de Prédiction
[cite_start]L'analyse de l'importance des variables montre que les facteurs financiers priment sur les données sociales[cite: 220, 227]:
1. **Statut de paiement (septembre) :** Le prédicteur le plus puissant. [cite_start]Un retard récent augmente drastiquement la probabilité de défaut[cite: 217].
2. [cite_start]**Âge et Plafond de crédit :** Variables discriminantes majeures[cite: 218, 227].
3. [cite_start]**Variables démographiques :** Le sexe, l'éducation et l'état civil n'ont qu'une contribution marginale[cite: 219].



## 🎓 Auteurs
* [cite_start]**BRILLET Gurvann** & **GOUBGOU Yamba Arsène** [cite: 4]
* [cite_start]**Superviseur :** Prof. DALALYAN Arnak [cite: 9]
* [cite_start]**Institution :** ENSAE Paris - Institut Polytechnique de Paris [cite: 5, 6, 7]
* [cite_start]**Date :** Janvier 2026 [cite: 10]