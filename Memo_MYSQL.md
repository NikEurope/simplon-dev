# MYSQL

### [Base de données relationnelle](https://fr.wikipedia.org/wiki/Base_de_données_relationnelle)

![exemple table](http://i.stack.imgur.com/ruxKF.png)

```bash
sudo apt-get install mysql-server php5-mysql
sudo mysql_install_db
sudo mysql_secure_installation
mysql -u root -p
```

#### Création / destruction de bases de données et de tables

```sql
SHOW DATABASES;
CREATE DATABASE test;
SHOW DATABASES;
DROP DATABASE test;
SHOW DATABASES;

CREATE DATABASE blog;

USE blog

SHOW TABLES;
CREATE TABLE auteurs( id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
prenom VARCHAR(30),
nom VARCHAR(30),
mail VARCHAR(40)
);

DESCRIBE auteurs
```

[:memo:Types de colonnes MYSQL court](http://buzut.fr/2012/05/08/les-differents-types-de-colonnes-mysql/)
[:book:Types de colonnes MYSQL détaillé - OC](https://openclassrooms.com/courses/choisir-les-bons-types-de-colonne-sql)

#### Insertion
```sql
INSERT INTO auteurs (`id`, `prenom`, `nom`, `mail`) VALUES (NULL, 'Carl', 'Marques', 'carl.m@gmail.com' );
INSERT INTO auteurs (`id`, `prenom`, `nom`, `mail`) VALUES (NULL, 'Lea', 'Léger', 'leam@gmail.com' );
```

#### Sélection
```sql
SELECT `id`,`prenom`, `nom`, `mail`  FROM auteurs ;
SELECT `id`,`prenom`, `nom`, `mail  FROM auteurs WHERE `prenom`="lea";
```
#### modification
```sql
UPDATE auteurs SET `prenom`="Karl" WHERE `id`=1;
```

#### suppression
```sql
DELETE FROM `auteurs` WHERE id=1;
```

[:memo:Introduction détaillée à MYSQL :fr:](http://aulas.pierre.free.fr/cou_sql_syntaxe.html)

#### Exploration : Créez une/des bases de données, des tables... pays, villes, journal, resultats sportifs

### PHPMyAdmin

```bash
sudo apt-get install phpmyadmin
```

Après installation : <a href="http://localhost/phpmyadmin" target="_blank">ouvrir phpmyadmin</a>

Si dossier non trouvé et qu'aucun *lien* vers phpmyadmin n'existe ds /var/www/html/':

```bash
sudo ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin

sudo service apache2 restart
```

[Guide d'installation](https://doc.ubuntu-fr.org/phpmyadmin)
