---
title: Custom Alerts
description: Eigene Alert-Designs für jeden Anlass — über die Standard-Alerts hinaus.
---

# Custom Alerts

Erstelle eigene Alerts die nicht an einen automatischen Trigger gebunden sind — für besondere Anlässe oder als Action-Chain Aktion.

## Wofür Custom Alerts?

Custom Alerts werden **nicht** automatisch bei Events ausgelöst. Stattdessen nutzt du sie in:

- **Action-Chains** — "WENN Kanalpunkte eingelöst → DANN Custom Alert zeigen"
- **Manuell** — Per Button in der Desktop App testen

Das gibt dir volle Kontrolle: Du bestimmst wann und wie der Alert erscheint.

## Custom Alert erstellen

1. Gehe in der Desktop App zu **Alerts**
2. Wähle den Event-Typ **Custom**
3. Klicke auf **+ Variante**
4. Gestalte den Alert wie einen [Standard-Alert](alert-editor.md)
5. Speichern

## Mit Action-Chain verknüpfen

1. Erstelle eine [Action-Chain](action-chains.md) mit dem gewünschten Trigger
2. Füge die Aktion **"Alert anzeigen"** hinzu
3. Wähle deinen Custom Alert aus der Liste
4. Speichern

### Beispiel

> **WENN** Kanalpunkte "Celebration" eingelöst werden
> **DANN** zeige Custom Alert "Party" im Alert-Kanal "celebrations"

!!! tip "Mehrere Custom Alerts"
    Erstelle verschiedene Custom Alerts für verschiedene Anlässe und verknüpfe sie mit unterschiedlichen Triggern.
