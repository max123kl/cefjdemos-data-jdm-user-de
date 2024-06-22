<!-- Filename: Auto_redirect_guests_to_login / Display title: Gäste automatisch zum Login umleiten -->

Added for testing

### Gewünschte Funktionalität

Angenommen, Sie haben einige Menüoptionen, bei denen ein Benutzer angemeldet sein muss,
wie "Artikel einreichen". Sie möchten, dass alle Benutzer die sehen können
eingeschränkten Menüpunkt, unabhängig davon, ob sie angemeldet sind oder nicht.

Wenn der Benutzer angemeldet ist, geht er einfach direkt zum eingeschränkten Menü
Artikel.

Wenn der Benutzer nicht angemeldet ist

- Ihnen wird das Anmeldeformular angezeigt, und
- Sobald sie sich erfolgreich angemeldet haben, fahren sie mit dem eingeschränkten fort
   Buchseite.

Wenn sie nicht registriert sind, haben sie die Möglichkeit, sich zu registrieren oder zu navigieren
zu einer anderen Seite.

### Lösung

So machen Sie das in Joomla!.

1. Erstellen Sie ein neues Menü aus dem Menümanager, sagen Sie, es heißt "verstecktes Menü".
2. Fügen Sie Menüelemente hinzu, auf die nur registrierte Benutzer zugreifen können
     (z. B. „Artikel einreichen“). Legen Sie die erforderlichen Zugriffsebenen fest
     dieser Menüpunkte auf "Registriert".
3. Erstellen Sie KEIN Modul für das „versteckte Menü“. Es wird nicht sein
     auf jeder Seite angezeigt werden, sodass kein Modul erforderlich ist.
4. Erstellen Sie Ihr „echtes“ Menü (zB „Hauptmenü“) und den Menüpunkt
     der für alle Benutzer angezeigt wird (z. B. „Artikel einreichen“).
     - Der Menüeintrag hat den Menüeintragstyp "Alias".
     - Der Parameter „Menüpunkt“ wird das Menü „Artikel einreichen“ sein
       Eintrag im "versteckten Menü".
     - Die Zugriffsebene für diesen Menüpunkt ist "Öffentlich", da wir
       Jeder soll es sehen und nutzen können.
5. Erstellen Sie für dieses Menü ein Modul vom Typ "mod_mainmenu", genau wie Sie
     tun für jedes Menü.
6. Wenn Sie Untermenüs wünschen, vergewissern Sie sich, dass Sie die Untermenüelemente hinzugefügt haben
     das "Hauptmenü" und nicht das "versteckte Menü".

Wenn nun ein Gast (nicht eingeloggter Benutzer) auf „Artikel einreichen“ zugreift
Menüauswahl, es leitet sie auf die Anmeldeseite um. Wenn sie sich anmelden
erfolgreich, gelangen sie auf die gewünschte Seite (in diesem Fall „Submit
ein Artikel"). Wenn sie bereits eingeloggt waren, gelangen sie direkt dorthin.

### Beispiel

In meinem Fall habe ich die folgenden Menüpunkte hinzugefügt:

1. ZUHAUSE
2. BLOG (IDOBlog)
3. WIKI (ein Wiki)
4. VERZEICHNIS (SOBI2)
5. KLEINANZEIGEN (Anzeigen)
6. FAQS (Bereich Artikel)
7. LADEN (VirtueMart)
8. Kontaktieren Sie uns (Kontakte)

Ich wollte, dass ALLE Menüpunkte öffentlich sichtbar sind (nicht registrierte
Benutzer eingeschlossen) am Frontend. Aber ich möchte die Menüpunkte 3,4,5,6 & 7
sind nur für REGISTRIERTE Benutzer zugänglich. Mit anderen Worten, wenn jemand klickt
über Menüpunkt 3/4/5/6/7 werden sie zu den Login-Modulen geführt.

Also habe ich ein "verstecktes Menü" mit den Menüpunkten für 3 - 7 erstellt, indem ich die verwendet habe
eingeschränkte Zugriffsebene. Als ich dann das "echte" Menü erstellte, verwendete ich
den Menütyp „Alias“ für diese Elemente und stellen Sie den Parameter „Menüelement“ ein
zum entsprechenden Menüpunkt im "versteckten Menü".

Soweit ich weiß, ist diese Methode auf alle Menüs im Menü anwendbar
Manager. Im Falle von Hilfe oder Anregungen kontaktieren Sie mich bitte unter
forums.joomla.org mein Benutzername ist ziggy03. Im Falle eines besseren bzw
Alternativmethode können Sie diese Seite gerne bearbeiten. Danke.