---
title: CrossChat für Simulcast
description: Chat-Brücke zwischen Twitch und YouTube beim gleichzeitigen Streamen.
---

# CrossChat für Simulcast

Synchronisiere den Chat zwischen Twitch und YouTube damit alle Zuschauer miteinander kommunizieren können.

## Voraussetzungen

- Pro-Plan
- Desktop App verbunden
- YouTube API Key eingerichtet

## Schritt für Schritt

### 1. YouTube API Key

1. [Google Cloud Console](https://console.cloud.google.com) → Projekt erstellen
2. YouTube Data API v3 aktivieren
3. API Key erstellen
4. In der Desktop App → **CrossChat** → Key eintragen

### 2. CrossChat aktivieren

1. Desktop App → **CrossChat**
2. **Bridge aktivieren**
3. Nachrichtenformat anpassen (z.B. `[{platform}] {user}: {message}`)

### 3. Simulcast starten

1. Starte deinen Stream auf **Twitch** und **YouTube** gleichzeitig
2. CrossChat erkennt automatisch beide Live-Streams
3. Nachrichten werden in beide Richtungen weitergeleitet

## Ergebnis

```
Twitch Viewer:   "Geiler Stream heute!"
→ YouTube Chat:  [Twitch] CoolViewer: Geiler Stream heute!

YouTube Viewer:  "Bin zum ersten Mal hier!"
→ Twitch Chat:   [YT] NewFan: Bin zum ersten Mal hier!
```

Beide Communities können miteinander kommunizieren — egal auf welcher Plattform sie zuschauen.

!!! tip "YouTube Quota beachten"
    CrossChat verbraucht YouTube API Quota. Bei sehr aktivem Chat kann das Limit erreicht werden. Details unter [YouTube Quota](../integrationen/youtube.md).
