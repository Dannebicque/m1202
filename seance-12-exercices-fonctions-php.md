# Séance 12 : Exercices Fonctions PHP

### **Exercice 1**

Ecrire une fonction qui prend en paramètre un tableau de nombre, et afficher la moyenne.  
Tester cette fonction avec les tableaux de votre choix.

Vous pouvez utiliser la fonction de la séance précédente pour afficher votre tableau.

### Exercice 2

L'écriture d’un champ de formulaire doit contenir un label et un champs. Le label et le champ sont associés grâce aux attributs l’**id** du champs et  **for** du label. 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'un champs de formulaire correctement rédigé" %}
```markup
<div>
    <label for="idChamp">Libelle du champ</label>
    <input type="text" name="nomDuChamp" id="idChamp" />
</div>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Il est bien sûr possible de mettre du CSS pour rendre tout cela esthétique, des valeurs par défaut, .... 

#### Ecrire un formulaire complet \(label et champs\) qui permet de saisir les données suivantes : 

* Nom
* Prénom
* Date de naissance
* Téléphone
* Adresse

### Exercice 3

Modifier le formulaire précédent pour que le champs et le label soit sur la même ligne, et que le texte du label soit aligné a droite. Modifier le formulaire pour que l’adresse soit composée d’un champ numéro, un champ rue, un champ adresse, un champ code postal, un champ ville. 

### Exercice 4 

Ecrire une fonction PHP qui prend des paramètres \(à définir\) et qui affiche le champ complet \(label + input\). Modifier votre code précédent afin d'utiliser vos fonctions à la place du code HTML.

### Exercice 5 

Installer le framework CSS : Bootstrap et modifier la fonction pour que la mise en page soit de type ”bootstrap” [http://getbootstrap.com/](http://getbootstrap.com/) 

{% code-tabs %}
{% code-tabs-item title="Exemple d\'un formulaire mis en forme avec Boostrap" %}
```markup
<form>
    <div class="form-group">
        <label for="exampleInputEmail1">
            Email address
        </label>
        <input type="email" class="form-control" id="exampleInputEmail1"
        placeholder="Email">
    </div>
    <div class="form-group">
        <label for="exampleInputPassword1">
            Password
        </label>
        <input type="password" class="form-control"
        id="exampleInputPassword1" placeholder="Password">
    </div>
    <button type="submit" class="btn btn-default">Submit</button>
</form>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Exercice 6

Compléter le fichier de fonction pour gérer tous les types de champs \(password, textarea, select\). On écrira une fonction par type de champ : ecritTextarea, ecritPassword, ecritSelect.



## Exercices complémentaires

### **Exercice 1**

Ecrire une fonction qui calcule un prix TTC en se basant sur un prix HT. Définir la fonction et les paramètres nécessaires. Choisir des exemples pour tester cette fonction

### **Exercice 2**

Ecrire une fonction qui prend en paramètre un tableau de mots, et qui affiche une phrase constituée de ces mots.

### **Exercice 3**

Ecrire une fonction qui affiche un tableau de taille $nb x $nb avec au croisement d’une ligne et d’une colonne, le résultat de la multiplication.  On fixera une valeur par défaut de 10. Vous devriez obtenir le résultat ci-dessous, qui a exécuté deux appels \($nb = 10 et $nb = 25\)

![R&#xE9;sultat &#xE0; obtenir](http://davidannebicque.fr/wp-content/uploads/2018/05/Capture-d%E2%80%99e%CC%81cran-2018-05-24-a%CC%80-13.23.08-257x300.png)

