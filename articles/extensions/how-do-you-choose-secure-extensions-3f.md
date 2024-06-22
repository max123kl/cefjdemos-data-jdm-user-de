<!-- Filename: How_do_you_choose_secure_extensions%3F / Display title: Wie wählt man sichere Erweiterungen aus? -->

Die Entscheidung zur Verwendung einer Erweiterung sollte gut überlegt
werden. Sobald unsichere Erweiterungen oder solche mit enthaltenem
Schadcode installiert sind, gilt die Website als kompromittiert. Es gibt
**keine Möglichkeit** eine Komponente vom Zugriff auf die
Datenbanktabellen abzuhalten. Darüberhinaus kann nicht verhindert
werden, dass eine Komponente Informationen aus der Website zu einer
Hacker-Website sendet. Falls eine unsichere oder Schadcode-verseuchte
Komponente installiert ist, gilt damit die gesamte Website als unsicher.

## Einfache Tipps um gute Entscheidungen in Bezug auf die Auswahl von Erweiterungen treffen zu können

- Wann wurde die letzte Version der Erweiterung veröffentlicht?

Falls dies schon über ein Jahr her ist, kann man das Projekt als
eingestellt betrachten. Daher sollte eine andere Erweiterung gesucht
werden. Man sollte keine alten Komponenten installieren.

- Um was für eine Art von Version handelt es sich (stabil, Release
  Candidate (RC), beta, alpha)?

Für produktive Websites sollten stabile Versionen verwendet werden.
Falls man nicht auf die stabile Version warten kann, sollten als einzige
andere Möglichkeit Release Candidates in Betracht gezogen werden. Es
wird nicht empfohlen beta oder alpha Versionen von Erweiterungen auf
einer produktiven Website zu installieren. Dies bedeutet, dass diese
Erweiterungen dann noch Fehler haben können, nicht ausreichend getestet
sind und Sicherheitsprobleme die noch nicht gefunden oder gefixt sind
aufweisen.

- Hat diese Erweiterung eine Vorgeschichte, die auf einen guten Umgang
  mit dem Thema Sicherheit hinweist?

Dies ist natürlich etwas subjektiv. Aber es können Rückschlüsse auf die
zukünftige Vertrauenswürdigkeit gezogen werden. Dieser Punkt erfordert
etwas Nachforschung. Gibt es auf den Downloadseiten und in den Archiven
des Enwicklers Hinweise auf viele Sicherheitsupdates? Gibt es Berichte
über Hackeraktivitäten durch diese Erweiterung? Ist der Entwickler
erfahren und hat er ein Bewusstsein für Sicherheit? Was denken andere
über diese Erweiterung?

- Gibt es eine Support Community für diese Erweiterung?

Dies ist wichtig für die Bedienbarkeit und die Sicherheit. Falls es eine
Support Community gibt ist die Wahrscheinlichkeit höher, dass
Sicherheitslücken gefunden und behoben werden. Eine Support Community
bedeutet das es Personen gibt die diese Erweiterung gerne weiter
verwenden möchten und sich daher darum kümmern. Dies fördert die
Wahrscheinlichkeit das Sicherheitsprobleme zeitnah gefunden und behoben
werden.

- Gibt es eine kompatible Version für die aktuellste Joomla Version?

Dieser Punkt ist im Übergangszeitraum zwischen zwei Versionen von
Bedeutung, solange die ältere Joomla Version noch in Verwendung ist.
Wenn die ältere Version das Supportende erreicht hat, ist ein Update
wesentlich einfacher, wenn die externen Erweiterungen mit der aktuellen
Joomla Version kompatibel sind.

- Ist die Erweiterung im allgemeinen frei von Fehlern?

Es ist fast unmöglich eine fehlerfreie Erweiterung zu haben. Je kleiner
die Anzahl der Fehler, umso besser. Sind Bugs vorhanden, bedeutet dies
Programmfehler. Umso mehr Fehler, desto höher ist das Risiko für Bedien-
und Sicherheitsprobleme. Sicherheitsprobleme sind oft nicht das Ergebnis
von einem Fehler, sondern von vielen Fehlern und schlechten
Programmierpraktiken. Zum Beispiel sind einige Sicherheitslücken durch
Drittanbieter, die Remote File Inclusion ermöglichen, ein Ergebnis von:

## Schlechte Programmierpraktiken

- Aktivierung von PHP's Register Globals .
- Verwendung von veralteten Erweiterungen.
- Keine anderen Sicherheitsmaßnahmen sind für PHP aktiviert. (url_fopen
  off, open_basedir restrictions, disabled PHP functions)
- Schlecht eingestellte Datei-Berechtigungen.
- Kein request filtering oder keine Software "firewall". (wie z.B.
  mod_rewrite rules oder mod_security Apache Module)

## Bugs

- Kein including defined('\_VALID_MOS') oder die... Anweisungen
- Schlecht aufgebaute include() Anweisungen.

## Wichtige Punkte zur Erinnerung

**Obgleich der Joomla! Core bei richtiger Konfiguration sicher ist, gibt
es Erweiterungen von Drittanbietern vom Alter und Qualität her
betrachtet in allen Schattierungen.** Wenn man den Entwicklern der
Erweiterung nicht absolut vertraut, sollte man den Code vor der
Installation der Erweiterung überprüfen. Folgende Liste deckt typische
Bereiche ab:

1\. Wie komplex ist die Erweiterung?

Je größer sie ist, desto sorgfältiger sollte sie überprüft werden. Falls
man nicht erkennt und versteht was die Erweiterung tut, sollte man ihr
nicht vertrauen.

2\. Liest die Erweiterung Dateien vom Server aus oder schreibt sie in
Dateien auf dem Server?

Programme die Dateien auslesen könnten unbeabsichtigt die eingestellten
Dateiberechtigungen umgehen oder sensible Systeminformationen an Hacker
weitergeben. Programme, die in Dateien schreiben haben das Potential
vorhandene Dateien zu ändern, zu zerstören oder Trojaner einzuschleusen.

3\. Interagiert die Erweiterung mit anderen Programmen des Systems?

Zum Beispiel senden viele Erweiterungen E-Mails als Reaktion auf eine
Formulareingabe, indem sie eine Verbindung mit dem sendmail Programm
öffnen. Wird dies in einer sicheren Art und Weise getan?

4\. Läuft die Erweiterung mit suid (set-user-id) Rechten?

Dies ist im Allgemeinen sehr gefährlich und sollte nie ohne einen guten
Grund getan werden.

5\. Überprüft die Erweiterung alle Benutzereingaben, wie z.B. in
Formularfeldern und URLs?

6\. Prüfen, ob die Erweiterung als  Gefährliche
Erweiterung
gelistet ist.

7\. Verwendet die Erweiterung explizite Pfadnamen beim Aufrufen externer
Programme?

Vertrauen auf die PATH Systemvariable zum Auflösen von partial path
names ist eine gefährliche Praktik.

8\. Ist die Erweiterung sicher gegen direkten Zugriff durch die URL?

Zum Beispiel:
`www.deinewebseite.de/components/com_bad_extension.php?jede_menge_schad_code_hier`

9\. Ist die Erweiterung sicher gegen Remote File Inclusions?

10\. Ist die Erweiterung sicher gegen SQL Injection?

11\. Ist die Erweiterung sicher gegen Cross Site Scripting (XSS)?

12\. Verwendet die Erweiterung PHP register_globals ON, oder Joomla! RG
Emulation ON?

Falls ja, verstößt sie wahrscheinlich gegen Regel Nummer 7.

13\. Stellt die Erweiterung Benutzern mit wenigen Rechten einen
umfangreichen Datenbankzugriff zur Verfügung?

Erlaubt sie zum Beispiel Benutzern mit Gastrechten oder registrierten
Benutzern Daten zu sehen die nur Benutzer mit Administratoren- oder
Publisher-Rechten sehen dürfen?

## Weitere Informationen

- Siehe: <a
  href="https://extensions.joomla.org/support/knowledgebase/for-jed-users/choosing-secure-extensions/"
  class="external text" target="_blank" rel="noreferrer noopener">Choosing
  Secure Extensions on the JED website</a>
- Siehe:
  <a href="https://extensions.joomla.org/vulnerable-extensions/about/"
  class="external text" target="_blank"
  rel="noreferrer noopener">Vulnerable Extension List</a>
