# Semaine 7

## Objectifs :
- JS : JQuery
- HTML : Composants Bootstrap
- ~~Git : Rebase~~

# J1

[Questionnaire semaine 6](http://goo.gl/forms/gAUPQBGKLd) : JS-DOM, Bootstrap, Git

#### Exercice d'entrainement JS

[Changer la couleur d'une div](http://jsbin.com/rirapo/1/edit?html,output)

Devine un nombre entre 1 et 10, avec tentative jusqu'à ce qu'on trouve

[Exercice JS/DOM](http://jsbin.com/zogape/edit?html,output) : liste d'utilisateurs


# J2

#### Consolidation JS

**Tableaux, les bases**
Les tableaux ( *Array*, *listes* ) permettent de regrouper plusieurs objets dans une même entité.
Les tableaux sont représentés à l'aide de crochets **\[ element0,element1,element2 \]**

```javascript
var tableauVide = [];
var plats = ["Gratin de courgettes", "Soupe de potirons", "Quiche lorraine", "Frites", "Petits pois", "Riz"];
var jours = ["lundi", "mardi", "mercredi", "jeudi", "vendredi", "samedi", "dimanche"];
var mois = ["janvier", "février", "mars", "avril", "mai", "juin", "juillet", "aout", "septembre", "octobre", "novembre", "décembre"];
```
Chaque élément d'une *liste* est rangé dans une case numérotée, en partant d'une case *n°0*
```javascript
console.log( '1er jour : ', jours[0] ); // affiche "lundi"
console.log( '2nd jour : ', jours[1] );
```

Comme les tableaux représentent plusieurs éléments, il est plus que conseillé d'utiliser des noms de variables au pluriel.

Les tableaux proposent plusieurs fonctions/méthodes permettant de manipuler leur contenu :
```javascript
tableau.push( nouvelElement); // ajoute un élement
jours.indexOf( "jeudi"); // renvoie la position de l'item "jeudi" dans le tableau, ou -1 s'iil n'est pas dans le tableau
jours.pop( ); // supprime le dernier élement
jours.shift( ); // supprime le 1er élement
```
[Exemples - JsBin](http://jsbin.com/vojeni/edit?html,console)

[:book: EloquentJS : structures de données (et chatons) :fr:](http://fr.eloquentjavascript.net/chapter4.html)
[:memo: Tableaux et objects JS pour les chats :us:](http://jsforcats.com/#objects)

**forEach, map, filter, reduce, every : des fonctions dans des fonctions...**

Un autre type de fonctions est proposé par les tableaux. La particularité de ces fonctions est d'attendre une autre fonction en paramètre.
En gros, ces foncitons permettent d'appeler une fonction en lui passant, tour à tour, chaque élément d'un tableau.
Les boucles permettent de faire cela, mais ces méthodes permettent d'être plus "concis", de se focaliser sur la logique,
sans parasiter son code avec des *variables compteurs*.

```javascript
jours.forEach( function(item){...} ); //
var joursMajuscule = jours.map( function(item){return item.toUpperCase()} );
var joursde5lettres = jours.filter( function(item){return item.length == 5} );

var totalNotes = [10, 12, 15, 8].reduce( function( cumul, valeur ) { return cumul + valeur });
```

[:fire: Learn RX : Introduction interactive à la programmation (reactive) fonctionnelle :us:](https://github.com/ReactiveX/learnrx) :
Des petits défis JS pour découvrir une approche alternative pour la manipulation de tableaux, *sans utiliser de boucle*.

:memo: [Un peu de programmation fonctionnelle en JS :fr:](http://www.24joursdeweb.fr/2014/un-peu-de-programmation-fonctionnelle-en-javascript/)

#### Correction Memo
[Correction Memo animé](http://jsbin.com/quvasa/edit?html,console,output)

**[Installation de NodeJS](http://nodejs.org)**
:warning: il est préférable d'installer NodeJS via `apt-get` cf. Annexes de bas de page

# J4

#### Consolidation JS

**[Les fonctions :fr:](http://fr.eloquentjavascript.net/chapter3.html)**

**[Les objets et petits chats :us:](http://jsforcats.com/#objects)**

#### [JQuery](https://jquery.com)
Librairie javascript qui peut faire gagner du temps pour pas mal de choses :
- accès aux élements de la dom
- petites transitions
- composants


```html
<!doctype html>
<head>
	<meta charset="UTF-8">
	<script src="//code.jquery.com/jquery-1.11.3.min.js"></script>
</head>
<body>

<img id="image" src="http://i.ebayimg.com/00/$T2eC16hHJHgE9n0yHGLBBRY0mkvCKw~~_35.JPG" alt="image">

<button onclick="$('#image').fadeOut()">Disparition</button>
<button onclick="$('#image').fadeIn()">Apparition</button>

</body>
</html>
```


[:memo:Intro à JQuery - OC :fr:](https://openclassrooms.com/courses/simplifiez-vos-developpements-javascript-avec-jquery)

:warning: on n'a pas toujours besoin de JQuery, et il est important d'au moins comprendre comment on pourrait faire les mêmes choses en JS [http://youmightnotneedjquery.com](http://youmightnotneedjquery.com)

# J5

![touchthis](https://media.giphy.com/media/GPuVXyAmkMco0/giphy.gif)

Vous reprendrez bien un peu de JQuery avant le week-end ? :yum:

[Exemple jQuery : apparition fadeIn() / disparition fondu ](http://jsbin.com/pohorug/edit?html,output)
+ cf. [fadeIn()](http://api.jquery.com/fadein/)
+ cf. [fadeOut()](http://api.jquery.com/fadeout/)

[Correction jQuery : animation, manipulation DOM](http://jsbin.com/fequko/edit?html,output)
+ cf. [append()](http://api.jquery.com/append/) remplace document.getElementById().appendChild( .. );

[:memo:Intro à JQuery - OC :fr:](https://openclassrooms.com/courses/simplifiez-vos-developpements-javascript-avec-jquery)

[:memo:Sites dynamiques avec JQuery - OC :fr:](https://openclassrooms.com/courses/un-site-web-dynamique-avec-jquery?status=published)

[Learn JQuery](https://learn.jquery.com/) » tutos, articles, FAQ :us:

#### [Composant Bootstrap](http://getbootstrap.com/components)
[Gestion de formulaires :us:](http://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-forms.php)


#### Challenges JS

**Pomodoro app**
une appli pour gérer des sessions [Pomodoro :us:](http://pomodorotechnique.com) [Wikipedia :fr:](https://fr.wikipedia.org/wiki/Technique_Pomodoro)
+ décider de la tâche à effectuer ;
+ démarrer le minuteur (25 minutes) ;
+ travailler sur la tâche jusqu'à ce que le minuteur sonne et la noter comme faite ;
+ prendre une courte pause (5 minutes) ;
+ tous les quatre pomodori prendre une pause un peu plus longue (15-20 minutes).

![pmodoro-exo](https://www.evernote.com/l/AAE4epHHb4VO66QJuh-ekhNCdqUr-peEJoMB/image.png)

ou

**Morpion**

**Pendu**

**Puissance4**




# Annexes

**[Héberger/Publier des pages web HTML/CSS/JS sur Google drive](https://support.google.com/drive/answer/2881970?hl=fr)**

**[Phonegap](http://phonegap.com)**
:warning: c'est un peu plus laborieux sous linux apparament :

[Tuto install phonegap on ubuntu](http://jeffmcmahan.info/blog/installing-cordova-on-linux/)

[Tuto install phonegap on ubuntu](http://dasunhegoda.com/installrun-phonegap-ubuntu/797/)

[Phonegap on ubuntu - step by step](http://www.fifthfloorstudio.net/?p=648)

[un autre tuto Phonegap sous ubuntu](http://www.levibotelho.com/development/the-complete-guide-to-running-phonegap-on-ubuntu/)


