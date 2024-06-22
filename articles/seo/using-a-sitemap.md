<!-- Filename: Using_A_Sitemap / Display title: Verwendung einer Sitemap -->

## Verwendung einer Sitemap

Suchmaschinen finden in der Regel Deine Seiten durch Links die von
anderen Seiten im Internet auf Deine Seite verweisen. Eine gute Maßnahme
ist es, eine Sitemap zu erstellen, die den 'Bots' eine Auflistung der
Unterseiten bietet - wie eine Art Karte, um alle Inhalte der Website zu
finden.  
Sitemaps sind nicht nur wichtig für die Suchmaschinen, sie helfen auch
Besuchern mit Behinderungen, sich durch die Webseitenstruktur zu
navigieren. Oft ist die Navigation über Menüs zu schwierig und Sitemaps
bieten eine leicht zugängliche Schnittstelle für Hilfsprogramme.
<a href="https://www.w3.org/TR/WCAG20-TECHS/G63.html"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">W3C Working Group Note on
Sitemaps</a>  

Eine Sitemap dient mehreren Zwecken:

- Bietet eine strukturierte Liste mit einer Übersicht aller Inhalte der
  Website
- Bietet dem Besucher schnell einen Überblick über die Struktur der
  Website
- Bietet eine alternative Möglichkeit zur Navigation durch die Website,
  ohne komplexe Menü-Strukturen nutzen zu müssen
- Bietet Suchmaschinen die Möglichkeit nach Inhalten zu suchen, die
  möglicherweise nicht durch das Menü erreichbar sind (z.B.
  Landingpages)

### XML-Sitemap Typen

Es ist auch möglich, XML-Sitemaps für bestimmte Arten von Informationen
anzubieten, einschließlich:

- Video - <a href="https://support.google.com/webmasters/answer/80471"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Google-Search Console Hilfe
  Video-Sitemaps</a>
- Bilder - <a
  href="https://support.google.com/webmasters/answer/answer.py?answer=178636"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Google-Search-Console Hilfe
  Bilder-Sitemaps</a>
- News -
  <a href="https://support.google.com/news/publisher/answer/75717"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Google News-Hilfe Überblick über
  News-Sitemaps</a>
- International - <a
  href="https://support.google.com/webmasters/answer/2620865?hl=en&amp;ref_topic=2370587"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Google-Search-Console Hilfe
  Internationale Sitemaps</a>

Diese Sitemap-Spezialisten ermöglichen die Bereitstellung von
Informationen in Bezug auf die spezifischen Medien-Typen - zum Beispiel
mit einer Video-XML-Sitemap können Angaben über die Laufzeit, Kategorie
und die Familienfreundlichkeit angegeben werden; mit Bilder-Sitemaps
können der Gegenstand des Bildes, seine Lizenz für die Verwendung und
die Art des Bildes angegeben werden.

### Erstellung einer Sitemap

Auf einer statischen Website ist das Erstellen einer Sitemap einfach.
Man erstellt manuell eine XML-Datei mit den entsprechenden Standards und
speichert diese als XML-Datei. Bei einer dynamischen Website, wo sich
der Inhalt regelmäßig ändert ist das keine Option - sonst muss die
Sitemap nach jeder Änderung der Inhalte manuell aktualisiert werden!

Aus diesem Grund gibt es mehrere Sitemap-Erweiterungen auf der Joomla
Extensions Directory (JED) <a
href="https://extensions.joomla.org/category/structure-a-navigation/site-map"
class="external text" target="_blank" rel="noreferrer noopener">Sitemap
Kategorie im Joomla Extensions Directory</a>, die XML-Sitemaps dynamisch
erstellen können, welche die von Suchmaschinen erwarteten
XML-Sitemap-Standards einhält.
<a href="https://www.sitemaps.org/" class="external text"
target="_blank" rel="nofollow noreferrer noopener">Sitemap-Protokoll</a>

Die meisten dieser Erweiterungen funktionieren über die Auswahl von
Menüpunkten, die in einer XML-Sitemap integriert werden sollen und durch
die Angabe, wie häufig sich diese ändern (siehe Update-Frequenz). Es ist
aber auch möglich, Unterseiten der Menüpunkte einzubinden (z.B. ein
Menüelement zeigt auf einen Kategorie-Blog, nun sollen aber alle Artikel
als einzelne Elemente angezeigt werden oder - ein anderes Beispiel wäre
ein Menüpunkt zeigt auf eine Shop-Kategorie-Seite - in der Sitemap soll
die Liste der Kategorie und zusätzlich jedes Produkt in einer separaten
Link aufgelistet werden).

### Update-Frequenz

In der XML-Sitemap kann manuell angegeben werden, wie oft die
Suchmaschinen-Spider die Website besuchen sollen. Die meisten
Suchmaschinen haben eingebaute Systeme, die automatisch die Frequenz
anpassen, je nachdem, wie oft die betreffende Seite geändert wird.

Zum Beispiel: In der XML-Sitemap wird festgelegt, dass die Website
täglich aufgesucht werden soll, aber die Website ändert sich nur 1 x pro
Woche, kann die Update-Frequenz angepasst werden und der Bot kommt nicht
mehr täglich wie vorgegeben. In verschiedenen Webmaster-Portalen kann
die Frequenz-Änderung erneut angestoßen werden (z.B. Google Webmaster
Tools).

Dies lässt vermuten, dass durch regelmäßig aktualisierte Inhalte das
'Durchsuchen durch Bots' häufiger erfolgt - wodurch diese Webseiten
schneller indiziert werden als Weseiten, deren Inhalte sich seltener
ändert.

Es ist generell sinnvoll, statische Webseiten entsprechend zu markieren,
um weniger häufig durchsucht zu werden als Webseiten deren Inhalte sich
häufig ändern. Zum Beispiel kann ein statischer Text mit einer
Update-Frequenz von einmal im Monat, ein Blog oder eine News-Seite
sollte mit einer Frequenz von einmal täglich markiert werden. je
nachdem, wie oft sich die Inhalte ändern.

### HTML-Sitemaps

Eine HTML-Sitemap ist im wesentlichen eine Tabelle von Inhalten der
Website, die den Besuchern zur Verfügung gestellt werden kann. Dies
dient im Wesentlichen zwei Zwecken:

1.  Bietet einen Anlaufspunkt wo die Besucher leicht eine Übersicht der
    gesamten Inhalte der Website vorfinden, auch wenn diese durch andere
    Navigationshilfen nicht leicht zugänglich sind
2.  Bietet eine zentrale Sammlung von Links zu den Inhalten innerhalb
    der Website, die leicht von den Suchmaschinen indiziert werden
3.  Bietet Benutzern mit Behinderungen eine leichte und schnelle
    Navigation durch die Website mit einer einfachen Liste von Links,
    anstatt komplexe Menüs

Zumindest eine XML-Sitemap sollte verlinkt werden, um die wichtigsten
Abschnitte und Seiten innerhalb der Website aufzulisten, allerdings ist
es besser, eine detaillierte Sitemap zu erstellen.

Wie bereits erwähnt, werden Erweiterungen angeboten, die das Erstellen
von XML-Sitemaps automatisch erledigen. Diese basieren auf den Inhalten
von Joomla.

### HTML-Sitemaps

XML-Sitemaps sind eine einfache Möglichkeit für Webmaster die
Suchmaschinen über neue und bestehende Seiten auf Ihren Websites zu
informieren, die für das Crawlen verfügbar sind. In seiner einfachsten
Form ist eine Sitemap eine XML-Datei, die Listen von URLs einer Website
enthält. Ergänzt durch zusätzliche Metadaten über jede URL (wann diese
zuletzt aktualisiert wurde, wie oft der Inhalt sich in der Regel ändert
und wie wichtig diese im Vergleich zu anderen URLs auf der Website ist),
damit die Suchmaschinen die Website intelligenter Crawlen.

Der Einsatz des Sitemap-Protokolls garantiert aber nicht, dass die
Website in den Suchmaschinen gelistet wird, bietet jedoch hilfreiche
Hinweise für die Webcrawler die Website besser zu crawlen.

1.  Eine XML-Sitemap bietet eine zentrale Sammlung von Links zu den
    Inhalten innerhalb der Website, die leichter von den Suchmaschinen
    indiziert werden
2.  Es ist möglich, spezielle XML-Sitemaps für News, Mobile URLs, Bilder
    und Videos zu erstellen

Verfügbar sind Erweiterungen die das Erstellen von XML-Sitemaps
basierend auf den Joomla! Inhalten automatisch erledigen.
