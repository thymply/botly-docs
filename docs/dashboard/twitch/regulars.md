---
title: Regulars
description: Stammzuschauer verwalten und mit besonderen Rechten belohnen.
---

# Regulars

Regulars sind deine treuesten Zuschauer. Gib ihnen einen besonderen Status — zwischen "Alle" und "Subscriber" in der Berechtigungsstufe.

## Was sind Regulars?

Regulars ist ein **Botly-eigenes User-Level**. Twitch kennt kein "Regular" nativ — es ist eine Botly-Funktion die du selbst verwaltest. Regulars stehen in der Hierarchie über "Everyone" aber unter "Subscriber":

```
Everyone < Regular < Subscriber < VIP < Mod < Broadcaster
```

## Vorteile für Regulars

- **Commands** können auf User-Level "Regular" eingeschränkt werden
- **AutoMod** kann Regulars von bestimmten Filtern ausnehmen
- Du erkennst treue Zuschauer auf einen Blick

## Regulars verwalten

1. Gehe zu **Twitch Bot** → **Regulars**
2. Gib den **Twitch-Username** ein
3. Wähle die **Plattform** (Twitch, YouTube oder Beide)
4. Klicke auf **Hinzufügen**

<!-- Screenshot: Regulars verwalten -->

Zum Entfernen klicke auf das Löschen-Symbol neben dem Namen.

## Regular in Commands nutzen

Beim Erstellen eines Commands kannst du im **User-Level** Dropdown "Regular" auswählen. Dann dürfen nur Regulars (und höher) den Command nutzen.

!!! tip "Exklusive Commands"
    Erstelle Commands nur für Regulars — z.B. `!vip-info` mit Infos zu kommenden Events oder exklusiven Links.

??? question "Werden Regulars automatisch erkannt?"
    Nein. Du musst jeden Regular manuell hinzufügen. Es gibt keine automatische Erkennung basierend auf Watchtime oder Follows.
