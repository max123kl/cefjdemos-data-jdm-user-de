<!-- Filename: J3.x:Adding_custom_fields/Usergroup_Field / Display title: Benutzergruppe Feld -->

## Benutzergruppe-Feld

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

### Benutzergruppen-Liste

Dieser Feld-Typ stellt ein Feld zum Laden einer Drop-down-Liste der
verfügbaren Joomla! Benutzergruppen zur Verfügung.

#### Optionen

Spezielle Optionen in diesem Bereich sind:

- Mehrfachauswahl
  Erlaubt die Auswahl von mehreren Werten.

#### Zugehörige Informationen

Siehe  Benutzergruppen
Formular-Feld-Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/thumb/2/24/Usergrouplist_field_create-en.png/800px-Usergrouplist_field_create-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/2/24/Usergrouplist_field_create-en.png/1200px-Usergrouplist_field_create-en.png 1.5x, https://docs.joomla.org/images/2/24/Usergrouplist_field_create-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Usergrouplist field create-en.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img
src="https://docs.joomla.org/images/thumb/3/38/Usergrouplist-en.png/800px-Usergrouplist-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/3/38/Usergrouplist-en.png/1200px-Usergrouplist-en.png 1.5x, https://docs.joomla.org/images/3/38/Usergrouplist-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Usergrouplist-en.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld angezeigt wie im folgenden Bild zu sehen. Die
Option *Automatische Anzeige* gibt die Position des Feldes an und das
Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<img
src="https://docs.joomla.org/images/thumb/a/a0/Usergrouplist_field_frontend-en.png/800px-Usergrouplist_field_frontend-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/a/a0/Usergrouplist_field_frontend-en.png/1200px-Usergrouplist_field_frontend-en.png 1.5x, https://docs.joomla.org/images/a/a0/Usergrouplist_field_frontend-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Usergrouplist field frontend-en.png" />

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/User_Field"
id="content-button" class="button expand success">Zurück: Benutzer
Feld</a> <a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/How%CC%9E_can_you_group_custom_fields"
id="content-button" class="button expand">Weiter: Wie man die Felder
gruppiert</a>
