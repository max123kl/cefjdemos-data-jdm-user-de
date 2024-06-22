<!-- Filename: How_to_check_if_mod_rewrite_is_enabled_on_your_server / Display title: Prüfen, ob "mod_rewrite" am Server aktiviert ist -->

Viele Probleme entstehen bei der Suchmaschinenoptimierung (SEO), wenn
der Hoster mod_rewrite (Apacheeinstellung) nicht aktiviert. Es wird oft
gesagt, dass aktiviert wurde, tatsächlich stimmt es aber nicht. Man kann
das überprüfen und den Grund für "HTTP-Fehler 500" selbst feststellen.

So erfolgt die Prüfung, ob mod_rewrite aktiviert ist!

**1. SEO im Backend aktivieren:**

Site → Konfiguration → SEO: Suchmaschinen-freundliche URLs auf "Ja".
"Apache mod_rewrite" auf "Ja" ("Dateiendung an URL anfügen" ist
optional).

  
**2. Umbennen der "htaccess.txt" auf ".htaccess":**

NUR diese Zeilen in die .htaccess eingeben:

    RewriteEngine On
    Options +FollowSymLinks
    RewriteRule ^joomla\.html http://www.joomla.org/? [R=303,L]

  
**3. Aufruf mit dem Browser von**
<a href="http://www.example.com/joomla.html" class="external free"
target="_blank"
rel="nofollow noreferrer noopener">http://www.example.com/joomla.html</a>

("www.example.com" mit der eigenen Adresse ersetzen).

Erfolgt die Umleitung auf joomla.org, ist mod_rewrite aktiviert. Erhält
man einen Fehler, ist mod_rewrite nicht aktiviert.

Anmerkung: Befindet sich die Website in einerm Ordner "/test/", muß der
Code in die Wurzel-.htaccess-Datei wie folgt eingefügt werden:

    RewriteEngine On
    Options +FollowSymLinks
    RewriteRule ^test/joomla\.html http://www.joomla.org/? [R=303,L]
