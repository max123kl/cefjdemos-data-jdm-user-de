<!-- Filename: J3.x:Adding_custom_fields/Sql_Field / Display title: SQL-Feld -->

## SQL-Feld

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

### SQL

Dieses Feld bietet eine Dropdown Liste aus Einträgen aus aus einer
Abfrage aus der Joomla! Datenbank. Die ersten Abfrageergebnisse aus der
Abfrage werden als Optionen in einer Dropdown Liste angezeigt.

#### Optionen

Spezielle Optionen in diesem Bereich sind:

- Mehrfachauswahl
  Erlaubt die Mehrfachauswahl - falls aktiviert.
- Abfrage
  Die SQL-Abfrage, die die Daten für die Dropdown-Liste liefert. Die
  Abfrage muss zwei Spalten zurückgeben; eine mit dem Namen"value", die
  die Werte der Listenelemente enthält; die andere mit dem Namen"text",
  die den Text in der Dropdown-Liste enthält.

#### Zugehörige Informationen

Siehe  SQL
Formular-Feld-Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.

<img
src="https://docs.joomla.org/images/thumb/c/cf/Sql_field_create-en.png/800px-Sql_field_create-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/c/cf/Sql_field_create-en.png/1200px-Sql_field_create-en.png 1.5x, https://docs.joomla.org/images/c/cf/Sql_field_create-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Sql field create-en.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img
src="https://docs.joomla.org/images/thumb/4/4a/Sql-en.png/800px-Sql-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/4a/Sql-en.png/1200px-Sql-en.png 1.5x, https://docs.joomla.org/images/4/4a/Sql-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Sql-en.png" />

##### Nutzung des Feldes im Frontend

Im Frontend kannst du das Feld wie im nachfolgenden Bild sehen. Die
Option "Automatische Anzeige" ist für die Position des Feldes
verantwortlich und dein Template ist für die Gestaltung des Feldes
verantwortlich.
Felder sind nur sichtbar im Frontend, wenn du diese auch mit Daten im
Artikel befüllt hast. Wenn es kein Pflichtfeld ist, können Sie es
vergessen?

<img
src="https://docs.joomla.org/images/thumb/6/66/Sql_field_frontend-en.png/800px-Sql_field_frontend-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/6/66/Sql_field_frontend-en.png/1200px-Sql_field_frontend-en.png 1.5x, https://docs.joomla.org/images/6/66/Sql_field_frontend-en.png 2x"
data-file-width="1291" data-file-height="661" width="800" height="410"
alt="Sql field frontend-en.png" />

<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Repeatable_Field"
id="content-button" class="button expand success">Zurück: Wiederholbares
Feld</a>
<a href="https://docs.joomla.org/J3.x:Adding_custom_fields/Text_Field"
id="content-button" class="button expand">Weiter: Text Feld</a>
