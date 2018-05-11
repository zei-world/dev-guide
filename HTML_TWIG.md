# TWIG

## Les variables

Les noms des variables doivent être aussi explicites que possible, et doivent utiliser le camelCase.

## Includes

Lorsqu'on inclus un fichier dans un autre, il est préférable d'isoler ce nouveau template en ne lui donnant
que les variables nécessaires :

```twig
{% include "fichier.html.twig" with {variable:valeur} only %}
```

Ainsi le template `fichier` n'aura accès qu'à `variable`, celà évite les conflits de nom entre les variables et
améliore les performances et la stabilité.

## One Line Block

Pour définir un block vide ou court il est possible de le faire en une seule ligne :

```twig
{% block content %}{% endblock %}
```

sera plutôt écrit

```twig
{% block content "" %}
```

## Documentation

https://twig.symfony.com/doc/2.x/
