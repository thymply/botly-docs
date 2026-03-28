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

## Voraussetzungen

- **Pro-Plan oder höher** (oder Desktop Lifetime)
- **YouTube API Key** — [Anleitung als PDF](../integrationen/youtube.md)
- **Desktop App** läuft und ist verbunden

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
    YouTube hat ein tägliches API-Quota von 10.000 Units. CrossChat nutzt die YouTube Live Chat API (kostengünstig), aber bei sehr aktivem Chat kann das Quota erreicht werden. Siehe [YouTube Quota](../integrationen/youtube.md).

!!! info "Nur während Livestream"
    CrossChat funktioniert nur wenn beide Plattformen gleichzeitig live sind. Im Offline-Modus ist die Bridge inaktiv.
