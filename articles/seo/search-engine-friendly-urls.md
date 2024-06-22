<!-- Filename: Search_Engine_Friendly_URLs / Display title: Suchmaschinenfreundliche URLs -->

**Suchmaschinenfreundliche (SEF-search engine friendly)**, **vom
Menschen lesbar** oder
<a href="https://en.wikipedia.org/wiki/Clean_URL" class="extiw"
title="wikipedia:Clean URL">clean URLs</a> sind URLs, die sowohl von
Menschen als auch von Suchmaschinen verstanden werden. Sie bilden den
Pfad zu der aufgerufenen Seite ab. Seit Version 1.5 kann Joomla! URLs in
verschiedenen Formaten erzeugen und parsen, darunter auch SEF URLs.
Dabei ist Joomla nicht vom URL-Rewriting (Apache mod-rewrite Modul) des
Webservers abhängig. SEF URLs können auch auf jedem Nicht-Apache Server
generiert werden. SEF URLs haben ein feststehendes Muster. Der Benutzer
kann jedoch  kurze, beschreibende Texte
(Aliase) für jeden Teil der URL
definieren.

Intern wird der lokale Teil der SEF URL (der Teil des Domain Namens)
eine **Route** genannt. Das Erzeugen und Verarbeiten von SEF URLs wird
daher als **Routing** bezeichnet. Der dazugehörige Code wird **Router**
genannt.

Ein gutes Beispiel für Routing ist die URL des "Willkommen zu Joomla!"
Beitrags in den Beispieldaten.

- Ohne die Aktivierung von SEF URLs, wird folgende URL erzeugt
  `http://www.beispiel.de/index.php?option=com_content&view=article&id=1:welcome-to-joomla&catid=1:latest-news&Itemid=50`
- Mit Aktivierung von SEF URLs und deaktiviertem mod_rewrite, wird diese
  URL generiert:
  `http://www.beispiel.de/index.php/the-­news/1-­latest­-news/1­-welcome­-to­-joomla`
- Sind sowohl SEF URLs als auch mod_rewrite aktiviert wird
  `http://www.beispiel.de/the-­news/1­-latest-­news/1-­welcome-­to­-joomla`
  erzeugt.

Suchmaschinenfreundliche URLs können durch die Einstellung
**Suchmaschinenfreundliche URL** in der *Globalen Konfiguration*
aktiviert werden. Diese Einstellung ist seit Joomla! 1.6 vorhanden.
Siehe auch  Enabling Search Engine Friendly (SEF)
URLs
für weitere Informationen.

## FAQs

### Was bedeuten die Zahlen in der URL?

Beim Vergleich der alten und der neuen URL sieht man Zahlen in der alten
URL ,

    http://www.beispiel.de/index.php?option=com_content&view=article&id=1:willkommen-bei-joomla&catid=1:letzte-neuigkeiten&Itemid=50

es gibt aber auch Zahlen in der neuen URL:

    http://www.beispiel.de/aktuell/1­-letzte-neuigkeiten/1-­willkommen-bei-joomla

Bei den Zahlen handelt es sich um Parameter, die von Joomla verwendet
werden, um die interne URL zu ermitteln und die entsprechende Seite
anzeigen zu können (im Beispiel handelt es sich bei der ersten Ziffer um
die ID der Kategorie, bei der Zweiten um die ID des Beitrags).

### Es gibt kein `index.php` mehr in der URL. Kann ich die Datei nun löschen?

**Nein!** Die URL enthält zwar kein `index.php` mehr, aber intern wird
der mod_rewrite zum Originalpfad umleiten, ohne es dem Anwender zu
zeigen.

### Was ist der Alias ? Wie kann man ihn erzeugen?

Alias-Felder finden sich rechts neben den Titel-Feldern in Beiträgen,
Kategorien und Menüeinträgen. Joomla! kann den Alias automatisch
erzeugen. Als Basis wird der Titel verwendet. Alle Großbuchstaben werden
in Kleinbuchstaben umgesetzt, Leerzeichen und Sonderzeichen sind in
einer URL nicht erlaubt und werden daher durch Bindestriche ersetzt.

### Verwendung eines selbst definierten Alias-Werts

Falls der von Joomla erzeugte Wert für den Alias nicht verwendet werden
soll, kann ein individueller Wert in das Alias-Feld eingetragen werden.
Die Verwendung von guten Schlüsselwörtern in der URL soll die
Suchmaschinenoptimierung verbessern. Die Schlüsselwörter können entweder
in den Titel eingebaut werden, woraus Joomla den Alias generiert oder
sie können direkt im selbst definierten Alias verwendet werden.

### Wie wird der Alias in der URL verwendet?

Im Menüeintrag verwendet Joomla! den Alias als Baustein. Sind die ersten
beiden SEF Einstellungen in der Konfiguration aktiviert
(Suchmaschinenfreundliche URL + URL Rewrite) und man erzeugt einen
Menüeintrag mit dem Titel Produkte erhält man folgende URL:
beispiel.de/produkte.

Joomla verwendet zusätzlich den Primärschlüssel der Daten innerhalb der
URL. So kann der Router zur richtigen Webseite navigieren. Im folgenden
wird das oben verwendete Beispiel weitergeführt: der Menüeintrag
Produkte hat den Menüeintragstyp Beiträge/Kategorieblog. Der Link des
Beitragtitels und/oder der Weiterlesen-Link bestehen dann aus drei
Teilen:

- Die URL des Menüeintrags - beispiel.de/produkte;
- Plus, den Primärschlüssel für die Kategorie und den Kategorie-Alias -
  32-Obst;
- Plus, den Primärschlüssel für den Beitrag und den Alias des Beitrags -
  1-Apfel;

Die vollständige URL ergibt sich dann zu:
`http://beispiel.de/produkte/32-obst/1-apfel`

### Wie können die Zahlen in den SEF URLs vermieden werden?

Die Zahlen in der SEF URL werden vom Joomla Router gebraucht, um die
Seitenzugriffe zu lenken. Mit einer stablilen Router Logik, können
Drittanbieter einfach Plugins entwickeln. So werden die Möglichkeiten
der Router vergrößert, z.B. durch bessere Auswahlmöglichkeiten. Dann
werden sicherlich auch die Zahlen aus den URLs entfernt.

## Route Formate und Routing Mechanismus

*Dieser Teil beschreibt Joomlas Core (built-in) Routing Mechanismus.
Externe Routing Erweiterungen können die Art der Erzeugung von Routes im
System verändern.*

### Route Formate

Zur Beschreibung des Joomla Routing Mechanismus im Detail muss der
Begriff **Route** erklärt werden. Angenommen das Joomla System wurde auf
`http://beispiel.de/sites/first/` installiert. Der Installationspfad
wird allgemein als **base URL** bezeichnet. Betrachtet man folgende
Beispiel-URL `http://beispiel.de/sites/first/products/32-fruit/1-apple`,
dann ist der erste Teil der URL die base URL, dieser Teil kann von
Joomla und den Routern der Komponenten nicht verändert werden. Der
zweite Teil `products/32-fruit/1-apple`, wird als **Route** bezeichnet,
und besteht wiederum aus drei **Segmenten**.

Das erste Segment einer Route wird bei einer typischen URL vom Alias des
Menüeintrags gebildet. Die SEF URL wird sozusagen durch den Menüeintrag
geleitet (**routed through**). Die anderen Segmente werden durch den
Router der Komponente bestimmt, die für den Menüeintragstyp zur
Verfügung verantwortlich ist. Zum Beispiel wird der Menüeintragstyp
*Kategorie - Blog* von der Komponente <a
href="https://docs.joomla.org/index.php?title=Inhalt&amp;action=edit&amp;redlink=1"
class="new" title="Inhalt (page does not exist)">Inhalt</a>
bereitgestellt. Daher ist dieser Router für die Erzeugung und das Parsen
des restlichen Segments verantwortlich.

Joomla kann auch für Erweiterungen Routen erzeugen, ohne einen
Menüeintrag zur Verfügung zu haben. In diesem Fall generiert das System
eine spezielle Route, die mit dem Wort `component` als erstes Segment
beginnt. Diese Route wird unter Verwendung eines festen Formats erzeugt:
der Name der Komponente (ohne das führende `com_`) wird zum zweiten
Segement und alle anderen Parameter als weitere Segemente angehängt.

### Grenzen

Es ist wichtig zu verstehen, dass die Erstellung von Menüpunkten die
*einzige* Möglichkeit für Joomla Benutzer ist, eine Route zu definieren,
die zu einer spezifischen Komponente führt. Allerdings können Routen
erstellt werden, ohne sie auf der Website in einem Menü anzuzeigen. Eine
häufig verwendete Methode besteht in der Erzeugung eines Menüs, welches
im Frontend nicht angezeigt wird. So ein Menü wird
Schattenmenü
genannt .

Der vorige Abschnitt zeigt, dass es nicht möglich ist, eine einzige
Komponente für die Behandlung aller Routen verantwortlich zu machen. Es
ist z.B. nicht möglich zu spezifizieren, dass die URL
`http://beispiel.de/deralias` den Beitrag mit dem Alias `deralias`
anzeigt, wobei `deralias` jeder beliebige Text sein kann. Falls solche
URLs benötigt werden, können für die einzelnen Beiträge, jeweils eigene
Menüpunkte im Schattenmenü erstellt werden. Dies ist jedoch nur bei
einer kleinen Anzahl von Beiträgen sinnvoll. Ansonsten ist eine Routing
Erweiterung notwendig.

Der Routing Mechanismus ist daher nicht so flexibel, wie ihn Benutzer
manchmal brauchen. Andererseits reduziert er die Wahrscheinlichkeit für
mehrdeutige Routen (gleiche Route, die auf verschiedene Seiten weist)
und hat so einen großen Vorteil. Da das erste Segment immer von einem
Menüeintrag gebildet wird, weiß das System sofort, welcher
Komponenten-Router zum Parsen verwendet werden muss.

## Details der Implementierung

### Handhabung der Routen

*Dieser Abschnitt beschreibt die Implementierung des Routings in Joomla.
Komponenten Enwickler könnte auch dies interessieren:
<a href="https://docs.joomla.org/Supporting_SEF_URLs_in_your_component"
class="mw-redirect"
title="Supporting SEF URLs in your component">Supporting SEF URLs in
your component</a>.*

Joomla Routen werden von der <a
href="https://docs.joomla.org/index.php?title=JRouter&amp;action=edit&amp;redlink=1"
class="new" title="JRouter (page does not exist)">JRouter Klasse</a>
erzeugt und aufgelöst. Diese Klasse schaut im Wurzel-Verzeichnis (root)
der aktiven Komponente nach (spezifiziert im `option` Parameter im query
string) und fügt die `router.php` Datei in das Wurzel-Verzeichnis der
Komponente ein. Es kann danach entweder die Funktion zur Erzeugung der
SEF URL oder die zur Interpretation der SEF URL aufgerufen werden.

Die JRouter Klasse wird vom Joomla CMS in `/includes/router.php`
überschrieben (overriden). In dieser Datei werden die Build- und
Parse-Funktionen überschrieben, um einen sauberen Aufbau der URLs (
build und parse) im Joomla zu erreichen.

Die `router.php` Datei einer Komponente (z.B.:
`/components/com_content/router.php`) sollte folgende Funktionen
enthalten:

- ContentBuildRoute - baut die SEF URL auf
  - Parameter
    - \$query - dieser Array enthält die querystring Variablen
  - Returns: ein Array aus Segmenten. Jedes Segment ist durch ein '/'
    getrennt. Da diese später kombiniert werden, um die eigentliche URL
    zu erzeugen, sollten diese Felder im Arry keine '/' Zeichen
    enthalten.
- ContentParseRoute - interpretiert eine SEF URL
  - Parameters
    - \$segments - dieses Array enthält die Segmente der angeforderten
      URL.
  - Returns: ein Name =\> (value) Array der querystring Variablen. Auf
    das Array verweist der Link.

### Das SEF Plugin

Das Joomla *System - SEF* Plugin erbt `JPlugin` und implementiert die
Funktion `onAfterRender()`. In dieser Funktion wird der Body der
Antwort, die an den Browser geschickt wird ermittelt, durch die
Verwendung von `JResponse::getBody()`. Der Body der Antwort wird dann
auf Links durchsucht die `/index.php...` enthalten. Danach werden diese
Teile der Links durch eine korrekter SEF URL ersetzt. Dies geschieht
während des Aufrufs von `JRoute::_(`*`url`*`)`.

JRoute baut SEF URLs durch Instanziierung von `JRouter`-Objekten auf.
Dabei gibt es die Anforderung mit, das korrekte Links aus den
weitergegebenen URLs aufgebaut werden.

### Handhabung von SEF URLs

Im Standard werden SEF URLs vom `JRouterSite`-Objekt (
`/includes/router.php`) gehandhabt. Sie werden von
`JApplication::route()` in der Datei index.php aufgerufen. Dieser Aufruf
erfolgt durch die `$app`-Variable. Diese ist eine Instantz von `JSite`
(von `/includes/application.php`).

`JApplication::route()` hat das Ergebnis (non-destructive) im `$_GET`
Array. `JApplication::route()` setzt Variablen in `$_GET` durch den
Aufruf von `JRequest::set()`, dabei ist das overwrite Flag auf false
gesetzt. Daher wird ein Variablenname, der von `JRouter::route()`
zurückgebeben wird und bereits in `$_GET` vorhanden ist, nicht in
`$_GET` übernommen. Die ermöglicht eigenentwickeltes Routing.

### Eigenentwickeltes Routing

Joomla erlaubt die Erstellung eigener Routing Mechanismen. Um diese zu
erzeugen wird ein Plugin benötigt, dass die
`JPlugin::onAfterInitialise()` Funktion überschreibt. Diese Funktion
parst dann die URL und erzeugt die benötigten Variablen in `$_GET` bevor
das Standard-Routing in Joomla abläuft.

*Siehe auch <a
href="https://docs.joomla.org/Creating_a_System_Plugin_to_augment_JRouter"
class="mw-redirect"
title="Creating a System Plugin to augment JRouter">Creating a System
Plugin to augment JRouter</a> als Beispiel.*
