# remove-public-url-laravel
how to remove laravel 7+ public url 

Create a file named as '.htaccess' in root and add the below code. That's it


RewriteEngine On

RewriteCond %{REQUEST_FILENAME} -d [OR]
RewriteCond %{REQUEST_FILENAME} -f
RewriteRule ^ ^$1 [N]

RewriteCond %{REQUEST_URI} (\.\w+$) [NC]
RewriteRule ^(.*)$ public/$1 

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ server.php
