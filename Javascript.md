# Introduction au Javascript

[Javascript pour débutants](https://www.youtube.com/watch?v=cQZOfeKrWDs)

[ Repl.it : Bac à sable JS](http://repl.it)

+ nombres
+ opérations mathématiques + / - *
+ chaines de caractères String [:book: :fr: Référence MDN ](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)
+ condition » [exemple](https://gist.github.com/rxlabz/3573e6790778df5eeb02)

+ ( operateur ternaire ) [exemples](http://jsbin.com/vudejakoxo/1/edit?js)

+ Exercice : le programme demande la couleur du cheval blanc d'Henri 4, puis combien y a-t-il de 7 nains ?
» [correction JSBin](http://jsbin.com/sikupuwoko/1/edit?js)

» [correction repl.it](https://gist.github.com/rxlabz/5a075775239fe0272d6e)

![Schema Henri IV](https://www.evernote.com/l/AAE_ew09fhxGjYCEqfiYZk1Y3RLeuGivHWoB/image.png)

#### Exercices
Calculatrice : le programme demande :
+ de choisir une opération (+ / - * ) ,
+ un 1er chiffre
+ un second chiffre
+ Le programme affiche ensuite le résultat de l'opération

**Exercice Dessiner c'est gagner**

[Ardoise magique](http://rxlabz.com/simplon/ardoise/index.html)

Les conditions
+ booléen : true false
+ égalité === en JS il est prudent d'utiliser systèmatiquement le strictement égal ===
```javascript
console.log();
```
+ inégalité !==

+ comparaisons > >= < <=

+ Opérateurs logiques
	+ ET && `(age > 18) && (age < 65)` » si age
	+ OU ||`(age < 18) || (age > 65)`
+ [typeof](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Opérateurs/L_opérateur_typeof)
il arrive parfois d'avoir besoin de vérifier si une variable contient un texte un nombre, ou autre chose encore.
```javascript
if( typeof uneVariable === "string" ){
	// instructions executées si uneVariable contient bien un texte
} else if( typeof uneVariable === "number" ){
	// instructions executées si uneVariable contient bien un nombre
}
```

+ :warning: Attention aux conversions Texte-Nombre
	+ [Référence Number - MDN](https://developer.mozilla.org/fr-FR/docs/Web/JavaScript/Reference/Global_Objects/Number)
	+ [NaN » Not A Number](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/NaN) [isNaN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/isNaN)

[Exemples](http://jsbin.com/cugice/edit?js,console)

**Exercice Devine un chiffre**

Le programme demande de deviner un chiffre entre 0 et 9 en 2 tentatives.
[Correction](https://gist.github.com/rxlabz/b673abaee282b66edfa6)

**Exercice Calculette J2**

[Correction](https://gist.github.com/rxlabz/9c76a3ddbbdb0b9df3c3)

**Exercice login / password**

+ Demander l'identifiant puis le mot de passe
+ vérifier que :
	+ l'identifiant saisi a plus de 4 caractères
	+ l'identifiant contient un @
	+ l'identifiant est "lea@gmail.com" et son mot de passe "12345"

[correction](https://gist.github.com/rxlabz/1508411d9a7a2936b684)

**Exercice calcul mental**

+ le programme tire au hasard une opération ( + * - ) et deux chiffres
+ le programme demande le résultat de l'opération à l'utilisateur » ex : "combien font 4 * 7"
+ affiche si la réponse est juste ou fausse


#### Tableaux

+ Créer un tableau
```html
var tableauVide = [];
var tableauDePrenoms = ["Paul", "Jack", "Bob", "Toto"];
var tableauDeNombres = [1 , 15 , 16 , 18, 21 ];
var tableauDeTrucs = ["Jack", true, 0.2, false, 1];
```
+ Longueur d'un tableau
```html
console.log( "nombres de prenoms " + tableauDePrenoms.length);
```

+ Parcourir un tableau
 ```html
console.log( tableauDePrenoms[0] );

console.log( tableauDePrenoms[3] );

console.log( tableauDePrenoms[tableauDePrenoms.length - 1] );
 ```
+ Ajouter
```html
tableauDePrenoms.push("Lili");
```

+ supprimer
```html
tableauDePrenoms.splice( 2,1); // efface le troisième objets
```
[Exemple](http://jsbin.com/jofiju/edit?js,console)

[:book: Référence Array - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array)

**Fonctions**

Une fonction est une liste d'instructions
```javascript
function ditBonjour(){
	console.log( "bonjour" );
}
```

+ paramétres

```javascript
function addition(valeur1 , valeur2){
	var resultat = valeur1 + valeur2;
	console.log('resultat : ' + resultat );
}
```
[Exemples de fonctions - JSBin](http://jsbin.com/fujida/1/edit?js,console)

#### Fonctions javascript utiles
**alert( message )**  permet d'afficher une petite fenêtre avec un message

**prompt( message )** permet d'afficher une petite fenêtre avec un message et une zone de réponse

**console.log( message )** permet d'afficher un texte dans la console du navigateur
» message que se laisse le développeur  en phase de développement pour obtenir des informations sur le déroulement du programme

#### Exercice
Reprendre l'exercice login/password en acceptant cette fois plusieurs paires mail/mdp et en donnant 4 essais à l'utilisateur.

Exemple » identifications valides : toto@gmail.com / 12345 ou titi@gmail.com / 54321 ...


+ switch / case
```javascript
switch(langue){
	case 'fr':
	console.log('merci');
	break;

	case 'en':
	console.log('thanks');
	break;

	case 'es':
	console.log('gracias');
	break;

	case 'it':
	console.log('grazie');
	break;

	default:
	console.log('merci');
	break;
}
```
[Exemple switch](http://jsbin.com/gequbu/1/edit?js,console)

**Boucles**

+ while : tant que ... instructions
``` javascript
var compteur = 0;

while( compteur < 5 ){
	console.log("compteur " + compteur);
	compteur++;
}
```

+ boucle for incrémentral
``` javascript
for(var i = 0; i < 5 ; i++){
	console.log( i )
}
```

**exemples**

[Exemple boucles](http://jsbin.com/racucu/2/edit?js,console)

[Boucles lettres](http://jsbin.com/sezuniruwo/8/edit?js)

[Boucles pyramides #](http://jsbin.com/lazetepefo/1/edit?js,console)

[Boucles pyramides numérique](http://jsbin.com/cozoralaqu/1/edit?js,console)

[Boucles pyramides lettre](http://jsbin.com/cefegibiwi/1/edit?js,console)


#### Exercices

**Exercice Fizzbuzz**
le programme affiche dans la console tous les nombres entre 1 et 100.
+ Pour chaque multiple de 5 il écrit "buzz"
+ Pour chaque multiple de 7 il écrit "fizz"
+ Pour chaque multiple de 5 et 7 il écrit "fizzbuzz"

Vous pouvez essayer d'utiliser le modulo %

[correction](http://jsbin.com/quvaci/2/edit?js,output)

**Exercice calcul moyenne**

Un programme demande de saisir 10 notes ( une par une et de 0 à 20 ) et affiche la moyenne à la fin

[correction](http://jsbin.com/mohodoz/edit?js,console)

## Fonctions et méthodes

#### Exemples

#### [String](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)
+ indexOf( elementRecherche ): renvoie la position
+ substring( positionPremierCaractere, limiteNonIncluse ): renvoie la sous chaine correspondante
+ split( char ) [exemple](http://jsbin.com/miketegiqu/edit?js)

=> [Référence MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)

#### [Array](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array)

+ monTableau.push(items)
+ monTableau.pop()
+ monTableau.shift()
+ monTableau.unshift( elements )

=> [Référence MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array)

#### Déclarer ses propres fonctions

Les fonctions permettent de définir des blocs d'instructions, le plus souvent définie par un nom.

```javascript
function ditBonjour(){
	alert("Bonjour");
}
```

#### Fonctions et paramètres/arguments

Une fonction peut parfois avoir besoin d'informations particulières pour pouvoir fonctionner
( exemple : les fonctions de l'[ardoise magique](http://rxlabz.com/simplon/ardoise)').

```javascript
function ditBonjour( prenom ){
	console.log( "Salut " + prenom );
}

function addition(a,b){
	var resultat = a + b;
	console.log( "resultat " + resultat );
}

```

#### Fonctions avec valeurs renvoyées

[Exemple](http://jsbin.com/cefofojova/edit?js)

**[Les fonctions :fr:](http://fr.eloquentjavascript.net/chapter3.html)**

**[Les objets et petits chats :us:](http://jsforcats.com/#objects)**

## Object

Les Object permettent de créer des *entités* possédant des propriétés nommées.
Chaque propriété peut contenir n'importe quelle sorte de données ( chaines de caractères, nombres, tableaux, object ...).

```javascript
var utilisateur = { nom:"Dupont", prenom:"Luc" };
console.log( utilisateur.nom );
console.log( utilisateur.prenom );

utilisateur.nom = "Martin";
console.log( utilisateur.nom );
```

Pour accéder à une propriété d'objet

```javascript
utilisateur.nom
// ou
utilisateur["nom"]
```

Pour parcourir toutes les propriétés d'un Object on peut utiliser une variante de la boucle **for** :
```javascript

for( var propriete in utilisateur){
	console.log( propriete + ' : ' + utilisateur[proprieté]);
}

```

**Exercice : Object & formulaire HTML**
Une page HTML contient un formulaire constitué de 3 champs :
- prenom
- nom
- ville

Au chargement de la page, on veut pré-remplir les champs du formulaires avec les données d'un objet JS

```javascript
var user = {
	prenom:'bob',
	nom:'Dupont',
	ville:75001
};

```

Le formulaire propose un bouton *Update* qui affiche, dans la console, l'objet modifié avec les valeurs saisies dans les champs du formulaire.

#### Défis

**Modérateur**

![moderateur-img](https://www.evernote.com/l/AAHESRlpdc1LOJpm0Q50g5N0-H68u_9dy44B/image.png)

Le programme supprime les smileys d'un texte saisi

[ » Code de base](http://jsbin.com/rayuvohidi/1/edit?html,js,output)

Quand l'utilisateur appuie sur "Modérer" tout texte saisi dans la textArea
apparait dans la #result-box avec chaque smiley remplaçé par un '--'

**calculatrice HTML/JS**

Version avec interface graphique ( button html )

![screen calculette](https://www.evernote.com/l/AAEAS5tq6IxCMoGKxWWkYUUoxeye6qLZ_C8B/image.png)

» permet des opérations à deux termes / facteurs : 5 + 4 , 11 * 57, 134 / 12...

**numberToRoman**
écrivez un programme qui peut convertir les nombres en nombres romains ( de 1 à 10... de 1 à 100?... de 1 à 1000? )

#### HTML/CSS/JS

[Exemple JS dans une page HTML](http://jsbin.com/jigaxe/1/edit?html,output)

#### Récupération des données d'un formulaire en javascript

```javascript
var form = document.getElementbyId("monFormulaire");
console.log("nom " + form.nom.value);
```

#### Exercice login/password avec un formulaire HTML
Créez un formulaire contenant 2 champs :
+ identifiant
+ mot de passe

( données attendues : toto@gmail.com / 12345 )

Affichez, dans la console navigateur ou dans la page, 'Bienvenue" ou "Erreur" en fonction des données saisies



#### Exercice
Une page HTML contient un formulaire constitué de 3 champs :
- prenom
- nom
- ville

Au chargement de la page, on veut pré-remplir les champs du formulaires avec les données d'un objet JS

```javascript
var user = {
	prenom:'bob',
	nom:'Dupont',
	ville:75001
};

```


#### JS : Les objets

Les *Object* permettent de créer et de décrire des *entités* auxquelles on peut définir soi même des propriétés.
Chaque propriété peut contenir n'importe quelle sorte de données ( chaines de caractères, nombres, tableaux,... object ...).

```javascript
var uneForme = {};
uneForme.type = 'rect';
uneForme.couleur = 'yellow';
uneForme.largeur = 200;
uneForme.hauteur = 50;
```


```javascript
var utilisateur = { nom:"Dupont", prenom:"Luc" };
console.log( utilisateur.nom );
console.log( utilisateur.prenom );

utilisateur.nom = "Martin";
console.log( utilisateur.nom );
```

Pour accéder à une propriété d'objet

```javascript
utilisateur.nom
// ou
utilisateur["nom"]
```

Pour parcourir toutes les propriétés d'un Object on peut utiliser une variante de la boucle **for** :
```javascript

for( var propriete in utilisateur){
	console.log( propriete + ' : ' + utilisateur[proprieté]);
}

```

Les objets permettent de décrire, de *modéliser des données* + ou - complexes.
Exemples :
- [des informations de divs](http://jsbin.com/rezoqu/10/edit?html,js,output) » créez en HTML les divs décrites en JS

- des formes
```javascript
var rectangle = {
	couleur:'red',
	largeur:100,
	hauteur:60
}

var rond = {
	couleur:'red',
	rayon:100
}
```
- une classe
```javascript
var classe5emeB = {
	niveau:5,
	id:'B',
	referent:{ nom:'Dupont', prenom:'Luc', matiere:'Fraçais' },
	eleves: [
		{
			nom:'Wong',
			prenom:'Li',
			notes : [
				{ matiere:'Francais', notes:11 },
				{ matiere:'EPS', notes:14 },
				{
					matiere:'SVT',
					notes:{
						trimestre1:12,
						trimestre2:15,
						trimestre3:14
					}
				}
			]
		},
		{ nom:'Dupont', prenom:'Luc', matiere:'Fraçais' },
		// ...
	]
}

// accès aux notes du 1er eleve
console.log('notes', classe5emeB.eleves[0].notes) ; // affiche les notes

```
- ...


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


#### JS : Les évenements

Un événement est un signal indiquant que quelque chose s'est passé dans la page HTML, par exemple que l'utilisateur a interagi avec un élément.

Exemples :
+ lorsqu'on click sur un bouton : le bouton émet un event 'click'
+ lorsqu'on survole une image : l'image émet un event 'mouseover'

On peut définir des écouteurs d'évenements pour *capter* ces évenements, et déclencher une/des action(s) en conséquence.
La déclaration d'écouteurs d'évenements peut se faire en html :
```html
<button id="monBouton" onclick="faitUnTruc()">Un bouton</button>
```
 ou en JS ( pur )
 ```javascript
document.getElementById('monBouton').addEventListener('click', function(ev){
 	console.log('le bouton a été cliqué');
});
 ```

 ou via JQuery
  ```javascript
 $('#monBouton').on('click', function(event){
  	console.log('le bouton a été cliqué');
 });
  ```

L'ajout d'écouteurs d'évenements en JS est surtout utile lorsqu'on créé des éléments HTML *dynamiquement*.

En JS, on peut également supprimer un écouteur.
:warning: Si on veut pouvoir enlever un écouteur, il faut utiliser une fonction nommée

+ en JS ( pur )
 ```javascript
 function reagitAuClick(ev){
  	console.log('le bouton a été cliqué');
 }

document.getElementById('monBouton').addEventListener('click', reagitAuClick);

// ...
document.getElementById('monBouton').removeEventListener('click', reagitAuClick);
```

+ via JQuery
```javascript
 $('#monBouton').off('click', reagitAuClick);
```

**L'Objet Event**

Lorsque on utilise un écouteur d'évenement, on peut récupérer l'objet *Event*, et utiliser les informations qu'il contient :
 + `event.target` : référence d el'objet qui a émis l'évenement
+ position de la souris :
+ touche ctrl ou shift enfoncée

```javascript
document.getElementById('monBouton').addEventListener('click', function(event){
 	console.log('target', event.target);
 	console.log('ctrl', event.ctrlKey);
 	console.log('pageX', event.pageX);
 	console.log('pageY', event.pageY);
});
```

**Bubbling**

Le DOM peut être vu comme un arbre, et certains évenements ( MouseEvent par exemple ) ont la possiblité de *remonter* l'arbre, ce qui permet d'écouter
l'évenement sur le conteneur direct ou un de ses parents, plutôt que sur tous les élements enfants.

[Exemple de bubbling](http://jsbin.com/vihice/edit?html,console,output) : dans cet exemple,
l'écouteur est ajouté au conteneur des boutons, et pas sur les boutons eux même.

[:memo: Bubbling & capturing :us:](http://javascript.info/tutorial/bubbling-and-capturing)

[:memo: Evenement JS - OC :fr:](https://openclassrooms.com/courses/dynamisez-vos-sites-web-avec-javascript/les-evenements-24)

**Evénements personnalisés**

+ [Créer et émettre des évenements](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Creating_and_triggering_events)
+ [Cross-browser custom events](tjrus.com/blog/custom-javascript-events)

[**LocalStorage**](http://www.alsacreations.com/article/lire/1402-web-storage-localstorage-sessionstorage.html)
Permet de sauvegarder "sur le disque" des données saisies / éditées dans une page web » exemple sauvegarder les pomodoros,
ou le meilleur temps au memo,...


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


### JS Orienté Objet (Classe inversée)

+ [:tv: Prog. orienté Objet en JS - Grafikart :fr:](http://www.grafikart.fr/tutoriels/javascript/poo-javascript-object-466) (:watch: 25mn)
+ [:memo: Les Objets en JS - OpenClassroom:fr:](https://openclassrooms.com/courses/dynamisez-vos-sites-web-avec-javascript/les-objets-5)
+ [:book: Prog. orientée Objet - EloquentJS :fr:](http://fr.eloquentjavascript.net/chapter8.html)
+ [:memo: POO , Prototype et JS :fr:](http://sebastien-dupire.info/faire-de-la-poo-avec-javascript.html)
+ [:memo: MDN - JS Orienté Objet :fr:](https://developer.mozilla.org/fr/docs/Web/JavaScript/Introduction_à_JavaScript_orienté_objet)

##### POO exemples

**Exemple 1** :
Créez une classe Chrono avec :
+ une méthode start()
+ une méthode pause()
+ une méthode stop()
+ une propriété currentTime

**Exemple 2** :

Créez une classe Produit :
- nom
- prix

Créez une classe Panier avec :
- une méthode ajoute( produit )
- une méthode retire( produit )
- une proprieté totalHT
- une proprieté totalTTC

**Utilisation** : ajouter ce qu'il faut à ce [code de base](http://jsbin.com/botala/2/edit?js,console) pour qu'il fonctionne.

```javascript
var baguette = new Produit( 'Baguette', 0.85); // prix HT
var croissant = new Produit( 'Croissant', 0.80);

var panier = new Panier();
panier.ajoute(baguette);
panier.ajoute(croissant);

console.log(panier.totalHT);
console.log(panier.totalTTC);
```


#### Programmation Orientée Objet

Nous avons vu comment les Objects permettent de définir des "structures" de données,
constituées d'un ensemble de *propriétés*, des variables appartenant à l'objet lui même'.

```javascript
var article = {
	id:1249,
	titre:"Insolite : il décrit un article de blog en javascript",
	categorie:"Web",
	tags:["Javascript","Orienté Objet"],
	contenu:"Quentin Galamond s'est aperçu un jour que le contenu d'une page HTML, ses tags, pouvait être représenté sous forme d'objet javascript...",
	dataPublication:"2015-12-05",
	dataModification:"2015-12-09",
	auteur:{
		id:4,
		nom:"Diaz",
		prenom:"Joe",
		mail:"jdiaz@me.com"
	},
	commentaires:[]
};
```
Nous avons vu que ces propriétés pouvaient contenir toutes sortes de valeurs : chaines des caractères, des nombres, des tableaux, des objets,...
et **même des fonctions**.

En Javascript, les fonctions sont des objets comme les autres.

```javascript

var chrono = {
	currentTime: 0,
	start:function(){
		console.log('start...');
	},
	pause:function(){
		console.log('pause...');
	},
	stop:function(){
		console.log('stop...');
	}
}
chrono.start();
```

```javascript

var Timer = function(){
  this.currentTime = 0;
	this.start = function(){
		console.log('T.start...');
	};
};

var t = new Timer();
t.start();

var t2 = new Timer();
t2.currentTime++;
console.log('t', t.currentTime, 't2', t2.currentTime);

// Timer.prototype permet de rajouter
Timer.prototype.pause = function(){
  console.log('pause');
};

t.pause();
t2.pause();
```

Pour le JS orienté objet mieux vaut se diriger vers l'EcmaScript 2015 (aka ES2015 aka ES6), voire [Typescript](http://www.typescriptlang.org)

## [Ecmascript 2015](http://es6-features.org)

ES2015 rajoute un certain nombre de fonctionnalités et de sucres syntaxiques

[BabelJS](http://www.babeljs.io) » *transpiler* / traducteur ES2015 vers "vieux javascript'"

[Principales nouveautés de ES2015 :fr:](http://ronanlevesque.fr/articles/les-principales-nouveautes-de-es6/)

[Introduction au JS de demain :fr:](https://www.wanadev.fr/introduction-a-ecmascript-6-le-javascript-de-demain/)

## Typescript

TypeScript est une extension de JS et de ES6. La particularité de TS est d'offrir un système de typage.

En Typescript, les variables ont des types définis "une fois pour toutes".
Quand on déclare une variable on indique ce qu'elle contiendra ( string, number, Array, ...) est toute incohérence
sera en mesure d'être détectée.

Cela permet notamment une meilleure détection erreurs pendant le développement, mais aussi des
IDE plus "pratiques" ( auto-complétion, refactoring automating ... ).

- :fire: [:memo: Typescript Quick Start](http://www.typescriptlang.org/Tutorial)

- [:memo: Visual Studio Code](https://code.visualstudio.com) : meilleur éditeur (gratuit) pour Typescript

- [:memo: Introduction à typeScript :fr:](http://yahiko.developpez.com/tutoriels/introduction-typescript/)


#### Installation live-server

installation node
```bash
sudo apt-get install npm
sudo npm install node
sudo apt-get install nodejs-legacy
sudo npm install live-server -g
```

#### AJAX

```javascript
function traiteResultat(){
	console.log("resultat", this.responseText);
	var data = JSON.parse(this.responseText);
	console.log('Nom 0', data.participants[0].nom);
}

var requete = new XMLHttpRequest();
requete.onload = traiteResultat;

requete.open("get", "users.txt", true);
requete.send();
```

```javascript
{
	"participants":[
		{
			"id":1,
			"nom":"Durant",
			"prenom":"Lea"
		},
		{
			"id":2,
			"nom":"Dupond",
			"prenom":"Joe"
		},
		{
			"id":3,
			"nom":"Martin",
			"prenom":"Jean"
		}
	]
}
```

:warning: Une étrangeté est à noter dans ce 1er exemple très basique : la référence à `this.responseText``
 dans la fonction `traiteResultat()`.

En fait, écrit de cette manière, traiteResultat s'éxecute dans le contexte ( aussi appelé **scope** )ππ de l'objet `requete` et non pas
 dans le contexte  "global" du script.

  En effet, si on essaye de logger `this` dans la fonction, on s'aperçoit que `this` renvoie en fait
  à l'objet XMLHttpRequest. :sad:


```javascript
function traiteResultat(){
	console.log("scope", this);
	// ...
}
```

C'est une des particularités du javascript 5 : le *scope* d'une fonction n'est pas forcèment celui dans lequel on
déclare la fonction.


Ici le scope dans lequel s'éxecute la fonction après réception des données, et celui de l'objet `requete`.

Oui et alors ? me direz vous...
Et bien le problème, est que, dans l'état, on ne pourra pas appeler les méthodes déclarées dans le contexte globale depuis la fonction `traiteResultat()`...

La solution ?

1. Il existe une "obscure" fonction **bind()** en javascript, qui permet de choisir le contexte dans lequel s'éxecutera une fonction.

2. on récuperera la valeur de responseText à partir de l'event, ou plutôt le target de l'event.


```javascript
/* la déclaration du paramètre event est facultative, mais son utilisation nous permet de récupérer
la référence de l'objet XMLHttpRequest, dans la mesure où c'est lui qui émet l'event,
et que par conséquent, c'est lui le target.
*/

function traiteResultat(event){
	console.log("resultat", event.target.responseText);
	var data = JSON.parse(event.target.responseText);
	console.log('Nom 0', data.participants[0].nom);
}

var requete = new XMLHttpRequest();

/* l'ajout de bind(this) permet de définir que l'on veut que
la fonction traiteResultat soit
 executée dans le contexte courant*/
requete.onload = traiteResultat.bind(this);

requete.open("get", "users.txt", true);
requete.send();
```

**Ancienne méthode IE9& -**

[ cf Ajax - OpenClassRoom ](https://openclassrooms.com/courses/dynamisez-vos-sites-web-avec-javascript/xmlhttprequest-1)

```javascript
function onLoadingState(event){
	console.log('data');
	if (requete.readyState === requete.DONE && requete.status === 200) {
		console.log('resultat', requete.responseText);
		var data = JSON.parse(requete.responseText);
		console.log('Nom 0', data.participants[0].nom);
	}
}

var requete = new XMLHttpRequest();
requete.addEventListener('readystatechange', onLoadingState );

requete.open("get", "users.txt", true);
requete.send();
```

#### Exercice Diaporama POO

# :tv: Conférences

[Introduction to JS and browser DOM](https://www.youtube.com/watch?v=ljNi8nS5TtQ) par le créateur de AngularJS

[JS the good parts](https://www.youtube.com/watch?v=hQVTIJBZook)

[:tv: The zen of javascript ](https://www.youtube.com/watch?v=QHs55-5FzgA) - 26mn:us:
Conf pour une approche zen des étrangetés du JS ( comme quoi même les développeurs expérimentés sont surpris par le JS ).


# :books: Bibliographie

[le JS pour les chats](http://jsforcats.com)

[:book: :fr: Eloquent Javascript](http://fr.eloquentjavascript.net) Le Javascript de a à z

[WTFJS :us: ](http://wtfjs.com) un comportement parfois "étrange"...