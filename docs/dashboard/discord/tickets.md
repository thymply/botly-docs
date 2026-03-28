---
title: Ticket-System
description: Support-Tickets mit Kategorien, Formularen und Transcripts für deinen Discord-Server.
---

# Ticket-System

Das Ticket-System erstellt temporäre private Kanäle für Support-Anfragen. User klicken auf einen Button, ein Kanal wird erstellt, Mods helfen, und beim Schließen wird ein Transcript gespeichert.

## Übersicht

Der Ablauf:

1. **Ticket-Panel** erscheint im konfigurierten Kanal (Embed mit Buttons)
2. User klickt auf einen **Kategorie-Button** (z.B. "Support", "Bug-Report")
3. Ein **privater Kanal** wird erstellt — nur der User + Support-Rollen sehen ihn
4. Bot sendet eine **Begrüßungsnachricht** mit Buttons zum Schließen und Claimen
5. Nach dem Schließen: **HTML-Transcript** wird im Log-Kanal gespeichert, Kanal wird gelöscht

## Einrichtung

1. Gehe zu **Discord** → Server → **Tickets**
2. Aktiviere das **Ticket-System**
3. Konfiguriere:

| Einstellung | Beschreibung |
|------------|-------------|
| **Ticket-Kanal** | Text-Kanal wo die Buttons erscheinen |
| **Ticket-Kategorie** | Discord-Kategorie für die Ticket-Kanäle |
| **Log-Kanal** | Text-Kanal für Transcripts |
| **Support-Rollen** | Rollen die alle Tickets sehen können |
| **Max. offene Tickets** | Pro User (Default: 1) |

4. Klicke auf **Speichern**

<!-- Screenshot: Ticket-Einstellungen -->

## Kategorien

Ticket-Kategorien erscheinen als Buttons im Panel. Jede Kategorie hat:

- **Name** — z.B. "Support", "Bug-Report"
- **Emoji** — z.B. 🆘, 🐛, 💡, 📩
- **Button-Farbe** — Blau, Rot, Grün oder Grau
- **Beschreibung** — Wird im Panel unter dem Namen angezeigt

### Standard-Kategorien

Beim ersten Aktivieren werden 4 Kategorien erstellt:

| Kategorie | Emoji | Farbe | Beschreibung |
|-----------|-------|-------|-------------|
| Support | 🆘 | Blau | Brauchst du Hilfe? |
| Bug-Report | 🐛 | Rot | Etwas funktioniert nicht richtig? |
| Feature-Request | 💡 | Grün | Du hast eine Idee? |
| Allgemein | 📩 | Grau | Sonstige Anfrage |

Diese kannst du bearbeiten oder löschen.

### Formulare

Kategorien können ein **Formular** haben — ein Discord-Popup mit bis zu 5 Feldern das der User beim Erstellen ausfüllt.

!!! tip "Strukturierte Bug-Reports"
    Lege für "Bug-Report" ein Formular an mit den Feldern: "Was ist passiert?", "Schritte zum Reproduzieren", "Erwartetes Verhalten", "Plattform". So bekommst du strukturierte Informationen statt "es geht nicht".

## Begrüßungsnachricht

Die Nachricht die der Bot im neuen Ticket-Kanal sendet.

### Verfügbare Variablen

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `{user}` | @Mention des Users | @CoolViewer |
| `{category}` | Name der Kategorie | Support |
| `{ticket_number}` | Ticketnummer | 0042 |

### Standard-Text

```
Hallo {user}, wie können wir dir helfen?

Beschreibe dein Anliegen und ein Moderator wird sich
so schnell wie möglich melden.

Kategorie: {category}
```

Du kannst den Text frei anpassen. Der "Standard"-Button setzt ihn zurück.

## Ticket-Panel senden

Klicke auf **Ticket-Panel senden** um die Embed-Nachricht mit den Buttons im konfigurierten Kanal zu erstellen. Das Panel bleibt permanent stehen.

!!! info "Panel aktualisieren"
    Wenn du Kategorien änderst, sende das Panel erneut — das alte wird automatisch gelöscht und durch das neue ersetzt.

## Für Moderatoren

### Ticket übernehmen (Claim)

Klicke auf **📌 Claim** um ein Ticket zu übernehmen. Im Kanal erscheint eine Nachricht wer das Ticket bearbeitet.

### Ticket schließen

1. Klicke auf **🔒 Ticket schließen**
2. Bestätige mit **Ja, schließen**
3. Der Bot erstellt ein HTML-Transcript und sendet es in den Log-Kanal
4. Der Ticket-Kanal wird nach 3 Sekunden gelöscht

Das Transcript enthält alle Nachrichten mit Zeitstempel, Autor und Anhängen — als herunterladbare HTML-Datei im Dark-Theme.

## Für User

- Klicke auf den gewünschten **Kategorie-Button** im Ticket-Panel
- Falls ein Formular konfiguriert ist: Fülle die Felder aus
- Dein Ticket-Kanal erscheint automatisch in der Kategorie
- Nur du und die Support-Rollen sehen den Kanal

!!! warning "Max. offene Tickets"
    Standardmäßig kann jeder User nur 1 offenes Ticket haben. Schließe dein altes Ticket bevor du ein neues erstellst.

## Statistiken

Oben auf der Ticket-Seite siehst du:

- **Offen** — Aktuell offene Tickets
- **Heute** — Heute erstellte Tickets
- **Gesamt** — Alle Tickets seit Aktivierung
