# Semaine 9

#### Objectifs
+ JS orienté Objet
+ Webdesign / Ergonomie

## J1

[Questionnaire Semaine 8](http://goo.gl/forms/l4QmCmSALZ) : RWD, JS : Object & Events, Bootstrap

[Rendus maquette et liste d'utilisateurs](https://mensuel.framapad.org/p/simply-rwd0)

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

## J2

**Visite de Alexandre Balmes [@pockystar](http://twitter.com/pockystar)**

#### Correction Galerie RWD

Correction avec Flex : Chloé : Maquette : https://github.com/simplon-chloeS/galerieresponsive
une correction sans Flex : http://jsbin.com/kifosa/edit?html,css,output

#### Correction liste utilisateurs
[Correction Model/View](http://jsbin.com/yatete/edit?html,js,outputv)

## J3

#### Documentaires

[Une contre histoire d'Internet](https://www.youtube.com/watch?v=tztUbIPb5oQ)

[Les gardiens du nouveau monde](https://www.youtube.com/watch?v=t5tBsVX5g0g)

[The story of Aaron Swartz](https://www.youtube.com/watch?v=gpvcc9C8SbM)

[Plus](docu)

## J4

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

# J5

![friiiiiiidayyyyyyy](http://i.imgur.com/QFVh2UJ.giffridaay)

## Annexes

**[Principales librairies spécialisées JS ( Jeu, Appli, ...)](librairiesJS)**

[:dart: Des challenges, des tutos web :us: ](http://www.freecodecamp.com)

#### Communautés Lyon

+ [Lyon JS](http://lyonjs.org) / [Twitter](https://twitter.com/lyonjs)

+ [La cuisine du web](http://www.lacuisineduweb.com)

+ [IxDA](http://www.ixda-lyon.fr) / [Twitter](https://twitter.com/interactif_lyon)

+ [Mix-IT - 21+22/04/2016](http://www.mix-it.fr/home) / [Twitter](https://twitter.com/mixit_lyon)

#### :fire: Swift
- [Apple ouvre les sources de Swift](http://rxlabz.github.io/swift/2015/12/05/apple-open-swift-sources.html)
- [Tour d'horizon de Swift](https://developer.apple.com/library/prerelease/ios/documentation/Swift/Conceptual/Swift_Programming_Language/GuidedTour.html#//apple_ref/doc/uid/TP40014097-CH2-ID1)
- [Essayez Swift en ligne](http://swiftlang.ng.bluemix.net/)
- [Guide Swift](https://developer.apple.com/library/prerelease/ios/documentation/Swift/Conceptual/Swift_Programming_Language/TheBasics.html#//apple_ref/doc/uid/TP40014097-CH5-ID309)
