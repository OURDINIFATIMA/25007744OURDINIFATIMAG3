# Projet F1 — Risque de crédit en Allemagne

**Cours :** BD & DS — S7, ENCG 2026  
**Sujet :** F1 — Risque de crédit en Allemagne  
**Tâche :** classification binaire à coûts asymétriques  
**Algorithme principal prévu :** Régression logistique (`LogisticRegression`, algorithme 8 du support)

## Objectif
Étudier si les caractéristiques d'un demandeur de crédit permettent de distinguer les profils classés « bon risque » et « mauvais risque », en tenant compte du coût plus élevé d'un mauvais client classé à tort comme bon.

## Structure
- `data/raw/` : fichier original téléchargé depuis UCI (à ajouter).
- `data/processed/` : données préparées pendant la séance d'examen.
- `docs/` : fiche du sujet et références.
- `notebooks/` : notebook de travail à créer pendant l'épreuve.
- `figures/` : graphiques produits pendant l'épreuve.
- `rapport/` et `presentation/` : exports finaux.

## Données
Source : UCI Machine Learning Repository, Statlog (German Credit Data), ID 144.  
Le jeu contient 1 000 observations et 20 variables explicatives. La cible distingue les risques bons (1) et mauvais (2). Le jeu ne comporte pas de valeurs manquantes déclarées par UCI.

**Action avant la séance :** télécharger `german.data` depuis la page UCI indiquée dans `docs/fiche_sujet_F1.md` et le placer dans `data/raw/`. Noter la date réelle du téléchargement.

## Règle d'examen
Conformément aux consignes, aucun code d'analyse ni résultat de modèle n'est préparé avant la séance. Le notebook sera réalisé pendant les deux heures de l'épreuve.
