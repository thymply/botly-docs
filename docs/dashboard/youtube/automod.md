---
title: AutoMod (YouTube)
description: Automatische Chat-Moderation für YouTube-Livestreams.
---

# AutoMod (YouTube)

Schütze deinen YouTube-Chat mit den gleichen Filtern die du von Twitch kennst.

## Verfügbare Filter

YouTube AutoMod nutzt die gleichen Filter wie Twitch:

- **Spam-Filter** — Zu viele Nachrichten in kurzer Zeit
- **Link-Filter** — URLs ohne Whitelist
- **Caps-Filter** — Zu viele Großbuchstaben
- **Geblockte Begriffe** — Wortliste

## Unterschiede zu Twitch

| Feature | Twitch | YouTube |
|---------|--------|---------|
| Timeout | Ja (X Sekunden) | Nur Nachricht löschen |
| Whisper/DM | Ja | Nein |
| Emote-Erkennung | Twitch Emotes + Emoji | Nur Emoji |
| !permit | Ja | Ja (Mention statt Whisper) |

!!! warning "Kein Timeout auf YouTube"
    YouTube Live Chat hat keine Timeout-Funktion. Alle Timeout-Aktionen werden zu "Nachricht löschen" umgewandelt.

## Einrichtung

Die YouTube AutoMod-Einstellungen werden separat von Twitch gespeichert. Du kannst für jede Plattform eigene Filter-Schwellwerte setzen.

1. Wähle **YouTube Bot** → **AutoMod**
2. Konfiguriere die Filter wie gewünscht
3. Klicke auf **Speichern**
