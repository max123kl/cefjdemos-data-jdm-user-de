<!-- Filename: J3.x:Adding_custom_fields/Color_Field / Display title: Farbfeld -->

## Zweck

Das Farbfeld bietet einen Auswahldialog zur visuellen Auswahl einer Farbe. Das Feld zeigt den resultierenden Hex-Wert an. 


## Felderstellung

Spezielle Optionen für dieses Feld:

- **Feldklasse** Auf *w-auto* setzen, um das Feld gerade breit genug für die Darstellung und den Wert zu machen. 


## Dateneingabe

Sie können einen Hex-Farbwert eingeben, wenn Sie wissen, dass Hex-Zahlen von 0 bis 9 und dann von a bis f reichen und die Zahlenpaare Rot, Grün und Blau sind. Beispielsweise ist #00ff00 kein Rot, maximales Grün und kein Blau. Alternativ können Sie einen Cursor verwenden, um eine Farbe visuell auszuwählen.

![Farbwähler](../../../en/images/fields/fields-colour-entry.png "Farbwähler")


## Datenanzeige

Der folgende Screenshot der Website zeigt das Feld, das in einem Beitrag angezeigt wird. Die Option *Automatische Anzeige* ist verantwortlich für die Position des Feldes und Ihr Template ist verantwortlich für das Design des Feldes.

Die standardmäßige Datenanzeige ist der Hex-Farbwert, der nicht sehr nützlich ist. Die einfache Lösung besteht darin, ein Template-Override für die Felder / Farb-Plugin zu erstellen. Ersetzen Sie einfach diese Zeile:
```
echo htmlentities($value);
```
durch diese Zeilen:
```
$value = htmlentities($value);
echo '<span style="background-color: ' . $value . ';"> ' . $value . '</span>';
```
Und der Hex-Wert wird von einem Farbfeld mit der Hintergrundfarbe des Wertes begleitet.

Suchen Sie nach dem **Blumenfarbe**-Element.

![Anzeige aller Felder](../../../en/images/fields/fields-display.png "Felder anzeigen")
```

*Translated by openai.com*

