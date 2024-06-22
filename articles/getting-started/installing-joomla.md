<!-- Filename: J4.x:Installing_Joomla / Display title: Joomla! installieren -->

## Einführung

Die erstmalige Installation von Joomla! ist sehr einfach. Nach Abschluss
der Vorarbeiten, dem Einrichten einer Hosting-Umgebung und dem Erstellen
einer Datenbank wird die Installation durch den eingebauten
Web-Installer zu einem Kinderspiel. Die einzelnen Schritte sind:

### Hosting Umgebung

Wenn noch keine Hosting-Umgebung eingerichtet ist, muss dies jetzt
nachgeholt werden, entweder bei einem Hosting-Anbieter oder auf dem
lokalen Computer. Details findet man in  Hosting
Setup.

Außerdem gibt es einige PHP-Einstellungen, die zur Installation von
Joomla erforderlich sind. Die Einstellungen befinden sich normalerweise
in einer *php.ini* oder *user.ini* Konfigurationsdatei auf dem Server.
Wenn ein Shared Hosting zur Verfügung steht, sollte man sich bei seinem
Provider erkundigen, wie man diese Einstellungen ändern kann, sofern
dies möglich ist. Falls eine lokale Umgebung, z.B. mit
XAMPP, ein
VPS oder dedizierter Rechner verwendet wird, sollten diese Einstellungen
uneingeschränkt möglich sein und selbst vorgenommen werden können.

Die Minimalanforderungen für die Datei *php.ini* sind nachfolgend
angegeben:

- *memory_limit:* 256M
- *upload_max_filesize:* 30M
- *post_max_size:* 30M
- *max_execution_time:* 30

Es ist zwar möglich, mit niedrigeren Werten für upload_max_filesize und
post_max_size zu arbeiten, aber größere Erweiterungen werden beim Upload
fehlschlagen und unvorhersehbare Probleme verursachen.

### Datenbank Setup

Wenn noch keine Datenbank eingerichtet ist, sollte dies jetzt nachgeholt
werden. Es wird für einen Hosting-Service im  Hosting
Setup-Tutorial
behandelt. Ferner gibt es das Tutorial  Erstellen einer Datenbank für
Joomla!,
das die Möglichkeiten von localhost und phpMyAdmin beschreibt.

Grundlegende Datenbankinformationen, die beim Start der eigentlichen
Joomla!-Installation benötigt werden, sollten vorher unbedingt notiert
werden.

- Wo befindet sich die Datenbank – normalerweise ist das *localhost*,
  auch bei einem Hosting-Service. Das kann auch ein spezieller Server
  des Hosts sein, wie z.B. *`dbserver1.yourhost.com`*.
- Name der Datenbank
- Name des Datenbankbenutzers
- Passwort des Datenbankbenutzers

## Vorbereitungen zur Installation

### Download und Upload der Joomla! Installationsdateien

Download der aktuellen Version von Joomla! über den Link auf der
<a href="https://downloads.joomla.org/" class="external text"
target="_blank" rel="noreferrer noopener">Joomla-Download</a>-Seite

Die heruntergeladene Zip-Datei des Joomla-Installationspakets auf den
Server übertragen. Bei einem Hosting-Service kann man vielleicht die
cPanel-Dateimanager-Upload-Funktion benutzen oder einen FTP-Client
verwenden, um die heruntergeladene Joomla 4.x Zip-Datei auf den Server
zu übertragen. Es gibt verschiedene FTP-Clients zur Auswahl. Hier findet
sich ein detaillierter <a
href="https://en.wikipedia.org/wiki/Comparison_of_FTP_client_software"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Vergleich von FTP-Client-Software</a>.
Im Zweifelsfall sollte FileZilla verwendet werden.

Das Stammverzeichnis (root) des Servers

Es empfiehlt sich, die heruntergeladene Zip-Paketdatei auf den Server zu
verschieben und dort zu entpacken, anstatt sie lokal zu entpacken und
dann den Dateiverzeichnisbaum zu verschieben. Normalerweise lädt man die
Webdateien in das Stammverzeichnis der Hosting-Umgebung hoch. Dieses
wird normalerweise *public_html* genannt. Andere enthalten z. B.
*htdocs* oder ähnliches. Dies hängt davon ab, was der Webhoster auf dem
Server eingerichtet hat. Für Joomla-Zwecke kann man die Dateien direkt
in *public_html* oder einen selbst erstellten Unterordner innerhalb
dieses Ordners laden.

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Warnung!

Wenn die Dateien auf dem eigenen Computer entpackt und dann auf den
Server kopiert werden, muss darauf geachtet werden, dass nur die Ordner
und Dateien verschoben werden, die **innerhalb** des Joomla-Pakets
enthalten sind. Wenn die Ordner und Dateien in einen Ordner entpackt
werden, der zum Beispiel *`Joomla`* heißt und dieser Ordner hochgeladen
wird, erreicht man die Website unter der URL *`yoursitename.com/Joomla`*
anstatt unter *`yoursitename.com`*. Das Joomla Unterverzeichnis kann in
einen anderen, der Website angemesseneren Namen, umbenannt werden, wie
z. B. jblog, was praktisch sein könnte. **Hinweis:** Verzeichnisnamen
sollten kleingeschrieben werden, ohne Leerzeichen und mit Minuszeichen
statt Unterstrichen, um Wörter zu trennen.

Die Zip-Paketdateien können mit diversen Tools (z.B. unzip) direkt auf
dem Host entpackt werden, welches auf dem Server installiert sein muss.
Falls Ihr Hosting-Service das Admin-Tool cPanel verwendet, kann im
File-Manager der Extract Knopf gedrückt werden. Unabhängig davon kann
auch das kostenlose Drittanbieter-Tool
<a href="https://www.akeeba.com/products/akeeba-kickstart.html"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Akeeba Kickstart</a> dafür benutzt
werden. Die entpackten Dateien und Verzeichnisse sollten im aktuellen
Ordner abgelegt werden. Die Extraktion auf dem lokalen Computer hängt
vom Betriebssystem ab. Mit einem Rechts-Klick könnte man prüfen, ob es
ein Menü zum Entpacken gibt. In diesem Fall legt das Betriebssystem die
Dateien möglicherweise in einem Ordner mit dem gleichen Namen wie die
Zip-Datei ab. Nach dem Entpacken sollte man die Zip-Datei löschen und
den Ordner, in den die Dateien extrahiert wurden, umbenennen, sodass er
einen kurzen Namen erhält, der für die Verwendung in einer URL geeignet
ist.

## Installation Starten

Wenn die oben genannten Anforderungen erfüllt sind, eine Datenbank
erstellt wurde und die erforderlichen Joomla!-Dateien vorhanden sind,
kann mit der Installation von Joomla! begonnen werden. Den Web-Installer
von Joomla! startet man, in dem der bevorzugte Browser geöffnet wird und
der Domain-Name der Website aufgerufen wird. Bei einer Host-Installation
wählt man *`https://www.yoursitename.com`*. Bei einer lokalen
Joomla-Installation sollte *`http://localhost/`* gewählt werden. Dann
erscheint der Installationsbildschirm..

<img
src="https://docs.joomla.org/images/thumb/c/c1/J4x_Installation_screen_page_1_de.png/500px-J4x_Installation_screen_page_1_de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/c/c1/J4x_Installation_screen_page_1_de.png/750px-J4x_Installation_screen_page_1_de.png 1.5x, https://docs.joomla.org/images/c/c1/J4x_Installation_screen_page_1_de.png 2x"
data-file-width="1000" data-file-height="514" width="500" height="257"
alt="J4x Installation screen page 1 de.png" />

Joomla wird versuchen, das Feld *Installationssprache auswählen*
automatisch mit der vom Browser verwendeten Sprache abzugleichen. Bei
Bedarf lässt sich diese Einstellung ändern.

Bitte die nachfolgenden Informationen eingeben:

- **Name der Website**: Der Name der Joomla!-Website – dies kann später
  auf der Seite  Globale Konfiguration der
  Website
  zu jedem beliebigen späteren Zeitpunkt geändert werden.

Wenn alles auf der ersten Seite ausgefüllt ist, auf die Schaltfläche
*Zugangsdaten einrichten* klicken, um fortzufahren.

## Zugangsdaten

Jetzt sollte das Fenster für die Anmeldedaten zu sehen sein.

<img
src="https://docs.joomla.org/images/thumb/5/55/J4x_Installation_screen_page_2_de.png/500px-J4x_Installation_screen_page_2_de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/5/55/J4x_Installation_screen_page_2_de.png/750px-J4x_Installation_screen_page_2_de.png 1.5x, https://docs.joomla.org/images/5/55/J4x_Installation_screen_page_2_de.png 2x"
data-file-width="1000" data-file-height="602" width="500" height="301"
alt="J4x Installation screen page 2 de.png" />

Bitte die nachfolgenden Informationen eingeben:

- **Name des Super-Benutzers**: der Real-Name des Administrators. So
  wird die Begrüßung durch Joomla beim Anmelden aussehen.
- **Benutzername des Super-Benutzers**: Der Benutzername für den **Super
  User**. Er sollte nicht *admin* lauten (das wäre eine gute  Mein
  Profil
  beschrieben, auf der *Administration*-Oberfläche geändert werden.
- **Passwort des Super-Benutzers**: Bitte bedenken, dass der Superuser
  die maximale Kontrolle über die Website und die
  Administrator-Oberfläche hat. Es sollte deshalb ein komplexes Passwort
  gewählt werden. Um es später zu ändern, kann in der
  *Administration*-Oberfläche das
  Benutzermenü
  aufgerufen werden.
- **E-Mail-Adresse des Super Benutzers**: Bitte hier eine gültige E-Mail
  eingeben, für den Fall, dass das Passwort vergessen wurde. An diese
  E-Mail-Adresse wird ein Link zum Ändern des Super-User-Passworts
  gesendet.

Wenn alles auf der zweiten Seite ausgefüllt ist, wird auf die
Schaltfläche **„Datenbankverbindung einrichten“** geklickt, um
fortzufahren.

## Datenbank-Konfiguration

Die Informationen über die Datenbank, die bei der Erstellung der
Datenbank für diese Installation notiert wurden, sind hier einzutragen.
Siehe auch die Seite  Datenbank für Joomla!
erstellen.

<img
src="https://docs.joomla.org/images/thumb/1/1a/J40_Installation_screen_page_3-de.png/500px-J40_Installation_screen_page_3-de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/1/1a/J40_Installation_screen_page_3-de.png/750px-J40_Installation_screen_page_3-de.png 1.5x, https://docs.joomla.org/images/1/1a/J40_Installation_screen_page_3-de.png 2x"
data-file-width="1000" data-file-height="753" width="500" height="377"
alt="J40 Installation screen page 3-de.png" />

Der Einfachheit halber wird in dieser Anleitung auf die Installation mit
einer <a href="https://en.wikipedia.org/wiki/MySQLi" class="extiw"
title="wikipedia:MySQLi">MySQLi</a>-Datenbank eingegangen. Die
Anweisungen auf der Installationsseite sind selbsterklärend, hier sind
sie noch einmal aufgeführt:

- **Datenbanktyp**: MySQLi ist die übliche verwendete Datenbank
- **Datenbank-Server**: Wo befindet sich die Datenbank? Üblich ist
  *localhost*, auch bei Hosting-Services. Einige Anbieter verwenden
  jedoch einen speziellen Datenbank-Server, wie z.B.
  *dbserver1.yourhost.com*.
- **Datenbank-Benutzername**: Der Benutzername, der für die Verbindung
  mit der Datenbank verwendet wird
- **Datenbank-Password**: Das Passwort zum Benutzernamen (nicht das
  Administrator-Passwort)
- **Datenbank-Name**: Der Name der Datenbank
- **Tabellen-Präfix**: Er wird aus Sicherheitsgründen automatisch
  generiert. Den per Zufall generierten Wert kann man übernehmen oder
  ändern. Wichtig ist nur, dass der Unterstrich (`_`) am Ende nicht
  vergessen wird.
- **Verbindungsverschlüsselung**: Bestimmt, wie die Verbindung zur
  Datenbank verschlüsselt werden soll. Wenn man es nicht besser weiß –
  dann bleibt man am besten bei der Voreinstellung. Dies ermöglicht es
  jedoch Unternehmen, die eine ein oder zwei Wege-Authentifizierung für
  die Datenbankverbindung verwenden, diese zu ermöglichen.

Alle diese und weitere Einstellungen können auf der Seite
Konfiguration
unter *Server-Optionen*, nach Abschluss der Installation, bearbeitet
werden. Bitte beachten, dass die Installation beschädigt wird, wenn
diese Einstellungen nach der Installation geändert werden, es sei denn,
es existiert eine vollständige Kopie der aktuellen Joomla-Datenbank. Die
typische Anwendung wäre, den Benutzernamen und das Passwort der
Datenbank zu aktualisieren oder den Umzug einer bestehenden Installation
auf einen neuen Host, mit anderen Parametern, abzuschließen.

Nachdem die Schaltfläche *Joomla! installieren* angeklickt wurde, wird
das sich drehende Joomla-Logo zu sehen sein. Sobald die Installation
abgeschlossen ist, sollte man die Erfolgsmeldung sehen.

## Fertigstellung

### Erfolg und Fertigstellung der Installation

Herzlichen Glückwunsch! Joomla 4 ist nun installiert.

<img
src="https://docs.joomla.org/images/thumb/f/f1/J40_Installation_screen_page_4_de.png/500px-J40_Installation_screen_page_4_de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/f/f1/J40_Installation_screen_page_4_de.png/750px-J40_Installation_screen_page_4_de.png 1.5x, https://docs.joomla.org/images/thumb/f/f1/J40_Installation_screen_page_4_de.png/1000px-J40_Installation_screen_page_4_de.png 2x"
data-file-width="1384" data-file-height="600" width="500" height="217"
alt="J40 Installation screen page 4 de.png" />

Wenn Joomla ohne die  Installation zusätzlicher
Sprachen
sofort verwendet werden soll, dann wählt man *Administrator öffnen*, um
zum *Administrator Dashboard* zu kommen oder wählt die Option *Site
öffnen*, um zur Homepage der Website zu springen. Möglicherweise ist ein
Abschnitt mit empfohlenen PHP-Einstellungen zu sehen.

- **Empfohlene Einstellungen**: Diese Einstellungen werden in der
  PHP-Konfiguration empfohlen, verhindern aber nicht, dass Joomla!
  installiert wird. Falls nötig, können sie mit Hilfe der obigen
  Anleitung geändert werden.

### Zusätzliche Sprachen

Im Rahmen des Joomla-Installationsprozesses besteht die Möglichkeit,
zusätzliche Sprachen zu installieren, bevor die Installation
abgeschlossen wird:

Dazu die Schaltfläche „Zusätzliche Sprachen installieren“ anklicken.

Dies führt zu einer zusätzlichen Installationsseite, auf der die
gewünschten Sprachen ausgewählt werden können.

#### Zusätzliche Sprachen Installieren

Eine Liste der vorhandenen Sprachpakete wird angezeigt (Deutsch ist
unter *German* zu finden)

<img
src="https://docs.joomla.org/images/thumb/5/56/J40_Installation_screen_page_5_de.png/500px-J40_Installation_screen_page_5_de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/5/56/J40_Installation_screen_page_5_de.png/750px-J40_Installation_screen_page_5_de.png 1.5x, https://docs.joomla.org/images/thumb/5/56/J40_Installation_screen_page_5_de.png/1000px-J40_Installation_screen_page_5_de.png 2x"
data-file-width="1368" data-file-height="755" width="500" height="276"
alt="J40 Installation screen page 5 de.png" />

**Nur bis zu drei gewünschte Sprachen auswählen** (bei mehr als drei
kann es zu Timeout-Problemen kommen – später können weitere Sprachen
installiert werden).

Bitte Folgendes im Hinterkopf behalten:

- Sprachpakete, die in benutzerdefinierten Installationspaketen
  enthalten sind, werden zu diesem Zeitpunkt nicht aufgelistet, da sie
  bereits installiert sind.
- Die Version der vorgeschlagenen Pakete passt zur Joomla-Hauptversion
  (4.0.x, 4.1.x, usw.). Die Unterversion des Pakets muss nicht
  übereinstimmen, z. B. wenn eine Version 4.0.3 installiert ist und ein
  4.0.2 Sprachpaket angezeigt wird.
- Nicht übereinstimmende Sprachpakete im Beispiel oben können nicht
  übersetzte Textstellen enthalten.
- Die nicht angepassten Sprachpakete werden als Update bereitgestellt,
  sobald die Pakete von den registrierten Übersetzungsteams aktualisiert
  werden. Das verfügbare Update wird sowohl im Dashboard als auch in
  **System **→** Erweiterungen **→** Sprachen** angezeigt.
  Dieses Verfahren ist vergleichbar mit
  **System **→** Verwalten **→** Sprachen **→** Sprachen installieren**.

Auf die Schaltfläche *Weiter* klicken, dann wird ein Fortschrittsbalken
angezeigt, während das Sprachpaket oder die Sprachpakete installiert
werden.

#### Standard-Sprache wählen

Wenn die Installation abgeschlossen ist, wird jetzt auf dem Bildschirm
ein Fenster mit ähnlichem Inhalt angezeigt: *Herzlichen Glückwunsch!
Joomla! wurde vollständig installiert*. Der wesentliche Unterschied
besteht in der Liste der installierten Sprachen, aus der die
Standardsprache für die Website und die Administratoroberfläche
ausgewählt werden kann.

<img
src="https://docs.joomla.org/images/8/8b/J40_Installation_screen_page_4_default_langs_de.png"
class="thumbborder" decoding="async" data-file-width="1384"
data-file-height="579" width="1384" height="579" alt="500" />

- Die Auswahl für die Standardsprache kann hier getroffen werden.
- Wenn die Standardsprache ausgewählt ist, zur Bestätigung auf die
  Schaltfläche *Standardsprache festlegen* klicken.
- Es wird eine Systemmeldung angezeigt, die bestätigt, dass Joomla die
  Standardsprachen für **Administrator** und **Site** eingestellt hat.
  Diese Meldung kann geschlossen werden.

#### Abschließen

Jetzt kann man das *Administrator Dashboard* aufrufen, indem man
*Administrator öffnen* wählt oder direkt zur Homepage der Website gehen,
indem man *Site öffnen* anklickt.

## Verwandte Informationen

-  Hosting
  Setup
-  Sicherheits-Checkliste / Einrichtung von Hosting und
  Server
-  Creating A VPS Testing
  Server
-  Joomla! an die eigene Umgebung
  anpassen
-  Joomla CLI
  Installation
