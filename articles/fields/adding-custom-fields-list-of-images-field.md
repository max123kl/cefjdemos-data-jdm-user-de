<!-- Filename: J3.x:Adding_custom_fields/List_of_Images_Field / Display title: Bilder-Listen Feld -->

<span id="section-portal-heading"></span>

## Bilder hinzufügen Feld

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

### Bilder hinzufügen

Bietet eine drop-down-Liste aus Bild-Dateien.

#### Optionen

Spezielle Optionen in diesem Bereich sind:

- Verzeichnis
  Das Verzeichnis, das die Bilddateien enthält, die im Bezug auf den
  Standardbildordner (einstellbar unter „Medien“  **→**  „Optionen“)
  aufgelistet werden sollen.
- Mehrfachauswahl
  Erlaubt die Auswahl von mehreren Werten.
- Bildklasse
  Die Klasse die zum Bild hinzugefügt werden soll (src tag).

#### Zugehörige Informationen

Siehe  Bilder-Listen Feld
Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img src="https://docs.joomla.org/images/2/21/Image_field_create-de.png"
decoding="async" data-file-width="800" data-file-height="711"
width="800" height="711" alt="Image field create-de.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img src="https://docs.joomla.org/images/3/30/Image-de.png"
decoding="async" data-file-width="800" data-file-height="518"
width="800" height="518" alt="Image-de.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<img
src="https://docs.joomla.org/images/4/41/Image_field_frontend-de.png"
decoding="async" data-file-width="800" data-file-height="586"
width="800" height="586" alt="Image field frontend-de.png" />

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/List_Field"
id="content-button" class="button expand success">Zurück: Listen
Feld</a>
<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Media_Field"
id="content-button" class="button expand">Weiter: Medien Feld</a>
