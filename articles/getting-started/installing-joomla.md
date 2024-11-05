<!-- Filename: J4.x:Installing_Joomla / Display title: Installation von Joomla -->

## Einführung

Die Installation von Joomla! zum ersten Mal ist sehr einfach. Nach Abschluss der vorbereitenden Schritte, der Einrichtung einer Hosting-Umgebung und der Erstellung einer Datenbank wird der integrierte Webinstaller von Joomla Ihre neue Seite in nur wenigen Minuten einrichten. Die vorherigen Schritte:

### Hosting-Einrichtung

Falls Sie noch keine Hosting-Umgebung eingerichtet haben, sollten Sie dies jetzt tun, entweder bei einem Hosting-Dienst oder auf Ihrem lokalen Computer.

Außerdem gibt es einige PHP-Einstellungen, die ausreichend sein müssen, damit Joomla installiert werden kann. Die Einstellungen befinden sich normalerweise in einer *php.ini*- oder *user.ini*-Konfigurationsdatei auf dem Server. Wenn Sie Shared Hosting nutzen, sprechen Sie mit Ihrem Hosting-Dienst darüber, wie diese Einstellungen geändert werden können, falls dies möglich ist. Wenn Sie auf einem lokalen Server arbeiten, zum Beispiel mit XAMPP, oder auf einem VPS oder dedizierten Host, sollten Sie durch diese Einstellungen nicht eingeschränkt sein und können sie selbst festlegen.

Die Mindestwerte für die *php.ini*-Datei sind unten aufgeführt:

- *memory_limit:* 256M
- *upload_max_filesize:* 64M
- *post_max_size:* 64M
- *max_execution_time:* 30

Es ist möglich, mit niedrigeren Werten für upload_max_filesize und post_max_size zu arbeiten, aber größere Erweiterungen werden beim Hochladen fehlschlagen und unvorhersehbare Probleme verursachen.

### Datenbankeinrichtung

Falls Sie noch keine Datenbank eingerichtet haben, sollten Sie dies jetzt tun. Dies wird für einen cPanel-Hosting-Dienst im Tutorial [cPanel Hosting](jdocmanual?article=user/hosting/cpanel-hosting "cPanel Hosting") behandelt. Es gibt auch ein *Erstellen einer Datenbank für Joomla!*-Tutorial, das localhost- und phpMyAdmin-Methoden abdeckt.

Sie sollten sich grundlegende Datenbankinformationen notieren, die benötigt werden, wenn die eigentliche Joomla-Installation gestartet wird.

- Speicherort der Datenbank, normalerweise *localhost* selbst bei einem Hosting-Dienst. Es kann sich um den Server eines bestimmten Hosts handeln, wie zum Beispiel *`dbserver1.yourhost.com`*.
- Der Datenbankname
- Der Datenbankbenutzername
- Das Passwort des Datenbankbenutzers

## Vorbereitung zur Installation

### Herunterladen und Hochladen von Joomla!-Paketdateien

Laden Sie die aktuelle Version von Joomla! über den Link auf der
[Download Joomla](https://downloads.joomla.org/) Seite herunter.

Verschieben Sie das heruntergeladene Joomla-Installationspaket-Zipfile auf den Server.
Bei einem Hosting-Dienst können Sie die cPanel Dateimanager-Uploadfunktion
nutzen oder einen FTP-Client verwenden, um das heruntergeladene Joomla
5.x-Zipfile auf Ihren Server zu übertragen. Es gibt verschiedene FTP-Clients.
Hier ist ein detaillierter [Vergleich von FTP-Client-Software](https://de.wikipedia.org/wiki/Vergleich_von_FTP-Client-Software).
Im Zweifelsfall verwenden Sie FileZilla.

Der *Root*-Ordner Ihres Servers

Es ist besser, das heruntergeladene Zip-Paket auf Ihren Server zu übertragen
und es dort zu entpacken, als es lokal zu entpacken und dann den gesamten
Dateibaum zu verschieben. Normalerweise laden Sie Ihre Webdateien in den Root-Ordner
Ihres Hosting-Dienstes hoch. Dieser wird typischerweise `public_html` genannt,
aber andere Varianten wie `htdocs` sind möglich und hängen davon ab, wie Ihr
Host den Server eingerichtet hat. Für Joomla-Zwecke können Sie die Dateien
direkt in *public_html* oder einen Unterordner, den Sie darin erstellt haben,
laden.

**Warnung:** Entpacken Sie die Dateien auf Ihrem eigenen Computer und kopieren
Sie diese dann auf Ihren Server, achten Sie darauf, nur die Ordner und Dateien
zu verschieben, die sich **innerhalb** des Joomla-Pakets befinden. Wenn Sie die
Ordner und Dateien in einen Ordner entpacken, zum Beispiel *`Joomla`* genannt,
und dann diesen Ordner hochladen, muss Ihr Standort unter
*`deinseitenname.com/Joomla`* anstatt *`deinseitenname.com`* aufgerufen werden.
Sie können das Unterverzeichnis von Joomla in etwas passenderes umbenennen,
zum Beispiel jblog, und das könnte Ihnen nützlich erscheinen. **Hinweis:**
Verzeichnisnamen sollten klein geschrieben, ohne Leerzeichen und mit
Bindestrichen statt Unterstrichen zur Trennung der Wörter sein.

Die Zip-Paketdateien können direkt auf dem Host mit verschiedenen
Befehlszeilenwerkzeugen (z.B. unzip), die auf dem Server installiert sein
müssen, extrahiert werden. Wenn Ihr Hosting-Dienst das Admin-Tool cPanel
verwendet, kann die Extraktion im Dateimanager durch Klicken auf den
Extract-Button durchgeführt werden. Außerdem kann das kostenlose
Drittanbieter-Tool Akeeba Kickstart für diesen Zweck verwendet werden. 
Die entpackten Dateien und Verzeichnisse werden in den aktuellen Ordner
gelegt. Die Extraktion auf Ihrem lokalen Computer hängt von Ihrem Betriebssystem ab.
Versuchen Sie, mit der rechten Maustaste zu klicken, um zu sehen, ob es ein
Extraktionsmenü gibt. In diesem Fall könnte Ihr Betriebssystem die Dateien in
einen Ordner mit demselben Namen wie die Zipdatei legen. Nach der Extraktion
können Sie die Zipdatei löschen und den Extraktionsordner in etwas Kurzes und
Nützliches für die Verwendung in einer URL umbenennen.

## Installation Starten

Mit den oben genannten Anforderungen, einer erstellten Datenbank und den erforderlichen Joomla-Dateien sind Sie bereit, Joomla zu installieren. Starten Sie den Joomla-Webinstaller, indem Sie Ihren bevorzugten Browser öffnen und zur Domain der Webseite navigieren. Bei einer Hosting-Installation verwenden Sie *`https://www.yoursitename.com`*. Wenn Sie Joomla lokal installieren, verwenden Sie *`http://localhost/`* und sollten den Installationsbildschirm sehen.

![Joomla-Installer Teil 1, Installationssprache und Site-Name](../../../en/images/getting-started/installing-joomla-installer-1.png)

Joomla wird versuchen, das Feld *Sprache auswählen* automatisch anhand der Sprache Ihres Browsers zu identifizieren. Sie können dies bei Bedarf ändern.

Füllen Sie die folgenden Informationen aus.

- **Site Name** Der Name Ihrer Webseite — dies kann jederzeit später auf der Seite „Globale Konfiguration der Webseite“ geändert werden.

Wenn alles auf der ersten Seite ausgefüllt ist, den *Logindaten einstellen* Button anklicken, um fortzufahren.

## Anmeldedaten

Sie sollten nun den Bildschirm mit den Anmeldedaten sehen.

![Joomla-Installer Teil 2, Anmeldedaten](../../../en/images/getting-started/installing-joomla-installer-2.png)

Füllen Sie die folgenden Informationen aus.

- **Echter Name** Der Name des Super-Benutzers. So wird Joomla Sie begrüßen, wenn Sie sich einloggen.
- **Benutzername des Super-Benutzerkontos** Der Benutzername für den *Super-Benutzer*. Vermeiden Sie es, *admin* als Administratornamen zu verwenden!
- **Admin-Passwort** Denken Sie daran, dass ein Super-Benutzer maximalen Zugriff auf die Site- und Administrator-Schnittstellen hat, also verwenden Sie ein schwieriges Passwort. Nutzen Sie **Mein Profil** in der *Administrationsschnittstelle*, um es später zu ändern.
- **Super-Benutzer-E-Mail-Adresse** Die E-Mail-Adresse des Super-Benutzers. Geben Sie eine gültige E-Mail-Adresse ein, falls Sie Ihr Passwort vergessen. Dies ist die E-Mail-Adresse, an die Sie einen Link zum Ändern des Super-Benutzer-Passworts erhalten.

Wenn alles auf der zweiten Seite ausgefüllt ist, klicken Sie auf die Schaltfläche *Datenbankverbindung einrichten*, um fortzufahren.

## Datenbankkonfiguration

Geben Sie die Datenbankinformationen ein, die Sie notiert haben, als Sie die Datenbank
für diese Installation erstellt haben.

![Joomla-Installer Teil 3, Datenbankkonfiguration](../../../en/images/getting-started/installing-joomla-installer-3.png)

Zur Vereinfachung beziehen sich diese Anweisungen auf die Installation
mit einer MySQLi-Datenbank. Die Anweisungen auf der Installationsseite sind
selbsterklärend, aber hier sind sie noch einmal:

- **Datenbanktyp** MySQLi ist die übliche Datenbank, die verwendet wird
- **Hostname** Wo sich Ihre Datenbank befindet. Üblich ist *localhost*,
  sogar bei Hosting-Diensten. Allerdings verwenden einige Hosts einen spezifischen Datenbankserver wie *dbserver1.yourhost.com*.
- **Benutzername** Der Benutzername, der zur Verbindung mit der Datenbank verwendet wird
- **Passwort** Das Passwort für den Datenbankbenutzer (nicht Ihr
  Administrator-Passwort)
- **Datenbankname** Der Name der Datenbank
- **Tabellenpräfix** Dies wird automatisch als Sicherheitsfunktion
  generiert. Sie können den zufällig generierten Standard akzeptieren oder ihn ändern.
  Vergessen Sie nur nicht, das Unterstrich-Zeichen (`_`) am Ende des
  Präfixes zu setzen.
- **Verbindung Verschlüsselung** gibt an, wie die Verbindung zur
  Datenbank verschlüsselt werden soll. Wenn Sie es nicht wissen, ist es am besten,
  die Standardeinstellung zu belassen. Es ermöglicht jedoch Unternehmen, die eine oder
  zweiseitige Authentifizierung für die Datenbankverbindung verwenden, dies bereitzustellen.

Alle diese Einstellungen und mehr können auf der Seite *Globale Konfiguration der Website*
unter *Serveroptionen* bearbeitet werden, nachdem die Installation abgeschlossen ist. Beachten Sie,
dass Sie Ihre Installation beschädigen, wenn Sie diese Einstellungen nach
der Installation ändern, es sei denn, Sie haben eine vollständige Kopie der aktuellen Datenbank,
die von der Joomla-Installation verwendet wird. Übliche Anwendungen wären, den
Benutzernamen und das Passwort der Datenbank zu aktualisieren oder eine vorhandene Installation auf einen neuen Host mit anderen Parametern zu verschieben.

Nachdem Sie die *Joomla installieren* Taste geklickt haben, sollten Sie die
Joomla-Installationsfortschrittsanzeige sehen.

![Joomla-Installer Teil 4, Installationsfortschrittsanzeige](../../../en/images/getting-started/installing-joomla-installer-4.png)

Sobald die Installation abgeschlossen ist, sollten Sie die Erfolgsseite sehen.

## Abschluss

### Erfolgreicher Abschluss der Installation

Herzlichen Glückwunsch! Ihre Joomla-Seite ist einsatzbereit.

![Joomla-Installer Teil 5, Ihre Joomla-Seite ist fertig](../../../en/images/getting-started/installing-joomla-installer-5.png)

Der obige Screenshot zeigt eine Entwicklerinstallation. Eine Produktionsinstallation entfernt automatisch den Installationsordner.

Wenn Sie Joomla sofort nutzen möchten, ohne zusätzliche Sprachen zu installieren, können Sie *Administrator öffnen* auswählen, um zum *Administrator-Dashboard* zu gelangen, oder *Seite öffnen*, um zur Startseite der Website zu gelangen. Möglicherweise sehen Sie einen Abschnitt mit empfohlenen PHP-Einstellungen.

- **Empfohlene Einstellungen** Diese Einstellungen werden in Ihrer PHP-Konfiguration empfohlen, verhindern aber nicht die Installation von Joomla!. Sie können sich auf die oben genannten Anweisungen beziehen, um zu erfahren, wie sie geändert werden können, falls dies notwendig ist.

### Zusätzliche Sprachen

Im Rahmen des Joomla-Installationsprozesses haben Sie die Möglichkeit, zusätzliche Sprachen zu installieren, bevor Sie die Installation abschließen.

Wählen Sie dazu die Schaltfläche Zusätzliche Sprachen installieren

Dies führt Sie zu einer zusätzlichen Installationsseite, auf der Sie die gewünschten Sprachen auswählen können.

#### Zusätzliche Sprachen installieren

Eine Liste von Sprachpaketen wird angezeigt.

![Joomla-Installer Teil 6, zusätzliche Sprachen installieren](../../../en/images/getting-started/installing-joomla-installer-6.png)

Wählen Sie bis zu 3 Sprachen aus, die Sie installieren möchten. (Mehr als 3 gleichzeitig können zu Timeout-Problemen führen; Sie können später weitere installieren.)

Beachten Sie Folgendes:

- Sprachpakete, die in benutzerdefinierten Distributionen enthalten sind, werden in diesem Schritt nicht angezeigt, da sie bereits installiert sind.
- Eine Version der vorgeschlagenen Pakete wird zur Joomla-Hauptversion passen (5.0.x, 5.1.x usw.). Die Nebenversionsnummer des Pakets kann jedoch nicht übereinstimmen, z.B. Sie installieren Version 5.0.3 und ein 5.0.2 Sprachpaket wird angezeigt.
- Nicht übereinstimmende Sprachpakete im obigen Beispiel können unübersetzte Zeichenfolgen enthalten.
- Die nicht übereinstimmenden Sprachpakete werden als Update angeboten, wenn die Pakete von den registrierten Übersetzungsteams aktualisiert werden. Das verfügbare Update wird sowohl im Kontrollpanel als auch unter **Erweiterungen → Update** angezeigt. Dieses Verhalten ist ähnlich wie **Erweiterungen → Sprachen installieren**.

*Weiter* und eine Fortschrittsleiste werden angezeigt, während das Sprachpaket oder die Sprachpakete installiert werden.

#### Standard-Sprache wählen

Wenn die Installation der Sprachen abgeschlossen ist, wird Ihnen nun ein ähnlicher Bildschirm *Herzlichen Glückwunsch! Ihre Joomla-Seite ist einsatzbereit.* angezeigt. Der Unterschied wird eine Liste der installierten Sprachen sein, die es Ihnen ermöglicht, die Standard-Sprache für die Seite und die Administrator-Oberfläche auszuwählen.

![Joomla-Installer Teil 7, Standardsprache wählen](../../../en/images/getting-started/installing-joomla-installer-7.png)

- Wählen Sie die Standardsprache, die Sie verwenden möchten.
- Wenn Sie die Standardsprache ausgewählt haben, bestätigen Sie diese mit der Schaltfläche *Standardsprache festlegen*.
- Eine Systemnachricht wird angezeigt, die bestätigt, dass Joomla die Standard-ADMINISTRATOR- und SITE-Sprache festgelegt hat. Diese Nachricht kann geschlossen werden.

#### Abschluss

Sie können nun zum *Administrator-Dashboard* navigieren. Melden Sie sich an, indem Sie *Administrator öffnen* auswählen oder gehen Sie direkt zur Startseite Ihrer Seite, indem Sie *Seite öffnen* wählen.

*Übersetzt von openai.com*

