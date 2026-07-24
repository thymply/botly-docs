---
title: Action-Chains
description: Automatisiere deinen Stream mit WENN-PRÜFE-TUE Regeln.
---

# Action-Chains

!!! warning "Botly Desktop wird eingestellt"
    Die Botly Desktop App wird eingestellt. Overlays laufen künftig direkt als Browser-Source im Dashboard — kein Download mehr nötig. Details im [Changelog](../changelog.md).

Action-Chains sind das Herzstück der Desktop App. Mit ihnen erstellst du **Automatisierungen**, die auf Events reagieren und komplexe Abläufe ausführen — ohne eine Zeile Code zu schreiben.

Das Prinzip: **WENN** etwas passiert → **PRÜFE** Bedingungen → **TUE** Aktionen.

## Das Konzept: WENN → PRÜFE → TUE

Jede Action-Chain besteht aus drei Teilen:

```
WENN:   Ein Event tritt ein (Follow, Sub, Donation, Hotkey, ...)
PRÜFE:  Bedingungen werden geprüft (Cooldown, Mindestbetrag, ...)
TUE:    Aktionen werden der Reihe nach ausgeführt
```

### Beispiel

> **WENN** jemand folgt
> **PRÜFE** ob der Cooldown abgelaufen ist
> **TUE** zeige einen Alert → sende eine Chat-Nachricht → spiele einen Sound

Die Aktionen werden **sequenziell** ausgeführt — eine nach der anderen. Du kannst mit "Warten"-Aktionen Pausen einbauen.

## Eine Action-Chain erstellen

### Schritt für Schritt

1. Öffne die **Desktop App**
2. Gehe zu **Action-Chains**
3. Klicke auf **"Neue Action-Chain"**
4. Vergib einen **Namen** (z.B. "Follow-Alert")
5. Wähle einen **Trigger** (das WENN)
6. Füge optional **Bedingungen** hinzu (das PRÜFE)
7. Füge **Aktionen** hinzu (das TUE)
8. Klicke auf **"Speichern"**

!!! tip "Testen"
    Jede Action-Chain hat einen **"Jetzt auslösen"**-Button zum manuellen Testen. Nutze ihn, bevor du live gehst.

## Trigger-Typen

Der Trigger bestimmt, **wann** die Action-Chain ausgelöst wird.

=== "Twitch"

    | Trigger | Beschreibung |
    |---------|-------------|
    | Follow | Jemand folgt deinem Kanal |
    | Subscription | Neues Abo oder Resub |
    | Gift Sub | Geschenk-Abo an Community |
    | Bits / Cheer | Bits werden gespendet |
    | Raid | Ein anderer Streamer raidet dich |
    | Channel Points | Kanalpunkte-Einlösung |
    | Chat Command | Bestimmter Befehl im Chat |
    | Chat Message | Nachricht mit Keyword |
    | Hype Train | Hype Train startet/endet |
    | Ad Break | Werbepause startet/endet |

=== "YouTube"

    | Trigger | Beschreibung |
    |---------|-------------|
    | New Member | Neues Kanalmitglied |
    | Super Chat | Super Chat Spende |
    | Super Sticker | Super Sticker Spende |
    | Chat Message | Nachricht mit Keyword |

=== "Discord"

    | Trigger | Beschreibung |
    |---------|-------------|
    | Member Join | Neues Server-Mitglied |
    | Reaction | Reaktion auf eine Nachricht |

=== "Donations"

    | Trigger | Beschreibung |
    |---------|-------------|
    | Tipeeestream | Donation über Tipeeestream |
    | StreamElements | Donation über StreamElements |
    | Streamlabs | Donation über Streamlabs |
    | Ko-Fi | Donation über Ko-Fi |

=== "System"

    | Trigger | Beschreibung |
    |---------|-------------|
    | Timer | Zeitgesteuert (alle X Minuten) |
    | Hotkey | Tastenkombination |
    | Manuell | Nur über "Jetzt auslösen" |
    | App-Start | Beim Starten der Desktop App |

!!! info "Vollständige Referenz"
    Alle Trigger mit ihren Parametern und Variablen findest du in der [Trigger-Typen Referenz](../referenz/trigger-typen.md).

## Aktions-Typen

Aktionen sind das, was **passiert**, wenn die Chain ausgelöst wird. Du kannst beliebig viele Aktionen kombinieren.

### Chat

| Aktion | Beschreibung |
|--------|-------------|
| **Chat-Nachricht** | Nachricht im Twitch/YouTube-Chat senden |
| **Ankündigung** | Twitch Announcement senden |
| **Shoutout** | Twitch Shoutout an einen User |

### OBS Studio

| Aktion | Beschreibung |
|--------|-------------|
| **Szene wechseln** | Zu einer OBS-Szene wechseln |
| **Quelle ein/aus** | OBS-Quelle sichtbar/unsichtbar machen |
| **Filter ein/aus** | OBS-Filter aktivieren/deaktivieren |
| **Screenshot** | Screenshot der aktuellen Szene |
| **Aufnahme starten/stoppen** | OBS-Aufnahme steuern |
| **Streaming starten/stoppen** | OBS-Streaming steuern |

### Alerts

| Aktion | Beschreibung |
|--------|-------------|
| **Alert anzeigen** | Einen Alert im Browser Source anzeigen |
| **Sound abspielen** | Audio-Datei abspielen |
| **TTS** | Text-to-Speech Nachricht |

### Steuerung

| Aktion | Beschreibung |
|--------|-------------|
| **Warten** | X Sekunden pausieren |
| **Counter** | Counter erhöhen/verringern/setzen |
| **Variable setzen** | Eigene Variable speichern |
| **Variable lesen** | Wert einer Variable abrufen |
| **Zufallszahl** | Zufällige Zahl generieren |

### Weitere

| Aktion | Beschreibung |
|--------|-------------|
| **HTTP Request** | Externe API aufrufen |
| **Datei lesen/schreiben** | Lokale Textdatei bearbeiten |
| **Programm starten** | Externe Anwendung starten |
| **Twitch API** | Twitch-Aktionen (Clip erstellen, Titel ändern, ...) |

!!! info "30+ Aktionstypen"
    Die vollständige Liste mit allen Parametern findest du in der [Aktions-Typen Referenz](../referenz/aktions-typen.md).

## Bedingungen

Bedingungen bestimmen, **ob** die Chain ausgeführt wird, nachdem der Trigger ausgelöst wurde.

### Cooldown

Verhindert, dass die Chain zu oft ausgelöst wird.

| Typ | Beschreibung |
|-----|-------------|
| **Globaler Cooldown** | Chain kann nur alle X Sekunden ausgelöst werden |
| **User-Cooldown** | Jeder User hat seinen eigenen Cooldown |

```
Globaler Cooldown: 30 Sekunden
→ Egal wer triggert, mindestens 30s Pause zwischen Auslösungen

User-Cooldown: 60 Sekunden
→ Jeder User kann nur alle 60s auslösen, andere User sind nicht betroffen
```

### Mindestbetrag

Für Donations, Bits und Super Chats:

```
Mindestbetrag: 5.00
→ Chain wird nur ausgelöst wenn der Betrag >= 5.00 ist
```

### User-Level

Einschränkung nach Benutzerrolle:

| Level | Beschreibung |
|-------|-------------|
| Alle | Jeder kann auslösen |
| Subscriber | Nur Abonnenten |
| VIP | Nur VIPs |
| Moderator | Nur Mods |
| Streamer | Nur du selbst |

### Zufallschance

Die Chain wird nur mit einer bestimmten Wahrscheinlichkeit ausgeführt:

```
Chance: 25%
→ Bei jedem Trigger wird gewürfelt — nur in 25% der Fälle läuft die Chain
```

!!! tip "Bedingungen kombinieren"
    Du kannst mehrere Bedingungen gleichzeitig setzen. Alle müssen erfüllt sein, damit die Chain läuft. Beispiel: Mindestbetrag 5.00 UND Cooldown 30s.

## Variablen in Actions

In vielen Aktionen kannst du **Variablen** verwenden, die automatisch mit den Event-Daten gefüllt werden.

### Syntax

Variablen werden in geschweiften Klammern geschrieben:

```
Willkommen {username}! Danke für die {amount} Bits!
```

### Verfügbare Variablen

Die verfügbaren Variablen hängen vom Trigger ab:

=== "Twitch Follow"

    | Variable | Beschreibung | Beispiel |
    |----------|-------------|---------|
    | `{username}` | Anzeigename des Users | `CoolViewer` |
    | `{user_id}` | Twitch User-ID | `12345678` |

=== "Twitch Sub"

    | Variable | Beschreibung | Beispiel |
    |----------|-------------|---------|
    | `{username}` | Anzeigename | `CoolViewer` |
    | `{tier}` | Abo-Stufe (1, 2, 3) | `1` |
    | `{months}` | Gesamte Abo-Monate | `6` |
    | `{message}` | Sub-Nachricht | `Weiter so!` |

=== "Bits / Donations"

    | Variable | Beschreibung | Beispiel |
    |----------|-------------|---------|
    | `{username}` | Anzeigename | `CoolViewer` |
    | `{amount}` | Betrag / Anzahl | `500` |
    | `{message}` | Nachricht | `Für den Death Counter!` |
    | `{currency}` | Währung (Donations) | `EUR` |

=== "System"

    | Variable | Beschreibung | Beispiel |
    |----------|-------------|---------|
    | `{streamer}` | Dein Kanalname | `thymply_` |
    | `{game}` | Aktuelle Kategorie | `Elden Ring` |
    | `{viewers}` | Aktuelle Zuschauerzahl | `142` |
    | `{uptime}` | Stream-Dauer | `2:34:12` |

!!! info "Vollständige Variablen-Referenz"
    Alle Variablen für alle Trigger findest du in der [Variablen-Referenz](../referenz/variablen.md).

## Beispiel 1: Follow-Alert mit Chat-Nachricht

Eine einfache Chain: Bei einem neuen Follow wird ein Alert angezeigt und eine Chat-Nachricht gesendet.

### Konfiguration

| Einstellung | Wert |
|------------|------|
| **Name** | Follow-Alert |
| **Trigger** | Twitch Follow |
| **Cooldown** | 5 Sekunden (global) |

### Aktionen

| # | Aktion | Einstellung |
|---|--------|------------|
| 1 | **Alert anzeigen** | Alert: "Follow Alert", Kanal: Standard |
| 2 | **Chat-Nachricht** | `Willkommen {username}! Danke für den Follow!` |

### Ergebnis

1. Jemand folgt deinem Kanal
2. Der Alert wird in der OBS Browser Source angezeigt (mit Animation, Sound, etc.)
3. Der Bot sendet eine Willkommensnachricht im Chat
4. Für 5 Sekunden werden keine weiteren Follow-Alerts ausgelöst

## Beispiel 2: Kanalpunkt → OBS + Sound + Warten + OBS

Eine komplexere Chain: Bei einer Kanalpunkte-Einlösung wird eine OBS-Quelle eingeblendet, ein Sound gespielt, gewartet und die Quelle wieder ausgeblendet.

### Konfiguration

| Einstellung | Wert |
|------------|------|
| **Name** | Kanalpunkt Celebration |
| **Trigger** | Channel Points: "Party Mode" |
| **Cooldown** | 60 Sekunden (global) |

### Aktionen

| # | Aktion | Einstellung |
|---|--------|------------|
| 1 | **Chat-Nachricht** | `{username} hat Party Mode aktiviert!` |
| 2 | **OBS: Quelle ein** | Szene: "Gaming", Quelle: "Confetti Overlay" |
| 3 | **Sound abspielen** | Datei: `party.mp3` |
| 4 | **Warten** | 10 Sekunden |
| 5 | **OBS: Quelle aus** | Szene: "Gaming", Quelle: "Confetti Overlay" |

### Ergebnis

1. Viewer löst "Party Mode" für Kanalpunkte ein
2. Bot sendet Chat-Nachricht
3. Confetti-Overlay erscheint in OBS
4. Party-Sound wird gespielt
5. Nach 10 Sekunden verschwindet das Overlay
6. 60 Sekunden Cooldown bis zur nächsten Einlösung

!!! warning "OBS muss verbunden sein"
    OBS-Aktionen funktionieren nur, wenn die Desktop App per WebSocket mit OBS verbunden ist. Siehe [OBS-Integration](../integrationen/obs.md).

## Tipps

### Cooldowns richtig setzen

- **Follow-Alerts**: 3-5 Sekunden reichen — Follows kommen selten in schneller Folge
- **Bits/Donations**: Kein Cooldown oder sehr kurz — jede Spende soll gewürdigt werden
- **Chat-Commands**: 10-30 Sekunden User-Cooldown verhindert Spam
- **Kanalpunkte**: 30-60 Sekunden global — sonst wird es chaotisch

### Reihenfolge der Aktionen

Die Aktionen werden von oben nach unten ausgeführt. Plane die Reihenfolge:

1. Erst Chat-Nachricht (sofort sichtbar)
2. Dann Alert (braucht einen Moment zum Laden)
3. Dann OBS-Aktionen
4. Warten
5. Aufräumen (Quellen ausblenden, etc.)

### Debugging

Wenn eine Chain nicht funktioniert:

1. **"Jetzt auslösen"** drücken — funktioniert es manuell?
2. **Log prüfen** — die Desktop App zeigt Fehler im Log-Tab
3. **OBS-Verbindung prüfen** — ist der WebSocket aktiv?
4. **Cooldown prüfen** — ist der Timer noch aktiv?
5. **Bedingungen prüfen** — erfüllt der Test-Trigger alle Bedingungen?

!!! tip "Schritt für Schritt testen"
    Erstelle die Chain erst mit einer einzigen Aktion. Teste sie. Füge dann die nächste Aktion hinzu und teste erneut. So findest du Probleme sofort.

## Nächste Schritte

- [Alert-Editor](alert-editor.md) — Alerts gestalten, die du in Chains nutzt
- [Trigger-Typen Referenz](../referenz/trigger-typen.md) — Alle Trigger im Detail
- [Aktions-Typen Referenz](../referenz/aktions-typen.md) — Alle Aktionen im Detail
- [Variablen-Referenz](../referenz/variablen.md) — Alle verfügbaren Variablen
