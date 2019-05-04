# Séance 8 :  Exercices sur les tableaux et les formulaires

## Exercice 1 : Tableau

Soit le tableau ci-dessous. Ecrire un code permettant d'afficher toutes les valeurs de ce tableau dans une liste ul/li

{% code-tabs %}
{% code-tabs-item title="Données pour l\'exercice 1" %}
```php
<?php

$pays = ['France', 'Belgique', 'Allemange', 'Angleterre', 'Espagne'];
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## **Exercice 2 : Tableau associatif**

Le code ci-dessous contient un tableau PHP. Ecrire le code permettant d’afficher ce tableau dans une page HTML. Vous pouvez récupérer les images directement sur Wikipedia.

{% code-tabs %}
{% code-tabs-item title="Données pour l\'exercice 2" %}
```php
<?php
//prix Nobel de physique
$tableau = [
	['Nom' => 'Einstein', 'Prenom' => 'Albert', 'Annee' => 1921, 'Image' => 'einstein.jpg', 'Description' => 'Pour ses contributions à la physique théorique, spécialement pour sa découverte de la loi de l\'effet photoélectrique.'], 
	['Nom' => 'Schrödinger' , 'Prenom' => 'Erwin', 'Annee' => 1933, 'Image' => 'schrodinger.jpg', 'Description' => 'Pour la découverte de nouvelles formes productives de la théorie atomique.'],
	['Nom' => 'Kao', 'Prenom' => 'Charles', 'Annee' => 2009, 'Image' => 'kao.jpg', 'Description' => 'Pour une avancée dans les communications par fibre optique.'],
];
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
On peut considérer que l'on connait le nom des clés.
{% endhint %}

## **Exercice 3 : Tableaux et formulaires**

Soit une tableau _$tCouleur_ qui comporte le nom de différentes couleurs. Ecrire un formulaire permettant d’obtenir des case à cocher, afin qu’un visiteur puisse choisir ses couleurs préférées. Définir le tableau, écrire le formulaire, écrire le fichier de traitement

## Exercice 4 : Trier un tableau

Sans utiliser la fonction sort \([https://www.php.net/manual/fr/function.sort.php](https://www.php.net/manual/fr/function.sort.php)\) de PHP, trier le tableau suivant.

```php
<?php

$tableau = [23, 12, 1, 34, 56, 3, 67];
```

