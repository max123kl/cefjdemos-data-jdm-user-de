<!-- Filename: Backup_Basics_for_a_Joomla!_Web_Site / Display title: Backup-Grundlagen für eine Joomla!-Webseite -->

Halte immer eine aktuelle Sicherung deiner Website bereit. Unfälle
können passieren, aber es gibt auch viele andere Gründe, warum es
hilfreich ist, Backup-Dateien bereit zu haben, bevor die Notwendigkeit
auftritt. **Hinweis: Backups sollten nicht verwendet werden, um eine
gehackte Website wiederherzustellen, da der Hack schon einige Zeit auf
der Website gewesen sein und somit Bestandteil des Backups sein
könnte.**

Ursachen für Datenverlust gibt es viele. Joomla!-Webseiten können von
böswilligen Angreifern kompromittiert werden, wenn der
Seiten-Administrator nicht auf die Sicherheit geachtet hat oder in
seltenen Fällen, wenn Hacker die beste Sicherheit umgehen. Joomla! ist
für die Teamarbeit entwickelt worden, und auch gute Autoren können einen
Fehler machen, die die Webseite beschädigt.

Es gibt viele Gründe, warum Webseiten-Administratoren die Webseite auf
einen früheren Zustand zurücksetzen müssen.

Praktiziere beides - Backup und Wiederherstellung. Niemand sollte bis
zum Ernstfall warten, um die Fähigkeiten seiner Werkzeuge zu testen. Oft
passiert es, dass ein leeres Backup erstellt wurde oder es ist
beschädigt oder die Dateien sind nicht dort, wo sie abgelegt sein
sollten. Niemand will ein Schiff, das mit leeren Rettungsbooten sinkt.
Es ist also ratsam, die Leute aus den Rettungsbooten rauszuholen und in
ein funktionierendes System zu wechseln.

Ein Backup ist nicht nur bei Unfällen hilfreich, es kann auch dazu
dienen, die Entwicklung neuer Features mit Hilfe einer gesicherten Kopie
der Webseite durchzuführen. Das Backup und die Wiederherstellung hilft,
den Auftritt mit neuen Anpassungen zu versehen, ohne die veröffentlichte
Webseite zu gefährden. Der Klon kann lokal mit Hilfe eines Test-Servers
erstellt werden oder in irgendeinem anderen Ordner auf dem Webspace, der
die gleichen PHP- und SQL-Versionen unterstützt.

Es kann leicht passieren, die Live-Webseite mit der Test-Webseite zu
verwechseln. Ändere deshalb einfach die Farbe in Deinem Template, um den
Entwickler daran zu erinnern, dass es sich nicht um die öffentliche
Webseite handelt.

## Sicherung einer Joomla Website mit Akeeba (Häufige Methode)

Dies ist die bevorzugte Methode - mit der Erweiterung Akeeba Backup.

- Akeeba-Backup erstellt eine *.jpa*-Datei
- Die *.jpa*-Datei enthält alle Ordner/Dateien und Datenbank Dateien.
- Die *.jpa*-Datei enthält auch ein Installationsprogramm
- Kickstart.php von Akeeba entpackt die *.jpa*-Datei
- Du führst den Installer aus und installierst deine Seite wie bei der
  Joomla-Installation.
- Der Installer ändert die Konfiguration für das Wiederherstellen an
  anderer Stelle und fragt die neuen Datenbankdetails ab.

Akeeba Backup kann vom <a
href="https://extensions.joomla.org/extensions/extension/access-a-security/site-security/akeeba-backup/"
class="external text" target="_blank" rel="noreferrer noopener">Joomla
Erweiterungs-Portal</a> heruntergeladen und installiert werden. Ein Link
mit einer umfangreichen Anleitung ist ebenfalls dort zu finden.

## Zweiteilige Backup-Methode

Es gibt zwei Teile die für eine vollständige Sicherung Deiner
Joomla!-Website notwendig sind. Diese sind:

1.  Die Datenbank-Informationen, die meistens in einer MySQL-Datenbank
    zu finden sind.
2.  Die Dateien und Ordner der Webseite, gehostet wie die meisten
    statischen HTML-Webseiten.

Wenn Du nicht ein Backup Deiner Dateien und der Datenbank hast, ist die
Sicherung unvollständig.

## Datenbank-Backup

Einer der ersten Schritte zum Backup einer Joomla! Webseite ist es, sie
offline zu stellen, das Backup durchzuführen und anschließend wieder
online zu stellen. Die Schritte in
<a href="https://docs.phpmyadmin.net/en/latest/index.html"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">der Dokumentation von phpMyAdmin</a>
lassen diesen sehr wichtigen Schritt aus. Gehe im Backend deiner
Joomla!-Seite zur Registerkarte globale Konfiguration und setze "Website
offline" = ja.

Das wird dann die Datei *configuration.php* im Stammverzeichnis Deiner
Joomla!-Webseite verändern.

Ein Administrator benötigt Zugang zum Kontrollzentrum des
Hosting-Anbieters, um die Datei zu sehen oder er kann die Datei per FTP
herunterladen und ansehen. In der *configuration.php* ist der Name der
Datenbank finden, die zu sichern ist.

Suche nach der Zeile mit dem ähnlichen Code `var $db = 'x1234';` or
`public $db = 'x1234';` Wobei "x1234" der Name der Datenbank ist.

Verwende die Anmeldeinformationen für den Server oder Hosting-Account
und öffne das PhpMyAdmin-Tool. Öffne die Datenbank, suche die Tabelle
mit dem Namen "users" und klicke dann auf das Symbol "Ansicht" um die
Daten in die Tabelle zu sehen.

Du solltest die Namen der Mitarbeiter sehen, die Zugang zu Deiner
Joomla!-Website haben. Diese Ansicht bietet dir die Sicherheit, dass du
zur Sicherung die richtige Datenbank ausgewählt hast.

Klicke auf die Registerkarte "exportieren", dann weiter.

Dein Browser lädt Deine Datenbank in eine SQL-Datei.

Finde heraus, wo der Browser die Datei abgelegt hat, dann verschiebe die
Datei in ein sicheres Laufwerk oder anderen Speicherort.

Server-SQL-Datenbanken können auch ohne PhpMyAdmin gesichert werden,
stattdessen kann man eine SQL-Befehlszeile nutzen. Wenn du weißt, was
hierfür zu tun ist, wird wahrscheinlich diese Dokumentation nicht
notwendig sein.

Es wird empfohlen, die Datenbank mindestens zweimal pro Woche oder sogar
täglich (und mehr) zu sichern, wenn du eine aktive Webseite hast.

## Backup des Dateisystems

Fahre nun mit offline geschalteter Webseite fort, wie oben beschrieben.
Deine Joomla! Ordner und Dateien können nun mit einem FTP-Programm oder
über den Dateimanager des Webhosters gesichert werden. Beide Optionen
funktionieren gleich gut.

FTP-Programme verschieben tausende Joomla!-Dateien, benötigen aber mehr
Zeit. Der FTP-Prozess kann langsam sein und möglicherweise unterbrochen
werden. Die meisten Webhoster besitzen einen Dateimanager im
Kontrollzentrum für tausende Dateien in einem Ordner. Damit lässt sich
sehr schnell eine zip-Datei erstellen.

Das bedeutet, dass deine Webseite für eine kürzere Zeit offline ist und
du nur eine zip-Datei zu sichern hast. Gehe ins Kundencenter deines
Webhosters und suche nach dem Dateimanager oder Dateiexplorer.

Wenn du den Dateimanager deines Webhosters benutzt, wähle den Ordner und
erstelle eine zip-Datei. Lade die zip-Datei lokal herunter und entpacke
diese auf deinem Rechner, um zu sehen, welche Dateien enthalten sind.
Der Entpacken-Schritt ist auch bei einer Wiederherstellung der Webseite
nötig.

Das Backup der Joomla!-Dateien ist nicht anders wie die Sicherung einer
statischen HTML-Webseite. Lade alle Dateien und Ordner innerhalb des
Joomla!-Ordners auf deinen lokalen PC herunter. Vergewissere dich, dass
die Datei- und Ordnerstruktur die gleiche bleibt wie bei deiner
online-Webseite. Wenn du die Dateien wiederherstellen willst, lade die
Dateien mit einem FTP-Programm auf einen neuen Server oder einem neuen
Ordner in deinem Webspace hoch.

**Sobald du die Dateien mittels zip oder FTP heruntergeladen hast,
schalte den Status deiner Webseite im Backend wieder auf online.**

## Weitere Dokumentationen zur Sicherung

Die meisten Administratoren einer Joomla!-Webseite haben Zugriff auf die
MySQL-Daten mithilfe der grafischen Benutzeroberfläche PhpMyAdmin, siehe
<a
href="https://phpmyadmin.readthedocs.org/de/latest/faq.html#how-can-i-backup-my-database-or-table"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Wie kann ich meine Datenbank oder
Tabelle sichern?</a> für mehr Informationen.

Es gibt mehrere automatisierte Backup-Erweiterungen für Joomla! im
<a href="http://extensions.joomla.org" class="external text"
target="_blank" rel="noreferrer noopener">Verzeichnis für
Joomla!-Erweiterungen</a>. Hier ist ein Link zu den <a
href="http://extensions.joomla.org/extensions/extension?searchall=backup&amp;controller=filter"
class="external text" target="_blank"
rel="noreferrer noopener">Backup-Erweiterungen für Joomla</a>.

Wenn die Server sich im gleichen Gebäude wie die Mitarbeiter befinden,
sollten die Web-Administratoren besonders vorsichtig sein und die
Backup-Dateien in einem anderen Gebäude sichern. Feuer -, Diebstahl -,
Wasser - oder sonstige Schäden können die online-Webseite UND gesicherte
Dateien vernichten. Der Web-Administrator sollte die Datenbank und
Dateien regelmäßig auf CD oder einer externen Festplatte speichern.

## Spezielle Hinweise

### 2FA (Zwei-Faktor-Authentifizierung)

Wenn du die Zwei-Faktor-Authentifizierung (seit Aug 2014 verfügbar)
nutzt und du aus der Webseite ausgesperrt bist, kannst du den Ordner
plugins/twofactorauth zu twofactorauth.BAK umbenennen und dich im
Backend anmelden. Dann deaktiviere alle Plugins unter der
"twofactorauth" Typen-Gruppe. Benenne anschließend den Ordner
twofactorauth.BAK wieder zu twofactorauth um.

- Siehe auch:  Tutorial zur
  Zwei-Faktor-Authentifizierung
