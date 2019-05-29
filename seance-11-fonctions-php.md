# Séance 11 : Fonctions PHP

## Présentations

 Lorsque l’on fait de la programmation, quelque soit le langage, on évite d'écrire plusieurs fois la même chose. En effet, dupliquer le code est une mauvaise pratique qui rend la maintenance et la correction de bugs difficile. Le code se trouvant à plusieurs endroits, il ne faut pas en oublier un lorsque l’on choisit de modifier quelque chose. 

On a déjà rencontré ce concept, les boucles par exemple permettent de faire une même action plusieurs fois, sans avoir à dupliquer le code. Mais cela ne peut se faire qu’a un unique endroit dans votre projet. Si on veut utiliser une même boucle \(par exemple pour afficher une liste de produit\), dans plusieurs pages de votre projet, il faut utiliser les fonctions. Une fonction est une série d’instructions qui effectue des actions et qui retourne une valeur. En général, dès que vous avez besoin d’effectuer des opérations un peu longues dont vous aurez à nouveau besoin plus tard, il est conseillé de vérifier s’il n’existe pas déjà une fonction qui fait cela pour vous. 

{% hint style="info" %}
PHP propose de nombreuses fonctions pour manipuler les tableaux, les chaînes, les dates, ...
{% endhint %}

Et si la fonction n’existe pas, vous avez la possibilité de la créer. Au final, vous n’avez pas forcément besoin de savoir exactement comment la fonction exécute le calcul, vous avez juste besoin de savoir ce dont elle a besoin, et ce qu’elle vous retourne. 

## Appeler une fonction 

L’appel d’une fonction \(existante ou que vous avez écrit\) est simple en PHP. Il suffit d'écrire son nom suivi de parenthèses, et éventuellement de paramètres si la fonction en nécessite. Nous y reviendrons. 

Par exemple pour appeler une fonction `calculVolume`, qui va calculer le volume d’un cube, je vais écrire : 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'appel d\'une fonction" %}
```php
<?php 
calculVolume(); 
?>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
Dans l'état ce code ne produira rien, voire même donnera une erreur. En effet la fonction n’existe pas. Ce n’est pas une fonction existante dans PHP. 
{% endhint %}

Si j’utilise une fonction qui nécessite un paramètre je dois le passer entre les parenthèses 

{% code-tabs %}
{% code-tabs-item title="Appel d\'une fonction avec un paramètre" %}
```php
<?php 
calculVolume(4); 
?> 
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Je peux passer des nombres, du texte ou encore des variables. Si ma fonction nécessite plusieurs paramètres, je dois les passer entre les parenthèses en les séparant par des virgules et en respectant l’ordre dans la documentation \(pour une fonction existante\), ou défini dans sa déclaration. 

{% code-tabs %}
{% code-tabs-item title="Appel d\'une fonction avec plusieurs paramètres" %}
```php
<?php 
fonctionImaginaire(17, 'Vert', true, 41.7, $uneVariable); 

?>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Récupérer le résultat d’une fonction 

Les exemples précédents exécutent des fonctions pour lesquels on ne récupère pas le résultat. On peut supposer que l’affichage, par exemple, se fait dans la fonction. Cependant, il sera souvent intéressant de récupérer le résultat d’une fonction pour l’exploiter dans notre programme. 

Pour cela, on doit stocker ce résultat dans une variable. 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'une fonction dont on récupère la réponse" %}
```php
<?php
$volume = calculVolume(4);
?> 
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ecrire ses fonctions 

Nous savons maintenant comment utiliser une fonction. Vous pouvez explorer la documentation PHP \([php.net](https://www.php.net)\) pour trouver un ensemble de fonction. Cependant il est fréquent d'écrire nos propres fonctions. Ecrivons par exemple la fonction calculVolume que l’on a utilisé précédemment 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'une fonction" %}
```php
<?php 
//définition de la fonction
function calculVolume($cote) 
{ 
    $volume = $cote * $cote * $cote ; 
    echo 'Le volume est de '.$volume.' cm3'; 
} 

//appel de ma fonction 
calculVolume(4);
?> 
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Regardons les lignes 3 à 7. C’est la fonction. En fait, ces lignes permettent de définir la fonction \(son nom, ce qu’elle est capable de faire, etc.\). Elles ne font rien de particulier, mais elles disent a PHP : "Une fonction calculVolume existe maintenant". Si on ne met pas la ligne 10, cette fonction ne servira jamais. 

Pour créer une fonction, vous devez écrire `function`. Ensuite, donnez-lui un **nom**. Par exemple, celle-ci s’appelle `calculVolume`. Il y a ensuite des parenthèses, et ce que l'on mets dans ces parenthèses sont appelés **les paramètres de la fonction,** c'est à dire  une \(ou plusieurs\) variable \(ou même 0. On peut écrire des fonctions sans paramètre\). 

Ces paramètres sont ce que la fonction à besoin pour "travailler", afin qu’elle sache la dimension d’un côt" pour calculer le volume. Notre fonction doit forcément être appel"e avec un paramètre \(il est dans ce cas appelé **paramètre obligatoire**\) sans quoi elle ne pourra pas fonctionner. 

Ensuite, vous repérez des accolades. Elles permettent de marquer les limites de la fonction. Cette dernière commence dès qu’il y a une `{` et se termine lorsqu’il y a une `}` . Entre les deux, il y a son contenu, une suite d'instruction, ce que fait la fonction. Dans cet exemple la fonction contient un `echo`, c’est à dire qu’elle affiche le résultat. On a vu précédemment que parfois on voulait pouvoir récup´erer le résultat pour le manipuler. Dans ce cas, on doit dire à notre fonction de nous renvoyer quelque chose. On utilise alors l’instruction **return**. Cette instruction renvoie à notre programme principal des informations. 

{% hint style="danger" %}
Attention, tout ce qui se trouve après un **return**, dans notre fonction ne sera jamais exécuté. En effet le **return**, marque la fin de notre fonction.
{% endhint %}

Exemple, la fonction ci-dessous retourne le volume calculé et ne l'affiche plus.

{% code-tabs %}
{% code-tabs-item title="Exemple d\'une fonction retournant une réponse" %}
```php
<?php 
function calculVolume($cote) 
{ 
    $volume = $cote * $cote * $cote; 
    return $volume; 
} 

//appel de ma fonction 
$v = calculVolume(4); 
echo 'Le volume est de ' . $v;
?>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

L'exemple ci-dessous produira le même résultat que le premier exemple, mais l'affichage n'est plus géré dans la fonction.

{% hint style="info" %}
Une fonction ne peut retourner qu'un seul élément. Si on souhaite retourner plusieurs valeurs, il faut construire un tableau et renvoyer le tableau.
{% endhint %}

## Exercices

### Exercice 1 

Ecrire une fonction qui calcule le volume d’un rectangle, dont on connait la largeur, la longueur et la hauteur. 

### **Exercice 2**

Ecrire une fonction qui prend deux nombres en paramètre et fait la moyenne de ces deux nombres.

### **Exercice 3**

Ecrire une fonction qui affiche un tableau. 

