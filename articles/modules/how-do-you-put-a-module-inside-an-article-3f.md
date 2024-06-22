<!-- Filename: How_do_you_put_a_module_inside_an_article%3F / Display title: Wie kann man ein Modul in den Inhalt eines Beitrags setzen? -->

Joomla!  <span class="small">≥ </span>2.5 Serie

Normalerweise sind Module Modulpositionen zugeordnet. Diese sind auf der
Webseite entsprechend den Festlegungen im Template verteilt. Manchmal
ist es notwendig ein Modul in einen Beitrag einzubetten. Im Joomla Core
gibt es dazu drei Möglichkeiten: loadposition, loadmodule und
loadmoduleid. Das Plugin *Inhalt - Module laden* muss aktiviert sein.

Syntax:

- {loadposition position,\[style\]}
- {loadmodule mod_type,the title,\[style\]}
- {loadmoduleid moduleId}

## loadposition

Um ein Modul innerhalb eines Beitrags einzufügen, wird das Modul auf
einer Position veröffentlicht und die Position dann folgendermaßen in
den Beitrag geladen:

1.  Erstellen eines Moduls und Festlegen der Modulposition auf
    ***meineposition***. ***meineposition*** kann ein beliebiger Wert
    sein, der nicht mit anderen, bereits vorhandenen Modulpositionen des
    Templates in Konflikt treten sollte. Dazu wird im Feld Position ein
    beliebiger Wert ***meineposition*** eingetragen und danach die
    Return-Taste gedrückt, anstelle einen Wert aus der Drop-Down-Liste
    auszuwählen.
2.  Zuordnung des Moduls zu **Auf allen Seiten** unter Menüzuweisung.
    Dies stellt sicher, das das Modul immer zu sehen ist, unabhängig
    davon wie der Seitenbesucher zu dem Beitrag gelangt. Das Modul wird
    nur angezeigt, wenn die load-Anweisung für das Modul in einem
    Beitrag
    erscheint.
3.  Im Bearbeiten-Modus wird im Beitrag an die Stelle in der das Modul
    erscheinen soll der Text ***{loadposition meineposition}***
    eingefügt. Dieser wird dann durch den Inhalt des Moduls ersetzt.

\*Wichtig: dieses funktioniert nur wenn das [Plugin *Inhalt - Module
laden* aktiviert
ist](https://docs.joomla.org/Help25:Extensions_Plugin_Manager_Edit#Content_-_Load_Modules "Special:MyLanguage/Help25:Extensions Plugin Manager Edit").
Falls das Plugin deaktiviert ist, wird der Text *{loadposition
meineposition}* unverändert im Beitrag angezeigt. Außerdem sollte der
Name der verwendeten Modulposition in Kleinbuchstaben geschrieben sein.
Die CamelCase-Schreibweise funktioniert nicht als Name der Position.

## loadmodule

Eine Alternative zu "{loadposition xx}" ist die "{loadmodule yyy}"
Variante, die mit gleichen Plugin umgesetzt wird.

In diesem Fall sucht das Plugin nach dem ersten Auftreten einen Moduls
dessen **Typ** mit der Zeichenkette 'yyy' übereinstimmt. So kann man
z.B. ein "mod_login" Modul laden, indem im Text eines Beitrages
{loadmodule login} eingefügt wird. In manchen Fällen gibt es mehre
Module des gleichen Typs, es soll aber nur eine spezifische Instanz des
Moduls geladen werden. Zum Beispiel gibt es zwei Login Module (die hier
Login 1 und Login 2 genannt werden). In diesem Fall verwendet man
{loadmodule mod_modType, modTitle} wobei mod\_**modType** mod_login und
**modTitle** für Ihre Instanz dieses Moduls ist. Das hieße für das obige
Beispiel endet man mit **{loadmodule mod_login Login 2}**. Man kann den
Stil, der für die Darstellung des Moduls verwendet werden soll, als
dritten Parameter {loadmodule login,Login 2,xhtml} angeben. Falls kein
Stil angegeben ist, wird "none" verwendet.

## loadmoduleid

Seit Joomla-Version 3.9.0 gibt es neben den Alternativen
`{loadposition xx}` und `{loadmodule yyy}` die Variante
`{loadmoduleid z}`, die ebenfalls vom Plugin umgesetzt wird.

In diesem Fall sucht das Plugin nach dem Modul, dessen `id` der Zahl `z`
entspricht. Man kann zum Beispiel das Modul mit der id 200 in den
Beitrag einfügen, indem man in den Editor-Text den Platzhalter
`{loadmoduleid 200}` einsetzt. Beachte dabei, dass diese Variante
weitere Parameter wie `style` nicht "versteht".

## Editor-Schaltfläche (seit Joomla!-Version 3.5)

Wenn das editor-xtd-Plugin "Schaltfläche - Modul" aktiviert ist, kannst
du den Editor-Button "Modul" verwenden, um die oben beschriebenen
Plugin-Tags bequemer in den Editor-Text einzufügen. Seit Joomla-Version
3.9 auch die Variante `loadmouleid`.

## Module innerhalb von Modulen

In Joomla! 2.5+ und Joomla! 3.x+ ist es möglich ein Modul innerhalb
eines "Eigene Inhalte (Custom HTML)"-Moduls einzufügen. Sie werden von
Content-Plugins (Inhalt-Plugins) genauso verarbeitet wie Artikel.

Damit dies funktioniert muss die Option **Inhalte vorbereiten**
aktiviert werden wie im Screenshot zu sehen ist.

<img
src="https://docs.joomla.org/images/f/f4/J3x_custom_html_prepare_content_option-de.png"
decoding="async" data-file-width="627" data-file-height="299"
width="627" height="299"
alt="Zeigt die Inhalte vorbereiten Option in einem Modul Eigene Inhalte." />

Man sollte daran denken, dass Formatierungsmöglichkeiten wie "chrome"
(Modulstil) des "Eigene Inhalte"-Moduls das "chrome" des
eingeschlossenen Moduls umschließen und so zu unerwünschten
Nebeneffekten bezüglich Formatierungen und Layout führen können. Das ist
der Grund, warum die Editor-Schalfläche "Modul" in diesem Modultyp nicht
verfügbar ist.
