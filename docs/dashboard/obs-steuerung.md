---
title: OBS-Steuerung
description: OBS Studio direkt aus dem Dashboard steuern — Szenen, Quellen, Filter.
---

# OBS-Steuerung

Steuere OBS Studio über den Relay-Agent direkt aus dem Dashboard oder per Action-Chain.

## Voraussetzungen

- **OBS Studio** (oder Streamlabs Desktop) mit aktiviertem WebSocket
- **Botly Desktop App** (Pro oder höher) als Relay-Agent

## Relay-Agent einrichten

Der Relay-Agent ist die Brücke zwischen Botly (Cloud) und OBS (lokal):

1. Installiere die [Botly Desktop App](../desktop/installation.md)
2. Verbinde sie mit deinem Botly-Account (Token)
3. Stelle die OBS WebSocket-Verbindung her (Port 4455)
4. Der Relay-Agent läuft im Hintergrund

!!! info "Warum ein Relay-Agent?"
    OBS läuft lokal auf deinem PC. Botly läuft in der Cloud. Der Relay-Agent verbindet beides über eine sichere WebSocket-Verbindung.

## Regeln erstellen

Regeln definieren was bei welchem Event passiert:

| Wenn... | Dann... |
|---------|---------|
| Jemand folgt | Szene wechseln |
| Raid kommt | Quelle einblenden |
| Donation eingeht | Filter aktivieren |

Die Regeln werden im Dashboard unter **OBS-Steuerung** konfiguriert.

## Verfügbare OBS-Aktionen

| Aktion | Beschreibung |
|--------|-------------|
| **Szene wechseln** | Zu einer bestimmten OBS-Szene wechseln |
| **Quelle ein/aus** | Eine Quelle sichtbar/unsichtbar machen |
| **Filter ein/aus** | Einen Quell-Filter aktivieren/deaktivieren |
| **Screenshot** | Screenshot der aktuellen Szene |
| **Aufnahme** | Aufnahme starten/stoppen |

!!! warning "Stream starten/stoppen ist gesperrt"
    Aus Sicherheitsgründen kann Botly den Stream nicht starten oder stoppen. Das muss manuell in OBS gemacht werden.

## OBS WebSocket aktivieren

1. Öffne OBS Studio
2. Gehe zu **Extras** → **WebSocket-Server Einstellungen**
3. Aktiviere **WebSocket-Server**
4. Merke dir den **Port** (Standard: 4455) und das **Passwort**
5. Trage beides in der Desktop App unter **OBS** ein
