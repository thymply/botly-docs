---
title: CrossChat Bridge
description: Chat-Nachrichten zwischen Twitch und YouTube in Echtzeit synchronisieren.
---

# CrossChat Bridge

Die CrossChat Bridge leitet Chat-Nachrichten zwischen Twitch und YouTube weiter — perfekt für Simulcast-Streamer.

## Konzept

Wenn du auf Twitch und YouTube gleichzeitig streamst, haben beide Chats normalerweise keine Verbindung. CrossChat ändert das:

```
Twitch Viewer:  "Geiler Stream!"
→ YouTube Chat: [Twitch] CoolViewer: Geiler Stream!

YouTube Viewer: "Danke für den Content!"
→ Twitch Chat:  [YT] YouTubeUser: Danke für den Content!
```

!!! info "Nur Twitch und YouTube"
    CrossChat verbindet nur Twitch und YouTube. Discord ist **nicht** Teil von CrossChat — dafür gibt es die [Live-Ankündigungen](../dashboard/discord/live-ankuendigungen.md).

## Voraussetzungen

- **Pro-Plan oder höher** (oder Desktop Lifetime)
- **YouTube API Key** (wird immer vom User gestellt)
- **Desktop App** läuft und ist verbunden

## YouTube API Key einrichten

Du brauchst einen eigenen YouTube API Key. Botly stellt **keinen** Key — so wird dein API-Quota nicht durch andere User verbraucht.

**Kurzfassung:**

1. Öffne die [Google Cloud Console](https://console.cloud.google.com)
2. Erstelle ein neues Projekt
3. Aktiviere die **YouTube Data API v3**
4. Erstelle einen **API Key** unter "Anmeldedaten"
5. Trage den Key in der Desktop App → **CrossChat** ein

!!! tip "PDF-Anleitung"
    Eine ausführliche Schritt-für-Schritt Anleitung findest du als PDF im Dashboard unter **Tools** → **YouTube API Key Anleitung**.

## Einrichtung

1. Gehe zu **CrossChat** in der Desktop App
2. Trage deinen **YouTube API Key** ein
3. Konfiguriere das **Nachrichtenformat**
4. Aktiviere die **Bridge**

## Nachrichtenformat anpassen

| Variable | Beschreibung |
|----------|-------------|
| `{user}` | Username des Absenders |
| `{message}` | Nachrichtentext |
| `{platform}` | Quell-Plattform (Twitch/YouTube) |

Standard: `[{platform}] {user}: {message}`

## Einschränkungen

!!! warning "YouTube API Quota"
    YouTube hat ein tägliches API-Quota von 10.000 Units. CrossChat ist optimiert, aber bei sehr aktivem Chat kann das Quota erreicht werden. Siehe [YouTube Quota](../integrationen/youtube.md).

!!! info "Nur während Livestream"
    CrossChat funktioniert nur wenn beide Plattformen gleichzeitig live sind.
