<!-- Filename: Security_Checklist/Hosting_and_Server_Setup / Display title: Sicherheits-Checkliste / Einrichtung von Hosting und Server -->

<table class="navbox" data-cellspacing="0">

<tbody>
<tr class="odd">
<td><table class="nowraplinks navbox-inner" data-cellspacing="0">

<tbody>
<tr class="header">
<th colspan="2" class="navbox-title" scope="col">Security Checklist <img
src="https://docs.joomla.org/images/7/7b/Compat_icon_CMS.png"
decoding="async" data-file-width="87" data-file-height="17" width="87"
height="17" alt="Joomla CMS" /></th>
</tr>
&#10;<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td colspan="2" class="navbox-abovebelow"></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td colspan="2" class="navbox-list navbox-odd"><table
class="nowraplinks navbox-subgroup" data-cellspacing="0">

<tbody>
<tr class="header">
<th colspan="2" class="navbox-title" scope="col"><em>Articles in this
series</em></th>
</tr>
&#10;<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td colspan="2" class="navbox-list navbox-odd"><ul>
<li><a href="https://docs.joomla.org/Security_Checklist/Getting_Started"
title="Special:MyLanguage/Security Checklist/Getting Started">Erste
Schritte</a></li>
<li><a
href="https://docs.joomla.org/Security_Checklist/Hosting_and_Server_Setup"
title="Special:MyLanguage/Security Checklist/Hosting and Server Setup">Einrichtung
von Hosting und Server</a></li>
<li><a href="https://docs.joomla.org/Enabling_HTTPS_on_your_site"
title="Special:MyLanguage/Enabling HTTPS on your site">Aktivierung von
HTTPS für die Webseite</a></li>
<li><a
href="https://docs.joomla.org/Security_Checklist/Where_can_you_learn_more_about_file_permissions%3F"
title="Special:MyLanguage/Security Checklist/Where can you learn more about file permissions?">Mehr
über Dateiberechtigungen</a></li>
<li><a
href="https://docs.joomla.org/Security_Checklist/Testing_and_Development"
title="Special:MyLanguage/Security Checklist/Testing and Development">Tests
und Entwicklung</a></li>
<li><a href="https://docs.joomla.org/Security_Checklist/Joomla!_Setup"
title="Special:MyLanguage/Security Checklist/Joomla! Setup">Einrichtung
von Joomla!</a></li>
<li><a
href="https://docs.joomla.org/Security_Checklisthttps://docs.joomla.org/Security%20Checklist/Site%20Administration">Verwaltung
der Webseite</a></li>
<li><a
href="https://docs.joomla.org/Security_Checklisthttps://docs.joomla.org/Security%20Checklist/Site%20Recovery">Wiederherstellung
der Webseite</a></li>
<li><a
href="https://docs.joomla.org/Security_Checklist/You_have_been_hacked_or_defaced"
title="Special:MyLanguage/Security Checklist/You have been hacked or defaced">Webseite
wurde gehackt oder verändert</a></li>
</ul></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>

## Einen passenden Hosting-Provider auswählen

### Die wichtigste Entscheidung

Die Auswahl von Hosting-Anbietern und Servern ist wahrscheinlich die
wichtigste Entscheidung für die Sicherheit einer Webseite. Aufgrund der
großen Vielfalt an Hosting-Optionen und Konfigurationen ist es jedoch
nicht möglich, eine vollständige Liste für alle Situationen zu
erstellen. Hier ist
**<a href="https://resources.joomla.org/en/category/hosting-providers"
class="external text" target="_blank" rel="noreferrer noopener">eine
Liste von Anbietern</a>**, die die Sicherheitsanforderungen für eine
typische Joomla-Seite erfüllen.
(FAQ

### Risiken von gemeinsam genutzten Servern

Wenn nur ein knappes Budget vorhanden ist und die Webseite keine
hochvertraulichen Daten verarbeitet, ist ein gemeinsam genutzter Server
wahrscheinlich ausreichend. Dennoch sollten die unvermeidlichen Risiken
stets im Blick behalten werden. Die meisten der unten aufgeführten Tipps
eignen sich für die Sicherung von Webseiten in gemeinsam genutzten
Serverumgebungen.

## Die Konfiguration des Apache-Servers

### Die Datei .htaccess verwenden

*Mehr Informationen dazu sind unter  Beispiele für die
.htaccess-Datei
zu finden.*

Typische Exploit-Versuche können mit lokalen .htaccess-Dateien des
Apache-Servers blockiert werden. Diese Option ist aber nicht auf allen
Servern aktiviert. Bei Problemen sollte der Hosting-Provider kontaktiert
werden. Mit .htaccess können sensible Bereiche, wie z. B. das
Administrator-Verzeichnis, mit einem Passwort geschützt und der Zugriff
auf sensible Verzeichnisse nach IP-Adresse eingeschränkt werden. Je nach
Konfiguration des Servers kann die Sicherheit außerdem durch den Wechsel
zu PHP7 erhöht werden.

Joomla enthält bereits eine  vorkonfigurierte
.htaccess-Datei,
aber der Administrator muss entscheiden, ob er diese nutzen möchte. Die
Datei heißt htaccess.txt. Um sie zu aktivieren, muss sie in .htaccess
umbenannt und per FTP in das Root-Verzeichnis der Webseite hochgeladen
werden. Ein wichtiger Punkt ist, dass sowohl die im
Joomla!-Installationspaket enthaltene Datei htaccess.txt als auch die
Live-Datei auf der Website .htaccess heißen, wobei letztere bei einer
Aktualisierung von Joomla! NICHT aktualisiert wird. Die Änderungen
müssen deshalb manuell vorgenommen werden, um die neue Dateiversion zu
verwenden.

Es sollte stets versucht werden, das **"Least Privilege"-Prinzip** für
die Ausführung von PHP mit Werkzeugen wie PHPsuExec, php_suexec oder
suPHP zu befolgen.

*Hinweis*: Dies sind fortgeschrittene Methoden, die eine Vereinbarung
und Koordination mit dem Hosting-Provider erfordern. Solche Optionen
werden serverweit aktiviert oder deaktiviert und sind auf gemeinsam
genutzten Servern nicht individuell einstellbar.

Außerdem sollte die Verwendung einer serverseitigen Filterlösung wie
Apache mod_security in Betracht gezogen werden - ein guter Ausgangspunkt
ist das OWASP ModSecurity
<a href="https://coreruleset.org/" class="external text" target="_blank"
rel="nofollow noreferrer noopener">CoreRuleSet</a>

### PHP als Apache-Modul ausführen

Dies verursacht Probleme mit Zugriffsberechtigungen, die zu
Sicherheitsproblemen führen können. Es ist besser, eine
Servereinstellung oder einen Hosting-Provider zu wählen, die php als
cgi-Prozess (wie etwa cgi-fcgi) zusammen mit phpSuExec oder einer
ähnlichen Konfiguration ausführt.

Die beiden besten Tutorials und Erklärungen zu Berechtigungen,
Eigentümerschaft an Ressourcen und deren Beziehungen sind von dieser
offiziellen Joomla-Doku-Seite:

- Dateiberechtigungen
-  Hinweise zu
  Dateiberechtigungen

Weitere Informationen zu speziellen Themen sind hier zu finden:

-  Wie funktionieren
  Unix-Berechtigungen?

Informationen zu phpSuExec und ähnlichen Anwendungen:

-  Verwendung von
  phpSuExec

### Das Apache-Modul mod_security verwenden

Die Einrichtung der Apache-Filter mod_security und mod_rewrite hilft bei
der Blockierung von PHP-Angriffen. Siehe dazu auch die
<a href="https://www.google.com/search?q=apache%20mod_security"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Google-Suche für mod_security</a> und
die <a href="https://www.google.com/search?q=apache%20mod_rewrite"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Google-Suche für mod_rewrite</a>.

*Hinweis*: Dies sind fortgeschrittene Methoden, die normalerweise eine
Vereinbarung und Koordination mit dem Hosting-Provider erfordern. Solche
Optionen werden serverweit aktiviert oder deaktiviert und sind auf
gemeinsam genutzten Servern nicht individuell einstellbar.

## Konfiguration von MySQL

### Die Datenbank absichern

MySQL-Nutzerkonten sollten mit eingeschränktem Zugriff eingerichtet
werden. Die Erstinstallation von MySQL ist unsicher und die Nutzung der
Datenbank erfordert eine sorgfältige Konfiguration. (Siehe die
<a href="http://dev.mysql.com/doc/" class="external text"
target="_blank" rel="nofollow noreferrer noopener">MySQL-Handbücher</a>)

*Hinweis*: Dieser Punkt gilt nur für diejenigen, die ihre eigenen Server
verwalten, wie z. B. dedizierte Server. Bei gemeinsam genutzten Servern
ist der Hosting-Provider für die Datenbanksicherheit verantwortlich.

## PHP konfigurieren

### Die Funktionsweise von PHP verstehen

Es ist wichtig zu verstehen, wie die php.ini-Datei verwendet und wie
PHP-Konfigurationen gesteuert werden. Dazu können die offizielle Liste
der <a href="http://us3.php.net/manual/en/ini.php#ini.list"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">php.ini-Direktiven</a> unter
<a href="http://www.php.net" class="external free" target="_blank"
rel="nofollow noreferrer noopener">http://www.php.net</a> und die gut
dokumentierte Standard-PHP.ini-Datei, die jeder PHP-Installation
beiliegt, genutzt werden.

### PHP7 verwenden

PHP-Versionen entwickeln sich weiter und einige davon sind veraltet.
Einige Hosting-Provider haben noch mehrere Versionen auf Servern
verfügbar, um veraltete Skripte zu unterstützen. Joomla
<img src="https://docs.joomla.org/images/4/4d/Compat_icon_3_x.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 3.x" /> und neuer sollten PHP7.x verwenden
(siehe die <a href="https://downloads.joomla.org/technical-requirements"
class="external text" target="_blank"
rel="noreferrer noopener">Anforderungen für Joomla!</a>).

### Lokale php.ini-Dateien verwenden

Auf gemeinsam genutzten Servern kann die Hauptdatei php.ini nicht
bearbeitet werden, aber möglicherweise können benutzerdefinierte, lokale
php.ini-Dateien hinzugefügt werden. Wenn das der Fall ist, müssen die
php.ini-Dateien in jedes Unterverzeichnis kopiert werden, das
benutzerdefinierte Einstellungen erfordert.

**Dabei sind einige wichtige Dinge zu beachten.**

1.  Lokale *php.ini*-Dateien haben nur dann eine Wirkung, wenn der
    Server für die Verwendung dieser Dateien konfiguriert ist. Dazu
    gehört eine *php.ini*-Datei im *http_root*-Verzeichnis. Es kann
    getestet werden, ob diese Datei die Webseite beeinflusst. Dazu wird
    eine offensichtliche Direktive in der lokalen php.ini-Datei gesetzt,
    um zu sehen, ob sich das Verhalten der Webseite entsprechend ändert.
2.  Lokale *php.ini*-Dateien wirken sich nur auf *.php*-Dateien aus, die
    sich im selben Verzeichnis befinden (oder von diesen Dateien
    eingeschlossen (*include()*) oder angefordert (*require()*) sind).
    Das bedeutet, dass es normalerweise nur zwei Joomla!-Verzeichnisse
    gibt, in denen eine *php.ini*-Datei platziert werden sollte. Das
    sind das Verzeichnis *http_root* (der tatsächliche Verzeichnisname
    kann ein anderer sein), in dem sich die Joomla! Front-End-Datei
    *index.php* befindet, und das Joomla!-Administrator-Verzeichnis, in
    dem sich die Back-End-Administrator-Datei *index.php* befindet.
    Andere Verzeichnisse, die keine über das Web aufgerufenen Dateien
    haben, benötigen keine lokalen *php.ini*-Dateien.
3.  Wenn in jedem Verzeichnis eine *php.ini*-Datei vorhanden ist, ist
    wahrscheinlich ein Skript dafür verantwortlich. Wenn dies nicht
    beabsichtigt ist, sollten sollten diese Dateien wahrscheinlich
    gelöscht werden.

### PHP disable_functions aktivieren

Mit disable_functions können gefährliche PHP-Funktionen deaktiviert
werden, die von der Webseite nicht benötigt werden. Hier ist ein
typisches Setup für eine Joomla!-Webseite:

         disable_functions = show_source, system, shell_exec, passthru, exec, phpinfo, popen, proc_open

### PHP open_basedir aktivieren (optional)

Unter Umständen *kann* es von Vorteil sein, *open_basedir* zu
aktivieren. Diese Direktive beschränkt die Dateien, die von PHP geöffnet
werden können, auf den angegebenen Verzeichnisbaum. Diese Direktive wird
NICHT davon beeinflusst, ob der abgesicherte Modus (Safe Mode) ein- oder
ausgeschaltet ist.

Die mit open_basedir angegebene Einschränkung ist ein Präfix, kein
Verzeichnisname. Das bedeutet, dass *open_basedir = /dir/incl* den
Zugriff auf */dir/include* und */dir/incls* erlaubt, falls diese
existieren. Um den Zugriff nur auf das angegebene Verzeichnis zu
beschränken, muss es mit einem Schrägstrich abgeschlossen werden.
Weitere Informationen sind unter <a
href="http://us3.php.net/manual/en/features.safe-mode.php#ini.safe-mode"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">PHP-Sicherheits- und
Safe-Mode-Konfigurationsrichtlinien</a> zu finden.

        open_basedir = /home/users/you/public_html

Wenn *open_basedir* gesetzt ist, kann es zusätzlich notwendig sein, die
PHP-Konfigurationsdirektive *upload_tmp_dir* auf einen Pfad zu setzen,
der in den Anwendungsbereich von *open_basedir* fällt, oder alternativ
den Pfad *upload_tmp_dir* zu *open_basedir* unter Verwendung des
entsprechenden Pfad-Trennzeichens für das Host-System hinzuzufügen.

        open_basedir = /home/users/you/public_html:/tmp

PHP verwendet das temporäre Verzeichnis des Systems, wenn
*upload_tmp_dir* nicht gesetzt ist oder wenn es zwar gesetzt ist, das
Verzeichnis aber nicht existiert. Daher kann es notwendig sein, es wie
oben zu *open_basedir* hinzuzufügen, um Fehler beim Hochladen von
Dateien innerhalb von Joomla zu vermeiden.

### PHP magic_quotes_gpc anpassen

**<span class="small">*Diese PHP-Funktion wurde ab PHP 5.3.0
(30.06.2009) als veraltet angesehen und ab PHP 5.4.0 aus PHP
entfernt.*</span>**

Die Direktive *magic_quotes_gpc* kann nach Bedarf für die Webseite
angepasst werden.

- Joomla! 3.0 und höher **erfordert**, dass *magic_quotes_gpc* auf
  **off** gesetzt ist und wird andernfalls nicht installiert.
- Joomla! empfiehlt, *magic_quotes_gpc* auf off zu setzen, wenn Joomla
  2.5.xx verwendet wird.
- Joomla! 1.5 ignoriert die Einstellung und funktioniert in beiden
  Fällen gut. Die sicherste Methode ist, *magic_quotes_gpc*
  auszuschalten und alle schlecht programmierten Erweiterungen zu
  vermeiden.
- Die empfohlene Einstellung für Joomla! 1.0.x ist ON, um vor schlecht
  geschriebenen Erweiterungen von Drittanbietern zu schützen.

Weitere Informationen sind unter  Magic Quotes und
Sicherheit
oder im <a href="http://php.net/magic_quotes" class="external text"
target="_blank" rel="nofollow noreferrer noopener">PHP-Handbuch, Kapitel
31. Magic Quotes</a> zu finden.

    to turn off    magic_quotes_gpc = 0
    to turn on     magic_quotes_gpc = 1

### PHP safe_mode deaktivieren

**<span class="small">*Diese PHP-Funktion wird seit PHP 5.3.0 als
veraltet angesehen und mit PHP 5.4.0 entfernt.*</span>**

Es wird dringend davon abgeraten, sich auf diese Funktion zu verlassen.
Die Verwendung von PHP *safe_mode* sollte vermieden werden. Dies war ein
Versuch, verbreitete Sicherheitsprobleme zu lösen und vermittelt ein
falsches Sicherheitsgefühl. Der *safe_mode* kann auch Eigentumsprobleme
mit Anwendungen und den von den Anwendungen erstellten Dateien
verursachen. Weitere Informationen sind auf der offiziellen PHP-Website
zu finden: <a href="http://php.net/manual/en/features.safe-mode.php"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">PHP-Handbuch: Safe Mode</a>

         safe_mode = 0

### PHP register_globals deaktivieren

**<span class="small">*Diese PHP-Funktion wird seit PHP 5.3.0 als
veraltet angesehen und mit PHP 5.4.0 entfernt.*</span>**

Die automatische Registrierung von globalen Variablen war wahrscheinlich
eine der dümmsten Entscheidungen, die die Entwickler von PHP getroffen
haben. Diese Direktive legt fest, ob die EGPCS-Variablen (Environment,
GET, POST, Cookie, Server) als globale Variablen registriert werden
sollen oder nicht. Durch die Registrierung sind sie sofort für alle
PHP-Skripte verfügbar und können bei unvorsichtiger Programmierung
eigene Variablen leicht überschreiben. Glücklicherweise haben die
PHP-Entwickler den Fehler längst erkannt und diese "Funktion" entfernt.

Wenn die Webseite auf einem gemeinsam genutzten Server liegt und der
Hosting-Provider darauf besteht, dass *register_globals* auf ON gesetzt
sein muss, ist Vorsicht geboten. Obwohl *register_globals* für die
eigene Site mit einer lokalen php.ini-Datei oft abgeschaltet werden
kann, bringt dies nur wenig Sicherheit. Andere Webseiten auf demselben
Server bleiben anfällig für Angriffe, die dann von innerhalb des Servers
Angriffe auf andere Seiten starten können.

Weitere Informationen sind im
<a href="http://php.net/manual/en/security.globals.php"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">PHP-Handbuch: Verwendung von Register
Globals</a> zu finden.

         register_globals = 0

### PHP allow_url_include deaktivieren

PHP allow_url_include sollte nicht verwendet werden. Diese PHP-Option
erlaubt es einem Programmierer, eine entfernte Datei unter Verwendung
einer URL statt eines lokalen Dateipfades einzubinden. Dies ist
unsicher. Wenn eine Anwendung (oder Erweiterung) dazu gebracht werden
kann, Inhalte von einer URL außerhalb ihrer selbst einzubinden, könnte
ein Angreifer die Anwendung (oder Erweiterung) dazu zwingen, Code von
deren Webseite aus auszuführen. Wenn eine Anwendung oder Erweiterung
diese Funktion benötigt, sollte eine Alternative gesucht werden. Die
Notwendigkeit der Nutzung dieser Funktion weist auf schwerwiegende
Designfehler innerhalb der Anwendung oder Erweiterung hin.

### PHP allow_url_fopen aktivieren

Diese Option aktiviert die URL-bezogenen fopen-Wrapper, die den Zugriff
auf URL-Objekt wie auf Dateien ermöglichen. Standardmäßig werden Wrapper
für den Zugriff auf entfernte Dateien über das ftp- oder http-Protokoll
bereitgestellt. Einige Erweiterungen wie zlib können zusätzliche Wrapper
registrieren. Hinweis: Diese Option kann aus Sicherheitsgründen nur in
der php.ini eingestellt werden. **Die Aktivierung und Verwendung von
allow_url_fopen sorgt dafür, dass das Ein-Klick-Update von Joomla
richtig funktioniert.**

Mehr Informationen sind unter <a
href="http://www.php.net/manual/en/filesystem.configuration.php#ini.allow-url-fopen"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">PHP-Handbuch: allow_url_fopen und
allow_url_include</a> zu finden.

       Proper setup will have this:
                    allow_url_fopen = 1
                  allow_url_include = 0

       PHP default: allow_url_fopen is enabled
       PHP default: allow_url_include is disabled

## Dateiberechtigungen

Wenn eine Joomla-Installation auf einem Apache-Server mit mod_php
gehostet wird, dann laufen alle virtuellen Hosts auf diesem Server im
gleichen Kontext wie der Joomla-Code. Wenn die Dateien einem anderen
Benutzer als 'nobody' oder 'wwwrun' gehören, sind die sichersten
Berechtigungen diejenigen, die Änderungen am Joomla-Code verhindern, es
sei denn über einen autorisierten Kanal, z. B. FTP:

- Stammverzeichnis der Dateien: 750 (z. B. public_html)
- Dateien: 644
- Verzeichnisse: 755 (711, wenn man auf Nummer sicher gehen will, aber
  nicht für Verzeichnisse, die aufgelistet werden müssen) (Besitzer:
  irgendein Benutzer)

Wenn diese Berechtigungen gesetzt sind, muss FTP verwendet werden, um
eine Joomla-Installation zu aktualisieren. Nicht alle Module
unterstützen dies. Module, die FTP-Upgrades nicht unterstützen, sollten
entfernt werden...

Andere Prozesse, die unter mod_php laufen, können die configuration.php
der Webseite lesen. Automatisierte Hacks können verhindert werden, indem
diese Datei umbenannt wird. FTP-Passwörter sollten auf solchen Hosts
nicht in der Konfigurationsdatei gespeichert werden, da der Zugang
dadurch kompromittiert wird.

Wenn eine Joomla-Installation auf Apache mit fast-cgi, suphp oder cgi
gehostet wird, die als anderer Benutzer läuft, sollten die
Berechtigungen wie folgt eingestellt werden:

- Stammverzeichnis der Dateien: 750 (z. B. public_html)
- PHP-Dateien: 600 (400, wenn man auf Nummer sicher gehen will)
- HTML- und Bilddateien: 644 (444, wenn man auf Nummer sicher gehen
  will)
- Verzeichnisse: 755 (711, um auf Nummer sicher zu gehen, aber nicht für
  Verzeichnisse, die aufgelistet werden müssen)

Wenn der verwendete Server 777-Berechtigungen benötigt, damit Joomla
korrekt funktioniert, dann sollte darauf bestanden werden, dass die
Seite auf einen anderen Server mit php als cgi und suphp und aktueller
serverseitiger Software (apache, php usw.) auf Ihrem bestehenden Host
umgezogen wird. Falls nötig sollte ein anderer Hosting-Provider gesucht
werden.

Es ist wichtig zu wissen, ob der Hosting-Provider den Server, auf dem
die Webseite liegt, angemessen gesichert hat. Der Provider oder der
Webseiten-Admin sollten regelmäßige (wöchentliche) Sicherheitsupdates
durchführen, um den Server auf dem neuesten Stand zu halten. Es sollte
auch überprüft werden, ob eine *jail shell* vorhanden ist. Als
Faustregel gilt: Je geringer der Preis für das Hosting, desto weniger
Service kann erwartet werden.

Weitere Informationen über Dateiberechtigungen sind hier zu finden:
Datei-Berechtigungen

## Einen Sicherungs- und Wiederherstellungsprozess einrichten

### Die wichtigste Regel

Es sollte jederzeit möglich sein, eine Webseite durch regelmäßige
Verwendung eines leistungsfähigen, externen Backup- und
Wiederherstellungsprozesses wieder in einen früheren Betriebszustand zu
versetzen. Der Backup- und Wiederherstellungsprozess sollte vorhanden
und getestet sein, BEVOR die Webseite live geht. Dies ist der beste Weg
(und oft der einzige), um sich vor unvermeidlichen Katastrophen zu
schützen, wie z. B:

1.  Defekte Webseite aufgrund eines fehlerhaften Upgrades
2.  Hardware-Ausfall, wie z. B. tote Festplatten, Stromausfälle,
    Server-Diebstahl, etc.
3.  Intervention einer Regierungsbehörde. (häufiger als oft vermutet)
4.  NeDie Notwendigkeit, schnell zu einem neuen Server oder
    Hosting-Provider umzuziehen.

Backups werden nicht für die Wiederherstellung einer
kompromittierten/gehackten Website empfohlen, da die Backups die
geänderten und gehackten Dateien bereits enthalten könnten. Die
Verwendung der Backups zur Wiederherstellung einer gehackten Site würde
dann nur den Hack auf der Webseite wieder einspielen.
