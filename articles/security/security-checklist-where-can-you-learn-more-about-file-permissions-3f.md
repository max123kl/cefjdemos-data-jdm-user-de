<!-- Filename: Security_Checklist/Where_can_you_learn_more_about_file_permissions%3F / Display title: Sicherheits-Checkliste / Wo kann ich mehr über Datei-Berechtigungen lernen? -->

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

Ausführlichere Hintergrundinformationen darüber, was Dateiberechtigungen
sind, sind zu finden im Wikipedia-Artikel über:
<a href="https://en.wikipedia.org/wiki/Filesystem_permissions"
class="extiw"
title="wikipedia:Filesystem permissions">Dateisystem-Berechtigungen</a>

Die meisten aktuellen Dateisysteme verfügen heute über Methoden zur
Verwaltung von Berechtigungen oder Zugriffsrechten für bestimmte
Benutzer und Benutzergruppen. Diese Berechtigungen steuern die Fähigkeit
der Benutzer, den Inhalt der Dateien und/oder des Dateiverzeichnisses
(Ordners) anzuzeigen und/oder Änderungen daran vorzunehmen. In einem
Unix/Linux-Server sind die Berechtigungen nach den folgenden 3
Bezeichnungen aufgeschlüsselt:

    r = Leseberechtigungen (die Fähigkeit, die Datei/Dateien in einem Verzeichnis anzuzeigen)
    w = Schreibberechtigungen (die Fähigkeit, in die Datei/Dateien in einem Verzeichnis zu schreiben)
    x = Ausführungsberechtigungen (die Fähigkeit, die Datei/Dateien in einem Verzeichnis auszuführen)

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Warning!

Die Anwendung von Datei- und Verzeichnisberechtigungen und deren
Kontrolle hängt vom Betriebssystem des Servers ab und kann komplex sein.
Mehr Informationen sind unter  empfohlene Berechtigungseinstellungen für
Joomla!
und  schlechte
Server-Berechtigungseinstellungen
zu finden.

Mehr über Berechtigungen und wie sie über den entsprechenden Link zum
richtigen Serverbetriebssystem oder zur richtigen Serverkonfiguration
geändert werden können:

-  Wie funktionieren
  UNIX-Dateiberechtigungen?
-  Wie funktiionieren
  phpSuExec-Dateiberechtigungen?

Auf Microsoft Windows basierende Server, IIS(Internet Information
Server) und PWS (Personal WebServer)

-  Wie funktionieren
  Windows-Dateiberechtigungen?
