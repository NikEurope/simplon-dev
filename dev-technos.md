
# Front-end
## Web
  - **HTML5**
  - **CSS3**
    - libs
      - *bootstrap* : lib CSS ... foundation
    - outils
      - Pré-processeurs : **Sass** : syntaxe css "enrichie" ( / Less / Stylus )
      - postCSS
  - **JS : EcmaScript 5 (es5)**
    - librairies :
      - *jquery*
      - **React / Angular** ( ...Ember, Backbone, VueJS ) / Meteor
    - outils / tools
      - **NPM Node Package Manager** (± équivalent de apt-get ) / package.json
        - gérer les librairies et outils utilisés par un projet
        - créer des raccourcis pour exécuter des scripts
      - **Babel** » convertir du es6/jsx en js "classique"(es5) / .babelrc
      - **webpack**, browserify : gérer les modules es6
      - **npm**, gulp, grunt, broccoli : outil "d'orchestration" d'autres outils ( babel, sass, minification...)

## ( ... Mobile : *Android* / iOS )

----------------------------------------------------

# Back-end :
  - OS serveur: **ubuntu** (... debian / centOS) | ( windows / mac )
  - serveurs : **Apache** (... NGinx ) ... NodeJS | ( serveur Java : tomcat, jboss... )
    - **(L)AMP** : Linux **Apache Mysql PHP**
      - **PHP 5.4+ / MySQL** ... JS | (Ruby / Python / Java / .Net ...)
        / autres BDD PostGreSQL / Oracle / NoSQL : **MongoDB**, Redis, CouchDB, ...DB

	- Librairie PHP
	  - **silex** / **Symfony** ( Laraval, Zend, Lumen, Slim...)
	  - *doctrine*

    - outillage :
      - **Composer** : gestion de librairies PHP ... (PEAR)
      - **Vagrant** / **puphpet**(puppet) » utilisation virtualbox pour créer des environnements serveurs
      - **Docker** ± comme vagrant mais avec des images moins lourdes
