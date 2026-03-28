---
title: Audit Log
description: Alle Änderungen im Dashboard nachvollziehen — wer hat was wann geändert.
---

# Audit Log

Das Audit Log protokolliert alle Änderungen die im Dashboard vorgenommen werden — Commands erstellen, AutoMod konfigurieren, Editoren einladen und mehr.

## Übersicht

Jeder Eintrag enthält:

| Feld | Beschreibung |
|------|-------------|
| **Zeitpunkt** | Datum und Uhrzeit der Änderung |
| **Benutzer** | Wer die Änderung gemacht hat |
| **Aktion** | Was geändert wurde (z.B. "Command erstellt") |
| **Details** | Name des betroffenen Objekts, alte/neue Werte |

## Zugang

Das Audit Log findest du unter **Allgemein** → **Audit Log** in der Landing-Sidebar. Es ist für den Account-Owner und Editoren mit entsprechender Berechtigung sichtbar.

## Filter

Oben auf der Seite kannst du filtern:

- **Zeitraum** — Letzte 7 Tage, 30 Tage oder 90 Tage
- **Aktions-Typ** — Commands, AutoMod, Regulars, Editoren, Einstellungen

## Protokollierte Aktionen

| Aktion | Beschreibung |
|--------|-------------|
| Command erstellt | Neuer Command oder Keyword angelegt |
| Command bearbeitet | Einstellungen eines Commands geändert |
| Command gelöscht | Command entfernt |
| AutoMod aktualisiert | Filter-Einstellungen geändert |
| Regular hinzugefügt | Neuer Regular-User |
| Editor eingeladen | Neuer Editor hat Zugang erhalten |
| Editor entfernt | Editor-Zugang entzogen |
| Welcome aktualisiert | Begrüßungsnachricht geändert |

!!! info "Automatische Bereinigung"
    Einträge älter als 90 Tage werden automatisch beim App-Start gelöscht. Das Audit Log ist nicht dafür gedacht, dauerhaft Daten zu archivieren — es dient der Nachvollziehbarkeit aktueller Änderungen.

## Paginierung

Das Log zeigt 50 Einträge pro Seite. Mit den Vor/Zurück-Buttons navigierst du durch ältere Einträge.

!!! tip "Wer hat was geändert?"
    Besonders nützlich wenn mehrere Editoren Zugang haben. Du siehst auf einen Blick wer wann welchen Command geändert oder gelöscht hat.
