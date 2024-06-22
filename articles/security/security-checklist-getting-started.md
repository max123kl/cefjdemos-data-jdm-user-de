<!-- Filename: Security_Checklist/Getting_Started / Display title: Sicherheits-Checkliste / Erste Schritte -->

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

### Sicherheit zählt

Die Sicherheit im Internet ist eine Herausforderung, die sich schnell
verändert, und ist ständigen Bedrohungen ausgesetzt. Es gibt nicht den
einen richtigen Weg, um eine Webseite zu sichern. Sicherheitsmethoden
veralten sehr schnell und unterliegen der schrittweisen Verbesserung und
ständigen Überarbeitung. Alle öffentlich zugänglichen Webseiten sind ein
Ziel für ständige Angriffe. Deshalb sollte ein Webseiten-Admin bereit
und in der Lage sein, für die Verwaltung einer dynamischen, rund um die
Uhr und weltweit zugänglichen, datenbankgesteuerten, interaktiven,
benutzerauthentifizierten Website genügend Zeit aufzubringen. Er muss
die Zeit und die Ressourcen zur Hand haben, um auf neue
Internet-Sicherheitsprobleme entsprechend reagieren zu können.

Die  Top 10 der dümmsten
Administrator-Tricks
ist eine komische und tragische Zusammenfassung der Fehler, die
unbedingt vermieden werden sollten. Es ist nicht nötig, alles auf die
harte Tour zu lernen! Abhängig von der eigenen Erfahrung kann die
Lektüre der Dümmsten Tricks entweder zum Lachen oder zum Weinen
verleiten. Glücklicherweise gibt es einige gut etablierte Prinzipien,
die bei der Sicherung von Joomla-Webseiten helfen können. Die folgenden
Checklisten erklären die wichtigsten bewährten Vorgehensweisen für die
Sicherheit von Joomla.

### Wie diese Dokumente gelesen werden sollten

1.  Nicht alle Techniken sind für jede Erfahrungsstufe geeignet. Es
    sollten diejenigen angewandt werden, die verstanden werden. Zu den
    anderen sollten zusätzliche Informationen eingeholt werden.
2.  Nicht alle Techniken sind für jeden Server geeignet. Wenn ein
    gemeinsam genutzter Server verwendet wird, müssen meist die
    Einstellungen des Hosting-Providers verwendet werden. Ein virtueller
    oder dedizierter Server erlaubt jedoch die Verwendung kreativerer
    Sicherheitstaktiken.
3.  Nicht alle Sicherheitstaktiken sind für alle Versionen von Joomla
    geeignet. Wenn eine Technik nur auf eine Version zutrifft, wird dies
    durch eines der folgenden Symbole angezeigt:
     <img src="https://docs.joomla.org/images/4/43/Compat_icon_1_0.png"
    decoding="async" data-file-width="40" data-file-height="17" width="40"
    height="17" alt="Joomla 1.0" /> <img src="https://docs.joomla.org/images/c/c8/Compat_icon_1_5.png"
    decoding="async" data-file-width="40" data-file-height="17" width="40"
    height="17" alt="Joomla 1.5" /> <img src="https://docs.joomla.org/images/d/da/Compat_icon_1_6.png"
    decoding="async" data-file-width="40" data-file-height="17" width="40"
    height="17" alt="Joomla 1.6" /> <img src="https://docs.joomla.org/images/8/87/Compat_icon_1_7.png"
    decoding="async" data-file-width="40" data-file-height="17" width="40"
    height="17" alt="Joomla 1.7" /> <img src="https://docs.joomla.org/images/5/53/Compat_icon_2_5.png"
    decoding="async" data-file-width="40" data-file-height="17" width="40"
    height="17" alt="Joomla 2.5" /> <img src="https://docs.joomla.org/images/9/9e/Compat_icon_3_0.png"
    decoding="async" data-file-width="40" data-file-height="17" width="40"
    height="17" alt="Joomla 3.0" /> <img src="https://docs.joomla.org/images/d/d6/Compat_icon_3_1.png"
    decoding="async" data-file-width="40" data-file-height="17" width="40"
    height="17" alt="Joomla 3.1" />

### Die wichtigsten Punkte

Diese Checklisten sind lang und werden immer länger, weil das gesamte
Thema sehr komplex und umfangreich ist. Dennoch besteht kein Grund für
Verzweiflung! Hier sind ein paar wesentliche Richtlinien für die
Sicherung jeder Website. Wenn diese befolgt werden, ist die Webseite vor
den meisten Katastrophen geschützt.

1.  **Frühzeitige und regelmäßige Backups**: Es sollte ein regelmäßiger
    Sicherungs- und Wiederherstellungsprozess eingerichtet (und genutzt
    und getestet) werden. Wenn dies richtig gemacht wird, kann die
    Webseite nach fast jeder denkbaren Katastrophe wiederhergestellt
    werden.
2.  **Rechtzeitige und regelmäßige Updates**: Aktualisierungen auf die
    neueste stabile Version von Joomla! und alle installierten
    Erweiterungen von Drittanbietern sollten umgehend durchgeführt
    werden. Dadurch wird sichergestellt, dass die Webseite stets
    geschützt ist, und zwar
    - vor den neuesten Schwachstellen, sobald eine Korrektur
      veröffentlicht wird, und
    - vor den neuesten Angriffsmethoden, sobald eine Verteidigung
      entwickelt wird.
3.  **Verwendung eines sicheren Hosts**: Ein hochwertiger Web-Host
    erspart viel Kummer. Angebote wie "unbegrenzte Bandbreite,
    unbegrenzter Festplattenspeicher, unbegrenzte Datenbanken usw." sind
    zwar verlockend, sollten aber mit Skepsis betrachtet werden.
4.  **Hilfe von der Community**: *Wenn ein Geschäft zu gut ist, um wahr
    zu sein, dann ist es das.* Diese Binsenweisheit sollte nie vergessen
    werden. Es scheint, dass nichts auf der Erde unbegrenzt ist - außer
    vielleicht die Leichtgläubigkeit von Narren und die Gier derer, die
    sie ausbeuten. Daher gilt: Wenn nicht genügend Erfahrung oder Wissen
    auf einem Gebiet vorhanden sind, sollte professionelle Hilfe in
    Anspruch genommen werden. Einer der großen Vorteile von GNU-Software
    ist der kostenlose Benutzer-Support. Dieser kann genutzt werden,
    indem in den Joomla!-Foren Fragen gestellt werden. Dabei sollte das
    am besten geeignete Forum verwendet werden, wie z. B. Installation,
    Migration und Aktualisierung, Administration.

Die hilfreichsten Beiträge im Joomla!-Sicherheitsforum werden zu denhinzugefügt. Viele der Punkte auf dieser Liste werden in den FAQs viel
ausführlicher erklärt.

Für Joomla!-Neulinge eignet sich auch der umfangreiche [Leitfaden für
Joomla!
Einsteiger](https://docs.joomla.org/Beginners "Special:MyLanguage/Beginners"),
der eine Fülle von Tipps und Tricks in einem leicht verständlichen
Format präsentiert. Selbst erfahrene Joomla!isten finden hier großartige
Ideen.

In den
<a href="http://forum.joomla.org" class="external text" target="_blank"
rel="noreferrer noopener">Joomla! Foren</a>, insbesondere im
<a href="http://forum.joomla.org/viewforum.php?f=714"
class="external text" target="_blank" rel="noreferrer noopener">Joomla!
3.x Security Forum</a> und im
<a href="http://forum.joomla.org/viewforum.php?f=621"
class="external text" target="_blank" rel="noreferrer noopener">Joomla!
2.x Security Forum</a>, sind viele weitere Tipps und Hinweise zu
Sicherheitsthemen zu finden..

Um alle Joomla-Sicherheitsankündigungen zu erhalten, sollten die Joomla
Security News abonniert werden. Dafür gibt es mehrere Möglichkeiten:

1.  <a
    href="http://feedburner.google.com/fb/a/mailverify?uri=JoomlaSecurityNews"
    class="external text" target="_blank"
    rel="nofollow noreferrer noopener">Automatische
    E-Mail-Benachrichtigungen</a>
2.  <a href="http://feeds.joomla.org/JoomlaSecurityNews"
    class="external text" target="_blank"
    rel="noreferrer noopener">RSS-Feed</a>.

### Die schlechten Neuigkeiten

1.  **Es gibt keine perfekte Sicherheit im Web!** Oder wie
    Wirtschaftswissenschaftler sagen würden: "Es gibt kein kostenloses
    Mittagessen." Man sollte sich nicht von der preisgekrönten
    Benutzerfreundlichkeit von Joomla täuschen lassen. Es ist nicht
    einfach, im offenen Internet eine sichere Website zu betreiben. Die
    Wahrung einer angemessenen Sicherheit erfordert ein breites und
    ständig wachsendes Spektrum an Fähigkeiten und Kenntnissen, ständige
    Wachsamkeit und einen robusten Sicherungs- und
    Wiederherstellungsprozess.
2.  **Den einen richtigen Weg gibt es nicht!** Aufgrund der Vielfalt und
    Komplexität moderner Web-Systeme lassen sich Sicherheitsprobleme
    nicht mit einfachen, für alle geeigneten Lösungen beheben. Ein
    Webseiten-Admin muss genug über die jeweilige Server-Infrastruktur
    wissen, um angemessene Sicherheitsentscheidungen treffen zu können.
    Starke Sicherheit ist ein bewegliches Ziel. Der Experte von heute
    könnte das Opfer von morgen sein. Willkommen im Spiel...
3.  **Erfahrung kann durch nichts ersetzt werden!** Um eine Website zu
    sichern, müssen echte Erfahrungen gesammelt werden (von denen einige
    bitter sein werden). Alternativ kann die Hilfe von erfahrenen
    Benutzern in Anspruch genommen werden. Oft fehlt die beträchtliche
    Zeit für den Erwerb der Kenntnisse, die für den sicheren Betrieb
    einer Webseite nötig sind. Dann sollte eine Person zu Rate gezogen
    werden, die dies bereits getan hat.

*Tipp*: Die augenzwinkernde Beschreibung der  Top 10 der dümmsten
Administrator-Tricks
zeigt typische Beispiele für das Erlernen von Web-Sicherheit auf die
harte Tour.

### Die guten Neuigkeiten

1.  **Selbst ein Anfänger kann der Menge einen Schritt voraus sein.**
    Die Benutzerforen für viele Systeme sind mit Posts wie
    <a href="http://www.google.com/search?q=Help!+I&#39;ve+been+hacked"
    class="external text" target="_blank"
    rel="nofollow noreferrer noopener">Hilfe! Ich bin gehackt worden</a>
    gefüllt. Diese werden in der Regel von Nutzern gepostet, die sich
    NICHT an die Standard-Sicherheitspraktiken gehalten haben. Wenn
    diese Checkliste durchgearbeitet wird, bevor die eigene Webseite
    angegriffen wird: Herzlichen Glückwunsch, das ist bereits ein großer
    Fortschritt gegenüber der großen Masse!.
2.  **Es ist nicht so schwer, wie es scheint.** Während die ersten
    Webseiten erstellt werden, können die Sicherheitsprobleme
    überwältigend erscheinen. Aber nicht alle Probleme müssen
    gleichzeitig behoben werden. Zunächst sollten die kritischsten
    Probleme ins Auge gefasst werden. Mit steigender Vertrautheit mit
    den
    <a href="http://www.gnu.org" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">GNU</a>-Werkzeugen und
    -Techniken, einschließlich
    <a href="http://www.gnu.org/" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">GNU/Linux</a>,
    <a href="http://www.apache.org" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">Apache</a>,
    <a href="http://www.mysql.com" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">MySQL</a>,
    <a href="http://en.wikipedia.org/wiki/SQL" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">SQL</a>,
    <a href="http://www.php.net" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">PHP</a>,
    <a href="http://en.wikipedia.org/wiki/HTTP" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">HTTP</a>,
    <a href="http://en.wikipedia.org/wiki/CSS" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">CSS</a>,
    <a href="http://en.wikipedia.org/wiki/XML" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">XML</a>,
    <a href="http://en.wikipedia.org/wiki/RSS" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">RSS</a>,
    <a href="http://en.wikipedia.org/wiki/TCP/IP" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">TCP/IP</a>,
    <a href="http://en.wikipedia.org/wiki/FTP" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">FTP</a>,
    <a href="https://git-scm.com/" class="external text" target="_blank"
    rel="nofollow noreferrer noopener">Git</a>,
    <a href="http://en.wikipedia.org/wiki/JavaScript" class="external text"
    target="_blank" rel="nofollow noreferrer noopener">JavaScript</a>,
    und
    <a href="http://www.joomla.org" class="external text" target="_blank"
    rel="noreferrer noopener">Joomla!</a>, können die
    Sicherheitsstrategien weiter verfeinert werden.
3.  **Hilfe ist nur einen Schritt entfernt.** Wenn ein Angriff auf eine
    Webseite vermutet wird, wird **stark davon abgeraten**, dies einfach
    mit allen Einzelheiten in den Joomla! Foren mitzuteilen. Wenn eine
    neue Sicherheitslücke oder eine neue Form des Angriffs vorliegt,
    könnte die Veröffentlichung dieser Informationen andere Webseiten in
    Gefahr bringen. Stattdessen sollten mögliche Sicherheitslücken an
    die
    <a href="http://developer.joomla.org/security" class="external text"
    target="_blank" rel="noreferrer noopener">Joomla! Security Task
    Force</a> gemeldet werden.
