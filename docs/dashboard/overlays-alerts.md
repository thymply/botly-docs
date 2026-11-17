---
title: Overlays & Alerts
description: Overlay-Link erstellen, in OBS als Browserquelle einbinden und Alerts für Twitch und YouTube einstellen.
---

# Overlays & Alerts

Mit Overlays zeigt Botly Stream-Events wie neue Follower oder Superchats als Alert direkt in deinem Stream. Du brauchst dafür keine zusätzliche Software: Botly erzeugt einen Overlay-Link, den du in OBS als Browserquelle einfügst.

!!! info "Ab Pro"
    Overlays und Alerts sind ab dem **Pro**-Plan verfügbar (auch in **Premium**). Im Free-Plan zeigt die Overlay-Karte unter **Tools** stattdessen einen Link zum Upgrade.

## Schritt 1: Overlay-Link erstellen

1. Öffne im Dashboard unter **Allgemein** den Bereich **Tools**
2. Gib in der Karte **Overlays** optional eine **Bezeichnung** ein (z. B. "Hauptszene")
3. Klicke auf **Overlay erstellen**

Jeder Link erscheint danach in der Liste mit:

| Anzeige / Knopf | Bedeutung |
|-----------------|-----------|
| **Zuletzt verbunden** | Wann der Link zuletzt geöffnet wurde, z. B. von OBS ("noch nie verbunden", solange er nirgends eingebunden ist) |
| **bedient** | Welche Alert-Typen der Link zeigt ("alle Typen" oder die zugeordneten Typen) |
| **Kopieren** | Kopiert den Link in die Zwischenablage |
| **Neu erzeugen** | Erzeugt einen neuen Link — der alte wird sofort ungültig und muss in OBS ersetzt werden |
| **Widerrufen** | Macht den Link dauerhaft unbrauchbar |

!!! warning "Link geheim halten"
    Wer den Overlay-Link kennt, sieht deine Alerts. Zeige ihn nicht im Stream. Ist er doch öffentlich geworden, klicke auf **Neu erzeugen**.

## Schritt 2: Link in OBS einbinden

1. Klicke beim Overlay-Link auf **Kopieren**
2. Füge in OBS in deiner Szene eine neue Quelle vom Typ **Browser** hinzu
3. Trage den kopierten Link als **URL** ein und bestätige

!!! tip "Quelle sichtbar lassen"
    Ist bei der Browserquelle "Herunterfahren wenn nicht sichtbar" aktiv, muss die Quelle in der aktiven Szene sichtbar sein, damit Alerts erscheinen.

## Schritt 3: Alerts einschalten

Die Alerts stellst du je Plattform ein: **Twitch Bot** → **Alerts** bzw. **YouTube Bot** → **Alerts**. Oben auf der Seite findest du einen Hinweis mit dem Link **Zu den Overlays**, der dich zu **Tools** → **Overlays** führt.

!!! note "Neue Alerts starten ausgeschaltet"
    Neu eingerichtete Alert-Typen sind ausgeschaltet. Schalte nur die Typen ein, die du im Stream sehen willst. Hattest du schon einen Overlay-Link, bevor diese Regel galt, bleiben deine Alerts so eingestellt wie bisher.

Für jeden Typ gibt es eine Zeile mit:

| Einstellung | Beschreibung |
|-------------|-------------|
| **Schalter** | Alert-Typ ein oder aus. Ausgeschaltete Typen sendet Botly gar nicht an das Overlay |
| **Dauer (Sekunden)** | Wie lange der Alert sichtbar bleibt, 2 bis 15 Sekunden |
| **Overlay-Link** | Welcher deiner Links den Typ zeigt (nur wenn du schon einen Link erstellt hast) |
| **Test** | Sendet einen Test-Alert dieses Typs an deine Overlays |

Klicke danach auf **Speichern**. Die Einstellungen gelten für alle deine Overlay-Links.

### Alert-Typen

| Plattform | Typ | Standard-Dauer |
|-----------|-----|----------------|
| Twitch | Neuer Follower | 4 Sekunden |
| Twitch | Neues Abo | 6 Sekunden |
| Twitch | Sub-Geschenk | 6 Sekunden |
| Twitch | Cheer | 6 Sekunden |
| Twitch | Raid | 8 Sekunden |
| Twitch | Kanalpunkte | 4 Sekunden |
| YouTube | Superchat | 6 Sekunden |
| YouTube | Super-Sticker | 6 Sekunden |
| YouTube | Neues Mitglied | 5 Sekunden |

### Mehrere Overlay-Links

Dein ältester Link ist der **Standard-Link** und zeigt alle eingeschalteten Typen. Erstellst du weitere Links (z. B. für eine zweite Szene), ordnest du im Bereich **Alerts** über das Feld **Overlay-Link** einzelne Typen einem dieser Links zu. Ein weiterer Link zeigt dann nur die ihm zugeordneten Typen; ohne Zuordnung zeigt er alle.

## Testen

Klicke beim gewünschten Typ auf **Test** — der Alert erscheint in deiner Browserquelle. Unter **Live-Vorschau** siehst du den Standard-Link direkt im Dashboard, auch ohne OBS (sobald du einen Link erstellt hast).

!!! info "Test bei ausgeschaltetem Typ"
    Ist der Typ ausgeschaltet, sendet Botly keinen Test und zeigt den Hinweis "Dieser Alert ist ausgeschaltet. Schalte ihn ein und speichere, um ihn zu testen." Der Test richtet sich nach den gespeicherten Einstellungen — schalte den Typ also ein und klicke zuerst auf **Speichern**.

## Alerts gestalten (Alert-Editor)

!!! info "Premium"
    Der Alert-Editor ist im **Premium**-Plan enthalten. In Pro öffnet der Knopf **Gestalten** den Hinweis zum Upgrade.

Klicke in der Zeile eines Alert-Typs auf **Gestalten**. Im Dialog stellst du für diesen Typ ein:

| Bereich | Einstellung |
|---------|-------------|
| **Text** | **Titel-Vorlage** (bis 80 Zeichen) und **Text-Vorlage** (bis 200 Zeichen). Leer lassen = Standardtext des Alerts |
| **Aussehen** | **Schrift**, **Position** (neun Stellen, z. B. „Oben Mitte“ oder „Unten rechts“), **Textfarbe**, **Akzentfarbe**, **Hintergrundfarbe** und **Deckkraft des Hintergrunds** |
| **Bild** | Eigenes Bild hochladen (PNG, JPEG, GIF oder WebP, höchstens 5 MB und 4096 × 4096 Pixel), Schalter **Bild anzeigen** |
| **Ton** | **Standard-Ton**, **Kein Ton** oder **Eigener Ton** (MP3, OGG oder WAV, höchstens 2 MB), dazu die **Lautstärke** |

Klicke danach auf **Speichern**. Mit **Test-Alert senden** prüfst du den gespeicherten Stand in OBS. **Zurücksetzen** stellt den Standard-Look wieder her und löscht das hochgeladene Bild und den Ton dieses Typs.

### Variablen

In den Vorlagen setzt Botly echte Werte ein, z. B. den Namen der Person, die gefolgt ist. Ein Klick auf eine Variable im Dialog fügt sie an der Cursorposition ein.

| Typ | Variablen |
|-----|-----------|
| Neuer Follower | `{user}` |
| Neues Abo | `{user}`, `{months}`, `{tier}` |
| Sub-Geschenk | `{user}`, `{amount}`, `{tier}` |
| Cheer | `{user}`, `{amount}`, `{message}` |
| Raid | `{user}`, `{viewers}` |
| Kanalpunkte | `{user}`, `{reward}`, `{cost}`, `{input}` |
| Superchat | `{user}`, `{amount}`, `{currency}`, `{message}` |
| Super-Sticker | `{user}`, `{amount}`, `{currency}` |
| Neues Mitglied | `{user}`, `{months}` |

Beispiel: `{user} hat {amount} Bits gecheert!`

!!! note "Ton in der Live-Vorschau"
    In der **Live-Vorschau** im Dashboard spielt ein Ton erst nach einem Klick in die Vorschau (Regel des Browsers). Prüfe den Ton mit **Test-Alert senden** in deiner OBS-Browserquelle.

### Nach einem Wechsel aus Premium

Wechselst du von Premium auf Pro oder Free, zeigen deine Alerts wieder den Standard-Look. Deine Gestaltung bleibt gespeichert und gilt wieder, sobald du erneut Premium hast. Deine hochgeladenen Dateien siehst du unter **Alerts** in der Karte **Hochgeladene Dateien** und kannst sie dort löschen.

## Wechsel auf Free

Fällt dein Abo auf den Free-Plan zurück, widerruft Botly deine Overlay-Links. Nach einem erneuten Upgrade erstellst du unter **Tools** → **Overlays** einen neuen Link und trägst ihn in OBS ein.

Probleme? Siehe [FAQ: Alerts werden nicht angezeigt](../faq.md#alerts-werden-nicht-angezeigt).
