# Semaine 5

## Objectifs
+ Javascript

## J1

#### JS
+ rappels : conditions, boucles, tableaux

+ ( operateur ternaire ) 
[exemples](http://jsbin.com/xuhereyucu/1/edit?js)

**exemples**

[Boucles lettres](http://jsbin.com/sezuniruwo/8/edit?js)

[pyramides #](http://jsbin.com/lazetepefo/1/edit?js,console)

[pyramides numérique](http://jsbin.com/cozoralaqu/1/edit?js,console)

[pyramides lettre](http://jsbin.com/cefegibiwi/1/edit?js,console)

[exercice : nom & mails](http://jsbin.com/cabigemiyu/edit?js)

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

Le formulaire propose un bouton *Update* qui affiche, dans la console, l'objet modifié avec les valeurs saisies dans les champs du formulaire.

## J2

#### refaire anciens exercices en utilisant des fonctions, des boucles...


#### [Henri IV 2 : le retour](http://jsbin.com/fucirixiru/1/edit?js,output)
Le programme pose une question tirée aléatoirement parmi les 4 proposées.
A chaque réponse juste, le score de l'utilisateur augmente et le programme tire une autre question ( jamais 2 fois la même).
S'il se trompe, ou qu'il répond à toutes les questions,
le programme lui indique son score dans une alerte.

[Correction](http://jsbin.com/qivuzewehi/edit?js)

#### Devine un nombre entre 1 et 100
Cette fois on a autant de chances que nécessaire !

#### Scope / Portée de variable

Si une variable est déclarée en dehors de toute fonction, elle est *globale*. Tous les scripts de la page peuvent y accéder.
Si elle est déclarée dans une fonction, elle n'existe que dans le bloc de la fonction.

[Exemple](http://jsbin.com/lewufuroqi/2/edit?js,console,output)

#### DOM / JS

**document.getElementById("elementId")** » renvoie l'objet HTML qui a l'id demandé ( unique )

[modification de styles css via js](http://jsbin.com/cepewicavi/edit?html,output)

[exemple d'animation en js](http://jsbin.com/faqudahaga/1/edit?html,output)

## J3

![carlton](https://33.media.tumblr.com/82a98ba71d60495ae0789aa876429f7f/tumblr_n0cpp9fflP1sia4voo1_400.gif)

[:tv: The zen of javascript ](https://www.youtube.com/watch?v=QHs55-5FzgA) - 26mn:us:
Conf pour une approche zen des étrangetés du JS ( comme quoi même les développeurs expérimentés sont surpris par le JS ).

Le Javascript pourquoi et comment faire :
- des sites web animés et interactifs => [CreateJS](http://www.createjs.com) : multimedia / [GreenSock](https://greensock.com/gsap) : animation
- des applications webs => [Vue.js](http://vuejs.org) [React](https://facebook.github.io/react/) / [Angular](https://angularjs.org)
- des jeux web, voire mobile et bureau  => [Phaser](http://phaser.io)
- des applications mobiles Phonegap => [Phonegap](http://phonegap.com) / [Ionic](http://ionicframework.com)
- des serveurs ou des applications en lignes de commande => [NodeJS](https://nodejs.org/en/)
- des applications de bureau => Exemple Atom => développé avec [Electron](http://electron.atom.io)

## J4

#### Object

Exemples : Ecole, Rectangle, Jeu

#### Le DOM

Le [DOM](https://developer.mozilla.org/fr/docs/Web/JavaScript/JavaScript_technologies_overview) - *Document Object Model* est en quelque sorte une représentation JS d'un document HTML.
Cette représentation offre une **API** - Application Programming Interface -
permettant la manipulation/modification du document.

[Manipulation du HTML en JS ](https://openclassrooms.com/courses/dynamisez-vos-sites-web-avec-javascript/manipuler-le-code-html-partie-1-2) - OpenClassroom

[What is the DOM?](https://css-tricks.com/dom/)

#### Manipulation du DOM

document.getElementsByClassName("className") » permet de récupérer une collection/tableau d'objet HTML

**document.getElementsByTagName("elementId")**

**Création dynamique d'élements HTML**

Créer et ajouter un élément HTML

```javascript
var liste = document.getElementById('maListe')
var li = document.createElement('li');
li.innerText = Math.random();
liste.appendChild(li);
```
[Exemple](http://jsbin.com/zudasejeza/2/edit?html,js,output)

**[Ajout / suppression de classes CSS](http://jsbin.com/biwofireye/edit?html,css,js,output)**

```javascript
var boite = document.getElementById('boite1');
boite.classList.add('actif');
...

boite.classList.remove('actif');

```

**Exercice**

**Memo** créez un jeu de memo

![memo_Game](https://www.evernote.com/l/AAF1deL0fNBI85MWJaZHIL7d03LcyCOEknkB/image.png)

4 paires de cartes "recto-verso" ( exemple : verso : gris et recto : rouge, vert, bleu, orange) sont affichées à l'écran, côté verso.
Quand on clique sur une carte la couleur de la carte s'affiche pendant 4 secondes.
Le joueur a 4 seconde pour "retourner" l'autre carte de même couleur
Les paires trouvées restent retournées.
Un compte à rebours de 20 secondes démarre à la 1ère carte retournée

Pour cet exercice vous pourriez éventuellement avoir besoin de :
+ [setTimeInterval]() / [setTimeOut](https://developer.mozilla.org/fr/docs/Web/API/WindowTimers/setTimeout)
+ [addEventListener](https://developer.mozilla.org/fr/docs/Web/API/EventTarget/addEventListener) : pour ajouter "dynamiquement" des écouteurs d'évenements, par exemple des écouteurs de click


## J5
![happy friday](https://media3.giphy.com/media/5VMNcCxVBibZK/200.gif)

# Annexes
[Learn RX](https://github.com/ReactiveX/learnrx) :
une approche alternative pour la manipulation de tableaux, sans utiliser de boucle. Pour le moment ça sera surtout utile pour codewars.
