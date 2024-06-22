<!-- Filename: Enabling_HTTPS_on_your_site / Display title: HTTPS der Webseite aktivieren -->

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

## Was ist SSL/TLS?

Transport Layer Security (TLS) ist der Nachfolger von Secure Sockets
Layer (SSL) - obwohl es in Blogbeiträgen oft immer noch als SSL
bezeichnet wird. Vielen ist beim Surfen im Internet sicher schon einmal
das Schlosszeichen neben der URL aufgefallen (abhängig vom verwendeten
Browser). Das bedeutet, dass alle Daten verschlüsselt an diese Webseite
gesendet werden. Daher kann jemand, der ein Netzwerk (oder ähnliches)
gehackt hat und Anfragen abfangen kann, keine der Daten einsehen - er
kann nur sehen, auf welche URLs zugegriffen wird.

## Warum ist die Verwendung von TLS wichtig?

Google (und die meisten anderen Suchmaschinen) behandeln Webseiten, die
https verwenden, inzwischen bevorzugt<sup>[\[1\]](#cite_note-1)</sup>.
Darüber hinaus weisen viele Browser die Benutzer darauf hin, wenn eine
Webseite mit einem Formular (z. B. ein Anmelde- oder Kontaktformular)
kein https verwendet<sup>[\[2\]](#cite_note-2)</sup>.

## Wie richte ich TLS ein?

Die Einrichtung des Zertifikats sollte der Hosting-Provider übernehmen.

Welches Zertifikat verwendet werden muss, hängt von den auf der Webseite
erforderlichen Sicherheitsvorkehrungen ab. Wenn darüber keine
Informationen vorliegen, dann ist wahrscheinlich die billigste und
einfachste Option die Verwendung von
<a href="https://letsencrypt.org/" class="external text" target="_blank"
rel="nofollow noreferrer noopener">Let's Encrypt</a>. Es ist kostenlos
und kann je nach Hosting-Provider oft direkt vom cpanel- oder
plesk-Hosting-Dashboard aus konfiguriert werden.

Ein gekauftes Dedicated IP- und SSL-Zertifikat sollte vom
Hosting-Provider eingerichtet werden. Er wird es signieren lassen und am
richtigen Ort installieren.

## Wie leite ich den Traffic meiner Webseite über https um?

### In Joomla

Der einfachste Weg zur Erzwingung von https-Traffic ist es, dies
innerhalb von Joomla zu tun. In der Globalen Konfiguration gibt es eine
"HTTPS erzwingen"-Option, mit der HTTPS entweder nur im
Administratorbereich oder für die gesamte Site erzwungen werden kann.
Meist wird Letzteres der Fall sein.

<img
src="https://docs.joomla.org/images/thumb/3/36/Enable_HTTPS_In_Global_Config-de.png/800px-Enable_HTTPS_In_Global_Config-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/3/36/Enable_HTTPS_In_Global_Config-de.png 1.5x"
data-file-width="1109" data-file-height="607" width="800" height="438"
alt="Image Showing the Force HTTPS option in the Joomla 3.x default backend template" />

### In der Datei .htaccess

    RewriteEngine on
    RewriteCond %{SERVER_PORT} !^443$
    RewriteRule .* https://%{HTTP_HOST}%{REQUEST_URI} [QSA,R=301,L]

    Redirect permanent / https://www.yourdomainname.com

#### Komplexere Beispiele in der .htaccess

Um beispielsweise auf einer Seite, die 'abc/def' oder 'ghi' in der URL
hat, von HTTP auf HTTPS umzuschalten, wird folgendes hinzugefügt:

Code:

    RewriteCond %{HTTPS} off
    RewriteRule ^(abc/def|ghi)(.*)/?$ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,NC,L]

... und um auf jeder Seite, die 'home' oder 'help' in der URL hat, von
HTTPS zurück zu HTTP zu wechseln:

Code:

    RewriteCond %{HTTPS} on
    RewriteRule ^(home|help)(.*)/?$ http://%{HTTP_HOST}%{REQUEST_URI} [R=301,NC,L]

Wenn SSL für einen bestimmten Ordner erzwungen werden soll, kann der
untenstehende Code in eine .htaccess-Datei eingefügt werden, die sich in
diesem bestimmten Ordner befindet:

Code:

    RewriteEngine On 
    RewriteCond %{REQUEST_URI} folder 
    RewriteRule ^(.*)$ https://www.example.com/folder/$1 [R,L]

Die Ordnerreferenz muss auf den tatsächlichen Ordnernamen geändert
werden. Außerdem sollte sichergestellt werden, dass
www.example.com/folder durch den tatsächlichen Domainnamen und Ordner
ersetzen, für den SSL erzwungen werden soll.

1.  <span id="cite_note-1">[↑](#cite_ref-1) <a
    href="https://webmasters.googleblog.com/2014/08/https-as-ranking-signal.html"
    class="external free" target="_blank"
    rel="nofollow noreferrer noopener">https://webmasters.googleblog.com/2014/08/https-as-ranking-signal.html</a></span>
2.  <span id="cite_note-2">[↑](#cite_ref-2) <a
    href="https://www.blog.google/products/chrome/milestone-chrome-security-marking-http-not-secure/"
    class="external free" target="_blank"
    rel="nofollow noreferrer noopener">https://www.blog.google/products/chrome/milestone-chrome-security-marking-http-not-secure/</a></span>
