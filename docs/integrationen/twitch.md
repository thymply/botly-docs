---
title: Twitch
description: Twitch-Integration — Scopes, EventSub und Bot-Verbindung.
---

# Twitch Integration

Wie Botly sich mit Twitch verbindet und welche Berechtigungen benötigt werden.

## Verbindung

Botly verbindet sich über **OAuth 2.0** mit Twitch. Bei der Autorisierung wirst du gefragt welche Berechtigungen du Botly gibst.

## Scopes (Berechtigungen)

Diese Berechtigungen fragt Botly ab, wenn du deinen Twitch-Kanal oder ein Bot-Konto verbindest:

| Scope | Wofür |
|-------|-------|
| `chat:read` | Chat-Nachrichten lesen |
| `chat:edit` | Chat-Nachrichten senden |
| `moderator:manage:banned_users` | Timeout und Ban |
| `moderator:manage:chat_messages` | Nachrichten löschen |
| `moderator:manage:chat_settings` | Chat-Einstellungen ändern |
| `moderator:read:chatters` | Liste der Zuschauer im Chat lesen |
| `moderator:read:followers` | Follows empfangen und Follow-Dauer lesen |
| `channel:read:ads` | Werbepausen erkennen (Ankündigung im Chat) |
| `channel:read:redemptions` | Kanalpunkte-Einlösungen empfangen |
| `channel:manage:redemptions` | Kanalpunkte-Belohnungen anlegen, ändern und löschen |
| `channel:read:subscriptions` | Abos, Resubs und Gifted Subs empfangen |
| `bits:read` | Bits empfangen |
| `channel:read:hype_train` | Hype Trains empfangen |
| `channel:read:goals` | Kanal-Ziele empfangen |
| `channel:read:polls` | Umfragen empfangen |
| `channel:read:predictions` | Vorhersagen empfangen |
| `channel:read:charity` | Spendenaktionen empfangen |
| `moderator:read:shoutouts` | Shoutouts empfangen |
| `channel:manage:vips` | VIP vergeben und entziehen |
| `moderator:manage:shield_mode` | Shield Mode |
| `clips:edit` | Clips erstellen ([Auto-Clip](../dashboard/twitch/auto-clip.md)), nur beim Twitch-Kanal, nicht beim Bot-Konto |

Beim Login mit Twitch fragt Botly nur die Berechtigungen für die Anmeldung ab (`user:read:email`, `chat:read`, `chat:edit`, `channel:read:redemptions`, `channel:manage:redemptions`). Die übrigen kommen erst, wenn du deinen Twitch-Kanal verbindest.

!!! tip "Neue Berechtigung"
    Kommt eine Berechtigung neu hinzu, gilt sie erst, wenn du deinen Twitch-Kanal neu verbindest. Fehlt `clips:edit` und ist Auto-Clip eingeschaltet, zeigt dir Botly im Bereich Auto-Clip den Hinweis **Neu verbinden**.

## EventSub

Botly nutzt **Twitch EventSub** für Echtzeit-Events:

- Stream online/offline
- Follows, Subs, Bits, Raids
- Channel Points Einlösungen
- Hype Trains

EventSub liefert Events in unter 1 Sekunde — schneller als das alte PubSub-System.

## Zwei Account-Typen

Du kannst Botly mit einem **Bot-Konto** oder mit deinem **Streamer-Account** nutzen:

| | Bot-Konto | Streamer-Account |
|---|---|---|
| Chat-Name | Separater Bot-Name | Dein eigener Name |
| Einrichtung | Zwei OAuth-Verbindungen | Eine OAuth-Verbindung |
| Empfehlung | Für professionelles Setup | Für den Anfang |

!!! info "Bot-Konto ab Pro"
    Ein eigenes Bot-Konto oder den Botly-Bot (myBotly) kannst du ab dem Pro-Plan im Bereich **Bot-Konto** einrichten. Im Free-Plan nutzt du Botly mit deinem Streamer-Account.
