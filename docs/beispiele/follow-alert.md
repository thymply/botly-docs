---
title: Follow-Alert mit OBS-Animation
description: Alert bei neuem Follower mit OBS-Quellensteuerung und Animation.
---

# Follow-Alert mit OBS-Animation

Zeige einen Alert und steuere gleichzeitig eine OBS-Quelle wenn jemand deinem Kanal folgt.

## Voraussetzungen

- Premium-Plan
- Desktop App verbunden
- OBS WebSocket aktiv

## Schritt für Schritt

### 1. Alert gestalten

1. Desktop App → **Alerts** → **Follow**
2. Wähle ein **Bild** (z.B. ein animiertes GIF)
3. **Text:** `{username} folgt jetzt!`
4. **Animation:** Bounce In, 1 Sekunde
5. **Sound:** Wähle eine Sounddatei
6. Speichern

### 2. Action-Chain erstellen

1. Desktop App → **Action-Chains** → **Neue Chain**
2. **Name:** "Follow-Celebration"
3. **Trigger:** Twitch Follow
4. **Cooldown:** 5 Sekunden

### 3. Aktionen hinzufügen

| # | Aktion | Einstellung |
|---|--------|------------|
| 1 | Alert anzeigen | Follow Alert, Standard-Kanal |
| 2 | OBS: Quelle ein | "Confetti Overlay" |
| 3 | Chat-Nachricht | `Willkommen {username}!` |
| 4 | Warten | 5 Sekunden |
| 5 | OBS: Quelle aus | "Confetti Overlay" |

## Ergebnis

Bei jedem Follow: Alert erscheint, Confetti-Overlay blendet sich ein, Chat-Nachricht wird gesendet. Nach 5 Sekunden verschwindet das Overlay.
