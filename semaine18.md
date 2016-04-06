# Semaine 18

## J1

+ Entretiens individuels

+ Exploration PHP :
  + Espace de noms
  + Traits
  + [Slim](http://www.slimframework.com), [Lumen](https://lumen.laravel.com), [Silex](http://silex.sensiolabs.org)
  + [Composer](https://getcomposer.org)


## Silex

+ [Introduction à Silex](https://openclassrooms.com/courses/premiers-pas-avec-le-framework-php-silex)
+ [Evoluer vers une architecture PHP professionnelle](https://openclassrooms.com/courses/evoluez-vers-une-architecture-php-professionnelle)

+ Exploration JS :
  + ES2015 / ES6
    + [les classes](http://putaindecode.io/fr/articles/js/es2015/classes/)
    + [var, let et const](http://putaindecode.io/fr/articles/js/es2015/const-let-var/)
    + [les fonctions fléchées](http://putaindecode.io/fr/articles/js/es2015/arrow-functions/)
    + [string templates](http://putaindecode.io/fr/articles/js/es2015/template-strings/)
π
  + [React](https://facebook.github.io/react/)

# J2

## PHP : Autoload

[Exemple](https://github.com/Simplon-lyon/dev-web/tree/master/php/autoload)

## PHP : Namespaces / Espaces de noms

Les namespaces permettent d'organiser ses classes ( et aussi fonctions et constantes depuis PHP 5.6 ) en packages.
[Exemple](https://github.com/Simplon-lyon/dev-web/tree/master/php/nspaces)

## [Composer](https://getcomposer.org/doc/00-intro.md)

Composer est un gestionnaire de packages/librairies pour PHP.

#### [Installation ](https://getcomposer.org/download/)

```bash
php -r "readfile('https://getcomposer.org/installer');" > composer-setup.php
sudo php composer-setup.php --install-dir=/usr/local/bin/composer
```

#### [Utilisation](https://getcomposer.org/doc/01-basic-usage.md)

+ **composer.json** : permet de décrire les dépendances d'un projet

```json
{
  "require":{
    "monolog/monolog":"1.0.*"
  }
}
```

+ composer install : installe les dépendances
```bash
composer install
```
+ composer update

```json
{
  "require":{
    "monolog/monolog":"1.17.*"
  }
}
```

+ composer require

+ [packagist](https://packagist.org)

+ composer autoload

exemple : autoload des classes trouvées ds `src/`
```json
{
"require":{},
"autoload": { "psr-4": { "App\\": "src/"} }
}
```
» nécessite de regénérer les classes d'autoload

```bash
composer dump-autoload
```

## J3

#### Création d'un virtual host

+ création d'un dossier pour nouveau projet et ajout d'un lien symbolique `ln -s` dans /var/www/
```bash
cd ~/sites
mkdir mon-projet
ln -s ~/sites/mon-projet /var/www/mon-projet
```

+ Définition d'une redirection locale du domaine mon-projet.com dans /etc/hosts
```bash
sudo vim /etc/hosts
```
  + Ajouter 1 ligne : `127.0.0.1 mon-projet.com`

+ créer un fichier de configuration pour le vhost
```bash
cd /etc/apache2/sites-available
sudo touch monprojet.conf
sudo vim monprojet.conf
```
+ ajouter le fichier de conf vhost à apache
```bash
sudo a2ensite monprojet.conf
```


```
# monprojet.conf
<Virtualhost :*>
ServerAdmin serveradmin@bbgi.com
    DocumentRoot /home/drupal_1
    ServerName mysite.com
    ServerAlias www.mysite.com
	<Directory /var/www/monprojet>

		Options Indexes FollowSymLinks
		AllowOverride All
		Require all granted
	</Directory>
</Virtualhost>
```

+ Redémarrer apache
```bash
sudo service apache2 reload
sudo service apache2 restart
```

+ .htaccess
```
<IfModule mod_rewrite.c>
    Options -MultiViews

    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.php [QSA,L]
</IfModule>
```


Pour autoriser la ré-écriture depuis le .htaccess
```bash
sudo a2enmod rewrite
```

» var/apache2/sites-availables » AllowOverride All

+ web/index.php

**[Silex](http://silex.sensiolabs.org)**

- installation

```bash
composer require silex/silex
```


#### Routes & actions

  $app->get('/',function(){
  	// retourne la réponse
  });


- views / twig templates
  + [Twig](http://twig.sensiolabs.org/)
  + views
- routes
  + post('/',...)

- [Sessions](http://silex.sensiolabs.org/doc/providers/session.html)

# Annexes
**Apache**
+ [:tv: Installer serveur LAMP](https://www.grafikart.fr/formations/serveur-linux)
+ [https://serversforhackers.com/series](https://serversforhackers.com/series)
+ [Intro Apache](https://doc.ubuntu-fr.org/projets/ecole/apache)
+ [Apache 2 Ubuntu](https://doc.ubuntu-fr.org/apache2)
+ [VirtualHost avec apache2 / ubuntu](https://doc.ubuntu-fr.org/tutoriel/virtualhosts_avec_apache2)
+ [Gestion de permissions](http://cyberzoide.developpez.com/unix/droits.php3)

+ [Ubuntu CentOS Debian](http://inthebox.webmin.com/choosing-a-linux-distribution-for-web-server)

+ [Boilerplate Silex/Bootstrap](https://github.com/aptoma/silex-bootstrap)


+ [Composer presentation](http://fr.slideshare.net/jasongr/composer-23263197)
+ [.htaccess](http://wiki.apache.org/httpd/Htaccess)

+ **[Doctrine](http://docs.doctrine-project.org/en/latest/)**

+ [Blog Simplon Boulogne](http://boulogne.simplon.co/blog/)
+ [Stratégie web et communication digitale / Simplon boulogne](http://boulogne.simplon.co/wp-content/uploads/2016/01/Stratégie-web-et-communication-digitale.pdf)

+ [Conférences Blendmix Lyon 2015](https://www.youtube.com/channel/UCVA4ZOoyUyLB_LS6flBjhRg/videos)
  + [Deepdive es6/es2015 :fr:](https://www.youtube.com/watch?v=uL9uAAzkFmI)
  + [demo es6](https://www.youtube.com/watch?v=YQreLTgIJ7o)