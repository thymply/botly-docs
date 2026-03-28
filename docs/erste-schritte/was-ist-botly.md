---
title: Was ist Botly?
description: Botly ist ein Multi-Plattform Streaming Bot für Twitch, YouTube und Discord.
---

# Was ist Botly?

Botly ist ein **Multi-Plattform Streaming Bot**, der Twitch, YouTube und Discord in einem einzigen Dashboard vereint. Statt drei verschiedene Tools zu verwalten, steuerst du alles über eine Oberfläche — Commands, Moderation, Alerts, Giveaways und mehr.

## Die drei Ebenen von Botly

Botly besteht aus drei Komponenten, die zusammenspielen:

### 1. Web-Dashboard (SaaS)

Das Dashboard erreichst du über den Browser unter [botly.thymply.de](https://botly.thymply.de). Hier verwaltest du:

- **Chat-Commands** für Twitch und YouTube
- **Counter** mit Auto-Switch pro Spiel
- **Timer**, **Giveaways**, **Mitspieler-Queue**
- **AutoMod** für alle drei Plattformen
- **Discord-Features** wie Welcome-Nachrichten, Reaction Roles, Temp-Voice
- **Editoren** einladen und Rechte vergeben

Das Dashboard ist kostenlos nutzbar (Free-Plan) und läuft komplett in der Cloud — du musst nichts installieren.

### 2. Chat-Bot (Cloud)

Der Bot selbst läuft auf Botly-Servern und verbindet sich mit deinen Kanälen. Er reagiert auf Chat-Nachrichten, Events (Follows, Subs, Raids) und führt deine konfigurierten Aktionen aus. Du musst keinen eigenen Server betreiben.

### 3. Desktop App (Premium)

Die Desktop App ist eine lokale Anwendung für Windows, die zusätzliche Premium-Features bietet:

- **Alert-Editor** — Stream-Alerts gestalten und live anzeigen
- **Action-Chains** — Komplexe Automatisierungen: WENN → PRÜFE → TUE
- **OBS-Steuerung** — Szenen, Quellen und Filter direkt steuern
- **CrossChat Bridge** — Chat zwischen Twitch und YouTube synchronisieren
- **Donations** — Tipeeestream, StreamElements, Streamlabs, Ko-Fi
- **KI-Assistent** — Lokal mit Ollama oder Cloud (OpenAI, Anthropic)

!!! info "Desktop App = Premium"
    Die Desktop App ist Teil des Premium-Plans. Du kannst Botly aber auch ohne Desktop App vollständig nutzen — alle Basis-Features laufen über das Web-Dashboard.

## Für wen ist Botly?

Botly ist für **Streamer**, die:

- auf **mehreren Plattformen** gleichzeitig streamen (oder wechseln wollen)
- **ein Tool** statt drei separate Bots verwalten wollen
- ihre **Alerts und OBS-Steuerung** lokal kontrollieren möchten
- **Automatisierungen** ohne Programmierkenntnisse erstellen wollen

Egal ob du gerade anfängst oder schon eine Community hast — Botly wächst mit deinen Anforderungen.

## Wie unterscheidet sich Botly?

| Feature | Botly | StreamElements | Streamlabs | Streamer.bot |
|---------|-------|----------------|------------|--------------|
| Twitch Bot | Ja | Ja | Ja | Ja |
| YouTube Bot | Ja | Nein | Eingeschränkt | Nein |
| Discord Bot | Ja | Nein | Nein | Nein |
| Web-Dashboard | Ja | Ja | Ja | Nein |
| Desktop App | Ja (Premium) | Nein | Desktop-only | Ja |
| Action-Chains | Ja | Nein | Nein | Ja (C#) |
| OBS-Steuerung | Ja | Nein | Nein | Ja |
| Lokale KI | Ja (Ollama) | Nein | Nein | Nein |
| Kostenloser Plan | Ja | Ja | Ja | Ja |

**Kurzfassung:**

- **StreamElements** — Starke Twitch-Overlays, aber nur Twitch und Cloud-only
- **Streamlabs** — Ressourcenhungrig, eigene Desktop App, kein YouTube-Bot
- **Streamer.bot** — Mächtig aber rein lokal, kein Dashboard, erfordert C#-Kenntnisse
- **Botly** — Vereint Cloud-Dashboard mit lokaler Desktop App, alle drei Plattformen

## Das Botly-Modell: SaaS + Lokal

Botly kombiniert zwei Ansätze:

**Cloud (SaaS):** Das Dashboard und der Chat-Bot laufen auf Botly-Servern. Du loggst dich ein und alles funktioniert — ohne Installation, ohne eigenen Server. Updates kommen automatisch.

**Lokal (Desktop App):** Die Desktop App läuft auf deinem PC. Alerts werden lokal gerendert, OBS wird direkt per WebSocket gesteuert, und die KI kann komplett offline laufen (Ollama). Deine Daten bleiben auf deinem Rechner.

!!! tip "Das Beste aus beiden Welten"
    Cloud für Zuverlässigkeit und Komfort, Lokal für Geschwindigkeit und Kontrolle. Du entscheidest, wie viel du lokal machen willst.

## Pläne im Überblick

| | Free | Pro | Premium |
|---|---|---|---|
| Commands, Timer, Counter | Ja | Ja | Ja |
| AutoMod (alle Plattformen) | Ja | Ja | Ja |
| Giveaways | — | Ja | Ja |
| Auto-Clip | — | Ja | Ja |
| Editoren | — | Ja | Ja |
| Desktop App | — | — | Ja |
| Action-Chains | — | — | Ja |
| Alert-Editor | — | — | Ja |
| KI-Assistent | — | — | Ja |

[Alle Details zu den Plänen](plaene.md){ .md-button }

## Nächste Schritte

1. [Account erstellen](account-erstellen.md) — Login mit Twitch, YouTube oder Discord
2. [Deinen ersten Bot einrichten](erster-bot.md) — In 5 Minuten zum laufenden Bot
3. [Dashboard-Übersicht](dashboard-uebersicht.md) — Navigation und Aufbau verstehen
