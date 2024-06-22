<!-- Filename: J4.x:Workflow / Display title: Workflow -->

Joomla!  4.x

## Einleitung

Die Publishing-Workflow-Komponente wird benutzt, um die statischen
Zustände (unveröffentlicht, veröffentlicht, gelöscht und archiviert)
durch einen etwas allgemeineren Ansatz zu ersetzen. Auf diese Weise kann
ein maßgeschneiderter Ablaufplan einfach erzeugt werden, um die eigenen
Beiträge innerhalb einer Komponente zu handhaben.

- Die Beitragsübersicht im Backendbereich von Joomla 3.x:

<img
src="https://docs.joomla.org/images/thumb/a/a4/Article_view_3-en.png/800px-Article_view_3-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/a/a4/Article_view_3-en.png/1200px-Article_view_3-en.png 1.5x, https://docs.joomla.org/images/thumb/a/a4/Article_view_3-en.png/1600px-Article_view_3-en.png 2x"
data-file-width="2538" data-file-height="766" width="800" height="241"
alt="Article view 3-en.png" />

- Die Beitragsübersicht im Backendbereich von Joomla 4.x:

<img
src="https://docs.joomla.org/images/thumb/6/68/J4_Articles_Backend-de.png/800px-J4_Articles_Backend-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/6/68/J4_Articles_Backend-de.png/1200px-J4_Articles_Backend-de.png 1.5x, https://docs.joomla.org/images/thumb/6/68/J4_Articles_Backend-de.png/1600px-J4_Articles_Backend-de.png 2x"
data-file-width="1726" data-file-height="542" width="800" height="251"
alt="J4 Articles Backend-de.png" />

Der Bereich der Artikelwerkzeuge ist jetzt kompakter und die Ansicht
insgesamt aufgeräumter. Sie können benutzerdefinierte Stufen für die
Beiträge erstellen und sie in Kategorien gruppieren.

Es gibt ein eigenes Tutorial, welche die Schritte für das Erzeugen eines
eigenen ersten Workflows enthalten:
Szenarios.
Weitere Informationen über die Implementierung der Komponente in anderen
Bereichen findet man auf der Seite des Google Summer of Code Projekts
DOC:  Implementierung der Arbeitsschritte zur
Veröffentlichung

Workflows können jederzeit deaktiviert werden, wenn man „Beiträge“ oder
„Workflows“ aufruft und oben rechts auf „Optionen“ klickt. Dort zu der
Registerkarte „Integration“ wechseln und nach unten bis „Workflow
aktivieren“ scrollen.

## Begriffe & Definitionen

- *Workflows* Es können etliche Abläufpläne erstellt werden. Jeder
  Ablaufplan zeigt das Bearbeitungsstadium, mögliche Übergänge und den
  Zustand der Elemente.
- *Stadien:* Die Stadien könnte man als Schritt innerhalb eines
  Ablaufplans betrachten.
- *Status:* Der Status eines Artikels kann unveröffentlicht,
  veröffentlicht, „im Papierkorb“ oder archiviert sein. Ein Zustand kann
  geändert werden, indem ein Übergang ausgeführt wird.
- *Übergänge:* Übergänge finden zwischen den unterschiedlichen Stufen
  statt. Sie sind der Bereich, in dem die Aktionen stattfinden.
- *Kategorien:* Beitrage können Kategorien zugewiesen werden.

## Workflows

Der Workflow ähnelt einer Reihe von Arbeitsschritten. Er ist über das
obere Hauptmenü unter „Inhalt“ erreichbar. Man kommt dann zur
„Workflow-Liste“, einer Übersicht über alle bestehenden Workflows. Ein
Workflow enthält mehrere Stadien mit unterschiedlichen Konditionen.
Elemente (z.B. Beiträge) können diese Zustände durchlaufen.

<img
src="https://docs.joomla.org/images/thumb/d/d0/Workflows-de.png/800px-Workflows-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/d/d0/Workflows-de.png/1200px-Workflows-de.png 1.5x, https://docs.joomla.org/images/d/d0/Workflows-de.png 2x"
data-file-width="1490" data-file-height="524" width="800" height="281"
alt="Workflows List" />

- Hier sieht man den Status des Workflows (veröffentlicht / versteckt)
- Neben dem Status befindet sich der Titel. Mit einem Klick auf diesen
  Titel kann man *den Workflow bearbeiten*
  - *Editierbar*: Title \| Description \| Status \| Default Option \|
    Permissions (Rights Management)
- Neben dem Titel befindet sich die Option *Manage* / *Verwalte* die
  Ablaufplanstadien (weiterführende Informationen unter
  Stadien
- Wiederum neben den "Stadien" befindet sich die Option "als Standard
  setzen"
- Ein gelbes Kreissymbol unterhalb von "Als Standard" oder "default"
  repräsentiert die Zahl der bestehenden Stadien innerhalb dieses
  Ablaufplans
- Auch wieder neben dem gelben Kreis befindet sich ein blaues
  Pfeilsymbol, welches die Zahl der bestehenden Übergänge in diesem
  Ablaufplan zeigt (weiterführende Infos unter
  Übergänge
- Darüber hinaus zeigt die Übersicht das Datum, an dem der Ablaufplan
  erstellt wurde, den Author und eine ID.

## Stufen

Die Stufen können über den Container „Workflows List“ aufgerufen werden,
indem man auf das gelbe Symbol klickt, das die Anzahl der Stufen
anzeigt. Der Name einer Stufe kann durch einen Klick auf die Stufe
bearbeitet werden.


<img
src="https://docs.joomla.org/images/thumb/3/3a/Stages-de.png/800px-Stages-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/3/3a/Stages-de.png/1200px-Stages-de.png 1.5x, https://docs.joomla.org/images/3/3a/Stages-de.png 2x"
data-file-width="1487" data-file-height="362" width="800" height="195"
alt="Stages View" />

<img
src="https://docs.joomla.org/images/thumb/4/40/Stages--edit-de.png/800px-Stages--edit-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/40/Stages--edit-de.png/1200px-Stages--edit-de.png 1.5x, https://docs.joomla.org/images/4/40/Stages--edit-de.png 2x"
data-file-width="1484" data-file-height="707" width="800" height="381"
alt="The Edit Stage view" />

- Im zweiten Bild kann die Stufe bearbeitet werden. Man kann sie
  aktivieren oder deaktivieren und eine Notiz verfassen. Es gibt auch
  einen Umschalter für „Standard“. Wenn nur ein Element vorhanden ist,
  lässt sich dieses nicht umschalten.

## Übergänge

Beiträge können von einer Stufe in eine andere übergehen. Die Übergänge
können über den Container „Workflow-Liste“ durch Klicken auf das blaue
Symbol verwaltet werden. Sie können mehrere Übergänge festlegen, die
Artikel durchlaufen können. Die möglichen Stufen basieren auf denen, die
Sie für diesen speziellen Workflow erstellt haben.

*Aktuelle Stufe* legt fest, wo dieser Übergang ausgeführt wird. Es
können alle Stufen oder eine bestimmte Stufe ausgewählt werden.

"Zielstufe" ist im Workflow die Stufe, die nach dem Übergang zugewiesen
wird.

<img
src="https://docs.joomla.org/images/thumb/a/a8/Transitions--edit--description-de.png/800px-Transitions--edit--description-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/a/a8/Transitions--edit--description-de.png/1200px-Transitions--edit--description-de.png 1.5x, https://docs.joomla.org/images/a/a8/Transitions--edit--description-de.png 2x"
data-file-width="1371" data-file-height="670" width="800" height="391"
alt="Edit Transitions View" />

Auf dem Reiter *Übergangs-Aktionen* wird festgelegt, auf welcher Stufe
sich der Eintrag befindet, nachdem der Übergang abgeschlossen ist. Wenn
der Eintrag beispielsweise ein Beitrag ist, könnte er nicht mehr
veröffentlicht werden, was exakt beim Übergang *Versteckt* geschieht.
Ferner kann definiert werden, ob der Eintrag am Ende des
Übergangszustandes als „Standard“ gekennzeichnet wird oder nicht.

<img
src="https://docs.joomla.org/images/thumb/8/87/Transitions--edit--transition-actions-de.png/800px-Transitions--edit--transition-actions-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/8/87/Transitions--edit--transition-actions-de.png/1200px-Transitions--edit--transition-actions-de.png 1.5x, https://docs.joomla.org/images/8/87/Transitions--edit--transition-actions-de.png 2x"
data-file-width="1377" data-file-height="647" width="800" height="376"
alt="Edit Transition Actions" />

Auf dem Reiter *Benachrichtigung* wird festgelegt, ob während dieser
Stufe eine Benachrichtigung verschickt werden soll. Wenn zum Beispiel
ein Beitrag geschrieben wurde, aber noch Korrektur gelesen werden muss,
könnte eine E-Mail an den Redakteur gesendet werden.

Außerdem kann ein zusätzlicher Nachrichtentext eingegeben werden. Hier
ist auch die Verwendung eines
Sprach-Strings
erlaubt, der den Nachrichtentext übersetzbar machen würde.

Mit der Option "Benutzergruppen" können Sie festlegen, wer die
Benachrichtigung erhalten soll. In dem gewählten Beispiel würden wir als
Benutzergruppe *Editor* wählen; dann würden alle Benutzer innerhalb
dieser Benutzergruppe eine Benachrichtigung erhalten.

Schließlich gibt es noch die Option "Benutzer". Damit können einzelne
Benutzer ausgewählt werden, die diese Benachrichtigung erhalten sollen.

<img
src="https://docs.joomla.org/images/thumb/d/de/Transitions--edit--notification-de.png/800px-Transitions--edit--notification-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/d/de/Transitions--edit--notification-de.png/1200px-Transitions--edit--notification-de.png 1.5x, https://docs.joomla.org/images/d/de/Transitions--edit--notification-de.png 2x"
data-file-width="1369" data-file-height="746" width="800" height="436"
alt="Edit Transition Notification" />

Der letzte Reiter ist "Berechtigungen". Hier wird festgelegt, wer diesen
Übergang verwenden darf.

- *Beispiel:* In der Transition „Nächster Schritt: Veröffentlichen“
  befinden sich Einträge ursprünglich im Zustand „versteckt“. Sie
  bedürfen beispielsweise noch einer Überprüfung. Nachdem sie überprüft
  wurden, können sie in den Status „veröffentlicht“ wechseln.
- Alle Aktionen des Workflow-Übergangs sind Joomla! Workflow-Plugins.
  Wenn man zu System **→** Plugins geht und in den Filter-Optionen den
  „Typ“ auf *workflow* ändert, so werden diese Plugins angezeigt, die,
  wie alle anderen Plugins auch deaktiviert werden können.

<img
src="https://docs.joomla.org/images/thumb/5/55/Workflows--plugins--workflows-de.png/800px-Workflows--plugins--workflows-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/5/55/Workflows--plugins--workflows-de.png/1200px-Workflows--plugins--workflows-de.png 1.5x, https://docs.joomla.org/images/5/55/Workflows--plugins--workflows-de.png 2x"
data-file-width="1502" data-file-height="463" width="800" height="247"
alt="Workflows Plugins" />

## Kategorien

Beiträge können Kategorien zugewiesen werden. Sie gehören zu einem
bestimmten Workflow und können auf verschiedene Weise angepasst werden.
Es kann ein Status, eine übergeordnete Kategorie festgelegt und auch der
Zugriff sowie die Berechtigungen eingeschränkt werden. Diese Option
befindet sich nicht innerhalb des Bildschirms „Workflows“. Für diese
Option muss zu Inhalt **→** Kategorien gewechselt werden. Wenn dort eine
beliebige Kategorie geöffnet ist, wird der Reiter „Workflows“ angezeigt.

- *Beispiel:* Falls bestimmte Beiträge, die nur für Administratoren oder
  Benutzer mit einem höheren Rang verfügbar sein sollen. Dazu kann man
  die Kategorie „Eingeschränkt“ aufrufen und alle Berechtigungen auf
  „Erlaubt“ für Administratoren oder höher setzen. Auf diese Weise
  müssen diese Berechtigungen nicht für jeden betroffenen Beitrag
  eingerichtet werden, sondern können in diese spezielle Kategorie
  verschoben werden und so Zeit eingespart werden.

<img
src="https://docs.joomla.org/images/thumb/c/c0/Workflow-categories-de.png/800px-Workflow-categories-de.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/c/c0/Workflow-categories-de.png/1200px-Workflow-categories-de.png 1.5x, https://docs.joomla.org/images/c/c0/Workflow-categories-de.png 2x"
data-file-width="1476" data-file-height="670" width="800" height="363"
alt="Workflow-categories-de.png" />

## Versionierung

Wenn der Workflow aktiviert ist, werden vom Workflow verwaltete Felder
von der Versionierung ausgeschlossen (wie zum Beispiel „Status“ oder
„Standard“), um Konflikte mit Zugriffsrechten zu vermeiden.

## Verwandte Informationen

Siehe auch:

-  Umsetzung des
  Publishing-Workflows
- Workflow/Szenarien
