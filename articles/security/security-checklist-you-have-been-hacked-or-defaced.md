<!-- Filename: Security_Checklist/You_have_been_hacked_or_defaced / Display title: Sicherheits-Checkliste / Webseite wurde gehackt oder verändert -->

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

## Die Webseite wurde gehackt oder verändert?

Bevor ein Beitrag im
<a href="https://forum.joomla.org/viewforum.php?f=714" class="extiw"
title="jforum:714">Joomla! Sicherheitsforum</a> gepostet wird, sollte
diese <a href="http://forum.joomla.org/viewtopic.php?f=432&amp;t=475313"
class="external text" target="_blank"
rel="noreferrer noopener">Zusammenfassung der Checkliste gelesen</a> und
dann als Vorlage für den Beitrag verwendet werden..

### Liste der Maßnahmen

- Die Webseite  offline
  nehmen
  (**Wir empfehlen die htaccess-Methode**)
- Das <a href="https://github.com/ForumPostAssistant/FPA/zipball/en-GB"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Forum Post Assistant and Security
  Tool (FPA)</a> starten. Die einfachen Anweisungen sind
  <a href="http://forum.joomla.org/viewtopic.php?f=621&amp;t=582860"
  class="external text" target="_blank" rel="noreferrer noopener">hier
  verfügbar</a>. Ausführlichere Anweisungen sind im Download-Paket
  enthalten. Dieses Paket muss entpackt und die Datei fpa-de.php in das
  Joomla-Stammverzeichnis des Servers hochgeladen werden. Der FPA ist
  auch in einem
  <a href="https://github.com/ForumPostAssistant/FPA/tarball/en-GB"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">tar.gz-Paket erhältlich</a>, falls
  ein Paket im Unix-Stil gewünscht oder benötigt wird. Die Datei
  fpa-de.php aus dem Paket muss in das Joomla-Stammverzeichnis des
  Servers hochgeladen werden.
- Alle Rechner mit FTP-, Joomla-Super-Admin- und Joomla-Admin-Zugang
  nach Malware, Viren, Trojanern, Spyware usw. durchsuchen (siehe
  [Lokale Sicherheit](#Local_Security) weiter unten)
- Sicherstellen, dass die neueste Version von
  <a href="http://www.joomla.org/download.html" class="external text"
  target="_blank" rel="noreferrer noopener">Joomla</a> für die auf der
  Website verwendete Joomla-Serie verwendet wird. (siehe unten:
  [Inkompatible Versionen](#incompatible_versions))
- Den **Hosting-Provider benachrichtigen** und mit ihm zusammenarbeiten,
  um die Webseite zu bereinigen und sicherzustellen, dass es keine
  Hintertüren zu Ihrer Website gibt.
- Die
  <a href="http://vel.joomla.org/" class="external text" target="_blank"
  rel="noreferrer noopener">Liste der anfälligen Erweiterungen</a>
  überprüfen, um festzustellen, ob anfällige Erweiterungen installiert
  sind. Diese sollten nicht länger verwendet werden. Ein Anhaltspunkt
  für angegriffene Erweiterungen ist die Protokolldatei. Hier ist ein
  Beispiel dafür, wonach gesucht werden sollte:
    //administrator/components/com_extension/admin.extension.php?mosConfig.absolute.path=http:

oder

    ../../../../../../../../../../../../../../../../proc/self/environ

- Die
  Sicherheits-Checkliste
  überprüfen, um sicherzustellen, dass alle Schritte durchlaufen wurden
  (bitte beachten, dass einige Schritte optional sind, aber trotzdem
  überprüft werden sollten).
- **Alle Passwörter ändern** und wenn möglich auch die Benutzernamen für
  die Admin-Oberfläche des Hosting-Providers, mysql, FTP,  Joomla! Super
  Admin
  und Joomla! Admin Passwort.Diese sollten häufig geändert werden.
  Passwörter sollten aus mindestens 12 gemischten alphanumerischen
  Zeichen bestehen und keine gemeinsamen Wortphrasen enthalten.
- Der Standard-Admin-Benutzer sollte nicht verwendet, sondern
  deaktiviert werden. Wenn das Admin-Passwort zugesetzt werden muss,
  sollten  diese
  Anweisungen
  befolgt werden.
- Alle Templates und Dateien **löschen und durch saubere Kopien
  ersetzen**
- Alle .pdf-, Bild- und Fotodateien auf Exploits **überprüfen und/oder
  ersetzen**. Alle verdächtigen Dateien löschen.
- Server-Protokolle auf IPs überprüfen, die verdächtige Dateien aufrufen
  oder versuchen, POST-Befehle an Dateien ohne Formulare zu senden
- Korrekte Berechtigungen für Dateien und Verzeichnisse verwenden. Sie
  sollten **niemals 777<sup>[\[1\]](#cite_note-1)</sup> sein. Ideal ist
  644 für Dateien und 755 für Ordner**.
- <a
  href="http://docs.cpanel.net/twiki/bin/view/AllDocumentation/CpanelDocs/AnonymousFTP"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">anonymes</a> FTP deaktivieren

## Chmod und Cron

WENN Zugriffsrechte für SSH (secure shell) über putty gesetzt sind,
können die Berechtigungen für Dateien und Verzeichnisse mit chmod
geändert werden. Wenn kein Shell-Zugriff vorhanden ist, können die
Befehle über <a href="http://de.wikipedia.org/wiki/cron" class="extiw"
title="de.wp:cron">Cron</a> ausgeführt werde, indem ein temporärer
Cron-Job eingerichtet wird. Der Befehl kann kopiert und in einen
Cron-Job eingefügt werden. Der Job sollte etwa 2 Minuten nach dem
Speichern des Jobs ausgeführt werden. Bei Verwendung des Befehls per
putty oder in einem Cron-Job wird für optimale Ergebnisse die Verwendung
des vollständigen physischen Pfads zu public_html empfohlen.

Für Dateien wird verwendet:

    find /home/xxxxxx/domains/xxxxxxx.com/public_html -type f -exec chmod 644 {} \;

und für Order wird verwendet:

    find /home/xxxxxx/domains/xxxxxxx.com/public_html -type d -exec chmod 755 {} \;

### Überwachung von Veränderungen der Dateien

Um das System auf aktuelle Dateiänderungen zu prüfen, können diese
Befehle von putty (SSH - secure shell) oder über einen Cron-Job
verwendet werden. Wenn der Befehl über einen Cron-Job ausgeführt wird,
kann er so eingestellt werden, dass er mehrmals täglich auf geänderte
Dateien prüft. Die Ergebnisse werden an den Inhaber des Domain-Kontos
gesendet und zeigen den Zeit-/Datumsstempel für alle geänderten Dateien
an. Bei Verwendung des Befehls per putty oder einem cron-Job wird für
optimale Ergebnisse die Verwendung des vollständigen physischen Pfads zu
public_html empfohlen.

    find /home/xxxxxx/domains/xxxxxxx.com/public_html -type f -ctime -1 -exec ls -ls {} \;

Es sollte beachtet werden, dass sich die Dateien der Webseiten in einem
Verzeichnis namens public_html, httpdocs, www oder o. ä. befinden
können, und dass der physische Pfad sich von den Beispielen
unterscheiden kann. Er sollte daher entsprechend angepasst werden.

## 777-Dateiberechtigungen

Wenn der verwendete Server 777-Berechtigungen benötigt, damit Joomla
korrekt funktioniert, dann sollte darauf bestanden werden, dass **die
Seite auf einen anderen Server** mit php als cgi und suphp und aktueller
serverseitiger Software (apache, php usw.) auf Ihrem bestehenden Host
umgezogen wird. Falls nötig sollte ein anderer Hosting-Provider gesucht
werden.

Um Verzeichnisse zu schützen, für deren Ausführung 777-Berechtigungen
erforderlich sind oder wenn diese Berechtigungen als Standard im
Bilder/Medien-Ordner festgelegt sind, kann dieser Code in einer
.htaccess-Datei innerhalb des Ordners hilfreich sein:

    # Sicherung des Verzeichnisses durch Deaktivierung der Skript-Ausführung
    AddHandler cgi-script .php .pl .py .jsp .asp .htm .shtml .sh .cgi
    Options -ExecCGI

especially in your images folder

- Es muss sichergestellt werden, dass sich dies in einer htaccess-Datei
  in einem Verzeichnis befindet, das keine Skripte ausführt oder die
  Erweiterungen wie erforderlich entfernt werden

Es ist wichtig zu wissen, ob der Hosting-Provider den Server, auf dem
die Webseite liegt, absichtlich gesichert hat und dass er **oder der
Seiten-Inhaber** regelmäßige (wöchentliche) Sicherheitsupdates
durchführen, um den Server auf dem neuesten Stand zu halten. Es sollte
auch überprüft werden, ob eine Jail-Shell vorhanden ist. Als Faustregel
gilt: Je preiswerter das Hosting ist, desto weniger kann vom Provider
erwartet werden.

## Ein sicherer Weg aus der Katastrophe

- Sicherung der Datei configuration.php und der Bilder und persönlichen
  Dateien nacheinander (nicht den gesamten Ordner, da er unerwünschte
  Dateien enthalten könnte).
- Löschung des gesamten Ordners, in dem Joomla! installiert ist
- Upload eines neuen sauberen Pakets der neuesten Version von Joomla
  Joomla 2.5.x oder Joomla 3.x (empfohlen), abzüglich des
  Installationsordners<sup>[\[2\]](#cite_note-2)</sup>
- Erneuter Upload der configuration.php & der Bilder
- Upload/Neuinstallation der neuesten Versionen der verwendeten
  Erweiterungen und Templates (noch besser ist die Verwendung von
  originalen sauberen Kopien, um sicherzustellen, dass der
  Hacker/Defacer keine Shell-Skriptdateien auf der Webseite hinterlassen
  hat)

Zu diesem Zweck wird die Webseite für etwa 15 Minuten vom Netz genommen.
Das Aufspüren von gehacktem oder verändertem html kann Stunden oder
sogar länger dauern.

### Lokale Sicherheit

- FTP-Zugangsdaten nicht im FTP-Programm speichern
  - Ein Passwort-Manager verwenden, wie etwa das kostenlose
    <a href="http://keepass.info/" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">keepass</a>
- Überprüfung von allen Rechnern mit FTP-, Joomla-Super-Admin- und
  Joomla-Admin-Zugang auf Malware, Viren, Trojaner, Spyware usw.
- Dafür können z. B. die folgenden Programme verwendet werden:
  - <a href="http://www.eset.com/" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">ENOD32</a> von eSet
  - <a href="http://www.safer-networking.org/" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">Spybot Search and
    Destroy</a>
  - <a href="http://www.malwarebytes.org/" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">Malwarebytes</a>
  - <a href="http://www.microsoft.com/security/" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">Microsoft Malicious
    Software Removal Tool</a>
  - <a
    href="http://www.free-av.com/de/tools/12/avira_antivir_rescue_system.html"
    class="external text" target="_blank"
    rel="nofollow noreferrer noopener">Linux AntiVirus Boot-CD</a>
  - <a href="http://www.javacoolsoftware.com/spywareblaster.html"
    class="external text" target="_blank"
    rel="nofollow noreferrer noopener">Spyware Blaster</a>
  - <a href="http://www.siteadvisor.com/" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">Siteadvisor</a>
- Unter Umständen Verwendung der
  <a href="http://ubcd4win.com/" class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Ultimate Boot-CD für Windows</a>,
  die für die Reparatur, Wiederherstellung oder Diagnose fast aller
  Heimcomputerprobleme verwendet werden kann

### Weitere Überlegungen

- Den Standard-Tabellenpräfix jos\_ nicht verwenden und wenn möglich
  Ein-Klick-Installationen vermeiden
- Den <a href="http://feeds.joomla.org/JoomlaSecurityNews?format=xml"
  class="external text" target="_blank" rel="noreferrer noopener">Joomla
  Sicherheits-Newsfeed</a> im Kontrollzetrum als Modul an oberster
  Stelle anzeigen lassen. <a
  href="https://docs.joomla.org/Screen.modulesadministrator.edit.15#Feed_Display"
  class="mw-redirect" title="Screen.modulesadministrator.edit.15">Den
  Sicherheits-Newsfeed einrichten</a>
  - <a
    href="https://docs.joomla.org/Screen.modulesadministrator.edit.15#How_to_access"
    class="mw-redirect" title="Screen.modulesadministrator.edit.15">Das
    Admin-Modul Feed-Anzeige</a> sollte, wenn noch nicht geschehen,
    hinzugefügt und an die erste Stelle im Backend-Kontrollzentrum
    gesetzt werden..
- Eventuell eine
  <a href="http://forum.joomla.org/viewtopic.php?p=1568940#p1568940"
  class="external text" target="_blank"
  rel="noreferrer noopener">Bot-Blockliste</a> zur .htaccess-Datei
  hinzufügen
- Wenn möglich,
  <a href="http://en.wikipedia.org/wiki/SSH_file_transfer_protocol"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">sFTP</a> statt FTP verwenden
- <a
  href="http://en.wikipedia.org/wiki/File_Transfer_Protocol#Anonymous_FTP"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Anonymes FTP</a> unter keinen
  Umständen aktivieren oder verwenden
- Einen Server verwenden, der
  <a href="http://www.modsecurity.org/" class="external text"
  target="_blank" rel="nofollow noreferrer noopener">mod_security</a>
  korrekt installiert hat
- Überprüfung auf hinzugefügte Sub-Domains und/oder Verzeichnisse
- Überprüfung auf
  <a href="http://en.wikipedia.org/wiki/Common_Gateway_Interface"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">CGI-Skripte</a>
- Überprüfung auf
  <a href="http://de.wikipedia.org/wiki/Cron" class="extiw"
  title="de.wp:Cron">Cron-Jobs</a>, die nicht vom Administrator
  eingerichtet wurden
- Download und Überprüfung der primären Zugriffs- und Fehlerprotokolle
  <sup>[\[3\]](#cite_note-3)</sup>
- Ablehnung aller IPs, die von der Webseite blockiert werden, aber zu
  einer Proxy-Seite gehören könnten
    Wenn die Webseite in der Vergangenheit bereits gehackt und keine vollständige Bereinigung der Webseite durchgeführt wurde, um vorhandene (auch versteckte) Hacks zu entfernen, können diese eine Hintertür für eine erneute Infektion hinterlassen.

- Eventuell Entfernung von "<a
  href="https://docs.joomla.org/How_do_you_remove_or_change_the_%22Welcome_to_the_Frontpage%22_title%3F"
  class="mw-redirect"
  title="How do you remove or change the &quot;Welcome to the Frontpage&quot; title?">Willkommen
  auf der Frontpage</a>", um <a
  href="http://www.google.co.uk/search?q=intext%3A+welcome+to+the+front+page+joomla&amp;"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Suchmaschinen-Attacken</a> zu
  verhindern
- Unbenutzte oder angreifbare Erweiterungen nicht einfach nicht
  veröffentlichen, sondern vollständig entfernen/deinstallieren. [Die
  Nichtveröffentlichung einer anfälligen Erweiterung bietet keinen
  Schutz!](https://docs.joomla.org/Why_isn%27t_un-publishing_a_vulnerable_extension_enough_to_protect_your_site%3F "Why isn't un-publishing a vulnerable extension enough to protect your site?").

### Bösartiger Code oder seltsame Links auf der Webseite

Es sollte überprüft werden, ob die originale Template-Datei
<a href="http://forum.joomla.org/viewtopic.php?f=432&amp;t=411735"
class="external text" target="_blank"
rel="noreferrer noopener">unerwünschten Code/bösartiges Javascript</a>
enthält oder ob ein kostenpflichtiges Template von einer nicht
vertrauenswürdigen Quelle, z. B. von File-Sharing-Sites, heruntergeladen
wurde

**<a href="http://www.iss.net/threats/gumblar.html" class="external text"
target="_blank" rel="nofollow noreferrer noopener">Gumblar</a>**
verwendet keine bestimmte Skript-Sicherheitslücke. Dieses Skript wird in
jede Seite auf einer Webseite injiziert. Es ist vorstellbar, wenn auch
nicht bestätigt, das es bei Bearbeitung und Speicherung der infizierten
Seite auch in die Datenbank eingeschleust wird. Das Skript ändert sich
bei jedem Zugriff. Es wurde in phpBB-, SMF- und vBulletin-Foren, in
WordPress 2.7.1-Blogs und auf proprietären PHP-Seites gefunden. Das
Skript beginnt mit *(function(*, hat keinen Namen und ist verschlüsselt.
Eine verbreitete Gumblar-Version beschädigt Webseiten aufgrund eines
Fehlers im Skript.

**iFrames**

Bei den jüngsten Iframe-Exploits wurde der bösartige Code nur in Dateien
mit den gängigsten Dateinamen (z. B. index.html, index.php usw.)
eingeschleust. Siehe auch
<a href="http://forum.joomla.org/viewtopic.php?f=432&amp;t=411735"
class="external text" target="_blank" rel="noreferrer noopener">Sticky
im zugehörigen Forum</a>

### Mitwirkende & Edition

<a
href="http://forum.joomla.org/memberlist.php?mode=viewprofile&amp;u=28000"
class="external text" target="_blank"
rel="noreferrer noopener">mandville</a> <a
href="http://forum.joomla.org/memberlist.php?mode=viewprofile&amp;u=67439"
class="external text" target="_blank"
rel="noreferrer noopener">PhilD</a> <a
href="http://forum.joomla.org/memberlist.php?mode=viewprofile&amp;u=3701"
class="external text" target="_blank"
rel="noreferrer noopener">fw116</a> <a
href="http://forum.joomla.org/memberlist.php?mode=viewprofile&amp;u=322239"
class="external text" target="_blank"
rel="noreferrer noopener">JeffChannell</a> <a
href="http://forum.joomla.org/memberlist.php?mode=viewprofile&amp;u=339316"
class="external text" target="_blank"
rel="noreferrer noopener">dynamicnet</a>

## Referenzen

1.  <span id="cite_note-1">[↑](#cite_ref-1) Berechtigungen sollten
    niemals auf 777 gesetzt sein</span>
2.  <span id="cite_note-2">[↑](#cite_ref-2) Inkompatible
    Versionen</span>
3.  <span id="cite_note-3">[↑](#cite_ref-3) primäre Zugriffs- und
    Fehlerprotokolle</span>

Wenn der Hosting-Provider PHP als Apache-Modul ausführt, wird es als
Benutzer/Gruppe des Webservers ausgeführt, was normalerweise "nobody",
"httpd" oder "apache" ist. In diesem Modus benötigen Dateien oder
Verzeichnisse, in die php-Skripte schreiben sollen, 777-Rechte
(Lesen/Schreiben/Ausführen auf Benutzer-/Gruppen-/Public-Ebene), wenn
der Besitzer der Dateien und Verzeichnisse nicht Chown (Besitzer
wechseln) des Benutzers ist. Ein solches Szenario ist vom
Sicherheitsstandpunkt aus absolut inakzeptabel, da '777' nicht nur dem
Webserver, sondern auch jedem anderen erlaubt, die Datei zu lesen oder
zu überschreiben. Wenn ein Provider nicht in der Lage ist, dies zu
ändern, sollte man unbedingt einen Wechsel des Hosting-Anbieters in
Betracht ziehen!

**Logs** Die Raw-Access-Protokolle sollten im Kontrollpanel überprüft
werden können.

Raw-Access-Protokolle ermöglichen es, ohne die Verwendung von Grafiken,
Diagrammen oder anderen Darstellungen zu sehen, wer auf eine Webseite
zugegriffen hat. In cPanel kann zum Beispiel das Menü Raw Access Logs
verwendet werden, um eine gezippte Version des Server-Zugriffsprotokolls
für die Webseite herunterzuladen. Dies kann sehr nützlich sein, wenn
schnell überprüft werden soll, wer auf die Webseite zugreift. Viele
vergessen, dass dies durch den Benutzer des Accounts aktiviert werden
muss und nicht automatisch bei der Erstellung eines Hosting-Accounts im
cPanel aktiviert wird!

**Inkompatible Versionen**

Dieses Dokument gilt für alle Versionen von Joomla. Für die Reparatur
einer Webseite sollte stets die neueste Version von Joomla verwendet
werden, die mit der Version der bestehenden Joomla-Webseite kompatibel
ist. Einige Versions-Upgrades erfordern eine  Migration der
Webseite
und machen die Joomla-Website unbrauchbar, wenn sie verwendet werden, um
eine frühere Version von Joomla bei der Reparatur einer gehackten
Webseite zu ersetzen. Zum Beispiel: Eine auf 1.5.xx basierende Website
kann nicht durch die Joomla-Version 2.5.xx ersetzt werden. Dies würde
die Website unbrauchbar machen und könnte außerdem zu einem Datenverlust
führen.
