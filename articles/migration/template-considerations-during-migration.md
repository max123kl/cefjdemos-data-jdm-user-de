<!-- Filename: Template_Considerations_During_Migration / Display title: Überlegungen zum Template bei der Migration -->

<img
src="https://docs.joomla.org/images/thumb/4/47/Copyedit.png/25px-Copyedit.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/47/Copyedit.png/38px-Copyedit.png 1.5x, https://docs.joomla.org/images/thumb/4/47/Copyedit.png/50px-Copyedit.png 2x"
data-file-width="200" data-file-height="200" width="25" height="25"
alt="Copyedit.png" />This Article Needs Your Help

*This article is tagged because it* **NEEDS UPDATING***. You can help
the Joomla! Documentation Wiki by <a
href="https://docs.joomla.org//docs.joomla.org/index.php?title=Template_Considerations_During_Migration/de&amp;action=edit"
class="external text" target="_blank"
rel="noreferrer noopener">contributing to it</a>.
<span class="small">More pages that need help similar to this one are
here.</span>
<span class="small">**NOTE-If you feel the need is satistified, please
remove this notice.**</span>*
**Reason:** See section 3.4 and 4

Templates können manchmal die geplanten Abläufe einer Migration
zunichtemachen. Es muss aber nicht so sein. Mit ein wenig Vorbereitung
versteht man die Fallstricke und findet die möglichen Optionen, um die
Probleme zu umgehen.

## Einleitung

Templates sind eine Erweiterung. Komponenten, Module und Plugins sind
ebenfalls Erweiterungen.

Bei der Konfiguration der Migration, muß entschieden werden, was mit dem
Template (es bestimmt das Aussehen der Website) zu tun ist.

Für die meisten Szenarien passen eine der folgenden Optionen:

- Es wird ein erworbenes Template von einem Template-Club eingesetzt.
- Es wird ein erworbenes Template von einem Template-Anbieter
  eingesetzt.
- Es wird ein selbst erstelltes Template verwendet.
- Es wird ein Standard-Template, welches zusammen mit der Joomla!
  Installation geliefert wurde verwendet
  - Joomla! 1.5 Standard-Templates sind Rhuk_milkway, JA Purity, Beez
  - Joomla! 2.5 Standard-Templates sind Atom, Beez3 und Beez25.
  - Joomla! 4 Standard-Template ist Cassiopeia.

## Template Szenario beurteilen

Vor der Entscheidung was zu tun ist, sollte über das Aussehen der
Website nachgedacht werden. Sollte das Design geändert werden, dann ist
dies der richtige Zeitpunkt dafür. Einer der größten Vorteile warum ein
neues Template eingesetzt werden sollte, sind die neuen Technologien und
Funktionen der aktuellsten Templates. In Joomla! 1.5 standen
beispielsweise noch keine responsiven Templates zur Verfügung und auch
zu Beginn des Joomla! 2.5 Lebenszyklus nicht.

Nehmen wir folgende Szenarien an:

### Es wird Protostar genutzt

Protostar ist nicht kompatibel mit Joomla 4.x. Die Migration wird mit
einem Klick von Joomla 3.10.x auf 4.x funktionieren, aber das Template
wird bei der Migration entfernt und durch Cassiopeia ersetzt werden.
Daher sollte Cassiopeia oder ein anderes Template in Joomla 4 verwendet
werden.

#### Warum kann man Protostar nicht in Joomla 4 übernehmen?

Protostar basiert auf einer alten Version von Bootstrap (Bootstrap 2)
und jQuery (1.x). Die Versionen dieser Komponenten sind veraltet und
haben bekannte Sicherheitsprobleme (Joomla 3 pflegte Fork-Versionen
dieser Bibliotheken mit Sicherheits-Patches) – Joomla 4 verwendet dafür
die neueste Version – Bootstrap 5. Dies bedeutet jedoch, dass Templates
aktualisiert werden müssen, um die neue HTML-Syntax zu verwenden, die
Bootstrap 5 erfordert.

### Bei Einsatz eines Templates, das von einem Template-Club gekauft wurde

Dies ist die einfachste Lösung – meistens jedenfalls. Wenn ein Template
von einem Template-Club gekauft haben, sollte man das Unternehmen
kontaktieren und nachfragen, ob es eine Version des Templates für Joomla
4.x gibt. Wenn ja, dann ist das hervorragend, aber es gibt ein paar
Dinge zu beachten. Wenn mit der Version 1.5 auf 4.x umgestiegen wird,
sollte geprüft werden, ob diese Version für Joomla 4 responsive ist,
falls das wichtig ist. Falls man von 1.5 auf 4 wechselt, ist es
wahrscheinlich, dass es Unterschiede zwischen der 1.5 Version des
Templates und der 4 Version des Templates geben wird. Es sollte darmit
gerechnet werden, dass einige Anpassungen am Template vorgenommen werden
müssen, wenn es *genau* gleich aussehen soll. Wenn von 1.5 auf 4.x
gewechselt wird, ist es wahrscheinlich, dass ein neues Template benötigt
wird.

Bei der Migration von 2.5 auf 3.x oder von 3.10.x auf 4.x sollten man
überprüfen, ob die Versionen 2.5 und 3.x oder 3.10.x und 4.x im gleichen
Paket des Entwicklers enthalten sind. Falls nicht, ist es ratsam, sich
beim Entwickler zu erkundigen, wie man ein Upgrade von Joomla 2.5 auf
3.x und dann von 3.10.x auf 4.x durchführt. Wenn 2.5 und 3.x oder 3.10.x
und 4.x im selben Paket enthalten sind, ist alles in Ordnung. Wenn
nicht, ist es möglicherweise trotzdem in Ordnung. Es hängt einfach vom
Upgrade-Pfad des Entwicklers ab.

### Wenn ein Template verwendet wird, das einmal bei einem Template-Anbieter gekauft wurde

Wenn ein Template von einem Template-Anbieter gekauft wurde, das ein
Einzelkauf war, sollte man sich bei dem Anbieter erkundigen, ob es eine
Version für Joomla 3.x oder 4.x gibt (je nach der Migration, die man
vornimmt). Wenn nicht, hat man vermutlich Pech gehabt. Dennoch könnte
man versuchen, einen Mitarbeiter des Unternehmens zu kontaktieren, um
herauszufinden, ob er das System aktualisieren kann, um es mit Joomla
3.x oder 4.x kompatibel zu machen.

Wenn das fehlschlägt, dann muss entweder:

1.  Ein neues Template gewählt werden.
2.  Das Template konvertieren, um es kompatibel mit Joomla! 3.x oder 4.x
    zu machen. (Hinweis: möglicherweise ist es nicht responsiv)

*Punkt 1* ist selbsterklärend. Entweder man wählt ein Template eines
kommerziellen Anbieters oder man passt das Standard-Template von
Cassiopeia (mehr zu Cassiopeia weiter unten) an, das mit Joomla 4.x
installiert wird.
*Punkt 2* ist nicht so einfach. Um ein bestehendes Template so zu
konvertieren, dass es mit Joomla 3 (und zukünftig mit Joomla 4)
kompatibel ist, siehe den folgenden Abschnitt.

## Template Umwandlungen oder Template Migrationen

### Template-Konvertierung von 1,5 nach 3.x

-  Template Migration von Joomla! 1.5 nach
  3.x

### Template Umwandlungen von 1.5 nach 2.5

-  Upgrading a Joomla 1.5 template to Joomla
  2.5
- <a
  href="http://magazine.joomla.org/issues/issue-may-2012/item/740-How-to-convert-Joomla-15-template-to-Joomla-25"
  class="external free" target="_blank"
  rel="noreferrer noopener">http://magazine.joomla.org/issues/issue-may-2012/item/740-How-to-convert-Joomla-15-template-to-Joomla-25</a>

### Template Umwandlungen von 2.5 nach 3.x

-  J3.x:Konvertieren eines Templates von einer früheren Joomla!
  Version
- <a
  href="http://stackoverflow.com/questions/16055707/convert-joomla-2-5-template-to-3-0"
  class="external free" target="_blank"
  rel="nofollow noreferrer noopener">http://stackoverflow.com/questions/16055707/convert-joomla-2-5-template-to-3-0</a>
- <a href="https://www.youtube.com/watch?v=E13QMWgvwlA"
  class="external free" target="_blank"
  rel="nofollow noreferrer noopener">https://www.youtube.com/watch?v=E13QMWgvwlA</a>

### Template-Konvertierung von 3.10.x nach 4

This section needs content. If you have knowledge on converting
templates built for Joomla 3 to make them compatible with Joomla 4,
please write a magazine article or post a YouTube or something that can
be linked from this area. Thanks in advance.

### Es wurde ein eigenes Template angefertigt

Bei Einsatz eines individuell angefertigten Templates für Joomla! 1.5,
2.5 oder 3.x, muss dieses für Joomla 4 konvertiert werden, um kompatibel
zu sein. Siehe Links im vorherigen Abschnitt. Wird ein Experte
gebraucht, der das vorhandene Template mit Joomla! 4.x kompatibel machen
soll, siehe im Joomla! Community Portal entweder unter
<a href="https://community.joomla.org/service-providers-directory/"
class="external text" target="_blank" rel="noreferrer noopener">Service
Provider</a> oder in den Kategorien für <a
href="https://community.joomla.org/service-providers-directory/listings/category/view/119-migrations-upgrades.html"
class="external text" target="_blank"
rel="noreferrer noopener">Migration- &amp; Upgradeservice</a> (en) nach.

### Bei Einsatz eines Joomla! Standard-Templates

Joomla! 1.5 Standard-Templates sind Rhuk_milkyway, JA Purity und Beez.
Joomla! 2.5 Standard-Vorlagen sind Atomic und zwei unterschiedliche
Versionen von Beez. Die Joomla! 3 Standard Templates sind Beez3 und
Protostar. Das Template wurde eventuell deutlich angepasst oder im
Original belassen. Bei Einsatz eines 2,5-Standard-Templates kann die
Migration nach Joomla! 3.x mit einem One-Click-Update durchgeführt
werden. Bei einem 1,5 Standard-Template, muss durch eine der oben
genannten Schritte gegangen werden, um es für Joomla 3.x zu
aktualisieren. (Sollte jemand der Meinung sein, dass diese Informationen
falsch sind, kann er sich bitte als Autor eintragen und es korrigieren).
Joomla 3 Standard-Templates sind **nicht** kompatibel mit Joomla 4. Es
wird nicht möglich sein, Protostar oder Beez3 in Joomla 4 zu verwenden.

Vor der Entscheidung, ob man sein 1.5-Template nach Joomla! 3
konvertiert, sollte ernsthaft darüber nachgedacht werden, ob nicht doch
ein ähnliches aktuelles Template infrage kommt. Die Vorteile sind, dass
es billiger und schneller im Einsatz ist, als die Konvertierung eines
alten Templates. Wenn das alte Template konvertiert werden soll, selbst
nicht in der Lage ist, dies zu tun, sollte man das Joomla! Community
Portal Service Providers Directory unter der Kategorie <a
href="https://community.joomla.org/service-providers-directory/listings/category/view/119-migrations-upgrades.html"
class="external text" target="_blank"
rel="noreferrer noopener">Migrations &amp; Upgrades</a> besuchen.

Protostar, das Template, das mit Joomla 3.x geliefert wird, ist
**nicht** kompatibel mit Joomla 4.x. Es muss einer der oben genannten
Schritte durchgeführt werden, um es für Joomla 4.x zu aktualisieren.

### Bei der Auswahl von Templates

- Sieh die Angebote eines Template-Anbieters an, die Auswahl ist
  meistens überwältigend
- Wenn es Dich überfordert, lege eine Pause ein, mach gegebenenfalls am
  nächsten Tag weiter
- Erinnere Dich. Bei der Umsetzung wird bei weitem nicht alles
  ausgenutzt, was das Template kann.
- Betrachte die Modulpositionen und Varianten des Templates
- Drink genug Wasser während der Suche nach Templates und bewege Dich ab
  und zu (die Suche kann also lange dauern)

## Einsatz des Standard-Templates Cassiopeia in Joomla! 4.x

Dieser Abschnitt ist unvollständig. Wenn Du Kenntnisse zu diesem Thema
hast, füge es bitte zu diesem Dokument hinzu. In der Zwischenzeit kann
auch eine Google-Suche über die Anpassung von Cassiopeia viele
Ergebnisse außerhalb der Joomla! Docs bringen.
