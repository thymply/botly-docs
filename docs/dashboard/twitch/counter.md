---
title: Counter
description: Zähler für Death Counter, Win Counter und mehr — mit Auto-Switch pro Spiel.
---

# Counter

Counter sind **numerische Zähler**, die du und deine Mods über Chat-Befehle steuern könnt. Der klassische Einsatz: ein **Death Counter** für Soulslike-Spiele. Aber Counter können für alles genutzt werden — Siege, Fails, Trinkspiel-Punkte, was auch immer du zählen willst.

## Was macht Counter besonders?

- **Chat-Befehle** zum Erhöhen, Verringern und Zurücksetzen
- **Auto-Switch pro Spiel** — der Zähler merkt sich den Wert für jede Twitch-Kategorie
- **Anpassbare Nachrichten** mit Variablen
- **Plattform-Auswahl** — Twitch, YouTube oder beide

## Counter erstellen

### Schritt für Schritt

1. Öffne das **Dashboard** und wähle deinen Bot
2. Gehe zu **Twitch Bot → Counter**
3. Klicke auf **"Counter erstellen"**
4. Fülle die Felder aus:

| Feld | Beschreibung | Beispiel |
|------|-------------|---------|
| **Name** | Der Chat-Befehl (ohne !) | `death` |
| **Startwert** | Anfangswert des Zählers | `0` |
| **Nachricht** | Was der Bot im Chat schreibt | `{user} hat den Zähler auf {value} gesetzt.` |
| **Plattform** | Wo der Befehl funktioniert | Twitch / YouTube / Beide |

5. Klicke auf **"Speichern"**

!!! tip "Name = Chat-Befehl"
    Der Name des Counters wird automatisch zum Chat-Befehl. Ein Counter namens `death` erzeugt die Befehle `!death`, `!death+`, `!death-` usw.

## Chat-Befehle

Jeder Counter erzeugt automatisch folgende Befehle:

| Befehl | Wer | Beschreibung |
|--------|-----|-------------|
| `!name` | Alle | Zeigt den aktuellen Wert |
| `!name+` | Mods | Erhöht um 1 |
| `!name-` | Mods | Verringert um 1 |
| `!name+ 5` | Mods | Erhöht um 5 (beliebige Zahl) |
| `!name- 3` | Mods | Verringert um 3 |
| `!name set 10` | Mods | Setzt auf exakt 10 |
| `!name reset` | Mods | Setzt auf den Startwert zurück |

### Beispiel im Chat

```
Viewer:  !death
Bot:     Death Counter: 14

Mod:     !death+
Bot:     thymply_ ist gestorben! Tode: 15

Mod:     !death reset
Bot:     Death Counter wurde zurückgesetzt. Tode: 0
```

!!! warning "Berechtigung"
    Nur **Moderatoren** und der **Streamer** können Counter verändern (`+`, `-`, `set`, `reset`). Viewer können nur den aktuellen Wert abfragen.

## Auto-Switch pro Spiel

Das Killer-Feature der Counter: **Auto-Switch**. Wenn du die Twitch-Kategorie wechselst, merkt sich der Counter den aktuellen Wert und lädt den gespeicherten Wert für das neue Spiel.

### Wie funktioniert Auto-Switch?

1. Du streamst **Elden Ring** — Death Counter steht auf 47
2. Du wechselst die Kategorie zu **Sekiro**
3. Der Counter wechselt automatisch auf den Sekiro-Wert (z.B. 23)
4. Du wechselst zurück zu **Elden Ring** — Counter ist wieder bei 47

### Auto-Switch aktivieren

1. Öffne den Counter im Dashboard
2. Aktiviere **"Auto-Switch pro Spiel"**
3. Fertig — der Counter speichert ab jetzt pro Kategorie

!!! info "Erster Start pro Spiel"
    Wenn du ein Spiel zum ersten Mal spielst, startet der Counter bei 0 (oder deinem Startwert). Ab dann wird der Wert für dieses Spiel gespeichert.

### Gespeicherte Werte einsehen

Im Dashboard siehst du eine Tabelle mit allen gespeicherten Spielen und deren Werten:

| Spiel | Wert | Zuletzt gespielt |
|-------|------|-----------------|
| Elden Ring | 47 | 25.03.2026 |
| Sekiro | 23 | 20.03.2026 |
| Dark Souls III | 89 | 15.03.2026 |

Du kannst einzelne Spielwerte manuell bearbeiten oder löschen.

## Nachrichten anpassen

Jeder Counter hat anpassbare Nachrichten für verschiedene Aktionen. Du kannst Variablen verwenden:

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `{value}` | Aktueller Zählerwert | `14` |
| `{amount}` | Um wie viel geändert wurde | `1` |
| `{user}` | Wer den Befehl ausgeführt hat | `thymply_` |
| `{game}` | Aktuelle Twitch-Kategorie | `Elden Ring` |
| `{name}` | Name des Counters | `Death Counter` |

### Nachricht-Vorlagen

**Abfrage** (`!name`):

```
{name}: {value}
```

**Erhöhen** (`!name+`):

```
{user} hat den {name} erhöht! Aktuell: {value}
```

**Verringern** (`!name-`):

```
{name} wurde um {amount} verringert. Aktuell: {value}
```

**Zurücksetzen** (`!name reset`):

```
{name} wurde zurückgesetzt. {game} startet bei {value}.
```

!!! tip "Kreative Nachrichten"
    Passe die Nachrichten an den Kontext an. Für einen Death Counter:
    `"RIP! {user} hat Tod Nr. {value} dokumentiert."` klingt besser als die Standard-Nachricht.

## Plattform-Auswahl

Du kannst für jeden Counter festlegen, auf welcher Plattform er funktioniert:

- **Twitch** — Befehl nur im Twitch-Chat
- **YouTube** — Befehl nur im YouTube-Chat
- **Beide** — Befehl auf beiden Plattformen, gleicher Zählerstand

!!! info "Geteilter Zählerstand"
    Bei "Beide" teilen sich Twitch und YouTube denselben Wert. Ein `!death+` im Twitch-Chat erhöht den Counter auch für YouTube-Viewer.

## Aktivieren / Deaktivieren

Jeden Counter kannst du mit einem Toggle ein- und ausschalten, ohne ihn zu löschen. Ein deaktivierter Counter:

- reagiert nicht auf Chat-Befehle
- behält seinen Wert und alle Einstellungen
- kann jederzeit wieder aktiviert werden

## Tipps & Beispiele

### Death Counter (Soulslike)

| Einstellung | Wert |
|------------|------|
| Name | `death` |
| Startwert | `0` |
| Auto-Switch | Aktiviert |
| Nachricht (Erhöhen) | `RIP! Tod Nr. {value} in {game}.` |
| Plattform | Beide |

### Win Counter (Competitive)

| Einstellung | Wert |
|------------|------|
| Name | `wins` |
| Startwert | `0` |
| Auto-Switch | Aktiviert |
| Nachricht (Erhöhen) | `GG! {value} Siege in {game} heute!` |
| Plattform | Twitch |

### Trinkspiel-Counter

| Einstellung | Wert |
|------------|------|
| Name | `drink` |
| Startwert | `0` |
| Auto-Switch | Deaktiviert |
| Nachricht (Erhöhen) | `Prost! Runde {value} geht auf {user}!` |
| Plattform | Beide |

!!! warning "Verantwortung"
    Trinkspiel-Counter sind natürlich nur zum Spaß. Trink verantwortungsvoll.

## Häufige Fragen

??? question "Kann ich mehrere Counter gleichzeitig haben?"
    Ja, du kannst beliebig viele Counter erstellen. Jeder hat seinen eigenen Namen und seine eigenen Chat-Befehle.

??? question "Wird der Wert bei einem Neustart zurückgesetzt?"
    Nein. Counter-Werte werden in der Datenbank gespeichert und überleben Neustarts, Updates und sogar Server-Wechsel.

??? question "Kann ich den Counter auch über das Dashboard ändern?"
    Ja. Im Dashboard kannst du den Wert direkt bearbeiten, ohne einen Chat-Befehl zu nutzen.

??? question "Funktioniert Auto-Switch auch bei YouTube?"
    Auto-Switch basiert auf der Twitch-Kategorie. Wenn du nur auf YouTube streamst, gibt es keine automatische Spielerkennung — du kannst den Wert aber manuell pro Spiel setzen.
