<!-- Filename: Pre-Update_Check / Display title: Kompatibilitätsprüfung (Pre-Update Check) -->

Neu in Joomla! 3.10.x ist die Komponente „Kompatibilitätsprüfung“. Diese
Ansicht der Komponente zeigt die technischen Spezifikationen des
Servers, auf dem die Website gehostet wird. Die Kern- und
Drittanbieter-Erweiterungen, welche den Update-Server verwenden, werden
in Listenform angezeigt.

**To navigate to the Update-screen:**

- Click the 'Live Update' tab.

**So ruft man die Installationsprüfung für das Update auf:**

- In der oberen Menüleiste auf den Menüpunkt **Komponenten **→** Joomla
  Update** klicken.
- Falls der Bildschirm die „Installationsprüfung“ nicht anzeigt, dann
  sollte man auf die Schaltfläche „Auf Updates prüfen“ klicken oder den
  Cache leeren und die Seite aktualisieren.
- Außerdem muss überprüft werden, ob die Seite auf dem Joomla Next
  Update Channel ist. **Administrator **→** Komponenten **→** Joomla
  Update **→** Optionen **→** Update-Server**. Hier *Joomla Next*
  wählen, dann auf *Speichern & Schließen* klicken.

## Technische Spezifikation

Der obere Teil der Kompatibilitätsprüfung zeigt, ob die aktuelle
Serverumgebung mit der aktuellen Zielversion von Joomla kompatibel ist,
sowohl für die erforderlichen PHP- als auch Datenbankeinstellungen. Die
Daten auf der Seite
<a href="https://downloads.joomla.org/technical-requirements"
class="external text" target="_blank"
rel="noreferrer noopener">Technische Anforderungen</a> zeigen die
Spezifikationen an, anhand derer wir prüfen.

<img
src="https://docs.joomla.org/images/thumb/5/51/Php_and_database_settings-de.png/800px-Php_and_database_settings-de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/5/51/Php_and_database_settings-de.png 1.5x"
data-file-width="912" data-file-height="593" width="800" height="520"
alt="Erforderliche PHP- und Datenbankeinstellungen der Komponente „Kompatibilitätsprüfung“" />
<img
src="https://docs.joomla.org/images/thumb/7/7d/Recommended_php_settings-de.png/800px-Recommended_php_settings-de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/7/7d/Recommended_php_settings-de.png 1.5x"
data-file-width="912" data-file-height="455" width="800" height="399"
alt="Empfohlene PHP-Einstellungen der Komponente „Kompatibilitätsprüfung“" />

Wichtig ist, dass Sie überprüfen, ob irgendetwas rot markiert ist und
mit Joomla 4.x nicht kompatibel sein wird. Wenn das der Fall ist, müssen
Sie mit Ihrem Hoster sprechen oder den Hoster wechseln, bevor Sie auf
Joomla 4.x migrieren können. Siehe auch  Warum
Migrieren
für weitere Informationen zur Planung und
Schritt-für-Schritt-Anleitungen.

## Kompatibilitätsprüfung für Erweiterungen

Die Komponente „Kompatibilitätsprüfung“ berücksichtigt auch
Erweiterungen von Drittanbietern.

Die Liste ist in Abschnitte unterteilt, die auf dem Tag *targetplatform*
basieren, den Erweiterungen, die gerade benutzt werden oder nicht. Für
Entwickler, siehe auch  Einsatz eines
Update-Servers
für weitere Informationen über diese Tags und wie man einen Update
Server einrichtet. Für weitere Informationen über das Joomla
Update-System, siehe die Seiten <a
href="https://extensions.joomla.org/support/knowledgebase/submission-requirements/joomla-update-system-requirement/"
class="external text" target="_blank" rel="noreferrer noopener">Joomla!
Update System Voraussetzungen</a> und <a
href="https://docs.joomla.org/Help39:Extensions_Extension_Manager_Update"
class="external text" target="_blank"
rel="noreferrer noopener">Erweiterungen Erweiterungs-Manager Update</a>.

Durch Klicken auf den Link **Details** rechts in jeder farbigen
Überschrift können zusätzliche Informationen zu den auf der Website
installierten Erweiterungen angezeigt werden.

<img
src="https://docs.joomla.org/images/thumb/f/f5/Pre_upgrade_checker_error-de.png/800px-Pre_upgrade_checker_error-de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/f/f5/Pre_upgrade_checker_error-de.png/1200px-Pre_upgrade_checker_error-de.png 1.5x, https://docs.joomla.org/images/f/f5/Pre_upgrade_checker_error-de.png 2x"
data-file-width="1320" data-file-height="451" width="800" height="273"
alt="Update-Informationen nicht verfügbar" />

Die hier aufgeführten Erweiterungen unterstützen noch nicht das
Joomla-Update-System oder haben zumindest keinen targetplatform-Tag, der
die Unterstützung für die ausgewählte Ziel-Joomla-Version anzeigt.
(siehe  Einen Update-Server
bereitstellen
Zur Überprüfung der Kompatibilität mit 4.x sollte der Entwickler der
aufgeführten Erweiterungen kontaktiert werden.

<img
src="https://docs.joomla.org/images/thumb/d/da/Pre_upgrade_checker_warning-de.png/800px-Pre_upgrade_checker_warning-de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/d/da/Pre_upgrade_checker_warning-de.png/1200px-Pre_upgrade_checker_warning-de.png 1.5x, https://docs.joomla.org/images/d/da/Pre_upgrade_checker_warning-de.png 2x"
data-file-width="1281" data-file-height="372" width="800" height="232"
alt="Update erforderlich" />

Die hier aufgeführten Erweiterungen benötigen ein Update, um unter 4.x
korrekt zu funktionieren. Bitte den Entwickler der aufgeführten
Erweiterungen kontaktieren, um abzuklären, ob die Komponente vor oder
nach dem Upgrade aktualisiert werden muss.

<img
src="https://docs.joomla.org/images/thumb/5/51/Pre_upgrade_checker_ok-de.png/800px-Pre_upgrade_checker_ok-de.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/5/51/Pre_upgrade_checker_ok-de.png/1200px-Pre_upgrade_checker_ok-de.png 1.5x, https://docs.joomla.org/images/5/51/Pre_upgrade_checker_ok-de.png 2x"
data-file-width="1277" data-file-height="285" width="800" height="179"
alt="Kein Update erforderlich" />

Die hier aufgeführten Erweiterungen geben an, dass sie 4.x-kompatibel
sind und kein Update erforderlich ist.

## Was hat es mit diesem *potenziell ernsten Upgrade-Problem* auf sich?

Plugins vom Typ (*system*, *user*, *authentication*, *actionlog*,
*twofactorauth*) könnten während der Ausführung des Upgrades gestartet
werden. Wenn es ein kritisches Problem innerhalb dieses Plugins gibt,
könnte dies zu einem beschädigten Upgrade führen und die Website
unbrauchbar machen. Aus diesem Grund muss jedes Plugin dieses Typs, das
nicht explizit als kompatibel aufgeführt ist, noch sorgfältiger
überprüft werden, bevor der Upgrade-Button gedrückt wird. Es wird
**dringend** empfohlen, die fraglichen Plugins zu deaktivieren und mit
dem jeweiligen Entwickler Rücksprache zu halten.

<img
src="https://docs.joomla.org/images/thumb/1/1e/Pre_upgrade_checker_popup-en.png/200px-Pre_upgrade_checker_popup-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/1/1e/Pre_upgrade_checker_popup-en.png/300px-Pre_upgrade_checker_popup-en.png 1.5x, https://docs.joomla.org/images/thumb/1/1e/Pre_upgrade_checker_popup-en.png/400px-Pre_upgrade_checker_popup-en.png 2x"
data-file-width="492" data-file-height="446" width="200" height="181"
alt="Die Popup-Warnung für ein mögliches Upgrade-Problem" />

Auf der Registerkarte *Live-Update* wird erneut die vollständige Liste
der potenziell gefährlichen Erweiterungen angezeigt.

<img
src="https://docs.joomla.org/images/thumb/b/b1/Live_upgrade_tab_errors-en.png/800px-Live_upgrade_tab_errors-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/b/b1/Live_upgrade_tab_errors-en.png/1200px-Live_upgrade_tab_errors-en.png 1.5x, https://docs.joomla.org/images/thumb/b/b1/Live_upgrade_tab_errors-en.png/1600px-Live_upgrade_tab_errors-en.png 2x"
data-file-width="2042" data-file-height="787" width="800" height="308"
alt="Die Live-Update-Meldung über mögliche störende Erweiterungen" />

Es wird **dringend** empfohlen, alle Erweiterungen einschließlich der
hier aufgelisteten Plugins zu deaktivieren, bevor das Upgrade gestartet
wird, da die hier aufgelisteten Erweiterungen nicht mit der Zielversion
kompatibel sein dürften und das Upgrade beschädigen könnten.

Wie mit Warnungen umgehen? Wenn die Warnungen nicht beachtet werden und
das Upgrade trotzdem durchgeführt werden soll, kann dies durch
Aktivieren der entsprechenden Option erfolgen. Da dies das Risiko mit
sich bringt, dass die Website nicht mehr ohne Weiteres wiederhergestellt
werden kann, ist dieses die letzte Erinnerung, dass ein Backup
erforderlich ist!

## Fragen und Antworten

Wir wollen das Ganze in einige Fragen und Antworten aufschlüsseln.

**F: Was bedeuten die Markierungen?**

A: Die grüne Markierung **Kein Update erforderlich** bedeutet, dass die
Erweiterung vom Entwickler als bereit für Joomla 4 markiert wurde. Sie
*sollte* mit einem Klick von 3.10.x auf 4.x umgestellt werden können.
Eine Überprüfung beim Entwickler wird empfohlen.

Die rote Markierung **Update-Informationen nicht verfügbar** bedeutet,
dass die Erweiterung keine Kompatibilitätsinformationen zur Erweiterung
hinterlegt hat. Eine Nachfrage beim Entwickler über die Umstellung von
3.10.x auf 4.x ist erforderlich.

Die gelb/orange Markierung **Ja (x.x.x)** bedeutet, dass die Erweiterung
vom Entwickler markiert wurde und dass die Erweiterung möglicherweise
ein Update benötigt, um mit Joomla 4 kompatibel zu sein. Die Erweiterung
könnte man aktualisieren und sehen, ob sich ein grünes „Ja“ zeigt. Wenn
nicht, sollte beim Entwickler wegen des Umstiegs von 3.10.x auf 4.x
nachgefragt werden.

Die graue Anzeige **Fehlendes Kompatibilitäts-Tag** bedeutet, dass die
Erweiterung kein Tag hat **oder** den Update-Server nicht verwendet. Der
Entwickler hat weder ja noch nein gesagt bzw. benötigt ein Update. In
einigen Fällen kann ein Paket installiert worden sein und der
Komponentenanteil hat ein Tag, aber die zusätzlichen Plugins oder Module
haben keine Tags. Wie immer muss man sich bei den Entwicklern der
Erweiterungen erkundigen, um den Migrationsweg von 3.10.x auf 4.x zu
klären.

**F: Was ist mit den Joomla-Kernkomponenten?**

A: Joomla-Core-Erweiterungen werden mit einem Klick von 3.10.x auf 4.x
migriert, mit diesen Ausnahmen:

Die Sprachpakete sind noch nicht bereit für Joomla 4 (Stand: September
2020). Mit der Zeit werden sie es sein. Wenn die Website von anderen
Sprachpaketen abhängt, sollte man mit der Migration warten, bis alle
Sprachpakete fertig sind.

Die Weblinks-Komponente ist noch nicht bereit für Joomla 4 (Stand:
September 2020). Wenn weiterhin Weblinks in der Joomla 4-Website
verwendet werden sollen, sollte man mit der Migration warten, bis die
Weblinks-Komponente fertig ist.

**F: Was ist mit den Templates?**

A: Aufgrund der Änderungen in Joomla 4 kann ein Template mit Joomla 4
kompatibel sein oder nicht. Die Kern-Templates wie Protostar, Beez3,
Beez5 und so weiter werden mit einem Klick in das neue
Cassiopeia-Template *konvertiert* und ältere Templates werden komplett
entfernt. Wenn man ein Club-Template eines Drittanbieters benutzt, das
nicht mit Joomla 4 kompatibel ist, muss man sein Standard-Template auf
Protostar (oder Beez3) ändern, bevor man den 1-Klick macht. Falls ältere
Administrator-Templates oder Core-Templates vorhanden sind, ist es
empfehlenswert, alle zu deinstallieren, mit Ausnahme derjenigen
Core-Templates, die als Standard eingestellt werden sollen. Dazu gehören
Bluestork, Hathor und die anderen beez Templates. Als
Administrator-Template bleibt Isis erhalten. Entweder man behält das
kompatible Template eines Drittanbieters, Protostar oder Beez3 als
Standard. Der Rest wird deinstalliert.

**F: Kann man plg_content_geshi deinstallieren?**

A: Ja. Dies ist ein Überbleibsel aus dem Entwicklungszyklus von 2.5 und
**muss** deinstalliert werden.

**F: Was ist mit all den FOF, fef, usw.?**

A: Viele Erweiterungen aus den roten oder gelb/orangen Überschriften
**werden/können** den 1-Klick passieren und problemlos migrieren. Es
wird empfohlen, dass man zu Erweiterungen→Verwalten→Verwalten geht und
alle Erweiterungen überprüft. Normalerweise werden die Erweiterungen,
die von Joomla erstellt wurden, mit einem Klick migriert. Typischerweise
werden auch die Akeeba-Erweiterungen migriert. Auch hier sollte man sich
bei den Entwicklern der Erweiterungen erkundigen, um den Migrationspfad
für **alle** Erweiterungen von Drittanbietern zu überprüfen.

**F: Zeigt die Prüfung der Erweiterungen vor dem Update alle auf der
Website installierten Erweiterungen an?**

A: Die Kompatibilitätsprüfung zeigt alle Erweiterungen an. Nur
Erweiterungen, die den Update-Server verwenden, erhalten
Kompatibilitätsinformationen. Diejenigen Erweiterungen, die den
Update-Server nicht verwenden, werden in der Liste mit dem '***Fehlenden
Kompatibilitäts-Tag'*** angezeigt.

## Zusammenfassung

Vom Standpunkt der Migration aus betrachtet, ist es meine Überzeugung,
dass die Überprüfung vor dem Update als Leitfaden verwendet werden
sollte. Es empfiehlt sich, eine zweite Registerkarte über
"Erweiterungen→Verwalten→Verwalten" zu öffnen, um Erweiterungen zu
deinstallieren oder zu prüfen, von wem sie stammen, damit die Entwickler
von Dritthersteller-Erweiterungen über den Weg zur Migration kontaktiert
werden können, den sie für die Migration ihrer Erweiterungen festgelegt
haben.
