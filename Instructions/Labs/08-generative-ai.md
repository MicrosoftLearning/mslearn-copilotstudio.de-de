---
lab:
  title: Verwenden generativer KI in Microsoft Copilot Studio
  module: Enhance Microsoft Copilot Studio agents
---

# Verwenden generativer KI in Microsoft Copilot Studio

## Szenario

In dieser Übung führen Sie die folgenden Schritte aus:

- Verwenden von Wissen und generativer KI in Ihrem Agent

Diese Übung dauert etwa **30** Minuten.

## Lernziele

- Verwendung der Funktion „Generative Antworten“, um die Antworten Ihres Agents zu verbessern.

## Weiterführende Schritte des Lab

- Aktivieren von generativer KI
- Hinzufügen von Wissen
  
## Voraussetzungen

- Erfordert abgeschlossenes **Lab: Erstellen von Agent-Aktionen**

## Ausführliche Schritte

## Übung 1: Konfigurieren von generativer KI

### Aufgabe 1.1: Aktivieren der Orchestrierung

1. Wenn es noch nicht geöffnet ist, rufen Sie das Microsoft Copilot Studio-Portal `https://copilotstudio.microsoft.com` auf und stellen Sie sicher, dass Sie sich in der entsprechenden Umgebung befinden.

1. Wählen Sie **Agents** in der linken Navigation aus.

1. Wählen Sie den **Immobilienbuchungsdienst** aus, den Sie im vorherigen Lab erstellt haben.

1. Wählen Sie die Schaltfläche **Einstellungen** oben rechts auf dem Bildschirm.

1. Stellen Sie im Abschnitt **Details** die Orchestrierung auf **Ja** um.

1. Wählen Sie **Speichern**.

1. Schließen Sie das Fenster Einstellungen.

### Aufgabe 1.2: Verwenden von generativen Antworten im Thema „Unterhaltungsförderung“

1. Wählen Sie die Registerkarte **Themen** und wählen Sie den **Systemfilter**.

1. Wählen Sie das Thema **Unterhaltungsförderung**.

    ![Screenshot der Themenknoten für die Unterhaltungsförderung.](../media/conversational-boosting-topic-original.png)

1. Überprüfen Sie den Knoten **Generative Antworten erzeugen**.

### Aufgabe 1.3: Konfigurieren der Authentifizierung

1. Wählen Sie oben rechts auf dem Bildschirm **Einstellungen** aus.

1. Wählen Sie die Registerkarte **Sicherheit** .

1. Wählen Sie die Kachel **Authentifizierung** aus.

1. Wählen Sie **Mit Microsoft authentifizieren**.

1. Wählen Sie **Speichern**.

1. Wählen Sie **Speichern**.

1. Schließen Sie das Fenster Einstellungen.

1. Wählen Sie **Veröffentlichen** und wählen Sie erneut **Veröffentlichen** aus.

## Übung 2: Hinzufügen von Wissen

### Aufgabe 2.1: Hinzufügen von Wissen aus Dataverse

1. Wählen Sie die Registerkarte **Wissen**.

1. Wählen Sie **+ Wissen hinzufügen**.

1. Wählen Sie **Dataverse** aus.

1. Wählen Sie die Tabelle **Real Estate Property** aus.

    ![Screenshot des Hinzufügens von Websitewissen.](../media/add-dataverse-knowedge-step1.png)

1. Wählen Sie **Zum Agent hinzufügen** aus.

### Aufgabe 2.2. Hinzufügen von Wissen aus Dateien

1. Öffnen Sie ein neues Fenster und navigieren Sie zu `https://download.microsoft.com/documents/customerevidence/Files/4000007499/SummitRealtyCaseStudy.docx`, um die Datei [**Microsoft-Fallstudie**](https://download.microsoft.com/documents/customerevidence/Files/4000007499/SummitRealtyCaseStudy.docx) herunterzuladen.

1. Wählen Sie **+ Wissen hinzufügen**.

1. Wählen Sie unter **Datei hochladen** die Fallstudie aus, die Sie heruntergeladen haben.

    ![Screenshot des Hinzufügens von Dateikenntnissen.](../media/add-file-knowledge.png)

1. Wählen Sie **Zum Agent hinzufügen** aus.

    ![Screenshot des Wissens.](../media/knowledge-added.png)

## Übung 3: Konfigurieren eines Fallbackthemas

### Aufgabe 3.1: Verwenden von generativen Antworten im Systemfallbackthema

1. Wählen Sie die Registerkarte **Themen** und wählen Sie den **Systemfilter**.

1. Wählen Sie das **Fallbackthema** aus.

    ![Screenshot des Systemfallbackthema-Knotens.](../media/fallback-topic-original.png)

1. Wählen Sie die **drei Punkte** im Knoten **Nachricht** aus und wählen Sie **Löschen**.

1. Wählen Sie das Symbol **+** unter dem Knoten **Bedingungen**, wählen Sie **Erweitert** und wählen Sie **Generative Antworten**.

1. Wählen Sie im Feld **Eingabe** die Registerkarte **System** aus, und wählen Sie **Activity.Text** aus.

1. Wählen Sie **Bearbeiten** unter **Datenquellen** aus.

    ![Screenshot des Knotens „Generative Antworten erstellen“](../media/fallback-topic-answers-2.png)

1. Wählen Sie **Nur ausgewählte Quellen suchen**.

1. Wählen Sie die Dataverse-Tabelle **Immobilien**.

1. Deaktivieren Sie **Der KI erlauben, ihr eigenes Allgemeinwissen zu verwenden**.

1. Aktivieren Sie das Kontrollkästchen **Anpassen** unter **Inhaltsmoderationsebene**, und wählen Sie **mittel** aus.

1. Wählen Sie **Speichern**.

## Übung 4: Testen generativer KI

### Aufgabe 4.1: Testen des Agent-Wissens

1. Falls noch nicht geöffnet, wählen Sie die Schaltfläche **Test** in der oberen rechten Ecke des Bildschirms, um das Bedienfeld für Tests zu öffnen.

1. Wählen Sie das Symbol **Neue Konversation beginnen** oben auf dem Bedienfeld für Tests.

1. Beobachten Sie den Agent, und stellen Sie fest, wie er die Wissensquellen verwendet.
