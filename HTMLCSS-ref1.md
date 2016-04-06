# Code Academy : HTML CSS

# HTML : Structure de base d'une page
---

- Doctype : le type de document
```html
<Doctype! html>
```
- HTML
```html
<html> </html>
```
- Head : Entête : Titre, méta données,  styles, scripts
```html
<head>
<title></title>
</head>
```
- body
```html
<body> </body>
```
+ la balise permet de définir un attribut lang
```html
<body lang="fr_FR">
```

## Structure minimale d'une page HTML5

```html
<Doctype! html>
<html>
	<head>
	<title>Title de la page</title>
	<!-- ... -->
	</head>
<body>
	...
</body>
</html>
```

## Body : le contenu visible de la page

- paragraphe
```html
<p>Un paragraphe de texte</p>
<p>Un autre de texte</p>
```
- les balises h1 à h6 permettent de définir des titres des plusieurs niveaux

- insertion d'image : <img>
```html
<img src="dossier/fichier.jpg" />
```

- insertion d'image dans un lien <a><img>
```html
<a href="lien.html"><img src="dossier/fichier.jpg" /></a>
```

## Liens

[Mozilla : Introduction au HTML](https://developer.mozilla.org/fr/docs/Web/Guide/HTML/Introduction )

# HTML II

- indentation
- ul/li & ol/li
- comment
```html
<!— … —>
```
- p style="" : font-size, color, font-family
- p style="" : background-color, text-align
``` html
<strong>/
```
- <em> Emphased


# HTML III

- table , tr, td
``` html
<tbody> <thead><th>
```
- 
```html
<th colspan="">
```
- div ( boites de couleurs )
- span

## Exo : Cliquable Photo Page
tableau 3*3 avec img cliquable et theader

# CSS
```html
<link type="text/css" re"stylesheet" href="" />
```
- element selector p span
- internal style
- trouver erreur ponctuation
- /* comments */
- couleur hexa
- px & em
- serif / sans-serif / cursive
- font-family multiple : Times, serif
- background-color
- width / height
- border : 1px solid blue
- a text-decoration

# CSS II
- display
- margin & -left -blt
- padding
- border-radius
- font-weight

# CSS selector
- children div div div h3
- universal *a
- .class & #id
- selector:pseudo-class_selector » a:hover, a:link, a:visited
- element:first-child
- element:nth-child(2)
- display:inline-block

# Positionnement CSS  - CSS Layout
- BoxModel : margin border padding content tlbr
- display : block inline-block inline none
- marge négative
- float : right left
- clear : left right both
- positionnement absolu : position:absolute
- position:relative
- position:fixed
- z-index