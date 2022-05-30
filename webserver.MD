# XAMPP

## Vairākas PHP versijas  

Katrai php versijai izveidot savu mapi iekš htdocs.

1. Ņemt x64 bitu, Non-Thread Safe versijas. [https://windows.php.net/downloads/releases/archives/](https://windows.php.net/downloads/releases/archives/) 

2. Izkomentēt rindu no httpd-xampp.conf
`SetEnv PHPRC "\\xampp\\php"`

3. Par katru versiju pielikt konfigurāciju httpd-xampp.conf faila apakšā.

```
ScriptAlias /php5640 "C:/xampp/php5640"
Action application/x-httpd-php5640-cgi /php5640/php-cgi.exe
<Directory "C:/xampp/php5640">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
        Require all granted
    </Files>
</Directory>

<Directory "C:\xampp\htdocs\env5640">
    <FilesMatch "\.php$">
        SetHandler application/x-httpd-php5640-cgi
    </FilesMatch>
</Directory>
```

4. Katrai PHP versijai ir jāizveido php.ini konfigurācijas fails no php.ini-development vai no php.ini-production
5. Iekš php.ini noņemt komentu no `extension_dir = "ext"` rindas.

## Virtual-hosts piemērs iekš httpd-vhosts.conf

PHP 7-8
```
<VirtualHost *:80>
    ServerAdmin admin@web.larzs.lv
    DocumentRoot "C:\xampp\htdocs\env8012\web"
    ServerName web.larzs.lv
    ErrorLog "logs/web.larzs.lv-error.log"
    CustomLog "logs/web.larzs.lv-access.log" common
    <Directory "C:\xampp\htdocs\env8012\web>
        Options -Indexes
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

## MySQL failu korupcijas post fix

* Stop the XAMPP server, MySQL and Apache
* Create a backup of the “/xampp/mysql/data” folder using a compression software
* Rename the “/xampp/mysql/data” folder to “/xampp/mysql/data-old”
* Create a new folder and name it “/xampp/mysql/data”
* Copy all folders from the “/xampp/mysql/backup” and paste it to the “/xampp/mysql/data” folder, which you have just created
* Copy all the databases from the “/xampp/mysql/data-old” folder and paste it to the “/xampp/mysql/data” folder
* Finally copy the “ibdata1” and all of the log files including “ib_logfile0, ib_logfile1 ” from “/xampp/mysql/data-old” and paste it to the “/xampp/mysql/data” folder
* Start MySQL from the XAMPP control panel
* Go to phpMyAdmin to check if all the databases are available and running properly

