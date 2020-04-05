# Séance 2 : Eléments du langage

## Quelques bonnes pratiques

### Indentation du code 

Il est important d’indenter le code HTML mais aussi PHP pour faciliter la lecture et la recherche d’erreurs 

{% tabs %}
{% tab title="Code non indenté" %}
```php
<!DOCTYPE html>
<html lang="fr">
<head>
<title>Ma page avec du PHP</title>
<meta charset="utf-8" />
</head>
<body>
<?php
echo '<img src="monimage.jpg" alt="image">';
?>
</body>
</html>
```
{% endtab %}

{% tab title="Code Indenté" %}
```php
<!DOCTYPE html>
<html lang="fr">
<head>
    <title>Ma page avec du PHP</title>
    <meta charset="utf-8" />
</head>
<body>
<?php
    echo '<img src="monimage.jpg" alt="image">';
?>
</body>
</html> 
```
{% endtab %}
{% endtabs %}

### Commentaires 

Les commentaires permettent de donner des informations et des explications lors de la lecture du code source PHP. Ils ne sont pas interprétés par le moteur.

Il existe des commentaires sur une seule ligne :

```php
<?php
    //j'affiche une image
    echo '<img src="monimage.jpg" alt="image">';
?>
```

Et des commentaires sur plusieurs lignes 

```php
<?php
/*
cet affichage ne fonctionne pas
echo '<img src="monimage.jpg" alt="image">';
je commente donc
*/
echo 'ici ca fonctionne';
?>
```

### Mise en page du code généré 

Si vous regardé le code généré \(afficher source de la page dans votre navigateur\), il est souvent difficile à lire. Il est possible de dire à PHP d’écrire ce code un peu plus "proprement". Pour sauter des lignes dans le code HTML généré, il faut utiliser le caractère spécial `\n` \(newline\) dans des chaînes délimitées par des guillemets.

```php
<?php
echo 'Bonjour !'."\n";
$note=11;
echo 'La note vaut : ';
echo $note."\n";
$bonus=1.5;
$note_totale=$note+$bonus;
echo 'La note finale vaut : '.$note_totale."\n";
?>
```

Le code ci-dessus donnera le résultat suivant :

![Le code HTML g&#xE9;n&#xE9;r&#xE9; est proprement format&#xE9;](.gitbook/assets/exemplecodeindente.PNG)

{% hint style="warning" %}
Jusqu'a présent lors des `echo` on a utilisé le caractère ' pour délimiter une chaîne. **C'est la bonne pratique et c'est ce que je vous impose sur ce module**. Mais on peut aussi utiliser des " \(guillemets\), notamment dans le cas particulier des caractères "\n" ou encore "\r".
{% endhint %}

