---
title: Variablen-Referenz
description: Alle verfügbaren Variablen für Commands, Nachrichten und Templates.
---

# Variablen-Referenz

Variablen werden in geschweiften Klammern geschrieben: `{variable}` oder `{variable:parameter}`.
Du kannst sie in Commands, Willkommensnachrichten, AutoMod-Warnungen und Live-Ankündigungen verwenden.

## Command-Variablen

### Basis (Free)

| Variable | Beschreibung | Beispiel-Eingabe | Beispiel-Ausgabe |
|----------|-------------|-----------------|-----------------|
| `{user}` | Dein Anzeigename | — | `Night` |
| `{channel}` | Kanalname | — | `die_prototypen` |
| `{touser}` | Erwähnter User oder du selbst | `!hug @Night` → `Night` | `!hug` → dein Name |
| `{query}` | Alles nach dem Command | `!wiki Python Programmierung` | `Python Programmierung` |
| `{userlevel}` | Deine Rolle im Chat | — | `moderator`, `subscriber`, `everyone` |
| `{count}` | Aufrufzähler (persistent) | — | `42` (zählt immer weiter) |
| `{count_stream}` | Aufrufzähler (pro Stream) | — | `7` (resettet bei Stream-Start) |

**Beispiele:**

```
!hug → {user} umarmt {touser}! ({count} Umarmungen insgesamt)
!rank → {user}, du bist {userlevel} in diesem Chat.
!fluchen → Der Streamer hat {count_stream} Mal geflucht in diesem Stream!
```

### Zeit (Free)

| Variable | Beschreibung | Beispiel-Eingabe | Beispiel-Ausgabe |
|----------|-------------|-----------------|-----------------|
| `{time}` | Aktuelle Uhrzeit (CET) | — | `14:30` |
| `{time:Zone}` | Uhrzeit in Zeitzone | `{time:America/New_York}` | `8:30` |
| `{countdown:Datum}` | Zeit bis zu einem Datum | `{countdown:Dec 25 2026 00:00}` | `3 Tage, 5 Stunden, 20 Minuten` |
| `{countup:Datum}` | Zeit seit einem Datum | `{countup:Jan 01 2024}` | `2 Jahre, 3 Monate, 1 Tag` |

**Unterstützte Zeitzonen:** `CET`, `EST`, `PST`, `GMT`, `JST` oder IANA-Format wie `Europe/Berlin`, `America/New_York`.

**Beispiele:**

```
!zeit → Es ist {time} Uhr in Deutschland und {time:America/New_York} in New York.
!weihnachten → Noch {countdown:Dec 25 2026 00:00} bis Weihnachten!
!streaming → Ich streame seit {countup:Mar 15 2023} auf Twitch!
```

### Stream (Free)

| Variable | Beschreibung | Beispiel-Ausgabe |
|----------|-------------|-----------------|
| `{uptime}` | Stream-Laufzeit | `2h 35m` |
| `{title}` | Aktueller Stream-Titel | `Chill-Stream mit Community` |
| `{game}` | Aktuelle Kategorie/Spiel | `Just Chatting` |
| `{followage}` | Wie lange du dem Kanal folgst (nur Twitch) | `1 Jahr, 3 Monate` |
| `{watchtime}` | Deine Zuschauzeit in dieser Session | `45m` |

**Beispiele:**

```
!uptime → {channel} streamt seit {uptime} — {game}: {title}
!followage → {user} folgt seit {followage}!
```

### Extern (Pro/Premium) :material-crown:{ .pro-badge }

Diese Variablen sind nur für **Pro** und **Premium** Nutzer verfügbar. Free-User sehen `[Pro erforderlich]`.

| Variable | Beschreibung | API |
|----------|-------------|-----|
| `{weather:Ort}` | Aktuelles Wetter | Open-Meteo (kostenlos) |
| `{twitch:User}` | Twitch-Profil-Info | Twitch API |
| `{steam:User}` | Steam-Profil-Info | Steam Web API |
| `{urlfetch:URL}` | Externe API aufrufen (Text) | HTTP GET |
| `{urlfetch_json:URL:pfad}` | Externe API aufrufen (JSON-Feld) | HTTP GET + JSON |

#### {weather:Ort}

```
!wetter → {weather:Berlin}
→ "Wetter in Berlin: 18°C, Bewölkt, Wind 12 km/h"
```

#### {twitch:User}

```
!check → {twitch:thymply}
→ "thymply streamt Just Chatting — Chill Stream" oder "thymply ist offline"
```

#### {steam:User}

```
!steam → {steam:night}
→ "Night spielt Counter-Strike 2" oder "Night ist Online auf Steam"
```

!!! info "Steam API Key"
    Für Steam-Variablen muss ein Steam Web API Key konfiguriert sein.

#### {urlfetch:URL}

Ruft eine externe URL auf und gibt die Antwort als Text zurück.

```
!joke → {urlfetch:https://api.example.com/random-joke}
→ "Warum können Geister so schlecht lügen? Weil man durch sie hindurchsieht."
```

- Nur HTTPS-URLs erlaubt
- Maximal 400 Zeichen Antwort
- Timeout: 3 Sekunden
- Rate-Limit: 1 Aufruf pro 5 Sekunden pro Command

#### {urlfetch_json:URL:pfad}

Wie `{urlfetch}`, aber parst die JSON-Antwort und gibt ein bestimmtes Feld zurück.

```
!joke → {urlfetch_json:https://api.example.com/jokes/random:joke.text}
→ "Warum können Geister so schlecht lügen?"
```

Der Pfad nutzt Punkt-Notation mit Array-Unterstützung:

- `joke.text` → `{"joke": {"text": "..."}}`
- `data.results[0].name` → `{"data": {"results": [{"name": "..."}]}}`

---

## Nachrichten-Variablen

Diese Variablen stehen in Willkommensnachrichten, AutoMod-Warnungen und Live-Ankündigungen zur Verfügung.

### Willkommen/Verabschiedung

| Variable | Beschreibung |
|----------|-------------|
| `{user}` | @Mention des Users |
| `{username}` | Name ohne Mention |
| `{server}` | Server-Name |
| `{membercount}` | Aktuelle Mitgliederzahl |

### AutoMod-Warnungen

| Variable | Beschreibung |
|----------|-------------|
| `{user}` | @Mention des Users |
| `{username}` | Name ohne Mention |

### Live-Ankündigungen (Twitch/YouTube)

| Variable | Beschreibung |
|----------|-------------|
| `{user}` | Streamer-Name |
| `{channel}` | Kanalname |
| `{title}` | Stream-Titel |
| `{game}` | Spiel/Kategorie |
| `{url}` | Link zum Stream |
| `{viewers}` | Zuschauerzahl |

### Counter-Nachrichten

| Variable | Beschreibung |
|----------|-------------|
| `{count}` | Aktueller Zählerwert |
| `{name}` | Name des Counters |
| `{game}` | Zugeordnetes Spiel |
| `{user}` | Aufrufender User |
| `{amount}` | Änderungsbetrag |

### Duplikat-Erkennung

| Variable | Beschreibung |
|----------|-------------|
| `{mention}` | @Mention des Users |
| `{game}` | Spielname |
| `{original}` | Originaler Vorschlag |
| `{count}` | Wie oft vorgeschlagen |
| `{link}` | Link zum Original |

### Temp Voice Channel Namen

!!! info "Kein @Mention"
    Im Temp-Voice-Kontext erzeugt `{user}` **keinen** @Mention — anders als in Willkommensnachrichten. Alle Variablen werden als reiner Text eingesetzt, da Discord keine Mentions in Kanalnamen erlaubt.

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
| `Gaming mit {user}` | `Gaming mit Thymply_` |

---

## Plattform-Unterschiede

### `{user}` je nach Kontext

| Kontext | Wert von `{user}` | Pingt den User? |
|---------|-------------------|:---------------:|
| **Twitch Command** | Display Name (`Thymply_`) | Nein |
| **YouTube Command** | Autorenname | Nein |
| **Discord Welcome** | @Mention (`@Thymply_`) | **Ja** |
| **Discord AutoMod** | @Mention (`@Thymply_`) | **Ja** |
| **Discord Temp Voice** | Display Name (`Thymply_`) | Nein |

### `{followage}` und `{watchtime}`

| Variable | Twitch | YouTube |
|----------|--------|---------|
| `{followage}` | Follow-Dauer (`1 Jahr, 3 Monate`) | `[Nur Twitch]` |
| `{watchtime}` | Session-Zuschauzeit | Session-Zuschauzeit |

### YouTube-Kompatibilität

Alle Free-Tier Command-Variablen funktionieren auch auf YouTube — mit Ausnahme von `{followage}` (gibt `[Nur Twitch]` zurück). Pro/Premium-Variablen wie `{weather}`, `{urlfetch}` und `{steam}` funktionieren plattformübergreifend.
