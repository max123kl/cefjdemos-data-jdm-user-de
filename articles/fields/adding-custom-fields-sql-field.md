<!-- Filename: J3.x:Adding_custom_fields/Sql_Field / Display title: SQL-Feld -->

## Zweck

Das SQL-Feld bietet eine Dropdown-Liste von Einträgen, die aus einer Datenbankabfrage erhalten werden. Um dieses Feld zu verwenden, müssen Sie wissen, wie man eine Abfrage erstellt, und Sie sollten diese in phpMyAdmin testen.


## Felderstellung

Besondere Optionen in diesem Feld sind:

- **Mehrfach** Erlaubt die Auswahl mehrerer Werte. Wenn auf *Ja* gesetzt, werden 4 Elemente in der Liste angezeigt. Andernfalls wird 1 Element angezeigt. In jedem Fall gibt es eine lange Liste zum Durchscrollen, um Auswahlen zu treffen - falls aktiviert.
- **Abfrage** Die SQL-Abfrage, die die Daten für die Dropdown-Liste bereitstellt. Die Abfrage muss zwei Spalten zurückgeben; eine mit der Bezeichnung 'value', die die Werte der Listenelemente hält; die andere mit der Bezeichnung 'text', die den Text in der Dropdown-Liste enthält.

In diesem Beispiel wird eine Tabelle verwendet, die eine Liste von Ländernamen enthält. Dies ist die Abfrage:
```
SELECT `id` AS value, `title` AS text
FROM `#__countrybase_countries`
WHERE `state` = 1
ORDER BY `title` ASC
```
![SQL-Feld](../../../en/images/fields/fields-sql.png "SQL-Feld")

## Dateneingabe

Einfach - aus der Liste auswählen.


## Datenanzeige

Der folgende Screenshot der Seite zeigt das Feld, das in einem Beitrag angezeigt wird. Die Option *Automatische Anzeige* ist für die Position des Feldes verantwortlich, und Ihre Vorlage ist für das Design des Feldes verantwortlich.

Suchen Sie nach dem Punkt **Herkunftsland**.

![Anzeige aller Felder](../../../en/images/fields/fields-display.png "Felderanzeige")

Die Ausgabe ist ein einzelner Eintrag oder eine durch Kommas getrennte Liste von Einträgen (Ländernamen), die dem Feldlabel (Herkunftsland) folgen.

