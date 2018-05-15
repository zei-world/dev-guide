# Déroulé du développement

Pour suivre ce déroulé, vous aurez besoin de cloner le dépôt GitLab hébergeant le code source de la plateforme. Si vous n'avez pas accès à ce dépôt... vous ne pourrez bien évidement pas exécuter ce qui va suivre.

## Trouver son identifiant
- Récupérez le numéro de l'identifiant de la Merge Request (!42 par exemple, le "!" faisant référence à une MR)
- Ajoutez en préfixe la lettre A si la MR est marquée avec le label "hotfix" ou la lettre R si la MR est marquée avec le label "feature"
- Vous obtenez alors A42 pour un _hotfix_ ou R42 pour une _feature_

## Récupérer sa branche
- Dans votre espace de travail, exécutez la commande `./bin/zei git:pull [ID]`
- Si la branche n'existe pas, elle sera créée avec le nom _hotfix/A42_ ou _feature/R42_
- Si elle existe déjà, vous récupérerez les dernières modifications
- Si pendant le développement vous voulez récupérer des modifications des autres, utilisez cette commande

## Développer sur sa branche
- Décomposez votre travail en différents commits de manière à diviser la logique de votre développement
- Précisez toujours dans la MR ce que vous faites et ce que vous avez fait en commentaire
- Vous pouvez même créer des issues dans le même dépôt pour vos tâches ou lancer un sujet à propos de la MR
- Pour utiliser les listes, marquez une tâche par ligne précédée de "* [ ] "
- Pour lier une issue à une MR, n'oubliez de mentionner l'identifiant de l'issue dans vos commits (!42)
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
- Allez sur la page de la Merge Request concernée
- Ajoutez le label "release" pour indiquer que le code est prêt pour une release
- Ajoutez le label "begonia" si votre code est en pré-production et doit être testé

## Etape finale
- Pour _review_ une MR, il faut y laisser un :thumbsup: ou un :thumbsdown:, n'hésitez pas à aussi écrire des commentaires
- Pour un hotfix, une fois qu'une personne a effectué une _review_, pour pouvez _merge_ la MR
- Pour une feature les _reviews_ sont à effectuer mais vous ne devez pas _merge_ la MR
- Soyez attentifs à vos notifications GitLab pour effectuer les _reviews_ des autres
- Pour connaitre les reviews à effectuer, cherchez les MR avec un label "release"
