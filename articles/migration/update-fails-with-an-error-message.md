<!-- Filename: J3.x:Update_fails_with_an_error_message / Display title: Update schlägt mit einer Fehlermeldung fehl -->

Joomla!  3.6.1

## Berichtete Fehler

Wenn bei der Aktualisierung mit der integrierten Joomla!-Aktualisierung
Erweiterung zur Version 3.6.1 die folgende Fehlermeldung angezeigt wird:
<img
src="https://docs.joomla.org/images/3/3f/Joomla-3.6.1-error-message-de.png"
decoding="async" data-file-width="800" data-file-height="38" width="800"
height="38" alt="Joomla-3.6.1-error-message-de.png" />

## Betroffene Versionen

Allgemeine Informationen

Dies betrifft nur die Joomla! Version(en): **3.6.1**

## Was ist die Ursache?

3.6.1 führt einen CSRF-Token ein, um die Joomla!-Aktualisierung
Komponente als eine zusätzliche Sicherheits-Ebene zu prüfen. Joomla!
3.6.0 bis hin zu 2.5.4 (quasi jede Version mit der
Aktualisierungs-Komponente) können von dem CSRF-Token-Problem betroffen
sein, da diese Versionen den Code zum Bestehen der Prüfung nicht
generieren. Zukünftige Updates werden ordnungsgemäß funktionieren

## Wie ist der Fehler zu lösen?

### Update von Joomla! mit Version 3.6.0

- Gehe zurück zum Administrations-Bereich
  `beispieldomain.de/administrator`
- Dann gehe zu Erweiterungen  **→**  Verwalten  **→**  Datenbank
- Es sollte eine Meldung sichtbar sein, dass die Datenbank veraltet ist.
- Klicke auf den **Reparieren**-Button links unter der Symbolleiste.

### Update von Joomla! KLEINER als Version 3.6.0

Wenn noch eine Version niedriger als 3.6.0 läuft:  

- Mach zuerst ein Update auf Joomla! 3.6.0 und **NICHT** direkt nach
  Joomla! 3.6.1  
- Aktualisiere die `com_joomlaupdate` (Joomla!-Aktualisierung
  Komponente) über den Erweiterungsmanager  
- und führe dann das Update von Joomla! 3.6.0 nach Joomla! 3.6.1 durch.

Die neue Version der `com_joomlaupdate` (Joomla!-Aktualisierung
Komponente) ist im Backend durch den normalen Erweiterungs-Aktualisierer
verfügbar.

Für mehr Informationen

Lies bitte die offizielle Mitteilung zu dieser Fehlfunktion <a
href="https://www.joomla.org/announcements/release-news/5666-the-joomla-3-6-1-update.html"
class="external text" target="_blank" rel="noreferrer noopener">HIER</a>

'*Hinweis*: Wenn die Website mit PHP 5.3 läuft, wird diese Fehlermeldung
möglicherweise angezeigt, wenn man versucht, sich anzumelden:  
` 0 Failed to start the session: already started by PHP ($_SESSION is set).`  
Joomla! 3.6.2 wird dieses Problem lösen. Siehe
<a href="https://github.com/joomla/joomla-cms/pull/11430"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Fix logging in in PHP 5.3</a>.
