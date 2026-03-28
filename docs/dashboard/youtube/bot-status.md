---
title: Bot-Status & Live-Erkennung
description: YouTube Bot steuern und Livestreams automatisch erkennen lassen.
---

# Bot-Status & Live-Erkennung

Der YouTube Bot erkennt automatisch wenn du live gehst und aktiviert sich — ohne dass du etwas tun musst.

## YouTube Bot verbinden

1. Logge dich mit deinem **Google-Account** ein (oder verknüpfe ihn nachträglich)
2. Wähle im Dashboard **YouTube Bot**
3. Der Bot verbindet sich automatisch mit deinem YouTube-Kanal

## Live-Erkennung

Botly nutzt **PubSubHubbub** (Googles Push-Dienst) um sofort zu erfahren wenn du live gehst:

1. Du startest einen Livestream auf YouTube
2. YouTube sendet eine Push-Benachrichtigung an Botly
3. Botly aktiviert den Chat-Bot und beginnt mit der Moderation
4. Wenn du offline gehst, deaktiviert sich der Bot automatisch

!!! info "Quota-sparend"
    PubSubHubbub ist kostenlos und verbraucht kein YouTube API Quota. Botly nutzt die YouTube API nur für einmalige Abfragen (1 Unit pro Check), nie für Polling.

## Bot-Status Übersicht

Die Status-Seite zeigt:

| Anzeige | Bedeutung |
|---------|-----------|
| **Grüner Punkt** | Bot ist aktiv und verbunden |
| **Grauer Punkt** | Bot ist offline oder nicht konfiguriert |
| **Live-Badge** | Du bist gerade live auf YouTube |

## Geteilte Features

Commands, Counter und Giveaways die auf "YouTube" oder "Beide" gestellt sind, funktionieren automatisch im YouTube-Chat. Du musst nichts extra konfigurieren.

!!! tip "Commands teilen"
    Stelle deine Commands auf "Twitch & YouTube" und sie funktionieren in beiden Chats gleichzeitig.
