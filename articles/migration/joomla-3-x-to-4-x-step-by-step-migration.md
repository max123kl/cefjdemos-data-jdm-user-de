<!-- Filename: Joomla_3.x_to_4.x_Step_by_Step_Migration / Display title: Joomla! 3.x nach 4.x: Migration - Schritt für Schritt -->

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Warnung!

Diese Anleitung geht davon aus, dass Joomla! 3.10.x verwendet wird. Wenn
eine frühere Version installiert ist, muss zuerst ein Upgrade auf
Joomla! 3.10.x durchgeführt werden, bevor auf Joomla! 4 umgestellt
werden darf. Es besteht kein Grund zur Eile. Bitte vorher alle
Erweiterungen für Joomla 4.x vorbereiten. Joomla 3.10.x wird bis zum 16.
August 2023 unterstützt.


Diese Dokumentation enthält eine Schritt-für-Schritt-Anleitung, um eine
3.10.x Webseite nach Joomla! 4.x zu migrieren. Zwar gibt es hunderte von
verschiedenen Szenarien, aber hier zeigen wir die grundlegende
Vorgehensweise zum Nachvollziehen. Sehr komplexe Migrationen werden
wahrscheinlich eine Folge von installierten Erweiterungen von
Drittanbietern sein. Dann sollte vorab Kontakt zu den Entwicklern der
installierten Erweiterung(en) aufgenommen werden, um den bestmöglichen
Migrationsweg zu erfahren.

## Einführung

Die Migration von Joomla! 3.10.x nach 4.x gilt als Mini-Migration. Das
bedeutet, dass die Joomla! Kernerweiterungen über die Joomla!
Update-Komponente auf der Backend-Administratoren-Seite per
„Ein-Klick-Upgrade“ Upgrade aktualisiert werden. Viele Drittanbieter
Erweiterungen sind ebenfalls als „Ein-Klick-Upgrade“ aktualisierbar,
einige jedoch nicht. Man muss sich jede einzelne ansehen und bestimmen
welchen Weg man gehen muss, um von 3.10.x auf 4.x zu migrieren. Falls
das noch nie getan wurde, könnte es interessant sein, die [Schritt für
Schritt Migration -
Selbsteinschätzung](https://docs.joomla.org/Migration_Step_by_Step_Self_Assessment "Special:MyLanguage/Migration Step by Step Self Assessment")
und  Planen für die Mini-Migration - Joomla 3.10 nach
4.x
zu lesen, bevor man die folgenden Schritte ausführt.
Joomla! Kern-Erweiterungen sind:

- Kategorien
- Beiträge
- Menüs
- Module (Kern Module - keine Drittanbieter)
- Aktions-Protokolle
- Banner
- Felder
- Inhalts Versionen
- Kontakte
- Nachrichten
- Newsfeeds
- Weiterleitungen
- Suche (Entkoppelt in 4.x. Bestehende 3.x-Sites werden trotzdem
  migriert. Wir empfehlen jedoch, in Zukunft den „Suchindex“ zu
  verwenden. Siehe die Hinweise unter „Jede Erweiterung einschätzen“)
- Suchindex
- Schlagwörter (Tags)
- Weblinks (entkoppelt, aber die Site verwendet sie möglicherweise und
  sie werden migriert. Siehe die Hinweise unter „Jede Erweiterung
  einschätzen“)

## Schritt für Schritt

### Eine Entwicklungsumgebung einrichten

1.  Bevor mit den Arbeiten fortgefahren wird, muss sichergestellt sein,
    dass die neueste Version von Joomla! 3.10.x installiert ist.
2.  Es muss ein Backup der aktuellen 3.10.x Website erstellt werden.
    Dazu kann ein empfohlenes Tool verwendet werden (siehe „Empfohlene
    Tools“ am Ende der Seite) oder man führt es manuell durch.
    -  Backup Grundlagen für eine Joomla!
      Webseite
    -  Was ist die empfohlene Vorgehensweise für ein
      Seiten-Backup?
3.  Bevor man fortfährt, sollte sichergestellt sein, dass die vorhandene
    Systemumgebung die
    <a href="https://downloads.joomla.org/technical-requirements"
    class="external text" target="_blank"
    rel="noreferrer noopener">technischen Voraussetzungen für Joomla! 4</a>
    erfüllt.
4.  Eine neue Datenbank und einen neuen Benutzer anlegen, um die 3.10.x
    Website wiederherzustellen.
5.  Anlegen einer Test-Site oder eines Build-Bereichs für die Arbeit und
    Wiederherstellung der Sicherungskopie der 3.10.x Website an einem
    der folgenden Orte:
    - Einer Subdomain.
    - Einem Unterverzeichnis.
    - Einem lokalen Laufwerk. Für Joomla! gibt es eine detaillierte
      Anleitung zur Installation von
      <a href="https:/https://docs.joomla.org/XAMPP" class="external text"
      target="_blank" rel="nofollow noreferrer noopener"
      title="Special:MyLanguage/XAMPP">XAMPP-Seite</a>. Allerdings sind
      <a href="https://www.wampserver.com/en/" class="external text"
      target="_blank" rel="nofollow noreferrer noopener">WAMP</a>,
      <a href="https://www.mamp.info/de/windows/" class="external text"
      target="_blank" rel="nofollow noreferrer noopener">MAMP</a> und
      <a href="https://sourceforge.net/projects/lampas/" class="external text"
      target="_blank" rel="nofollow noreferrer noopener">LAMP</a> alles
      geeignete Alternativen.
    - Einem neuen Hosting-Account auf einer temporären Domain im
      Stammverzeichnis. (Wenn im Zuge der Migration die Hosts gewechselt
      werden sollen).
      - Wiederherstellung einer Website auf einem lokalen Rechner. Siehe
         Lokale
        Joomla-Installation
        und  Einrichten des Rechners für die
        Joomla-Entwicklung.
      - Wiederherstellen der Website mit einem der unten auf der Seite
        aufgeführten Tools (bitte die Entwicklerdokumentation lesen).
6.  In einem Testumfeld sollte die Joomla! 3.10.x-Instanz auf die
    neueste unterstützte Version aktualisiert werden.
7.  Prüfen, ob das Datenbankschema auf die neueste Version 3.10.x
    aktualisiert ist, indem aus dem Dropdown-Menü
    **Erweiterungen **→** Verwalten **→** Datenbank** aufgerufen wird.
    Wenn das Schema nicht auf dem neuesten Stand ist, wie im folgenden
    Bild zu sehen, klickt man auf die Schaltfläche **Reparieren**:<img
    src="https://docs.joomla.org/images/thumb/6/61/J310-admin-extension-database-fix-en.png/800px-J310-admin-extension-database-fix-en.png"
    class="thumbborder" decoding="async"
    srcset="https://docs.joomla.org/images/thumb/6/61/J310-admin-extension-database-fix-en.png/1200px-J310-admin-extension-database-fix-en.png 1.5x, https://docs.joomla.org/images/thumb/6/61/J310-admin-extension-database-fix-en.png/1600px-J310-admin-extension-database-fix-en.png 2x"
    data-file-width="2560" data-file-height="812" width="800" height="254"
    alt="J310-admin-extension-database-fix-en.png" />
8.  Den Papierkorb leeren: Befinden sich noch irgendwelche Einträge im
    Papierkorb? Wenn ja, sollten diese gelöscht werden (und alle
    dazugehörigen Medien, wenn sie nicht an anderer Stelle auf der
    Website verwendet werden). Beiträge (auch Kategorien und
    Menüeinträge), die sich im Papierkorb befinden, können zu Problemen
    beim erfolgreichen Abschliessen einer Migration führen.
9.  Testen.
10. Noch einmal ein Backup machen.

### Jede Erweiterung einschätzen

In der
Planung
wurde bestimmt, welche Erweiterungen von Drittanbietern erhalten bleiben
oder entfernt werden und wie sie migriert werden. Für diesen Teil der
Schritt-für-Schritt-Anleitung werden zwei verschiedene Bereiche der
Seite besonders genutzt. Die Kompatibilitätsprüfung in

Komponenten

 Kompatibilitätsprüfung.

1.  Verwenden der **Kompatibilitätsprüfung**: Um die
    Kompatibilitätsprüfung verwenden zu können, muss die Joomla!
    Update-Komponente auf Joomla 4 eingestellt sein. Dazu geht man wie
    folgt vor:
2.  Zu **Komponenten **→** Joomla-Update** wechseln. (Hier sollte
    stehen, dass keine Updates gefunden wurden. Wenn das nicht der Fall
    ist, dann muss Joomla auf die neueste Version *3.10.x* aktualisiert
    und getestet werden. Danach ein weiteres Backup machen.) Jetzt auf
    die Schaltfläche Optionen in der oberen rechten Ecke klicken.
3.  Aus der Dropdown-Liste für den Update-Server *Joomla Next*
    wählen.<img
    src="https://docs.joomla.org/images/thumb/b/b7/Migration_J3toJ4_update_channel-de.png/800px-Migration_J3toJ4_update_channel-de.png"
    class="thumbborder" decoding="async"
    srcset="https://docs.joomla.org/images/thumb/b/b7/Migration_J3toJ4_update_channel-de.png/1200px-Migration_J3toJ4_update_channel-de.png 1.5x, https://docs.joomla.org/images/b/b7/Migration_J3toJ4_update_channel-de.png 2x"
    data-file-width="1202" data-file-height="634" width="800" height="422"
    alt="Migration J3toJ4 update channel-de.png" />
4.  Auf *Speichern & Schließen* klicken
5.  Anschließend zeigt Joomla die installierte Version, die neueste
    Joomla!-Version und die URL für das Update-Paket an. Außerdem werden
    noch einmal die Anforderungen für Joomla 4 angezeigt. Falls die
    Prüfung feststellt, dass entweder ein inkompatibles System oder
    inkompatible Erweiterungen vorhanden sind, wird das hier gemeldet.
    Bitte diese Seite genau prüfen.<img
    src="https://docs.joomla.org/images/thumb/a/a7/J310-admin-update_to_4-pre_update_check-de.png/800px-J310-admin-update_to_4-pre_update_check-de.png"
    class="thumbborder" decoding="async"
    srcset="https://docs.joomla.org/images/thumb/a/a7/J310-admin-update_to_4-pre_update_check-de.png/1200px-J310-admin-update_to_4-pre_update_check-de.png 1.5x, https://docs.joomla.org/images/a/a7/J310-admin-update_to_4-pre_update_check-de.png 2x"
    data-file-width="1352" data-file-height="753" width="800" height="446"
    alt="J310-admin-update to 4-pre update check-de.png" />
6.  Auf der Registerkarte Installationsprüfung der Joomla
    Update-Komponente findet sich die Kompatibilitätsprüfung und die
    Drittanbieter Erweiterungsprüfungen. Wenn eine geplante Erweiterung
    hier nicht aufgeführt ist, sollte sie zu der Liste der zu
    untersuchenden Erweiterungen hinzugefügt werden.
7.  Wenn in der Vergangenheit von Joomla! 2.5 auf 3.x migriert wurde, so
    kann es sein, dass noch einige Erweiterungen vorhanden sind, die
    bereinigt werden müssen. Nachfolgend sind ältere 2.5 oder 3.x
    Erweiterungen aufgeführt, die vor dem Update auf Joomla 4
    deinstalliert werden müssen:
    - plg_content_geshi
    - Bluestork Administrator Template
    - Beez_20
    - Beez5
    - Atomic

    1.  Wenn es um Templates geht, sollten alle Core Frontend- oder
        Backend-Templates außer Protostar und Beez3 (Frontend-Templates)
        und Isis oder Hathor (Administrator-Templates) deinstalliert
        werden. **Hinweis: Protostar ist *nicht* kompatibel mit Joomla
        4**. Nach der Migration wird das Template entfernt. Ein Template
        muss als "Standard" ausgewählt werden und Protostar oder Beez3
        können verwendet werden. Protostar wird bei der Migration auf
        Joomla 4.x entfernt.
    2.  Wenn weitere Dateien gefunden werden, die deinstalliert werden
        müssen, sollte man sie zu dieser Seite hinzufügen. Da dies ein
        Wiki ist, kann jeder die Seite ergänzen. Vielen Dank im Voraus
        für eure Hilfe.
8.  Ob eine Erweiterung kompatibel ist oder nicht, lässt sich an den
    Tags erkennen. Diese Tags geben in der Regel ein eindeutiges Bild
    ab, ob sie Nein oder Ja bedeuten. Steht dort „Update-Informationen
    nicht verfügbar“, bedeutet das, dass der Entwickler der Erweiterung
    kein Tag in seiner Erweiterung verwendet hat, sodass man nicht weiß,
    ob sie mit Joomla 4 kompatibel ist oder nicht. Zur Überprüfung
    sollte man mit dem Entwickler sprechen.
9.  **Erweiterungen aktualisieren**: Zuerst alle Erweiterungen
    aktualisieren, die in auf der Website verbleiben sollen. In Joomla!
    3.10.x kann man zu **Erweiterungen → Aktualisieren** gehen und auf
    **Updates suchen** klicken. Dadurch wird ein Hinweis in der Spalte
    *Version* unter dem Menüpunkt *Verwalten* hinzugefügt, der einige
    Kompatibilitätsinformationen aus dem Backend enthält. Diese Funktion
    unterstützt nur Erweiterungen, die über die Registerkarte Update des
    Erweiterungsmanagers aktualisiert werden. Wenn Erweiterungen
    installiert sind, die nicht die Joomla-Erweiterungsaktualisierung
    verwenden, müssen sie, wie unten beschrieben, manuell überprüft
    werden. Das Gleiche gilt für die Erweiterungen, die einen Hinweis
    (Tooltip) haben. Die Art des Pakets und der Migrationspfad muss mit
    dem Entwickler der Erweiterung geklärt werden, um festzustellen, wie
    die Aktualisierung/Migration erfolgen soll.
10. Um Erweiterungen zu untersuchen und zu deinstallieren Erweiterungen:
    nach **Erweiterungen **→** Verwalten** wechseln
11. Auf die Schaltfläche *Suchwerkzeuge* klicken, um die Filteroptionen
    anzuzeigen
12. Aus dem Dropdown-Menü *Typ wählen* die Option „Paket“ auswählen.<img
    src="https://docs.joomla.org/images/thumb/8/8c/J310-admin-extension-manage-package-de.png/800px-J310-admin-extension-manage-package-de.png"
    decoding="async"
    srcset="https://docs.joomla.org/images/8/8c/J310-admin-extension-manage-package-de.png 1.5x"
    data-file-width="1000" data-file-height="370" width="800" height="296"
    alt="J310-admin-extension-manage-package-de.png" />Es wird
    empfohlen, zuerst „Paket“ zu wählen, da bei der Deinstallation eines
    Pakets automatisch die zugehörigen Module, Plugins und alle anderen
    Komponenten des Pakets auf einmal deinstalliert werden.
13. Deinstallieren aller Pakete, die nicht mehr benötigt werden oder die
    nicht nach Joomla 4 migriert werden sollen.
14. Den Vorgang für alle Typen im Dropdown-Menü auf der Registerkarte
    Verwalten wiederholen: Komponente, Datei, Sprache, Bibliothek,
    Modul, Plugin und Template. Falls der Urheber "Joomla! Projekt"
    angegeben ist, dann diese Erweiterungen unverändert lassen. Für alle
    anderen gilt: Deinstallieren der Erweiterungen, die nicht verwendet
    werden oder nicht mit Joomla! 4.x kompatibel sind. **HINWEIS!** Es
    ist nicht möglich, ein Template zu deinstallieren, das als Standard
    eingestellt ist. Daher muss ein von Core unterstütztes Template wie
    Beez3 oder Protostar ausgewählt und dann deinstalliert werden, wenn
    dies erforderlich ist. Eine weitere Anmerkung: **Protostar ist nicht
    kompatibel mit Joomla 4.x**. Nach der Migration wird es verschwunden
    sein. Falls es als Standardtemplate ausgewählt wird, wird es einfach
    zu Joomla 4.x migriert.
15. Alle Paket- und Komponentenversionen, die auf der Website
    installiert bleiben sollen, müssen erfasst werden. Dazu kann man sie
    zu Referenzzwecken einfach in ein Dokument kopieren und einfügen.
16. Für alle Erweiterungen, die nicht über den Erweiterungsmanager mit
    einem Klick (**Erweiterungen → Verwalten → Aktualisieren**) auf den
    neuesten Stand gebracht werden können, müssen manuell aktualisiert
    werden.
17. Vor und während der Aktualisierung ist darauf zu achten, ob die
    Erweiterungen, im gleichen Paket, für die Version 3.10.x als auch
    für die Version 4.x vorbereitet sind. Wenn dies der Fall ist, lässt
    sich das „One-Click-Update“ problemlos durchführen. Ist dies nicht
    der Fall und haben 3.10 und 4.x unterschiedliche Pakete, muss von
    Fall zu Fall entschieden werden. Normalerweise trifft eines der
    folgenden Szenarien zu:
    - Die Erweiterung hat separate Pakete, beim Upgrade auf 4.x wird
      dies automatisch erkannt und sie funktioniert nach wie vor. Der
      Entwickler sollte dies bestätigen.
    - Die Erweiterung hat separate Pakete, die in 3.10.x deinstalliert
      und dann mit der Joomla 4.x Version neu installiert werden müssen,
      sobald die Seite migriert ist. Ein Beispiel hierfür könnte ein
      Inhalts-Plugin sein. Es ist sehr einfach, das in 3.10.x zu
      deinstallieren und es dann in 4.x wieder zu installieren.
    - Siehe  Überlegungen zum Template bei der
      Migration
      für weitere spezielle Informationen über Templates und
       Konvertieren eines Templates von einer früheren Joomla!
      Version

#### Anmerkungen zur Suche (com_search)

Die Suche (com_search) wird in Joomla 4.x abgekoppelt. Die Suche
(com_search) wird zu Joomla 4 migriert. Nach der Migration muss sie über
den com_installer auf die Joomla 4.x Version aktualisiert werden. Die
Suche wird weiterhin gepflegt, aber mehr auf die Art und Weise wie die
Erweiterung eines Drittanbieters, indem sie Updates über den
com_installer erhält. Wir empfehlen, in Zukunft Smart Search
(com_finder) zu verwenden. Die Suche wird weiterhin unter
<a href="https://extensions.joomla.org/category/official-extensions/"
class="external free" target="_blank"
rel="noreferrer noopener">https://extensions.joomla.org/category/official-extensions/</a>
verfügbar sein.

#### Anmerkungen zu Weblinks

Weblinks wurde bereits in Joomla 3.4 ausgelagert. Wenn es auf einer
2.5-Seite verwendet wurde, würde der Migrationsprozess dies bemerken und
die Weblinks-Komponente und Daten migrieren. Für die Migration von
3.10.x nach 4.x wird es genauso sein. Die Komponente ist nach wie vor
verfügbar und wird in der JED unter
<a href="https://extensions.joomla.org/category/official-extensions/"
class="external text" target="_blank" rel="noreferrer noopener">Official
Extensions</a> gepflegt.

#### Anmerkungen zum Legacy-Routing

Legacy-Routing wird in Joomla 4.x nicht mehr verfügbar sein. Wenn die
Migration vorgenommen wird und Legacy-Routing benutzt wird, stellt das
System automatisch auf Modern-Routing um. Nach der Umstellung auf Joomla
4.x und bevor die Website online geht, sollte ein „Broken Link Checker“
eingesetzt werden.

### Der Umstieg auf Joomla! 4.x

Sobald die Erweiterungen von Drittanbietern entweder aktualisiert oder
deinstalliert wurden, sodass nur noch die mit Joomla! 4 kompatiblen
Erweiterungen in der Installation vorhanden sind, geht es mit den
folgenden Schritten weiter:

1.  Wechseln zu
    **System **→** Site **→** Konfiguration **→** Registerkarte
    „Server“** und die Einstellungen für die Fehleranzeige von
    Systemstandard auf Maximum ändern. Dann auf Speichern & Schließen
    klicken. <img
    src="https://docs.joomla.org/images/thumb/1/1e/J310-system-global-config-server-tab-de.png/500px-J310-system-global-config-server-tab-de.png"
    class="thumbborder" decoding="async"
    srcset="https://docs.joomla.org/images/thumb/1/1e/J310-system-global-config-server-tab-de.png/750px-J310-system-global-config-server-tab-de.png 1.5x, https://docs.joomla.org/images/1/1e/J310-system-global-config-server-tab-de.png 2x"
    data-file-width="829" data-file-height="625" width="500" height="377"
    alt="J310-system-global-config-server-tab-de.png" />
2.  Ein weiteres Backup vornehmen.
3.  Weiterfahren mit **Komponenten **→** Joomla Update**. (Hier sollte
    stehen, dass keine Updates gefunden wurden. Wenn das nicht der Fall
    ist, sollte Joomla auf die neueste Version aktualisiert und getestet
    werden. Dann nochmal ein Backup machen). Jetzt auf die Schaltfläche
    Optionen in der oberen rechten Ecke klicken.
4.  Aus der Dropdown-Liste für den Update-Server *Joomla Next*
    auswählen.<img
    src="https://docs.joomla.org/images/thumb/6/69/J310-component-joomla-update-select-support-de.png/500px-J310-component-joomla-update-select-support-de.png"
    class="thumbborder" decoding="async"
    srcset="https://docs.joomla.org/images/thumb/6/69/J310-component-joomla-update-select-support-de.png/750px-J310-component-joomla-update-select-support-de.png 1.5x, https://docs.joomla.org/images/6/69/J310-component-joomla-update-select-support-de.png 2x"
    data-file-width="895" data-file-height="596" width="500" height="333"
    alt="J310-component-joomla-update-select-support-de.png" />
5.  Auf *Speichern & Schließen* klicken
6.  Danach wird die installierte Joomla-Version, die neueste
    Joomla!-Version und die URL für das Update-Paket angezeigt. Joomla
    wird wieder die Anforderungen für Joomla 4 zeigen. Falls ein
    inkompatibles System oder inkompatible Erweiterungen vorhanden sind,
    wird das hier angezeigt. Bitte unbedingt sorgfältig, ohne Zeitdruck,
    überprüfen.<img
    src="https://docs.joomla.org/images/thumb/4/40/J310-to-j4-dev-update-found-de.png/800px-J310-to-j4-dev-update-found-de.png"
    class="thumbborder" decoding="async"
    srcset="https://docs.joomla.org/images/4/40/J310-to-j4-dev-update-found-de.png 1.5x"
    data-file-width="1000" data-file-height="662" width="800" height="530"
    alt="J310-to-j4-dev-update-found-de.png" />
7.  Wenn das Update nicht angezeigt wird, zu
    **Erweiterungen **→** Verwalten **→** Aktualisieren** gehen und in
    der Toolbar auf „Leeren“ klicken. Jetzt sollte das Update auf
    Joomla! 4 angezeigt werden.
8.  Jetzt die Daumen drücken und für alle Fälle ein Backup bereithalten.
9.  Dann auf die Schaltfläche „Update installieren“ klicken.
10. Mit einem Tee kann die kleine Pause überbrückt werden bis die
    Statusleiste vollständig grün geladen ist. Wie lange dies dauert,
    hängt von der Website, der Internetverbindung und der
    Servergeschwindigkeit ab. Der Vorgang kann etwa zwei Minuten dauern.
    Wenn die Aktualisierung abgeschlossen ist, wird vermutlich eine
    Abmeldung beim Administrator erfolgen. Bitte erneut anmelden.
    Zweimal.
11. Wenn alles geklappt hat, wird die Administrationsoberfläche im
    Backend völlig neu aussehen.<img
    src="https://docs.joomla.org/images/thumb/b/bb/J4-administrator-overview-de.png/800px-J4-administrator-overview-de.png"
    class="thumbborder" decoding="async"
    srcset="https://docs.joomla.org/images/b/bb/J4-administrator-overview-de.png 1.5x"
    data-file-width="1000" data-file-height="461" width="800" height="369"
    alt="J4-administrator-overview-de.png" />
12. Zu **System **→** Wartung **→** Datenbank** wechseln und auf
    *Reparieren* klicken, falls irgendwelche Fehler angezeigt werden.
13. Zu **System **→** Installieren **→** Überprüfen** wechseln auf
    *Überprüfen* klicken und nachsehen, ob noch irgendwelche
    Erweiterungen zu installieren sind. (Es sollte keine vorhanden
    sein!)
14. Nun zum Frontend der Website gehen und nachsehen, ob sie angezeigt
    wird, selbst wenn es sich nicht um das richtige Template handelt.
    Wenn ja, kann es weitergehen. Wenn nicht, siehe  „Häufige
    Migrations-Fehler“.
15. Ein neues Backup erstellen.
16. Das neue Template oder andere Erweiterungen installieren, falls
    vorhanden. Häufig ein weiteres Backup erstellen.
17. Alles konfigurieren – häufig sichern.
18. Einen Link-Checker starten und alle defekten Links reparieren.
19. Alles testen – oft sichern.
20. Wenn alles wie erwartet funktioniert, die Fehleranzeige auf Standard
    zurücksetzen
    (**System → Einstellungen → Konfiguration → Registerkarte
    „Server“**). Nicht vergessen: Speichern & Schließen.

### Mit der Joomla! 4.x-Website online gehen

1.  Sobald das System in Betrieb genommen werden kann, sollte ein
    letztes Mal ein Backup der 3.10-Website erstellt werden. Sichern in
    ein Unterverzeichnis oder einer Subdomain, falls gewünscht.
2.  Sichern der Joomla! 4.x Seite und umziehen oder wiederherstellen der
    Joomla! 4.x Site in das Stammverzeichnis (oder den Nameserver
    ändern), falls sie auf einer temporären Domain im Stammverzeichnis
    eines neuen Hosting-Accounts erstellt wurde.
3.  Erneut testen.
4.  Falls in der Vergangenheit Sicherheitsänderungen an der
    .htaccess-Datei vorgenommen wurden, muss möglicherweise eine Zeile
    (oder mehrere Zeilen) darin geändert werden, um ein Update auf die
    nächste Version von Joomla 4 zu ermöglichen. Siehe
    <a href="https://docs.joomla.org/Htaccess_changes_after_joomla4.0.4"
    class="external text" target="_blank"
    rel="noreferrer noopener">Htaccess-Änderungen nach Joomla 4.0.4</a>
    um festzustellen, ob die Datei geändert werden muss oder nicht.

Übersetzt mit www.DeepL.com/Translator (kostenlose Version)

1.  Die Website von Joomla! 3.10 innerhalb von ein paar Tagen vom Server
    entfernen. Es sei denn, die Datei *robots.txt* wurde so bearbeitet,
    dass sie die Suchmaschinen-Spider blockiert.
2.  Alle Entwicklungsseiten, mit denen gearbeitet wurde, entfernen oder
    auf den neuesten Stand bringen, falls sie auf einer aktuellen
    Version laufen, um Hacking-Versuche auf dem Server abzuwehren.

Wenn sich während der Migration auf 4.x Daten auf der 3.10-Site geändert
haben, sollten diese Daten auf die 4.x-Site übertragen werden, bevor das
System online geht. Das kann manuell geschehen (man muss darauf achten,
dass die Benutzer-IDs gleich bleiben – der Reihe nach vorgehen) oder mit
Hilfe einer <a
href="https://extensions.joomla.org/category/migration-a-conversion/data-import-a-export%20transfer%20tool/third-party%20extension/"
class="external text" target="_blank"
rel="noreferrer noopener">Drittanbieter-Erweiterung</a>.

## Empfohlene Tools

- <a
  href="http://extensions.joomla.org/extensions/access-a-security/site-security/backup/1606"
  class="external text" target="_blank" rel="noreferrer noopener">Akeeba
  Backup</a> ist sehr beliebt für Backups und Rücksicherungen. Mehr
  unter <a href="https://extensions.joomla.org/tags/backup/"
  class="external text" target="_blank"
  rel="noreferrer noopener">Backup-Tools</a>.

## Verwandte Informationen
