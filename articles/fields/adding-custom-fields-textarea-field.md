<!-- Filename: J3.x:Adding_custom_fields/Textarea_Field / Display title: Textbereichsfeld -->

## Zweck

Das Textbereichsfeld ist ein Bereich zur Eingabe von mehrzeiligem Text. Ein einfaches Textfeld hat keinen WYSIWYG-Editor.

### Optionen

Besondere Optionen in diesem Feld sind:

- **Zeilen** Die Höhe des sichtbaren Textbereichs in Zeilen. Wenn weggelassen, wird die Höhe vom Browser bestimmt. Der Wert begrenzt nicht die Anzahl der einzugebenden Zeilen. Die Zeilen sind im Backend aktiv, während ein Beitrag, ein Kontakt oder eine Drittanbieter-Komponente erstellt wird, die benutzerdefinierte Felder unterstützt. Diese Option hat keine Auswirkung auf die Größe des Feldes im Frontend.
- **Spalten** Die Breite des sichtbaren Textbereichs in Zeichen. Wenn weggelassen, wird die Breite vom Browser bestimmt. Der Wert begrenzt nicht die Anzahl der einzugebenden Zeichen. Die Spalten sind im Backend aktiv, während ein Beitrag, ein Kontakt oder eine Drittanbieter-Komponente erstellt wird, die benutzerdefinierte Felder unterstützt. Diese Option hat keine Auswirkung auf die Größe des Feldes im Frontend.
- **Maximale Länge** Die maximale Anzahl an Zeichen, die eingegeben werden können.
- **Filter** Dem System erlauben, bestimmte HTML-Tags oder Rohdaten zu speichern.

## Dateneingabe

Einfach: den Text eingeben, der angezeigt werden soll.


## Datenanzeige

Der folgende Screenshot der Seite zeigt das Feld, das in einem Beitrag angezeigt wird. Die Option *Automatische Anzeige* ist für die Position des Feldes verantwortlich, und Ihr Template ist für das Design des Feldes verantwortlich.

Suchen Sie nach dem **Klassifizierungs**eintrag.

![Anzeige aller Felder](../../../en/images/fields/fields-display.png "Felderanzeige")

Das Feldlabel startet einen einzelnen Textblock, es sei denn, Sie haben HTML-Tags wie `<p>...</p>` eingegeben.

