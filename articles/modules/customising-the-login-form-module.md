<!-- Filename: Customising_the_Login_Form_module / Display title: Das Modul "Anmeldeformular" anpassen -->

## Beschreibung

<img
src="https://docs.joomla.org/images/2/29/Login_module_example-de.png"
class="thumbimage" decoding="async" data-file-width="220"
data-file-height="280" width="220" height="280"
alt="Login module example-de.png" />

Das Modul zeigt Besuchern ein Formular mit Eingabefeldern für
Benutzernamen und Passwort. Nach Eingabe einer gültigen Kombination in
beiden Feldern erhalten Besucher Zugang zu weiteren Ressourcen der
Website. Welche Ressourcen das sind wird seperat eingestellt. Weitere
Informationen unter
<a href="https://forum.joomla.org/viewtopic.php?t=376371"
class="external text" target="_blank" rel="noreferrer noopener">Forum:
restricting user access to resources</a>.

Nach erfolgreicher Anmeldung zeigt das Modul einen "Abmelden"-Button.
Benutzer werden nach einer einstellbaren Zeit der Inaktivität
automatisch abgemeldet.

Um für Besucher sichtbar zu sein, muß das Modul veröffentlicht und einer
oder mehreren Seiten der Joomla!-Site zugewiesen sein.

Das Modul wird in der gewählten Position des aktuellen Templates
angezeigt. Man kann das Modul auch im Hauptinhalt anzeigen lassen,
nachdem ein Menüelement angeklickt wurde. Weitere Informationen unter Creating a Login Form menu
item.

## Einstellungen anpassen

Man kann angezeigte Informationen und einige Verhaltensweisen des
Anmeldeformulars anpassen. Das Vorgehen hierzu:

1.  Im Administrator-Backend anmelden. Weitere Informationen unter: [An-
    oder Abmelden im
    Administrator-Backend](https://docs.joomla.org/Logging_in_or_out_of_the_Administrator_back-end "Special:MyLanguage/Logging in or out of the Administrator back-end").
2.  Auf den **Erweiterungen **→** Module**-Menüeintrag klicken.
3.  Aus der Liste den Modultyp "Anmeldeformular" wählen. Es kann
    passieren, dass man in der Liste durch mehrere Seiten blättern muß.
    Einfacher ist es, sich die "Suchwerkzeuge" anzeigen zu lassen
    (Button "Suchwerkzeuge" ) und aus dem Dropdown *- Modultyp wählen -*
    den Eintrag "Benutzer - Anmeldung" zu wählen (man kann sich an der
    alphabetischen Sortierung orientieren oder auch das Suchfeld des
    Dropdowns verwenden.)
4.  Modulnamen anklicken, z.B. **Benutzer-Anmeldung**.
5.  "Module: \[Bearbeiten\]" wird mit vier Tabs angezeigt: Modul,
    Menüzuweisung, Erweitert und Modulberechtigungen.
6.  Gewünschte Anpassungen durchführen.
7.  Um die Änderungen zu speichern, auf den **Speichern**- oder
    **Speichern & Schließen**-Button der Werkzeugleiste klicken.
    - Der **Speichern**-Button der Werkzeugleiste speichert die
      Änderungen, man bleibt aber im Bearbeitungs-Formular.
    - Der **Speichern & Schließen**-Button der Werkzeugleiste speichert
      Änderungen und führt zurück zur Modul-Liste.
8.  Die Nachricht "Das Modul wurde gespeichert" in grüner Farbe wird
    angezeigt, um die Sicherung der Anpassungen zu bestätigen.

## Veröffentlichen

<img
src="https://docs.joomla.org/images/thumb/b/b5/Login_module_j39.png/300px-Login_module_j39.png"
class="thumbimage" decoding="async"
srcset="https://docs.joomla.org/images/thumb/b/b5/Login_module_j39.png/450px-Login_module_j39.png 1.5x, https://docs.joomla.org/images/thumb/b/b5/Login_module_j39.png/600px-Login_module_j39.png 2x"
data-file-width="900" data-file-height="520" width="300" height="173" />
<a href="https://docs.joomla.org/File:Login_module_j39.png"
class="internal" title="Enlarge"></a>Login Module in Module Manager

Sollen sich bestimmte (authorisierte) Besucher der Website anmelden
können, um zusätzliche Ressourcen zu sehen, muß das "Anmeldung"-Modul
veröffentlicht werden. Dafür gibt es zwei Möglichkeiten:

1.  den Status in der Module-Liste auf **Veröffentlicht** (grüner Haken)
    setzen oder
1.  den Namen des Moduls in der Module-Liste anklicken, im
    Bearbeitungs-Formular den Status auf **Veröffentlicht** ändern und
    *Speichern*.

Weitere Informationen unter  Modul "Anmeldung"
anpassen

### Siehe auch

Regeln für die Registrierung von Benutzern

;

-  Logging in or out of the Administrator
  back-end
-  Setting user registration
  policy

## Menüzuweisung

You can make the Login Form module appear on one or more pages by
assigning it to selected Menu Items. This is done using the fields in
the Menu Assignment group on the Module Edit screen. To learn how to do
this see  Changing the Login Form module
settings.
The following list describes the settings in the Menu Assignment group.

- **Menus**: Is a radio button field with the following options:
  - **All**: The Login Form module will appear on all screens.
  - **None**: The Login Form module will not appear on any screens.
  - **Select Menu Item(s) from the List**: The Login Form module will
    appear on those screens selected in the **Menu Selection** field.
- **Menu Selection**: Shows a list of all the Menus and Menu Items from
  which one or more may be selected. This field is only used if the
  **Menus** field is set to **Select Menu Item(s) from the List**. To
  select more than one Menu Item on the list, you *Shift-click* to
  select a range of items, or *Control-click* to select or deselect
  individual items.

## Einstellungen

If you wish to customise the information in the Login Module you will
need to [navigate to the login module edit page in the Administration
section of
Joomla](https://docs.joomla.org/Changing_the_Login_Form_module_settings "Changing the Login Form module settings").
Then consult  the help screen
page
