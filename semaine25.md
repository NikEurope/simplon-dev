# Semaine 25

## Symfony

```
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteBase /symfony_demo
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^(.*)$ web [QSA,L]
</IfModule>
```

