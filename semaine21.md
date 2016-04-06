# Semaine 21

## Objectifs
+ Module ES6 : Webpack
+ Vagrant / PuPhpet


## J1

- Techlunch : PHPStorm
  - projet et modèle de projet
  - gestion Database
    - accès contenu des tables
    - accès console pour test SQL
  - live templates : snippets / raccourcis de code » pour créer les siens : "Save as live template..."
  - Git cf. settings/version Control & panneau Version Control
  - FTP : Menu Tools / Deployment / Configuration » config (S)FTP »

## J2

### React

#### Declaration de composant

**ES5**
```javascript
var MonCompo = React.createClass({
	getInitialState:function(){
		// ...
	},
});
```

**ES2015/ES6**
```javascript
class MonCompo extends React.Component{
	constructor(props, context){
		// ...
	}
}
```

+ [Cycle de vie des composants React]()

#### Données de composants

Les composants React distinguent deux types de données :
 - les données injectées et non modifiables : les props
 - l'état / state : les données gérées par le composant lui même : le state

## J3

### React

+ [Transitions](https://facebook.github.io/react/docs/animation.html) : CSSTransitionGroup
:warning: react-with-addons.min.js à la place de react.min.js

+ Développement mobile : [React native](https://facebook.github.io/react-native/)

Plus Loin avec React
+ [React Router](https://github.com/reactjs/react-router)
+ Gestion des données dans une application "complexe"
  + Préconisation [Flux](https://facebook.github.io/flux/docs/overview.html)
  + » exemple [Redux](https://github.com/reactjs/react-redux)
+ Animation++ [React Motion](https://github.com/chenglou/react-motion)


### PHP POO

+ Classes abstraites

Classe de base, définissant des méthodes et des propriétés, mais destinée à ne pas être instanciée
Seules les classes qui hériteront de la classe abstraites pourront être instanciés


```php
abstract class ObjectManager{
	public $tableName;

	public function connect(){
		//
	}

	public function removeItem(itemId){
		$q = "DELETE FROM $tableName WHERE id=:id";
		// ...
	}
}
```

+ Traits : ajouter des fonctionnalités à plusieurs classes sans lien d'héritage

```php
Trait
```


