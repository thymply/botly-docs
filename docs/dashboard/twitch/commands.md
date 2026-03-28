---
title: Commands
description: Chat-Befehle erstellen, Aliase vergeben, Auto-Timer setzen und Variablen nutzen.
---

# Commands

Commands sind Chat-Befehle auf die dein Bot automatisch antwortet — das Grundgerüst jedes Stream-Bots.

## Übersicht

Die Commands-Seite hat drei Tabs:

- **Custom Commands** — Deine eigenen Befehle mit `!` Prefix
- **Keywords** — Reagieren auf Text ohne `!` (Content-Match)
- **Default Commands** — System-Befehle (`!commands`, `!title`, `!game`, `!uptime`, `!permit`)

## Custom Command erstellen

1. Gehe zu **Twitch Bot** → **Commands**
2. Klicke auf **+ Neuer Command**
3. Fülle das Modal aus:

| Feld | Beschreibung | Beispiel |
|------|-------------|---------|
| **Command** | Befehl mit `!` Prefix | `!discord` |
| **Antwort** | Bot-Antwort mit Variablen | `Unser Discord: discord.gg/...` |
| **Cooldown** | Sekunden zwischen Auslösungen | `10` |
| **User-Level** | Wer darf den Befehl nutzen | Alle / Sub / VIP / Mod |
| **Senden als** | Bot oder Streamer Account | Bot |
| **Plattform** | Twitch, YouTube oder Beide | Beide |

4. Klicke auf **Speichern**

## Keywords (ohne !)

Keywords reagieren wenn der Text **irgendwo** in einer Chat-Nachricht vorkommt — ohne `!` Prefix. Sie haben einen eigenen Tab auf der Commands-Seite.

!!! info "Wann Keywords nutzen?"
    Keywords eignen sich für automatische Antworten auf häufige Fragen. Beispiel: Ein Keyword "welches mikrofon" antwortet mit deinem Equipment, egal wie die Frage formuliert ist.

Wechsle zum **Keywords**-Tab und erstelle dort ein neues Keyword. Der Name wird ohne `!` gespeichert.

**Beispiele:**

| Keyword | Antwort |
|---------|---------|
| `welches mikrofon` | Ich nutze ein Shure SM7B! |
| `gg` | GG! Gut gespielt! |
| `discord` | Unser Discord: discord.gg/dein-link |

## Aliase

Ein Command kann mehrere Namen haben:

- Aliase werden im Modal als kommagetrennte Liste eingegeben
- Aliase bekommen automatisch das gleiche Prefix wie der Hauptbefehl
- Beispiel: Command `!discord`, Aliase: `dc, dis` → reagiert auf `!discord`, `!dc`, `!dis`

## Antworttyp (Response Type)

Bestimme **wie** der Bot antwortet:

| Typ | Beschreibung | Twitch | YouTube |
|-----|-------------|--------|---------|
| **Normal** | Nachricht im Chat | Ja | Ja |
| **Antwort** | Twitch Reply-Feature | Ja | @Username |
| **Erwähnung** | @User vor der Nachricht | Ja | Ja |
| **Flüstern** | DM an den User | Ja | Nicht verfügbar |

!!! warning "Whisper-Fallback"
    Wenn der User Flüsternachrichten deaktiviert hat, sendet der Bot stattdessen einen Hinweis im Chat: "Ich konnte dir keine Flüsternachricht senden." Die eigentliche Antwort wird **nicht** öffentlich gepostet — private Inhalte (z.B. Gewinn-Codes) bleiben geschützt.

!!! info "YouTube + Flüstern"
    YouTube unterstützt kein Flüstern. Botly verwendet stattdessen eine Erwähnung (@User).

## Bedingungen (Conditions)

Bestimme **wann** der Command aktiv ist:

- **Immer aktiv** — Reagiert immer (Standard)
- **Nur wenn live** — Nur während des Streams
- **Nur wenn offline** — Nur wenn du nicht streamst
- **Ablaufdatum** — Command wird nach dem Datum automatisch deaktiviert

Abgelaufene Commands werden mit einem "Abgelaufen"-Badge markiert und sind deaktiviert.

!!! tip "Ablaufdatum nutzen"
    Perfekt für zeitbegrenzte Aktionen wie Events oder Gewinnspiele. Der Command wird automatisch deaktiviert — du musst nicht daran denken.

## Auto-Timer

Lass einen Command automatisch in regelmäßigen Abständen posten:

1. Aktiviere **Auto-Timer** im Command-Modal
2. Stelle das **Zeitintervall** ein (1-60 Minuten)
3. Optional: **Mindest-Nachrichten** — Timer postet nur wenn genug Chat-Aktivität da ist

Der Timer wird zurückgesetzt wenn jemand den Command manuell auslöst.

## Variablen

Nutze Variablen in der Antwort die automatisch mit Live-Daten gefüllt werden:

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `$(user)` | Username des Aufrufers | `CoolViewer` |
| `$(channel)` | Kanalname | `thymply_` |
| `$(game)` | Aktuelle Twitch-Kategorie | `Elden Ring` |
| `$(title)` | Stream-Titel | `Chill Stream!` |
| `$(uptime)` | Stream-Dauer | `2:34:12` |
| `$(count)` | Wie oft der Command aufgerufen wurde | `42` |
| `$(args)` | Text nach dem Command | `Hallo Welt` |
| `$(followage)` | Wie lange der User folgt | `3 Monate` |

## Beispiele

**Social Links:**
```
!discord → Unser Discord: discord.gg/dein-link
!socials → Folge mir auf Twitter: @deinname | Insta: @deinname
```

**Dynamisch:**
```
!game → $(channel) spielt gerade $(game)
!followage → $(user) folgt seit $(followage)
```

## Häufige Fragen

??? question "Wie viele Commands kann ich erstellen?"
    Unbegrenzt — in jedem Plan. Es gibt kein Limit für Commands.

??? question "Kann ich Commands importieren?"
    Ja. Klicke auf **Importieren** und lade eine JSON- oder CSV-Datei hoch. Nightbot und Moobot Format wird unterstützt.
