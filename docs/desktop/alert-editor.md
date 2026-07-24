---
title: Alert-Editor
description: Stream-Alerts gestalten — Layout, Bilder, Text, Animationen.
---

# Alert-Editor

!!! warning "Botly Desktop wird eingestellt"
    Die Botly Desktop App wird eingestellt. Overlays laufen künftig direkt als Browser-Source im Dashboard — kein Download mehr nötig. Details im [Changelog](../changelog.md).

Gestalte deine Stream-Alerts genau so wie du sie haben willst — mit dem visuellen Editor in der Desktop App.

## Default Alerts

Botly erstellt automatisch einen Default-Alert für jeden Event-Typ:

| Event | Beschreibung |
|-------|-------------|
| **Follow** | Neuer Follower |
| **Subscription** | Neues Abo / Resub |
| **Gift Sub** | Geschenk-Abo |
| **Bits / Cheer** | Bits-Spende |
| **Raid** | Eingehender Raid |
| **Channel Points** | Kanalpunkt-Einlösung |
| **Donation** | Spende über Drittanbieter |

## Alert gestalten

Wähle einen Event-Typ in der linken Spalte und eine **Variante**. Dann konfiguriere:

### Bild

- **Bilddatei** wählen (PNG, GIF, WebP)
- Aus der [Medien-Bibliothek](medien.md) oder vom PC
- Bildgröße wird automatisch angepasst

### Text

| Einstellung | Beschreibung |
|------------|-------------|
| **Nachricht** | Text mit Variablen (z.B. `{username} folgt jetzt!`) |
| **Schriftgröße** | In Pixel |
| **Schriftfarbe** | Farbwähler |
| **Textschatten** | Farbe, Offset, Weichzeichnung |

### Layout

Bestimme wo Bild und Text zueinander stehen:

| Layout | Beschreibung |
|--------|-------------|
| **Oben** | Bild oben, Text unten |
| **Unten** | Text oben, Bild unten |
| **Links** | Bild links, Text rechts |
| **Rechts** | Text links, Bild rechts |
| **Hintergrund** | Bild als Hintergrund, Text darüber |

### Animationen

| Einstellung | Optionen |
|------------|---------|
| **Eingangs-Animation** | Fade In, Slide Down/Up/Left/Right, Zoom, Bounce, Rotate |
| **Eingangs-Dauer** | 0.5-3 Sekunden |
| **Ausgangs-Animation** | Fade Out, Slide, Zoom, Bounce |
| **Ausgangs-Dauer** | 0.5-3 Sekunden |
| **Anzeigedauer** | Wie lange der Alert sichtbar bleibt |

### Sound

- **Sounddatei** wählen (MP3, WAV, OGG)
- **Lautstärke** einstellen
- Wird beim Alert-Start abgespielt

## Live-Vorschau

Die Vorschau zeigt deinen Alert in Echtzeit:

- **Schachbrettmuster** simuliert Transparenz (wie in OBS)
- **Breite/Höhe** Felder unter der Vorschau steuern die Alert-Größe
- Die Vorschau skaliert automatisch wenn der Alert größer als die Bühne ist

Klicke auf **Vorschau** um den Alert mit Animation abzuspielen. **Live testen** sendet den Alert an deine OBS Browser Source.

## Varianten

Du kannst **mehrere Varianten** pro Event erstellen. Bei jedem Auslösen wird zufällig eine Variante gewählt.

1. Wähle einen Event-Typ
2. Klicke auf **+ Variante**
3. Gestalte die neue Variante
4. Optional: **Gewichtung** einstellen (höher = häufiger gewählt)

!!! tip "Abwechslung"
    Erstelle 3-4 Follow-Alert Varianten mit unterschiedlichen Bildern und Sounds. So wirkt dein Stream lebendiger.

## TTS (Text-to-Speech)

Alerts können optional vorgelesen werden:

1. Aktiviere **TTS** in den Alert-Einstellungen
2. Wähle **Sprache** und **Stimme**
3. Passe **Geschwindigkeit** und **Lautstärke** an

TTS nutzt die Browser Speech Synthesis API — keine zusätzlichen Kosten.

## Hintergrund-Layout

Beim Layout **"Hintergrund"** wird das Bild als Hintergrund verwendet und der Text darüber gelegt.

- **Ausrichtung:** Oben, Zentriert oder Unten
- **Alert-Größe:** Passt sich automatisch an die Bildgröße an
- Das Bild füllt den gesamten Alert-Bereich aus

## Responsive Vorschau

Die Vorschau-Bühne passt sich dem verfügbaren Platz an:

- **16:9 Seitenverhältnis** (wie ein OBS-Stream)
- Alert bleibt in seiner **konfigurierten Größe** innerhalb der Bühne
- Wenn der Alert größer als die Bühne ist, wird er automatisch **herunterskaliert** (nie hochskaliert)
- **Breite/Höhe** Felder unter der Vorschau steuern die Alert-Größe (bis 1920x1080)
- Vorschau kann per Button ein-/ausgeblendet werden

!!! info "Alert-Kanäle"
    Für verschiedene Alert-Typen (z.B. Vollbild-Raids vs. kleine Follow-Alerts) kannst du separate OBS Browser Sources nutzen. Siehe [Alert-Kanäle](alert-kanaele.md).
