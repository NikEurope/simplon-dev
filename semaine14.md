# Semaine 14

## Objectifs :
- Challenge inter-simplon
- PHP / MySQL :
	- conception base de données
	- sessions
	- sécurité de base

## J1

[Questionnaire Semaine 13](http://goo.gl/forms/JLFrmZzB8C)

## J2

#### Défi Crypto

Sachant que Dede vaut Nono, et inversement.

Que vaut **Sx Myno Go Dbecd** ?

Écrivez le programme de chiffrement et déchiffrement.

#### PHP

+ **Sauvegarde de mot de passe**

PHP et MySQL proposent des fonctions de [hashage](https://fr.wikipedia.org/wiki/Fonction_de_hachage) permettant de "crypter" les mots de passe
 afin de les rendre illisibles.

ex: SHA('SECRET') = 3c3b274d119ff5a5ec6c1e215c1cb794d9973ac1

**MySQL**

+ insertion
```sql
INSERT INTO users(`mail`,`password`) VALUES ( 'toto@gmail.com', SHA('SECRET'));
```

+ récupération
```sql
SELECT * FROM users WHERE `password`=SHA('SECRET')
```

**PHP**

```php
$code = sha1('SECRET');
```

#### Les Sessions

Les sessions permettent de stocker sur le serveur, des variables associées à un utilisateur.
Ces données sont temporaires, et les sessions et leur données sont détruites à la fermeture du navigateur.


```php
<?php
	session_start();
	if( ! $_SESSION['compteur'] )
		$_SESSION['compteur'] = 0;
	else
		$_SESSION['compteur'] += 1;
	echo "Nombre de vues : ".$_SESSION['compteur'];
?>
<a href="destroy_sessions.php">Effacer</a>
```

[Exemple 1](https://github.com/Simplon-lyon/dev-web/blob/master/php/sessions/sessions.php)

[Exemple 2](https://github.com/Simplon-lyon/dev-web/blob/master/php/sessions/sessions_v2.php)

Typiquement, les sessions sont utilisées pour garder des informations d'identification.
 Une fois l'identification effectuée, le serveur associe des informations, des variables de sessions,
 à l'utilisateur. Ces variables de sessions $_SESSION seront accessibles par tous les scripts PHP,
 et permettront par exemple de savoir si l'utilisateur qui ouvre une page est bien autorisée à le faire.


```php
<?php
	if( !$_SESSION['identifiant']   ){
		// l'utilisateur n'est pas identifié » affichage du formulaire de login
		include('login.php');
	} else if (!$_SESSION['role'] < 3){
		echo "Vous n'avez pas les droits permettant d'accèder à cette page";
	}
// ...
```

+ Destruction de session

```php
session_unset(); // efface les var de session
session_destroy(); // détruit la session
```

[Les sessions ( et les cookies ) sur OC](https://openclassrooms.com/courses/concevez-votre-site-web-avec-php-et-mysql/variables-superglobales-sessions-et-cookies)
[Les sessions sur PHP facile](http://www.lephpfacile.com/cours/18-les-sessions)


## Startups : différentes approches

**:fire: Lean Startup**

+ Tester au plus vite, son idée d'abord, puis au plus vite un vrai proto, auprès de "vrais gens".

+ Minimum Viable product

+ Itérations : Learn / Build / Measure
![lean loop](https://media-mediatemple.netdna-ssl.com/wp-content/uploads/2012/08/fig-6.png)

:tv: [Lean Startup intro - Eric Ries](https://www.youtube.com/watch?v=fEvKo90qBns)

:mortar_board: [How to build a startup - Steve Blank - :tv: MOOC gratuit :us:](https://www.udacity.com/course/how-to-build-a-startup--ep245)


**Bootstrap : 37 Signals/ BaseCamp**

+ auto-financement d'un projet grâce à activités annexes

:tv: [Unlearn your MBA - David Heinemeier-Hansson](https://www.youtube.com/watch?v=MlhAkNWC1qo)

:tv: [A secrete for making money online - David Heinemeier-Hansson](https://www.youtube.com/watch?v=0CDXJ6bMkMY&index=1&list=PLGUdxvommyXEs3sXclqdaxPmTHWla0LeH)

:tv: [Basecamp, Bootstraping , startups... 1 - Jason Fried](https://www.youtube.com/watch?v=UZGS_IOPZpk)

:tv: [Basecamp, Bootstraping , startups... 2 - Jason Fried](https://www.youtube.com/watch?v=AmvvGDfPE1U)

:book: [Getting Real](https://gettingreal.37signals.com)

:book: [Re-work](https://37signals.com/rework/)

## J3

#### HTML / JS : Data-* attributes
permet de stocker des informations textuelles annexes dans les tags html

```html
<div id="photo1"
	data-author-id="142"
	data-city="Lyon"
	data-tags="urbain, architecture, France" >
	<!-- ... -->
<div/>
```
**Utilisation en JS**
Pour accéder à ces attributs en JS :
- `element.setAttribute('data-author-id', 142);`
- `element.getAttribute('data-author-id');`
ou
- `element.dataset.taskId = 117;` : attention au camelCase

[Exemple](https://github.com/Simplon-lyon/dev-web/blob/master/front/html/data_attributes.html)

[:memo: data-* - Alsacréations](http://www.alsacreations.com/article/lire/1397-html5-attribut-data-dataset.html)

[:memo: How to use HTML data-* attributes](http://www.sitepoint.com/use-html5-data-attributes/)

[:memo: data attributes from js & css](https://hacks.mozilla.org/2012/10/using-data-attributes-in-javascript-and-css/)

## J4

#### Startup week

#### :warning: Rendu Simpllo | portfolio repoussé au 27 (mercredi)
Correction sous forme de code review : 5 mn par projet

## Annexes

+ [UX - Little Big Details](http://littlebigdetails.com)

+ [JS : évenements personnalisés](http://www.sitepoint.com/javascript-custom-events/)
	[Exemple monolithe](https://github.com/Simplon-lyon/dev-web/blob/master/front/html/alpha_custom_events.html)
	[Exemple séparé](https://github.com/Simplon-lyon/dev-web/blob/master/front/html/custom_events.html)

+ [Librairie JS de gestion de dates](http://momentjs.com)

+ [:tv: Intro à la cryptographie](https://www.youtube.com/watch?v=g8RmT-CwTMo)

+ [Plus loin avec la sauvegarde sécurisée de mot de passe](https://alias.io/2010/01/store-passwords-safely-with-php-and-mysql/)

+ [Le PHP Facile](http://www.lephpfacile.com/cours/)
