# Semaine 15

## Objectifs
+ MySQL : conception de base de données
+ PHP POO

## J1

:fire: **Tuto SQL**
+ [SQL tutorial - Part 1 : basics :us:](http://net.tutsplus.com/tutorials/other/sql-for-beginners/)
+ [SQL tutorial - Part 2 : index, requêtes avancées, datatypes :us:](http://code.tutsplus.com/tutorials/sql-for-beginners-part-2--net-8274)

### Conception de Bases de données relationnelles

#### [Principes de base de la normalisation des bases de données](https://support.microsoft.com/fr-fr/kb/283878)
[Intro normalisation 2](http://www.phpro.org/tutorials/Introduction-To-Database-Normalization.html#5)

- 1ère forme normale
  + éliminer les répétitions
  + créer une table pour chaque entité distincte
  + définir un chp d'identification unique pour chaque table ( clé primaire )

- 2nde forme normale
  + des tables pour chaque jeu de données pouvant être utilisés à plusieurs reprises
  + créer une clé étrangère entre les tables dépendantes

### Relations entre objets
- one to one : 1 utilisateur a un mail/password
- one to many : 1 utilisateur est propriétaire de plusieurs tâches
- many to many : plusieurs utilisateurs peuvent être proprio de plusieurs tâches

+ [Clés primaire et étrangères - OC :fr:](https://openclassrooms.com/courses/administrez-vos-bases-de-donnees-avec-mysql/cles-primaires-et-etrangeres)
+ [SQL tutorial - Part 3 : Database relationships :us:](http://code.tutsplus.com/tutorials/sql-for-beginners-part-2--net-8274)

**Exemple Todo app**

+ tâches ( task ) : id, titre, etat, description, date_creation, date_completion,...

Est ce que tout le monde peut voir / editer la tâche ? A qui appartient elle ?

+ users : id, mail, nom, password, date_inscription, last_visit

  + si une tâche ne peut appartenir qu'à un user : on pourrait éventuellement ajouter une colonne user_id
  + si on veut prévoir l'éventualité de plusieurs users par tâches » une table de liaison user_task{id_user, id_task}

**Plus loin**

+ projets / catégories / tags / fichiers liés...


## J2

### Relations entre les tables

+ Clés étrangères » InnoDB / MyISAM

[différences MyISAM / InnoDB](http://www.tux-planet.fr/mysql-les-principales-differences-entre-myisam-et-innodb/)

```sql
CREATE TABLE `users_tasks` (
  `id_user` int(11) NOT NULL,
  `id_task` int(11) NOT NULL,
  FOREIGN KEY (`id_user`) REFERENCES `users` (`id_user`),
  FOREIGN KEY (`id_task`) REFERENCES `tasks` (`id_task`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

Il est tout à fait recommandé [d'indexer](http://sql.sh/cours/index) les colonnes liées aux clés étrangères ( KEY est synonyme de INDEX )

```sql
CREATE TABLE `users_tasks` (
  `id_user` int(11) NOT NULL,
  `id_task` int(11) NOT NULL,
  KEY (`id_task`),
  INDEX  (`id_user`),
  FOREIGN KEY (`id_user`) REFERENCES `users` (`id_user`),
  FOREIGN KEY (`id_task`) REFERENCES `tasks` (`id_task`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

**Contraintes : Régles automatisées**

Les clés étrangères ( foreign keys ) permettent également de définir des options de suppressions et/ou de mise à jour.
Pour faire simple, on peut définir que la suppression de l'entité d'une clé étrangère peut provoquer
la suppression des éléments liés.
Exemple : si on supprime le compte de bob@gmail.com, cela supprime automatiquement
les liaisons de la table users_tasks

```sql
CREATE TABLE `users_tasks` (
  `id_user` int(11) NOT NULL,
  `id_task` int(11) NOT NULL,
  KEY `ud_task_fk` (`id_task`),
  KEY `users_fk` (`id_user`),
  CONSTRAINT `users_fk` FOREIGN KEY (`id_user`) REFERENCES `users` (`id_user`) ON DELETE CASCADE,
  CONSTRAINT `ud_task_fk` FOREIGN KEY (`id_task`) REFERENCES `tasks` (`id_task`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci
```

Alors concrètement comment ça marche ?!

+ Bob crée une tâche dans la table *tasks*
+ on ajoute une correspondance dans la table users_tasks entre l'id de Bob et l'id de la tâche créée

Pour cela, il est possible de récupérer facilement le dernier id inséré +
+ En SQL : `LAST_INSERT_ID()`,
+ en php, via mysqli : `mysqli_insert_id()` ( ou `mysqli->insert_id`)
+ en php, via PDO : `$db->lastInsertId()`

```php
<?php

$titre = 'Acheter piles';

try
{
    $db = new PDO('mysql:host=localhost; dbname=labz;charset=utf8', 'root', 'root');
} catch ( Exception $e ){
    die('Erreur : '.$e->getMessage() );
}

$requete = "INSERT INTO tasks (`titre`,`date_creation`,`etat` ) VALUES (:titre, NOW(), 0)";
$q = $db->prepare( $requete );
$q->bindParam(":titre", $titre, PDO::PARAM_STR);
$resultats = $q->execute();

if( $resultats ){
    $userId = 1 /* $_SESSION[ 'userId' ]*/;
    $taskId = $db->lastInsertId();
    $q2 = $db->prepare( "INSERT INTO users_tasks(id_user, id_task) VALUES (:userId, :taskId) " );
    $q2->bindParam(":userId", $userId, PDO::PARAM_INT);
    $q2->bindParam(":taskId", $taskId, PDO::PARAM_INT);
    $res_link = $q2->execute();
}

echo $res_link ? "ok" : "error";

?>
```

#### Jointures

Pour effectuer une sélection de données de plusieurs tables, on peut utiliser des jointures.

![jointures](assets/jointure-sql.jpg)

Exemples :

Soit 3 tables :
- users { id_user, mail, password }
- tasks { id_task, titre, etat, date_creation }
- users_tasks { id_user, id_task }

```sql
SELECT mail FROM users
JOIN users_tasks USING(id_user)
WHERE id_task = 1
```
ou
```sql
SELECT mail FROM users
JOIN users_tasks ON users.id_user = users_tasks.id_user
WHERE id_task = 1
```

[Jointures - OC](https://openclassrooms.com/courses/administrez-vos-bases-de-donnees-avec-mysql/jointures-1)
[Jointures SQL](http://sql.sh/cours/jointures)

#### Extras : fonctions SQL

+ ORDER BY
+ LIMIT
+ GROUP BY

+ COUNT(*)

+ IN()
+ LIKE
+ MIN(), MAX(), AVG(), SUM()
+ ...


#### PHP POO

Les bases de données permettent de stocker des jeux de données, représentant des entités / objets.
Ne serait-il pas pratique de pouvoir utiliser le même genre d'objet en PHP ?

Malheureusement, PHP ne connait ni nos *tasks* ni nos *users*... :sad:
Pour pallier à cette ignorance, nous avons la possibilité de déclarer nos propres types d'objets.

Pour ce faire nous allons créer/"déclarer" des *classes* : des définitions de types d'objets
que notre application manipule/utilise.

Plutôt que de manipuler des objets "indéfinis", des tableaux aux propriétés infinies,

type `array("id"->1, "titre"->"acheter du pain")`,

nous pourrions manipuler des entités aux caractéristiques "strictement connues",
choisies par nos soins pour répondre à nos besoins :
des tâches définies par : un id, un titre, une date, un état. NI PLUS NI MOINS!

exemple : `$task->titre`

```php
<?php
class Task{

    var $id;
    var $title;
    var $date_creation;
    var $completed;
}

$tache1 = new Task();
$tache1->title = 'test';
$tache1->date_creation = new DateTime();
$tache1->completed = true;

print_r( $tache1);
?>
```

Cette classe nous permet de déclarer l'existence, au sein des scripts PHP,
d'un type d'objet Task, défini par un id, un titre, une date de création et un état ( completé ou pas).

```php

<?php
class Task{

	public $id;
	public $title;
	public $date_creation;
	public $completed;

	function __construct($id, $title, $date, $completed) {
		$this->id = $id;
		$this->title = $title;
		$this->date_creation = $date;
		$this->completed = $completed;
	}

	function __toString ()
	{
		return "Tâche : [$this->id] $this->title ";
	}
}

$uneTache = new Task( 1, 'acheter du pain', new DateTime(), true );

echo $uneTache;

?>
```

## J3

+ correction défi Simpllo / Portfolio

## J4

![cooode](https://media0.giphy.com/media/hJ2BmdBT1IF7q/200.gif)

[:tv: PHP POO - Grafikart](https://www.grafikart.fr/formations/programmation-objet-php)
π
[:book: PHP POO - OC](https://openclassrooms.com/courses/programmez-en-oriente-objet-en-php)

:question: (Guide Gandi - Simple Hosting)[https://wiki.gandi.net/fr/simple]

[:tv: PHPStorm tutos](https://www.youtube.com/playlist?list=PLQ176FUIyIUbfeFz-2EbDzwExRlD0Bc-w)

[:tv: PHP Storm - Deployment & Remote Host](https://www.youtube.com/watch?v=AHK20LWEWXQ)

[Ma veille sur Twitter](https://twitter.com/rxlabz/following)

![break](https://media0.giphy.com/media/3Q2hJ4FLN1UvS/200.gif)


## Annexes

+ **Hébergement Gandi Simple Hosting et cache**
Par défaut Gandi Simple Hosting utilise un cache (cf.[Varnish](https://fr.wikipedia.org/wiki/Varnish)) » les changements apportés mettent
qlq minutes à être pris en compte.
Pour "annuler" ce cache : Créez un fichier *.htaccess* à la racine du dossier du site ( à côté de index)
et collez `Header add Cache-Control "max-age=1"` dedans.

[cf. Cache automatique sur Simple Hosting](https://wiki.gandi.net/fr/simple/cache)

+ Web documentaires

[Webdocumentaires, webreportages et webfictions d’Arte](http://www.arte.tv/sites/webdocs/)

[Exemples de webdoc](http://www.blogduwebdesign.com/web-documentaires/les-web-documentaires-10-exemples-de-qualite-a-decouvrir/898)
