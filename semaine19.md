# Semaine 19

## Objectifs :
- JS "moderne" : ES6 / Babel
- React
- NodeJS/Express


## J1

[Rappel JS](https://developer.mozilla.org/fr/docs/Web/JavaScript/Une_réintroduction_à_JavaScript)

### JS moderne

#### Ecmascript ES6 / ES2015

+ [Babel](http://babeljs.io) : transforme votre code es2015 en code es5 ( javascript "normal" )
+ [Learn ES2015](http://babeljs.io/docs/learn-es2015/)
+ [Essayer ES2015](http://babeljs.io/repl/)
+ [Babel CLI](https://babeljs.io/docs/usage/cli/)

+ [ES6 Essentials](http://www.2ality.com/2015/08/getting-started-es6.html)

**Installation Babel-cli**
```bash
npm init -y
sudo npm install babel-cli babel-preset-es2015 --save-dev
echo '{ "presets": ["es2015"] }' > .babelrc

./node_modules/.bin/babel script.es6 --watch --out-file script.js
```
+ initialisation de npm
+ installation de babel et de la config de transpilation par défaut
+ création du fichier de config de babel .babelrc
+ ajout du preset es2015 ds .babelrc
+ lancement de la surveillance du fichier script.es6

**Principales nouveautés**

[Exemple](https://github.com/Simplon-lyon/mini-intro-es2015)

- classes
  - constructor
  - héritage via extends
  - méthodes et get / set
- fonctions fléchées
- fonctions : valeur par défaut de paramètres / liste indéfinis de paramètres
- templates
- object literals
- destructuration
- ...

[ :tv: intro es6/es2015 :fr:](https://www.youtube.com/watch?v=uL9uAAzkFmI)

#### Putain de code » articles :fr: sur es6
+ [:memo: Fonctions fléchées :fr:](http://putaindecode.io/fr/articles/js/es2015/arrow-functions/)
+ [:memo: objet literals :fr:](http://putaindecode.io/fr/articles/js/es2015/object-literals/)
+ [:memo: nouvelles méthodes d'array :fr:](http://putaindecode.io/fr/articles/js/es2015/array-methods-addition/)
+ [:memo: Maps et LeakMaps :fr:](http://putaindecode.io/fr/articles/js/es2015/maps-weakmaps/)
+ [:memo: paramètres rest et opérateur spread :fr:](http://putaindecode.io/fr/articles/js/es2015/rest-spread/)

#### La bible de l'ES6
+ [Exploring ES6](http://exploringjs.com/es6/)
  + [classes](http://www.2ality.com/2015/02/es6-classes-final.html)
  + [modules](http://www.2ality.com/2014/09/es6-modules-final.html)
  + [tableaux](http://www.2ality.com/2014/05/es6-array-methods.html)


## J2

#### NPM
- gestionnaire de librairie JS / node + execution de scripts shell
- package.json
  - dependencies : liste des lib utilisées dans le projet
  - devDependencies : liste des libs/outils utilisés pour le dev
  - scripts : scripts shell

`npm init -y` créé un fichier de config ( -y » force les valeurs par défaut)
`npm install` installe les dépendances décrites dans le fichier de config
`npm run nomScript` execute un script déclaré dans le fichier package.json

#### Exemples ES6

+ rappels : map, filter, reduce » en plus pratique en es2015

## J3

#### Les promesses en JS

+ [:memo: Les promesses en JS :fr:](https://zestedesavoir.com/tutoriels/446/les-promesses-en-javascript/)
+ [:memo: JS promise :us:](http://www.sitepoint.com/overview-javascript-promises/)
+ [:memo: ES6 Les promesses / Babel](http://babeljs.io/docs/learn-es2015/#promises)
+ [:book: ES6 Les promesses ref](http://exploringjs.com/es6/ch_promises.html)

#### [React](https://facebook.github.io/react/)

Librairie de création de composants pour le web ( cf. React Native pour mobile )

- React.createClass » crée un composant React
  - composant.render() » renvoie le html (jsx) de représentation du compo

  - composant.props : informations injectées depuis l'extérieur
  - composant.state : information que le composant manipule, gère, modifie....

  - évenements et appel de méthodes "internes" du composant

  - cycle de vie :
    - componentDidMount : appelé qd le compo a été affiché
    - componentWillUnmount : appelé qd le compo va être supprimé
    - ...


+ [Exemple livecode React 1](https://github.com/Simplon-lyon/intro-react-jsx) ( sans config :cold_sweat: )


## J4 : un petit rab de config ?

![yeah](https://media3.giphy.com/media/fKBh0mt02CypW/200.gif)


Vous pourriez essayer de configurer npm pour ne plus avoir besoin d'être exécuté en sudo...

+ [Régler les permissions npm (utilsation sans sudo) ](https://docs.npmjs.com/getting-started/fixing-npm-permissions)
+ ou [NPM without npm](https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md)

A propos de config, un petit tour du côté des scripts shell pourrait être bénéfique.

Un script de ce genre, enregistré dans un fichier *newpj.sh* , permet par exemple
d'exécuter toutes les lignes de commandes nécessaires pour une initialisation
très basique d'un projet react/babel ( :warning: nécessite que npm marche sans sudo).

```bash
#!/bin/sh
# la première ligne permet de définir par quelle application le script doit être interpretée

echo "initialisation d\'un projet react/babel..."
git init
npm init -y

echo 'creation du .gitignore'
echo 'node_modules\n*.iml\n*.js' > .gitignore # ecrit une liste de fichiers à ignorer dans git

echo 'installation outils dev...'
npm install -D babel-cli babel-preset-es2015 # -D est le raccourci de de --save-dev

echo 'installation outils dev'
npm install -S react react-dom

echo 'creation du README'
touch README.md

echo 'git » 1er commit'
git add .
git commit -m "1er commit"

echo 'initialisation terminée : '

ls -a
```

pour l'executer : `sh newpj.sh`

+ [intro Bash :fr:](http://www.trustonme.net/didactels/148.html)
+ [intro script shell - OC :fr:](https://openclassrooms.com/courses/reprenez-le-controle-a-l-aide-de-linux/introduction-aux-scripts-shell)
+ [cours complet :fr:](http://aral.iut-rodez.fr/fr/sanchis/enseignement/bash/)

#### React

+ [Exemple livecode React 1](https://github.com/Simplon-lyon/intro-react-jsx) ( sans config :cold_sweat: )
+ [Tutoriel](https://facebook.github.io/react/docs/tutorial.html)
+ [Animation](https://facebook.github.io/react/docs/animation.html)

## Annexes

+ [:tv: Workshops Le Wagon](https://www.youtube.com/playlist?list=PLkbmdtbypn7RqYSvBqewZNtf9uFEYs0KN)
  + [:tv: Web component design](https://www.youtube.com/watch?v=ewxMpl09OwE)
  + [:tv: Intro dataviz avec D3](https://www.youtube.com/watch?v=ZEtyr9C01cg)  [-> PDF pour suivre](https://github.com/martindaniel4/d3Wagon/blob/master/d3Wagon.pdf)
  + [:tv: Bonnes pratiques de l'emailing marketing :fr:](https://www.youtube.com/watch?v=jEBDJQP8qyU)

+ [:book: NPM documentation](https://docs.npmjs.com)
+ [bases de NPM](http://maxlab.fr/2015/03/comprendre-et-maitriser-npm-introduction/)

+ [The art of ui animation](http://markgeyer.com/pres/the-art-of-ui-animations/#/)
+ [:book: UI Design & Dev](http://www.anotheruiguy.com/ux-design-dev/_book/) » bouquin en ligne sur les nombreux trucs à creuser pour le dev front-end

+ [Plus loin avec React - exemples](https://github.com/facebook/react/wiki/Examples)
+ [Config projet React : état de l'art 0.14.7]

+ [Firebase](https://www.firebase.com/docs/web/guide/understanding-data.html)
+ [Express](http://expressjs.com)

