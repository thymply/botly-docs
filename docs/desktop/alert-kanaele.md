---
title: Alert-Kanäle
description: Mehrere OBS Browser Sources für verschiedene Alert-Typen nutzen.
---

# Alert-Kanäle

Trenne verschiedene Alert-Typen auf eigene OBS Browser Sources auf — für maximale Kontrolle über die Darstellung.

## Konzept

Standardmäßig werden alle Alerts über eine einzige Browser Source angezeigt. Mit Alert-Kanälen kannst du mehrere Browser Sources verwenden:

| Kanal | Browser Source in OBS | Inhalt |
|-------|---------------------|--------|
| **Standard** | `http://localhost:PORT/alerts` | Follow, Sub, Bits |
| **Raids** | `http://localhost:PORT/alerts?channel=raids` | Nur Raids (Vollbild) |
| **Donations** | `http://localhost:PORT/alerts?channel=donations` | Nur Donations |

## Kanal erstellen

1. Gehe zu **Alerts** → **Kanäle**
2. Klicke auf **+ Neuer Kanal**
3. Vergib einen **Namen** (z.B. "raids")
4. Kopiere die **URL**

## In OBS einrichten

1. Erstelle eine neue **Browser Source** in OBS
2. Füge die kopierte **URL** ein
3. Setze **Breite** und **Höhe** passend zu deinem Alert
4. Deaktiviere **"Herunterfahren wenn nicht sichtbar"**

## Alert einem Kanal zuweisen

Im Alert-Editor findest du die Einstellung **"Kanal"** — wähle den gewünschten Kanal für jeden Alert/Variante.

!!! tip "Beispiel-Setup"
    - **Standard-Kanal**: Follow, Sub, Bits (kleine Ecke im Stream)
    - **Raid-Kanal**: Raid Alert (Vollbild-Overlay)
    - **Donation-Kanal**: Donation Alerts (andere Position/Größe)
