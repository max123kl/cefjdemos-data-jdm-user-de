<!-- Filename: Copying_a_Joomla_website / Display title: Eine Joomla!-Website kopieren -->

<span id="main-portal-heading">Tutorial  
Eine Joomla!-Website kopieren</span>

  
Eine Joomla!-Website zu kopieren erfolgt in zwei Schritten: Die Dateien
kopieren, die Datenbank kopieren (hier ist der Inhalt gespeichert).
Beides sind separate Schritte. Welche Schritt zuerst durchgeführt wird,
macht keinen Unterschied. Wird die Website häufig aktualisiert und muß
sie für die Kopie offline geschalten werden, die Datenbankkopie zuletzt
erstellen, um die Offlinezeit zu minimieren.

## Website kopieren (häufige Methoden)

#### Akeeba

- Akeeba-Backup erstellt eine .jpa-Datei
- Die .jpa Datei enthält alle Ordner/Dateien und Datenbank-Dateien.
- Die .jpa-Datei enthält auch ein Installationsprogramm
- Kickstart.php (von Akeeba) entpackt die .jpa-Datei
- Mit dem Installer die Site wie eine Joomla!-Installation installieren
- Der Installer ändert die Konfiguration für das Wiederherstellen an
  anderer Stelle und fragt die neuen Datenbankdetails ab.

Nach Erstellen der Datenbank für Joomla! Akeeba von <a
href="https://extensions.joomla.org/extensions/extension/access-a-security/site-security/akeeba-backup/"
class="external text" target="_blank" rel="noreferrer noopener">Joomla
extension directory</a> laden und installieren. Ein Link mit einer
umfangreichen Anleitung ist ebenfalls dort.

### Dateien mit FTP kopieren

Eine Möglichkeit, Dateien einer Joomla!-Installation zu einer anderen zu
kopieren ist die Nutzung eines FTP-Programmes am Desktop. Dafür werden
zuerst die zur Installation gehördenden Dateien vom Webserver geladen,
um sie dann in die neue Joomla!-Installation zu laden. Die neue
Installation kann ein anderer Ordner desselben Webservers oder ein neuer
Ordner eines anderen Webservers sein.

Beim Verschieben müssen Ordner und Dateien in derselben Struktur
erhalten bleiben. FTP-Programme erledigen das automatisch, da sie Sätze
an Ordner und Dateien verwenden (die benutzte FTP-Software verfügt meist
über Hilfedokumentation, die FTP und Benutzung der Software erklärt).
Nach dem Verschieben müssen meist die Joomla!-Konfigurationsdateien und
Einstellung des Webservers angepasst werden, damit die Website läuft.

Selten kommt die Beschädigung einer Datei während des FTP-Transfers vor,
indem nur ein Dateiteil erfolgreich übermittelt wird. Treten in der
neuen Joomla!-Installation merkwürdige und unerwartete Fehler auf, kann
das erneute Hinaufladen aller Dateien helfen.

#### Dateien vom Server auf den Computer laden

1.  Die FTP-Software (z.B. FileZilla) mit dem Webserver verbinden
2.  Den Ordner wählen, der geladen werden soll (meist " /public_html/"
    oder "/htdocs/")
3.  Dateien/Ordner auswählen oder per Ziehen + Ablegen die Ordner von
    "Remote Site" auf "Local Site" kopieren.
4.  Das Laden der entfernten Dateien beginnt
5.  Anschließend auf fehlerhafte Übertragungen prüfen

#### Dateien vom Computer auf den Server laden

1.  Prüfen, ob die "configuration.php" die korrekten Einstellungen für
    den Server hat (besonders: localhost, database, database user,
    database password, log_path, tmp_path)
2.  Die FTP-Software (z.B. FileZilla) mit dem Webserver verbinden
3.  Den Ordner wählen, in den geladen werden soll (meist "
    /public_html/" oder "/htdocs/")
4.  Dateien/Ordner auswählen oder per Ziehen + Ablegen die Ordner von
    "Local Site" auf "Remote Site" kopieren.
5.  Das Laden der lokalen Dateien auf den entfernten Server beginnt
6.  Anschließend auf fehlerhafte Übertragungen prüfen

### Kopieren der Datenbank mit phpMyAdmin

phpMyAdmin kann für Ex- und Import einer Datenbank benutzt werden, indem
einfach eine Kopie mit anderem Namen am Server erstellt wird.

#### Export der Datenbankkopie auf den Computer

1.  In phpMyAdmin an der Datenbank anmelden, die kopiert wird
2.  An der linken Seite auf den Datenbanknamen klicken
3.  "Export"-Tab wählen
4.  "Sichern als"-Option wählen
5.  "OK" klicken

Nach einer Abfrage wird die Datenbankdatei am Computer gespeichert.

#### Import der Kopie in eine neue Datenbank

Zuerst eine neue, leere Datenbank mit der Software des Providers am
Server erstellen. Sie muß UTF8 (utf8_general_ci) sein. Nachdem die
Datenbank erstellt ist:

1.  In phpMyAdmin an der neuen Datenbank anmelden
2.  An der linken Seite auf den Datenbanknamen klicken
3.  "Import"-Tab wählen
4.  In "Zu importierende Datei:" den "Durchsuchen..."-Button klicken und
    am Computer die Datenbankdatei wählen
5.  Import der Datenbank durch Klick auf "OK"

**Tipp:** Wird der Fehler "Keine Datanbank gewählt" gezeigt, wurde meist
vergessen, vorher auf der linken Seite den Datenbanknamen anzuklicken.

### Ändern der Configuration.php

Damit Joomla am neuen Webserver arbeiten kann, müssen dessen
Einstellungen in der configuration.php eingetragen werden. Dies muß
geprüft/geändert werden:

       var $host = 'localhost'; // usually "localhost". If it's different for your server then your hosting provider should be able to tell you that.
        var $user = 'the_db_username';
        var $db = 'the_databasename';
        var $password = 'the_db_password';
            var $live_site = ''; // is usually empty.
            var $cookie_domain = ''; // Should be empty.

Joomla arbeitet, auch wenn \$log_path und \$tmp_path falsch sind, es
können jedoch keine Erweiterungen installiert werden. Im Backend der
neuen Joomla!-Site anmelden.

Pfad: System \> Systeminformationen \> Verzeichnisrechte.  
Die letzen 4 Zeilen prüfen:

    cache (Cache Directory) Writable
    administrator/cache (Cache Directory)  Writable
    /var/www/some/other/folder/example.com/logs/ (Log directory) Unwritable
    /var/www/some/other/folder/example.com/tmp (Temp directory)  Unwritable

Sind `$log_path` und `$tmp_path` "Schreibgeschützt", müssen die Werte in
`configuration.php` geändert werden.

Den Wert von "Cache Directory" ohne den "/cache/"-Teil verwenden. Ändern
von `$log_path` und `$tmp_path` auf

       var $log_path = '/var/www/example.com/logs';
       var $tmp_path = '/var/www/example.com/tmp';

Zeigen die Verzeichnisrechte `$log_path` und `$tmp_path` als
"Beschreibbar", können Erweiterungen installiert werden.

## Kopieren der Website mit der SSH-Kommandozeile (Methode für erfahrene Benutzer)

### Kopieren der Dateien mit komprimierter Archivdatei

Mit FTP eine große Anzahl an Dateien zu kopieren kann unsicher sein. Hat
man bei Quell- und Zielsystem Zugang mit der Kommandozeile, kann man
eine komprimierte Archivdatei aller Dateien des Quellsystems erstellen
und diese Datei auf das Zielsystem transferieren, wo sie dekomprimiert
wird.

#### Archivdatei erstellen

In Unix-ähnlichen Systemen (z.B. Linux) kann das **gzip**-Programm für
.zip-Dateien oder das **tar**-Programm für .tar.gz oder .tar.bz2-Dateien
benutzt werden. Für Details in der Kommandozeile **man gzip** oder **man
tar** eingeben. Beispiel:

    tar cvfz joomlabackup.tar.gz /path-to-joomla

erzeugt eine gzip-komprimierte Archivdatei *joomlabackup.tar.gz*, die
alle Dateien der Joomla!-Installation enthält.

**Wichtige Anmerkung!** Wenn man das tar-Kommando gibt, darf man NICHT
im Ordner sein, von dem man das Backup erzeugt, da man sonst in eine
Endlosschleife gerät.

#### Archivdatei extrahieren

Ist die Archivdatei am Zielsystem, wird sie entpackt. Dafür das
entsprechende Kommando verwenden. Um die obern erstellte Archivdatei zu
entpacken, dies eingeben

    cd /path-to-joomla
    tar xvfz joomlabackup.tar.gz

Sind Benutzer- und -gruppen-IDs zwischen Quell- und Zielsystem
unterschiedlich, muß der Besitz der eben extrahierten Dateien geändert
werden. Auf einem Apachesystem muß zum Beispiel dieses Kommando
eingegeben werden

    cd /path-to-joomla
    chown -R www-user:www-group *

damit Apache Besitzer der Joomla!-Dateien ist.

*Bitte den Hostingprovider für die korrekten Gruppen- und Benutzernamen
`www-group` und `www-user` des Systems fragen.*

### Kopieren der Datenbank mit der MySQL-Kommandozeile

Meist wird `mysqldump` zum Erzeugen der Datenbankkopie eingegeben:

    $ mysqldump -u user -p db-name > db-name.out

Die `db-name.out`-Datei mit sftp/ssh auf den entfernten MySQL-Server
kopieren:

    $ scp db-name.out user@remote.box.com:/backup

Wiederherstellung der Datenbank am entfernten Server (Anmeldung mit
ssh):

    $ mysql -u user -p db-name < db-name.out
