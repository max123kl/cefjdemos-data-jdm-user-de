<!-- Filename: J3.x:Adding_custom_fields/Overrides / Display title: Anwendung von Feldern / Overrides -->

## Einsatz von Feldern in Overrides

**Artikel in dieser Serie**

1.  Einführung
2.   Parameter für alle Eigenen
    Felder
3.  Kalender-Feld
4.  Kontrollkästchen-Feld
5.   Farbe
    Feld
6.   Editor
    Feld
7.   Zahlen
    Feld
8.   Listen
    Feld
9.   Bilder-Listen
    Feld
10.  Medien
    Feld
11.  Optionsfeld
    (radio)
12.  Repeatable
    Field
13.  Sql
    Feld
14. Textfeld
15.  Textbereich
    Feld
16.  URL
    Feld
17.  Benutzer
    Feld
18.  Benutzergruppe
    Feld
19.  Wie man die Eigenen Felder
    gruppiert
20.  Welche Komponenten unterstützen die Eigenen
    Felder
21.  Implementierung in der eigenen
    Komponente
22.  Eigene Felder in Overrides
    anwenden

## Wie man Felder in Overrides verwendet

## Einleitung

Die wahre Stärke der Felder besteht in der Möglichkeit, diese in eigenen
Overrides beliebig einsetzen zu können. Hier folgt ein Beispiel wie das
erfolgen kann.

## Aufruf eines Feldes in einem Override

Grundsätzlich stehen alle Felder die dem aktuellen Element zugehören zur
Verfügung. Der Aufruf erfolgt über eine neue Eigenschaft der Variable
`$ item` mit dem Namen `jcfields`. Die `$item->jcfields` Eigenschaft ist
ein Array, das die folgenden Daten pro Feld enthält, wobei das Feld wie
in diesem Beispiel aussieht:

```php
    Array
    (
        [4] => stdClass Object
            (
                [id] => 4
                [title] => article-editor
                [name] => article-editor
                [checked_out] => 0
                [checked_out_time] => 0000-00-00 00:00:00
                [note] =>
                [state] => 1
                [access] => 1
                [created_time] => 2017-04-07 12:08:59
                [created_user_id] => 856
                [ordering] => 0
                [language] => *
                [fieldparams] => Joomla\Registry\Registry Object
                    (
                        [data:protected] => stdClass Object
                            (
                                [buttons] =>
                                [width] =>
                                [height] =>
                                [filter] =>
                            )

                        [initialized:protected] => 1
                        [separator] => .
                    )

                [params] => Joomla\Registry\Registry Object
                    (
                        [data:protected] => stdClass Object
                            (
                                [hint] =>
                                [render_class] =>
                                [class] =>
                                [showlabel] => 1
                                [disabled] => 0
                                [readonly] => 0
                                [show_on] =>
                                [display] => 2
                            )

                        [initialized:protected] => 1
                        [separator] => .
                    )

                [type] => editor
                [default_value] =>
                [context] => com_content.article
                [group_id] => 0
                [label] => article-editor
                [description] =>
                [required] => 0
                [language_title] =>
                [language_image] =>
                [editor] =>
                [access_level] => Public
                [author_name] => Super User
                [group_title] =>
                [group_access] =>
                [group_state] =>
                [value] => Bar
                [rawvalue] => Bar
            )

    )
```

### Das Feld rendern mit Einsatz des FieldsHelper

Um das Feld zu rendern, kann `FieldsHelper::render()` eingesetzt werden,
indem die benötigten Werte übergeben werden.

```php
    /**
     * Renders the layout file and data on the context and does a fall back to
     * Fields afterwards.
     *
     * @param   string  $context      The context of the content passed to the helper
     * @param   string  $layoutFile   layoutFile
     * @param   array   $displayData  displayData
     *
     * @return  NULL|string
     *
     * @since  3.7.0
     */
    public static function render($context, $layoutFile, $displayData)
```

#### Beispiel Code für das Override mit Einsatz von FieldsHelper

```php
<?php foreach ($this->item->jcfields as $field) : ?>
	// Render the field using the fields render method
	<?php echo $field->label . ':' . $field->value; ?>
<?php endforeach ?>
```

#### Beispiel Code für ein einfaches Override

```php
<?php foreach ($this->item->jcfields as $field) : ?>
	// Render the field using the fields render method
	<?php echo $field->label . ':' . $field->value; ?>
<?php endforeach ?>
```

### jcfields_enthält_nicht_die_benötigten_Felder"\>`$item->jcfields` enthält nicht die benötigten Felder

Die `jcfields` Eigenschaft wird mit dem Plugin Event Code
`onContentPrepare` generiert, indem der Kontext der Felder übergeben
wird. Das Feld Plugin liest die Felder aus der Datenbank aus und fügt
die Werte der jcfields Eigenschaft hinzu. Vergewissere Dich, dass die im
Override eingesetzte Komponente auch das Ereignis `onContentPrepare` mit
dem Kontext implementiert ist, der für die Felder verwendet wird.

Bei Einsatz einer Joomla! Kernkomponente, sollte das automatisch
funktionieren.

### Individuelle Felder laden

Um einzelne Felder zum Inhalt hinzuzufügen, wähle zunächst spezifische
Namen für die benutzerdefinierten Felder aus, indem der *Feldname* des
Feldes eingesetzt wird, welcher verwendet wird um das Feld direkt im
Override-Code zu referenzieren. Wähle im `Optionen` Tab
`Automatische Anzeige` das Feld **Nein**, um zu verhindern, dass es
automatisch an einer der Standardpositionen angezeigt wird.

Füge den folgenden Code am Anfang der Datei ein, um den direkten Zugriff
nach Namen auf Felder in den Overrides zu aktivieren. Dies sollte für
jede überschriebene PHP-Datei erfolgen, in der einzelne Felder eingefügt
werden sollen.

```php
<?php foreach($item->jcfields as $jcfield)
     {
          $item->jcFields[$jcfield->name] = $jcfield;
     }
?>
```

Und schließlich sollte der Platzierungscode des Feldes an der Stelle
eingefügt werden, an der die Feldbezeichnung oder der Feld-Wert
angezeigt werden soll.

Um das **Bezeichnung** des Feldes zum Override hinzuzufügen, gebe den
unten stehenden Code ein und ersetze `name-of-field` durch den Namen des
Feldes.

```php
<?php echo $item->jcFields['name-of-field']->label; ?>
```

Um den **Wert** des Feldes zum Override hinzuzufügen, den unten
stehenden Code eingeben und `name of-field` durch den Namen des Feldes
ersetzen. Vorsicht: In der 3.x Serie ist **value** in der Tat das
**rawvalue**. Siehe hierzu:
<a href="https://github.com/joomla/joomla-cms/issues/20216"
class="external free" target="_blank"
rel="nofollow noreferrer noopener">https://github.com/joomla/joomla-cms/issues/20216</a>
(en)

```php
<?php echo $item->jcFields['name-of-field']->rawvalue; ?>
```

Dieser Code kann zu jedem Teil des Overrides hinzugefügt werden.
Beispiele: Der Inhalt eines div, der src-String in einem `img` tag,
innerhalb eines CSS Klassenattributs, etc.

<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Implement_into_your_component"
id="content-button" class="button expand success">Zurück:
Implementierung in der eigenen Komponente</a>
