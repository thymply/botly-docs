---
title: Bot-Konto & Live-Erkennung
description: Bot-Konto des YouTube Bots verwalten und Livestreams automatisch erkennen lassen.
---

# Bot-Konto & Live-Erkennung

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

## Bot-Konto

Im Bereich **Bot-Konto** (**YouTube Bot** → **Bot-Konto**) legst du fest, über welchen Account der Bot im Live-Chat schreibt:

| Situation | Was du siehst |
|---------|-----------|
| **Kein Bot-Konto verbunden** | Der Bot schreibt über deinen Streamer-Account. Mit **Bot-Konto verknüpfen** verbindest du einen separaten YouTube-Account als Bot |
| **Bot-Konto verbunden** | Name und Bild des Bot-Kontos. Mit **Trennen** löst du die Verbindung wieder |
| **Kein YouTube-Kanal verbunden** | Hinweis, zuerst einen YouTube-Kanal zu verbinden |

!!! info "Verbindung neu herstellen"
    Ist die Verbindung zu deinem Bot-Konto nicht mehr gültig, zeigt das Dashboard oben einen Hinweis mit dem Knopf **Neu verbinden**. Bis du das Bot-Konto neu verbindest, schreibt Botly mit deinem Kanal.

## Geteilte Features

Commands, Counter und Giveaways die auf "YouTube" oder "Beide" gestellt sind, funktionieren automatisch im YouTube-Chat. Du musst nichts extra konfigurieren.

!!! tip "Commands teilen"
    Stelle deine Commands auf "Twitch & YouTube" und sie funktionieren in beiden Chats gleichzeitig.
