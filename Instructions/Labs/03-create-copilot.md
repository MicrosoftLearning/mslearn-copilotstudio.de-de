---
lab:
  title: Erstellen eines ersten Copiloten
  module: Build an initial copilot with Microsoft Copilot Studio
---

# Erstellen eines ersten Copiloten

## Szenario

Dieses Lab deckt Folgendes ab:

- Erstellen und Benennen eines neuen Copiloten
- Hinzufügen einer Beschreibung der Aufgaben des Copiloten
- Konfigurieren von generativen KI-Antworten

## Lernziele

- Generieren von Skripten mit Copilot und natürlicher Sprache
- Konfigurieren von generative KI-Antworten für einen Copiloten

## Weiterführende Schritte des Lab

- Erstellen eines neuen Copiloten
- Sagen Sie Ihrem Copiloten, was seine Hauptaufgabe ist wie er sich verhalten soll
- Hinzufügen von generativen KI-Anweisungen
  
## Voraussetzungen

- Erfordert abgeschlossenes **Lab: Importieren der Dataverse-Lösung**

## Übung 1: Erstellen eines Copiloten

In dieser Übung greifen Sie auf das Microsoft Copilot Studio-Portal und die Umgebung für Fachkräfte in der Entwicklung zu und erstellen einen neuen Copiloten.

### Aufgabe 1.1: Microsoft Copilot Studio-Portal

1. Navigieren Sie in einer neuen Registerkarte zum Microsoft Copilot Studio-Portal `https://copilotstudio.microsoft.com` und melden Sie sich mit Ihren Microsoft 365-Anmeldedaten an, wenn Sie erneut dazu aufgefordert werden.

1. Wenn Sie dazu aufgefordert werden, wählen Sie **Kostenlose Testversion beginnen**.

1. Stellen Sie sicher, dass Sie sich in der entsprechenden Umgebung befinden.

### Aufgabe 1.2: Erstellen eines Copiloten

1. Wählen Sie **Erstellen** im linken Navigationsbereich und wählen Sie die Kachel **Neuer Agent**.

    ![Erstellen im Copilot Studio-Portal.](../media/create-copilot-agent.png)

1. Geben Sie in das Textfeld **Name** **`Real Estate Booking Service`** ein.

1. Geben Sie in das Textfeld **Beschreibung** **`Create bookings for real estate properties`** ein.

1. Geben Sie in das Textfeld **Anweisungen** **`Create a copilot for topics relating to creating bookings for real estate properties`** ein.

1. Oben sollte **Sprache** auf **Englisch (en-US)** festgelegt werden.

    ![Sprache des Copilot-Agents.](../media/copilot-agent-language.png)

1. Wählen Sie die **drei Punkte** oben rechts auf der Seite und wählen Sie **Erweiterte Einstellungen bearbeiten**.

    ![Weitere Optionen im Copilot Studio-Portal.](../media/copilot-studio-more-options-2.png)

1. Wählen Sie **Buchungen** unter **Lösung** aus.

1. Geben Sie `labcopilot` als **Schema-Namen** ein.

    ![Erweiterte Einstellungen im Copilot Studio-Portal.](../media/copilot-studio-advanced-settings.png)

1. Wählen Sie **Speichern**.

1. Wählen Sie oben rechts auf dem Bildschirm **Erstellen**.

1. Geben Sie im rechten Fenster **Agent testen** **`How do I make a booking?`** ein. Zeigen Sie die Antwort an.

Lassen Sie dieses Fenster geöffnet.

## Übung 2: Hinzufügen von generativen KI-Antworten

In dieser Übung greifen Sie auf das Microsoft Copilot Studio-Portal zu und fügen Wissen hinzu, mit dem der Copilot Fragen beantworten wird, indem Sie generative KI verwenden.

### Aufgabe 2.1: Aktivieren von generativen KI-Antworten

1. Stellen Sie auf der Registerkarte **Übersicht** sicher, dass **KI sein eigenes allgemeines Wissen zu nutzen erlauben** im Abschnitt **Wissen** auf **Aktiviert** festgelegt ist.

    ![Aktiviertes Wissen im Copilot Studio Portal.](../media/knowledge-enabled.png)

### Aufgabe 2.2: Hinzufügen einer Wissensquelle

1. Wählen Sie die Registerkarte **Wissen**.

    ![Registerkarte „Wissen“ im Copilot Studio-Portal.](../media/knowledge-tab.png)

1. Wählen Sie **+ Wissen hinzufügen**.

    ![Wissensquellen im Copilot Studio-Portal.](../media/knowledge-sources.png)

1. Wählen Sie **Öffentliche Websites** aus.

1. Geben Sie in das Textfeld **Link zur öffentlichen Website** **`https://create.microsoft.com/en-us/`** ein.

    ![Fügen Sie im Copilot Studio-Portal einen Link zur öffentlichen Website hinzu.](../media/add-website-knowledge-source.png)

1. Wählen Sie **Hinzufügen**.

1. Wählen Sie **Hinzufügen**.

1. Klicken Sie auf die Registerkarte **Übersicht**.

    ![Benutzerdefinierter Copilot im Copilot Studio-Portal.](../media/copilot-studio-copilot2.png)

1. Wählen Sie die **drei Punkte** am oberen Rand des Bereichs **Agent testen**.

1. Aktivieren Sie **Nachverfolgen der Themenverläufe**.

    ![Screenshot der Bedienfeldoptionen für Tests.](../media/test-pane-options.png)

1. Wählen Sie oben im Bereich **Agenten testen** das Symbol **Eine neue Konversation beginnen** (Aktualisierungssymbol) neben dem **X**.

    ![Screenshot der Bedienfeldoptionen für Tests.](../media/copilot-test-pane-start-new-conversation.png)

1. Geben Sie in das Textfeld **Nachricht eingeben** **`How do I boost real estate promotion?`** ein.

    ![Screenshot der Ergebnisse des Bedienfelds „Testen“.](../media/test-pane-results.png)