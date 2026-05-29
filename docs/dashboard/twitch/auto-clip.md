---
title: Auto-Clip
description: Automatisch Twitch-Clips erstellen bei bestimmten Events.
---

# Auto-Clip

Auto-Clip erstellt automatisch Twitch-Clips wenn bestimmte Events eintreten — Raids, große Donations oder auf Chat-Befehl.

## Einrichtung

1. Gehe zu **Twitch Bot** → **Auto-Clip**
2. Aktiviere **Auto-Clip**
3. Wähle die **Trigger-Events**

## Trigger-Events

| Event | Beschreibung |
|-------|-------------|
| **Raid** | Bei jedem eingehenden Raid |
| **Große Donation** | Ab einem konfigurierbaren Betrag |
| **Chat-Befehl** | Per `!clip` im Chat |

## Einstellungen

| Einstellung | Beschreibung | Standard |
|------------|-------------|---------|
| Clip-Verzögerung | Sekunden nach dem Event | 5 |
| Clip-Dauer | Länge des Clips | 30 Sekunden |

!!! note "Twitch-Limit"
    Twitch erlaubt maximal einen Clip alle 60 Sekunden pro Kanal. Bei mehreren schnellen Events wird nur der erste geClippt.

!!! info "Premium Feature"
    Auto-Clip ist ab dem Premium-Plan verfügbar.
