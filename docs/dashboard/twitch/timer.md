---
title: Timer
description: Automatische Chat-Nachrichten in regelmäßigen Abständen senden.
---

# Timer

Timer senden automatisch wiederkehrende Nachrichten in deinen Chat — perfekt für Social-Links, Regeln oder Ankündigungen.

## Wie Timer funktionieren

Timer sind in Botly Teil der Commands. Jeder Command kann einen **Auto-Timer** aktivieren, der ihn in regelmäßigen Abständen automatisch postet.

!!! info "Timer = Command mit Auto-Timer"
    Es gibt keine separate Timer-Sektion. Erstelle stattdessen einen Command und aktiviere den Auto-Timer im Modal.

## Timer erstellen

1. Gehe zu **Twitch Bot** → **Commands**
2. Erstelle einen neuen Command (z.B. `!socials`)
3. Aktiviere **Auto-Timer** im Modal
4. Stelle das **Zeitintervall** ein (z.B. 15 Minuten)
5. Optional: **Mindest-Nachrichten** aktivieren
6. Speichern

<!-- Screenshot: Auto-Timer Einstellungen im Command-Modal -->

## Einstellungen

### Zeitintervall

Wie oft der Timer postet (1-60 Minuten). Empfehlungen:

| Typ | Intervall |
|-----|-----------|
| Social Links | 15-30 Minuten |
| Regeln / Hinweise | 20-30 Minuten |
| Aktive Aktionen | 5-10 Minuten |

### Mindest-Nachrichten

Wenn aktiviert, postet der Timer nur wenn seit dem letzten Post mindestens X Nachrichten im Chat geschrieben wurden. Verhindert Spam in ruhigen Phasen.

!!! tip "Empfehlung: 5-10 Nachrichten"
    So wird der Timer nicht in einem leeren Chat gepostet, aber auch nicht zu lange verzögert.

### Nur wenn live

Timer mit der Bedingung "Nur wenn live" posten nur während des Streams. Perfekt für Stream-bezogene Hinweise.

## Timer in der Command-Liste

Commands mit aktivem Auto-Timer zeigen einen blauen **Auto-Tag** in der Liste:

```
!socials  Auto: 15 Min. / 10 Nachr.  Twitch & YT
```

## Beispiele

| Command | Antwort | Intervall |
|---------|---------|-----------|
| `!socials` | Folge mir auf Twitter und Instagram! @name | 20 Min. |
| `!rules` | Seid nett zueinander! Kein Spam, keine Links ohne Erlaubnis. | 30 Min. |
| `!merch` | Neuer Merch im Shop: shop.example.com | 15 Min. |

??? question "Kann ich den Timer manuell zurücksetzen?"
    Ja — wenn jemand den Command manuell im Chat eingibt (z.B. `!socials`), wird der Timer zurückgesetzt und zählt von vorne.
