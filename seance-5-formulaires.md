# Séance 5 : Formulaires

## Présentation \(succinte\) des formulaires en HTML 

### Structure de base 

La structure d’un formulaire de saisie se compose d’un élément FORM contenant essentiellement une suite de contrôles \(éléments input, textarea, select, button, etc.\) mais aussi des éléments de structuration de document afin d’aligner correctement les champs d’entrée. 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'un formulaire " %}
```markup
<form method="(1)" action="(2)">
    du texte, des boutons, des zones de saisie ...
<input type="submit" value="(3)" />
</form>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

1. désigne la méthode qui sera utilisée pour envoyer les informations du formulaire ; c’est "**GET**" \(_par défaut_ ; les données du formulaire sont envoyées dans l’URL\) ou "**POST**" \(les données sont envoyées dans le corps du message, elles ne sont donc pas visibles dans l’URL\). 
2. désigne l’URL du programme \(PHP dans notre cas\) qui va traiter les données. 
3. désigne le texte qui va apparaître dans le bouton d’envoi. 

### Les principaux contrôles

#### Input 

Les zones de saisie, les boutons radios et les cases à cocher sont définis par ce contrôle; la syntaxe \(simplifiée\) en est : 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'un champ \"input\"" %}
```markup
<input type="type" name="nom" value="valeur" />
```
{% endcode-tabs-item %}
{% endcode-tabs %}

* **type** peut être : 
  * **text** : pour une zone de saisie au sens habituel du terme \(une zone rectangulaire où l’utilisateur écrit des données, sur une seule ligne\); c’est ce qui sera dans cette zone qui sera envoyé au programme de traitement; 
  * **password** : pour une zone de saisie de mot de passe \(identique à text, mais le texte saisi n’apparaît pas à l'écran que sous la forme d’astérisques, pour éviter d'être lisible par une tierce personne\); 
  * **checkbox** : pour une case à cocher \(a priori pour un choix multiple\); 
  * radio : pour un bouton radio \(des boutons radios de même nom \(name\) sont mutuellement exclusifs\); 
  * **submit** : pour un bouton d’envoi; c’est le clic sur ce bouton qui envoie le contenu du formulaire au programme de traitement; 
  * **hidden** : pour une variable cachée; permet de cacher des valeurs nécessaires au traitement mais qu’on ne veut pas voir affichées à l’écran; attention, caché ne veut pas dire secret : ces valeurs sont visibles dans le code source de la page; 
  * **reset** : pour remettre les zones de saisie à leurs valeurs par défaut \(les valeurs qu’elles ont lors du chargement de la page\); 
  * **file** : pour permettre à l’utilisateur de choisir un fichier sur son ordinateur. Il faudra gérer l’upload dans la partie traitement 
* **name**: est le nom de la variable qui sera envoyé au fichier de traitement; cela n’a a priori pas de sens pour un bouton submit ou reset, mais c’est absolument nécessaire pour les autres; les zones doivent en principe avoir des noms différents, sauf pour le boutons radios : les boutons radios de même nom sont mutuellement exclusifs ; 
* value est la valeur du contrôle 

#### select 

Pour créer des listes déroulantes ; 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'un \"select\"" %}
```markup
<select name="menu">
    <option>premier choix</option>
    <option>deuxieme choix</option>
    <option>troisieme choix</option>
</select>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Cette zone permettra d’envoyer une variable de nom _menu_ qui aura pour valeur le choix sélectionné. Pour pré-sélectionner un choix dans la liste il suffit d’ajouter l’attribut `selected=”selected”` dans la balise correspondante. On peut avoir besoin d’envoyer une valeur différente de celle qui est affichée \(par exemple demander à l’utilisateur de choisir une personne par ses nom et prénom, et envoyer l’identifiant de cette personne dans une table d’une base de données\). On utilisera alors l’attribut `value` dans la balise comme dans l'exemple ci-après

{% code-tabs %}
{% code-tabs-item title="Exemple d\'un select avec des valeurs pour les options" %}
```markup
<select name="responsable">
    <option value="1"> marcel durand</option>
    <option value="2"> georges dupont</option>
    <option value="3"> pierre martin</option>
</select>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Dans cet exemple si on choisit _georges dupont_ la variable _responsable_ aura la valeur 2. 

#### textarea 

Pour des zones de saisies plus grandes qu’avec input.

{% code-tabs %}
{% code-tabs-item title="Exemple d\'un textarea" %}
```markup
<textarea name="nom" rows="4" cols="40">
Texte par defaut...
</textarea>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

##  Traitement des formulaires 

### Principes 

Le traitement d’un formulaire se fait toujours \(pour notre semestre 1\) avec un langage serveur. PHP est un langage serveur. Il faut donc maintenant écrire un fichier de traitement pour le formulaire. Ce fichier doit porter le nom que vous avez mis dans l’attribut _action_ de votre balise form. Il existe ensuite deux façon de traiter les éléments. Cela dépend si le formulaire est envoyé en **POST** ou en **GET**. Dans PHP on récupère les éléments avec des ”**tableaux superglobaux**”. Ces tableaux sont des tableaux particuliers qui sont automatiquement présent si on peut s’en servir \(par exemple si un formulaire est envoyé\). Leur syntaxe est la suivante : 

* `$_POST[ ]` si le formulaire est envoyé en POST \(method=”POST”\) 
* `$_GET[ ]` si le formulaire est envoyé en GET \(method=”GET”\) 

Il faut ensuite préciser le nom du champ \(input, select ou textarea\) que l’on souhaite récupérer en écrivant par exemple `$ POST['nom du champ']`. Le nom du champ est la valeur de l’attribut name de votre champ. 

4 2.2 Exemple Listing 6 – Exemple de fichier contenant le formulaire 1 ... 2 3

Nom :  4

Prénom :  5

Age :  6

 7 8 ... Un exemple de fichier de traitement permettant d’afficher les donn´ees dans le formulaire pourrait ressembler au code ci-dessous : Listing 7 – Exemple de fichier contenant le formulaire 1 ... 2  9 ... 3 Exercices 3.1 Exercice 1 : Calculatrice Ecrire un formulaire ´ « calculatrice » qui comprendra 2 cases \(zone de saisie libre\) pour la saisie des nombres \(op´erande\), un groupe de 4 cases \`a cocher pour le choix de l’op´eration, un bouton pour effectuer l’op´eration. 5 3.2 Exercice 2 : Table de multiplication Ecrire un formulaire qui demande deux nombres a et b. Il affiche ensuite ´ la table de multiplication par a sur b lignes. 3.3 Exercice 3 : Petit jeu Vous devez deviner le nombre que le programme a choisi. Vous proposez une solution, et le programme vous r´epond « trop petit » ou « trop grand » suivant le cas, jusqu’\`a trouver le bon nombre. 6
