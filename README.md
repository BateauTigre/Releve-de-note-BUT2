# Notes S3 - BUT Informatique

Petit site pour calculer ses moyennes d'UE du semestre 3 du BUT Info et savoir quelle note il faut avoir dans les matières pas encore notées pour valider chaque UE.

Tout tient dans un seul fichier `index.html`. On peut l'utiliser en invité (notes gardées dans le navigateur) ou se connecter avec un compte Supabase pour retrouver ses notes sur tous ses appareils.

## Fonctionnalités

- **Synthèse** : une note par matière, et les 6 UE se recalculent en direct (moyenne, jauge avec le seuil de 10, statut).
- **« Il te faut »** : pour chaque UE, la moyenne à avoir sur les matières encore vides pour atteindre 10 (ou 8 si 10 n'est plus possible).
- **Mes notes** : le détail des évaluations de chaque matière (notes, coefs, ajout ou suppression d'évals).
- **Relier à Mes notes** : un interrupteur pour que la Synthèse reprenne automatiquement les moyennes calculées dans Mes notes. Désactivé, les deux parties sont indépendantes.
- **Coefficients fixes** : ceux des UE et des évaluations prévues ne se modifient pas (seules les évals qu'on ajoute soi-même ont un coef à choisir).
- **Connexion** : au démarrage, choix entre « Se connecter » (email + mot de passe) et « Continuer en tant qu'invité ».
- **Onglet Semestre 4** prévu (pas encore commencé).
- Responsive : téléphone et PC.

## Utilisation

1. Ouvrir `index.html` dans un navigateur.
2. Choisir « Se connecter » ou « Continuer en tant qu'invité ».
3. Rentrer ses notes dans **Synthèse** ou dans **Mes notes**.
4. Lire ce qu'il faut pour chaque UE.

Le site part vide : aucune note n'est pré-remplie.

- **En invité** : les notes restent dans le navigateur (`localStorage`), rien n'est envoyé.
- **Connecté** : les notes sont enregistrées dans Supabase et chacun ne voit que les siennes (Row Level Security). À la première connexion, les notes déjà tapées en invité sont reprises sur le compte. Les boutons « Effacer les notes » et « Tout effacer » remettent tout à zéro.

## Règle de passage

Pour passer en BUT3 : au moins 4 compétences sur 6 à 10 ou plus et aucune sous 8 (moyenne S3 + S4), et toutes les UE de BUT1 validées. Le site ne calcule que le S3 : vérifiez le règlement de votre IUT.

## Auteur

Arthur Goubill — [github.com/BateauTigre](https://github.com/BateauTigre)
