# Javascript (côté client)

Les fichiers .js sont tous situés dans le même dossier `/app/Resources/js`.

Nous utilisons Assetic avec YUI Compressor pour compiler les fichiers : ils sont validés, minifiés et enfin regroupés
dans le même fichier s'ils se trouvent sur la même page. Ces fichiers se trouvent dans le dossier `/web/assets/js`.

## Variables
Afin de maximiser la compatibilité des navigateurs, les variables sont toutes déclarées avec `var`.

Les chaînes de caractères doivent être déclarées avec les doubles guillemets `""`.

Le nom des variables doit être explicite, en anglais et dans au format lowerCamelCase.

Terminez votre déclaration par un point virgule `;`.

Evitez de déclarer plusieurs variables d'un coup.

```javascript
var example1 = "Ceci est un exemple";
var longerStringName = "Et là c'en est un autre";
var dont, do = 1, that = 2, please = 3;
```

## Conditions
Les conditions sont écrites comme cela :
```javascript
if(success) { // Toujours utiliser des accolades et effectuer des retours à la ligne
  console.log("Nous y sommes !");
}
```

Utilisez TOUJOURS une vérification du type dans vos comparaisons avec `===` ou `!==`.

## Objets et tableaux
Déclarez-les de la manière suivante :
```javascript
var shortObj = { a: 1, b: 2 }; // Sur une ligne pour les plus courts
var longObj = { // Comme cela pour les plus longs
  firstElement: "Premier élément",
  secondOne: "Second élément",
  lastOne: "Dernier élément"
};

var shortArr = [ "A", "B", 1, 2 ];
var longArr = [
  "Je crois que vous avez compris le principe de cet exemple",
  "Il s'agit du même principe que pour les objets"
];
```

Notez que vous pouvez laisser une virgule à la fin du dernier élément, ce choix est libre.
```javascript
var arr = [
  1,
  2, // <- Cette virgule
];
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
var fn = function() { // Pas de fonctions sous forme d'expression
}; // Pas de point virgule à la fin
```

Optimisez les conditions dans votre fonctions et favorisez les `return` aux `else` dans une condition :
```javascript
// Version non optimisée
function() {
  if(success) {
    if(error.code === 0) {
      return "Tout est OK";
    } else {
      return "Code erreur : " + error.code;
    }
  } else {
    return "Erreur !";
  }
}

// Version optimisée
function() {
  if(!success) { // Ordre respecté
    return "Erreur !";
  }
  if(error.code !== 0) { // Erreurs en premier
    return "Code erreur : " + error.code;
  }
  return "Tout est OK"; // Fonctionnement normal en dernier
}
```

## Opérateur ternaire
Ne l'utiliser que si cela permet un code plus lisible :
```javascript
// Bien
var getStatus = isUserConnected ? ("Connected as " + username) : "Not connected";

// Pas bien (même si c'est plus court et stylé)
var calculate = (a > 0 && b === 1) ? (a - b) : (b < 0 ? 0 : a)
```

## JQuery
La librairie étant installée, vous pouvez accéder a son API avec `$`.

Important : vérifiez toujours que votre code est écrit dans un bloc de démarrage :
```javascript
$(document).ready(function() {
  $("p").text("Hello World");
});
```
