---
title: Werbung / Ads
description: Twitch-Werbepausen automatisch ankündigen und Rückkehr-Nachrichten senden.
---

# Werbung / Ads

Lass den Bot Werbepausen automatisch ankündigen — mit Vorwarn-Nachrichten und Rückkehr-Bestätigung.

## Werbe-Ankündigung

Wenn eine Werbepause startet, sendet der Bot automatisch eine Nachricht im Chat.

### Einrichtung

1. Gehe zu **Twitch Bot** → **Werbung**
2. Aktiviere **Werbe-Ankündigung**
3. Passe die **Nachricht** an

Verfügbare Variablen:

| Variable | Beschreibung |
|----------|-------------|
| `{duration}` | Werbedauer in Sekunden |
| `{minutes}` | Werbedauer in Minuten (gerundet) |
| `{type}` | "manuell" oder "automatisch" |

### Rückkehr-Nachricht

Optional: Eine Nachricht die nach Ablauf der Werbedauer automatisch gepostet wird.

## Vorwarnung

Warne deine Viewer **vor** der Werbepause:

1. Aktiviere **Vorwarnung vor Werbepause**
2. Füge Warnmeldungen hinzu (z.B. 60 Sekunden vorher, 30 Sekunden vorher)
3. Jede Warnung hat eigenen Text und Timing

!!! tip "Mehrere Warnungen"
    Erstelle zwei Warnungen: 60 Sekunden und 10 Sekunden vor der Werbung. So haben Viewer genug Zeit sich darauf einzustellen.
