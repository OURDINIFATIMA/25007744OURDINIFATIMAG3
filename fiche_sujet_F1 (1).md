# Fiche sujet F1 — Risque de crédit en Allemagne

## 1. Intitulé
Risque de crédit en Allemagne — classification binaire à coûts asymétriques.

## 2. Contexte et intérêt
Une banque doit évaluer le risque associé à une demande de crédit. Une erreur consistant à accorder un crédit à un client qui présente un mauvais risque peut coûter davantage qu'un refus injustifié d'un bon client. La classification doit donc être interprétée en tenant compte des coûts d'erreur, et pas uniquement de l'exactitude globale.

## 3. Problématique
Dans quelle mesure les caractéristiques d'un demandeur présentes dans le jeu Statlog (German Credit Data) permettent-elles de distinguer les dossiers classés comme bons risques des dossiers classés comme mauvais risques, tout en limitant les erreurs les plus coûteuses ?

## 4. Objectif mesurable
Construire un modèle de classification binaire et évaluer ses décisions à l'aide de la matrice de coûts fournie par UCI. Comparer le modèle à une règle de référence simple. Le seuil de décision devra être choisi sur les données d'apprentissage/validation, puis évalué une seule fois sur le jeu de test. Le seuil et le critère de réussite définitif seront fixés pendant l'épreuve, avant consultation des résultats du test.

## 5. Nature de la tâche
Classification binaire à coûts asymétriques.

## 6. Jeu de données
- **Nom :** Statlog (German Credit Data).
- **Source :** UCI Machine Learning Repository, dataset 144.
- **URL :** https://archive.ics.uci.edu/dataset/144/statlog%2Bgerman%2Bcredit%2Bdata
- **Auteur indiqué :** Hans Hofmann.
- **Référence bibliographique :** Hofmann, H. (1994). *Statlog (German Credit Data)* [Dataset]. UCI Machine Learning Repository. DOI : https://doi.org/10.24432/C5NC77
- **Licence :** Creative Commons Attribution 4.0 International (CC BY 4.0).
- **Taille :** 1 000 observations et 20 variables explicatives.
- **Unité d'observation :** un dossier de demandeur de crédit.
- **Format brut à récupérer :** `german.data`.
- **Période :** données historiques ; la page UCI indique un dépôt en 1994, mais ne précise pas ici une période d'observation complète.
- **Valeurs manquantes :** UCI indique qu'il n'y a pas de valeurs manquantes.
- **Date d'extraction :** à compléter après téléchargement effectif.

## 7. Variable cible
La dernière colonne du fichier `german.data` représente la classe de risque :
- `1` : bon risque de crédit.
- `2` : mauvais risque de crédit.

Pour faciliter l'interprétation, la cible pourra être recodée en `0 = bon risque` et `1 = mauvais risque`, en documentant explicitement ce choix.

## 8. Dictionnaire initial de variables
Les noms ci-dessous sont des noms descriptifs de travail. Le fichier brut UCI utilise des codes d'attributs.

| Variable (attribut UCI) | Description | Type | Unité | Rôle |
|---|---|---|---|---|
| Attribute1 | Statut du compte courant | Catégorielle | Catégories de solde | Explicative |
| Attribute2 | Durée du crédit | Entier | Mois | Explicative |
| Attribute3 | Historique de crédit | Catégorielle | Catégories | Explicative |
| Attribute4 | Objet du crédit | Catégorielle | Catégories | Explicative |
| Attribute5 | Montant du crédit | Entier | Deutsche Mark (DM) | Explicative |
| Attribute6 | Épargne / obligations | Catégorielle | Catégories de solde | Explicative |
| Attribute7 | Ancienneté dans l'emploi actuel | Catégorielle | Tranches d'ancienneté | Explicative |
| Attribute8 | Taux de mensualité rapporté au revenu disponible | Entier | Pourcentage | Explicative |
| Attribute13 | Âge du demandeur | Entier | Années | Explicative |
| Class | Qualité du risque de crédit | Binaire après recodage | 0/1 | Cible |

Le dictionnaire complet (5 à 8 variables principales minimum dans le compte rendu final) sera vérifié avec la documentation UCI et le fichier effectivement téléchargé.

## 9. Algorithme principal envisagé
Régression logistique (`LogisticRegression`, algorithme 8 du support). Elle est adaptée à une classification binaire et fournit des probabilités qui permettent d'étudier plusieurs seuils de décision. Le prétraitement des variables catégorielles et numériques devra être intégré dans un pipeline pour éviter les fuites de données.

## 10. Point d'attention obligatoire
La fiche F1 des consignes signale que le seuil de décision fait partie du livrable. UCI fournit une matrice de coûts : coût 5 lorsqu'un mauvais risque est prédit comme bon, coût 1 lorsqu'un bon risque est prédit comme mauvais, et coût 0 pour une décision correcte. Les lignes représentent les classes réelles et les colonnes les classes prédites (1 = bon, 2 = mauvais).

## 11. Limites à discuter
- Jeu ancien, déposé en 1994 : il ne représente pas nécessairement les pratiques ni les profils actuels des emprunteurs.
- La matrice de coûts simplifie la réalité économique d'une banque.
- Les données ne garantissent pas la représentativité de l'ensemble des demandeurs de crédit.
- Les variables démographiques et personnelles nécessitent une réflexion sur l'équité et l'usage responsable du scoring.
- Une bonne performance statistique ne suffit pas à justifier une décision de crédit individuelle.

## 12. Éléments à réaliser pendant l'épreuve
Exploration descriptive, trois graphiques interprétés, préparation sans fuite de données, séparation apprentissage/validation/test, référence simple, réglage du seuil sur validation, évaluation finale, analyse des erreurs, limites et conclusion. Aucun code d'analyse ni résultat ne doit être préparé avant la séance.
