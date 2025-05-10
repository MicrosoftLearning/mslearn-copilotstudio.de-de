---
lab:
  title: Erstellen von Agentaktionen
  module: Enhance Microsoft Copilot Studio copilots
---

# Erstellen von Copilotaktionen

## Szenario

Dieses Lab deckt Folgendes ab:

- Erstellen von Agentaktionen

## Lernziele

- Hinzufügem von Power Automate, um auf Daten in Microsoft Dataverse zuzugreifen

## Weiterführende Schritte des Lab

- Erstellen eines Power Automate-Cloudflows zum Abrufen von Dataverse-Daten mit einer Agent-Aktion
- Erstellen eines Power Automate-Cloudflows zum Erstellen von Dataverse-Daten mit einer Agent-Aktion
  
## Voraussetzungen

- Erfordert abgeschlossenes **Lab: Arbeiten mit Entitäten**

## Ausführliche Schritte

## Übung 1: Erstellen einer Agent-Aktion zum Abrufen von Daten aus Dataverse

Microsoft Copilot Studio kann mithilfe von Power Automate-Cloudflows auf Daten in Microsoft Dataverse zugreifen.

### Aufgabe 1.1: Erstellen eines Power Automate-Flows zum Abrufen einer Immobilie

1. Navigieren Sie zum Microsoft Copilot Studio-Portal `https://copilotstudio.microsoft.com` und stellen Sie sicher, dass Sie sich in der entsprechenden Umgebung befinden.

1. Wählen Sie **Agenten** im linken Navigationsbereich aus.

1. Wählen Sie den **Immobilienbuchungsdienst** aus, den Sie im vorherigen Lab erstellt haben.

1. Klicken Sie auf die Registerkarte **Actions** (Aktionen).

1. Wählen Sie **+ Aktion hinzufügen** aus.

    ![Screenshot von Schritt 1 zum Hinzufügen einer Aktion.](../media/add-action-step-1.png)

1. Wählen Sie den **Flow-Filter** aus, und wählen Sie dann **Flow mit Power Automate für Desktop ausführen** aus.

1. Wählen Sie **Flow aus Copilot ausführen** in der oberen linken Ecke des Bildschirms und geben Sie `Get Property` als Flownamen ein.

1. Wählen Sie den Trigger-Schritt **Flow von Copilot ausführen** und wählen Sie **+ Eingabe hinzufügen**.

1. Wählen Sie **Text** aus.

1. Geben Sie `Bedrooms` für **Eingabe** und `Number of Bedrooms` für **Bitte Eingabe eingeben** ein.

    ![Screenshot der Trigger-Eigenschaften des Flows.](../media/create-flow-step2.png)

1. Wählen Sie das Symbol **+** zwischen den beiden Schritten im Flow und wählen Sie **Aktion hinzufügen**.

1. Geben Sie `Dataverse` in das Feld **Suchen** ein und wählen Sie **Mehr anzeigen** für den **Microsoft Dataverse**-Connector.

    ![Screenshot der Suche nach einem Connector im Flow.](../media/create-flow-step3.png)

1. Wählen Sie die Aktion **Zeilen auflisten**.

1. Wenn Sie zur Authentifizierung aufgefordert werden, wählen Sie **Authentifizierung** und wählen Sie **Anmelden**.

    > **Hinweis:** Wenn Sie die Fehlermeldung '**Fehler beim Erstellen der OAuth-Verbindung** sehen, müssen Sie möglicherweise Popups in Ihrem Browser zulassen.

    ![Screenshot des OAuth-Fehlers.](../media/failed-oauth-popup.png)

    ![Screenshot des Zulassens von Popups in Edge.](../media/failed-oauth-popup-2.png)

1. Wählen Sie **Immobilien** als Tabellenname.

1. Geben Sie `contoso_bedrooms eq ` (mit einem Leerzeichen nach **eq**) in das Feld **Filterzeilen** ein.

1. Wenn das Feld **Filterreihen** noch immer ausgewählt ist, wählen Sie das **Blitz**-Symbol rechts daneben und dann den Parameter **Bedrooms**.

    ![Screenshot der Konfiguration der Aktion „Zeilen auflisten“.](../media/create-flow-step4.png)

1. Markieren Sie im Hauptbedienfeld von Power Automate die Aktion **Auf Copilot reagieren** und wählen Sie **+ Ausgang hinzufügen**.

1. Wählen Sie **Text** aus.

1. Geben Sie `PropertyId` für **Namen eingeben** ein

1. Markieren Sie das Feld **Wert eingeben, um zu antworten mit** und wählen Sie **fx (Ausdruck einfügen)** aus.

1. Geben Sie den folgenden Ausdruck in das obere Feld ein:

    ```
    first(outputs('List_rows')?['body/value'])['contoso_realestatepropertyid']
    ```

    ![Screenshot der Konfiguration der Antwortaktion.](../media/create-flow-step5.png)

1. Wählen Sie **Hinzufügen**.

1. Wählen Sie **+ Eine Ausgabe hinzufügen** aus.

1. Wählen Sie **Text** aus.

1. Geben Sie `PropertyName` für **Namen eingeben** ein.

1. Markieren Sie das Feld **Wert eingeben, um zu antworten mit** und wählen Sie **fx (Ausdruck einfügen)** aus.

1. Geben Sie den folgenden Ausdruck ein:

    ```
    first(outputs('List_rows')?['body/value'])['contoso_propertyname']
    ```

1. Wählen Sie **Hinzufügen**.

1. Wählen Sie die Registerkarte **Einstellungen** im Bereich **Auf Copilot reagieren**.

1. Stellen Sie sicher, dass **Asynchrone Antwort** auf **Aus** gesetzt ist.

    ![Screenshot der Antwortaktionseinstellungen.](../media/create-flow-step6.png)

1. Wählen Sie **Speichern** in der Nähe der oberen rechten Ecke der Seite.

1. Warten Sie, bis der Speichervorgang abgeschlossen ist, wählen Sie **Veröffentlichen** und schließen Sie die Registerkarte „Power Automate“, sobald die Veröffentlichung abgeschlossen ist.

### Aufgabe 1.2: Hinzufügen einer Agent-Aktion zum Abrufen einer Immobilie

1. Wählen Sie **Aktualisieren** im Copilot Studio-Dialogfeld aus, um den neuen Flow zu sehen.

1. Wählen Sie den Flow **Eigenschaft abrufen**.

    ![Screenshot von Schritt 1 zum Hinzufügen einer Flowaktion.](../media/add-action-flow-step-1.png)

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Weiter** aus.

1. Klicken Sie auf **Fertig stellen**.

### Aufgabe 1.3: Hinzufügen der Agent-Aktion „Eigenschaft abrufen“ zum Thema

1. Wählen Sie die Registerkarte **Themen**.

1. Wählen Sie das Thema **Immobilienbesichtigung buchen**.

1. Wählen Sie das Symbol **+** unterhalb des Knotens **Wie viele Schlafzimmer benötigen Sie?**, wählen Sie **Aktion aufrufen** und wählen Sie dann den Flow **Eigenschaft abrufen**.

    ![Screenshot von Schritt 2 zum Hinzufügen einer Flowaktion.](../media/add-action-flow-step-2.png)

1. Wählen Sie für den Eingabeparameter **Bedrooms** die Variable **NumberofBedrooms**.

    ![Screenshot von Schritt 3 zum Hinzufügen einer Flowaktion.](../media/add-action-flow-step-3.png)

1. Markieren Sie die **drei Punkte** im Knoten **Welche Immobilie möchten Sie sehen?** und wählen Sie **Löschen**.

1. Wählen Sie das Symbol **+** unter dem Knoten **Aktion** und wählen Sie **Nachricht senden**.

1. In das Feld **Nachricht eingeben** geben Sie `Property ` ein (mit einem Leerzeichen dahinter).

1. Wählen Sie im gleichen Knoten das Symbol **{X} (Variable einfügen)** und wählen Sie die Variable **PropertyName**.

    ![Screenshot von Schritt 4 zum Hinzufügen einer Flowaktion.](../media/add-action-flow-step-4.png)

1. Wählen Sie **Speichern**.

## Übung 2: Erstellen einer Agent-Aktion zum Erstellen von Daten in Dataverse

Microsoft Copilot Studio kann Daten in Microsoft Dataverse mithilfe von Power Automate-Cloudflows erstellen.

### Aufgabe 2.1: Erstellen eines Power Automate-Flows zum Durchführen einer Buchung

1. Wählen Sie die Registerkarte **Aktionen** in **Immobilien-Buchungsdienst** aus.

1. Wählen Sie **+ Aktion hinzufügen** aus.

1. Scrollen Sie nach unten und wählen Sie **+ Neue Aktion** und dann **Neuer Power Automate-Flow** .

1. Wählen Sie **Flow aus Copilot ausführen** in der oberen linken Ecke des Bildschirms und geben Sie `Create Booking Request` als Flownamen ein.

1. Wählen Sie den Trigger-Schritt **Wenn ein Agent den Flow anruft** und wählen Sie **+ Einen Input hinzufügen**.

1. Wählen Sie **Text** aus.

1. Geben Sie `PropertyId` als **Eingabe** ein und `Property` für **Bitte Eingabe eingeben**.

1. Wählen Sie **+ Eingabe hinzufügen** aus.

1. Wählen Sie **Text** aus.

1. Geben Sie `ViewerName` als **Eingabe** ein und `Viewer Name` für **Bitte Eingabe eingeben**.

1. Wählen Sie **+ Eingabe hinzufügen** aus.

1. Wählen Sie **Text** aus.

1. Geben Sie `ViewerEmail` als **Eingabe** ein und `Viewer Email` für **Bitte Eingabe eingeben**.

    ![Screenshot der Aktion zum Konfigurieren von Flowparametern.](../media/create-flow2-step1.png)

1. Wählen Sie das Symbol **+** zwischen den beiden Schritten im Flow und wählen Sie **Aktion hinzufügen**.

1. Geben Sie `Dataverse` in das Feld **Suchen** ein und wählen Sie **Mehr anzeigen** für den **Microsoft Dataverse**-Connector.

1. Wählen Sie die Aktion **Neue Zeile hinzufügen**.

1. Wählen Sie **Buchungsanfragen** als Tabellenname aus.

1. Geben Sie `Copilot booking` in das Feld **Buchungsname** ein.

1. Wählen Sie unter **Erweiterte Parameter** die Option **Alle anzeigen** aus.

1. Geben Sie `contoso_bookingrequests(PropertyId)` in das Feld **Eigenschaft (Immobilieneigenschaften)** ein, bewegen Sie den Cursor innerhalb der Klammern, wählen Sie das **Blitz**-Symbol und wählen Sie dann den Parameter **PropertyId**.

1. Markieren Sie das Feld **Betrachter-E-Mail**, wählen Sie das **Blitz**-Symbol und wählen Sie dann den Parameter **ViewerEmail**.

1. Markieren Sie das Feld **Betrachtername**, wählen Sie das **Blitz**-Symbol und wählen Sie dann den Parameter **ViewerName**.

    ![Screenshot der Aktion zum Konfigurieren des Flows zum Hinzufügen von Zeilen.](../media/create-flow2-step2.png)

1. Wählen Sie die Aktion **Auf Copilot reagieren** aus.

1. Wählen Sie die Registerkarte **Einstellungen** aus.

1. Stellen Sie sicher, dass **Asynchrone Antwort** auf **Aus** gesetzt ist.

1. Wählen Sie **Speichern** in der oberen rechten Ecke des Fensters.

1. Warten Sie, bis die Speicherung abgeschlossen ist, wählen Sie **Veröffentlichen** und schließen Sie die Registerkarte „Power Automate“.

### Aufgabe 2.2: Hinzufügen einer Agent-Aktion zum Erstellen einer Buchungsanfrage

1. Wählen Sie **Aktualisieren** im Copilot Studio-Dialogfeld aus, um den neuen Flow zu sehen.

1. Wählen Sie den Flow **Buchungsanfrage erstellen**.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Weiter** aus.

1. Klicken Sie auf **Fertig stellen**.

### Aufgabe 2.3: Hinzufügen der Agent-Aktion „Buchungsanfrage erstellen“ zum Thema

1. Wählen Sie die Registerkarte **Themen**.

1. Wählen Sie das Thema **Immobilienbesichtigung buchen**.

1. Wählen Sie das Symbol **+** unterhalb des Knotens **An welchem Datum und zu welcher Uhrzeit möchten Sie die Immobilie sehen?**, wählen Sie **Aktion hinzufügen** und dann den Flow **Buchungsanfrage erstellen**.

1. Wählen Sie die Variable **PropertyId** für den Eingabeparameter **PropertyId**.

1. Wählen Sie die Variable **Name** für den Eingabeparameter **ViewerName**.

1. Wählen Sie die Variable **EmailAddress** für den Eingabeparameter **ViewerEmail**.

1. Wählen Sie das Symbol **+** unter dem neuen Knoten **Aktion**, wählen Sie **Themenverwaltung**, wählen Sie **Zu einem anderen Thema wechseln** und wählen Sie **Gespräch beenden**.

1. Wählen Sie **Speichern**.

1. Wählen Sie **Veröffentlichen** und wählen Sie erneut **Veröffentlichen** aus.

## Übung 3: Testen der Agent-Aktionen

### Aufgabe 3.1: Stellen einer Buchungsanfrage

1. Falls geschlossen, wählen Sie die Schaltfläche **Testen** in der oberen rechten Ecke des Bildschirms, um das Bedienfeld zum Testen zu öffnen.

1. Wählen Sie die **drei Punkte** am oberen Rand des Bedienfelds oben rechts auf dem Bildschirm.

    ![Screenshot der Bedienfeldoptionen für Tests.](../media/test-pane-options.png)

1. Wenn sie nicht aktiviert ist, aktivieren Sie **Nachverfolgen der Themenverläufe**.

1. Wählen Sie das Symbol **Neue Konversation beginnen** oben auf dem Bedienfeld für Tests.

1. Wenn die Meldung **Gesprächsbeginn** erscheint, wird Ihr Agent ein Gespräch beginnen. Geben Sie als Antwort einen Triggerausdruck für das Thema ein, das Sie erstellt haben.

    `I want to book a real estate showing`

1. Geben Sie die folgenden Informationen ein:

    ```
    Name: <Your name>
    ```
    ```
    Email address: <Your email address>
    ```

1. Nachdem Sie die Informationen angegeben haben, zeigt eine adaptive Karte die eingegebenen Informationen an und fragt, ob die Details korrekt sind. Wählen Sie **Ja** aus.

1. Wählen Sie **Haus** für die Art der Immobilie aus.

1. Geben Sie `3` für die Anzahl der Schlafzimmer ein.

    ![Screenshot des Testbedienfelds mit den eingegebenen Informationen.](../media/test-pane-action-results.png)

1. Geben Sie `Tomorrow 2:00 PM` in den Prompt **An welchem Datum und zu welcher Uhrzeit möchten Sie die Immobilie sehen?** ein.

1. Wählen Sie **Ja** auf die Aufforderung **Hat das Ihre Frage beantwortet?**.

1. Wählen Sie eine beliebige Bewertung aus.

1. Wählen Sie **Nein** bei der Aufforderung **Kann ich sonst noch helfen?**.
    >[!Note] Möglicherweise werden keine Antworten generiert.

### Aufgabe 3.2: Überprüfen der Buchungsanfrage

1. Falls noch nicht geöffnet, navigieren Sie zu `https://make.powerapps.com` in einer neuen Registerkarte.

1. Stellen Sie sicher, dass Sie sich in der richtigen Umgebung befinden.

1. Wählen Sie **Spielen** auf der modellgesteuerten App **Immobilienverwaltung**.

1. Wählen Sie in der linken Navigation **Buchungsanfragen**.

    ![Screenshot des Maker-Portals mit den Daten der Buchungsanfrage.](../media/booking-request-row.png)
