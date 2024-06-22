<!-- Filename: J3.x:Adding_custom_fields/User_Field / Display title: Benutzer Feld -->

## Benutzer-Feld

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

### Benutzer

Dieser Feld-Typ stellt ein Auswahl eines Benutzers in einer Modal-Liste
zur Verfügung. Das Feld zeigt den Benutzernamen und speichert die
Benutzer-ID.

#### Optionen

Gibt es keine speziellen Optionen in diesem Bereich.

#### Zugehörige Informationen

Siehe  Benutzer
Formular-Feld-Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/thumb/1/1f/User_field_create-en.png/800px-User_field_create-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/1/1f/User_field_create-en.png/1200px-User_field_create-en.png 1.5x, https://docs.joomla.org/images/1/1f/User_field_create-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="User field create-en.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img
src="https://docs.joomla.org/images/thumb/7/71/User-en.png/800px-User-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/7/71/User-en.png/1200px-User-en.png 1.5x, https://docs.joomla.org/images/7/71/User-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="User-en.png" />

Und wenn Du darauf klickst, öffnet sich ein modales Fenster, in dem man
einen Benutzer auswählen kann.

<img
src="https://docs.joomla.org/images/thumb/1/1a/User_2-en.png/800px-User_2-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/1/1a/User_2-en.png/1200px-User_2-en.png 1.5x, https://docs.joomla.org/images/1/1a/User_2-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="User 2-en.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<img
src="https://docs.joomla.org/images/thumb/e/e5/User_field_frontend-en.png/800px-User_field_frontend-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/e/e5/User_field_frontend-en.png/1200px-User_field_frontend-en.png 1.5x, https://docs.joomla.org/images/e/e5/User_field_frontend-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="User field frontend-en.png" />

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Url_Field"
id="content-button" class="button expand success">Zurück: URL Feld</a>
<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Usergroup_Field"
id="content-button" class="button expand">Weiter: Benutzergruppen
Feld</a>
