---
title: Kanalpunkte
description: Kanalpunkte-Belohnungen im Dashboard anlegen und bearbeiten, je Belohnung Overlay-Alert und Chat-Antwort einstellen.
---

# Kanalpunkte

Im Bereich **Kanalpunkte** verwaltest du die Belohnungen deines Twitch-Kanals direkt im Dashboard. Für jede Belohnung legst du außerdem fest, ob beim Einlösen ein Overlay-Alert erscheint, mit welchem Text, und ob der Bot im Chat antwortet.

!!! info "Ab Pro"
    Kanalpunkte sind ab dem **Pro**-Plan verfügbar (auch in **Premium**). Im Free-Plan zeigt der Bereich einen Hinweis mit Link zum Upgrade.

!!! note "Nur für Affiliates und Partner"
    Kanalpunkte gibt es bei Twitch nur für Affiliates und Partner. Ist dein Kanal keins von beiden, zeigt Botly einen Hinweis statt der Liste.

## Belohnungen verwalten

1. Gehe zu **Twitch Bot** → **Kanalpunkte**
2. Klicke auf **+ Neue Belohnung** oder beim gewünschten Eintrag auf das Stift-Symbol
3. Fülle die Felder aus und klicke auf **Speichern**

| Feld | Beschreibung |
|------|-------------|
| **Titel** | Name der Belohnung, höchstens 45 Zeichen |
| **Kosten (Kanalpunkte)** | Preis in Kanalpunkten, mindestens 1 |
| **Beschreibung für Zuschauer** | Erklärung der Belohnung, höchstens 200 Zeichen |
| **Belohnung aktiv** | Aus = die Belohnung ist auf Twitch pausiert |
| **Zuschauer muss einen Text eingeben** | Zuschauer schreiben beim Einlösen einen Text (z. B. einen Songwunsch) |
| **Cooldown aktiv** / **Cooldown (Sekunden)** | Wartezeit, bis die Belohnung wieder eingelöst werden kann, 1 bis 604800 Sekunden |

Mit dem Papierkorb-Symbol löschst du eine Belohnung auf Twitch. Botly fragt vorher nach.

### Belohnungen, die nicht mit Botly angelegt wurden

Twitch erlaubt Änderungen nur an Belohnungen, die mit derselben Anwendung angelegt wurden. Belohnungen, die du auf Twitch oder mit einem anderen Werkzeug erstellt hast, tragen den Hinweis **Nicht von Botly**:

- Titel, Kosten, Beschreibung und Löschen änderst du für sie nur auf Twitch.
- Overlay-Alert und Chat-Antwort stellst du auch für sie in Botly ein.

## Overlay-Alert je Belohnung

| Einstellung | Beschreibung |
|-------------|-------------|
| **Overlay-Alert zeigen** | Aus = für diese Belohnung erscheint kein Alert |
| **Eigener Alert-Text (optional)** | Text, den der Alert statt der Standardanzeige zeigt. Leer = Standard-Alert |

!!! warning "Hauptschalter unter Alerts"
    Ein Kanalpunkte-Alert erscheint nur, wenn der Typ **Kanalpunkte** unter **Twitch Bot** → **Alerts** eingeschaltet ist. Die Einstellung je Belohnung kann einzelne Belohnungen ausschalten oder ihren Text ändern. Mehr zu Overlays: [Overlays & Alerts](../overlays-alerts.md).

Belohnungen ohne eigene Einstellung zeigen den Alert wie bisher.

## Chat-Antwort je Belohnung

Schalte **Bot antwortet im Chat** ein und trage die **Chat-Antwort** ein (höchstens 400 Zeichen). Bei jeder Einlösung schreibt der Bot diesen Text in deinen Chat, über dasselbe Konto wie deine Commands.

## Variablen

| Variable | Beschreibung | Alert-Text | Chat-Antwort |
|----------|-------------|:---:|:---:|
| `{user}` | Name der Person, die eingelöst hat | ✓ | ✓ |
| `{reward}` | Titel der Belohnung | ✓ | ✓ |
| `{input}` | Text, den die Person beim Einlösen eingegeben hat | ✓ | ✓ |
| `{cost}` | Kosten in Kanalpunkten | ✓ | ✓ |

In der Chat-Antwort gehen außerdem alle [Command-Variablen](../../referenz/variablen.md), zum Beispiel `{followage}` oder `{uptime}`.

Beispiel: `Danke {user}! {reward} für {cost} Punkte ist notiert: {input}`

## Editoren

Editoren mit dem Recht **Kanalpunkte** sehen und bearbeiten diesen Bereich für deinen Kanal. Ohne das Recht zeigt Botly ihnen einen Hinweis. Rechte vergibst du unter [Editoren](editoren.md).
