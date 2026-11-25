# Notes S3 - BUT Informatique

Petit site pour calculer ses moyennes d'UE du semestre 3 du BUT Info et savoir quelle note il faut avoir dans les matières pas encore notées pour valider chaque UE.

Tout tient dans un seul fichier `index.html` : pas de serveur, pas de compte, pas de base de données.

## Fonctionnalités

- **Synthèse** : une note par matière, et les 6 UE se recalculent en direct (moyenne, jauge avec le seuil de 10, statut).
- **« Il te faut »** : pour chaque UE, la moyenne à avoir sur les matières encore vides pour atteindre 10 (ou 8 si 10 n'est plus possible).
- **Mes notes** : le détail des évaluations de chaque matière (notes, coefs, ajout ou suppression d'évals).
- **Relier à Mes notes** : un interrupteur pour que la Synthèse reprenne automatiquement les moyennes calculées dans Mes notes. Désactivé, les deux parties sont indépendantes.
- **Coefficients modifiables** pour chaque UE, au cas où ils changent.
- **Onglet Semestre 4** prévu (pas encore commencé).
- Responsive : téléphone et PC.

## Utilisation

1. Ouvrir `index.html` dans un navigateur.
2. Rentrer ses notes dans **Synthèse** ou dans **Mes notes**.
3. Lire ce qu'il faut pour chaque UE.

Le site part vide : aucune note n'est pré-remplie. Les notes sont enregistrées seulement dans le navigateur de la personne (`localStorage`). Rien n'est envoyé ailleurs, et chacun ne voit que ses propres notes. Les boutons « Effacer les notes » et « Tout effacer » remettent tout à zéro.

## Mettre en ligne avec GitLab Pages

Ajouter un fichier `.gitlab-ci.yml` à la racine du dépôt :

```yaml
pages:
  stage: deploy
  script:
    - mkdir -p public
    - cp index.html public/
  artifacts:
    paths:
      - public
  rules:
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
```

Après le push, l'adresse du site s'affiche dans **Deploy > Pages** du projet.

## Règle de passage

Pour passer en BUT3 : au moins 4 compétences sur 6 à 10 ou plus et aucune sous 8 (moyenne S3 + S4), et toutes les UE de BUT1 validées. Le site ne calcule que le S3 : vérifiez le règlement de votre IUT.

## Auteur

Arthur Goubill — [github.com/BateauTigre](https://github.com/BateauTigre)
