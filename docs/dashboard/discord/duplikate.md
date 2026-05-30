---
title: Spielvorschläge
description: Doppelte Spielvorschläge in Discord-Kanälen automatisch erkennen und entfernen.
---

# Spielvorschläge

Die **Spielvorschlag-Prüfung** erkennt, wenn dasselbe Spiel mehrfach in einem Discord-Kanal vorgeschlagen wird, und entfernt die doppelte Nachricht automatisch.

## Konzept

In überwachten Kanälen prüft der Bot jede Nachricht auf **Spiel-Store-Links**. Erkennt er einen, extrahiert er den Spielnamen aus der URL und vergleicht ihn mit den bereits vorgeschlagenen Spielen. Liegt die Ähnlichkeit über der eingestellten Schwelle, gilt der Vorschlag als Duplikat: Die Nachricht wird gelöscht und eine Warnung gepostet. Andernfalls wird das Spiel als neuer Vorschlag gemerkt.

### Unterstützte Stores

Der Spielname wird aus Links dieser Plattformen erkannt:

- Steam
- Epic Games
- GOG
- Humble Bundle
- itch.io
- PlayStation Store
- Xbox / Microsoft Store

!!! info "Nur Store-Links werden geprüft"
    Die Prüfung greift nur bei Nachrichten mit einem Spiel-Store-Link. Reiner Text ohne Link wird nicht als Spielvorschlag gewertet.

## Einrichtung

1. Gehe zu **Discord** → Server → **Spielvorschläge**
2. Aktiviere die **Spielvorschlag-Prüfung**
3. Füge unter **Überwachte Kanäle** die Kanäle hinzu, in denen Spielvorschläge gepostet werden
4. Konfiguriere die Einstellungen
5. Klicke auf **Speichern**

## Einstellungen

| Einstellung | Beschreibung | Standard |
|------------|-------------|---------|
| **Warnmodus** | Temporär (Warnung wird nach Ablauf gelöscht) oder Permanent (Warnung bleibt stehen) | Temporär |
| **Anzeigedauer** | Wie lange die temporäre Warnung sichtbar bleibt (5–60 Sekunden) | 15s |
| **Ähnlichkeitsschwelle** | Ab welcher Übereinstimmung ein Spiel als Duplikat gilt (50–100 %) | 80 % |
| **Warnungsnachricht** | Text, der bei einem erkannten Duplikat gepostet wird | siehe unten |
| **Überwachte Kanäle** | Kanäle, in denen die Prüfung aktiv ist | — |

## Warnungsnachricht

Die Nachricht, die der Bot postet, wenn ein doppelter Spielvorschlag entfernt wurde.

### Verfügbare Variablen

| Variable | Beschreibung |
|----------|-------------|
| `{mention}` | @Mention des Users, der das Duplikat gepostet hat |
| `{game}` | Name des erkannten Spiels |
| `{original}` | User, der das Spiel zuerst vorgeschlagen hat |
| `{count}` | Anzahl der bereits bekannten Spiele |
| `{link}` | Link zum ursprünglichen Vorschlag |

### Standard-Text

```
{mention} Das Spiel **{game}** wurde bereits vorgeschlagen! {link}
```

## Bestandsscan

Mit dem **Bestandsscan** kannst du bereits vorhandene Spielvorschläge in den überwachten Kanälen einlesen, damit die Prüfung auch ältere Vorschläge kennt.

1. Wähle den **Zeitraum** (1, 3, 6 oder 12 Monate)
2. Klicke auf **Scan starten**

Der Bot liest die Nachrichten-Historie der überwachten Kanäle und merkt sich die gefundenen Spiele.

!!! tip "Aufräumen"
    Ein Cleanup entfernt gemerkte Spiele, deren ursprüngliche Nachricht inzwischen gelöscht wurde — so bleibt die Liste der bekannten Vorschläge aktuell.

!!! info "Pro-Feature"
    Die Spielvorschlag-Prüfung ist ab dem Pro-Plan verfügbar.
