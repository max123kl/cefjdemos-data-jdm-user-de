<!-- Filename: J3.x:Adding_custom_fields/Calendar_Field / Display title: Kalenderfeld -->

## Zweck

Das Kalenderfeld bietet ein Textfeld für die Eingabe eines Datums. Ein Symbol neben dem Textfeld ruft einen ausklappbaren Kalender auf, der zur Auswahl eines Datums aus einem grafischen Kalender verwendet werden kann.

## Feld-Erstellung

Allgemeine Feldparameter werden in einem separaten Beitrag beschrieben.

* **Titel** Sie können mehrere Datumsfelder in einem Beitrag haben, daher ist es wichtig, den Titel sorgfältig zu setzen, um Mehrdeutigkeiten in der Ausgabe zu vermeiden.
* **Beschriftung** Dies wird in der Ausgabe angezeigt. Wenn es leer gelassen wird, wird es aus dem Inhalt des Titelfeldes übernommen, kann aber geändert werden.
* **Uhrzeit anzeigen** Wenn auf *Ja* gesetzt, wird die Uhrzeit dem Datumsfeld, dem Datumsauswahlwerkzeug und dem Ausgabedatum hinzugefügt. **Vorsicht**: Auch wenn Sie die Uhrzeit im Standarddatum nicht angeben, wird die Uhrzeit angezeigt, wenn die Option *Uhrzeit anzeigen* aktiv ist.
* **Platzhalter** Kann auf ein Datumsformat wie *JJJJ-MM-TT* gesetzt werden, um Benutzer an das erforderliche Format zu erinnern und/oder um eine Erinnerung daran zu geben, wofür das Datum steht, wie *Datum der Ankunft*.

## Dateneingabe

Das Kalenderfeld ist in der Anwendung einfach. Sie können das Datum im erforderlichen Format eingeben oder ein Datum mit dem Datumswähler auswählen. Achten Sie darauf, das Datum korrekt einzugeben. Ein Fehler im Datum wird beim Speichern auf ein neues Datum korrigiert. Zum Beispiel wird ein Datum von 2024-14-02 in 2025-02-02 korrigiert.

Der folgende Screenshot zeigt ein Erwerbsdatum:

![Erwerbsdatum Eintrag](../../../en/images/fields/fields-date-entry.png "Erwerbsdatum")

Felder erscheinen nur in einem Beitrag, wenn sie im Beitragsdateneingabeformular ausgefüllt sind.

## Datenanzeige

Der folgende Screenshots der Website zeigt das Feld, das in einem Beitrag angezeigt wird. Die Option *Automatische Anzeige* ist verantwortlich für die Position des Feldes und Ihr Template ist verantwortlich für das Design des Feldes.

Suchen Sie nach dem Element **Erwerbsdatum**.

![Anzeige aller Felder](../../../en/images/fields/fields-display.png "Anzeige der Felder")

Die Datumsformate werden mithilfe von Sprachstrings lokalisiert.

*Übersetzt von openai.com*

