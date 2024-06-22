<!-- Filename: How_do_you_block_directory_scans_using_htaccess%3F / Display title: Ordnerscans mit htaccess blockieren -->

**Anweisungen**

Umschreiberegeln von Apache der `.htaccess`-Datei hinzufügen. Beispiel:
Weiterleitung aller Zugriffsversuche auf Dateien, deren Namen mit
"phpMyAdmin" beginnt, auf `index.php` um.

  
**Beispiel der Apache-Umschreiberegel**

    RewriteRule ^/phpMyAdmin.*$ /index.php

  
**Einige Tipps zu Regulären Ausdrücken**

    ^ Bedeutet Beginn des Dateinamens
    . Bedeutet jeder Buchstabe außer Zeilenvorschub
    * Bedeutet einer oder mehr des vorhergehenden Buchstabens
    $ Bedeutet Ende der Zeile
