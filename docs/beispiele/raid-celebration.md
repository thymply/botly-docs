---
title: Raid-Celebration
description: Vollbild-Animation bei einem Raid mit OBS-Szenen-Wechsel.
---

# Raid-Celebration

Eine spektakuläre Vollbild-Animation wenn ein anderer Streamer dich raidet.

## Voraussetzungen

- Premium-Plan
- OBS-Szene "Raid" mit Celebration-Animation vorbereitet

## Schritt für Schritt

1. Erstelle in OBS eine **"Raid" Szene** mit einer Vollbild-Animation (Video, GIF oder Bild)
2. Desktop App → **Action-Chains** → **Neue Chain**
3. **Trigger:** Twitch Raid
4. **Bedingung:** Mindestbetrag 5 (mindestens 5 Viewer im Raid)

### Aktionen

| # | Aktion | Einstellung |
|---|--------|------------|
| 1 | Chat-Nachricht | `RAID! Willkommen {username} mit {amount} Viewern!` |
| 2 | OBS: Szene wechseln | "Raid" |
| 3 | Alert anzeigen | Raid Alert (Custom) |
| 4 | Warten | 15 Sekunden |
| 5 | OBS: Szene wechseln | "Gaming" (zurück) |

## Ergebnis

Bei einem Raid mit mindestens 5 Viewern: Chat-Nachricht → OBS wechselt zur Raid-Szene → Custom Alert → 15 Sekunden Celebration → zurück zur Gaming-Szene.
