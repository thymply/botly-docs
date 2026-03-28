---
title: Live-Ankündigungen
description: Automatische Discord-Benachrichtigungen wenn du auf Twitch oder YouTube live gehst.
---

# Live-Ankündigungen

Dein Discord-Server erfährt automatisch wenn du auf Twitch oder YouTube live gehst — mit anpassbarer Nachricht, Embed und optionalem Live-Rolle.

## Einrichtung

1. Gehe zu **Discord** → Server → **Live-Ankündigungen**
2. Wähle den **Ankündigungs-Kanal** (z.B. #live)
3. Füge **Streamer** hinzu (Twitch und/oder YouTube)
4. Passe die **Nachricht** und das **Embed** an
5. Speichern

## Streamer hinzufügen

### Twitch-Streamer

Gib den Twitch-Login-Namen ein. Botly nutzt EventSub um Live-Events in Echtzeit zu erkennen.

### YouTube-Streamer

Gib die YouTube-Kanal-URL oder den @Handle ein. Botly nutzt PubSubHubbub für Push-Benachrichtigungen.

## Nachricht anpassen

Verfügbare Variablen:

| Variable | Beschreibung |
|----------|-------------|
| `{channel}` | Kanalname |
| `{game}` | Aktuelle Kategorie (Twitch) |
| `{title}` | Stream-Titel |
| `{url}` | Link zum Stream |
| `{viewers}` | Zuschauerzahl |

## Kombinierte Ankündigung (Twitch + YouTube)

Wenn du auf beiden Plattformen gleichzeitig streamst (Simulcast), kann Botly eine **kombinierte Nachricht** senden statt zwei separate.

### Einrichtung

1. Trage bei Twitch- und YouTube-Streamer die gleiche **Discord-User-ID** ein
2. Konfiguriere die **kombinierte Nachricht** mit Variablen für beide Plattformen
3. Setze die **Verzögerung** (wie lange Botly wartet bevor es die zweite Plattform als "nicht live" betrachtet)

Wenn die erste Plattform live geht, wartet Botly die eingestellte Verzögerung ab. Geht die zweite Plattform in dieser Zeit auch live, wird eine kombinierte Nachricht gesendet. Andernfalls eine normale.

!!! info "Nachricht wird editiert"
    Wenn die erste Plattform bereits eine Nachricht gesendet hat und die zweite Plattform nachzieht, wird die bestehende Nachricht zu einer kombinierten Nachricht **editiert** — kein Doppelpost.

## Offline-Verhalten

Wenn der Stream endet:

1. Die Ankündigung wird zu einem **Offline-Embed** editiert (dunkelgrau, "ist offline")
2. Optional: Nachricht wird nach X Minuten **automatisch gelöscht**

Die Einstellung "Nachricht löschen nach (Min., 0=nie)" steuert ob und wann die Nachricht verschwindet.

## Live-Rolle

Optional: Vergib automatisch eine Discord-Rolle wenn du live gehst. Mitglieder mit dieser Rolle werden z.B. im Chat hervorgehoben.

!!! info "Free-Plan: max. 1 Streamer"
    Im Free-Plan kannst du einen Streamer pro Plattform konfigurieren. Ab Pro gibt es kein Limit.
