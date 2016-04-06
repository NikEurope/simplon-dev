# PHP

## Installation
+ [LAMP : Linux Apache Mysql PHP](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-14-04)

```php

// variables
$nom = "Dupond";
$prenom = 'Jack';
$age = 27;

// fonction
function salut( $nom ){
	echo "Hola ".$nom;
}

salut("Internet");

// tableau
$jours = ["lundi", "mardi", "mercredi", "jeudi","vendredi"];

// tableau associatif ( +-= JS Object )
$notes = [
	"Francais"=> 13,
	"SVT"=> 11,
	"EPS"=>12
];
echo $notes["SVT"];

```

[:memo:Introduction détaillée au PHP :fr:](http://aulas.pierre.free.fr/cou_php_base.html)


## PHP / MYSQL - Introduction

Il existe plusieurs manières d'accéder à une base de données, mais le principe/process est souvent le même :
+ on crée une connexion à la base de données
+ on décrit une requête
+ on exécute une requête
+ on récupére le résultat
+ on traite le résultat : génération/affichage de HTML ou renvoi de JSON par exemple

+ **[mysqli  - OC](https://openclassrooms.com/courses/maitrisez-mysqli-sans-poo)**

**Sélection**
```php
<?php
if( $connexion = mysqli_connect('localhost', 'root', 'root', 'blog') ){
	$requete = "SELECT * FROM auteurs";

	$reponses  = mysqli_query($connexion, $requete);

	while( $auteur = mysqli_fetch_assoc($reponses) ){
		echo "<div>".$auteur["nom"]."-".$auteur["mail"]."</div>";
	}
	mysqli_free_result($reponses);
} else {
	echo "erreur BDD !";
}
?>
```
**Insertion**

```php
<?php
if( $connexion = mysqli_connect('localhost', 'root', 'root', 'blog') ){
	$requete = "INSERT INTO auteurs(`id`,`prenom`,`nom`,`mail`) VALUES (NULL, 'Li', 'Wang','liwang@gmail.com')";

	$resultat  = mysqli_query($connexion, $requete);

	echo "resultat : ".($resultat ? 'ok':'false');
} else {
	echo "erreur BDD !";
}
?>
```

+ [PDO - OC](https://openclassrooms.com/courses/concevez-votre-site-web-avec-php-et-mysql/lire-des-donnees-2)

```php
<?php
	try
	{
		$connexion = new PDO('mysql:host=localhost; dbname=blog;charset=utf8', 'root', 'root');
	} catch ( Exception $e ){
		die('Erreur : '.$e->getMessage() );
	}

	$requete = "SELECT * FROM auteurs";
	$resultats = $connexion->query($requete);
	while( $auteur = $resultats->fetch() ){
		echo "<div>".$auteur["nom"]."-".$auteur["mail"]."</div>";
	}
	$resultats->closeCursor();
?>
```


## Annexes

+ Channels
  + <a href="https://www.youtube.com/user/phpacademy" target="_blank">php academy</a>


+ :tv: Grafikart : <a href="https://www.youtube.com/watch?v=bqpXOT5mwW4" target="_blank">REST</a>