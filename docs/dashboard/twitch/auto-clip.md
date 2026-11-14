---
title: Auto-Clip
description: Automatisch Twitch-Clips erstellen bei Emote-Spam, Chat-Hype, Gifted Subs, Raids oder per Chat-Befehl.
---

# Auto-Clip

Auto-Clip erstellt automatisch einen Twitch-Clip, wenn in deinem Stream etwas Besonderes passiert — zum Beispiel wenn der Chat explodiert, jemand viele Subs verschenkt oder ein großer Raid kommt. Zusätzlich können Mods per Chat-Befehl einen Clip auslösen.

!!! info "Premium Feature"
    Auto-Clip ist im **Premium**-Plan verfügbar.

## Einrichtung

1. Gehe zu **Twitch Bot** → **Auto-Clip**
2. Schalte die gewünschten Trigger ein (alle sind am Anfang ausgeschaltet)
3. Passe die Schwellenwerte an
4. Klicke auf **Speichern**

## Trigger

| Trigger | Löst einen Clip aus, wenn … | Einstellungen (Standard) |
|---------|----------------------------|--------------------------|
| **Clip-Command** | jemand mit ausreichendem Level den Befehl in den Chat schreibt | **Command** (`!clip`), **Min. Level** (Mod) |
| **Emote-Spam** | im Zeitfenster zusammen mindestens so viele Emotes im Chat stehen | **Min. Emotes** (10), **Zeitfenster (Sek.)** (30) |
| **Chat-Hype** | im Zeitfenster mindestens so viele Chat-Nachrichten eingehen | **Min. Nachrichten** (20), **Zeitfenster (Sek.)** (30) |
| **Gifted Subs** | jemand auf einmal mindestens so viele Subs an die Community verschenkt | **Min. Gifted Subs** (5) |
| **Raid** | ein Raid mit mindestens so vielen Zuschauern eintrifft | **Min. Viewer** (10) |

!!! note "Emotes zählen"
    Beim Emote-Spam zählt jedes verschiedene Emote einmal pro Nachricht. Schreibt jemand dasselbe Emote fünfmal in eine Nachricht, zählt das als ein Emote.

### Min. Level beim Clip-Command

| Auswahl | Wer darf clippen |
|---------|------------------|
| **Alle** | Jeder im Chat |
| **Sub** | Abonnenten, Mods und du |
| **Mod** | Mods und du |

## Was passiert beim Clip?

- Botly erstellt den Clip über deinen verbundenen Twitch-Account und postet den Link im Chat: `📎 Clip erstellt! https://clips.twitch.tv/…`
- Botly erstellt höchstens **einen Clip pro 60 Sekunden**. Treffen in dieser Zeit weitere Trigger ein, entsteht kein zusätzlicher Clip.
- Eine Verzögerung oder eine Clip-Länge stellst du in Botly nicht ein — der Clip entsteht in dem Moment, in dem der Trigger auslöst.

Deine Clips findest du anschließend im [Clips Dashboard](clips-dashboard.md).
