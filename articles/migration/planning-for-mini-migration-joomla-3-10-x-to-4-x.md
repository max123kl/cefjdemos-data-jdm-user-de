<!-- Filename: Planning_for_Mini-Migration_-_Joomla_3.10.x_to_4.x / Display title: Planung einer Mini-Migration - Joomla 3.10.x nach 4.x -->

Ein Upgrade von Joomla! 3.10.x zu 4.x wird als Mini-Migration oder
kleine Migration betrachtet. Dies bedeutet, dass
Joomla!-Kernerweiterungen mit einem „Ein-Klick-Update“ aktualisiert
werden. Erweiterungen von Drittanbietern werden nicht zwingend
unterstützt und sollten von Fall zu Fall geprüft werden.

## Einleitung

Migrationen sind ein guter Zeitpunkt, um Ziele neu zu bewerten,
aufzuräumen und andere Bereiche/Elemente der Website auszubauen. Je
organisierter man seine Ideen/Gedanken/Pläne einbringen kann, desto
besser. Planen, planen, planen. Planung macht die Umsetzung einfacher.

Die Planung beginnt, indem die folgenden Fragen beantwortet oder die
unten aufgeführten Aufgaben durchgeführt werden. Abhängig von der
Komplexität der Website müssen möglicherweise weitere Punkte
berücksichtigt werden. Leider gibt es keine Möglichkeit, jedes mögliche
Szenario aufzulisten. Bitte im Forum
<a href="https://forum.joomla.org/viewforum.php?f=812"
class="external text" target="_blank"
rel="noreferrer noopener">Migrieren und Upgraden auf Joomla 4.x</a>
(engl.) um Hilfe bitten oder im deutschen Forum
<a href="https://forum.joomla.de/board/51-erste-schritte-und-probleme"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Joomla4.x Erste Schritte und
Probleme</a> nachfragen.

## Die 3.10.x Brückenversion

Joomla! 3.10.x soll eine Brückenfunktion zwischen der Joomla! 3 Reihe
und der neuen Joomla! 4 Reihe übernehmen. Joomla! 3.10.x wird in erster
Linie eine Version sein, die Backports von API-Änderungen aus dem
Joomla! 4.x Entwicklungszweig enthält, um den Wechsel zur nächsten
Hauptversion für die Benutzer zu erleichtern. Neu in Joomla 3.10.x ist
eine herausragende Funktion der Joomla!-Update-Komponente, die beidem
Mini-Migrationsprozess helfen soll: die
Kompatibilitätsprüfung.
Sobald die Website auf 3.10 aktualisiert wurde, kann die
Kompatibilitätsprüfung die Verträglichkeit der PHP- und SQL-Optionen,
der Einstellungen und der verwendeten Erweiterungen mit Joomla! 4.0
untersuchen, sofern die Entwickler der Erweiterungen das
targetplatform-Tag verwendet haben. Mehr dazu in der Dokumentation
Kompatibilitätsprüfung.

## Die Migration planen

Die folgenden Schritte gehen davon aus, dass die Joomla! 3.x Seite
bereits auf die Version 3.10.x aktualisiert wurde. Somit können die
Vorteile der Kompatibilitätsprüfung als Teil der Vorbereitung genutzt
werden.

1.  Überprüfen, ob auf der Website mindestens die Version 3.10.x läuft.
2.  Beurteilen der ursprünglichen Website-Ziele. Die Migration ist eine
    Gelegenheit, die Ziele wieder in den Fokus zu rücken oder die
    Ausrichtung zu ändern.
3.  Erfüllt der Server die minimalen
    <a href="https://downloads.joomla.org/de/technical-requirements-de"
    class="external text" target="_blank"
    rel="noreferrer noopener">technischen Anforderungen</a> für Joomla!
    4? Wenn nicht, sollte der Provider gewechselt werden. Es gibt keinen
    besseren Zeitpunkt für einen Wechsel als während einer Migration.
4.  Welche Art von Installationsumgebung soll verwendet werden? Eine
    Installation auf dem lokalen Rechner? Eine Subdomain oder ein
    Unterverzeichnis auf dem Server? Ein neuer Server/Hosting-Account
    wegen der technischen Anforderungen?
5.  Es sollte eine Liste aller verwendeten Drittanbieter-Erweiterungen
    erstellt werden. Dazu gehören Komponenten, Module, Plugins, Sprachen
    und Templates. Zu Referenzzwecken können die Informationen einfach
    in ein Dokument kopiert/eingefügt werden, aber auch Papier und Stift
    reichen aus. Es sollte festgehalten werden, ob diese Erweiterungen
    stark, mäßig, kaum oder gar nicht genutzt werden.
6.  Ermitteln, ob wichtige Drittanbieter-Erweiterungen für die Version
    von Joomla, auf die migriert werden soll, kompatibel sind. Dazu muss
    (sobald Joomla 3.10.x läuft) in der Joomla-Update-Komponente die
    Option „Joomla! Next“ ausgewählt werden. Außerdem muss geprüft
    werden, ob sie mit Joomla! 4 kompatibel sind. Das Update auf 4.x
    sollte nicht ausgeführt werden, es ist lediglich die Option „Joomla!
    Next“ in den Joomla Update Optionen auszuwählen, damit die
    Kompatibilitätsprüfung angezeigt werden kann. Das hilft, um einen
    Überblick über die verwendeten Erweiterungen und deren
    Kompatibilität zu gewinnen. Es ist kein Ersatz dafür, dass man
    trotzdem Erweiterungen → Verwalten aufrufen muss. Mehr dazu in der
    Schritt-für-Schritt-Anleitung und der Dokumentation für die
    Komponente
    Kompatibilitätsprüfung.
    Dies ist einfach dazu da, sich darauf vorzubereiten, welche
    Erweiterungen von Drittanbietern beibehalten oder ersetzt werden
    sollen.
7.  Entscheiden, ob wirklich alle verwendeten Erweiterungen benötigt
    werden. Könnte es sein, dass Joomla! 4 eingebaute Funktionen hat,
    die den Einsatz einer Drittanbieter-Erweiterung überflüssig machen
    könnten?
8.  Die Kategorien und Beiträge durchsehen. Gibt es Aufräumarbeiten, die
    erledigt werden müssen, damit keine unnötigen Inhalte migriert
    werden?
9.  Wie steht es mit dem Template? Falls das Template von einem
    Drittanbieter gekauft wurde, gibt es eine 4.x-Version dafür? Soll es
    weiter verwendet werden? Ist ein Upgrade-Weg vom Entwickler
    veröffentlicht worden? Ist die neue Version responsiv? Ist das
    Template ein selbst erstelltes Template? Oder wurde es aufwendig von
    einem Drittanbieter-Template angepasst? Das Joomla Core Template für
    Joomla 3.x, **Protostar ist *nicht* kompatibel mit Joomla 4**. Nach
    der Migration wird es gelöscht werden. Die Verwendung des
    Joomla-Core-Templates für Joomla 4.x, Cassiopeia, könnte eine
    mögliche Option sein. Für eine Erweiterung der Template-basierten
    Betrachtungen, siehe  Überlegungen zum Template bei der
    Migration.
10. Wenn das Template gegen ein neues ausgetauscht wird, sind dann neue
    Bilder erforderlich? Wenn beispielsweise die jetzige Website einen
    weißen Hintergrund hat und das Logo oder andere Bilder im
    .jpg-Format mit weißem Hintergrund verwendet werden, sieht das auf
    einem neuen Template mit grauem oder farbigem Hintergrund nicht sehr
    schön aus.
11. Wenn die Website neu zu gestalten ist oder Änderungen am Site-Design
    oder der Navigation vorgenommen werden, entstehen dann eventuell
    überflüssige Seiten, die eine Umleitung erfordern? Wenn ja, dann
    sollte man sie dokumentieren. Eine Tabelle ist praktisch, um Links
    zu dokumentieren, die geändert werden müssen.

<a
href="https://docs.joomla.org/Joomla_3.x_to_4.x_Step_by_Step_Migration"
id="content-button" class="button expand">Joomla! 3.10 nach 4.x:
Migration – Schritt für Schritt</a>
