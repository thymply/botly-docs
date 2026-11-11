---
title: Giveaway
description: Verlosungen im Chat durchführen — einrichten, Teilnehmer verwalten, Gewinner ziehen.
---

# Giveaway

Starte Verlosungen direkt aus dem Dashboard. Zuschauer nehmen per Keyword im Chat teil, der Bot verkündet den Gewinner. Das Giveaway gilt für Twitch und YouTube (unter **YouTube Bot** → **Giveaway** findest du dieselbe Ansicht).

## Giveaway einrichten

Die Einrichtung hat drei Schritte.

1. **Typ** — Wähle **Keyword**: Wer das Keyword im Chat schreibt, nimmt teil. (Weitere Typen wie *Aktive Chatter* folgen.)
2. **Teilnehmer** — Lege fest, welche Userlevel teilnehmen dürfen: Zuschauer, Regular, VIP, Sub/Mitglied, Moderator. Alle sind vorausgewählt. Auf YouTube zählt ein Kanalmitglied als Sub, VIP gibt es dort nicht.
3. **Einstellungen**
    - **Keyword** — z. B. `!join` (Pflichtfeld)
    - **Spammer entfernen** — Wer das Keyword 4-mal oder öfter schreibt, ist nicht mehr berechtigt.
    - **Nur einmalige Gewinner** — Wer in diesem Stream schon gewonnen hat, kann nicht noch einmal gewinnen.
    - **Chat-Ansage** — Eröffnung, Schließen und Gewinner werden im Chat angesagt.

Unter **Erweiterte Einstellungen** findest du außerdem:

- **Glücks-Multiplikator je Userlevel** (×1 bis ×10) — es zählt der höchste Wert der Rollen, die ein Teilnehmer beim Beitritt hat.
- **Titel**, **Anzahl Gewinner** und **Dauer** (Minuten, 0 = bis du die Teilnahme schließt)
- **Antwortzeit des Gewinners** — so lange hat der Gewinner Zeit, im Chat zu antworten (Standard 60 Sekunden, 10 Sekunden bis 30 Minuten)
- **Plattform** — Twitch, YouTube oder Beide
- die **Chat-Nachrichten** für Eröffnung, Beitritt, Schließen und Gewinner

Klicke auf **Giveaway starten**.

## Während des Giveaways

- Die **Teilnehmerliste** zeigt jeden Teilnehmer mit Userlevel, darüber die Zählung „N Teilnehmer, N berechtigt“. Mit der Suche findest du einzelne Namen.
- Mit dem Schalter **Berechtigt** nimmst du einen Teilnehmer von der Ziehung aus oder holst ihn zurück.
- Bei **Beide** zeigt ein Kennzeichen, ob jemand über Twitch oder YouTube teilnimmt. Bei nur einer Plattform entfällt es.
- **Teilnahme schließen** beendet die Anmeldung. Läuft eine Dauer, schließt Botly sie automatisch.

```
Bot:     Giveaway gestartet! Schreibe !join um teilzunehmen!
Viewer1: !join
Bot:     Viewer1 nimmt teil!
```

!!! info "YouTube"
    Auf YouTube bestätigt der Bot Beitritte nicht einzeln im Chat. Eröffnung, Schließen und Gewinner werden auch dort angesagt.

## Gewinner ziehen

1. Klicke auf **Gewinner ziehen**. Die Teilnahme bleibt dabei offen, bis du sie schließt.
2. Der Gewinner-Dialog zeigt den Namen und zählt die Antwortzeit herunter.
3. Schreibt der Gewinner im Chat, erscheint seine Nachricht im Dialog mit **„Hat geantwortet nach …“**. Antwortet er erst nach Ablauf, steht dort zusätzlich **zu spät**; antwortet er gar nicht, zeigt der Dialog **Keine Antwort**.
4. Mit **Neu ziehen** ziehst du einen anderen Gewinner. Der vorige wird als „neu gezogen“ markiert und nicht noch einmal gezogen.

## Beenden oder Zurücksetzen?

Beide Knöpfe löschen die Teilnehmer und bringen dich zurück zur Einrichtung, deine Einstellungen bleiben als Vorschlag erhalten. Der Unterschied liegt bei den **Gewinnern**:

| | Beenden | Zurücksetzen |
|---|---|---|
| Teilnehmer | gelöscht | gelöscht |
| Gewinner | bleiben gespeichert | werden gelöscht |
| Gedacht für | das normale Ende eines Giveaways | einen Fehlstart, z. B. Testziehung oder falsches Keyword |

Wichtig ist das nur mit **Nur einmalige Gewinner**: Nach **Beenden** kann ein Gewinner in diesem Stream nicht noch einmal gewinnen, nach **Zurücksetzen** schon.

## Datenschutz

Gewinner und ihre Chat-Nachrichten im Gewinner-Dialog werden nach spätestens 7 Tagen gelöscht. Nachrichten des Gewinners werden nur in den ersten 30 Minuten nach der Ziehung aufgezeichnet.

??? question "Kann ich nach dem Beenden noch einen Gewinner ziehen?"
    Nein. Beenden löscht die Teilnehmerliste. Ziehe den Gewinner vorher, gern auch nach **Teilnahme schließen**.
