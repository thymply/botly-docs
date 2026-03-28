---
title: Duplikate-Erkennung
description: Doppelte Nachrichten und Copy-Paste-Spam automatisch erkennen und löschen.
---

# Duplikate-Erkennung

Erkennt und entfernt automatisch doppelte Nachrichten und Copy-Paste-Spam in deinem Discord.

## Konzept

Die Duplikate-Erkennung vergleicht neue Nachrichten mit kürzlich gesendeten Nachrichten im gleichen Kanal. Wenn ein User die gleiche oder eine sehr ähnliche Nachricht innerhalb eines Zeitfensters erneut postet, wird sie entfernt.

## Einrichtung

1. Gehe zu **Discord** → Server → **Duplikate**
2. Aktiviere die **Duplikate-Erkennung**
3. Konfiguriere den **Ähnlichkeits-Schwellwert** (wie ähnlich müssen Nachrichten sein)
4. Speichern

## Einstellungen

| Einstellung | Beschreibung | Standard |
|------------|-------------|---------|
| Ähnlichkeit | Prozentuale Übereinstimmung | 90% |
| Zeitfenster | Wie weit zurück prüfen | 60 Sekunden |
| Min. Länge | Kurze Nachrichten ignorieren | 10 Zeichen |

!!! tip "Scan & Cleanup"
    Unter "Duplikate" findest du auch einen **Scan**-Button der bestehende Duplikate im Kanal findet und auf einen Klick entfernt.

!!! info "Pro Feature"
    Duplikate-Erkennung ist ab dem Pro-Plan verfügbar.
