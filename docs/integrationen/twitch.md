---
title: Twitch
description: Twitch-Integration — Scopes, EventSub und Bot-Verbindung.
---

# Twitch Integration

Wie Botly sich mit Twitch verbindet und welche Berechtigungen benötigt werden.

## Verbindung

Botly verbindet sich über **OAuth 2.0** mit Twitch. Bei der Autorisierung wirst du gefragt welche Berechtigungen du Botly gibst.

## Scopes (Berechtigungen)

| Scope | Wofür |
|-------|-------|
| `chat:read` | Chat-Nachrichten lesen |
| `chat:edit` | Chat-Nachrichten senden |
| `channel:read:subscriptions` | Abo-Events empfangen |
| `bits:read` | Bits-Events empfangen |
| `channel:manage:broadcast` | Titel & Kategorie ändern |
| `clips:edit` | Clips erstellen |
| `moderation:read` | Moderations-Events |
| `moderator:manage:chat_messages` | Nachrichten löschen |
| `moderator:manage:banned_users` | Timeout/Ban |

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
