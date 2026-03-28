---
title: OBS Studio
description: OBS WebSocket Verbindung einrichten und OBS aus Botly steuern.
---

# OBS Studio Integration

Verbinde OBS Studio per WebSocket mit der Botly Desktop App.

## Unterstützte Software

| Software | Version | WebSocket |
|----------|---------|-----------|
| **OBS Studio** | 28+ | Eingebaut (obs-websocket 5.x) |
| **Streamlabs Desktop** | Aktuell | Plugin erforderlich |

## WebSocket aktivieren

### OBS Studio

1. Öffne **Extras** → **WebSocket-Server Einstellungen**
2. Aktiviere **WebSocket-Server aktivieren**
3. Port: `4455` (Standard)
4. Setze ein **Passwort** (empfohlen)
5. Klicke auf **Übernehmen**

### In der Desktop App

1. Gehe zu **OBS**
2. Trage **Host** (`localhost`), **Port** (`4455`) und **Passwort** ein
3. Klicke auf **Verbinden**
4. Grüner Punkt = verbunden

## Steuerungsmöglichkeiten

Über die OBS-Verbindung kann Botly:

- **Szenen wechseln** — Zu jeder konfigurierten Szene
- **Quellen ein-/ausblenden** — Sichtbarkeit toggling
- **Filter ein-/ausschalten** — Auf jeder Quelle
- **Screenshots machen** — Der aktuellen Szene
- **Aufnahme steuern** — Starten/Stoppen

!!! warning "Einschränkungen"
    Aus Sicherheitsgründen kann Botly den Stream **nicht** starten oder stoppen und OBS **nicht** beenden. Diese Aktionen müssen manuell ausgeführt werden.

## Verbindung prüfen

In der Desktop App unter **OBS** siehst du:

- **Status-Punkt** — Grün = verbunden, Grau = getrennt
- **Szenen-Liste** — Alle verfügbaren OBS-Szenen
- **Quellen-Liste** — Quellen der aktuellen Szene

!!! tip "Automatische Verbindung"
    Die Desktop App verbindet sich beim Start automatisch mit OBS wenn die Einstellungen gespeichert sind.
