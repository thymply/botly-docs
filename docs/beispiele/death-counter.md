---
title: Death Counter mit Auto-Switch
description: Automatischer Zähler der sich pro Spiel den Stand merkt.
---

# Death Counter mit Auto-Switch

Ein Death Counter der automatisch den Wert pro Twitch-Kategorie wechselt — perfekt für Soulslike-Spiele.

## Voraussetzungen

- Botly-Account (Free reicht für 1 Counter)
- Twitch Bot verbunden

## Schritt für Schritt

### 1. Counter erstellen

1. Gehe zu **Twitch Bot** → **Counter**
2. Klicke auf **Neuer Counter**
3. Einstellungen:
   - **Name:** `death`
   - **Startwert:** `0`
   - **Auto-Switch:** Aktiviert
   - **Plattform:** Beide

### 2. Nachrichten anpassen

- **Erhöhen:** `RIP! Tod Nr. {value} in {game}.`
- **Abfrage:** `{name}: {value} Tode in {game}`
- **Zurücksetzen:** `{name} in {game} zurückgesetzt.`

### 3. Im Stream nutzen

```
Mod:     !death+
Bot:     RIP! Tod Nr. 48 in Elden Ring.

Viewer:  !death
Bot:     Death Counter: 48 Tode in Elden Ring

# Kategorie-Wechsel zu Sekiro...

Viewer:  !death
Bot:     Death Counter: 23 Tode in Sekiro
```

## Ergebnis

Der Counter merkt sich den Wert pro Spiel. Wenn du zwischen Elden Ring (48 Tode) und Sekiro (23 Tode) wechselst, wird automatisch der richtige Wert geladen.
