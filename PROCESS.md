# Déroulé du développement

Pour suivre ce déroulé, vous aurez besoin de cloner le dépôt GitHub hébergeant le code source de la plateforme. Si vous n'avez pas accès à ce dépôt... vous ne pourrez bien évidement pas exécuter ce qui va suivre.

## Trouver son identifiant
- Récupérez le numéro de l'identifiant de la Pull Request (#42 par exemple)
- Ajoutez en préfixe la lettre A si la PR est marquée avec le label "hotfix" ou la lettre R si la PR est marquée avec le label "feature"
- Vous obtenez alors A42 pour la _hotfix_ ou R42 pour une _feature_

## Récupérer sa branche
- Dans votre espace de travail, exécutez la commande `./bin/zei git:pull [ID]`
- Si la branche n'existe pas, elle sera créée avec le nom _hotfix/A42_ ou _feature/R42_
- Si elle existe déjà, vous récupérerez les dernières modifications
- Si pendant le développement vous voulez récupérer des modifications des autres, utilisez cette commande

## Développer sur sa branche
- Créez des issues pour vos tâches, vous pourrez les regrouper en une seule avec des listes de tâches
- Décomposez votre travail en différents commits de manière à diviser la logique de votre développement
- Pour utiliser les listes, marquez une tâche par ligne précédée de "- [ ] "
- Pour lier une issue à une PR, n'oubliez de mentionner l'identifiant de l'issue dans vos commits (#42)
- pour fermer une issue depuis un commit, écrivez "closes" avant l'identifiant de l'issue

## Envoyer sa branche
- Il est recommandé de régulièrement envoyer ses commits avec la commande `./bin/zei git:publish [ID]`
- Si d'autres développeurs ont besoin de vos commits, utilisez cette commande
- Si vous souhaitez tester votre code en pré-production, utilisez `./bin/zei begonia [ID]`

## Terminer sa branche
- Une fois le développement terminé et les commits écrits, exécutez `./bin/zei git:finish [ID]`
- Votre branche sera envoyée et votre espace de travail sera nettoyé
- S'il s'agit d'une _feature_, on vous proposera d'envoyer votre code en pré-production

## Lancer la révision de code
- allez vous la page de la Pull Request concernée
- ajoutez le label "release" pour indiquer que le code est prêt pour une release
- ajoutez le label "begonia" si votre code est en pré-production et doit être testé
- dans le champ Reviewers cliquez sur "zei-world/devs"

## Etape finale
- pour un hotfix, une fois qu'une personne a effectué une _review_, pour pouvez _merge_ la PR
- pour une feature les _reviews_ sont à effectuer mais vous ne devez pas _merge_ la PR
- soyez attentifs à vos notifications GitHub pour effectuer les reviews des autres
- pour connaitre les reviews à effectuer, cherchez les PR avec un label "release"
