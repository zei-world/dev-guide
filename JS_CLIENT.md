# Javascript (côté client)

Les fichiers .js sont tous situés dans le même dossier `/app/Resources/js`.

Nous utilisons Assetic avec YUI Compressor pour compiler les fichiers : ils sont validés, minifiés et enfin regroupés
dans le même fichier s'ils se trouvent sur la même page. Ces fichiers se trouvent dans le dossier `/web/assets/js`.

## JQuery
La librairie étant installée, vous pouvez accéder a son API avec `$`.

Important : vérifiez toujours que votre code est écrit dans un bloc de démarrage :
```javascript
$(document).ready(function() {
  $("p").text("Hello World");
});
```

## Variables
Afin de maximiser la compatibilité des navigateurs, les variables sont toutes déclarées avec `var`.

Les chaînes de caractères doivent être déclarées avec les doubles guillemets `""`.

Le nom des variables doit être explicite et dans au format lowerCamelCase.

Terminez votre déclaration par un point virgule `;`.

Evitez de déclarer plusieurs variables d'un coup.

```javascript
var exemple1 = "Ceci est un exemple";
var nomUnPeuPlusLong = "Et là c'en est un autre";
var ne, faites = 1, pas = 2, ceci = 3;
```

## Fonctions
Les fonctions sont déclarées de la manière suivante :
```javascript
// Fonction nommée
function test(a, b) { // Toujours effectuer un retour à la ligne
  return a + b;
}

// Fonction anonyme
function() {
  console.log(test(1, 2)); // Utilisez bien des fonctions déclarées AVANT
}

// A ne pas faire...
var variable = function() { // Pas de fonctions sous forme d'expression
}; // Pas de point virgule à la fin
```

## Conditions
Les conditions sont écrites comme cela :
```javascript
if(success) { // Toujours utiliser des accolades et effectuer des retours à la ligne
  console.log("Nous y sommes !");
}
```
