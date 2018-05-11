# Less & CSS

## Architecture - En cours

Pour le moment les fichiers sont tous dans `app/Resources/less`.
Mais les différentes stratégies utilisés dans le web sont actuellement à l'étude afin de trouver la plus adaptée à ZEI.

## Généralités

Exemple :
```less
.classe {
  propriete: valeur;
  
  .autre-classe {
    propriete: valeur;
  }
}
```
L'indentation est à 2 espaces et les accolades suivent le selecteur.
On va préférer définir toutes les propriétés avant d'ouvrir un nouveau selecteur hérité.
Pour nommer les classes et les variables, on utilisera des noms aussi explicites que possible et avec des tirets `-` 
entre chaque mots.

## Variables

Pour le moment le projet n'utilise aucune variable CSS.

Les variables Less sont elles très utilisées et se déclarent comme ceci:

```less
@nom-de-variable : 15px;
margin-left: @nom-de-variable;
```
Plus d'infos sur les variables et mixins Less :
http://lesscss.org/features/#variables-feature-overview

Pour une meilleur maintenabilité du code, les variables et mixins sont à définir en début de fichier lorsque possible.

Pour les variables de couleur, elles sont à définir dans `app/Resources/less/colors.less`.

## Les selecteurs

Les selecteur sont définis dans l'ordre suivant:
```less
div {

}
#id {

}
.class {

}
```

Pour la maintenabilité du code, il faut éviter autant que possible les selecteurs d'enfant direct `>`,
on va préférer donner un nouveau nom de classe.
```less
.container > div {}
```
devient
```less
.content {}
```

## Les propriétés

Il n'y a pas d'ordre dans lequel définir les propriétés car la perte de temps est supérieur au gain de lisibilité,
cependant il est fortement recommandé de regrouper ensemble les propriétés similaires
(margin-top avec margin-bottom, etc..)

## Les commentaires - En cours

Les commentaires seront revus avec la stratégie d'architecture, mais en attendant, même si les variables et noms
de classes sont censés être explicites, il ne faut pas hésiter à commenter pour décrire des blocs ou du contenu,
pour expliquer des calculs etc...

## Intégrer ses feuilles de style

Afin que les feuilles de style soient compilées et intégrées dans les pages il faut l'indiquer en twig en
spécifiant bien un nom de sortie unique :

```twig
{% stylesheets
    filter='less,?yui_css'
    output='assets/css/nom_du_fichier_css_unique.css'
    '../app/Resources/less/fichier_less_a.less'
    '../app/Resources/less/fichier_less_b.less'
    '../app/Resources/less/fichier_less_c.less' %}
    <link rel="stylesheet" type="text/css" media="screen" href="{{ asset_url }}"/>
{% endstylesheets %}
```

Pour les feuilles de style devant être utilisées sur toutes les pages du projet il faut les nommer 
`zei_nom_explicite.less`
et l'importer dans `zei_main.less` avec la balise d'import
```less
@import "zei_nom_explicite";
```
