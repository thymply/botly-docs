---
title: AutoMod (Twitch)
description: Automatische Chat-Moderation — Spam, Links, Caps, Emotes und mehr filtern.
---

# AutoMod (Twitch)

AutoMod schützt deinen Chat automatisch vor Spam, unerwünschten Links, Caps-Lock und mehr. Alle Filter sind einzeln konfigurierbar.

## Übersicht der Filter

| Filter | Was wird erkannt | Standard |
|--------|-----------------|----------|
| **Spam-Filter** | Zu viele Nachrichten in kurzer Zeit | An |
| **Doppelte Nachrichten** | Gleiche Nachricht wiederholt | Aus |
| **Zeichen-Wiederholung** | AAAAAAA oder !!!!!!! | Aus |
| **Link-Filter** | URLs ohne Whitelist | An |
| **Caps-Filter** | ZU VIELE GROßBUCHSTABEN | An |
| **Emote-Filter** | Emote-Spam | Aus |

## Spam-Filter

Erkennt User die zu viele Nachrichten in kurzer Zeit senden.

| Einstellung | Beschreibung | Standard |
|------------|-------------|---------|
| Max. Nachrichten | Nachrichten pro Zeitfenster | 5 |
| Zeitfenster | Sekunden | 10 |
| Aktion | Löschen / Timeout 5s-10min | Timeout 5 Min. |
| Ausnahme ab | Ab welchem Level ignorieren | VIP |

## Doppelte Nachrichten

Erkennt wenn ein User die gleiche Nachricht mehrfach postet.

| Einstellung | Standard |
|------------|---------|
| Max. gleiche Nachrichten | 3 |
| Zeitfenster | 30 Sekunden |

## Link-Filter

Filtert URLs die nicht auf der Whitelist stehen.

| Einstellung | Beschreibung | Standard |
|------------|-------------|---------|
| Aktion | Löschen / Timeout | Timeout 5 Min. |
| Ausnahme ab | User-Level | VIP |
| Whitelist | Erlaubte Domains (eine pro Zeile) | youtube.com, twitch.tv, discord.gg |

### !permit System

Mods können mit `!permit @username` einem User erlauben, für 2 Minuten Links zu posten:

```
Mod:     !permit @viewer42
Bot:     @viewer42 darf jetzt für 2 Minuten Links posten.
Viewer:  Schaut euch dieses Video an: https://youtube.com/watch?v=...
         (wird NICHT gelöscht)
```

Die Permit-Dauer ist konfigurierbar (Standard: 120 Sekunden). Während der Dauer darf der User beliebig viele Links posten.

!!! warning "Twitch AutoMod Konflikt"
    Twitch hat einen eigenen Link-Filter ("Links von unbekannten Nutzern blockieren"). Wenn dieser aktiv ist, funktioniert `!permit` nur für Botlys Filter — Twitch blockiert trotzdem. Für volle Kontrolle: Twitchs Link-Filter deaktivieren und nur Botlys nutzen.

## Caps-Filter

Erkennt Nachrichten mit zu vielen Großbuchstaben.

| Einstellung | Beschreibung | Standard |
|------------|-------------|---------|
| Max. Großbuchstaben | Prozentual | 70% |
| Min. Nachrichtenlänge | Kurze Nachrichten ignorieren | 10 Zeichen |
| Aktion | Löschen / Timeout | Timeout 5 Min. |
| Ausnahme ab | User-Level | VIP |

## Emote-Filter

Erkennt Emote-Spam — zu viele Emotes in einer Nachricht.

| Einstellung | Standard |
|------------|---------|
| Max. Emotes pro Nachricht | 10 |
| Ausnahme ab | VIP |
| Aktion | Timeout 30 Sek. |

## Ausnahmen (User-Level)

Jeder Filter hat eine **Ausnahme-Stufe**. User auf oder über diesem Level werden vom Filter ignoriert:

```
Keine Ausnahme → Regular → Subscriber → VIP → Moderator
```

Moderatoren und Broadcaster werden **immer** ausgenommen.

## Geblockte Begriffe

Unter dem AutoMod-Bereich findest du die **Wortliste**. Nachrichten die einen geblockten Begriff enthalten werden automatisch gelöscht.

!!! tip "Beste Praxis"
    Starte mit den Standard-Einstellungen und passe sie an deinen Chat an. Ein kleiner Chat braucht weniger aggressive Filter als ein großer.
