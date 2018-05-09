# Développement back-end (Symfony)

### Encodage
- Vous **devez** utiliser `UTF-8` sans `BOM` pour l'encodage des fichiers.
- Vous **devez** laisser une ligne vide à la fin de chaque fichier

### Tags
Vous **ne devez pas** utiliser :
- de tags de fermeture PHP `?>`
- les tags courts tels que `<?`, `<%`, `<%=` ou `%>`

### Indentation et lignes
- Les indentations doivent être de **4 espaces**.
- Chaque ligne de code ne doit pas dépasser **120 charactères**.
- Il ne doit y avoir qu'une seule déclaration par ligne, et une seule propriété par déclaration.
- Il ne doit pas y avoir d'espaces à la fin d'une ligne.

### Exemple de code
```php
<?php

namespace Bundle\Acme;

use Bundle\BiduleInterface;
use Bundle\Truc;

/**
 * Description de la classe
 */
class Zei extends Truc implements BiduleInterface
{
    const UNE_CONSTANTE = 42;

    /**
     * @var string
     */
    private $begonia;


    /**
     * @param string $parametre description du parametre
     */
    public function __construct($parametre)
    {
        $this->begonia = $parametre;
    }

    /**
     * @return string
     */
    public function getBegonia()
    {
        return $this->begonia;
    }

    /**
     * Fait des choses étranges à une chaine de caractères
     *
     * @param bool|string $chaine Une chaine de caractères à modifier
     *
     * @return string|null La chaine transformée
     *
     * @throws \Exception Quand la chaine est problématique
     */
    private function bidouilleTexte($chaine)
    {
        if('problematique' === $chaine) {
            throw new \Exception(sprintf('Cette chaine est problématique'));
        }

        if('' === $chaine) {
            return null;
        }

        $tableau = [
            'uneValeur' => 'bob',
            'uneAutreValeur' => 'frank',
            'uneDerniereValeurPourLaRoute' => 'donald',
        ];

        if($chaine === $tableau['uneValeur']) {
            return substr($chaine, 0, 5).'nawak';
        }
    }

    /**
     * Exemple de méthode avec un nom long et beaucoup de paramètres
     *
     * @param Type $arg1
     * @param string $arg2
     * @param array arg3
     */
    private function methodeQuiAUnNomTresTresLong(
        Type $arg1,
        $arg2,
        array $arg3 = []
    ) {
        // corps de la méthode
    }
}
```
