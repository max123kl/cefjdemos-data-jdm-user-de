<!-- Filename: Cache / Display title: Cache -->

Joomla hat verschiedene Möglichkeiten, "Dinge" zwischenzuspeichern. Hier
ist ein Überblick für Administratoren und Entwickler – was, wo und wann.

# Für Administratoren

Joomla bietet dem Administrator die Möglichkeit, die ganze Webseite oder
nur Teile seiner Webseite zwischenzuspeichern. Diese Anleitung erklärt
wie.

Auf einer Joomla-Website Webseite gibt es 3 Dinge, die
zwischengespeichert werden können:

1.  Die ganze Seite selbst - der Seiten-Cache
2.  Die Ausgabe der Joomla-Komponente für diese Webseite - der
    View-Cache.
3.  Die Ausgabe der auf dieser Seite gezeigten Modulen - der
    Modul-Cache.

Mit einer Reihe von Cache-Einstellungen wird die Zwischenspeicherung
gesteuert:

1.  Das System-Plugin "System - Page Cache"
2.  Die globale Konfiguration, Registerkarte System,
    Cache-Einstellungen. Setzen der System-Cache-Option auf
    - AUS - Caching deaktiviert
    - EIN - Konservatives Caching
    - EIN - Progressives Caching
3.  Viele Module haben in ihren Optionen eine Registerkarte Erweitert,
    in der das Caching auf *Global verwenden* oder *Kein Caching*
    eingestellt werden kann.

Wie im Folgenden beschrieben gibt es auch Regeln für das Caching, die
innerhalb des Joomla-Codes implementiert sind und über die man keine
Kontrolle hat.

Man kann den Cache über den Administrator-Menüeintrag System → Cache
löschen leeren. Generell kann man sich Joomla mit 3 Stufen des Cache
ansteigender Aggressivität vorstellen.

1.  Konservatives Caching
2.  Progressives Caching
3.  Seiten-Caching

Wir werden uns diese drei im Folgenden im Detail ansehen.

Darüber hinaus können Joomla-Entwickler Caching-Funktionen verwenden, um
das Ergebnis von Datenbankabfragen zu speichern, z.B. um die
Reaktionsfähigkeit der Website zu erhöhen, aber dies ist außerhalb des
Bereichs der Administratorfunktionen.

## Seitencaching

Um dies einzuschalten, geht man zu Administrator Extensions → Plugins.
Sucht dort das System - Page Cache-Plugin und aktiviert es. Das
bedeutet, dass Seiten der Website nun zwischengespeichert werden und
wenn sie erneut aufgerufen werden, wird die zwischengespeicherte Seite
bereitgestellt anstatt sie von Joomla aus den Informationen in der
Datenbank zu generieren. Die zwischengespeicherte Seite wird weiterhin
bedient, bis sie abgelaufen ist - wie durch den Parameter *Cache Time*
in den Globalen Konfiguration → System → Cache-Einstellungen definiert.

Wenn man diese Seite als Tutorial liest und Seitencaching testen möchte,
sind diese Cache-Einstellungen der globalen Konfiguration am besten:

- Cache-Speicher - Datei
- Cache-Verzeichnis - leer lassen
- Cache-Dauer - 15 (die Standardeinstellung von 15 Minuten)
- Plattformspezifischer Cache - Nein
- Cache - AUS - Cache deaktiviert

Um zu überprüfen, ob der Seitencache funktioniert, geht man zu einer
Webseite, die einen Beitrag anzeigt. Nachdem man diese Seite angezeigt
hat, sollten man im Dateisystem ein `cache/page` Verzeichnis mit einer
Datei finden, die einen Dateinamen wie `-cache page-.php` enthält
(Joomla muss separate Cacheseiten für separate URLs speichern, so dass
die zweite Zeichenkette von Hex-Ziffern ein Hash der URL der Webseite
ist, um den Dateinamen eindeutig auf dieser Seite zu zuordnen).

Als Administrator den Text dieses Beitrags ändern und die Seite der
Website erneut anzeigen. Man sollte die zwischengespeicherte Version,
nicht den geänderten Text finden.

Das Ändern eines Beitrags (oder eines anderen Joomla-Elements) löscht
nicht den Seitencache für die Webseite(n), auf der dieser Beitrag
angezeigt wird. Um den Seitencache zu löschen, geht man zu Administrator
→ System → Cache löschen. Klickt man auf das Kontrollkästchen neben der
*Cachegruppe* "Seite" und drückt man die Schaltfläche Löschen. Wenn man
seine Webseite erneut anzeigt, sollte man nun den geänderten Text
angezeigt bekommen.

Wenn die Website eine Funktion wie einen Einkaufskorb hat, wird das
Anwenden von Page Caching zu Problemen führen, da die Seiten zeigen
müssen, was der Kunde bereits ausgewählt hat, anstatt eine gecachte
Seite anzuzeigen, die allen gemeinsam ist. Sie können das System - Page
Cache-Plugin jedoch so konfigurieren, dass das Zwischenspeichern
bestimmter Menüpunkte oder bestimmter URLs und URL-Bereiche (auf der
Registerkarte Erweitert) ausgeschlossen ist, so dass nur wirklich
statische Seiten zwischengespeichert werden.

## Konservatives Caching

Mit konservativen Caching kann man die Ansichts-Ausgabe von Komponenten
und die Ausgabe von Modulen, die das Caching erlauben,
zwischenspeichern. Beachten sollte man jedoch, dass dies nur auf Seiten
funktioniert, die nicht über den Seitencache zwischengespeichert werden.
Bei diesen Seiten wird die gesamte Webseite zwischengespeichert und
konservatives Caching wird nicht berücksichtigt.

Um konservatives Caching einzuschalten:

1.  Gehe zu Administrator → System → Globale Konfiguration → System-Tab
    und stelle in den Cache-Einstellungen den System-Cache auf EIN -
    Konservatives Caching.
2.  Gehe zu Erweiterungen → Module und wähle die Module aus, die
    zwischengespeichert sollen. Wenn dieses Modul das Caching erlaubt,
    dann sollte man unter der Registerkarte Erweitert die Option Caching
    auf

- Global - das Modul wird zwischengespeichert (da unter Global jetzt
  konservatives Caching eingestellt ist)
- Kein Caching - dies Modul wird nicht zwischengespeichert.

(Beachte, dass die Cache-Zeit in der globalen Konfiguration in Minuten
angegeben ist, während die Cache-Zeit in den Moduleinstellungen in
Sekunden angegeben ist.)

Um zu überprüfen, ob es funktioniert, sich abmelden und einen Artikel
der Webseite laden. Im Dateisystem sollte ein Ordner `cache/com_content`
sein, der die Cache-Datei enthält.

Man findet auch andere Verzeichnisse wie `cache/com_languages` (da die
Anzeige der Seite das Laden der aktuellen Sprache beinhaltet, und diese
wird ebenfalls zwischengespeichert) und Verzeichnisse, die sich auf den
Modul-Cache beziehen, z.B. `cache/com_modules`. Diese resultieren aus
der Verwendung von Cache, den Entwickler innerhalb der Joomla-Anwendung
kodiert haben.

Wenn man den Beitrag bearbeitet und speichert, dann die Seite
aktualisiert wird der bearbeitete Text angezeigt. Immer wenn eine
Bearbeitung gespeichert wird, leert Joomla den Cache für diesen Beitrag.

Man kann jedoch nachweisen, dass der Cache funktioniert, wenn man die
Cache-Datei im Verzeichnis `cache/com_content` mit einem einfachen
Texteditor bearbeitet. Damit ändert man einen Buchstaben innerhalb des
Beitrags und speichert die Cache-Datei. Aktualisiert man nun die
Webseite, sollte die Änderung der Cache-Datei zu sehen sein.

Wie kann man auswählen, welche Ansicht der Komponenten
zwischengespeichert wird und unter welchen Umständen? Leider ist das
nicht möglich. Dies wird von den Joomla-Entwicklern in der
Komponenten-PHP festgelegt. Für jede Komponente gelten unterschiedliche
Kriterien. Welche das sind, ist in der Datei `controller.php` zu finden.
Für die Komponente Kontakt z.B. findet man die Kriterien zum Zeitpunkt
des Schreibens (Joomla Version 3.9.2.) in der Datei
`components/com_contact/controller.php`.

    if (JFactory::getApplication()->getUserState('com_contact.contact.data') === null)
    {
        $cachable = true;
    }

Das bedeutet, dass die mit Kontakten verknüpften Ansichten
zwischengespeichert werden können, es sei denn, es gibt Sitzungsdaten,
die mit com_contact.contact.data verschlüsselt sind - was der Fall ist,
wenn der Benutzer in der Benutzersitzung ein Kontaktformular angezeigt
hat (z.B. auf einer Seite, auf die ein Menüpunkt vom Typ Kontakte /
Single Contact zeigt).

Die entsprechende Datei für Artikel
`components/com_content/controller.php` enthält:

    $cachable = true;
    if ($user->get('id') || ($this->input->getMethod() === 'POST' && (($vName === 'category' && $this->input->get('layout') !== 'blog') || $vName === 'archive' )))
    {
        $cachable = false;
    }

Der Ausdruck `$user->get('id')` ist wahr, wenn es sich um einen
angemeldeten Benutzer handelt. Das bedeutet, Beiträge angemeldeter
Benutzer werden nie zwischengespeichert. Die nachfolgenden Ausdrücke
beziehen sich auf andere Bedingungen, wenn das Caching nicht
durchgeführt wird, selbst wenn der Benutzer nicht angemeldet ist.

Auf diese Weise kann man erkennen unter welchen Umständen die
Zwischenspeicherung erfolgt, aber sie zu ändern ist nicht ratsam. Man
kann auch demonstrieren, dass Module zwischengespeichert werden, indem
man das Joomla Breadcrumbs-Modul verwendet. Man muss sicherstellen, dass
es an einer Modulposition auf der Webseite angezeigt wird, seine
Caching-Option einstellt und die zwischengespeicherte Datei im
Cache/mod_breadcrumbs manuell bearbeitet.

## Progressives Caching

Wie das konservative Caching speichert auch das progressive Caching die
Ausgabe aus Komponentensichten und Modulen. Der funktionale Unterschied
zwischen den beiden besteht darin, dass beim Progressive Caching **für
nicht angemeldete Benutzer alle Module immer zwischengespeichert
werden**. In diesem Fall hat die Einstellung der Option *No Caching* für
ein Modul keine Auswirkung. Wenn die Caching-Speicheroption auf *Datei*
steht, dann finden Sie die Modul-Cache-Datei (die Ausgabe aller Module
wird in derselben Datei gespeichert) im Verzeichnis `cache/com_modules`.

Um das progressives Caching einzuschalten, geht man zu Administrator →
System → Global Configuration → System-Tab und stellt in den
*Cache-Einstellungen* den System-Cache auf *AN- Progressive Caching*.

Hinsichtlich der Bedingungen für das Caching von
Joomla-Kernkomponentenansichten gibt es **keinen Unterschied zwischen
konservativem und progressivem Caching**. Trotz allem, was man auf
einigen Websites lesen kann und Antworten auf Fragen zum Stapelüberlauf,
ist es nicht der Fall, dass sich konservatives Caching auf das nicht
angemeldete Mitglied bezieht und progressives Caching auf das
angemeldete Mitglied.

## Zusammenfassung

Eine Zusammenfassung der Caching-Typen findet man unten.

### Seitencaching

- **Konfiguration**: Integriertes Plugin (Erweiterungen → Plugin Manager
  → System - Page Cache)
- **Caches**: jede ganze Seite der Website.
- **Basierend auf**: URL
- **Mehr Info**:
  - Optionales Browser-Caching: Cachiert auch auf dem Browser/Computer
    der Besucher.
  - Nur Cacheseiten für Gastbesucher (nicht für eingeloggte Besucher).
    Sei vorsichtig bei der Verwendung dieses Plugins, wenn man eine
    interaktive Website hat, auf der man Inhalte basierend auf
    Session-/Cookie-Informationen und nicht nur auf der reinen
    URL-Server verwenden möchten. Funktionen wie ein Einkaufswagen
    funktionieren nicht.

### Ansicht Caching

- **Konfiguration'**: Globale Konfiguration -\> Cache
- **Caches**: Jede Ansicht einer Komponente
- **Basierend auf**: URL, Ansicht, Parameter, …
- **Mehr Info**: Entwickler einer Komponente müssen dies in ihren Code
  aufnehmen, damit sie funktioniert. Meist ist dies nicht der Fall. Die
  Joomla Hauptinhaltskomponente verwendet diese, aber nur für
  Gastbesucher Ihrer Website, obwohl dies nicht für jede Komponente
  verpflichtend ist.

### Modul Caching

- **Konfiguration'**: Globale Konfiguration -\> Cache
- **Caches'**: Jedes Modul (individuell angepasst über die erweiterten
  Parameter jedes Moduls)
- **Basierend auf**: Der Modul-ID, der Ansichtsebenen des Benutzers und
  der *Itemid*-Parameter im HTTP-Request.
- **Mehr Info**: Um Probleme zu vermeiden bei manchen Modulen
  deaktivieren.

### Weiteres Caching

Wenn man andere Cachesysteme und -möglichkeiten ausprobieren möchten,
sollte man Erweiterungen von Drittanbietern rund um das Caching testen.

### Caching Engines oder Speicher

- **Konfiguration'**: Globale Konfiguration -\> Cache

Hier wählen, welches System die Website für das gesamte Caching
verwenden soll. Einige Optionen sind: APC, Bachelor, Datei, Memcache,
Redis, XCache.

APC zum Beispiel speichert auch Ihren PHP-Operationscode.

# Für Entwickler

Die Klasse *JCache''* erlaubt viele verschiedene Arten und Ebenen des
Caching. Die folgenden Unterklassen sind speziell entwickelt worden,
aber man kann seine eigenen hinzufügen oder die Hauptklasse auf viele
verschiedene Arten verwenden.

Vergiss nicht, dass die erste Ebene des Cache, auf die gestoßen ist,
jedes tiefere Caching überschreibt. Man nimmt an, dass zu viele Ebenen
auch kontraproduktiv sind (*aber zu verifizieren*).

- **JCacheView** cacht und gibt die Ausgabe einer bestimmten Ansicht (in
  MVC) zurück. Eine Cache-ID wird automatisch aus der URI, der
  spezifischen Ansicht und ihrer spezifischen Methode generiert oder man
  kann seine eigene angeben.

Dies kann automatisch über die Display-Funktion des Basiscontrollers
erfolgen. Zum Beispiel in der Steuerung der eigenen Komponente:

    class DeliciousController extends JController {
        function display() {
            parent::display(true); //true asks for caching.
        }
    }

Es gibt auch einige urlparams zu beachten. Überprüfe dies <a
href="https://joomla.stackexchange.com/questions/5781/how-can-i-use-joomlas-cache-with-my-components-view/7000#7000"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">"joomla stack"</a>

Beachte auch, dass Aktualisierungen (z.B. Hits oder Besucherzahlen)
NICHT aktualisiert werden (es sei denn, man fügt dies außerhalb dieser
Methode und damit eines tieferen MVC-Teils hinzu.)

- **JCachePage** cacht und gibt den Text der Seite zurück.
- **JCacheCallback** cacht und gibt die Ausgabe und die Ergebnisse von
  Funktionen oder Methoden zurück.

Wenn man Abfragen zwischenspeichern möchte, ist dies eine gute Klasse,
wie hier gezeigt:  Using caching to speed up your
code

- *JCacheOutput* cacht und gibt die Ausgabe zurück.

Dies ist eher für das Caching eines bestimmten Teils des PHP-Codes
gedacht. Es verhält sich wie ein Ausgabepuffer, aber im Cache.

## Referenzen

- <a
  href="https://forum.joomla.org/viewtopic.php?f=428&amp;t=326990&amp;start=0"
  class="external text" target="_blank" rel="noreferrer noopener">Better
  performance with Joomla System Cache plugin (Joomla Forum)</a>
- <a
  href="https://api.joomla.org/cms-3/classes/Joomla.CMS.Cache.Cache.html"
  class="external text" target="_blank"
  rel="noreferrer noopener">JCache</a>
- <a
  href="https://joomla.stackexchange.com/questions/5781/how-can-i-use-joomlas-cache-with-my-components-view/7000#7000"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">How can I use Joomla's Cache with my
  components view? (joomla stackexchange beta)</a>
