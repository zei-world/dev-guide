# Déroulé du développement

Pour suivre ce déroulé, vous aurez besoin de cloner le dépôt GitLab hébergeant le code source de la plateforme. Si vous n'avez pas accès à ce dépôt... vous ne pourrez bien évidement pas exécuter ce qui va suivre.

## Récupérer sa branche
- Dans votre espace de travail, exécutez la commande `./bin/zei git:pull [BRANCHE]`
- `[BRANCHE]` peut être `feature/A42`, `feature/R42`, `hotfix/A42` ou encore `hotfix/R42`
- Si la branche n'existe pas elle sera créée, sinon vous récupérerez les dernières modifications
- Si pendant le développement vous voulez récupérer des modifications des autres, utilisez cette commande

## Développer sur sa branche
- Décomposez votre travail en différents commits de manière à diviser la logique de votre développement
- Précisez toujours dans la MR ce que vous faites et ce que vous faites en commentaire
- Pour utiliser des listes marquez une tâche par ligne précédé de "* [ ] "
- Pour lier une issue à une MR, mentionnez l'identifiant de l'issue dans vos commits (!42)
- pour fermer une issue depuis un commit, écrivez "closes" avant l'identifiant de l'issue

## Envoyer sa branche
- Il est recommandé de régulièrement envoyer ses commits avec la commande `./bin/zei git:publish [BRANCHE]`
- Si d'autres développeurs ont besoin de vos commits, utilisez cette commande
- Si vous souhaitez tester votre code en pré-production, utilisez `./bin/zei begonia [BRANCHE]`

## Terminer sa branche
- Une fois le développement terminé et les commits écrits, exécutez `./bin/zei git:finish [BRANCHE]`
- Votre branche sera envoyée et votre espace de travail sera nettoyé

## Lancer la révision de code
- Allez sur la page de la Merge Request concernée
- Ajoutez le label "release" pour indiquer que le code est prêt pour une release
- Ajoutez le label "begonia" si votre code est en pré-production et doit être testé

## Etape finale
- Pour _review_ une MR, laissez un :thumbsup: ou un :thumbsdown:, accompagnez de commentaires
- Pour un _hotfix_, une fois qu'une personne a effectué une _review_, pour pouvez _merge_ la MR
- Pour une _feature_ les _reviews_ sont à effectuer mais vous ne devez pas _merge_ la MR
- Soyez attentifs à vos notifications GitLab pour effectuer les _reviews_ des autres
- Pour connaitre les reviews à effectuer, cherchez les MR avec un label "release"
