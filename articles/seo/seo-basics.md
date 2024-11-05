<!-- Filename: jdocmanual?manual=user&heading=seo&filename=seo-basics.md / Display title: SEO-Grundlagen -->

## Definition

Suchmaschinenoptimierung ist der Prozess der Verbesserung einer Vielzahl von Merkmalen einer Website mit dem Ziel, die Position zu verbessern, in der sie in Suchmaschinen platziert wird.

Der Prozess der Optimierung einer Website ist facettenreich, da es viele Faktoren gibt, die beeinflussen, wo eine Seite in einer Suchmaschine platziert werden könnte.

- Sicherstellen, dass Inhalte mit Semantischem HTML eine angemessene Struktur haben
- Verbesserung der Qualität des Inhalts einzelner Seiten
- Sicherstellen, dass die Website Anfragen schnell bearbeiten kann
- Aktivieren von suchmaschinenfreundlichen URLs, um die Webadresse von Seiten „menschlich lesbar“ zu machen
- Hinzufügen von kontextuellem semantischen Markup mithilfe von Schema-Daten

Ressource: Leitfaden für Suchmaschinenoptimierung (SEO) Starter Guide

## Seitenstruktur und beschreibende URLs

In den frühen Tagen waren Webseiten als einzelne HTML-Dateien in einer Baumhierarchie strukturiert. Einige Webseiten sind immer noch so strukturiert. CMS unterscheiden sich jedoch. Einzelne Seiten werden aus Inhalten zusammengestellt, die in Datenbanktabellen gespeichert sind. Die URLs für die früheren und letzteren sind unterschiedlich, möglicherweise in etwa so:
```
https://www.example.com/user/seo/seo-basics.html
https://www.example.com/index.php?option=com_jdocmanual&view=manual&manual=user&heading=seo&filename=seo-basics
```
Offensichtlich ist die erste einfacher zu merken und einfacher zu tippen. Suchmaschinen bevorzugen sie.

Im Joomla CMS kann eine URL der ersten Form wie folgt eingerichtet werden:

1. Erstellen Sie eine Inhaltskategorie mit dem Namen **User**.
2. Erstellen Sie eine Inhaltskategorie namens **SEO**, die ein Unterelement von *User* ist.
3. Erstellen Sie einen Beitrag und ordnen Sie ihn der Kategorie *SEO* zu.
4. Erstellen Sie ein Menüelement **User** vom Typ **Kategorieliste** unter Verwendung der Kategorie *User*.
5. Erstellen Sie ein Menüelement **SEO** vom Typ **Kategorieliste** mit der Kategorie *SEO*.
6. Richten Sie die SEO-Funktionalität von Joomla in der *Globalen Konfiguration* ein.

Testen Sie es mit Ihrer SEO-URL: Navigieren Sie über die Listen User und SEO zur Seite SEO Basics. Die Breadcrumbs sollten Folgendes anzeigen: `Sie sind hier: Startseite / User / SEO / SEO Basics`. Aber nicht, wenn Sie einen Menüpunkttyp für *SEO Basics* als Einzelbeitrag erstellt haben!

## Reduzierung von Duplikaten

Das Problem bei CMSs ist, dass derselbe Inhalt unter verschiedenen URLs verfügbar gemacht werden kann. Im obigen Beispiel funktionieren beide URLs (aber nicht auf dieser Seite), ebenso wie `https://example.com/index.php?option=com_content&view=category&id=18&ItemID=17`. Nur eine davon sollte von Suchmaschinen anerkannt und als die **kanonische** URL festgelegt werden. Aber welche und wie?

Das **System - SEF** Plugin bietet einige Unterstützung. Es hat drei Einstellungen:

* **Site-Domain:** Wenn Ihre Seite über mehr als eine Domain erreichbar ist, geben Sie hier die bevorzugte (manchmal als kanonisch bezeichnete) Domain ein. **Hinweis:** `https://example.com` und `https://www.example.com` sind unterschiedliche Domains.
* **Strikte Handhabung von index.php:** Diese Option ermöglicht eine strengere Handhabung von 'index.php' in URLs, wenn im Globalen Konfigurationsbereich 'URL-Rewriting verwenden' aktiviert ist. Sie entfernt 'index.php', wenn eine URL es noch enthält, und leitet eingehende Anfragen mit 'index.php' auf die Version ohne 'index.php' um.
* **Trailing-Slash für URLs:** Zwingt Joomla, nur URLs mit oder ohne abschließenden Schrägstrich zu verwenden. Bei Aktivierung wird die korrekte URL mit Umleitungen erzwungen und wird nur angewendet, wenn 'Suffix zu URL hinzufügen' deaktiviert ist.

**Kanonische Tags** Erklärung von Daniel Morell:

* Wie man Joomla kanonische Tags erstellt
* Plugin und Dokumentation:

Für Joomla 4 und 5 muss vor der Aktivierung das Plugin `if ($app->isAdmin()) {` in `if ($app->isClient('admin')) {` auf den Zeilen 72 und 99 von *plugins /system / customcanonical / customcanonical.php* geändert werden.

In einem Beitrag wählen Sie die Registerkarte Veröffentlichungen und dann den *Kanonische URL* **Auto** Button. Dies platziert einen Link wie den folgenden auf jeder Seite, die den einzelnen Beitrag anzeigt:
```
	<link href="/jdm3/en/user/seo/seo-basics.html" rel="canonical" />
```

## Inhaltliche Qualität

Gestalten Sie das, was Sie schreiben, interessant und leicht lesbar. Lange Absätze sind oft überwältigend und schwer zu lesen. Einzeilige Absätze sehen falsch aus! Vielleicht sollten sie stattdessen Aufzählungspunkte sein. Streben Sie Absätze von etwa drei Zeilen an. Lesen Sie, was Sie schreiben, und streichen Sie unnötige Wörter.

Halten Sie Ihren Inhalt aktuell und vermeiden Sie das Kopieren von Informationen von anderen Websites. Überprüfen Sie Ihren Inhalt, wenn möglich.

### Semantisches HTML

Inhalte sollten aus einer Hierarchie von Überschriften und Absätzen mit anderen erforderlichen Elementen bestehen (wie Listen, Tabellen usw.). Verwechseln Sie nicht Struktur mit Aussehen – verwenden Sie also keine Überschrift zur Hervorhebung oder Hervorhebung für eine Überschrift. Dies ist ein Beispiel für semantische Auszeichnung von Beiträgen:

```html
  <h2>Verwendung von Überschriften</h2>
  <p>Dies ist ein Beitrag über die Bedeutung von Überschriften.</p>

  <h2>Warum Überschriften verwenden?</h2>
  <p>Es ist wichtig, Überschriften zu verwenden, damit Suchmaschinen-Bots erkennen können, welcher
  Teil Ihres Beitrags <strong>wichtig</strong> ist.</p>

  <h3>Arten von Überschriften</h3>
  <p>Sie können festgelegte Arten von Überschriften verwenden, aber sie sollten innerhalb Ihrer Seite geordnet und strukturiert sein. H1 wird der von Joomla eingefügte Seitentitel sein, wobei H2 für Unterüberschriften der Seite verwendet wird. Alle Überschriften innerhalb Ihrer Unterüberschriften sollten entsprechend mit H3, H4 und H5 fortgeführt werden.</p>

  <h2>Ist es schwer, Überschriften umzusetzen?</h2>
  <p>Es ist wirklich einfach, Überschriften umzusetzen. Sie verwenden einfach den passenden HTML-Code.</p>
```

Beachten Sie, dass ein Beitragstitel bei Bedarf zu einer `<h1>`-Überschrift wird, also verwenden Sie ihn nicht im Beitragsinhalt.

## Suchbegriffe antizipieren

Wählen Sie eindeutige Titel für Ihre Seiten und Überschriften innerhalb von Seiten. Zum Beispiel, wenn Sie nicht wissen, was *Semantisches HTML* ist oder mehr Informationen zu diesem Thema möchten, wären dies die Wörter, die Sie in eine Suchmaschine eingeben. Denken Sie an die Personen, die an den Informationen interessiert sein könnten, die Sie bereitstellen. Wonach werden sie suchen? Aber halten Sie Titel und Überschriften ziemlich kurz – einige Quellen sagen, nicht mehr als 60 Zeichen.

## Vorsicht mit Werbeanzeigen

Nichts wird Besucher der Website mehr abschrecken als überall erscheinende Werbeanzeigen, die die eigentlichen Informationen vor den Augen hin- und herbewegen. Anzeigen, die sich alle paar Sekunden ändern, sind ebenfalls störend und belasten die Ressourcen des Endnutzers. Viele werden Adblocker verwenden!

## Vorsicht mit Links

Links sind sowohl ein Segen als auch ein Fluch! Sie können das SEO-Ranking deiner Website positiv oder negativ beeinflussen, je nachdem, ob du Links zu seriösen oder unseriösen Quellen hast. Und sie müssen gepflegt werden. Möglicherweise hast du Links zu internen oder externen Beiträgen, die verschwunden sind, veraltete Informationen präsentieren oder nicht mehr relevant sind. Der beste Rat: Verlinke nur, wenn das Ziel echten Nutzen für deine Website-Besucher bietet, und nutze das `nofollow` Link-Attribut, wenn du nicht möchtest, dass die Zielseite mit deiner Seite in Verbindung gebracht wird.

Es gibt viele Link-Checker-Tools, einige kostenlos oder freemium und andere kostenpflichtig, oft als Teil eines Website-Überwachungsdienstes.  

## Seitentitel und Beschreibung

Im `<head>` jeder Seite sollte es einen `<title>`-Tag und einen `<description>`-Tag geben. Joomla macht es sehr einfach, für jede Seite einen anderen Titel festzulegen. Leider macht es das auch sehr einfach, zu versäumen, einen geeigneten Titel und eine Beschreibung auf jeder Seite festzulegen.

Nehmen wir als Beispiel die oben erwähnte **SEO**-Kategorieliste. Im Quelltext der Seite steht im `<title>`-Tag **SEO** und die `<description>` fehlt. Im Formular **Menüs: Artikel bearbeiten** für dieses Menüelement gibt es eine Registerkarte **Seitendarstellung** mit einem Feld **Browsertitel**. Dort `SEO - Liste von Beiträgen` einfügen und genau das erscheint im `<title>`-Tag und im Browsertab.

In der Registerkarte **Metadaten**, mit dem **Meta-Beschreibung**-Feld auf `Liste von Beiträgen zur Suchmaschinenoptimierung.` gesetzt, erscheint das genau im `<description>`-Feld. Die Beschreibung wird manchmal verwendet, um einen Seitentitel in Suchergebnissen zu begleiten, daher sollte sie relevant sein.

Weitere Informationen:
* Magazinbeitrag: Joomla SEO-Titel-Tags
* Erkunde den Kern: Natürliche SEO-Optionen

## Bilder optimieren

Es versteht sich von selbst, dass attraktive Bilder eine Website enorm verbessern können. Aber zu viele Bilder, die zu groß sind, ziehen SEO-Strafen nach sich. Hier einige Tipps:

* Platzieren Sie Bilder neben dem Text, den sie veranschaulichen.
* Verwenden Sie beschreibenden **alt**-Text.
* Verwenden Sie mit Minuszeichen getrennte Wörter für die Bildnamen, zum Beispiel katze-auf-heißem-dach.jpd.
* Verwenden Sie den richtigen Bildtyp für die jeweilige Aufgabe: png für Poster, jpg für Fotografien.
* Verwenden Sie responsive Bilder – es gibt ein Joomla-Plugin, das dynamisch webp-Versionen von png- und jpg-Bildern in verschiedenen Größen erstellt.

*Übersetzt von openai.com*

