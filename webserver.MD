# XAMPP

## Vairākas PHP versijas

Katrai php versijai izveidot savu mapi iekš htdocs.

1. Ņemt x64 bitu, Non-Thread Safe versijas. https://windows.php.net/downloads/releases/archives/

2. Izkomentēt rindu no httpd-xampp.conf
``#SetEnv PHPRC "\\xampp\\php" ``

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
5. Iekš php.ini noņemt komentu no ``extension_dir = "ext"`` rindas.