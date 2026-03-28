---
title: Discord
description: Discord Bot-Integration, Berechtigungen und Server-Einrichtung.
---

# Discord Integration

Wie du den Botly Discord-Bot zu deinem Server hinzufügst und die nötigen Berechtigungen einrichtest.

## Bot einladen

1. Logge dich im Botly Dashboard ein
2. Wähle **Discord**
3. Falls der Bot nicht auf deinem Server ist, klicke auf den **Einladungslink**
4. Wähle deinen Server und bestätige die Berechtigungen

## Berechtigungen

Der Bot benötigt folgende Discord-Berechtigungen:

| Berechtigung | Wofür |
|-------------|-------|
| Nachrichten senden | Chat, Welcome, Ankündigungen |
| Nachrichten verwalten | AutoMod (Löschen) |
| Rollen verwalten | Reaction Roles |
| Kanäle verwalten | Temp-Voice |
| Reaktionen hinzufügen | Reaction Roles |
| Mitglieder sehen | Welcome (Membercount) |
| Embed-Links | Rich Embeds für Ankündigungen |
| Dateien anhängen | Bilder in Embeds |

## Bot-Hierarchie

!!! warning "Rolle Position"
    Die Botly-Rolle muss in der Server-Hierarchie **über** allen Rollen stehen die sie verwalten soll (Reaction Roles, AutoMod). Ziehe die Botly-Rolle in den Server-Einstellungen nach oben.

## Mehrere Server

| Plan | Server |
|------|--------|
| Free | 1 |
| Pro | 3 |
| Premium | 5 |
