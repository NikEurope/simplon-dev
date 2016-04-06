# Semaine 3

## Objectifs
+ HTML : HTML5 et sémantique, élements formulaires
+ CSS : sélecteurs avancés & CSS3

## A faire dans la semaine

#### JS pour **mercredi 28/10**

**Login password avec tableaux**

Bonus => **proposition d'inscription si mail inconnu**
+ Si le mail saisi par l'utilisateur n'est pas connu, le programme lui propose de s'inscrire.
+ si l'utilisateur accepte, le programme stocke le nouveau mail, demande un mot de passe et le stocke aussi

#### Airbnb ( cf. [semaine 2](semaine-2.md) ) à rendre sur github **vendredi 30/10**.

# J1

[Questionnaire Prog. JS](http://goo.gl/forms/Gm5TB9EMbo)

#### Correction JS

**Fizzbuzz** [correction](http://jsbin.com/quvaci/2/edit?js,output)

**Moyenne**
[correction](https://gist.github.com/anonymous/f958b7b9d32b877175a5)



#### Sites d'entrainement JS
+ [code academy](https://www.codecademy.com/fr/tracks/javascript)
+ [khan academy ](https://fr.khanacademy.org/computing/computer-programming/programming) (jusqu'au chapitre 'objets')
+ [code combat](http://codecombat.com)

#### HTML


```html
<!DOCTYPE HTML>
<html>
<head>
        <title>Titre principal de la page</title>
        <meta charset="utf-8">
        <meta name="description" content="165c. uniques">
</head>
<body>
    <section>
        <header><!-- Entête de la zone considérée --></header>
        <nav><!-- Nav. principale de la page -> site --></nav>
        <article>
            <header>Titre de l'article</header>
            <section>

            </section>
            <aside>Annexes</aside>
        </article>
        <footer><!-- Pied-de-page de la page -> site --></footer>
    </section>
</body>
</html>
```
[:memo: HTML5 : Nouveaux éléments de section, article, header, footer, aside, nav - Alsacréations :fr:](http://www.alsacreations.com/article/lire/1376-html5-section-article-nav-header-footer-aside.html)

[HTML5 : quel tag choisir ? :us: ](http://html5doctor.com/downloads/h5d-sectioning-flowchart.png)

[:memo: Exemple de structuration HTML5 - PDF :fr: ](https://www.vectorskin.com/wp-content/uploads/2010/09/structure_HTML5.pdf)

#### CSS

# Ajouter des styles à un document

- inline
```html
<a href="" style="color:red;" />
```

- intégré ( embedded )
```html
<style type="text/css">
a{
background-color:grey; color:white
} </style>
```

- externe
```html
<link rel="stylesheet" type="text/css" href="styles.css"></link>
```


- externe : importer une feuille de style dans une autre feuille de style
```css
@import "styles.css";
 span {
     border: medium black dashed;
     padding: 10px;
 }
```

#### Exercices

**Journal et articles**

Créez une home page de journal avec des liens vers 2 pages d'articles
![schema-exo](https://www.evernote.com/l/AAF3aX3WP6BF4JiF6VaTrKzJwUzajxWSHi0B/image.png)

# J2

#### Formulaire

[Les principales balises de formulaire - JSBin ](http://jsbin.com/taxayo/6/edit?html,output)
+ form
+ fieldset / legend
+ input
  + type text
  + type radio
  + type check
  + type email color date [... voir liste complète](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
+ textarea
+ select

[ Style de formulaire - Exemple :us: ](https://24ways.org/2009/have-a-field-day-with-html5-forms)


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


#### CSS positionnement

Comme expliqué [ici](http://fr.learnlayout.com) il y a 4 types de positionnement en CSS :
+ **static** : c'est le type de positionnement par défaut qu'on utilise depuis le début

Les 3 autres positionnement utilisent 4 nouvelles propriétés : left, right, top, bottom.

![TRBL](http://help.adobe.com/fr_FR/FlashPlatform/reference/actionscript/3/images/rectangle.jpg)

+ **relative** : position TRBL par rapport à **la position qu'un objet devrait occuper si il était en position static**
+ **absolute** : TRBL par rapport à son plus proche parent positionné en relative, fixed ou absolute ( ou body s'il n'y en a aucun)

[Exemple 1](http://alistapart.com/d/css-positioning-101/example_e.html)
[Exemple 2](http://alistapart.com/d/css-positioning-101/example_f.html)

+ **fixed** : position TRBL par rapport à l'écran ( viewport ), ne bouge pas en cas de scrolling. Il n'a pas d'incidence sur son entourage.

Ces positionnements peuvent vous amener à devoir gérer :
- la profondeur ou ordre d'affichage [**z-index** :memo: :fr:](http://www.alsacreations.com/astuce/lire/84-comment-fonctionne-la-proprit-css-z-index.html) : la plus grande valeur est au 1er plan; et ne fonctionne qu'avec des objets positionnés en fixed, relative ou absolute.

**Exemple de position relative**
Le carré bleu est positionné en *relative* » left:100px
![exemple relative](https://www.evernote.com/l/AAG8OtnG8BpLxpkNRDi82ybNV7ANi56nts8B/image.png)

Exemple de position absolute : deux div imbriquées sans width, height ni border )

![exemple relative](https://www.evernote.com/l/AAE3u0LMJhlHiaRDUt-nRfh2ALzgXNDiHs4B/image.png)

[:memo: Bon tour d'horizon détaillé du positionnement via float, display et position](http://learn.shayhowe.com/html-css/positioning-content/)

[:memo: Bon article sur les positions CSS :us: ](http://alistapart.com/article/css-positioning-101)


#### CSS TIPS
:warning: pour éviter que les marges et les padding soit ajoutés à la largeur width d'un bloc

```html
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}
```

#### CSS auto-découverte

+ overflow : visible, hidden, scroll

+ h1, h2 » **union** : appliquer une même règle à plusieurs sélecteurs
+ .boite .item » **descendant** : appliquer une règle à des descendants
+ .header > h1 » **descendant immédiat**

+ ::first-line
+ ::first-letter

+ :before
+ :after

+ :first-child
+ :last-child
+ :nth-child(n)
+ :nth-last-child(n)

[les 30 principaux sélecteurs CSS](http://code.tutsplus.com/fr/tutorials/the-30-css-selectors-you-must-memorize--net-16048)

#### CSS extras

:dart:	[Entrainement sélecteurs CSS](http://flukeout.github.io)

:memo: [Bonnes pratiques CSS :fr:](http://openweb.eu.org/articles/grands-principes-de-construction-moderne-de-css)

:memo [Unités de mesure :fr:](http://outils-css.aliasdmc.fr/unites-de-longueurs-css.php)

# J3

:warning: vérification tout le monde est inscrit au groupe simplon-lyon sur github

#### CSS colors
+ hexadecimal #FFAA00
+ rgb( 255, 160, 0) » red green blue » pour chaque couleur une valeur de 0 à 255
+ rgba( 255, 160, 0, 0.3) » red green blue alpha(=opacité)
+ hsl(60,100%,100%) » hue saturation light » teinte saturation luminosité
	+ hue R0 V120 B240
	+ 100% = saturation max » 0 équivaut à un niveau de gris
	+ 100% = luminosité max, 0 = noir
+ hsla( 60,100%,100%, 0.5 )

**Opacité** : >= 0 && <= 1

```html
	opacity : 0.3;
```
:warning: mal géré par [vieux navigateurs](https://developer.mozilla.org/fr/docs/Web/CSS/opacity)

[Référence color MDN :fr:](https://developer.mozilla.org/fr/docs/Web/CSS/color_value)
#### CSS background

+ background-color
+ background-color transparent
+ background-image : url("...")
+ background-repeat » no-repeat, repeat,repeat-x, repeat-y
+ background-position » 1. décalage horizontal / 2.vertical || left top / right top / ...
	+ pour centrer : 50%

**raccourci** »»»  background : #color url("...") 50% no-repeat

**Exercice**

En partant de [ce code](http://jsbin.com/dinugehera/edit?html,output),
représentez ces notifications en ajoutant seulement des styles css, sans rien toucher dans le body

![img-modele](https://www.evernote.com/l/AAH8MzSrArBBbJSlookIlDitMMhIiQvJSk8B/image.png)

Icones
+ http://rxlabz.com/simplon/files/icons/icon_check_white.png
+ http://rxlabz.com/simplon/files/icons/dialog-warning.png

[**Correction notifs css**](http://jsbin.com/rejara/edit?html,output)

#### :trophy: Webdesign / CSS awards

+ http://www.awwwards.com/
+ http://www.thefwa.com/
+ http://www.cssdesignawards.com/
+ https://www.thebestdesigns.com/
+ http://www.csswinner.com/winners


#### Questionnaire
[Votre avis sur la formation](http://goo.gl/forms/7NKqYfkLsS)

#### Corrections JS / Dojo

+ **Calculatrice**

+ **Calcul mental**

+ **Password login Form**

+ **Password login tableaux**

+ **numberToRoman**

# J4

Cette journée est destinée à revoir les points abordés qui restent obscurs et/ou qui demandent à être revus.

Pour ceux qui ont envie de nouveaux défis, voilà quelques pistes HTML/CSS et JS.

### HTML/CSS : Pratiquer

**Nouvelle version de votre CV**

**Reproduire au plus proche la page d'accueil de http://acme-world.com**
+ notez l'effet de survol sur les principaux boutons du menu » essayez de les refaire : d'abord sans, puis avec l'animation

![captyre-acme](https://www.evernote.com/l/AAETnNTLnt5M758O3QhLgDMog3UFlO6GedAB/image.png)

**Reproduire au plus proche la page de contact COMPLETE http://acme-world.com/contacts**

### JS : Pratiquer

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

# J5

![thanks](https://media0.giphy.com/media/FyH83LEK2hytq/200.gif)

# Annexes de la semaine

#### Scratch :cat:
+ [Scratch](https://scratch.mit.edu) : initiation ludique à la programmation
+ [Scratch : mode d'emploi](http://www.rxlabz.com/simplon/scratch/ScratchNotes1.pdf)

#### Videos
[:tv: Témoignage et conseil d'une dev junior](https://www.youtube.com/watch?v=B22o_yeDE_s)

#### Git suite

+ Récupération d'un dossier depuis Github

```html
$ cd chemin/dossier/de/destination
$ git clone chemin/github/du/projet.git
```

[:book: Contribution à un projet :fr: ](https://git-scm.com/book/fr/v1/Git-distribué-Contribution-à-un-projet)

[:book: Hello Github :us:](https://guides.github.com/activities/hello-world/)
