# How-to-solve-forbidden-error-for-post-pages
How to solve forbidden error for post pages 


first  open terminal
following run command 

Enabling mod_rewrite

```
sudo a2enmod rewrite
```

This will activate the module or alert you that the module is already enabled. To put these changes into effect, restart Apache.

```
sudo systemctl restart apache2 
```

then 

```
sudo nano /etc/apache2/apache2.conf  
```


# access here, or in any related virtual host.

```sh
<Directory />
        Options FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>

<Directory /usr/share>
        AllowOverride None
        Require all granted
</Directory>

<Directory /var/www/html>
        Options Indexes FollowSymLinks
        AllowOverride all
        Require all granted
</Directory>

#<Directory /srv/>
```


# viewed by Web clients.

```sh
<FilesMatch "^\.ht">
        Require all granted
</FilesMatch>
#
```


Now save  click ctrl+o then enter ctrl+x and enter 

```
sudo systemctl restart apache2 
````
and refresh your page 
