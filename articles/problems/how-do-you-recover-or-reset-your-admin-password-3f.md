<!-- Filename: How_do_you_recover_or_reset_your_admin_password%3F / Display title: Wie kann das Administrator Passwort wieder hergestellt oder zurückgesetzt werden? -->

Passwort Wiederherstellung für Joomla! 2.5 und höher

Diese Anleitung ist für die Versionen ab Joomla! 2.5 zu verwenden. Falls
noch Joomla! 1.5 eingesetzt wird  sind die Anweisungen hier zu
finden..

Normalerweise können in der Benutzerverwaltung des Backends Benutzer und
deren Passwörter anlegt, bearbeitet und gelöscht werden. Dazu muss man
im Backend eingeloggt und der Benutzergruppe Super Benutzer zugeordnet
sein.

In manchen Situationen ist dies nicht mehr möglich. Zum Beispiel könnte
die Website "gehackt" und die Passwörter geändert worden sein. Die
Person, die die Passwörter wusste, ist nicht mehr verfügbar oder das
verwendete Passwort wurde vergessen.

In diesen Fällen ist es möglich die Joomla! Datenbank so zu verändern,
daß man sich wieder als Super Benutzer anmelden kann.

## Methode 1: Datei: configuration.php

Bei Zugriffsmöglichkeit auf die `configuration.php` Datei der
Joomla!-Installation auf den Server, kann das Passwort mit folgender
Methode wieder hergestellt werden:

1\. Man verbindet sich mit der Site über ein FTP Programm und ermittelt
die Dateirechte der Datei configuration.php. Falls die Rechte auf 444
oder einen anderen Wert gesetzt sind, werden sie auf 644 geändert. Dies
hilft Probleme zu vermeiden, wenn die Datei später im
Wiederherstellungs-Prozess hochgeladen wird.

2\. Die Konfigurationsdatei herunterladen.

3\. Die Datei configuration.php in einem Texteditor, wie zum Beispiel
Notepad++, öffnen und folgende Zeile

    public $root_user='myname';

an das untere Ende der Liste hinzufügen. Dabei ist myname ein
Benutzername mit Administrator Zugriffsrechten, für den man das Passwort
kennt. Anstelle eines Benutzernamens mit Administratorzugriff kann auch
ein Benutzername verwendet werden, der sich in der Berechtigungsstufe
„Benutzergruppe Autoren“ oder höher befindet.

4\. Die Datei configuration.php wird gespeichert und auf die Seite
hochgeladen. Die Dateirechte der Datei configuration.php können auf 644
stehen bleiben.

Dieser Benutzer wird nun ein temporärer Super Benutzer.

5\. Nach dem Anmelden im Backend kann das Passwort des Administrators,
für den das Passwort nicht bekannt ist, geändert werden oder ein neuer
Super Benutzer angelegt werden.

6\. Nach der Änderung sicherstellen, dass der in einer Warnbox
angezeigte "Click here to try to do it automatically"-Link verwendet
wird, um die, an die Datei configuration.php angefügte, Zeile, zu
entfernen. Falls dies nicht erfolgreich war, muss die Zeile manuell, mit
Hilfe des Text-Editors, aus der Datei configuration.php entfernt werden.

7\. Mit Hilfe eines FTP-Programmes werden nun die Dateirechte der Datei
configuration.php überprüft. Sie sollten 444 sein. Falls die zusätzliche
Zeile manuell angehängt wurde, müssen die Dateirechte der Datei
configuration.php auf 444 geändert werden.

Falls es keine Benutzer gibt, die ihr Passwort kennen und keine Frontend
Registrierung verwendent werden kann, ist die nachfolgend beschriebene
Datenbankänderung eine weitere Option.

## Methode 2: Direktes Editieren der Datenbank

Wenn die oben beschriebenen Methoden nicht funktionieren, gibt es zwei
weitere Möglichkeiten, die direkt auf der MySQL Datenbank arbeiten.

### Änderung des Passworts in der Datenbank

Falls der Super Benutzer noch definiert ist, besteht die einfachste
Möglichkeit darin, das Passwort in der Datenbank auf einen neuen Wert zu
ändern. Dies erfordert, den Zugriff auf die MySQL Datenbank über
phpMyAdmin oder einen anderen Client.

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Es ist sehr wichtig, das Super
Benutzer-Passwort zu ändern, wenn der Zugriff auf das Backend wieder
hergestellt ist.

Diese Anleitung zeigt, wie man ein Passwort manuell ändern kann -
"secret"

1.  In der phpMyAdmin wird die passende Datenbank zum Joomla! System in
    der Dropdown Liste auf der linken Seite ausgewählt. Es werden nun
    die Datenbanktabellen auf der linken Seite des Bildschirms
    angezeigt.

2.  Die Tabelle mit "\_users" anklicken (Wichtig: die Tabelle muss einen
    Präfix haben, möglichweise weicht der Präfix vom früher verwendeten
    jos\_ ab).

3.  Anklicken des "Anzeigen" Buttons in der oberen Werkzeugleiste.
    Dadurch werden alle eingerichteten Benutzer der Website angezeigt.

4.  Bei dem Benutzer, dessen Passwort geändert werden soll, wird das
    "Bearbeiten" Icon für diese Zeile geklickt.

5.  Es öffnet sich ein Formular. Dort kann das Passwort (password) Feld
    bearbeitet werden. Folgender Wert muss kopiert werden

        d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199

    und in das Passwort Feld (password) eingetragen werden. Danach den
    "OK" Button drücken. phpMyAdmin sollte die Nachricht "1 Zeile(n)
    betroffen" ausgeben. Damit wurde das Passwort zu **"secret"**
    geändert.

6.  Jetzt erfolgt die Anmeldung im Joomla Backend mit dem soeben
    bearbeiteten Benutzer und dem geänderten Passwort. Danach muss das
    Passwort auf einen sicheren Wert geändert werden. Es sollten alle
    vorhandenen Benutzer überprüft werden, um sicher zu gehen, dass sie
    legitim sind. Falls die Website gehackt wurde, sollten alle
    Passwörter der Website geändert werden.

## Anlegen eines neuen Super Benutzers

Falls das Ändern des Passwortes nicht funktionierte oder nicht klar ist,
welcher Benutzer zu der Gruppe der Super Benutzer gehört, kann mit
dieser Methode ein neuer Benutzer angelegt werden.

1.  In der phpMyAdmin wird die passende Datenbank zum Joomla! System in
    der Dropdown Liste auf der linken Seite ausgewählt. Es werden alle
    Datenbanktabellen auf der linken Seite des Bildschirms angezeigt.
2.  Nach dem Drücken des "SQL" Buttons in der Werkzeugleiste, kann ein
    SQL-Query auf der ausgewählten Datenbank ausgeführt werden. Es wird
    ein Feld namens "Run SQL query/queries on database " angezeigt.
3.  Nach dem Leeren des Feldes wird nachfolgender SQL-Code (in der
    grauen Box) in das Feld kopiert. Durch das Drücken des "OK" Buttons
    wird der Query ausgeführt und dadurch ein neuer Adminstrator in der
    Datenbanktabelle angelegt.
4.  Untenstehender SQL Code, kann für diesen Schritt verwendet werden

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Es muss unbedingt sichergestellt
werden, dass der Datenbanktabellen Präfix des Codes mit dem der eigenen
Datenbank übereinstimmt.

Der nachfolgende Code verwendet jos31\_ als Tabellennamen Präfix. Dies
ist nur ein Beispiel. Der tatsächliche Präfix wird beim Installieren
zufällig "RANDOM" vergeben oder entspricht dem, was individuell
eingestellt wurde. Es müssen alle im Code vorkommenden "jos31\_" Präfixe
durch den Präfix des eigenen Systems ersetzt werden!

**SQL Code zur Verwendung mit Joomla
 <img src="https://docs.joomla.org/images/5/53/Compat_icon_2_5.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 2.5" /> <img src="https://docs.joomla.org/images/4/4d/Compat_icon_3_x.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 3.x" /> <img src="https://docs.joomla.org/images/b/bd/Compat_icon_4_x.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 4.x" />**

    INSERT INTO `jos31_users`
       (`name`, `username`, `password`, `params`, `registerDate`, `lastvisitDate`, `lastResetTime`)
    VALUES ('Administrator2', 'admin2',
        'd2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199', '', NOW(), NOW(), NOW());
    INSERT INTO `jos31_user_usergroup_map` (`user_id`,`group_id`)
    VALUES (LAST_INSERT_ID(),'8');

Nun sollte die Anmeldung in das Backend mit dem Benutzernamen "admin2"
und dem Passwort "secret" möglich sein. Nach dem Anmelden muss in der
Benutzerverwaltung das Passwort geändert werden und eine valide E-Mail
Adresse eingetragen werden. Falls der Verdacht besteht, dass das System
"gehackt" worden ist, sollten alle Benutzer auf Legitimität überprüft
werden, insbesondere die Super Benutzer.

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Warning!

Warnung: Die auf dieser Seite verwendeten Passwörter sind öffentlich und
daher nur zur Wiederherstellung zu verwenden. Falls die Passwörter nicht
auf sichere Werte geändert werden, kann die Webseite gehackt werden. Die
Passwörter müssen unbedingt nach dem Anmelden auf sichere Werte geändert
werden.


Die obigen Code Beispiele ändern das Passwort zu "secret". Zwei andere
mögliche Werte sind nachfolgend aufgezeigt.

    - password = "this is the MD5 and salted hashed password"
    ------------------------------------------------------
    - admin  = 433903e0a9d6a712e00251e44d29bf87:UJ0b9J5fufL3FKfCc0TLsYJBh2PFULvT
    - secret = d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199
    - OU812  = 5e3128b27a2c1f8eb53689f511c4ca9e:J584KAEv9d8VKwRGhb8ve7GdKoG7isMm
