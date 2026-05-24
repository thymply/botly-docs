---
title: Variablen-Referenz
description: Alle verfügbaren Variablen für Commands, Nachrichten und Templates.
---

# Variablen-Referenz

Variablen werden in geschweiften Klammern geschrieben: `{variable}` oder `{variable:parameter}`.
Du kannst sie in Commands, Willkommensnachrichten, AutoMod-Warnungen, Live-Ankündigungen und mehr verwenden.

[:flag_gb: English version](variablen-en.md)

---

## Command-Variablen (Twitch & YouTube)

### Basis (Free)

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{user}` | Dein Anzeigename | `Thymply_` |
| `{channel}` | Kanalname | `die_prototypen` |
| `{touser}` | Erwähnter User oder du selbst | `!hug @Night` -> `Night` |
| `{query}` | Alles nach dem Command | `!wiki Python` -> `Python` |
| `{userlevel}` | Deine Rolle im Chat | `moderator`, `subscriber`, `everyone` |
| `{count}` | Aufrufzähler (persistent) | `42` (zählt immer weiter) |
| `{count_stream}` | Aufrufzähler (pro Stream) | `7` (resettet bei Stream-Start) |

**Beispiele:**

```
!hug -> {user} umarmt {touser}! ({count} Umarmungen insgesamt)
!rank -> {user}, du bist {userlevel} in diesem Chat.
!fluchen -> Der Streamer hat {count_stream} Mal geflucht in diesem Stream!
```

### Zeit (Free)

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{time}` | Aktuelle Uhrzeit (CET) | `14:30` |
| `{time:Zone}` | Uhrzeit in Zeitzone | `{time:America/New_York}` -> `8:30` |
| `{countdown:Datum}` | Zeit bis zu einem Datum | `3 Tage, 5 Stunden, 20 Minuten` |
| `{countup:Datum}` | Zeit seit einem Datum | `2 Jahre, 3 Monate, 1 Tag` |
| `{date}` | Aktuelles Datum (DD.MM.YYYY) | `24.05.2026` |
| `{date:FORMAT}` | Datum in bestimmtem Format | `{date:long}` → `24. Mai 2026` |

**Unterstützte Zeitzonen:** `CET`, `EST`, `PST`, `GMT`, `JST` oder IANA-Format wie `Europe/Berlin`, `America/New_York`.

**{date} Formate:**

| Format | Beispiel | Beschreibung |
|--------|---------|-------------|
| `{date}` | `24.05.2026` | Standard (DD.MM.YYYY) |
| `{date:short}` | `24.05.26` | Kurz (DD.MM.YY) |
| `{date:iso}` | `2026-05-24` | ISO 8601 |
| `{date:long}` | `24. Mai 2026` | Ausgeschrieben |
| `{date:weekday}` | `Samstag` | Wochentag |
| `{date:month}` | `Mai 2026` | Monat und Jahr |
| `{date:us}` | `May 24 2026` | US-Format |
| `{date:us_long}` | `May 24, 2026` | US-Format lang |

```
!zeit -> Es ist {time} Uhr in Deutschland und {time:America/New_York} in New York.
!weihnachten -> Noch {countdown:Dec 25 2026 00:00} bis Weihnachten!
!streaming -> Ich streame seit {countup:Mar 15 2023} auf Twitch!
!datum -> Heute ist {date:weekday}, der {date:long}.
```

### Zufall (Free)

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{random.X-Y}` | Zufallszahl zwischen X und Y | `{random.1-100}` → `42` |
| `{random:a\|b\|c}` | Zufälliges Element aus Liste (Pipe-getrennt) | `{random:ja\|nein\|vielleicht}` → `nein` |

```
!8ball -> {random:ja|nein|vielleicht|frag morgen|absolut nicht}
!würfeln -> {user} würfelt eine {random.1-6}!
!choose -> {random:Schere|Stein|Papier}
```

### Stream (Free)

| Variable | Beschreibung | Beispiel-Ausgabe | Plattform |
|----------|-------------|-----------------|-----------|
| `{uptime}` | Stream-Laufzeit | `2h 35m` | Twitch + YouTube |
| `{title}` | Aktueller Stream-Titel | `Chill-Stream mit Community` | Twitch + YouTube |
| `{game}` | Aktuelle Kategorie/Spiel | `Just Chatting` | Twitch + YouTube |
| `{followage}` | Wie lange du dem Kanal folgst | `1 Jahr, 3 Monate` | Nur Twitch |
| `{watchtime}` | Deine Zuschauzeit in dieser Session | `45m` | Twitch + YouTube |

!!! warning "Nur Twitch"
    `{followage}` funktioniert nur auf Twitch. Auf YouTube wird `[Nur Twitch]` angezeigt.

```
!uptime -> {channel} streamt seit {uptime} -- {game}: {title}
!followage -> {user} folgt seit {followage}!
```

### Extern (Pro/Premium) :material-crown:{ .pro-badge }

Diese Variablen sind nur für **Pro** und **Premium** Nutzer verfügbar. Free-User sehen `[Pro erforderlich]`.

| Variable | Beschreibung | API | Cache |
|----------|-------------|-----|-------|
| `{weather:Ort}` | Aktuelles Wetter | Open-Meteo | 10 Min |
| `{twitch:User}` | Twitch-Profil-Info | Twitch API | — |
| `{steam:User}` | Steam-Profil-Info | Steam Web API | — |
| `{urlfetch:URL}` | Externe API aufrufen (Text) | HTTP GET | — |
| `{urlfetch_json:URL:pfad}` | Externe API (JSON-Feld) | HTTP GET + JSON | — |

#### {weather:Ort}

```
!wetter -> {weather:Berlin}
-> "Wetter in Berlin: 18 Grad C, Bewölkt, Wind 12 km/h"
```

#### {twitch:User}

```
!check -> {twitch:thymply}
-> "thymply streamt Just Chatting -- Chill Stream" oder "thymply ist offline"
```

#### {steam:User}

```
!steam -> {steam:night}
-> "Night spielt Counter-Strike 2" oder "Night ist Online auf Steam"
```

!!! info "Steam API Key"
    Für Steam-Variablen muss ein Steam Web API Key in den Einstellungen konfiguriert sein.

#### {urlfetch:URL}

Ruft eine externe URL auf und gibt die Antwort als Text zurück.

```
!joke -> {urlfetch:https://api.example.com/random-joke}
-> "Warum können Geister so schlecht lügen? Weil man durch sie hindurchsieht."
```

- Nur HTTPS-URLs erlaubt
- Maximal 400 Zeichen Antwort
- Timeout: 3 Sekunden
- Rate-Limit: 1 Aufruf pro 5 Sekunden pro Command

#### {urlfetch_json:URL:pfad}

Wie `{urlfetch}`, aber parst die JSON-Antwort und gibt ein bestimmtes Feld zurück.

```
!joke -> {urlfetch_json:https://api.example.com/jokes/random:joke.text}
-> "Warum können Geister so schlecht lügen?"
```

Der Pfad nutzt Punkt-Notation mit Array-Unterstützung:

- `joke.text` -> `{"joke": {"text": "..."}}`
- `data.results[0].name` -> `{"data": {"results": [{"name": "..."}]}}`

---

## Discord Willkommen & Verabschiedung

| Variable | Beschreibung | Beispiel-Ausgabe | Pingt? |
|----------|-------------|-----------------|:------:|
| `{user}` | @Mention des Users | `@Thymply_` | **Ja** |
| `{username}` | Name ohne Mention | `Thymply_` | Nein |
| `{server}` | Server-Name | `Mein Discord Server` | Nein |
| `{membercount}` | Aktuelle Mitgliederzahl | `1337` | Nein |

**Standard-Begrüßung:** `Willkommen auf dem Server, {user}!`

**Standard-Verabschiedung:** `{username} hat den Server verlassen.`

```
Willkommen auf dem Server, {user}! Du bist Mitglied #{membercount} auf {server}!
```

---

## Discord AutoMod-Warnungen

| Variable | Beschreibung | Beispiel-Ausgabe | Pingt? |
|----------|-------------|-----------------|:------:|
| `{user}` | @Mention des Verstoßenden | `@Thymply_` | **Ja** |
| `{username}` | Name ohne Mention | `Thymply_` | Nein |

Verfügbar in: Spam-Warnung, Link-Filter-Warnung, Schimpfwort-Filter-Warnung.

---

## Discord Temp Voice Channel Namen

!!! info "Kein @Mention"
    Im Temp-Voice-Kontext erzeugt `{user}` **keinen** @Mention. Alle Variablen werden als reiner Text eingesetzt, da Discord keine Mentions in Kanalnamen erlaubt.

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `{user}` | Display Name (Server-Nickname oder globaler Name) | `Thymply_` |
| `{username}` | Eindeutiger Discord Handle (immer Kleinbuchstaben) | `thymply_` |
| `{game}` | Aktuelles Spiel des Users (Fallback: `Chillen`) | `Minecraft` |

**Beispiel-Templates:**

| Template | Ergebnis |
|----------|---------|
| `Kanal von {user}` | `Kanal von Thymply_` |
| `{username}'s Raum` | `thymply_'s Raum` |
| `{user} spielt {game}` | `Thymply_ spielt Minecraft` |

---

## Discord Live-Ankündigungen

### Twitch-Stream

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{user}` | Streamer Anzeigename | `Thymply_` |
| `{channel}` | Twitch-Kanalname | `thymply_` |
| `{title}` | Stream-Titel | `Chill-Stream mit Community` |
| `{game}` | Spiel/Kategorie | `Just Chatting` |
| `{url}` | Link zum Stream | `https://twitch.tv/thymply_` |
| `{viewers}` | Zuschauerzahl | `142` |
| `{mention}` | @Mention des Discord-Users | `@Thymply_` |
| `{vod}` | Link zum letzten VOD (falls vorhanden) | `https://twitch.tv/videos/...` |

### YouTube-Stream

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{user}` | Kanalname | `einfruechtchen` |
| `{channel}` | Kanalname | `einfruechtchen` |
| `{title}` | Stream-Titel | `Minecraft Survival` |
| `{url}` | Link zum Stream | `https://youtube.com/watch?v=...` |
| `{viewers}` | Zuschauerzahl | `85` |

### Kombinierte Ankündigung (Twitch + YouTube gleichzeitig)

| Variable | Beschreibung |
|----------|-------------|
| `{streamer}` | Streamer-Name |
| `{twitch_name}` | Twitch-Kanalname |
| `{youtube_name}` | YouTube-Kanalname |
| `{twitch_url}` | Twitch-Stream-URL |
| `{youtube_url}` | YouTube-Stream-URL |
| `{twitch_game}` | Twitch-Kategorie |
| `{title}` | Stream-Titel |
| `{viewers}` | Zuschauerzahl |

---

## Discord Tickets

| Variable | Beschreibung | Beispiel-Ausgabe | Pingt? |
|----------|-------------|-----------------|:------:|
| `{user}` | @Mention des Ticket-Erstellers | `@Thymply_` | **Ja** |

Verfügbar in der Ticket-Begrüßungsnachricht.

---

## Discord Duplikat-Erkennung

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{mention}` | @Mention des Users | `@Thymply_` |
| `{game}` | Spielname | `Minecraft` |
| `{original}` | Wer es zuerst vorgeschlagen hat | `Night` |
| `{count}` | Wie oft vorgeschlagen | `3` |
| `{link}` | Link zum Original-Vorschlag | `https://discord.com/channels/...` |

---

## Discord Counter-Nachrichten

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{count}` | Aktueller Zählerwert | `42` |
| `{name}` | Name des Counters | `Deaths` |
| `{game}` | Zugeordnetes Spiel | `Elden Ring` |
| `{user}` | Aufrufender User | `Thymply_` |
| `{amount}` | Änderungsbetrag | `1` |

---

## Twitch Werbe-Ankündigung

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{duration}` | Werbedauer in Sekunden | `90` |
| `{minutes}` | Werbedauer in Minuten (gerundet) | `1.5` |
| `{type}` | Art der Werbepause | `manuell` oder `automatisch` |

**Nachricht bei Werbebeginn:**
```
Werbepause ({duration}s)! Lehnt euch zurück, bin gleich wieder da!
```

**Vorwarnungen:** In Vorwarnungs-Nachrichten stehen zusätzlich zur Verfügung:

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{seconds}` | Sekunden bis zur Werbung | `30` |
| `{minutes}` | Minuten bis zur Werbung | `0.5` |

---

## Plattform-Übersicht

### `{user}` je nach Kontext

| Kontext | Wert | Pingt? |
|---------|------|:------:|
| **Twitch Command** | Display Name (`Thymply_`) | Nein |
| **YouTube Command** | Autorenname | Nein |
| **Discord Welcome** | @Mention (`@Thymply_`) | **Ja** |
| **Discord AutoMod** | @Mention (`@Thymply_`) | **Ja** |
| **Discord Temp Voice** | Display Name (`Thymply_`) | Nein |
| **Discord Tickets** | @Mention (`@Thymply_`) | **Ja** |
| **Discord Counter** | Aufrufender User | Nein |

### YouTube-Kompatibilität

Alle Free-Tier Command-Variablen funktionieren auch auf YouTube -- mit Ausnahme von `{followage}` (gibt `[Nur Twitch]` zurück). Pro/Premium-Variablen wie `{weather}`, `{urlfetch}` und `{steam}` funktionieren plattformübergreifend.
