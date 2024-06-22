<!-- Filename: J4.x:Workflow/Scenarios / Display title: Workflow/Szenarien -->

## Workflows realisieren

Die allgemeine Reihenfolge der Aufgaben, um einen neuen Workflow
einzurichten sind:

1.  Planen
2.  Neue **Benutzergruppen** hinzufügen (optional)
3.  Neue **Benutzer** hinzufügen und sie den entsprechenden
    **Benutzergruppen** zuweisen (optional)
4.  Neuen **Workflow** erstellen
5.  Die **Stufe(n)** für diesen **Workflow** mit der/den
    **Bedingung(en)** erstellen
6.  Die **Übergänge** des Workflows anlegen
7.  Hinzufügen oder Bearbeiten der entsprechenden **Kategorie**, für den
    **Workflow**
8.  Die **Berechtigungen** der **Kategorie** bearbeiten, sodass die
    neuen **Benutzergruppen** nur die für sie erforderlichen
    Berechtigungen erhalten
9.  Falls erforderlich, Benachrichtigungen einrichten
10. Den Login-Zugang für die **Benutzer** im Frontend einrichten (oder
    im Backend: ist in dieser Anleitung nicht enthalten) (optional)

## Planung

Genau planen, was der Workflow leisten soll. Die Planung ist immer der
wichtigste Teil. Diese Fragen sollten bei der Planung nützlich sein:

- Wie viele Benutzergruppen (auch wenn es nur einen Benutzer in dieser
  Gruppe gibt) müssen eine Aufgabe übernehmen?
- Wie viele verschiedene Aufgaben wird es im Workflow geben?
- Muss eine der Gruppen Benachrichtigungen erhalten, um ihre Aufgabe zu
  erfüllen?
- Werden die Gruppen ihre Aufgaben über das Frontend oder das Backend
  oder eine Mischung aus beiden verrichten?
- Welche Kategorien haben einen/diesen Workflow?
- Werden unterschiedliche Kategorien unterschiedliche Workflows haben?

## Erstes (Beispiel-)Szenario

- Eine Benutzergruppe kann Blogbeiträge erstellen, diese aber nicht
  veröffentlichen
- Eine zweite Benutzergruppe genehmigt die Blogbeiträge und
  veröffentlicht sie

### Anlegen neuer Benutzergruppen

1.  Zu **Benutzer** **→** **Gruppen** **→** Neu wechseln
2.  Den **Gruppentitel** eingeben: *Blog-Autor*
3.  Die **Übergeordnete Gruppe** auswählen: Registriert
4.  „Speichern & Neu“ klicken
5.  Den **Gruppentitel** eingeben: *Blog-Freigabe*
6.  Die **Übergeordnete Gruppe** auswählen: Registriert
7.  „Speichern & Schließen“ klicken

### Neuen Benutzer anlegen (oder vorhandenen Benutzer bearbeiten)

Using the directions on  create your new
**Users**.

1.  **Benutzer** anlegen und diese(n) der **Benutzergruppe**
    *Blog-Autor* zuordnen.
2.  **Benutzer** anlegen und diese(n) der **Benutzergruppe**
    *Blog-Freigabe* zuordnen.

**HINWEIS**: Wenn gewollt ist, dass die **Benutzer** bei einem
**Übergang** (siehe weiter unten) Benachrichtigungen erhalten, dann die
Option **System-E-Mails erhalten** bei jedem **Benutzer**, der
Benachrichtigungen erhalten soll, aktivieren.

### Workflow erstellen

1.  Zu **Inhalt** **→** **Workflows** **→** Neu wechseln
2.  Den **Namen** eingeben: *Blog-Workflow*
3.  „Speichern & Schließen“ klicken

**HINWEIS**: Diesen Workflow nur dann als *Standard* markieren, wenn er
für sämtliche neuen Beiträge, die in Kategorien **ohne** zugewiesenen
Workflow erstellt werden, als Standard-Workflow verwendet werden soll.
Bestehende Beiträge werden nicht geändert.

### Stufe(n) des Workflows erstellen

1.  In der Listenansicht **Workflows** auf den Link "**verwalten**"
    neben dem **Blog Workflow** in der Spalte **Status** klicken. Der
    Standardstatus **Veröffentlicht** wird angezeigt.
2.  Auf den **Standardstatus** klicken und den **Titel** in
    „Veröffentlicht“ ändern: *Neuen Blogbeitrag veröffentlichen*.
3.  The **Condition of items in this state: Published** will remain
    unchanged.
4.  Click Save & New.
5.  Enter the **Title**: *New blog post, unpublished*.
6.  Change the **Condition** of items in this **State** to Unpublished.
7.  Change the **Default** to Yes (Green) since this is the **Default
    State** for Articles in this Workflow.
8.  Click Save & Close.

### Create Transition for the Workflow

There are two ways to access **Transitions**:

1.  Click **Transitions** from the sidebar while in the States list
    view.
2.  Click the blue line with arrows in both directions from the
    **Workflow** list view.
1.  Go to **Transitions**.
2.  Click New.
3.  Add the **Title**: *Approve/Publish*
4.  Select the **State** *New blog post – unpublished* in the **From
    state** field drop-down.
5.  Select the **State** *Publish new blog post* in the **To state**
    field drop-down.
6.  Click Save and remain in this **Transition**.
7.  Click the **Permissions** tab of the **Transition**.
8.  Select the **User Group** *Blog Approvers*.
9.  For the **Action** **Execute transition**, select **Allowed** from
    the **Select New Setting** drop-down.
10. Click Save & Close.

**NOTE**: You can quickly access your **States** and **Transitions**
from the **Workflow** list view. The orange circle is the States and has
the quantity of States listed next to the Workflow Title. The blue line
with arrows in both directions is for Transitions and shows the quantity
of Transitions for the Workflow.

### Assign Workflow & User Group Permissions to the Category

1.  Go to **Content** **→** **Categories**
2.  Access the *Blog* **Category** (or create it if necessary) and click
    the **Workflow** tab.
3.  Click the drop-down and select *Blog Workflow*.
4.  Click the **Permissions** tab.
5.  Click on the *Blog Poster* **User Group**.
6.  For the **Action** Create and Edit, change the **Select New
    Setting** drop-down to Allowed.
7.  Click on the *Blog Approvers* **User Group**.
8.  For the **Action** Delete, Edit, Edit State and Edit Own, change the
    **Select New Setting** drop-down to Allowed.
9.  Click Save & Close.

For more information on ACL and assigning permissions to User Groups,
see the  ACL
Tutorial.

### Setting up Notifications

Notifications use the Joomla core Messaging component. It is very basic.
When enabled for Workflows, it will send a message to the User
associated with the Group assigned to the Transition. The message simply
states that they have a message in the site. It will then be their
responsibility to login and check the articles that need approval and
publish them.

**To set up notifications for the Workgroup Transitions:**

1.  Go to **Extensions** **→** **Plugins**
2.  Click the **Table Options** button and **Select Type** of content
3.  Click on **Content – Joomla** and then toggle Yes for **Email on
    transition execution**
4.  Then make sure that the **Users** themselves have **Receive System
    Emails** toggled to Yes in **Users** **→** **Manage**.

### To set it up so that Users can Post and Approve from the frontend

1.  Create a **Menu Item** for the **Menu Item Type** Login so that your
    Blog Posters can login.
    **Menus** **→** *Choose or create a
    menu* **→** New **→** **Users** **→** **Login**
    OR
2.  Create a module for Login so that your Blog Posters can login.
    **Extensions** **→** **Modules** **→** New **→** **Login**
3.  Add a **Menu Item** to a Menu that displays only for the
    **Registered User Group** to Add an article
    **Menu Item Type Articles** **→** **Create Article**
    **NOTE**: this will display for all Registered Users unless you
    create an Access Level for your Blog Poster User Group and select
    this in the Menu Item under Access.
4.  When your **User** logs in, they add an **Article**, enter the
    content and Save.
5.  This will trigger a notification to the Blog Approvers Users that
    there is a new private message on the site. It doesn’t get more
    specific than that. Approvers should just come to the site and
    approve the Article. It will also send a message to Super Admins.
6.  When the Blog Approver logs in, they can navigate to where the new
    article will appear. They will be able to see the unpublished
    article and edit it/approve it/publish it. Then they can Save &
    Close and logout.

**Admin note**: Super Admins can use Batch to move existing Articles to
a different workflow than it is currently assigned. It won’t make a
difference if the Articles are already published.

## Scenario \#2

Add another scenario here to help others see the power of Workflows.
Docs can be edited or added to by anyone with an account.

## Related Information

See also:

-  Publishing Workflow
  Implementation
-  Publishing
  Workflow
