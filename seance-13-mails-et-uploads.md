# Séance 13 : Mails et Uploads

## Envoi de mails

L'envoi d'un email en php se fait en utilisant la fonction `mail` \([https://www.php.net/manual/fr/function.mail.php](https://www.php.net/manual/fr/function.mail.php)\). Cette fonction permet d'envoyer des emails basiques. Bien souvent, sur de plus gros projets on utilisera des librairies qui permettront un plus grand contrôle et une écriture un peu plus simple, notamment si l'on souhaite intégrer des pièces jointes ou définir des en-têtes de manière précise.

{% hint style="danger" %}
Il est très fréquent, sur les hébergement mutualisés que la fonction mail soit désactivé, afin d'éviter l'envoi en masse d'emails.
{% endhint %}

L'utilisation de la fonction mail est relativement simple, elle prend a minima les paramètres suivants :

1. le destinataire
2. le sujet
3. le message

{% code title="Exemple d\'utilisation de la fonction mail" %}
```php
mail('mail@gmail.com', 'Le Sujet de mon mail', 'Tout le message de mon mail');
```
{% endcode %}

Dans l'exemple ci-dessus, le message et le mail envoyé sont au format texte. Nous verrons un peu plus loin comment envoyer un message avec du HTML.

Si l'on souhaite préciser l'expéditeur, le mail de réponse, ... il faut définir le 4eme paramètre, qui comprend l'en-tête du mail. Sa structure est un peu particulière, vous avez un exemple ci-dessous.

{% code title="Un exemple de header additionnel." %}
```php
$headers = 'From: webmaster@example.com' . "\r\n" .
     'Reply-To: webmaster@example.com' . "\r\n" .
     'X-Mailer: PHP/' . phpversion();
```
{% endcode %}

Pour envoyer un email en HTML, il faut définir toute la page HTML dans le message, puis définir les headers afin de préciser que vous envoyer un email au format HTML. Ci-dessous un exemple avec également plusieurs destinataires.

{% code title="Mail au format HTML" %}
```php
<?php
     // Plusieurs destinataires
     $to  = 'johny@example.com, sally@example.com'; // notez la virgule

     // Sujet
     $subject = 'Calendrier des anniversaires pour Août';

     // message
     $message = '
     <html>
      <head>
       <title>Calendrier des anniversaires pour Août</title>
      </head>
      <body>
       <p>Voici les anniversaires à venir au mois d\'Août !</p>
       <table>
        <tr>
         <th>Personne</th><th>Jour</th><th>Mois</th><th>Année</th>
        </tr>
        <tr>
         <td>Josiane</td><td>3</td><td>Août</td><td>1970</td>
        </tr>
        <tr>
         <td>Emma</td><td>26</td><td>Août</td><td>1973</td>
        </tr>
       </table>
      </body>
     </html>
     ';

     // Pour envoyer un mail HTML, l'en-tête Content-type doit être défini
     $headers[] = 'MIME-Version: 1.0';
     $headers[] = 'Content-type: text/html; charset=iso-8859-1';

     // En-têtes additionnels
     $headers[] = 'To: Mary <mary@example.com>, Kelly <kelly@example.com>';
     $headers[] = 'From: Anniversaire <anniversaire@example.com>';
     $headers[] = 'Cc: anniversaire_archive@example.com';
     $headers[] = 'Bcc: anniversaire_verif@example.com';

     // Envoi
     mail($to, $subject, $message, implode("\r\n", $headers));
?>
```
{% endcode %}

### Exercice 1

Ecrire un fichier PHP qui vous envoie un email.

### Exercice 2

Ecrire un formulaire de contact et la page de traitement associé qui envoie un email au webmaster du site \(vous\).

Dans un deuxième temps modifiez le code afin que lorsque je clique sur répondre, ce soit l'adresse de l'expéditeur \(celui qui a complété le formulaire de contact\) qui soit dans le mail. \(il faut définir le reply-to\)

## Uploads

[http://antoine-herault.developpez.com/tutoriels/php/upload/](http://antoine-herault.developpez.com/tutoriels/php/upload/)

### Exercice 1

Lire et tester le tutoriel ci-dessus.

### Exercice 2

Modifier le code obtenu pour afficher l'image en plus du message de confirmation.

### Exercice 3

En vous inspirant de la [documentation de php.net](http://php.net/manual/fr/function.readdir.php), écrire un code qui liste et affiche l'ensemble des images contenu dans le répertoire d'upload.

