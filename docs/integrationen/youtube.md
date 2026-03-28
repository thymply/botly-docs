---
title: YouTube
description: YouTube API Integration, PubSubHubbub und automatische Live-Erkennung.
---

# YouTube Integration

Wie Botly YouTube-Livestreams erkennt, die API nutzt und Quota-sparend arbeitet.

## Verbindung

Botly nutzt **Google OAuth 2.0** für die YouTube-Verbindung. Du autorisierst Botly bei der Anmeldung.

## Live-Erkennung

Botly erkennt YouTube-Livestreams über **PubSubHubbub** (WebSub):

1. YouTube sendet eine Push-Benachrichtigung wenn ein neues Video/Stream startet
2. Botly prüft per API ob es ein Livestream ist (1 Unit)
3. Während des Streams: Offline-Check alle 10 Minuten (1 Unit)

!!! info "Kein Polling"
    Botly pollt **nie** die YouTube Search API (100 Units pro Aufruf). Stattdessen nutzt es kostenlose Push-Benachrichtigungen.

## API Quota

YouTube Data API v3 hat ein Tagesbudget von **10.000 Units**.

| Aktion | API Call | Units |
|--------|---------|-------|
| Kanal per @Handle auflösen | channels.list | 1 |
| Video/Livestream prüfen | videos.list | 1 |
| Noch live? (Offline-Check) | videos.list | 1 |

Bei 5 Streamern: ca. **750 Units/Tag** — weit unter dem Limit.

!!! warning "Keine Search API"
    Botly nutzt **nie** die YouTube `search` API (100 Units pro Request). Alle Features basieren auf PubSubHubbub + `videos.list` (1 Unit).

## YouTube API Key

Für CrossChat und einige Features brauchst du einen **YouTube API Key**:

1. Gehe zur [Google Cloud Console](https://console.cloud.google.com)
2. Erstelle ein Projekt
3. Aktiviere die **YouTube Data API v3**
4. Erstelle einen **API Key**
5. Trage ihn in der Desktop App ein

Eine ausführliche Anleitung findest du als PDF im Dashboard unter **Tools**.
