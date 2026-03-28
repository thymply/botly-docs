---
title: Temp-Voice Kanäle
description: Temporäre Sprachkanäle, die automatisch erstellt und gelöscht werden.
---

# Temp-Voice Kanäle

Erstelle automatisch temporäre Sprachkanäle wenn jemand einem bestimmten Kanal beitritt — und lösche sie wieder wenn alle gehen.

## Konzept

Du erstellst einen "Trigger-Kanal" (z.B. "Sprachkanal erstellen"). Sobald jemand diesem Kanal beitritt, erstellt der Bot automatisch einen neuen Sprachkanal mit dem Namen des Users. Wenn alle den Kanal verlassen, wird er gelöscht.

## Einrichtung

1. Erstelle einen Voice-Kanal auf deinem Server (z.B. "Kanal erstellen")
2. Gehe zu **Discord** → Server → **Temp-Voice**
3. Erstelle einen neuen **Voice-Trigger**
4. Wähle den **Trigger-Kanal** und die **Kategorie** für neue Kanäle
5. Konfiguriere das **Namens-Format** (z.B. "{user}'s Kanal")
6. Speichern

## Einstellungen

| Einstellung | Beschreibung |
|------------|-------------|
| **Trigger-Kanal** | Voice-Kanal der neue Kanäle auslöst |
| **Kategorie** | Wo die neuen Kanäle erstellt werden |
| **Namens-Format** | Template mit `{user}` Variable |
| **Max. User** | Maximale Teilnehmer (0 = unbegrenzt) |

!!! info "Free-Plan: max. 1 Voice-Trigger"
    Im Free-Plan kannst du einen Voice-Trigger konfigurieren. Ab Pro gibt es kein Limit.
