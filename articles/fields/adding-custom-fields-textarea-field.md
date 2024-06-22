<!-- Filename: J3.x:Adding_custom_fields/Textarea_Field / Display title: Textbereich Feld -->

## Textbereich-Feld

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

### Textbereich

Dieser Feld-Typ stellt einen Textbereich für die Eingabe von
mehrzeiligem Text zur Verfügung.

#### Optionen

Spezielle Optionen in diesem Feld sind:

- Zeilen
  Die Höhe des sichtbaren Textbereichs in Zeilen. Wenn keine Angabe
  gemacht wird, gilt die Browsereinstellung. Dieser Wert hat keinen
  Einfluss auf die Anzahl der Zeichen, die in das Feld eingegeben werden
  können. Die Zeilen sind im Backend aktiv wenn Du einen Artikel, einen
  Kontakt oder eine Komponente eines Drittherstellers mit
  Felder-Unterstützung verwendest. Diese Option hat keinen Einfluss auf
  die Größe des Feldes im Frontend.
- Spalten
  Die Breite des sichtbaren Textbereichs in Spalten. Wenn keine Angabe
  gemacht wird, gilt die Browsereinstellung. Dieser Wert hat keinen
  Einfluss auf die Anzahl der Zeichen, die in das Feld eingegeben werden
  können. Die Spalten sind im Backend aktiv wenn Du einen Artikel, einen
  Kontakt oder eine Komponente eines Drittherstellers mit
  Felder-Unterstützung verwendest. Diese Option hat keinen Einfluss auf
  die Größe des Feldes im Frontend.
- Maximale Länge
  Die maximale Anzahl an Zeichen, die eingegeben werden können.
- Filter
  Dem System erlauben, bestimmte HTML-Tags oder ungefilterte Eingaben zu
  speichern.

#### Zugehörige Informationen

Siehe  Textbereich
Formular-Feld-Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/thumb/e/ec/Textarea_field_create-de.png/800px-Textarea_field_create-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/e/ec/Textarea_field_create-de.png/1200px-Textarea_field_create-de.png 1.5x, https://docs.joomla.org/images/e/ec/Textarea_field_create-de.png 2x"
data-file-width="1291" data-file-height="800" width="800" height="496"
alt="Textarea field create-de.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img
src="https://docs.joomla.org/images/thumb/d/dc/Textarea-en.png/800px-Textarea-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/d/dc/Textarea-en.png/1200px-Textarea-en.png 1.5x, https://docs.joomla.org/images/d/dc/Textarea-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Textarea-en.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<img
src="https://docs.joomla.org/images/thumb/4/4e/Textarea_field_frontend-en.png/800px-Textarea_field_frontend-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/4e/Textarea_field_frontend-en.png/1200px-Textarea_field_frontend-en.png 1.5x, https://docs.joomla.org/images/4/4e/Textarea_field_frontend-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Textarea field frontend-en.png" />

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Text_Field"
id="content-button" class="button expand success">Zurück: Textfeld</a>
<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Url_Field"
id="content-button" class="button expand">Weiter: URL Feld</a>
