---
title: Giveaway mit Ankündigung
description: Automatische Verlosung mit Discord-Benachrichtigung.
---

# Giveaway mit Ankündigung

Starte eine Verlosung im Stream und lass automatisch eine Ankündigung in Discord posten.

## Voraussetzungen

- Botly-Account (Free reicht für Giveaways)
- Discord-Server mit dem Bot verbunden

## Schritt für Schritt

### 1. Giveaway erstellen

1. Dashboard → **Twitch Bot** → **Giveaway**
2. **Titel:** "Steam Key Giveaway"
3. **Keyword:** `!join`
4. **Plattform:** Beide (Twitch + YouTube)
5. **Giveaway starten**

### 2. Im Stream

```
Bot:     Steam Key Giveaway gestartet! Schreibe !join um teilzunehmen!
Viewer1: !join
Viewer2: !join
...
```

### 3. Gewinner ziehen

1. Klicke auf **Gewinner ziehen** im Dashboard
2. Der Bot verkündet den Gewinner:

```
Bot:     Der Gewinner ist... Viewer1! Herzlichen Glückwunsch!
```

## Discord-Ankündigung

Für eine automatische Discord-Ankündigung nutze die [Live-Ankündigungen](../dashboard/discord/live-ankuendigungen.md) mit einem speziellen Kanal (z.B. #giveaways).

!!! tip "Timer-Giveaway"
    Setze einen Timer auf das Giveaway — z.B. 10 Minuten. Nach Ablauf wird automatisch ein Gewinner gezogen.
