# Semaine 2

## Objectifs
+ Introduction à la programmation
+ Introduction à Git

#### Exercices HTML/CSS annexes pour la semaine

+ [maquette 4 colonnes](http://ironsummitmedia.github.io/startbootstrap-4-col-portfolio/)
+ [maquette 1 colonnes](http://ironsummitmedia.github.io/startbootstrap-1-col-portfolio/)
+ [Site basique](http://ironsummitmedia.github.io/startbootstrap-small-business/)

Et pour finir reproduire au plus proche les 2 premiers blocs de la page d'accueil de [Airbnb](https://www.airbnb.fr/)

![homebnb](assets/s2_airbnb_home.png)

# J1
[Questionnaire semaine 1](http://goo.gl/forms/esr9RdnvFt)

## Introduction à la programmation ( javascript )

[ Repl.it : Bac à sable JS](http://repl.it)

+ nombres
+ opérations mathématiques + / - *
+ chaines de caractères String [:book: :fr: Référence MDN ](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)
+ condition » [exemple](https://gist.github.com/rxlabz/3573e6790778df5eeb02)

+ Exercice : le programme demande la couleur du cheval blanc d'Henri 4, puis combien y a-t-il de 7 nains ?
» [correction](https://gist.github.com/rxlabz/5a075775239fe0272d6e)

#### Exercices
Calculatrice : le programme demande :
+ de choisir une opération (+ / - * ) ,
+ un 1er chiffre
+ un second chiffre
+ Le programme affiche ensuite le résultat de l'opération

**Exercice Dessiner c'est gagner**

[Ardoise magique](http://rxlabz.com/simplon/ardoise/index.html)

# J2

#### Rappels & QR : HTML / CSS
+ box model : margin, padding, border
+ float et clear
+ display : block, inline, inline-block

» [:+1: learnlayout :fr:](http://fr.learnlayout.com)

Exercices HTML/CSS ( maquettes, airbnb )

#### Scratch :cat:
+ [Scratch](https://scratch.mit.edu) : initiation ludique à la programmation
+ [Scratch : mode d'emploi](http://www.rxlabz.com/simplon/scratch/ScratchNotes1.pdf)

# J3

#### Introduction à la programmation Javascript

[Repl.it](http://repl.it)
Les conditions
+ booléen : true false
+ égalité === en JS il est prudent d'utiliser systèmatiquement le strictement égal ===
```javascript
console.log( 2 == '2'); // true
console.log( 2 === '2'); // false
console.log( 'a' !== 'b'); // true
console.log( 'A' == 'B'); // false
console.log( 'A' === 'B'); // false
```
+ inégalité !==
+ comparaisons > >= < <=
+ Opérateurs logiques
	+ ET && `(age > 18) && (age < 65)`
	+ OU ||`(age < 18) || (age > 65)`
+ [typeof](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Opérateurs/L_opérateur_typeof)
+ :warning: Attention aux conversions Texte-Nombre
	+ [Référence Number - MDN](https://developer.mozilla.org/fr-FR/docs/Web/JavaScript/Reference/Global_Objects/Number)
	+ [NaN » Not A Number](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/NaN) [isNaN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/isNaN)

[Exemples](http://jsbin.com/cugice/edit?js,console)

#### Exercice Devine un chiffre
Le programme demande de deviner un chiffre en 0 et 9 en 2 tentatives.
[Correction](https://gist.github.com/rxlabz/b673abaee282b66edfa6)

#### Exercice Calculette J2
[Correction](https://gist.github.com/rxlabz/9c76a3ddbbdb0b9df3c3)

#### Exercice login / password
+ Demander l'identifiant puis le mot de passe
+ vérifier que :
	+ l'identifiant saisi a plus de 4 caractères
	+ l'identifiant contient un @
	+ l'identifiant est "lea@gmail.com" et son mot de passe "12345"

[correction](https://gist.github.com/rxlabz/1508411d9a7a2936b684)

#### Exercice calcul mental
+ le programme tire au hasard une opération ( + * - ) et deux chiffres
+ le programme demande le résultat de l'opération à l'utilisateur » ex : "combien font 4 * 7"
+ affiche si la réponse est juste ou fausse

# J4

#### Introduction à la programmation Javascript

**Tableaux**

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
function addition(){

}
```
[Exemples de fonctions - JSBin](http://jsbin.com/fujida/1/edit?js,console)

#### Fonctions javascript utiles
**alert( message )**  permet d'afficher une petite fenêtre avec un message

**prompt( message )** permet d'afficher une petite fenêtre avec un message et une zone de réponse

**console.log( message )** permet d'afficher un texte dans la console du navigateur

#### Exercice
Reprendre l'exercice login/password en acceptant cette fois plusieurs paires mail/mdp et en donnant 4 essais à l'utilisateur.

Exemple » identifications valides : toto@gmail.com / 12345 ou titi@gmail.com / 54321 ...


#### Atom : packages
Emmet
+ [Demo interactive](http://docs.emmet.io)
+ [:memo: Emmet Memo](http://docs.emmet.io/cheat-sheet/)
+ [:video: Tutoriel FR (13mn)](http://www.grafikart.fr/tutoriels/sublime-text-2/emmet-376)

# J5

#### Introduction à la programmation Javascript


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

[Exemple boucles](http://jsbin.com/racucu/2/edit?js,console)

**Exercice Fizzbuzz**
le programme écrit les nombres entre 0 et 100.
+ Pour chaque multiple de 5 il écrit "buzz"
+ Pour chaque multiple de 7 il écrit "fizz"
+ Pour chaque multiple de 5 et 7 il écrit "fizzbuzz"

Vous pouvez essayer d'utiliser le modulo %

**Exercice calcul moyenne**

Un programme demande de saisir 10 notes ( une par une et de 0 à 20 ) et affiche la moyenne à la fin


[Exemple JS dans une page HTML](http://jsbin.com/jigaxe/1/edit?html,output)


#### Git

Initialisation d'un dossier git

```bash
$ git init
$ touch index.html
$ atom index.html
$ git status
$ git add index.html
$ git status
$ git commit -m "1ere sauvegarde"
$ git log
...
$ git commit -m "2nde sauvegarde"
...
```

Configuration
```bash
$ git config --global user.name "votreNom"
$ git config --global user.email votre@mail.com
```

#####  :octocat: Github

+ création d'un projet sur github "semaine2"
+ remote add : association de notre dossier local et le dossier github
+ push : publication de notre dossier local sur github

```bash
$ git remote add origin git@github.com:votreUser/semaine2.git
$ git push -u origin master
```

**Ressources Git**

+ [:memo: Memo git :fr:](https://training.github.com/kit/downloads/fr/github-git-cheat-sheet.pdf)
+ [Try git](https://try.github.io/levels/1/challenges/1)
+ [Hello Github](https://guides.github.com/activities/hello-world/)

+ [:book: Git :fr:](https://git-scm.com/book/fr/v1)

# :books: Bibliographie
[:book: :fr: Eloquent Javascript](http://fr.eloquentjavascript.net) Le Javascript de a à z

[WTFJS :us: ](http://wtfjs.com) un comportement parfois "étrange"...