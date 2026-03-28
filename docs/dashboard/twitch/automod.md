---
title: AutoMod (Twitch)
description: Automatische Chat-Moderation — Spam, Links, Caps, Emotes und mehr filtern.
---

# AutoMod (Twitch)

AutoMod schützt deinen Chat automatisch vor Spam, unerwünschten Links, Caps-Lock und mehr. Alle Filter sind auf einen Blick konfigurierbar — mit Aktionen und Ausnahmen pro Filter.

## Übersicht

| Filter | Was wird erkannt | Standard |
|--------|-----------------|----------|
| **Caps-Filter** | Zu viele Großbuchstaben | An |
| **Emote-Filter** | Emote-Spam | Aus |
| **Spam-Filter** | Nachrichtenflut + Duplikate | An |
| **Link-Filter** | URLs ohne Whitelist | An |

Alle Filter werden in einem 2-Spalten Grid angezeigt — alles gleichzeitig sichtbar, kein Aufklappen nötig.

### Aktionen pro Filter

Jeder Filter hat eine eigene Aktionsauswahl (Segmented Control):

| Aktion | Beschreibung |
|--------|-------------|
| **Löschen** | Nachricht wird sofort gelöscht |
| **30s** | 30 Sekunden Timeout |
| **5m** | 5 Minuten Timeout |
| **10m** | 10 Minuten Timeout |

### Ausnahmen pro Filter

Jeder Filter hat eine Ausnahme-Stufe. User auf oder über diesem Level werden ignoriert:

```
Alle → Subscriber → VIP → Moderator
```

Moderatoren und Broadcaster werden immer ausgenommen.

## Caps-Filter

| Einstellung | Standard |
|------------|---------|
| Max. Großbuchstaben (Slider) | 70% |
| Min. Nachrichtenlänge | 10 Zeichen |
| Aktion | 5m |
| Ausnahme ab | VIP |

## Emote-Filter

Erkennt Emote-Spam — Twitch-Emotes und Unicode-Emojis.

| Einstellung | Standard |
|------------|---------|
| Max. Emotes pro Nachricht | 10 |
| Aktion | 30s |
| Ausnahme ab | VIP |

## Spam-Filter

| Einstellung | Standard |
|------------|---------|
| Max. Nachrichten | 5 |
| Zeitfenster | 10 Sekunden |
| Aktion | 5m |
| Ausnahme ab | VIP |

Zusätzlich im Spam-Filter:

- **Doppelte Nachrichten** — Max. 3 gleiche Nachrichten in 30 Sekunden
- **Zeichen-Wiederholung** — Max. 15 gleiche Zeichen hintereinander (z.B. AAAAAAA)

## Link-Filter

| Einstellung | Standard |
|------------|---------|
| Aktion | 5m |
| Ausnahme ab | VIP |
| Whitelist | youtube.com, twitch.tv, clips.twitch.tv |
| !permit Dauer | 120 Sekunden |

### Whitelist

Domains werden als Tags angezeigt. Klicke **+ Domain** um neue hinzuzufügen (mehrere pro Zeile). Standard-Domains: youtube.com, twitch.tv, clips.twitch.tv.

### !permit

Mods können mit `!permit @username` einem User temporär Links erlauben:

```
Mod:     !permit @viewer42
Bot:     @viewer42 darf jetzt für 2 Minuten Links posten.
```

!!! warning "Twitch AutoMod Konflikt"
    Twitch hat einen eigenen Link-Filter. Wenn dieser aktiv ist, funktioniert `!permit` nur für Botlys Filter — Twitch blockiert trotzdem. Wir empfehlen Twitchs Link-Filter zu deaktivieren und stattdessen Botlys Filter mit Whitelist und !permit zu nutzen.

## Gesperrte Begriffe

Unter den Filtern — volle Breite. Begriffe als rote Tags, Zähler-Badge, **+ Hinzufügen** öffnet Modal (mehrere pro Zeile).

!!! tip "Beste Praxis"
    Starte mit den Standard-Einstellungen und passe sie an deinen Chat an. Ein kleiner Chat braucht weniger aggressive Filter als ein großer.
