# Semaine 8

Objectifs :
+ RWD, Bootstrap, ~~Foundation~~
+ JS : Objets, Evénements
+ DRY : Don't repeat Yourself
+ Git : Fork / Collaborate

## J1

**[Questionnaire semaine 7](http://goo.gl/forms/yzDyd0az43)**


#### Exercice RWD : Galerie photos

:warning: à rendre via Github lundi 7/12

Dans un 1er temps : reproduire cette maquette de galerie photo ( sans bootstrap... pour commencer ).

+ [Largeur supérieure à 1024px](https://www.evernote.com/l/AAFBVRlrJAFKnaO3PtfJ8bo_EnalLku_5LUB/image.png)

+ [Largeur supérieure à 600px et inférieure ou égale à 1024px](https://www.evernote.com/l/AAFPgSRuDbNLx4Zaz1uAQD7oOFLix-m7SBYB/image.png)

+ [Largeur inférieure à 600px](https://www.evernote.com/l/AAEGOQ6hoxNJwoIBLo9AuroWACd45SvurIQB/image.png)

Puis, pour pratiquer :

- le js : créer dynamiquement les divs contenant les images à partir d'un tableau d'Object photo du type :

[ { titre:'monImage1', description:'blabla', url:'http://...' }, { titre:'monImage2', description:'blabla', url:'http://...' },...]

- le html/ css : améliorez le graphisme, ajoutez des transitions, des animations...



:bulb: Rappels utiles :

**:triangular_ruler: Unités de mesures en CSS**

[:memo: Les unités de mesure CSS :fr:](http://www.w3.org/Style/Examples/007/units.fr.html)

[ 7 nouvelles unités : em, rem, vw vh,vmin vmax...](http://webdesign.tutsplus.com/articles/7-css-units-you-might-not-know-about--cms-22573)

[:memo: quelle unité de mesure choisir :us:](http://thenewcode.com/775/Which-CSS-Measurements-To-Use-When)

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

## J2

? 1er meetup le 23/12 avec présentation / demo / workshop ?

#### Exercice JS / DOM
Créez 5 divs *HTML en JS* à partir d'un tableau de couleurs `['red', 'pink', 'green', 'yellow', 'cyan']`
Chaque div permet de changer la background de la page **UNE SEULE FOIS**.

[Correction](http://jsbin.com/wayete/1/edit?html,js,output)

#### Exercice Bootstrap

Reprendre exercice de [gestion de liste d'utilisateurs](http://jsbin.com/zogape/edit?html,output) en améliorant l'aspect graphique à l'aide de Bootstrap.

Exemple *minimum*

![bootstrap exo](https://www.evernote.com/l/AAGKjkctfMRAtZKgK0s6POoK1PZN780oyYcB/image.png)

## DRY : Don't Repeat Yourself
####Création d'un "template" / *boilerplate* de dossier pour nouveau projet web####

L'idée est de mettre en pratique le principe du **DRY**. Il est nécessaire d'essayer de **repensez et d'améliorez continuellement ses méthodes, outils, organisation...** (  sans non plus y passer tout son temps... :) )

Le développement d'un projet web comporte un certain nombre de tâches répétitives.
Il existe de nombreux outils, gratuits et opensource, ou pas, qui peuvent nous aider à gagner du temps.
Toutefois, même si l'intégration dans son workflow, d'outils standards/référence, "prêt à l'emploi", est progressivement nécessaire,
 il peut être utile d'apprendre à se créer ses propres "outils".

+ création d'un dossier avec fichiers de base:
	+ style-base.css : définition des régles de styles *systèmatiques* cf [CSSReset]
	+ scripts-base.js : avec des fonctions raccourcis "à la jQuery" ( ex : des fonctions byId(), byTag()... )
	+ index.html intégrant les le fichier css et js

+ [initialisation git du dossier, et dépôt sur github](https://github.com/Simplon-lyon/dev-web/wiki/Git)

+ pour utiliser le template :
	- cloner le projet depuis github `git clone http://github.com/VOUS/PROJET.git`
	- supprimez le .git `rm -rf dossier_template/.git`
	- renommez le dossier chargé `mv dossier_template/ nouveauProjet/`
	- initialisez git dans le nouveau dossier `cd nouveauProjet/ ; git init`

L'utilisation de ce template pourra être simplifiée en créant par exemple un alias pour lancer toutes ces instructions en une commande.
Cela constitue également un petit préambule à l'utilisation des outils d'automatisation front-end modernes ( NPM, Webpack, Grunt, Gulp, ... ).

à suivre donc...

## J4

Rappels J2

#### Shell : Création d'alias pour l'utilisation du template de [dossier web](http://github.com/Simplon-lyon/web-default.git)
dans ~/.bash_aliases, créez un alias *npj* (*nouveau projet*).
```bash
alias npj='git clone http://github.com/VOUS/DOSSIER.git ; rm -rf dossier_template/.git ; mv dossier_template/ '
```

**Utilisation** ( :warning: re-démarrez la console après enregistrement de l'alias )
```bash
npj monNouveauProjet/
```


#### Point sur avancement du projet exploration / restitution

#### [Git fork / pull request](https://github.com/Simplon-lyon/dev-web/wiki/Git#collaborer-sur-un-projet--fork-et-pull-request)

## J5

![exciting](https://media4.giphy.com/media/xTiTnvMb8gkmBvwFiM/200.gif)


## Annexes

#### [Utiliser la console sous Windows](http://playntek.fr/logiciel/cmder-l'invite-de-commande-de-windows-ultime)
À creuser : Cmder, Powershell, cigwin, consoleZ


#### JS

**Evénements personnalisés**

+ [Créer et émettre des évenements](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Creating_and_triggering_events)
+ [Cross-browser custom events](tjrus.com/blog/custom-javascript-events)

[**LocalStorage**](http://www.alsacreations.com/article/lire/1402-web-storage-localstorage-sessionstorage.html)
Permet de sauvegarder "sur le disque" des données saisies / éditées dans une page web » exemple sauvegarder les pomodoros,
ou le meilleur temps au memo,...

#### HTML / CSS
[Quelques outils / bonnes pratiques pour le front-end](http://www.alsacreations.com/tuto/lire/1683-guide-ultime-pour-accelerer-son-developpement-frontend.html)

**HTML / CSS**
- [Sass](http://sass-lang.com) / [Less](http://lesscss.org) » pré-processeurs CSS » pseudo languages qui apportent de nouvelles fonctionnalités aux CSS
- [Foundation](http://foundation.zurb.com) » concurrent de bootstrap » [:tv: Bootstrap 6 est sorti depuis qlq jours](https://www.youtube.com/watch?v=aEotvNIrrmg)


#### Entreprenariat

**:fire: Lean Startup**

:tv: [Lean Startup intro - Eric Ries](https://www.youtube.com/watch?v=fEvKo90qBns)

:mortar_board: [How to build a startup - Steve Blank - :tv: MOOC gratuit :us:](https://www.udacity.com/course/how-to-build-a-startup--ep245)


**37 Signals/ BaseCamp / Bootstraped startup**

:tv: [Unlearn your MBA - David Heinemeier-Hansson](https://www.youtube.com/watch?v=MlhAkNWC1qo)

:tv: [A secrete for making money online - David Heinemeier-Hansson](https://www.youtube.com/watch?v=0CDXJ6bMkMY&index=1&list=PLGUdxvommyXEs3sXclqdaxPmTHWla0LeH)

:tv: [Basecamp, Bootstraping , startups... 1 - Jason Fried](https://www.youtube.com/watch?v=UZGS_IOPZpk)

:tv: [Basecamp, Bootstraping , startups... 2 - Jason Fried](https://www.youtube.com/watch?v=AmvvGDfPE1U)

:book: [Getting Real](https://gettingreal.37signals.com)

:book: [Re-work](https://37signals.com/rework/)

