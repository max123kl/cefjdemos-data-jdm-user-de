<!-- Filename: Security_Checklist/Testing_and_Development / Display title: Sicherheits-Checkliste / Testen und Entwicklung -->

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

## Sicher testen und entwickeln

### Lokal entwickeln, global einsetzen

Eine Webseite sollte zunächst auf einem lokalen Rechner entwickelt und
getestet werden. Die lokale Installation von Joomla! ist nicht so
schwer, wie es vielleicht klingt, und vermittelt wichtige
Grundkenntnisse für Joomla!-Entwickler.

### Eine IDE verwenden

Die Verwendung einer integrierten Entwicklungsumgebung (Integrated
Development Environment, IDE) bietet viele Vorteile. Eine kostenlose
IDE, die von vielen Joomla!-Entwicklern verwendet wird, ist
<a href="https://code.visualstudio.com/" class="external text"
target="_blank" rel="nofollow noreferrer noopener">Visual Studio
Code</a>. Anweisungen zur Installation von VSCode sind unterzu finden.

### Ein Versionierungssystem verwenden

Es sollte möglich sein, mit einem modernen Versionskontrollsystem,
normalerweise
<a href="https://git-scm.com/" class="external text" target="_blank"
rel="nofollow noreferrer noopener">git</a>, zu einer früheren Version
der Website zurückzukehren. Die oben erwähnte Visual Studio Code IDE
enthält Plugins für Git. Dies ermöglicht die Verwendung des Joomla!
Quellcode-Repositorys, das auf
<a href="https://github.com/joomla/joomla-cms/releases"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">GitHub</a> bereitgestellt wird, sowie
aller anderen Projekte auf GitHub, GitLab oder BitBucket (die drei
beliebtesten Git-Versionskontrollsysteme).

### Weitere empfohlene Tools

Eine von der Joomla-Community zusammengestellte Liste von
<a href="http://forum.joomla.org/index.php/topic,25307.0.html"
class="external text" target="_blank" rel="noreferrer noopener">Software
und Tools für Entwickler</a> ist im Joomla!-Forum zu finden..

## Zuerst einen Sicherungsprozess einrichten

### Die wichtigste Regel

**Es muss jederzeit möglich sein, eine Webseite durch regelmäßige
Anwendung eines starken, externen Backup- und
Wiederherstellungsprozesses wieder in einen früheren Zustand zu
versetzen.**

Der Backup- und Wiederherstellungsprozess muss einsatzbereit und
getestet sein, BEVOR die Webseite in Betrieb genommen wird.

Dies ist der beste Weg (und oft auch der einzige), um sich von
unvermeidlichen Katastrophen wie den Folgenden zu erholen:

1.  Eine kompromittierte oder gehackte Seite
2.  Beschädigung der Seite durch eine fehlerhafte Aktualisierung
3.  Hardware-Ausfall, wie z. B. tote Festplatten, Stromausfälle,
    Server-Diebstahl, etc.
4.  Intervention einer Regierungsbehörde (häufiger als oft vermutet)
5.  Die Notwendigkeit, schnell zu einem neuen Server oder
    Hosting-Provider umzuziehen
