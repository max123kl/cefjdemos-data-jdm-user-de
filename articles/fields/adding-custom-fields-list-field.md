<!-- Filename: J3.x:Adding_custom_fields/List_Field / Display title: Listen-Feld -->

## Listen-Feld

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

### Liste

Dieses Feld bietet eine Dropdown Liste oder Listenbox mit selbst
definierten Werten. Wenn das Feld einen gespeicherten Wert hat, wird
dieser Wert beim ersten Laden der Seite angezeigt. Wenn der Wert leer
ist, wird der Standardwerd (falls definiert) angezeigt.

#### Optionen

Spezielle Optionen in diesem Feld sind:

- Mehrfachauswahl
  Erlaubt die Mehrfachauswahl - falls aktiviert.
- Listenwerte
  Die Werte der Liste.

#### Zugehörige Informationen

Siehe
Listenformular-Feld-Typ

#### Screenshots

##### Feld erstellen

Als Beispiel erstellen wir ein Feld mit den Optionen wie im nächsten
Bild gezeigt.
<img src="https://docs.joomla.org/images/0/08/List_field_create-de.png"
decoding="async" data-file-width="800" data-file-height="578"
width="800" height="578" alt="List field create-de.png" />

##### Nutzung des Feldes im Backend

Im Backend wird während der Erstellung oder Bearbeitung eines Beitrages
(oder auch Kontaktes) das Feld wie im folgenden Bild angezeigt:

<img src="https://docs.joomla.org/images/4/45/List-de.png"
decoding="async" data-file-width="800" data-file-height="429"
width="800" height="429" alt="List-de.png" />

##### Nutzung des Feldes im Frontend

Im Frontend wird das Feld wie im Folgenden Bild angezeigt.

<img
src="https://docs.joomla.org/images/b/b5/List_field_frontend-de.png"
decoding="async" data-file-width="800" data-file-height="284"
width="800" height="284" alt="List field frontend-de.png" />

Die Option *Automatische Anzeige* gibt die Position des Feldes an und
das Template bestimmt das Design des Feldes.
Felderinhalte werden nur im Frontend angezeigt, wenn es im Beitrag mit
Daten gefüllt wurde. Das Feld kann auch als Pflichtfeld deklariert
werden, dann vergisst man auch nicht das Ausfüllen.

<a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Integer_Field"
id="content-button" class="button expand success">Zurück:
Zahlen-Feld</a> <a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/List_of_Images_Field"
id="content-button" class="button expand">Weiter: Bilder-Listen Feld</a>
