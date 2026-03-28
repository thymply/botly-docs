---
title: Deinen ersten Bot einrichten
description: In wenigen Minuten zum laufenden Bot auf Twitch, YouTube oder Discord.
---

# Deinen ersten Bot einrichten

Von der Anmeldung bis zum ersten Chat-Befehl — in unter 5 Minuten.

## Voraussetzungen

- Ein [Botly-Account](account-erstellen.md) (kostenlos)
- Mindestens eine verknüpfte Plattform (Twitch, YouTube oder Discord)

## Schritt 1: Twitch Bot verbinden

1. Wähle im Dashboard **Twitch Bot**
2. Klicke auf **Bot-Account verbinden**
3. Autorisiere den Bot-Account auf Twitch

!!! tip "Bot vs. Streamer Account"
    Du kannst wählen ob der Bot als **separater Account** oder als **dein eigener Account** im Chat schreibt. Für den Anfang reicht dein eigener Account — einen separaten Bot-Account kannst du später einrichten.

<!-- Screenshot: Bot-Account Seite -->

## Schritt 2: Ersten Command erstellen

1. Gehe zu **Twitch Bot** → **Commands**
2. Klicke auf **+ Neuer Command**
3. Fülle aus:
   - **Command:** `!discord`
   - **Antwort:** `Unser Discord: discord.gg/dein-link`
   - **Cooldown:** `10` Sekunden
4. Klicke auf **Speichern**

```
Viewer:  !discord
Bot:     Unser Discord: discord.gg/dein-link
```

!!! info "Sofort aktiv"
    Der Command ist sofort im Chat verfügbar — kein Neustart nötig.

## Schritt 3: Im Chat testen

Öffne deinen Twitch-Chat und tippe `!discord`. Der Bot sollte sofort antworten.

Falls nicht:

1. Prüfe ob der Bot-Account verbunden ist (grüner Punkt unter **Bot-Status**)
2. Prüfe ob der Command aktiviert ist (Toggle in der Command-Liste)
3. Warte den Cooldown ab (Standard: 5 Sekunden)

## Schritt 4: Discord-Server verbinden

1. Wechsle im Dashboard zu **Discord**
2. Wähle deinen Server aus der Liste
3. Der Bot wird automatisch aktiv

!!! warning "Bot muss auf dem Server sein"
    Der Botly Discord-Bot muss auf deinem Server eingeladen sein. Falls er nicht in der Liste erscheint, lade ihn über den Link im Dashboard ein.

## Nächste Schritte

Du hast jetzt einen laufenden Bot. Hier sind ein paar Ideen:

| Feature | Was es macht | Anleitung |
|---------|-------------|-----------|
| **Commands** | Chat-Befehle erstellen | [Commands](../dashboard/twitch/commands.md) |
| **Counter** | Death Counter, Win Counter | [Counter](../dashboard/twitch/counter.md) |
| **AutoMod** | Chat automatisch moderieren | [AutoMod](../dashboard/twitch/automod.md) |
| **Welcome** | Discord-Mitglieder begrüßen | [Welcome](../dashboard/discord/welcome.md) |
| **Reaction Roles** | Rollen per Emoji vergeben | [Reaction Roles](../dashboard/discord/reaction-roles.md) |

??? question "Muss ich den Bot manuell starten?"
    Nein. Der Bot läuft in der Cloud und ist automatisch aktiv sobald du ihn verbunden hast.

??? question "Kosten die ersten Features etwas?"
    Nein. Der Free-Plan enthält unbegrenzte Commands, AutoMod, Giveaways und mehr. Details unter [Pläne & Preise](plaene.md).
