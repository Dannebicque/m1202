# Séance 3 : Boucles

## Les boucles

Les boucles permettent de répéter plusieurs fois un même bloc d'instructions \(rupture de séquence\) 

Il existe 3 boucles en PHP : 

* La boucle for ... \(pour\) 
* La boucle while ... \(tant que\) 
* La boucle do ... while ... \(jusqu'à\)

### Boucle FOR

La boucle for permet de répéter un bloc d'instructions quand on connaît a priori le nombre d'itérations \(nombre de boucles\) à effectuer. 

```php
<?php 
echo 'Punition'."\n"; 
for ($i=0; $i<100; $i++)
{ 
    echo 'Je dois apprendre mon cours !';
} 
?>
```

`$i` est la variable de boucle, c'est elle qui détermine le nombre d'itérations

Trois éléments dans les parenthèses : 

* Initialisation de la variable de boucle \(`$i=0`\)
* Condition qui doit être vraie pour exécuter le bloc \(`$i<100`\)
* Modification de la variable de boucle \(`$i++`\)

```php
<?php 
echo 'Liste des entiers de 0 -> 10'."\n"; 
for ($i=0; $i<=10; $i++) 
{ 
    echo ''.$i.''."\n"; 
}
?>
```

```php
<?php
echo '<p>Liste des entiers pairs de 0 -> 10</p>'."\n";
for ($i=0; $i<=10; $i=$i+2) 
{
    echo '<p>'.$i.'</p>'."\n";
}
?>
```

```php
<?php
echo 'Liste des entiers impairs de 11 -> 1'."\n"; 
for ($i=11; $i>1; $i=$i-2) { 
    echo ''.$i.''."\n"; 
} 
?> 
```

#### Exercice

{% tabs %}
{% tab title="Ennoncé" %}
Ecrire une boucle qui fait la somme des nombres de 1 à 100, et qui affiche le résultat.
{% endtab %}

{% tab title="Correction" %}
```php
<!DOCTYPE html>
<html lang ="fr">
<head>
    <title>Ma page avec du PHP </title>
    <meta charset="utf-8" />
</head>
<body>
<?php
$somme = 0;
for ($i = 1 ; $i <= 100; $i++) //equivalent à $i=$i+1
{
    $somme = $somme + $i; // équivalent $somme += $i;
}
echo 'La somme des 100 premiers nombres est '.$somme;
?>
</body>
</html>
```
{% endtab %}
{% endtabs %}

### Boucle While

La boucle while permet de répéter un bloc d'instructions quand on ne connaît pas a priori le nombre d'itérations \(nombre de boucles\). 

```php
<?php 
echo 'Punition'."\n"; 
$i=0; 
while ($i < 100)
{
    echo $i.' Je dois apprendre mon cours !';
    $i++;
} 
```

`$i` est la variable de boucle, c'est elle qui détermine le nombre d'itérations 

Trois éléments : 

* Initialisation de la variable de boucle `$i=0`; \(on peut mettre autre chose que 0\) 
* Condition qui doit être vraie pour exécuter le bloc \(`$i<100`\) 
* Modification de la variable de boucle `$i++`; \(on peut agir différemment sur $i\)

{% tabs %}
{% tab title="Ennoncé" %}
Ecrire une boucle \(avec un while\) qui affiche tous les nombres impairs \(à partir de 2\), inférieurs à 20.
{% endtab %}

{% tab title="Correction" %}
```php
$i=3;
while($i<20)
{
    echo $i.' ';
    $i+=2; //pour augmenter de 2 en 2. ou $i=$i+2
}
```

Ou

```php
$i = 2;
echo 'Les nombres suivants sont impairs : ';
while ($i < 20) {
    if ($i % 2 !== 0) { //on vérifie que le nombre est impair en calculant le modula par 2. S'il est différent de 0, alors le nombre est impair
        echo $i.' ';
    }
    $i++;
}
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
**Attention aux boucles infinies.** Si vous oubliez d'incrémenter `$i` dans la boucle while, la condition ne sera jamais vérifiée, et votre boucle ne s'arrêtera jamais. Le serveur ne rendra la main que lorsqu'il aura planté. Il peut se produire la même chose avec une boucle for, si la condition est mal écrite.
{% endhint %}

### Boucle Do ... While

La boucle `do … while …` permet de répéter un bloc d'instructions quand on ne connaît pas a priori le nombre d'itérations \(nombre de boucles\) au moins une fois. 

```php
<?php 
echo 'Punition'."\n".''; 
$i=0; 
do 
{ 
    echo 'Je dois apprendre mon cours ! '."\n"; 
    $i++; 
} while ($i < 100)
?> 
```

`$i` est la variable de boucle, c'est elle qui détermine le nombre d'itérations.

 Trois éléments : 

* Initialisation de la variable de boucle `$i=0`; \(on peut mettre autre chose que 0\) 
* Condition qui doit être vraie pour exécuter le bloc \(`$i<10`\) 
* Modification de la variable de boucle `$i++`; \(on peut agir différemment sur $i\) 

#### Exercices complémentaires

#### Exercice 1

Ecrire une boucle qui fait la somme des nombres de 1 à 100 et qui affiche le résultat avec une boucle WHILE.

#### Exercice 2

Ecrire une boucle qui affiche tous les nombres impairs \(à partir de 2\), inférieurs à 20 avec une boucle for.



