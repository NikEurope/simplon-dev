# Semaine 10

## Objectif :
- fin du projet exploration
- JS orienté objet
- Webdesign / UIDesign / Ergonomie

## J1

[Questionnaire Formation](http://goo.gl/forms/Hv4wluHXX6)

**Projet Exploration**

** Début des entretiens individuels**


## J2

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


## Principes de (Web)design

+ Histoire de l'Art
+ PAO / Print
+ Web
+ App

[8 universal web design principles](http://conversionxl.com/8-universal-web-design-principles-you-should-to-know/)
- [Hiérarchie visuelle](http://52weeksofux.com/post/443828775/visual-hierarchy)
- Proximité
- Similarité
- [loi de Hick](http://uxdesign.smashingmagazine.com/2012/02/23/redefining-hicks-law/)
- proportion
- loi de Fitt
- ...

[:memo: Design principles](http://www.sylvantech.com/~talin/projects/ui_design.html)

[:newspaper: In defense of eye candy](http://alistapart.com/article/indefenseofeyecandy)

##### Trends
- 1995 - 2010 : [évolution du Web Design](https://creativemarket.com/blog/2013/05/13/evolution-of-web-design)
- [20 ans de webdesign](http://blog.hubspot.com/marketing/look-back-20-years-website-design)
- [2004-2015](http://www.templatemonster.com/infographics/web-design-trends-years-2004-2014.php)
- [2010](http://www.smashingmagazine.com/2010/05/web-design-trends-2010/)
- 2016 : [Prédiction1](http://www.creativebloq.com/web-design/trends-2016-111517914)

##### UI Design Guidelines

- [Apple Design guidelines](https://developer.apple.com/design/)
  - [Apple iOS Human Interface Guidelines](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/)
  - [Apple OSX Human Interface Guidelines](https://developer.apple.com/library/mac/documentation/UserExperience/Conceptual/OSXHIGuidelines/)
  - [Apple watchOS Human Interface Guidelines](https://developer.apple.com/watch/human-interface-guidelines/)
  - [Apple tvOS Human Interface Guidelines](https://developer.apple.com/tvos/human-interface-guidelines/)

- [Google Material Design](https://www.google.com/design/spec/material-design/introduction.html)
	- [Google Design](https://design.google.com)

- [Microsoft : Design Universal Windows App](https://dev.windows.com/fr-fr/design)
- [Saleforce Lightning Design System](https://www.lightningdesignsystem.com) : [:newspaper: Présentation](https://medium.com/salesforce-ux/salesforce-lightning-design-system-lightning-experience-everywhere-dd15400da69#.i860zxfmh)

##### Inspiration
+ [Dribbble](https://dribbble.com) : réseau social / portfolio pour designers
+ [Behance](https://www.behance.net) : réseau social / portfolio pour designers ( racheté par Adobe )
+ [ffffound](http://ffffound.com) : flux d'images diverses

### UI, Ergonomie, UX

[:book: 52 weeks of UX ](http://52weeksofux.com/tagged/week_1)

## J3

![dvador](https://media4.giphy.com/media/tWsh1fnuxNBuw/200.gif)

**Projet exploration**

**Diaporama sans POO**

Dans un fichier texte (JSON), décrivez une liste de photos ( titre et url), puis chargez le,
et utilisez le pour faire défiler automatiquement les photos dans une img.

**Diaporama en POO**

même chose mais en créant des objets Diaporama
```javascript
var diaporama1 = new Diaporama("photos1.txt", "idElementImg" );
```

**Pendu, scrabble, boggle...**
Pour ceux qui bossent, ont bossé ou veulent bosser des *jeux de mots*,
voici un lien pour charger la liste des mots du dico francais

http://www.rxlabz.com/labz/liste_francais.txt

## J4

![sprint](https://media3.giphy.com/media/3gcSvSHUpfprW/200.gif)

**Finalisation projet exploration**

[Compte Dev Microsoft](https://www.visualstudio.com/en-us/products/visual-studio-dev-essentials-vs.aspx) » donne accès à 6 mois gratuit sur [Pluralsight](https://www.pluralsight.com)

## Annexes

[Accessibilité checklist 1](https://checklists.opquast.com/fr/accessibility-first-step/)

[Accessibilité checklist 2](https://checklists.opquast.com/fr/accessibility-second-step/)