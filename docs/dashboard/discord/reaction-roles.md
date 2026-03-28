---
title: Reaction Roles
description: Discord-Rollen per Reaktion auf eine Nachricht vergeben.
---

# Reaction Roles

Lass deine Mitglieder sich selbst Rollen zuweisen indem sie auf eine Nachricht reagieren.

## Konzept

Du erstellst ein **Rollen-Panel** — eine Nachricht mit Emojis. Jedes Emoji ist mit einer Discord-Rolle verknüpft. Wenn ein Mitglied auf das Emoji reagiert, bekommt es die Rolle. Reaktion entfernen = Rolle entfernen.

## Panel erstellen

1. Gehe zu **Discord** → Server → **Reaction Roles**
2. Klicke auf **Neues Panel**
3. Wähle den **Kanal** für die Nachricht
4. Vergib einen **Titel** und optional eine **Beschreibung**
5. Füge **Emoji-Rolle Paare** hinzu (bis zu 20 pro Panel)
6. Klicke auf **Erstellen**

Der Bot sendet eine Embed-Nachricht im gewählten Kanal mit allen Emojis.

<!-- Screenshot: Reaction Roles Panel -->

## Emoji-Rolle Paare

Für jedes Paar wählst du:

- **Emoji** — Standard-Emoji oder Custom-Emoji deines Servers
- **Rolle** — Die Discord-Rolle die vergeben wird

!!! warning "Bot-Rolle Hierarchie"
    Der Bot kann nur Rollen vergeben die **unter** seiner eigenen Rolle in der Server-Hierarchie stehen. Stelle sicher dass die Botly-Rolle über den Rollen steht die vergeben werden sollen.

## Tipps

!!! tip "Kategorien erstellen"
    Erstelle mehrere Panels für verschiedene Kategorien: Spiele, Benachrichtigungen, Farben etc.

!!! tip "Max. 20 Emojis"
    Discord erlaubt maximal 20 Reaktionen pro Nachricht. Für mehr Rollen erstelle ein zweites Panel.

!!! info "Free-Plan: max. 1 Panel"
    Im Free-Plan kannst du ein Reaction Role Panel erstellen. Ab Pro gibt es kein Limit.
