# Séance 9 : Manipulation de tableaux et des formulaires

## **Exercice 1**

Créer un formulaire \(méthode POST\) pour saisir le nom, le prénom, et choisir l’année dans laquelle on se trouve \(MMI1, MMI2, MMI1D, MMI2D, LPMIM\). Valider le formulaire et afficher une phrase personnalisée, de votre choix, en fonction de l’année sélectionnée.

## **Exercice 2**

Construire un tableau composé de 20 valeurs aléatoire \(regarder la fonction [rand](http://php.net/manual/en/function.rand.php)\). Afficher ce tableau et mettre en évidence \(dans le tableau affiché\) le minimum, le maximum et calculer la moyenne des valeurs.

## **Exercice 3** : Inverser une chaîne de caractères.

Une chaîne de caractères \(par exemple ‘Bonjour tout le monde’\) **est en fait un tableau**. Il est donc possible de manipuler cette chaîne de la même manière, et donc on peut facilement accéder à un caractère précis.

Par exemple :

```php
<?php
$chaine = 'Bonjour tout le monde';
echo $chaine[3]; //affichera j
```

* Ecrire un programme qui prend une chaîne de caractère et l’écrit à l’envers \(en utilisant une boucle!\).
* Ecrire un formulaire permettant de saisir une chaîne de caractère et de l’afficher à l’envers.

## **Exercice 4 :** Formulaire et traitement dans la même page, et vérification des champs.

On va ici voir comment traiter et vérifier un formulaire sur une même page. \(pas de page traitement spécifique\).

Pour cela on peut utiliser une fonction PHP « isset », qui permet de vérifier sur une variable est définie. Ecrire un formulaire contenant 3 champs \(nom, prénom, date de naissance\), en méthode POST, et dont l’action est la même page.

Ecrire le traitement, si le formulaire est correctement rempli \(si le bouton « submit » est cliqué, **et** tous les champs sont remplis\), alors on affiche un message et on masque le formulaire, sinon, on affiche un message d’erreur, et on remet le formulaire pré-rempli des données précédentes.

