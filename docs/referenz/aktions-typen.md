---
title: Aktions-Typen
description: Alle 30+ verfügbaren Aktionen für Action-Chains — Chat, OBS, Alerts und mehr.
---

# Aktions-Typen

Vollständige Referenz aller Aktionen die du in Action-Chains verwenden kannst.

## Chat-Aktionen

| Aktion | Beschreibung | Parameter |
|--------|-------------|-----------|
| **Chat-Nachricht** | Nachricht im Chat senden | Text, Plattform |
| **Ankündigung** | Twitch Announcement | Text, Farbe |
| **Shoutout** | Twitch Shoutout | Username |
| **Antworten** | Auf die auslösende Nachricht antworten | Text |

## OBS-Aktionen

| Aktion | Beschreibung | Parameter |
|--------|-------------|-----------|
| **Szene wechseln** | Zu einer OBS-Szene wechseln | Szenen-Name |
| **Quelle ein/aus** | Sichtbarkeit einer Quelle | Szene, Quelle, Ein/Aus |
| **Filter ein/aus** | Filter aktivieren/deaktivieren | Quelle, Filter, Ein/Aus |
| **Screenshot** | Screenshot der aktuellen Szene | — |
| **Aufnahme starten** | OBS-Aufnahme starten | — |
| **Aufnahme stoppen** | OBS-Aufnahme stoppen | — |

## Alert-Aktionen

| Aktion | Beschreibung | Parameter |
|--------|-------------|-----------|
| **Alert anzeigen** | Alert im Browser Source zeigen | Alert-Name, Kanal |
| **Sound abspielen** | Audio-Datei abspielen | Datei, Lautstärke |
| **TTS** | Text-to-Speech Nachricht | Text, Stimme, Lautstärke |

## Steuerungs-Aktionen

| Aktion | Beschreibung | Parameter |
|--------|-------------|-----------|
| **Warten** | X Sekunden pausieren | Sekunden |
| **Counter erhöhen** | Counter-Wert hochzählen | Counter, Menge |
| **Counter verringern** | Counter-Wert runterzählen | Counter, Menge |
| **Counter setzen** | Counter auf Wert setzen | Counter, Wert |
| **Variable setzen** | Eigene Variable speichern | Name, Wert |
| **Variable lesen** | Wert einer Variable abrufen | Name |
| **Zufallszahl** | Zufällige Zahl generieren | Min, Max |

## Erweiterte Aktionen

| Aktion | Beschreibung | Parameter |
|--------|-------------|-----------|
| **HTTP Request** | Externe API aufrufen | URL, Methode, Body |
| **Datei lesen** | Lokale Textdatei lesen | Pfad |
| **Datei schreiben** | In lokale Textdatei schreiben | Pfad, Inhalt |
| **Programm starten** | Externe Anwendung starten | Pfad, Argumente |
| **Twitch Clip** | Clip erstellen | — |
| **Twitch Titel** | Stream-Titel ändern | Neuer Titel |
| **Twitch Kategorie** | Spielkategorie ändern | Kategorie |

!!! tip "Aktionen verketten"
    Aktionen werden von oben nach unten ausgeführt. Nutze "Warten" um Pausen einzubauen. Beispiel: Quelle einblenden → 5 Sek. warten → Quelle ausblenden.
