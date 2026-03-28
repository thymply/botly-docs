---
title: Mitspieler / Player Queue
description: Warteschlange für Viewer-Games — Zuschauer können sich zum Mitspielen anmelden.
---

# Mitspieler / Player Queue

Lass deine Zuschauer sich per Chat-Befehl in eine Warteschlange eintragen und ziehe Mitspieler für dein Spiel.

## Konzept

Die Mitspieler-Liste ist eine Warteschlange. Viewer treten bei, du pickst die nächsten Spieler — first come, first served.

## Chat-Befehle

| Befehl | Wer | Beschreibung |
|--------|-----|-------------|
| `!joinlist` | Alle | Der Liste beitreten |
| `!leavelist` | Alle | Die Liste verlassen |
| `!listplayers` | Alle | Aktuelle Liste anzeigen |
| `!pickplayer` | Mod | Nächsten Spieler ziehen |
| `!pickplayer 3` | Mod | Nächste 3 Spieler ziehen |
| `!clearlist` | Mod | Liste komplett leeren |

## Dashboard

Im Dashboard siehst du die aktuelle Liste mit Position, Name und Beitrittszeit. Du kannst:

- **Picken** — Nächsten Spieler ziehen (oberster in der Liste)
- **Aktualisieren** — Liste neu laden
- **Liste leeren** — Alle Einträge entfernen
- Einzelne Spieler per Klick entfernen

<!-- Screenshot: Mitspieler-Liste im Dashboard -->

## Einstellungen

Unter "Einstellungen" (aufklappbar) findest du:

| Einstellung | Beschreibung | Standard |
|------------|-------------|---------|
| **Max. Spieler** | 0 = unbegrenzt | 0 |
| **Plattform** | Twitch, YouTube oder Beide | Beide |
| **Join-Nachricht** | Bot-Antwort beim Beitreten | `{user} ist auf Platz {position}!` |
| **Leave-Nachricht** | Bot-Antwort beim Verlassen | `{user} hat die Liste verlassen.` |
| **Liste voll** | Wenn Max erreicht | `Die Liste ist voll!` |
| **Bereits drin** | Bei doppeltem !joinlist | `Du bist bereits in der Liste!` |

### Verfügbare Variablen

- `{user}` — Username
- `{position}` — Platz in der Liste
- `{count}` — Aktuelle Teilnehmerzahl
- `{max}` — Maximale Teilnehmer

!!! tip "Zwischen Runden leeren"
    Nach jeder Spielrunde: `!clearlist` im Chat oder "Liste leeren" im Dashboard. So startet die nächste Runde frisch.
