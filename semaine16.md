# Semaine 16

Objectifs :
- PHP POO
- Wordpress
- Site promo

## J1

[Rendus](https://docs.google.com/spreadsheets/d/1_3hKUqEXERYwRaanYfWzpKfMfiRVSr8-R8Oq846BlS8/edit?usp=sharing)

[Questionnaire semaine 14/15](http://goo.gl/forms/7SnkJ7MK0R)

#### [Wordpress](http://fr.wordpress.org)
- installation
- prise en main du backo
- thèmes
- personnalisation

#### Correction Donatello - [PHP simple](https://github.com/Simplon-lyon/donatello-basic)

## J2

#### Logs PHP

```php
error_log( "test de log : ".mktime() );
```

Fichier de log apache : `/var/log/apache2/error.log`

```bash
$ tail -F /var/log/apache2/error.log
```

### PHP : Typage

- [typage](http://php.net/manual/fr/language.oop5.typehinting.php) / [Les types PHP](http://php.net/manual/fr/language.types.php)

Lorsqu'une fonction est appellée avec des arguments,
elle s'attend à recevoir un certain type de données.

Le javascript est un langage *non typé*, il ne permet pas ce genre de précision ( d'où [Typescript](http://www.typescriptlang.org) ...).
PHP5 permet un peu de typer, et PHP7 encore un peu plus.

Certaines fonctions PHP attendent des paramètres d'un certain type :

```php
echo array_sum([4,7]);
echo array_sum(8); // warning : array attendu
```

Pour nos fonctions aussi nous allons pouvoir préciser les types des paramètres attendus.

```php
<?php
function min( array $valeurs ){
	//
}
?>
```
:warning: en PHP5 on ne peut pas typer les paramètres avec des valeurs *scalaires* int, float, boolean, string.

Par contre on va pouvoir utiliser nos propres types d'objets, nos classes

### PHP : Définition

- classes
 - propriétés / attributs
 - constantes
 - constructeur
 - méthodes
   + [arguments et méthodes](http://php.net/manual/fr/functions.arguments.php)
- [instanceof](http://php.net/manual/fr/language.operators.type.php)
- héritage
- Interfaces

+ [Support intro POO PHP PDF](docs/intro_poo_php.pdf)

```php
<?php
class Panier{
	// constantes
	const FRAIS_PORT = 7.2;

	private $client;

	// propriétés
	public $produits;

	public function getTotal(){
		//
	}

	// constructeur
	function __construct(Client $client) {
		error_log('nouveau panier...' );
	}

	// méthodes
	function ajouteProduit(Produit $produit){
		$this->produits[] = $produit; // ajoute un element à un tableau == array_push($tableau, $item);
	}
}

class Produit{
// ...
}

class Client{
// ...
}

?>
```
+ [**Exemple classes Formes**](https://github.com/Simplon-lyon/dev-web/tree/master/php/intro_poo/formes)
+ [**Exemple classes Panier**](https://github.com/Simplon-lyon/dev-web/tree/master/php/intro_poo/panier)

+ Documentation du code `/** ... */`

+ [:memo: PHP POO - OC](https://openclassrooms.com/courses/programmez-en-oriente-objet-en-php)

+ [:tv: PHP POO - Grafikart](https://www.grafikart.fr/formations/programmation-objet-php)

+ [:book: Design patterns tête la première](https://www.google.fr/search?q=design+pattern+t%C3%AAte+la+premi%C3%A8re+-+Recherche+Google&oq=design+pattern+t%C3%AAte+la+premi%C3%A8re+-+Recherche+Google&aqs=chrome..69i57.206j0j7&sourceid=chrome&es_sm=91&ie=UTF-8#q=design+pattern+t%C3%AAte+la+premi%C3%A8re)
+ :fire: [:book: Design patterns tête la première](https://www.google.fr/search?q=design+pattern+t%C3%AAte+la+premi%C3%A8re+-+Recherche+Google&oq=design+pattern+t%C3%AAte+la+premi%C3%A8re+-+Recherche+Google&aqs=chrome..69i57.206j0j7&sourceid=chrome&es_sm=91&ie=UTF-8#q=design+pattern+t%C3%AAte+la+premi%C3%A8re)

+ [:book: Référence php.net](http://php.net/manual/fr/language.oop5.php)

_______________________

#### [Trello Profils](https://trello.com/b/ZBVjY6rs/profilssimplonlyon)

- [inscription groupe trello](https://trello.com/invite/b/ZBVjY6rs/6c9ef89f1e22243b5b58ad58a9abf21b/profilssimplonlyon)

_______________________

## J3

+  Projet profils : découpage sous-équipes / objectifs
	- finalisation maquettage
	- définition des données DB & JS

_______________________

## J4

![scrum](https://media0.giphy.com/media/PiL8nejwL3T6o/200.gif)

+ Sprint : Profils

## J5

![gong](https://media.giphy.com/media/UatRnEUNX8iCQ/giphy.gif)

## Annexes

+ [PHP : plus loin avec variables OC](https://openclassrooms.com/courses/allez-plus-loin-avec-les-variables)

