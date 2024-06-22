<!-- Filename: J3.x:Adding_custom_fields/Integer_Field / Display title: Feld für natürliche Zahlen -->

<span id="section-portal-heading"></span>

## Feld für natürliche Zahlen

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

### natürliche Zahlen

Dieses Feld bietet eine Dropdown Liste mit Zahlenwerten zwischen Minimum
(erster Wert) und Maximum (letzter Wert).

#### Optionen

Special options within this field are:

- Mehrfachauswahl
  Erlaubt die Auswahl von mehreren Werten.
- Erster
  Dieser Wert ist die niedrigste Zahl in der Liste.
- Letzter
  Dieser Wert ist die höchste Zahl in der Liste.
- Schritt
  Jede Option wird die vorherige Option um diesen Wert erhöhen. Beginnt
  mit dem ersten Wert und wird fortgesetzt bis der letzte Wert erreicht
  ist.

#### Zugehörige Informationen

Siehe  Feldtyp natürliche
Zahlen

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/e/e2/Integer_field_create-de.png"
decoding="async" data-file-width="800" data-file-height="632"
width="800" height="632" alt="Integer field create-de.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img src="https://docs.joomla.org/images/2/2a/Integer-de.png"
decoding="async" data-file-width="800" data-file-height="606"
width="800" height="606" alt="Integer-de.png" />

##### Nutzung des Feldes im Frontend

Im Frontend ist das Feld wie im folgenden Bild zu sehen. Die Option
*Automatische Anzeige* ist für die Position des Feldes und das Template
ist für die Gestaltung des Feldes zuständig.

<img
src="https://docs.joomla.org/images/8/86/Integer_field_frontend-de.png"
decoding="async" data-file-width="800" data-file-height="284"
width="800" height="284" alt="Integer field frontend-de.png" />

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Editor_Field"
id="content-button" class="button expand success">Zurück: Editor
Feld</a>
<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/List_Field"
id="content-button" class="button expand">Weiter: Listen Feld</a>
