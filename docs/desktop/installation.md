---
title: Installation & Einrichtung
description: Download, Installation und Verbindung der Desktop App mit Botly.
---

# Installation & Einrichtung

Lade die Desktop App herunter, installiere sie und verbinde sie mit deinem Botly-Account.

## Voraussetzungen

- **Windows 10/11** (64-bit)
- **Botly Pro oder höher**
- Eine aktive Internetverbindung

!!! info "Kein Python nötig"
    Die Desktop App ist eine standalone .exe — du brauchst kein Python oder andere Abhängigkeiten zu installieren.

## Download

1. Logge dich im [Botly Dashboard](https://botly.thymply.de) ein
2. Gehe zu **Tools** → **Botly Desktop**
3. Klicke auf **Download**
4. Lade den **NSIS Installer** herunter (.exe)

## Installation

1. Starte den heruntergeladenen **BotlyDesktop_Setup.exe**
2. Folge dem Installer (Standardpfad: `C:\Program Files\BotlyDesktop`)
3. Eine Desktop-Verknüpfung wird automatisch erstellt
4. Starte **Botly Desktop** über die Verknüpfung

<!-- Screenshot: NSIS Installer -->

## Erster Start: Token eingeben

Beim ersten Start fragt die App nach einem **Verbindungstoken**:

1. Im Dashboard unter **Tools** → **Botly Desktop** findest du den **Token**
2. Kopiere den Token
3. Füge ihn in der Desktop App ein
4. Klicke auf **Verbinden**

Der Token verbindet deine Desktop App dauerhaft mit deinem Botly-Account. Du musst ihn nur einmal eingeben.

!!! warning "Token geheim halten"
    Der Token ist wie ein Passwort. Teile ihn nicht mit anderen — wer den Token hat, kann deine Desktop App fernsteuern.

## OBS WebSocket aktivieren

Für die OBS-Steuerung muss OBS WebSocket aktiv sein:

1. Öffne **OBS Studio**
2. Gehe zu **Extras** → **WebSocket-Server Einstellungen**
3. Aktiviere **WebSocket-Server**
4. Notiere den **Port** (Standard: 4455) und setze ein **Passwort**
5. In der Desktop App → **OBS**: Trage Port und Passwort ein
6. Klicke auf **Verbinden** — der grüne Punkt zeigt die Verbindung an

## Datenverzeichnis

Die Desktop App speichert ihre Daten unter:

```
%LOCALAPPDATA%\BotlyDesktop\
├── config.ini        (Einstellungen)
├── data\desktop.db   (Lokale Datenbank)
└── logs\             (Log-Dateien)
```

Die Programmdateien liegen im Installationsverzeichnis, die Benutzerdaten separat in AppData.

## Update

Bei neuen Versionen:

1. Lade den neuen Installer herunter
2. Installiere ihn über die bestehende Installation
3. Deine Einstellungen und Daten bleiben erhalten
