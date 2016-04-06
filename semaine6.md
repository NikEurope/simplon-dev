# Semaine 6

Objectifs :
+ consolidation JS ( DOM )
+ Intro au responsive
+ Intro à Bootstrap

[Questionnaire semaine 5](http://goo.gl/forms/Gu310ab0n9)

[Questionnaire Simplon](https://docs.google.com/forms/d/1ium7o3SnHUIqAIXNuHJ4fal9WVgBcdlDhParrIPCrm4/viewform)

## J1

#### JS : Rappels

- **Object**
=> correction exercice pré-remplissage formulaire
- **Fonctions** : paramètres et renvoi
- **DOM** : manipulation de HTML avec JS : modification , création

#### Point projet Exploration / Restitution
Rendu le 16/12 => Atelier 21, 22, 23 décembre


# J2

## Exercice DOM/JS - sélection pays/capitale

=> [Base](http://jsbin.com/miyiwi/1/edit?html,output)
=> [Correction](http://jsbin.com/maxodo/edit?html,output)

## Intro Responsive Web Design

#### media queries

les medias queries permettent de définir des feuilles ou des régles CSS en fonctions de caractéristiques du navigateur, et du device
utilisé pour affiché une page html

```html

<!-- feuille de style pour écran ( ordinateur, tablettes, mobiles )-->
<link rel="stylesheet" href="styles.css" media="screen"/>

<!-- feuille de style pour impression-->
<link rel="stylesheet" href="impression.css" media="print"/>

<!-- feuille de style pour écran ( ordinateur, tablettes )-->
<link rel="stylesheet" href="styles_bigscreen.css" media="screen and (min-width:800px)"/>

<!-- feuille de style pour écran ( ordinateur, tablettes )-->
<link rel="stylesheet" href="styles_smallscreen.css" media="screen and (max-width:800px)"/>

```

Dans les feuilles de styles, certaines règles peuvent n'être appliquées que dans certaines conditions

La syntaxe est :

@media [logic] mediaType [and (condition) [and...]]

où logic = *only* || *not*, et [mediaType](https://developer.mozilla.org/fr/docs/Web/CSS/Media_queries) = screen || print || tv || ..

**Exemples**

@media screen and (condition)

@media only screen and (condition1) and( condition2 )

@media not print and (condition1)

```css

body{
	font-size:1.2em;
}

@media screen and (min-width:1024px){
	body{
		font-size:1.5em;
	}
}

@media screen and (min-width:800px){
	body{
		font-size:2em;
	}
}

```

**Les différents critères de condition**:
+ min-width, max-width, min-height, max-height
+ device-width, device-height
+ orientation
+ aspect-ratio, device-aspect-ratio
+ device-pixel-ratio
+ resolution

[Exemple - Responsive layout](http://jsbin.com/fawiko/1/edit?html,output)

[Media queries @alsacreations :fr:](http://www.alsacreations.com/article/lire/930-css3-media-queries.html)

[Media queries @open-classroom :fr:](http://www.alsacreations.com/article/lire/930-css3-media-queries.html)

[Responsive design :us:](http://learn.shayhowe.com/advanced-html-css/responsive-web-design/) => bien détaillé

[Common RWD techniques :us:](http://www.sitepoint.com/common-techniques-in-responsive-web-design/) avec de bonnes illustrations

[MDN media queries :fr: ](https://developer.mozilla.org/fr/docs/Web/CSS/Media_queries) : liste de medias features expliquées

## J3

**Pratique HTML / RWD**

Reprenez les maquettes HTML réalisées durant les 1ères semaines (
[maquette 4 colonnes](http://ironsummitmedia.github.io/startbootstrap-4-col-portfolio/) ,
[maquette 1 colonnes](http://ironsummitmedia.github.io/startbootstrap-1-col-portfolio/) ,
[Site basique](http://ironsummitmedia.github.io/startbootstrap-small-business/) et Airbnb) et essayez de les rendre plus "responsive".

#### Pratique JS
**Exercice DOM/JS - pays/capitale v2**
Cette fois ce ne sont pas les élements de la liste qui sont cliquables,
mais 2 boutons *suivant* et *précédent*, qui permettent de faire défiler les différents pays. cf. [base](http://jsbin.com/kefava/edit?html,js,output)
A l'ouverture de la page, le 1er élement de la liste doit être 'selected' et affiché dans la zone détail.

## J4

#### Introduction à [Bootstrap](http://getbootstrap.com)

Bootstrap est un framework/librairie CSS offrant :
- un système de grilles responsives
- l'homogéneisation de certains comportements entre les principaux navigateurs
- des composants ( [Dropdown](http://getbootstrap.com/components/#dropdowns),
[Button group](http://getbootstrap.com/components/#btn-groups), [Navigation bar](http://getbootstrap.com/components/#navbar)
[alertes modales](http://getbootstrap.com/javascript/#modals)...)
- un thème HTML/CSS de base et des [thèmes alternatifs](https://bootswatch.com/)
- une librairie d'icones
- ...

:book: Documentation officielle

+ [CSS :us:](http://getbootstrap.com/css)
+ [Composants :us: ](http://getbootstrap.com/components)
+ [Composants JS :us:](http://getbootstrap.com/javascript)


[:memo: Prendre bootstrap en main - OC](https://openclassrooms.com/courses/prenez-en-main-bootstrap)

[:tv: Utiliser Bootstrap :fr:](http://www.grafikart.fr/tutoriels/html-css/bootstrap-twitter-182)

BootStrap : [Prise en main :us:](http://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-get-started.php) ,
[gestion de formulaires :us:](http://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-forms.php)

[Composants Bootstrap :us:](http://www.w3schools.com/bootstrap/bootstrap_get_started.asp)

#### Autres frameworks CSS

[Foundation](http://foundation.zurb.com) : "concurrent" de Bootstrap

[PureCSS](http://purecss.io) : un autre...



### Git
#### Les branches
Les branches git permettent d'apporter des modifications à un dossier, tout en préservant l'état original, et en permettant facilement d'y revenir ( sans rien perdre de son "test").

Souvent la branche principale d'un projet reste sur le dernier "état fonctionnel",
et les modifications se font sur des branches jusqu'à ce qu'on soit sûr
qu'elles fonctionnent.

```bash
git branch maBrancheDeTest
git checkout maBrancheTest
```
ou en condensé

```bash
git checkout -b maBrancheTest
```
Une fois que l'on a effectué et commité les modifications souhaitées, on peut revenir à la branche principale,
*master* et fusionner les modifications effectuées dans l'autre branche.

```bash
git checkout master
git merge maBrancheTest
```

A présent la branche master contient les modifications effectuées sur *maBrancheTest*.
On peut maintenant supprimer la branche désormais inutile.

 ```bash
git branch -d maBrancheTest
 ```

#### Collaborer sur un projet : Fork et pull request
Le fork permet de créer dans son compte github,
une copie d'un projet existant, de manière à pouvoir y apporter des modifications,
et les proposer au propriétaire du projet par la suite

Une fois un projet forké sur github ( ou bitbucket.com ), on peut le cloner sur son poste avec la commande habituelle :
 `git clone https://github.com/moi/leprojet.git`

Une fois cloné, il faut créer une branche sur laquelle on apportera nos modifications.

```bash
git checkout -b mesModifications
```

Une fois les modifications terminées, on peut pusher notre branche sur Github
```bash
git push -u origin mesModifications
```

Pour faire un pull request il faut s'assurer que nos modifications sont applicables à la dernière version
du dossier original. En effet si des changements ont été effectués depuis nos modifications pourraient créer des conflits.
Pour s'assurer que notre fork est bien à jour, il faut ajouter le .git original ( celui du projet que l'on a forké )
dans la liste de nos remotes, avec le nom *upstream*

 ```bash
git remote add upstream http://github.com/auteur/projet.git
git branch -a
 ```
`git branch -a` permet de voir toutes les branches du projet : locales et distantes

 Ensuite pour mettre à jour notre projet local,
 et y intégrer les modifications qui ont été effectuées sur le dépot original (la branche upstream/master)
 ```bash
git fetch upstream
git merge upstream/master
```

Ensuite sur Github on peut créer une 'pull request' pour ajouter nos modifications au projet original.

[:tv: Forker / merger / pull requester sur Github :fr: 15mn](https://youtu.be/D5QGiIM1j20?t=13m19s)

**De la lecture sur le sujet**

![wwstime](https://media0.giphy.com/media/WQD6NEEsVTvxK/200.gif)

[:memo: Différents workflow pour travailler à plusieurs sur un projet :us:](https://www.atlassian.com/git/tutorials/comparing-workflows/centralized-workflow)

[:memo: using pull requests :us:](https://help.github.com/articles/using-pull-requests/)

[:memo: Fork a repo :us:](https://help.github.com/articles/fork-a-repo/)

[:memo: fork, branches, commits & pull request :us:](https://github.com/sevntu-checkstyle/sevntu.checkstyle/wiki/Development-workflow-with-Git:-Fork,-Branching,-Commits,-and-Pull-Request)


## J5

![h5](https://media2.giphy.com/media/mbNF0QlmkXx6w/200.gif)

## Annexes

**[Luke Wroblewsi, User Xperience Expert](http://www.lukew.com)**

:tv: Conférence [part1](https://www.youtube.com/watch?v=ZhnN1CdwvTs) [part2](https://www.youtube.com/watch?v=br_szl80J1M)

[:tv: Série de vidéos sur l'ergonomie d'applications mobiles'](https://www.youtube.com/watch?v=xAKnPtbfNfY&list=PLg-UKERBljNy2Yem3RJkYL1V70dpzkysC)
