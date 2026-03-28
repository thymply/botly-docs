---
title: Geteilte Features
description: Commands und Features die auf Twitch und YouTube gleichzeitig funktionieren.
---

# Geteilte Features

Einige Features funktionieren plattformübergreifend — ein Command für Twitch und YouTube gleichzeitig.

## Platform-Selector

Bei geteilten Features findest du einen **Platform-Selector** mit drei Optionen:

| Option | Bedeutung |
|--------|-----------|
| **Twitch & YouTube** | Feature auf beiden Plattformen aktiv |
| **Nur Twitch** | Feature nur im Twitch-Chat |
| **Nur YouTube** | Feature nur im YouTube-Chat |

## Welche Features sind geteilt?

| Feature | Plattform-Auswahl | Geteilter Zustand |
|---------|-------------------|-------------------|
| **Commands** | Ja (pro Command) | Gleiche Antwort auf beiden Plattformen |
| **Counter** | Ja (pro Counter) | Gleicher Zählerstand |
| **Giveaway** | Ja | Gemeinsame Teilnehmerliste |
| **Mitspieler** | Ja (in Settings) | Gemeinsame Warteschlange |
| **Regulars** | Ja (pro Regular) | Gleicher Status auf beiden Plattformen |
| **AutoMod** | Getrennt | Separate Einstellungen pro Plattform |

!!! info "AutoMod ist getrennt"
    AutoMod-Einstellungen werden für Twitch und YouTube **separat** gespeichert. Das ist sinnvoll weil die Plattformen unterschiedliche Moderations-Funktionen haben (z.B. kein Timeout auf YouTube).

## Wie es funktioniert

Wenn ein Command auf "Twitch & YouTube" steht:

1. Der Command funktioniert in **beiden** Chats
2. Variablen wie `{user}` werden pro Plattform aufgelöst
3. Der Cooldown gilt plattformübergreifend
4. Counter-Werte sind identisch auf beiden Plattformen
