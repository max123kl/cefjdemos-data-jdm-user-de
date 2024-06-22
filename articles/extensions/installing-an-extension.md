<!-- Filename: Installing_an_extension / Display title: Installation einer Erweiterung -->

Bevor Du beginnst ist es immer klüger, vorher die Dokumentation im
Zusammenhang mit einer Erweiterung zu lesen. Die meisten Erweiterungen
haben Homepages und Foren bei denen es ratsam ist, diese sich vorher
anzuschauen. Wenn in der Erweiterung eine README-Datei enthalten ist,
solltest Du sie lesen.

Für die meisten Erweiterungen wird diese Methode angewendet:

- Lade die Erweiterung auf Deinem lokalen Rechner als zip-Paket-Datei.
- Im Backend Deiner Joomla!-Webseite (Administration) wähle
  Erweiterungen  **→**  Installieren/Deinstallieren.
- Klicke auf die Schaltfläche "Durchsuchen" und wähle das Paket der
  Erweiterung auf deinem Rechner.
- Klicke auf den Hochladen & Installieren Button.
- Einige Erweiterungen können weitere Anweisungen zur Installation
  enthalten.
- Beachte dass die enthaltenen Module und Plugins aktiviert werden
  müssen, damit Sie funktionieren.

Es gibt einige Situationen in denen diese Methode nicht funktioniert.

Manchmal ist es nötig, die Datei vor der Installation lokal zu
entpacken. Wenn Du eine Fehlermeldung erhältst, dass die Datei nicht im
richtigen Format vorliegt, ist es oft das Entpacken vorher nötig. Teste
die Installation der einzelnen Elemente nach dem Entpacken. Beachte,
dass die hochgeladenen Dateien noch mit dem Installer gepackt werden
müssen.

Manchmal kannst Du den automatischen Installer nicht nutzen. Zum
Beispiel überschreiten sehr große Erweiterungen die maximal erlaubte
upload-Größe Deines Hosts.

Auch, wenn ein solcher Fehler zu sehen ist:

    Warning: is_dir() [function.is-dir]: open_basedir restriction in effect. File(/) is not within the allowed path(s): ...

das passiert, wenn die Rechte des Hosting-Kontos eingeschränkt sind. Es
führt dazu, dass Joomla! versucht zu prüfen, ob das Root-Verzeichnis
vorhanden ist. Automatisches Installieren wird nicht möglich sein.

## Manuelle Installation

Zunächst werden alle Dateien in einem lokalen Verzeichnis entpackt (z.B.
`com_installer`). Anschließend wird das Verzeichnis via FTP unter das
Joomla! Installationsverzeichnis (z.B. `administrator/components`)
gelegt, je nachdem welcher Typ von Extension installiert werden soll (zu
sehen in einer Zeile der xml Datei, z.B.

). Jetzt kann die Erweiterung über Erweiterung-\>Verwalten -\>
Paketdatei hochladen installiert werden. Hier muss sicher gestellt
werden, dass der richtige Verzeichnispfad angegeben wird.
