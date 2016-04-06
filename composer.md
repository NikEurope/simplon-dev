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