<!-- Filename: J3.x:Adding_custom_fields/Text_Field / Display title: Textfeld -->

## Textfeld

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

### Text

Dieser Feld-Typ stellt ein Textfeld für die Eingabe von Daten zur
Verfügung.

#### Optionen

Spezielle Optionen in diesem Feld sind:

- Filter
  Erlaubt dem System, bestimmte HTML-Tags oder Rohdaten zu speichern.
  Verwende den Raw-Filter, um sicherzustellen, dass der HTML-Code
  erhalten bleibt, wenn das Formular verarbeitet wird.
- Maximale Länge
  Die maximale Anzahl an Zeichen, die eingegeben werden können.

#### Zugehörige Informationen

Siehe  Text
Formularfeldtyp

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img src="https://docs.joomla.org/images/f/fd/Text_field_create-de.png"
decoding="async" data-file-width="800" data-file-height="440"
width="800" height="440" alt="Text field create-de.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img src="https://docs.joomla.org/images/3/30/Text-de.png"
decoding="async" data-file-width="800" data-file-height="199"
width="800" height="199" alt="Text-de.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<a
href="https://docs.joomla.org/index.php?title=Special:Upload&amp;wpDestFile=Text_field_frontend-de.png"
class="new" title="File:Text field frontend-de.png">800px</a>

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Sql_Field"
id="content-button" class="button expand success">Zurück: SQL Feld</a>
<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Textarea_Field"
id="content-button" class="button expand">Weiter: Textbereich Feld</a>
