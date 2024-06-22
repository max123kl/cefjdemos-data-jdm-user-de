<!-- Filename: J3.x:Adding_custom_fields/Calendar_Field / Display title: Anwendung von Eigene Felder / Kalender-Feld -->

## Kalender-Feld

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

## Das Kalender-Feld

Stellt ein Textfeld für die Eingabe eines Datums zur Verfügung. Neben
dem Textfeld ist ein Icon zum öffnen eines Popup-Kalenders. Dieser kann
zur Auswahl des Datums genutzt werden.

#### Optionen

Wenn das Standarddatum genutzt wird: Der Wert kann ISO 8601 Format
(JJJJ-MM-TT HH:MM:SS) oder NOW sein, welches das aktuelle Datum
anzeigt.
**Achtung**: Wurde im Standarddatum keine Zeit angeben, aber die Option
*Uhrzeit anzeigen* ist aktiviert, wird die Uhrzeit trotzdem angezeigt.
Spezielle Optionen des Feldes sind:

- Uhrzeit anzeigen
  Wenn aktiviert, erwartet das Kalenderfeld ein Datum und Uhrzeit und
  wird auch die Zeit anzeigen. Das Format ist lokalisiert und verwendet
  bei der Ausgabe das Format der regulären Sprachdateien.

#### Zugehörige Informationen

Siehe:

-  Kalender Formular
  Feldtyp
- <a href="http://php.net/manual/de/datetime.formats.date.php"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Datums-Formate</a>

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/thumb/f/f9/Calendar_field_create-de.png/670px-Calendar_field_create-de.png.jpeg"
decoding="async"
srcset="https://docs.joomla.org/images/f/f9/Calendar_field_create-de.png 1.5x"
data-file-width="800" data-file-height="561" width="670" height="470"
alt="Calendar field create-de.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img
src="https://docs.joomla.org/images/thumb/9/92/Calendar-de.png/670px-Calendar-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/9/92/Calendar-de.png 1.5x"
data-file-width="800" data-file-height="687" width="670" height="575"
alt="Calendar-de.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Faled angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<img
src="https://docs.joomla.org/images/thumb/4/43/Calendar_field_frontend-de.png/670px-Calendar_field_frontend-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/4/43/Calendar_field_frontend-de.png 1.5x"
data-file-width="800" data-file-height="494" width="670" height="414"
alt="Calendar field frontend-de.png" />

<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Parameters_for_all_Custom_Fields"
id="content-button" class="button expand success">Zurück: Parameter für
alle Felder</a> <a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Checkboxes_Field"
id="content-button" class="button expand">Weiter: Checkbox Feld</a>
