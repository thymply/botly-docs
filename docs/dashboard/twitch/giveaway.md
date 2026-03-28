---
title: Giveaway
description: Verlosungen im Chat durchführen — erstellen, Teilnahme, Gewinner ziehen.
---

# Giveaway

Starte Verlosungen direkt aus dem Dashboard und lass den Bot den Gewinner im Chat verkünden.

## Giveaway erstellen

1. Gehe zu **Twitch Bot** → **Giveaway**
2. Fülle aus:
   - **Titel** — z.B. "Steam Key Giveaway"
   - **Keyword** — z.B. `!join` (Chat-Befehl zum Teilnehmen)
   - **Min. Level** — Wer darf teilnehmen (Alle, Sub, VIP, Mod)
   - **Plattform** — Twitch, YouTube oder Beide
3. Klicke auf **Giveaway starten**

<!-- Screenshot: Giveaway erstellen -->

## Teilnahme

Nachdem das Giveaway gestartet ist:

```
Bot:     Giveaway gestartet! Schreibe !join um teilzunehmen!
Viewer1: !join
Bot:     Viewer1 nimmt teil! (3 Teilnehmer)
Viewer2: !join
Bot:     Viewer2 nimmt teil! (4 Teilnehmer)
```

!!! info "Duplikat-Schutz"
    Jeder User kann nur einmal teilnehmen. Doppelte `!join` werden ignoriert.

## Gewinner ziehen

1. Klicke auf **Gewinner ziehen** im Dashboard
2. Der Bot verkündet den Gewinner im Chat
3. Optional: Weiteren Gewinner ziehen (falls der erste nicht reagiert)

```
Bot:     Der Gewinner ist... Viewer1! Herzlichen Glückwunsch!
```

## Timer-Giveaway

Du kannst ein Giveaway mit Timer starten — es endet automatisch nach der eingestellten Zeit.

## Plattform-Auswahl

Giveaways können auf Twitch, YouTube oder beiden Plattformen gleichzeitig laufen. Bei "Beide" werden Teilnehmer aus beiden Chats zusammengeführt.

??? question "Was passiert wenn das Giveaway beendet wird ohne Gewinner zu ziehen?"
    Die Teilnehmerliste bleibt gespeichert. Du kannst jederzeit nachträglich einen Gewinner ziehen.
