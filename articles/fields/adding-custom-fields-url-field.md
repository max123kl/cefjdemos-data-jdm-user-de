<!-- Filename: J3.x:Adding_custom_fields/Url_Field / Display title: URL-Feld -->

## URL-Feld

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

### URL

Dieser Feld-Typ stellt ein Eingabe-Feld für URLs zur Verfügung.

#### Optionen

Spezielle Optionen in diesem Bereich sind:

- Schemata
  Erlaubte Schemata sind HTTP, HTTPS, FTP, FTPS, MAILTO, URL und FILE.
  Das Feld ist eigentlich ein Textfeld des Typs URL im Backend, wenn Du
  einen Artikel, einen Kontakt oder eine Komponente eines
  Drittherstellers mit Felder-Unterstützung verwendest. Es kann nur eine
  korrekte URL mit Schemata und Domain wie `http://example.com`
  eingegeben werden. Die URL wird vor dem Speichern in
  <a href="https://en.wikipedia.org/wiki/Punycode" class="external text"
  target="_blank" rel="nofollow noreferrer noopener">punycode</a>
  übersetzt. Das stellt die Funktionsfähigkeit der URL unabhängig vom
  Umfeld sicher.
- Relative URLs
  Definiert, ob relative URLs erlaubt sind.

#### Zugehörige Informationen

Siehe  URL
Formular-Feld-Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/thumb/f/f4/Url_field_create-en.png/800px-Url_field_create-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/f/f4/Url_field_create-en.png/1200px-Url_field_create-en.png 1.5x, https://docs.joomla.org/images/f/f4/Url_field_create-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Url field create-en.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img
src="https://docs.joomla.org/images/thumb/c/ce/URL-en.png/800px-URL-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/c/ce/URL-en.png/1200px-URL-en.png 1.5x, https://docs.joomla.org/images/c/ce/URL-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="URL-en.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<img
src="https://docs.joomla.org/images/thumb/c/c7/Url_field_frontend-en.png/800px-Url_field_frontend-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/c/c7/Url_field_frontend-en.png/1200px-Url_field_frontend-en.png 1.5x, https://docs.joomla.org/images/c/c7/Url_field_frontend-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Url field frontend-en.png" />

<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Textarea_Field"
id="content-button" class="button expand success">Zurück: Textbereich
Feld</a>
<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/User_Field"
id="content-button" class="button expand">Weiter: Benutzer Feld</a>
