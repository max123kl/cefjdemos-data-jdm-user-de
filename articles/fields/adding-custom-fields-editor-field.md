<!-- Filename: J3.x:Adding_custom_fields/Editor_Field / Display title: Editor-Feld -->

## Editor-Feld

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

### Editor

Dieses Feld bietet eine Liste der verfügbaren WYSIWYG Editoren.

#### Optionen

Spezielle Optionen in diesem Feld sind:

- Schaltflächen Anzeigen
  Hier kann definiert werden, ob der Editor Button angezeigt werden
  soll.
- Schaltflächen verbergen
  Hier können spezielle Buttons in einem Dropdown zum Verbergen des
  Editors ausgewählt werden. **Hinweis**: Diese Option macht nur Sinn,
  wenn die Option *Schaltflächen anzeigen* auf *Ja* eingestellt ist.
- Breite
  Dieser Wert definiert die Breite (in Pixel) des WYSIWYG Editors.
  Standardwert ist 100%.
- Höhe
  Dieser Wert definiert die Höhe (in Pixel) des WYSIWYG Editors. Der
  Standardwert ist 250 px.

#### Zugehörige Informationen

Siehe  Editor
Formular-Feld-Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/thumb/a/a6/Editor_field_create-de.png/800px-Editor_field_create-de.png.jpeg"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/a/a6/Editor_field_create-de.png/1200px-Editor_field_create-de.png.jpeg 1.5x, https://docs.joomla.org/images/thumb/a/a6/Editor_field_create-de.png/1600px-Editor_field_create-de.png.jpeg 2x"
data-file-width="2362" data-file-height="1514" width="800" height="513"
alt="Editor field create-de.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img
src="https://docs.joomla.org/images/thumb/a/a2/Editor-de.png/800px-Editor-de.png.jpeg"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/a/a2/Editor-de.png/1200px-Editor-de.png.jpeg 1.5x, https://docs.joomla.org/images/thumb/a/a2/Editor-de.png/1600px-Editor-de.png.jpeg 2x"
data-file-width="2354" data-file-height="1325" width="800" height="450"
alt="Editor-de.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<img
src="https://docs.joomla.org/images/thumb/7/73/Editor_field_frontend-de.png/800px-Editor_field_frontend-de.png.jpeg"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/7/73/Editor_field_frontend-de.png/1200px-Editor_field_frontend-de.png.jpeg 1.5x, https://docs.joomla.org/images/thumb/7/73/Editor_field_frontend-de.png/1600px-Editor_field_frontend-de.png.jpeg 2x"
data-file-width="2018" data-file-height="773" width="800" height="306"
alt="Editor field frontend-de.png" />

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Color_Field"
id="content-button" class="button expand success">Zurück: Farbe-Feld</a>
<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Integer_Field"
id="content-button" class="button expand">Weiter: Zahlen-Feld</a>
