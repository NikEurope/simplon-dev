# Semaine 24

Objectifs :
- Back
  - Symfony
  - PHPUnit
- Front : consolidation

## J1

**Rappels**

+ [Composer](composer)

### <a href="https://phpunit.de" target="_blank">PHP_Unit</a>

```bash
$ composer global require phpunit/phpunit
```

+ <a href="https://phpunit.de/manual/current/en/writing-tests-for-phpunit.html" target="_blank">Tests avec PHP Unit</a>

### [Symfony3](http://symfony.com)

- <a href="http://symfony.com/download" target="_blank">installation</a>
  - <a href="https://github.com/symfony/symfony-installer" target="_blank">Symfony installer</a>

```bash
$ symfony new mon_projet
$ cd mon_projet
$ php bin/console server:run
```
Ouvrir <a href="https://localhost" target="_blank">localhost:8000</a>

**projet demo**

```bash
$ symfony demo
$ cd symfony_demo
$ php app/console server:run
```

#### POO

Une des raisons d'être de la POO est d'offrir un ensemble d'outils et de concepts,
permettant d'obtenir du code "simple" à faire **évoluer**.

- **le typage** permet d'assurer la cohérence du code
- **l'héritage** permet de créer des déclinaisons d'une même entité "originelle"
- les **interfaces** permettent de définir des catégories d'objet, définies par des "savoirs-faire" ( des méthodes ), et sans origine communes

- le principe d'**encapsulation**, invite à réfléchir à la construction des objets en distinguant leur "partie visible" (API) de leur mécanismes internes (private, protected).
- le principe de **composition**, préconise qu'une entité ne doit pas gérer trop de chose différentes,
et qu'en **déléguant** des sous-tâches à d'autres entités,
le système est plus souple qu'en créant des monstres "multi-tâches"

- les **design patterns** sont des schema/stratégies pour régler de manière "souples" à l'aide d'outils de la poo,
des problématiques récurrentes de la programmation logicielle ( faciliter l'ajout de nouveaux types , de nouvelles fonctionnalités, permettre l'annulation de commandes, )

- **MVC / Model-View-Controller** est un agglomérat de design pattern destiné à organiser la séparation données / vue / interactions

- **injection de dépendances** ( inversion de contrôle ) : amène l'idée que si une entité à besoin d'autres entités,
 il est préférable de déléguer la construction des autres entités ( les dépendances ).

:book: Lecture conseillée :
<a href="https://books.google.fr/books/about/Design_patterns.html?hl=fr&id=zzdn6U95_f8C" target="_blank">Design pattern la tête la 1ère</a>

## J2
**Back-end**
- Symfony :
  - <a href="http://symfony.com/doc/current/quick_tour/the_big_picture.html" target="_blank">quick tour </a>(Big picture, View, Controllers, Architecture)
  - parcourez les contrôleurs et les vues du projet symfony_demo,
  - essayez d’appliquer ce que vous comprenez dans un nouveau projet : modifier la page d’index par défaut, ajouter un lien vers une autre page, créer le contrôleur et la vue twig de cette nouvelle page… au mieux essayez de refaire un (bout de) projet php existant avec Symfony
- mettre à jour votre compte Github, au minimum :
  - fichier README avec lien vers demo et cours descriptif des sujets étudiés dans le projet

**Front-end** :
- <a href="http://opquast.com/fr/" target="_blank">Opquast</a>

- **SVG via JS** <a href="http://svgjs.com" target="_blank">SVG.js</a> ou <a href="http://snapsvg.io" target="_blank">snapsvg.io</a>

```javascript
var scene = SVG('scene').width(500).height(300);
scene.circle(10).x(30).y(40);
```

- **Animation via js** : <a href="http://velocityjs.org" target="_blank">velocity.js</a>
```javascript
// velocity sans jquery : chainage d'anims
Velocity( element, {x:30}, {complete:function(){console.log('x complete');}} );
Velocity( element, {y:30}, {complete:function(){console.log('y complete');}} );
```
<a href="http://www.rxlabz.com/labz/anims/4p_rect_libs.html" target="_blank">Exemple animation SVG avec Velocity.js</a>
 / <a href="https://github.com/Simplon-lyon/dev-web/blob/master/front/html/anims/4p_rect_libs.html" target="_blank">sources</a>

### Annexes

+ <a href="http://exercism.io/" target="_blank">Exercism.io</a> Exercice pour test unitaires JS/PHP/....
  + <a href="http://exercism.io/cli" target="_blank">CLI</a>

+ [PHP Pandas](http://daylerees.com/php-pandas/)
+ [PHP the right way](http://www.phptherightway.com)

+ [:tv: Machine learning :us:](https://www.youtube.com/watch?v=cKxRvEZd3Mw)
+ [:tv: Machine Learning : AlphaGo :us:](https://www.youtube.com/watch?v=qWcfiPi9gUU)

