<!-- Filename: J4.x:CLI_Database_Exporter_Importer / Display title: CLI Datenbank Export Import -->

## Einführung

Bevor Sie Joomla! aktualisieren oder eine Drittanbieter-Erweiterung installieren, wird dringend empfohlen, dass Sie Ihre Website sichern. Die Joomla! Kommandozeilenoberfläche (CLI) bietet Befehle zum Exportieren (Sichern) und Importieren (Wiederherstellen) Ihrer Joomla! Datenbank an. Beachten Sie, dass das Dateisystem nicht gesichert wird, dies sollte separat erfolgen.

## Anforderungen

Um diese Befehle zu verwenden, benötigen Sie Terminalzugriff auf den Host, auf dem die Seite installiert ist. Dies kann bei Shared Hosting ein Problem sein! Sie benötigen zudem grundlegende Kenntnisse über Linux-Shell-Befehle wie ls und cd. Wenn all dies nicht vertraut ist, sollten Sie wahrscheinlich Akeeba Backup verwenden, die beliebteste Backup- und Wiederherstellungserweiterung, die für die grundlegende Nutzung kostenlos ist.

## Speicherort für temporäre Sicherungen

Achten Sie darauf, einen geeigneten Speicherort für eine Sicherungskopie auszuwählen. Er sollte sich innerhalb Ihres persönlichen Dateibereichs, aber außerhalb Ihres Webbaums befinden. Das Ziel ist es, eine Sicherungsdatei zu erstellen, die Sie auf Ihren lokalen Computer oder einen anderen sicheren Ort herunterladen können, woraufhin Sie die Sicherungsdatei löschen können, um Speicherplatz zu sparen. Vermeiden Sie es, den System-Ordner /tmp zu benutzen, der von jedem Nutzer gelesen werden kann. Der beste Ort ist Ihr persönlicher tmp-Ordner. Die Ordnerstruktur sieht folgendermaßen aus:
```
|-/home/username/tmp - Ihr persönlicher tmp-Ordner
|-/home/username/public_html - Ihr Joomla-Stammverzeichnis
```

## Anleitungen

Melden Sie sich bei Ihrem Host an und gehen Sie zum Stammverzeichnis Ihrer Website.
```
cd /home/username/public_html
```

- Listen Sie alle verfügbaren CLI-Befehle auf:
```sh
  php cli/joomla.php list
```
- Exportieren Sie die Datenbank in den tmp-Ordner des Kontos:
```sh
  php cli/joomla.php database:export --folder /home/username/tmp/mydbname
```
- Importieren Sie die Datenbank aus einem Ordner:
```sh
php cli/joomla.php database:import --folder /home/username/tmp/mydbname
```

Sie können auch:

- Die Datenbank als .zip-Datei exportieren:
```sh
php cli/joomla.php database:export --zip --folder /home/username/tmp/mydbname
```
- Eine Tabelle exportieren:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --folder /home/username/tmp/mydbname
```
- Eine Tabelle als .zip-Datei exportieren:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --zip --folder /home/username/tmp/mydbname
```
- Eine Tabelle importieren:
```sh
php cli/joomla.php database:import --table xxxxx_action_log_config --folder /home/username/tmp/mydbname
```
- Falls Sie Hilfe benötigen:
```sh
php cli/joomla.php database:export --help
php cli/joomla.php database:import --help
```

## Sicherung

Um ein vollständiges Backup von Ordnern, Dateien und der Datenbank zu erstellen, führen Sie diese Befehle aus:

1. Archivieren Sie Ihr Joomla-Stammverzeichnis:
```sh
tar --exclude='/home/username/public_html/tmp' -zcvf /home/username/tmp/joomla_bak.tgz /home/username/public_html > /home/username/tmp/joomla_bak.log
```
2. Exportieren Sie die gesamte Joomla-Datenbank aus dem Joomla-Stammverzeichnis:
```sh
php cli/joomla.php database:export --folder /home/username/tmp/db_bak
```

## Wiederherstellen

Um es wiederherzustellen, stellen Sie zuerst sicher, dass die Datenbank und der Datenbankbenutzer existieren. Führen Sie dann diese Befehle aus:

1. Archiv extrahieren:
```sh
tar -xvf /home/username/tmp/joomla_bak.tgz --directory /home/username/public_html
```
2. Stellen Sie sicher, dass Sie sich im Stammverzeichnis Ihrer Website befinden:
```sh
cd /home/username/public_html
```
2. Joomla-Datenbank importieren:
```sh
php cli/joomla.php database:import --folder /home/username/tmp/db_bak
```

## Notizen

Bei den Optionen -zcvf und -xvf des tar-Befehls steht das v für verbose – eine Liste der verarbeiteten Dateien scrollt schnell über den Terminalbildschirm. Lassen Sie das v weg, um die Liste nicht zu sehen.
*Übersetzt von openai.com*

