---
title: Kanalpunkt-Einlösung
description: Channel Points lösen Sound, Chat-Nachricht und OBS-Aktion aus.
---

# Kanalpunkt-Einlösung

Eine Action-Chain die bei einer Kanalpunkte-Einlösung einen Sound spielt, eine Chat-Nachricht sendet und eine OBS-Quelle steuert.

## Voraussetzungen

- Premium-Plan
- Twitch Channel Point Reward erstellt
- OBS WebSocket aktiv

## Schritt für Schritt

1. Erstelle ein **Channel Point Reward** auf Twitch (z.B. "Party Mode", 5.000 Punkte)
2. Desktop App → **Action-Chains** → **Neue Chain**
3. **Trigger:** Channel Points → "Party Mode"
4. **Cooldown:** 60 Sekunden (global)

### Aktionen

| # | Aktion | Einstellung |
|---|--------|------------|
| 1 | Chat-Nachricht | `{username} hat Party Mode aktiviert!` |
| 2 | OBS: Quelle ein | "Confetti Overlay" |
| 3 | Sound abspielen | `party.mp3` |
| 4 | Warten | 10 Sekunden |
| 5 | OBS: Quelle aus | "Confetti Overlay" |

## Ergebnis

Viewer löst "Party Mode" ein → Bot-Nachricht im Chat → Confetti-Overlay in OBS → Party-Sound → Nach 10 Sekunden verschwindet das Overlay. 60 Sekunden Cooldown bis zur nächsten Einlösung.
