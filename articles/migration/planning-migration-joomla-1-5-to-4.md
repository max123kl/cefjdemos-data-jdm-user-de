<!-- Filename: Planning_Migration_-_Joomla_1.5_to_4 / Display title: Planung der Migration von Joomla! 1.5 nach 4 -->

Ausgehend von Joomla! 1.5 nach 4 ist das Upgrade als große Migration zu
bezeichnen. Dies bedeutet erhebliche Veränderungen wie Joomla!
funktioniert. Der Aufbau von Tabellen und der grundlegenden Technologie
haben sich stark verändert dass eine Migration nötig ist, statt ein
Upgrade oder Update. Beide Erweiterungstypen, die Joomla! Kern-nahen
Erweiterungen und alle Erweiterungen von Drittanbietern müssen die
Migration auf Joomla! 4 vollziehen. Dies betrifft auch das Template.
Jedes einzelne Element muss betrachtet, geplant, entschieden und
ausgeführt werden. Die große Migration erfordert Fleiß, Konzentration
und eine gute Planung im gesamten Prozess.

## Einleitung

Das Gute an einer Migration ist die Gelegenheit, die Webseiten-Ziele neu
zu bedenken, ihr ein frisches Aussehen (Template) zu geben, Aufzuräumen
und die Webseite mit neuen Funktionen und Bereichen weiter zu
entwickeln. Gehe organisiert mit Deinen Ideen, Gedanken und Plänen an
die Migration heran. Eine gute Planung macht die Umsetzung leichter.

Mit der Planung solltest Du Dir die folgenden Fragen stellen oder die
unten aufgeführten Aufgaben Schritt für Schritt abarbeiten. Je komplexer
die Webseite, desto größer ist der Aufwand. Leider gibt es keinen
Masterplan für jedes mögliche Szenario.

Konkrete Fragen kannst Du im
<a href="https://forum.joomla.org/viewforum.php?f=808" class="extiw"
title="jforum:808">Joomla 4.x General Questions/New to Joomla 4.x
Forum</a>. stellen.

## Planungsschritte

### Allgemeines

1.  Prüfe die ursprünglichen Ziele der Webseite. Eine Migration ist ein
    guter Zeitpunkt den Fokus neu auszurichten.
2.  Unterstützt der Server oder Webspace die erforderlichen
    <a href="http://www.joomla.org/about-joomla/technical-requirements.html"
    class="external text" target="_blank"
    rel="noreferrer noopener">technischen Mindestanforderungen</a> für
    Joomla! 4? Wenn nicht, sollte der Hoster kontaktiert werden. Wird
    über einen Wechsel des Webhosters nachgedacht? Die Migration ist ein
    guter Zeitpunkt.
3.  Welche Entwicklungsumgebung soll eingesetzt werden? Lokal, Subdomain
    oder Unterordner auf dem Webspace? Ein neuer Server oder ein neues
    Webhostingpaket?

### Joomla Kern

1.  Räum auf Deiner bisherigen Webseite auf. Betrachte die Bereiche,
    Kategorien und Beiträge. Bereiche werden ab Joomla! 2.5 als oberste
    Kategorien eingesetzt. Entferne unnötige Inhalte, diese müssen dann
    auch nicht migriert werden. Du kannst auch eine Liste anfertigen, um
    einen besseren Überblick beim Aufräumen zu haben.
2.  Sortiere die Inhalte auf der aktuellen Webseite. Machen alle
    Kategorien Sinn oder können einige weg? Mach auch hier eine Liste
    mit den Kategorien - welche werden in der neuen Website benötigt?
3.  Befinden sich Beiträge im Papierkorb? Weg damit (und damit alle
    verbunden Medien, wenn diese nicht an anderer Stelle eingesetzt
    sind). Beiträge (auch Kategorien und Menüpunkte) die sich im
    Papierkorb befinden, können doppelte Alias-Einträge nach der
    Migration verursachen.
4.  Der Media Manager: Entscheide Dich, ob Du das gesamte Verzeichnis
    /images übernehmen möchtest oder nur einen Teil davon. Um zu
    vermeiden, dass die Migration des Media Managers zur Katastrophe
    wird, solltest Du besser bestimmte Bilder oder Bildersammlungen per
    FTP oder cPanel sichern und dann wieder in die migrierte Seite
    hochladen. So vermeidest Du Probleme und mußt nicht die vollen
    Ordner in die Migration einbeziehen. Strukturiere die Ablage des
    Mediamanagers sinnvoll, damit Dir das spätere Arbeiten damit
    leichter fällt.
5.  Werden Kern-Komponenten wie Kontakte, Weblinks oder Newsfeeds
    eingesetzt? Notiere Dir, was Du davon nach der Migration noch
    benötigst.
6.  Prüfe Deine Menüs. Möchtest Du alle Einträge noch nach der Migration
    einsetzen oder können einige gelöscht werden? Lösche auch die
    Einträge im Papierkorb, um doppelte Aliase zu verhindern.
7.  Wenn Du das Design wechselst, änderst oder die Navigation
    umstrukturierst, achte auf veraltete Seiten die ggf. noch verlinkt
    sind. Richte dafür falls nötig eine Umleitung ein und verfolge alle
    möglichen URLs. Bei komplexen Seiten solltest Du dir Notizen machen
    oder eine tabellarische Übersicht anlegen.
8.  Hast Du den Joomla! Kern Deiner 1.5 Seite "gehackt"? Wenn ja, dann
    werden diese Änderungen die Migration nicht überstehen. Es gibt
    andere, sicherere Lösungen, als den Kern zu "hacken". Informiere
    Dich vor der Migration über mögliche Alternativen und "Overrides" um
    die Ausgaben vom Kern in Joomla! 4 zu überschreiben (<a
    href="https://docs.joomla.org/How_to_override_the_output_from_the_Joomla!_core"
    class="new"
    title="Special:MyLanguage/How to override the output from the Joomla! core (page does not exist)">How
    to override the output from the Joomla! core</a>, [Understanding
    Output
    Overrides](https://docs.joomla.org/Understanding_Output_Overrides "Special:MyLanguage/Understanding Output Overrides"),
     Layout Overrides in
    Joomla.
9.  Prüfe den User Manager. Möchtest Du alle Nutzer in die neue Version
    mitnehmen? Ist ein Aufräumen angebracht? Vielleicht existieren noch
    Super Administratoren die nicht länger einen Zugriff haben dürfen
    oder auch etwaige Spam-Benutzer, die man löschen sollte? Verwendest
    Du Erweiterungen von Drittanbietern um die Benutzerprofile zu
    optimieren oder zu verwalten? Dieser Schritt erfordert eine
    sorgfältige Planung. Ganz besonders wenn die Nutzer häufig ihre
    Daten ändern.
10. Gibt es neue Funktionen von Joomla! 4 die Du verwenden möchtest? Zum
    Beispiel die Zugriffskontrolle / Access Control Levels (ACLs) oder
    Tags, Workflows oder Custom Fields? Wenn ja, dann plane es gleich
    mit in die Migration ein. Das Planen der Zugriffsebenen (ACLs)
    erfordert Disziplin und Vorsicht. Gründlichkeit ist hier sehr
    wichtig.

### Erweiterungen von Drittanbietern

1.  Mach Dir eine Liste aller Erweiterungen von Drittanbietern. Diese
    beinhaltet Komponenten, Module, Plugins, Sprachen und Templates. Du
    kannst sie von der Seite Verwalten kopieren und in ein Dokument
    einfügen, wenn du sie benötigst oder fertige Dir einfach eine Liste
    an. Ein Blatt Papier und ein Stift genügen. Kategorisiere auf der
    Liste die Erweiterungen nach dem Nutzungsgrad (häufig, mittel,
    selten oder gar nicht).
2.  Prüfe welche Erweiterung von Drittanbietern zuverlässig eine
    Migration nach Joomla! 4 unterstützen. Informiere Dich auf der Seite
    des jeweiligen Entwicklers.
3.  Werden wirklich alle Erweiterungen benötigt? Möglicherweise bringt
    Joomla! 4 bereits gewünschte Funktionen mit, die eine Erweiterung
    unnötig machen.
4.  Was ist mit dem Template? Ist es ein gekauftes Template? Wird
    möglicherweise eine 4.x-Version angeboten? Willst Du dieses Template
    weiter nutzen? Gibt es eine Upgrade-Möglichkeit beim Entwickler? Ist
    die neue Version responsiv und unterstützt sie mobile Geräte? Wurde
    das Template für den Kunden entwickelt oder handelt es sich um ein
    stark angepasstes Drittanbieter-Template? Für eine Anpassung des
    Templates siehe  Template Considerations During
    Migration.
5.  Wenn Du Dein Template änderst, wie sieht es mit aktuellen Bildern
    aus? Zum Beispiel wenn Deine Webseite einen weißen Hintergrund hat
    und Dein Logo oder andere Bilder sind .jpg-Bilder mit weißem
    Hintergrund, wird es nicht schön schön aussehen wenn das neue
    Template einen farbigen Hintergrund besitzt.
6.  Änderst Du das Design oder die Navigation der Webseite, achte auf
    veraltete Einträge die ggf. eine Umleitung erfordern.

<a
href="https://docs.joomla.org/Joomla_1.5_to_4.x_Step_by_Step_Migration"
id="content-button" class="button expand">Die Migration von Joomla! 1.5
nach 4.x Schritt für Schritt</a>
