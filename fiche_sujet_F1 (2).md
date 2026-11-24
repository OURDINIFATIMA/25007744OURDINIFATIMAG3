# Fiche sujet F1 — Risque de crédit en Allemagne

## 1. Présentation du sujet

- **Titre :** Risque de crédit en Allemagne — classification binaire à coûts asymétriques
- **Domaine :** Finance et gestion du risque de crédit
- **Type de problème :** Classification binaire supervisée
- **Algorithme principal envisagé :** Régression logistique (*Logistic Regression*)

## 2. Problématique

Dans quelle mesure les caractéristiques d'un demandeur de crédit, présentes dans le jeu de données Statlog (German Credit Data), permettent-elles de distinguer les dossiers classés comme bons risques des dossiers classés comme mauvais risques, tout en limitant les erreurs de classification les plus coûteuses ?

## 3. Objectifs du projet

- Construire un modèle de classification binaire permettant de prédire le risque de crédit.
- Identifier les caractéristiques associées aux bons et aux mauvais risques.
- Évaluer les performances du modèle à l'aide de plusieurs indicateurs.
- Prendre en compte les coûts asymétriques des erreurs de classification.
- Comparer les résultats du modèle à une règle de référence simple.

## 4. Présentation du jeu de données

- **Nom :** Statlog (German Credit Data)
- **Source :** UCI Machine Learning Repository
- **Lien :** https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data
- **Auteur :** Hans Hofmann (1994)
- **Taille :** 1 000 observations et 20 variables explicatives
- **Fichier brut :** `german.data`

Chaque observation représente un demandeur de crédit. Les variables décrivent notamment sa situation financière, son historique de crédit, son emploi et certaines caractéristiques personnelles.

## 5. Variable cible

La variable cible initiale comporte deux classes :

- **1 :** Bon risque de crédit
- **2 :** Mauvais risque de crédit

Pour faciliter l'analyse, la variable pourra être recodée de la manière suivante :

- **0 :** Bon risque
- **1 :** Mauvais risque

Ce recodage sera documenté dans le notebook.

## 6. Coûts des erreurs de classification

Le jeu de données fournit une matrice de coûts asymétriques :

| Situation | Coût |
|---|---:|
| Un mauvais risque est prédit comme bon risque | 5 |
| Un bon risque est prédit comme mauvais risque | 1 |
| Classification correcte | 0 |

L'objectif est donc de limiter particulièrement les erreurs consistant à accorder un crédit à un demandeur présentant un mauvais risque.

## 7. Méthodologie envisagée

1. Présentation et exploration du jeu de données.
2. Analyse des variables numériques et catégorielles.
3. Préparation des données et traitement des variables.
4. Séparation des données en ensembles d'apprentissage et de test.
5. Construction d'un modèle de régression logistique.
6. Évaluation à l'aide de la matrice de confusion, de l'accuracy, du rappel, du F1-score et du coût total.
7. Étude du seuil de décision afin de tenir compte des coûts asymétriques.
8. Comparaison avec une règle de référence simple.
9. Interprétation des résultats et présentation des limites du modèle.

Le seuil de décision sera choisi à partir des données d'apprentissage ou de validation, puis évalué une seule fois sur les données de test.

## 8. Limites du projet

- Le jeu de données est historique et ne représente pas nécessairement les conditions actuelles du marché du crédit.
- La matrice de coûts constitue une simplification de la réalité économique.
- Les résultats dépendent de la qualité et de la représentativité des données.
- Les prédictions d'un modèle ne doivent pas constituer à elles seules la base d'une décision individuelle d'octroi de crédit.

## 9. Référence bibliographique

Hofmann, H. (1994). *Statlog (German Credit Data).* UCI Machine Learning Repository.

- **DOI :** https://doi.org/10.24432/C5NC77
- **Licence :** CC BY 4.0
