---
title: Variablen-Referenz
description: Alle verfügbaren Variablen für Commands, Alerts und Action-Chains.
---

# Variablen-Referenz

Vollständige Liste aller Variablen die du in Commands, Alerts und Action-Chains verwenden kannst.

## Twitch-Events

| Variable | Beschreibung | Verfügbar in |
|----------|-------------|-------------|
| `{username}` / `$(user)` | Anzeigename des Users | Alle Events |
| `{user_id}` | Twitch User-ID | Alle Events |
| `{channel}` / `$(channel)` | Kanalname | Alle Events |
| `{game}` / `$(game)` | Aktuelle Twitch-Kategorie | Alle Events |
| `{title}` / `$(title)` | Stream-Titel | Alle Events |
| `{viewers}` | Aktuelle Zuschauerzahl | Alle Events |
| `{uptime}` / `$(uptime)` | Stream-Dauer | Alle Events |
| `{tier}` | Abo-Stufe (1, 2, 3) | Sub, Gift Sub |
| `{months}` | Gesamte Abo-Monate | Sub |
| `{streak}` | Abo-Streak | Sub |
| `{message}` | Benutzer-Nachricht | Sub, Bits, Donation |
| `{amount}` | Betrag / Anzahl | Bits, Donation, Raid |
| `{followage}` / `$(followage)` | Follower-Dauer | Follow, Commands |
| `{watchtime}` / `$(watchtime)` | Zuschauzeit | Commands |
| `{count}` / `$(count)` | Aufrufzähler des Commands | Commands |
| `{args}` / `$(args)` | Text nach dem Command | Commands |

!!! info "Zwei Schreibweisen"
    Variablen funktionieren in beiden Schreibweisen: `{variable}` und `$(variable)`. Nutze was dir besser gefällt.

## YouTube-Events

| Variable | Beschreibung | Verfügbar in |
|----------|-------------|-------------|
| `{username}` | YouTube-Kanalname | Alle Events |
| `{amount}` | Super Chat Betrag | Super Chat |
| `{currency}` | Währung | Super Chat |
| `{message}` | Nachrichtentext | Super Chat, Chat |
| `{level}` | Mitgliedschafts-Level | New Member |

## Discord-Events

| Variable | Beschreibung | Verfügbar in |
|----------|-------------|-------------|
| `{user}` | @Mention des Users | Member Join, Reaction |
| `{username}` | Name ohne Mention | Member Join |
| `{server}` | Server-Name | Alle Events |
| `{channel}` | Kanal-Name | Reaction |
| `{membercount}` | Mitgliederzahl | Member Join |

## Donation-Events

| Variable | Beschreibung | Verfügbar in |
|----------|-------------|-------------|
| `{username}` | Name des Spenders | Alle Anbieter |
| `{amount}` | Spenden-Betrag | Alle Anbieter |
| `{currency}` | Währung (EUR, USD, etc.) | Alle Anbieter |
| `{message}` | Spenden-Nachricht | Alle Anbieter |
| `{provider}` | Anbieter-Name | Alle Anbieter |

## Counter-Variablen

| Variable | Beschreibung |
|----------|-------------|
| `{value}` | Aktueller Zählerwert |
| `{amount}` | Um wie viel geändert wurde |
| `{name}` | Name des Counters |

## System-Variablen

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `{streamer}` | Dein Kanalname | `thymply_` |
| `{date}` | Aktuelles Datum | `28.03.2026` |
| `{time}` | Aktuelle Uhrzeit | `14:30` |
| `{random}` | Zufallszahl (1-100) | `42` |
