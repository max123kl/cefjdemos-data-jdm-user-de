<!-- Filename: Potential_backward_compatibility_issues_in_Joomla_4 / Display title: Rückwärtskompatibilität: Mögliche Probleme in Joomla 4 -->

<img
src="https://docs.joomla.org/images/thumb/e/e5/Quill_icon.png/30px-Quill_icon.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/e/e5/Quill_icon.png/45px-Quill_icon.png 1.5x, https://docs.joomla.org/images/thumb/e/e5/Quill_icon.png/60px-Quill_icon.png 2x"
data-file-width="71" data-file-height="59" width="30" height="25"
alt="Quill icon.png" />Content is Incomplete

This article or section **is incomplete, which means it may be lacking
information.** You are welcome to assist in its completion by editing it
as well. If this article or section <a
href="https://docs.joomla.org//docs.joomla.org/index.php?title=Potential_backward_compatibility_issues_in_Joomla_4/de&amp;action=history"
class="external text" target="_blank" rel="noreferrer noopener"></a> <a
href="https://docs.joomla.org//docs.joomla.org/index.php?title=Potential_backward_compatibility_issues_in_Joomla_4/de&amp;action=history"
class="external text" target="_blank" rel="noreferrer noopener">has not
been edited in several days</a>, please consider helping complete the
content.
<span class="small">This article was <a
href="https://docs.joomla.org//docs.joomla.org/index.php?title=Potential_backward_compatibility_issues_in_Joomla_4/de&amp;diff=cur"
class="external text" target="_blank" rel="noreferrer noopener">last
edited</a> by
Max123kl
(talk\|
contribs
5 months ago. *(<a
href="https://docs.joomla.org//docs.joomla.org/index.php?title=Potential_backward_compatibility_issues_in_Joomla_4/de&amp;action=purge"
class="external text" target="_blank"
rel="noreferrer noopener">Purge</a>)*</span>

In diesem Dokument werden mögliche Probleme mit der
Abwärtskompatibilität für Joomla! 4 behandelt. Es werden Probleme
aufgelistet, die möglicherweise zu Problemen mit Erweiterungen führen.

Die Vergleichsbasis ist Joomla! 3.10.

## Aktualisierte Systemanforderungen

Die Systemanforderungen wurden wie folgt aktualisiert:

- PHP 7.2.5
- MySQL 5.6
- PostgreSQL 11.0
- SQL-Server Support wurde eingestellt.

### PHP MySQL Erweiterung

- Joomla unterstützt die Verwendung des PHP-Treibers ext/mysql (der in
  PHP 7.0 entfernt wurde) **nicht mehr**. Joomla wird automatisch
  versuchen, die mysqli-Erweiterung (verfügbar seit PHP 5.3) oder den
  mysql-PDO-Treiber (verfügbar seit PHP 5.3) zu verwenden. Andernfalls
  wird keine Datenbankverbindung hergestellt.
- Der Strict-Modus wurde aktiviert. Die folgenden Flags sind jetzt
  standardmäßig in Joomla 4 aktiv und möglicherweise müssen die
  Datenbankabfragen entsprechend aktualisiert werden. Das wird uns bei
  zukünftigen Upgrades der MySQL-Version helfen und wird auch enger an
  Postgres ausgerichtet, um eine einfachere Kompatibilität mit Abfragen
  in beiden Sprachen zu ermöglichen.
    'STRICT_TRANS_TABLES',
    'ERROR_FOR_DIVISION_BY_ZERO',
    'NO_AUTO_CREATE_USER',
    'NO_ENGINE_SUBSTITUTION',

Folglich wird Joomla 4 nur **NULL-Datumsvorgaben** verwenden. Die
Verwendung des *invalid default date* von 0000-00-00 00:00:00 in Joomla
4 ist veraltet.

### PHP Postgres Erweiterung

- Joomla unterstützt die Verwendung des PHP-Treibers ext/pgsql nicht
  mehr. Joomla wird automatisch versuchen, den PostgreSQL PDO-Treiber
  (verfügbar seit PHP 5.3 und Joomla 3.9) zu verwenden, andernfalls wird
  keine Verbindung mit der Postgres-Datenbank hergestellt.

### PHP GMP Erweiterung

Das ist für die Verwendung der Funktion  WebAuthn Passwordless
Login
erforderlich. Hinweis: Die PHP-GMP-Erweiterung ist standardmäßig auf den
meisten Hosting-Sites installiert. Das  WebAuthn Passwordless
Login
System-Plugin ist in Joomla 4 auf https-Seiten standardmäßig aktiviert.

### PHP mcrypt Erweiterung

Diese Erweiterung ist für die Verwendung der Klasse
Joomla\CMS\Crypt\Cipher\CrytoCipher und ihres Alias JCryptCipherCrypto
erforderlich.

## CMS Libraries

Die folgenden Änderungen wurden in den Joomla! CMS-Bibliotheken gemacht,
das ist hauptsächlich der Code, der in Joomla! 3.7 und früheren
Versionen im Verzeichnis „libraries/cms“ gefunden wurde.

### Installer

- Plugin Discover-Installationen suchen nicht mehr nach Xml-Dateien in
  den Joomla! 1.5 Plugin-Ordner-Layouts.
- In 3.x haben nur Plugin-Skripte die Preflight-Methode aufgerufen und
  keine macht Postflight während des Deinstallationsprozesses verfügbar.
  Bei allen Erweiterungstypen werden diese Hooks
  (Programm-Schnittstellen) in 4.0 verfügbar sein, wenn sie
  deinstalliert werden. Wenn Sie derzeit ein Preflight und ein
  Postflight durchführen und davon ausgehen, dass sie nur in einem
  Installations-/Aktualisierungskontext angewendet werden, ist diese
  Logik jetzt falsch und Sie sollten die Installationsroute verwenden
  (die als einer der Methodenparameter angegeben wird).
- Bei der Deinstallation eines Plugins wird jetzt die
  Deinstallationsfunktion im Erweiterungs-Skript ausgelöst, bevor
  SQL-Abfragen ausgelöst werden (dies ist jetzt mit allen anderen
  Erweiterungstypen konsistent).

#### aus Joomla! entfernte Klassen

Die folgenden Klassen wurden in Joomla! 4.0 entfernt:

- JInstallerComponent (ersatzweise JInstallerAdapterComponent benutzen)
- JInstallerFile (ersatzweise JInstallerAdapterFile benutzen)
- JInstallerLanguage (ersatzweise JInstallerAdapterLanguage benutzen)
- JInstallerLibrary (ersatzweise JInstallerAdapterLibrary benutzen)
- JInstallerModule (ersatzweise JInstallerAdapterModule benutzen)
- JInstallerPackage (ersatzweise JInstallerAdapterPackage benutzen)
- JInstallerPlugin (ersatzweise JInstallerAdapterPlugin benutzen)
- JInstallerTemplate (ersatzweise JInstallerAdapterTemplate benutzen)
- JSubMenuHelper (ersatzweise JHtmlSidebar benutzen. Bitte beachten: im
  Gegensatz zu JSubMenuHelper muss jetzt ein Platzhalter in der
  Ansichtsvorlage hinzugefügt werden)

#### JInstallerAdapter Vererbung

JInstallerAdapter ist nicht mehr von JAdapterInstance abhängig und von
Natur aus JObject.

Benutzerdefinierte Installer-Adapter müssen jetzt automatisch geladen
werden.

### Menü

#### JMenu ist jetzt eine abstrakte Klasse

JMenu ist jetzt eine abstrakte Klasse. Unterklassen von JMenu müssen
jetzt auch eine Lademethode implementieren.

#### Manuelles Include-Verhalten entfernt

Die Logik in JMenu::getInstance(), eine Datei manuell aus dem Pfad
includes/menu.php der Anwendung einzubinden, wurde entfernt. Die
Unterklasse JMenu sollte stattdessen automatisch geladen werden.

#### JMenuItem

- Die Eigenschaft params kann nicht mehr direkt aus JMenuItem abgerufen
  werden. Stattdessen sollte die Methode getParams() verwendet werden
  (verfügbar seit Joomla 3.7)
- JMenuItem::set und JMenuItem::get wurden entfernt. Die Eigenschaften
  müssen eindeutig benannt werden
- Es gibt jetzt die Klasse AdministratorMenuItem, die von MenuItem
  abhängt und zusätzliche öffentliche Eigenschaften enthält, die im
  Administrator Menü-Eintrag verwendet werden.

### Pagination

- Die beiden magischen Funktionen für die Paginierung
  (Seitennummerierung) *pagination_item_active* und
  *pagination_item_inactive* wurden entfernt. Stattdessen sollte jetzt
  joomla.pagination.link aus JLayouts verwendet werden
- Die magische Funktion für die Paginierung *pagination_list_render* ist
  veraltet. Man sollte daher joomla.pagination.list aus JLayout
  verwenden

### Pathway

#### Manuelles Include-Verhalten entfernt

Die Logik in JPathway::getInstance(), eine Datei aus dem Pfad
includes/pathway.php der Anwendung manuell einzubinden, wurde entfernt.
Die Unterklasse JPathway sollte stattdessen automatisch geladen werden.

### Router

#### Manuelles Include-Verhalten entfernt

Die Logik in JRouter::getInstance(), eine Datei manuell aus dem Pfad
includes/router.php der Anwendung einzubinden, wurde entfernt. Die
Unterklasse JRouter sollte stattdessen automatisch geladen werden.

#### Änderungen der Methodensignatur

Die attachBuildRule und attachParseRule sind nun typisiert, um Callables
zu benötigen.

### JVersion

Unterstützung für den Zugriff auf die JVersion-Klassenkonstanten als
Klasseneigenschaften wird nicht mehr unterstützt. Die Konstanten wurden
in Joomla! 3.5 eingeführt, um zu verhindern, dass die alten
Klasseneigenschaften bearbeitet werden können.

Die folgenden veralteten Konstanten wurden entfernt:

- JVersion::RELEASE
- JVersion::DEV_LEVEL
- JVersion::BUILD

### JHtml

- Die Registerfunktion in JHtml ist nun typisiert, um eine Callable zu
  benötigen. Unterklassen von JHtml müssen nun mit dieser Signatur
  übereinstimmen (beachte, dass dies bereits auf Funktionscode-Ebene
  erforderlich war).
- JHtml::\_ erlaubt es nicht mehr, nicht-öffentliche Methoden in JHtml
  aufzurufen
- JHtml::\_ ist nun eine endgültige Methode (Man kann sie nicht mehr
  überschreiben, wenn mandie Unterklasse JHtml verwendet) und ihre
  Signatur hat sich geändert, um die Vorteile moderner PHP-Funktionen
  (skalare und variadische Typisierungspunkte) zu nutzen.
- JHtmlBootstrap::modal wurde entfernt. Verwende
  JHtmlBootstrap::renderModal
- JHtmlSortablelist::sortable wurde zugunsten von
  JHtmlDraggablelist::draggable als veraltet eingestuft – die alte
  Methode dient als Proxy für die neue Methode, um die Entfernung von
  jQuery UI aus dem Joomla Kern zu erleichtern. Alle Media Assets, die
  sich auf die ursprüngliche jQuery UI-Implementierung beziehen, wurden
  entfernt.
- JHtmlBatch wurde entfernt, da der gesamte Code in die Layouts für die
  Overrides von Templates verschoben wurde. Man sollte JLayouts im Code
  direkt verwenden.

### Updater

- Wir haben die veraltete Handhabung von Ganzzahl-Clients aus der
  Adapterklasse der Updater-Erweiterung entfernt. Bitte jetzt **site**
  und **administrator** verwenden und nicht mehr die Integer-Werte **0**
  / **1**.

## Plattform

Die folgenden Änderungen wurden an den Bibliotheken der Joomla!
Plattform vorgenommen (dies ist in erster Linie Code, der sich in den
Verzeichnissen \`libraries/joomla\` oder \`libraries/legacy\` in Joomla!
3 befindet).

### Access

- JAccess::\$assetPermissionsById und JAccess::\$assetPermissionsByName
  und JAccess::preloadPermissionsParentIdMapping wurden ersatzlos
  entfernt. Seit Version 3.6 haben wir andere Methoden und
  Klasseneigenschaften verwendet, um das Laden von Assets zu optimieren.
  Siehe den <a href="https://github.com/joomla/joomla-cms/pull/12850"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Pull-Request: JAccess Bugfixes und
  Optimierungen</a>, um die Gründe für diese Maßnahme zu erfahren.
- JAccess::getActions wurde entfernt. Stattdessen sollte
  JAccess::getActionsFromFile oder JAccess::getActionsFromData verwendet
  werden.

### Application

#### aus Joomla! entfernte Klassen

Die folgenden Klassen wurden in Joomla! 4.0 entfernt:

- JApplicationWebRouter (verwenden Sie stattdessen das Paket
  \`joomla/router\`)
- JApplicationWebRouterBase (verwenden Sie stattdessen das Paket
  \`joomla/router\`)
- JApplicationWebRouterRest (verwenden Sie stattdessen das Paket
  \`joomla/router\`)

Alle Referenzen auf JSite und JAdministrator wurden entfernt (diese
waren seit Joomla 3.2 nur noch sogenannte Alias-Klassen)

#### = Veraltete Klassen

Die folgenden Klassen sind veraltet und für die Entfernung in Joomla!
5.0 geplant:

- JApplicationBase (verwenden Sie stattdessen
  Joomla\Application\Application\AbstractApplication)

#### Änderungen an CLI/Web-Klassen

Die Klassen JApplicationCli und JApplicationWeb wurden neu
zusammengesetzt, um stattdessen aus dem Anwendungspaket des Frameworks
zu erweitern. Dies bricht die Typprüfung für ein JApplicationBase-Objekt
ab. Aus Gründen der Aufwärtskompatibilität wird empfohlen, zu prüfen, ob
Anwendungsklassen eine Instanz von
Joomla\Application\AbstractApplication sind (JApplicationBase hat diese
Klasse seit Joomla! 3.4 erweitert).

Zusätzlich sind diese beiden Klassen nun abstrakt. Entwickler, die diese
Klassen implementieren, müssen eine \`doExecute'-Methode mit der Logik
ihrer Anwendung bereitstellen.

Die registerEvent-Methode ist nun typischerweise so eingestellt, dass
für den \$handler-Parameter eine Aufrufbarkeit erforderlich ist.

Anwendungen, die sowohl Web- als auch CLI-Anwendungen unterstützen
wollen, sollten nun gegen das \Joomla\CMS\Application\\
CMSApplicationInterface antreten - dies enthält gängige Methoden (einige
davon wurden in Joomla 3.x nur in der Klasse JApplicationCms gefunden),
die von allen Codes verwendet werden können. Es wird dringend empfohlen,
dass alle benutzerdefinierten Anwendungen (insbesondere CLI-Anwendungen)
diese Schnittstelle implementieren, um Kompatibilitätsprüfungen zu
erleichtern. Gleichzeitig sollten alle Typ-Hints die Schnittstelle und
nicht eine konkrete Klasse verwenden.

##### JApplicationCli

- Alt: JApplicationCli **→** JApplicationBase **→** 
  Joomla\Application\AbstractApplication
- Neu:
  JApplicationCli **→** Joomla\Application\AbstractCliApplication **→** 
  Joomla\Application\AbstractApplication

##### JApplicationWeb

- Alt: JApplicationWeb **→** JApplicationBase **→** 
  Joomla\Application\AbstractApplication
- Neu:
  JApplicationWeb **→** Joomla\Application\AbstractWebApplication **→** 
  Joomla\Application\AbstractApplication
- Die alten Methoden zum Aufruf von JApplicationWeb::redirect wurden
  entfernt.
  - Mit einer Nachricht und messageType-Parametern (Aufruf von
    enqueueMessage separat)
  - Die Übergabe eines True/False-Wertes als 2nd/3rd-Params anstelle
    eines Redirect-Codes führt zu einer InvalidArgumentException,
    anstatt auf ein 303 zu setzen.
- JApplicationWeb::\$singleValueResponseHeaders wurde entfernt, da die
  Framework-Anwendung ab dem Release 2.0 intern PSR-7 Response-Objekte
  verwenden wird. Dies ändert die Art und Weise, wie die Kopfdaten
  gespeichert werden, so dass es sich immer um ein multidimensionales
  Array handelt, wobei jeder Top-Level-Schlüssel die Headernamen und der
  Wert ein Array mit allen Werten für diesen Header ist.

##### CMSApplication

- Die Klasseneigenschaften \$\_clientId, \$\_messageQueue und \$\_name
  wurden alle umbenannt, um das Unterstrichpräfix zu entfernen.
- Implementiert nun die CMSApplicationInterface.
- Wenn ein Fehler beim Abrufen eines Pathway-, Router- oder Menüobjekts
  mit den entsprechenden Methoden auftritt, poppt die Ausnahme nun auf
  und nicht mehr die Methode, die die Ausnahme stillschweigend abfängt
  und null zurückgibt
- CMSApplication::getInstance will now additionally try and load the
  user object (using the loadIdentity function)
- ConsoleApplication und ApiApplication können zu irreführenden
  Ergebnissen führen. Bitte verwende CMSApplication::isClient (verfügbar
  ab <img src="https://docs.joomla.org/images/a/a7/Compat_icon_3_7.png"
  decoding="async" data-file-width="40" data-file-height="17" width="40"
  height="17" alt="Joomla 3.7" />). Weitere Informationen finden Sie
  unter  Discover auf welchem Client Ihr Extensionscode
  läuft.

##### JApplicationSite

Die Klasseneigenschaften \$\_language_filter und \$\_detect_browser
wurden umbenannt, um den Unterstrich-Präfix zu entfernen.

Die veraltete Methode JApplicationSite::getPageParameters wurde
zugunsten ihres Alias JApplicationSite::getParams entfernt.

##### JApplicationHelper

JApplicationHelper::parseXMLLangMetaFile wurde ersatzlos entfernt.

### Archiv

- Das Archivpaket wurde zugunsten des Frameworks-Archivpakets entfernt.
  Beachte, dass die API unverändert bleiben sollte.
- Bei der Fehlerbehandlung werden nun Ausnahmen anstelle von JError
  verwendet.

### Client

\Joomla\CMS\Client\ClientWrapper wurde entfernt. Verwendung der
statischen Methoden in \Joomla\CMS\Client\ClientHelper

### Crypt

- JCrypt::hasStrongPasswordSupport wurde ersatzlos entfernt, da alle
  PHP-Versionen, die mit Joomla 4 kompatibel sind, ein starkes
  Passwort-Hashing unterstützen.

#### aus Joomla! entfernte Klassen

Die folgenden Verschlüsselungen wurden in Joomla! 4.0 entfernt:

- JCryptCipher3Des
- JCryptCipherBlowfish
- JCryptCipherMcrypt
- JCryptCipherRijndael256
- JCryptCipherSimple

diese wurden ersatzlos entfernt. Verwenden Sie JCryptCipherCrypto

#### aus Joomla! entfernte Methoden

- JCrypt::hasStrongPasswordSupport wurde ersatzlos entfernt (dies
  versuchte, bcrypt polyfills auf Linux-Hosting zu erkennen, gab aber
  immer true zurück, da wir PHP 5.3.10 in Joomla 3.3 benötigten).

### Cache

- JCacheController::get benötigt jetzt eine aufrufbare. Dadurch wurde
  JCacheControllerCallback::call entfernt.
- JCacheStorage::test wurde entfernt. Verwende stattdessen
  JCacheStorage::isSupported.
- Die Standardspeicher-Engines werden nicht mehr manuell geladen, da sie
  nun automatisch geladen werden.
- JCacheControllerOutput::start und JCacheControllerOutput::end wurden
  ersatzlos entfernt.
- CacheLite-Speicher wurde entfernt, da er nicht mit PHP7 kompatibel ist
  (was unsere Minimalversion ist).
- Die Fehlerbehandlung verwendet nun Exceptions anstelle von JError.

### Komponente

- \Joomla\CMS\Component\Component\ComponentRecord erweitert JObject
  nicht mehr.

### Dokument

#### Änderung bei der Vererbung

Die folgenden Klassen haben ihre Vererbung geändert:

- JDocumentError (reicht jetzt von \Joomla\Cms\Document\HtmlDocument
  anstelle von \Joomla\Cms\Document\Document)

Hinweis: Als Ergebnis dieser Änderung setzt das Rendern einer
Fehlerseite das Dokument-Objekt in Joomla\CMS\Factory::\$document
zurück. Der Grund dafür ist, dass wir ein sauberes Dokument wollen, mit
dem wir arbeiten können. Wenn die Fehlerseite ausgelöst wird, sind wir
nicht an den Metadaten interessiert, welche die Komponente gesetzt hat
oder an den Medien, die von einem fehlerhaften Modul hinzugefügt wurden
oder welches Plugin auch immer der Darstellung hinzugefügt wurde. Wir
wollen eine saubere Umgebung zum Rendern der Fehlerseite, die nur die
geladenen Daten der Fehlerseite enthält.

#### Renderer

- Um der RSS-Feed-Spezifikation zu entsprechen, erlaubt
  JDocumentRendererFeedRss nun die Konfiguration des lastBuildDate
  Elements über die Klasseneigenschaft JDocumentFeed::\$lastBuildDate,
  wenn ein Feed gerendert wird. Dieser Wert ist standardmäßig auf die
  aktuelle Zeit voreingestellt, wie es bei Joomla! 3.x und früher der
  Fall ist, jedoch kann die Zeit korrekt eingestellt werden, indem man
  diese Klasseneigenschaft in ein JDate-Objekt ändert, das den
  gewünschten Zeitstempel darstellt.
- hier ist nun ein RendererInterface, das alle Renderer implementieren
  sollten.
- JDocumentRenderer ist nun eine abstrakte Klasse und implementiert
  RendererInterface.
- Alternativ zu kann man nun für Metadaten, für CSS und für Javascript
  einzeln laden. Die Absicht ist es, den Benutzern optional zu erlauben,
  alle Javascripts am unteren Rand des HTML-Dokuments in ihren Vorlagen
  zu platzieren.

#### JDocumentFeed

Der Eigenschaftstyp von JDocumentFeed::\$lastBuildDate wurde von einer
Zeichenkette in ein JDate-Objekt geändert. Die Eigenschaft wurde bisher
nicht von der Core Joomla API verwendet, aber Erweiterungen können es
verwendet haben.

### Datenbank

- Dieses Paket wurde durch das Joomla Framework Database Package
  ersetzt.
- Der Debug-Modus wurde überarbeitet (siehe die Framework-Dokumente für
  weitere Informationen).
  <a href="https://github.com/joomla-framework/database"
  class="external autonumber" target="_blank"
  rel="nofollow noreferrer noopener">[1]</a>)

### Factory

- Factory::getApplication nimmt keine Argumente mehr an. Diese waren
  irreführend, da sie immer die aktive Anwendung nach dem ersten Aufruf
  im Bootstrap zurückgaben, egal welche Argumente in die Funktion
  übergeben wurden.
- Factory::getXml wurde zusammen mit dem JXMLElement entfernt. Verwende
  stattdessen SimpleXMLElement direkt.
- Factory::: getEditor wurde entfernt, verwende stattdessen
  JEditor::getInstance.
- Factory:: getUri wurde entfernt, verwende stattdessen
  Uri::getInstance().

### Umgebung

- JBrowser::isSSLConnection has been removed. Use
  JApplicationCms::isSSLConnection (available since Joomla 3.2)

### Dateisystem

- Die Wrapperklassen des Dateisystems wurden entfernt. Verwende
  weiterhin die ursprünglichen statischen Methoden.

### Filter

- JFilterInput::\_remove wurde entfernt zugunsten von
  JFilterInput::remove
- JFilterInput::\_cleanTags wurde entfernt zugunsten von
  JFilterInput::cleanTags
- JFilterInput::\_cleanAttributes wurde entfernt zugunsten von
  JFilterInput::cleanAttributes
- JFilterInput::\_decode wurde entfernt zugunsten von
  JFilterInput::decode
- JFilterInput::\_escapeAttributeValues wurde entfernt zugunsten von
  JFilterInput::escapeAttributeValues
- JFilterInput::\_stripCSSExpressions wurde entfernt zugunsten von
  JFilterInput::stripCSSExpressions

Alle oben genannten Abwertungen und Löschungen sollen es der Klasse
ermöglichen sich mit der Elternklasse des Frameworks wieder zu
verknüpfen.

### Form

- Die Verzeichnisse libraries/joomla/form/fields und
  libraries/joomla/form/rules sind nicht mehr registriert, um
  Formularklassen zu finden, sondern alle Formularklassen sollten
  automatisch geladen werden.
- Zwei neue Eigenschaften wurden addfieldprefix hinzugefügt, das ein
  Namensraum-Präfix für Erweiterungen registriert (soll als Ersatz für
  addfieldpath verwendet werden). Ein Beispiel für die Verwendung siehe
  <a href="https://github.com/joomla/joomla-cms/pull/16419"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">diesen Github PR</a>.
- JForm::getControlGroup wurde entfernt und verwendet den Alias
  JForm::renderField (verfügbar seit Joomla 3.2.3).
- JForm::getControlGroups wurde entfernt und verwendet den Alias
  JForm::renderFieldset (verfügbar seit Joomla 3.2.3).
- Beim Rendern eines Feldes mit der Option hiddenLabel in JForm – sie
  blendet jetzt nur noch das Label in der Benutzeroberfläche aus – wird
  das html weiterhin mit der Klasse sr-only für die Barrierefreiheit des
  Bildschirm-Lesers gerendert.
- JFormFieldUsergroup wurde entfernt. Verwende stattdessen
  Joomla\CMS\Form\Field\UsergrouplistField (verfügbar seit Joomla 3.2).
- In der Formular-Klasse wurden die geschützten Methoden filterField()
  und validateField() entfernt. Dadurch werden alle benutzerdefinierten
  Formular-Klassen, die den Kern von Form erweitern und diese Methoden
  verwenden, ungültig. Dies wurde zugunsten der Filterung auf Feldebene
  ersetzt (siehe
  <a href="https://github.com/joomla/joomla-cms/pull/12414"
  class="external free" target="_blank"
  rel="nofollow noreferrer noopener">https://github.com/joomla/joomla-cms/pull/12414</a>
  für weitere Informationen).

#### Fields

- Die Filtereigenschaften von JFormFieldFilelist und
  JFormFieldFolderList wurden in `fileFilter` bzw. `folderFilter`
  umbenannt (um die Verwendung des regulären Joomla-Filterattributs bei
  zurückgegebenen Werten zu ermöglichen)
- JFormPredefinedlistField die Filtereigenschaften wurde umbenannt in
- JFormFieldEditor::save wurde ersatzlos entfernt.
- JFormFieldText::getSuggestions wurde entfernt zugunsten von
  JFormFieldText::getOptions

#### Media Field

Der Feldtyp „Medien“ schreibt nun die Bild-Metadaten in den internen
Wert. Hier ein Beispielwert:

images/banners/osmbanner1.png#joomlaImage://local-images/banners/osmbanner1.png?width=468&height=60

Um die endgültige Bild-URL oder den relativen Bilddateipfad zu erzeugen,
kann die neue Hilfsfunktion verwendet werden:

echo \Joomla\CMS\HTML\HTMLHelper::cleanImageURL(\$oldValue);

Zum Abrufen des reinen Wertes (ohne Adapterinformationen und Metadaten)
aus dem Wert, der im Medienformularfeld gespeichert ist:

echo
\Joomla\CMS\Helper\MediaHelper::getCleanMediaFieldValue(\$oldValue);

Die Funktion cleanImageURL bereinigt die Bild-URL nicht, sondern gibt
ein Objekt zurück, bei dem ein Teil des Objekts die bereinigte URL ist.
Die Verwendung von echo führt zu einem Fehler. Für weitere Informationen
zu diesem Thema, siehe <a
href="https://github.com/joomla/joomla-cms/issues/35871#issuecomment-968107241"
class="external autonumber" target="_blank"
rel="nofollow noreferrer noopener">[2]</a>

### Wrapper

- Die Formular-Wrapper-Klassen wurden entfernt. Bitte die ursprünglichen
  statischen Methoden beibehalten.

### HTTP

#### Veraltete Klassen und Interfaces

Die folgenden Klassen und Interfaces sind veraltet und wurden für die
Entfernung in Joomla! 5.0 geplant:

- JHttpResponse (verwende stattdessen Joomla\Http\Response)
- JHttpTransport (implementiere stattdessen
  Joomla\Http\TransportInterface)

### Klassenwechsel =

Das HTTP-Paket des Frameworks ist nun in Joomla! 4.0 und JHttp enthalten
und die Unterklassen JHttpTransport wurden überarbeitet, um das
Upstream-Paket zu verwenden.

##### JHttp

- JHttp wird nicht mehr mit einem cacerts.pem-Bundle im
  transports-Verzeichnis angeboten, stattdessen wird das
  composer/ca-Bundle verwendet, das mit dem Core ausgeliefert wird.

Der JHttp class constructor wurde mit den folgenden Änderungen
gelockert:

- Der Optionsparameter ist nicht mehr als
  Joomla\Registry\Registry-Objekt typisiert, ein Array oder ein
  beliebiges Objekt, das die
  Schnittstelle<a href="https://secure.php.net/manual/en/class.arrayaccess.php"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">ArrayAccess</a> implementiert, kann
  stattdessen verwendet werden.
- Der Transportparameter erlaubt nun jedes
  Joomla\Http\TransportInterface-Objekt.

##### JHttpTransport

Die nun veraltete JHttpTransport-Schnittstelle erweitert
Joomla\Http\TransportInterface jetzt und hat zu Rückwärtskompatibilität
geführt, die Änderungen in der Schnittstelle brechen. Der Konstruktor
ist nicht mehr Teil der Schnittstelle, und die \`Request()\`Methode der
Schnittstelle hat eine Signaturänderung erfahren. Insbesondere der
zweite Parameter, der zuvor die JUri-Klasse typisiert hat, typisiert nun
Joomla\Uri\Uri\UriInterface.

##### JHttpResponse

Beim Refactoring des Response-Objekts, das vom HTTP-Paket des Frameworks
übernommen werden soll, das nun die PSR-7 ResponseInterface-API
verwendet, wurde ein kleiner Kompatibilitätsbruch in der Struktur der
Response-Header vorgenommen. Ab 4.0 ist dies nun immer ein
multidimensionales Array, wobei der Schlüssel der Headername und der
Wert ein Array von Werten für diesen Header ist (früher war dies eine
Zeichenkette).

### Bilder

#### Veraltete Klassen und Interfaces

Die folgenden Klassen und Interfaces sind veraltet und wurden für die
Entfernung in Joomla! 5.0 geplant:

- JImageFilter (stattdessen Joomla\CMS\Image\ImageFilter verwenden)
- JImageFilterBackgroundfill (stattdessen
  Joomla\CMS\Image\Filter\Backgroundfill verwenden)
- JImageFilterBrightness (stattdessen Joomla\CMS\Image\Filter\Brightness
  verwenden)
- JImageFilterContrast (stattdessen Joomla\CMS\Image\Filter\Contrast
  verwenden)
- JImageFilterEdgedetect (stattdessen Joomla\CMS\Image\Filter\Edgedetect
  verwenden)
- JImageFilterEmboss (stattdessen Joomla\CMS\Image\Filter\Emboss
  verwenden)
- JImageFilterGrayscale (stattdessen Joomla\CMS\Image\Filter\Grayscale
  verwenden)
- JImageFilterNegate (stattdessen Joomla\CMS\Image\Filter\Negate
  verwenden)
- JImageFilterSketchy (stattdessen Joomla\CMS\Image\Filter\Sketchy
  verwenden)
- JImageFilterSmooth (stattdessen Joomla\CMS\Image\Filter\Smooth
  verwenden)

#### Klassenwechsel

Die Klassen aus dem Image-Paket des Frameworks wurden in das CMS und
JImage integriert und die JImageFilter-Unterklassen wurden so
umstrukturiert, dass sie nun verwendet werden können. D.h. alle Klassen
unter dem Namespace Joomla\Image wurden in den Namespace
Joomla\CMS\Image verschoben.

### Menü

- JMenu::\$\_items, JMenu::\$\_default und JMenu::\$\_active wurden
  entfernt (Bitte beachten, dass diese Eigenschaften geschützt waren,
  sodass dies nur benutzerdefinierte Unterklassen von JMenu betrifft).

### Neuer MVC-Layer

- Dies wurde in Joomla 4 entfernt. Wir haben entschieden, dass dieser
  Versuch nicht erfolgreich war und haben daher die Entwicklungsarbeit
  an dem ursprünglichen MVC-Layer fortgesetzt (siehe den Abschnitt
  "Legacy MVC").
  <a href="https://github.com/joomla-extensions/legacy-mvc"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Auf GitHub</a> gibt es ein Plugin,
  das mit eigenen Erweiterungen ausgeliefert werden kann. Während dessen
  kann man zurück auf das Legacy MVC migrieren (bitte beachten, dass
  dies nicht standardmäßig mit Joomla 4 ausgeliefert wird).

### Keychain

Das Entfernen der Keychain in 4.0 hat das Entfernen der folgenden Klasse
zur Folge:

- JKeychain

### Pathway

- Bei JPathway::\$\_pathway und JPathway::\$\_count wurde das
  Unterstrich-Präfix entfernt (bitte beachten, dass diese Eigenschaften
  geschützt waren, sodass dies nur benutzerdefinierte Unterklassen von
  JPathway betrifft)
- JPathway::\_makeItem wurde zugunsten von JPathway::makeItem entfernt
  (bitte beachten, dass diese Methode geschützt war, sodass dies nur
  benutzerdefinierte Unterklassen von JPathway betrifft).

### Profiler

- JProfiler::getmicrotime und JProfiler::getMemory wurden zugunsten der
  nativen PHP-Methoden entfernt, die sie enthalten haben (`microtime(1)`
  bzw. `memory_get_usage()`)

### Table

- JTable::\_\_construct Datenbankobjekt ist nun typisiert, um ein
  JDatabaseDriver zu sein.
  - Unterklassen von JTable müssen sicherstellen, dass sie ein
    JDatabaseDriver-Objekt an den übergeordneten Konstruktor übergeben.
  - Unterklassen von JTable müssen die Methodensignatur von setDbo()
    ändern, wenn sie eine erweiterte Version dieser Methode haben, um
    den typehint aufzunehmen.
- Es gibt eine neue Methode JTable::hasField - alle Instanzen von
  property_exists auf JTable-Instanzen verwenden nun diese
  Proxy-Methode, um eine bessere Interoperabilität von Tabelleninstanzen
  zu ermöglichen.
- Das JTableObserver-Muster (und die entsprechenden Klassen) wurden aus
  JTable entfernt. JTable löst nun Ereignisse und Tags aus, die
  Inhaltshistorie (und alle anderen benutzerdefinierten Anwendungen
  dieses Musters) sollten zu Standard-Plugins wechseln.

### Mail

Die folgenden Methoden wurden in Joomla! 4.0 entfernt:

- JMail::sendAdminMail wurde entfernt.

#### Exceptions

JMail fängt keine Exceptions mehr von PHPMailer ab. Es liegt nun in der
Verantwortung des Objekts, das JMail aufruft, diese Ausnahmen
entsprechend zu behandeln. Wenn der Mailversand in der globalen
Konfiguration deaktiviert ist, wird der Aufruf von
`\Joomla\CMS\Mail\Mail::send()` eine
`\Joomla\CMS\Mail\Exception\MailDisabledException` auslösen.

### Sprache

- Die Funktionen setTransliterator, setPluralSuffixesCallback,
  setIgnoredSearchWordsCallback, setLowerLimitSearchWordCallback,
  setUpperLimitSearchWordCallback und
  setSearchDisplayedCharactersNumberCallback sind nun typisiert, um ein
  Callable zu benötigen.
- Der `"_QQ_"` Platzhalter für doppelte Anführungszeichen wurde entfernt
  (dies existierte nur, um einen alten PHP-Bug zu umgehen, der behoben
  wurde). Escape doppelte Anführungszeichen bei Bedarf (z.B. `\"`)
- Das Format für die Sprachdateinamen wurde geändert, um die Arbeit in
  Übersetzungstools von Drittanbietern (wie Crowdin) zu erleichtern.
  INI-Sprachdateien müssen nicht mehr den Sprachcode enthalten (d.h.
  en-GB.com_contact.ini =\> com_contact.ini). Im Spezial-Fall von
  en-GB.ini wurde die Datei im Core-Sprachpaket in joomla.ini und
  en-GB.xml in langmetadata.xml umbenannt. Es gibt einen b/c Layer, der
  weiterhin die alten Joomla 3-Dateinamen in Joomla 4 erkennen wird.
- \Joomla\CMS\Language\Multilanguage::getSiteLangs wurde entfernt.
  Stattdessen bitte
  \Joomla\CMS\Language\LanguageHelper::getInstalledLanguages(0)
  benutzen.
- JLanguage::exists wurde entfernt. Stattdessen bitte
  Joomla\CMS\Language\LanguageHelper::exists benutzen.
- Die Wrapper-Klassen JTextWrapper, LanguageHelperWrapper und
  TransliterateWrapper wurden entfernt. Die darin enthaltenen statischen
  Methoden können weiterhin verwendet werden.
- Die Behandlung von pdf_fonts und die Unterstützung für Sprachpakete
  (`language/pdf_fonts`) wurde aus dem Sprachinstaller entfernt
  (<a href="https://github.com/joomla/joomla-cms/pull/31288"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">siehe GitHub PR #31288</a>).

### Legacy MVC Layer

#### Legacy Controller

- JControllerLegacy wurde aus der Legacy-Schicht entfernt, und wir
  beabsichtigen nicht, es oder seine Unterklassen in naher Zukunft zu
  entfernen.
- JControllerLegacy erweitert JObject nicht mehr. Controller sollten
  keine der in der Klasse JObject enthaltenen Methoden aufrufen.
- JControllerLegacy implementiert eine Schnittstelle für mehrere
  Task-Controller.
- JControllerLegacy::\_construct nimmt nun zusätzliche Argumente an.
  Wenn Sie zuvor ein Controller-Objekt über
  JControllerLegacy::getInstance erhalten haben, müssen Sie Ihren Code
  nicht ändern.
  - Parameter 2: Eine optionale MVCFactoryInterface-Instanz.
  - Parameter 3: Eine optionale CMSApplicationInterface-Instanz.
  - Parameter 4: Eine optionale Input-Instanz
  - Parameter 5: Eine optionale FormFactoryInterface-Instanz.
- JControllerForm verwendet nun das StringInflector-Paket, um die
  Listenansicht zu bestimmen. Dies sollte die Möglichkeit verbessern,
  die Listenansicht von mehr Ansichtsnamen zu erraten. Wenn
  Extension-Entwickler feststellen, dass ihre Listenansicht nicht mehr
  gefunden wird, sollte man die Klasseneigenschaft *view_list* manuell
  in seinem Controller setzen.

#### Legacy View

- JViewLegacy wurde aus der Legacy-Schicht entfernt, und wir
  beabsichtigen nicht mehr, es oder seine Unterklassen in naher Zukunft
  zu entfernen.
- JViewHtml wurde in zwei Klassen unterteilt - AbstractView und
  HtmlView. Die abstrakte Sicht enthält die Logik für den Zugriff auf
  Modelle und die Ermittlung des Namens der Sicht und ist als
  Basisklasse für Nicht-Html-Sichten gedacht. Die Html-Sicht enthält die
  gleiche Logik wie bisher.
- Es gibt jetzt zwei Unterklassen von JViewHtml -
  \Joomla\CMS\MVC\View\ListView und \Joomla\CMS\MVC\View\FormView, die
  entwickelt wurden, um die Entwicklung von Listen- und
  Formularansichten zu beschleunigen und die Code-Duplizierung zu
  reduzieren.

### Library

- JLibraryHelper::\_load wurde entfernt. Bitte stattdessen
  \Joomla\CMS\Helper\LibraryHelper::loadLibrary benutzen.

### Session

Das Session-Paket wurde grundlegend überarbeitet, um das Session-Paket
des Frameworks zu nutzen. Diese Änderung betrifft in erster Linie die
Interna des Pakets. Änderungen an der primären öffentlichen API über die
JSession-Klasse sind minimal.

### String

Der alte Alias der JString-Klasse wurde entfernt. Bitte stattdessen
\Joomla\String\StringHelper benutzen.

#### Entfernte Klassen und Interfaces

Die folgenden Klassen und Interfaces wurden in Joomla! 4.0 entfernt:

- JSessionExceptionUnsupported
- JSessionHandlerInterface
- JSessionHandlerJoomla
- JSessionHandlerNative
- JSessionStorage
- JSessionStorageApc
- JSessionStorageDatabase
- JSessionStorageMemcache
- JSessionStorageMemcached
- JSessionStorageNone
- JSessionStorageWincache
- JSessionStorageXcache

#### JSession

JSession erweitert jetzt die Klasse Joomla\Session\Session des
Frameworks. Viele der Methoden haben eine geänderte Signatur, außerdem
existiert eine Kompatibilitätsschicht, die beim Umstieg hilft.

##### Veraltete Namensraum-Parameter

Die Methoden *get*, *set*, *has* und *clear* unterstützten bisher einen
Namensraum-Parameter. Dieser Parameter ist jetzt veraltet. Der
Namensraum sollte dem Namen vorangestellt werden, bevor diese Methoden
aufgerufen werden.

##### JSession::clear() überarbeitet

In der Klasse Joomla\Session\Session wird die Methode *clear* verwendet,
um alle Daten aus dem Sitzungsspeicher zu löschen. In JSession wird
diese Methode verwendet, um einen einzelnen Schlüssel zu entfernen. Wenn
diese Methode mit Parametern aufgerufen wird, wird sie die neue Methode
*Joomla\Session\Session::remove()* aufrufen.

##### JSession::getInstance() veraltet

Die einzelne Methode *getInstance()* ist veraltet. Das Sitzungsobjekt
sollte stattdessen von der aktiven Anwendung oder dem Dependency
Injection Container abgerufen werden.

##### Sitzungs-Handler

In Joomla! 3.x und früher wurden Sitzungs-Handler durch die Klasse
JSessionStorage und ihre Unterklassen repräsentiert. In Joomla! 4.0 sind
SSitzungs-Handler nun Implementierungen von
Joomla\Session\HandlerInterface (das eine Erweiterung von PHP's <a
href="https://secure.php.net/manual/en/class.sessionhandlerinterface.php"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">SessionHandlerInterface</a> ist. Alle
Handler, die in Joomla! 3.x unterstützt wurden, sind in 4.0 weiterhin
verfügbar, zusätzlich zu zwei weiteren Handlern: ein Handler, der die
APCu-Erweiterung nativ implementiert und ein Handler, der Redis
unterstützt.

### Social-Media Bibliotheken

Die Pakete facebook, github, google, linkedin, openstreetmap, mediawiki
und twitter wurden alle aus dem CMS entfernt.

### User

- JUser::getParameters wurde entfernt. Es lassen sich nicht mehr alle
  Parameter für einen Benutzer abrufen, stattdessen können mit
  JUser::getParam gezielt einzelne Parameter abgerufen werden.

#### Helper

- JUserHelper::getCryptedPassword wurde entfernt. Joomla 4 unterstützt
  nur Hashing mit der nativen PHP-Funktion password_hash (über
  JUserHelper::hashPassword (verfügbar seit Joomla 3.2.1))
- JUserHelper::getSalt wurde ersatzlos entfernt (dadurch wurde der Hash
  von JUserHelper::getCryptedPassword erstellt, der nun ebenfalls
  entfernt wurde).
- JUserHelper::invalidateCookie, JUserHelper::clearExpiredTokens und
  JUserHelper::getRememberCookieData wurden ersatzlos entfernt. Sie
  wurden seit Joomla 3.2 im Kern nicht mehr verwendet, da ihre Logik in
  das Cookie-Authentifizierungs-Plugin verschoben wurde.
- JUserWrapperHelper wurde entfernt. Die statischen Methoden in
  JUserHelper können weiter verwendet werden.

### Ersatzlos entfernte Klassen

- JNode
- JTree
- JGrid
- JError (native Ausnahmen verwenden, falls eine Fehlerbehandlung
  erforderlich ist)

#### Hilfsprogramme

##### Entfernte Klassen und Interfaces

Die folgenden Klassen und Interfaces wurden in Joomla! 4.0 entfernt:

- JArrayHelper

stattdessen Joomla\Utilities\ArrayHelper; verwenden.

## Externe Libraries

Die folgenden Änderungen wurden an den externen Bibliotheken
vorgenommen, die Joomla! verpackt und versendet.

### PHPMailer

Joomla! 4.0 wird mit PHPMailer 6 ausgeliefert. Bitte das
<a href="https://github.com/PHPMailer/PHPMailer" class="external text"
target="_blank" rel="nofollow noreferrer noopener">GitHub Repository</a>
für relevante Änderungen überprüfen.

### PHPUTF8

Bei Joomla! 3.4 befand sich die PHPUTF8-Bibliothek an zwei Stellen im
Joomla! Paket; \`libraries/phputf8\` und
\`libraries/vendor/joomla/string/src/phputf8\`. In Joomla! 4.0 ist die
Kopie der Bibliothek in \`libraries/phputf8\` entfernt worden. Die
Klasse Joomla\String\StringHelper stellt viele Funktionen der Bibliothek
zur Verfügung und die Autoloader-Definition des Composers importiert
ebenfalls einen Großteil der Bibliothek. Wenn jedoch eine Funktion
benötigt wird, die nicht bereits enthalten ist, sollten die
erforderlichen Funktionen aus dem Pfad
\`libraries/vendor/joomla/string/src/phputf8\` importiert werden.

### SimplePie

Die SimplePie-Bibliothek ist nicht mehr in Joomla! 4.0 enthalten.

### jQuery

Joomla! 4.0 wird mit jQuery 3 ausgeliefert. Bitte
<a href="https://jquery.com/upgrade-guide/3.0/" class="external text"
target="_blank" rel="nofollow noreferrer noopener">den
Upgrade-Leitfaden</a> für relevante Änderungen lesen. Bitte beachten,
dass auch jQuery Migrate nicht mehr enthalten ist. Wir empfehlen, es
lokal zu verwenden, um bei Problemen mit deinem Code zu helfen.

### jQuery UI

jQuery UI wurde aus Joomla 4 entfernt. Es wurde zwar nicht offiziell für
tot erklärt, aber es gab seit 2016 keine neue Version von jQuery UI
mehr.

### Bootstrap

Joomla! 4.0 wird mit Bootstrap 5 ausgeliefert. Bootstrap 2.3.2 wurde
entfernt, aber wir haben einige BS2-Klassen beibehalten, um die
Migration zu erleichtern (z.B. Das alte unsichtbare BS2-Element
existiert noch für Bildschirmlesegeräte)

### FOF

FOF 2.x wurde entfernt.

## Templates

Alle Joomla! 3 Templates - ISIS und Hathor im Backend, sowie Protostar
und Beez im Frontend werden nicht mehr unterstützt. Das neue 4.0
Backend-Template heißt Atum und das Frontend-Template Cassiopeia.

Als Konsequenz müssen alle Erweiterungen auf den neuen Bootstrap 5 Stil
migriert werden, und somit die aktuelle Bootstrap 2.3.2 Implementierung
ersetzen. Weitere Informationen zu Bootstrap findet man auf der <a
href="https://getbootstrap.com/docs/5.0/getting-started/introduction/"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Bootstrap 5</a> Website und auf der
<a href="https://getbootstrap.com/2.3.2/" class="external text"
target="_blank" rel="nofollow noreferrer noopener">Bootstrap 2.3.2</a>
Website.

- Joomla 4 wird das Template-Favicon direkt laden und nicht das Favicon
  im Joomla-Stammverzeichnis, um dem Konzept gerecht zu werden, dass das
  Template die einzige Quelle der Wahrheit ist.
- Frontend-Komponenten und Modulansichten verwenden jetzt das
  Klassen-Markup „Block Element Modifier“ (BEM), um die Unterstützung
  von Templates für andere Frameworks als Bootstrap zu erleichtern. Auf
  der <a href="http://getbem.com/" class="external text" target="_blank"
  rel="nofollow noreferrer noopener">BEM-Website</a> findet man weitere
  Informationen, wie ähnliche Klassen erstellt werden können.

Es gibt auch Änderungen an den Optionen der Kernkomponenten, die
beachtet werden sollten, wenn das Tempalte gleichzeitig 3.x und 4.x
unterstützen soll: <a
href="https://docs.joomla.org/J4.x:Changed_parameters_for_template_providers"
class="external free" target="_blank"
rel="noreferrer noopener">https://docs.joomla.org/J4.x:Changed_parameters_for_template_providers</a>.

## Sonstiges

- Die globale Variable *\$\_PROFILER* wurde entfernt. Bitte stattdessen
  */Joomla/CMS/Profiler/Profiler::getInstance* verwenden.

### Medien in Bibliotheken

Im Bibliotheksstammordner des CMS sind keine Medien erlaubt. Alle mit
Joomla-Bibliotheken verbundenen Assets sollten gemäß den besten
Beispielen in den Medienordner gelegt werden. Der direkte Zugriff wird
mit einer *.htaccess* bzw. *web.config* Datei im Stammverzeichnis des
Bibliotheksverzeichnisses geblockt.

### Bin

Das Entfernen des Schlüsselbundes in 4.0 hat dazu geführt, dass das
gesamte Bin-Verzeichnis entfernt wurde, da es nur den Schlüsselbund
enthielt.

### Komponenten

- Alle Komponenten wurden im Namensraum angeordnet und die Verzeichnisse
  entsprechend überarbeitet. Für weitere Informationen dazu lese das
  Tutorial zum Erstellen einer Komponente in Joomla 4.
- Die Profilansicht com_admin wurde entfernt (Dies scheint, historisch
  bedingt, durch Probleme beim Zugriff auf com_users erstellt worden zu
  sein. Dies ist nicht mehr der Fall, sodass alle Benutzerbearbeitungen
  über com_users edit user view im Backend laufen).
- com_actionlogs PHP 5.5 Backfill-Code wurde entfernt und entsprechend
  `ActionlogsHelper::getCsvData()` ist nun vom Typ angedeutet, dass er
  ein `Generator` Objekt liefert.
- Die CSV-Export-Headers von com_actionlogs wurden geändert, damit sie
  mit den in der Benutzeroberfläche angezeigten Zeichenfolgen
  übereinstimmen.
- Bei den Kernel-Komponenten wurde der URL-Routing-Modus 'Legacy' aus
  Joomla 3.7 entfernt. Sie sollten entweder Ihre .htaccess-Datei oder
  die Redirect-Komponente verwenden, um alle internen URLs, die sich
  ändern, zu reparieren. Sie können den 'Modern'-Modus in Joomla 3
  ausprobieren, indem Sie den Anweisungen
  hier
  folgen.
- Die MailTo-Komponente wurde ersatzlos entfernt. Wenn diese
  Funktionalität verwendet wurde, sollte eine alternative Komponente auf
  JED zu finden sein.
- In der Frontend-Kontaktansicht von com_contact wurde die Eigenschaft
  „contact“ entfernt, da sie ein Duplikat der Eigenschaft „item“ war.
  Wir haben uns entschieden, \$this-\>item beizubehalten, da es mit dem
  in den Ansichten in „Beitrag“ und „Schlagwort“ konsistent ist.
  Template-Overrides müssen aktualisiert werden, um dies wiederzugeben.
- Das wiederholbare Feld in com_fields wurde zugunsten des neuen Feldes
  im Unterformular entfernt. Daten aus wiederholbaren Feldern werden
  automatisch in das neue Unterformularfeld migriert, aber in einem
  anderen Format gespeichert.
- Die xreference-Felder wurden aus *\#\_\_contact_details*,
  *\#\_\_content* und *\#\_\_newsfeeds* entfernt, da sie nicht benutzt
  wurden.

### Plugins

- Das Plugin zur Google Mail-Authentifizierung (Gmail) wurde entfernt.
  Für weitere Informationen bitte <a
  href="https://developer.joomla.org/news/724-removal-of-the-gmail-authentication-plugin-as-of-joomla-4-0.html"
  class="external text" target="_blank" rel="noreferrer noopener">diesen
  Blogbeitrag</a> lesen.
- Die Google reCAPTCHA v1-Unterstützung wurde vollständig aus dem
  CAPTCHA-Plugin entfernt. Dies funktionierte seit Q2 2018 nicht mehr.
  Google hat die Unterstützung dafür eingestellt.
- Das reCAPTCHA-Plugin verwendet jetzt die offizielle PHP-Bibliothek von
  Google für CAPTCHA
- Bei Plugins, welche die 3.x-Kompatibilitätsschicht verwenden, ist der
  Name *result* eine geschützte Eigenschaft, sowohl für Eingabeparameter
  als auch für Rückgabewerte. Informationen zum neuen empfohlenen Ansatz
  für Plugins findet man unter  Ein Plugin für Joomla!
  erstellen
- Bei Plugins, welche die 3.x-Kompatibilitätsschicht verwenden, muss für
  alle Typ-Hinweise zu Events, die eine Klasse erfordern, **muss** diese
  Klasse automatisch geladen werden, bevor für das Plugin eine Instanz
  erstellt wird.
- Das Event „onContentBeforeSave“ benötigt jetzt den Parameter *data*.
  Dieser wurde in \Joomla\CMS\MVC\Model\LegacyModel seit 3.7 übergeben,
  wird aber nun konsistent von den Kern-Erweiterungen übergeben und vom
  Joomla-Kern Inhalts-Plugin verwendet.
- Der Rücksprung vor dem Aufruf von `parent::__construct()` im
  Konstruktor eines Plugins wird nicht mehr unterstützt, um das Plugin
  nicht in die Warteschlange des Event-Dispatchers zu stellen.
- *onUserBeforeDataValidation* Event ist veraltet zugunsten von
  *onContentBeforeValidateData* (Das Event war von allen Inhaltstypen
  nutzbar und nicht benutzerspezifisch. Bitte beachten, dass beide
  Events während der Laufzeit von Joomla 4 aufgerufen werden. Der Code
  sollte auf das neue Event migriert werden, wenn Joomla 3 nicht mehr
  unterstützt werden muss.

### Plugin-Events

- In Joomla 4 funktionieren Events, deren Name nicht mit „on“ beginnt,
  nicht mehr. Sie produzieren nicht einmal einen Fehler, so dass es sehr
  schwer ist, herauszufinden, warum sie nicht funktionieren. Das
  bedeutet, dass sowohl die Namen von Funktionen in Plugins als auch die
  Namen der Aufrufe überschrieben werden müssen. Für weitere
  Informationen bitte
  <a href="https://github.com/joomla/joomla-cms/issues/36062"
  class="external autonumber" target="_blank"
  rel="nofollow noreferrer noopener">[3]</a> lesen.

### Administrator-Hilfen

- JAdministratorHelper wurde ersatzlos entfernt (Es wurde in
  JApplicationAdministrator integriert).
- JSubMenuHelper wurde ersatzlos entfernt (Bitte stattdessen die
  JHtmlSidebar verwenden – verfügbar seit 3.0).
- JToolbarHelper wurde in das Hauptbibliotheksverzeichnis verschoben.

### Module

- Das Administrator-Modul *submenu* wurde entfernt.
- Die Logik von *Module Chromes* (Modulstile) in Template-Dateien
  `html/modules.php` wurde in die `JLayout`-Dateien verschoben.
  `modChrome_x`-Funktionen in `modules.php` werden nicht mehr
  unterstützt. Siehe
  <a href="https://github.com/joomla/joomla-cms/pull/23570"
  class="external free" target="_blank"
  rel="nofollow noreferrer noopener">https://github.com/joomla/joomla-cms/pull/23570</a>
  für Details.
- Die *Modul Chromes* (Modulstile) `modChrome_horz`, `modChrome_xhtml`,
  `modChrome_rounded` wurden aus Template `system` ersatzlos entfernt.
- Die Modulklassensuffixe wurden umbenannt und vereinheitlicht. Diese
  heißen jetzt „Module Class“ und werden an die Liste der Klassen im
  Module Chrome angehängt. (Sie werden nicht mehr in der Modulausgabe
  selbst gerendert.)

### Fehlerbehandlung

- Joomla wird nun die PHP-Fehler E_USER_DEPRECATED behandeln und an JLog
  übergeben - dies ist nützlich für die Behandlung von Verwerfungen in
  vielen PHP-Bibliotheken von Drittanbietern (beachte, dass es das Laden
  der Seite blockiert, wenn der Debug-Modus aktiviert ist).
- Joomla\CMS\Exception\Exception\ExceptionHandler arbeitet jetzt nur
  noch mit Ausnahmen, die in JApplication::execute ausgegeben werden.
  Wir verwenden nun den ErrorHandler von Symfony, wenn dies fehlschlägt
  oder Ausnahmen außerhalb davon ausgegeben werden. Wir erwarten, dass
  dies für die meisten Benutzer minimale Auswirkungen hat und in vielen
  Fällen eine hilfreichere Meldung geben sollte als der traditionelle
  Fehler "Fehler beim Anzeigen der Fehlerseite" für Benutzer, wenn die
  Dinge sehr schlecht laufen.
- Joomla\CMS\Exception\Exception\ExceptionHandler ist jetzt
  formatbewusst und wird Fehler in html, json, xml, feed oder
  client-bewussten Formaten anzeigen.
- Die Joomla\CMS\Exception\ExceptionHandler::render() Signatur wurde
  geändert, um den Throwable Typ-Hinweis aufzunehmen. Vor 3.5, als PHP
  7-Unterstützung hinzugefügt wurde, wurde dies als Exception typisiert,
  und seit 3.5 wurde im Code selbst typgeprüft.

### Base Tag

Frühere Joomla-Versionen setzten ein Header-Tag der aktuellen URL im
Frontend. Dies wurde entfernt, da es keinen eindeutigen Zweck erfüllte.

### JavaScript

Die Datei *caption.js* wurde aus Joomla entfernt. Bitte die nativen
HTML-Elemente *figure* und *figcaption* verwenden. (In
*layouts/joomla/content/intro_image.php* kann JLayout als Beispiel
betrachtet werden).

saveOrderAjax übermittelt nicht die kompletten Formulardaten (wie in
Joomla 3), sondern nur die cid und die Bestellvariable. Dies kann
unzureichend sein, da einige Erweiterungen mehr Daten für die richtige
Sortierung benötigen - siehe:
<a href="https://github.com/joomla/joomla-cms/issues/36346"
class="external free" target="_blank"
rel="nofollow noreferrer noopener">https://github.com/joomla/joomla-cms/issues/36346</a>

### Namespacing

Die Verwendung von Klassen wie *\$msg = JText::\_( 'Hello man!' );* kann
nun das Namespacing verwenden. Daraus würde dann *\$msg = Text::\_(
'Hello man!' );* werden. Um Namensräume zu verwenden, müssen die
richtigen Namensraum-Deklarationen hinzugefügt werden. Diese sollte nach
dem *defined('\_JEXEC') or die;* hinzugefügt werden.

Um den richtigen Namensraum herauszufinden, kann man entweder der
Anleitung hier folgen: <a
href="https://groups.google.com/forum/#!topic/joomla-dev-general/1ua9zIqlcVc"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">SO confused about namespace &amp;
enquemessage...</a> oder die generierte pdf-Referenzdatei verwenden: <a
href="https://docs.joomla.org/images/9/9c/J%21_namespace_reference.pdf"
class="external text" target="_blank"
rel="noreferrer noopener">namespace reference.pdf</a>

#### Namensraum-Zuordnung und Name der Manifestdatei

Die automatische Namespace-Zuordnung funktioniert nicht mit
Manifestdateien für Erweiterungen mit dem Namen `manifest.xml`. Siehe:
<a href="https://github.com/joomla/joomla-cms/issues/37750"
class="external free" target="_blank"
rel="nofollow noreferrer noopener">https://github.com/joomla/joomla-cms/issues/37750</a>
