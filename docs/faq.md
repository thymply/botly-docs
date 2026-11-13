---
title: FAQ & Troubleshooting
description: Häufige Fragen und Lösungen für bekannte Probleme.
---

# FAQ & Troubleshooting

Antworten auf die häufigsten Fragen und Lösungen für bekannte Probleme.

---

## Bot reagiert nicht im Chat

??? question "Der Bot ist online, antwortet aber nicht auf Commands"
    **Prüfe diese Punkte:**

    1. **Bot-Status** — Ist der grüne Punkt sichtbar? Falls grau: Bot-Account neu verbinden
    2. **Command aktiviert?** — Toggle in der Command-Liste prüfen
    3. **Cooldown** — Warte die eingestellten Sekunden ab und versuche es erneut
    4. **Richtiger Kanal** — Ist der Bot im richtigen Twitch-Kanal?
    5. **User-Level** — Hat der testende User die nötige Berechtigung?
    6. **Plattform** — Ist der Command auf der richtigen Plattform aktiv (Twitch/YouTube)?

    Falls nichts hilft: Gehe zu **Twitch Bot** → **Bot-Status** und klicke auf **Neu verbinden**.

## Alerts werden nicht angezeigt

??? question "Alerts werden ausgelöst, aber im Stream nicht sichtbar"
    Alerts laufen über **Overlays** (ab Pro): einen Overlay-Link, den du als Browser-Source in deine Streaming-Software einfügst.

    **Prüfe diese Punkte:**

    1. **Overlay-Link erstellt?** — Unter **Tools** → **Overlays** erzeugst du den Link
    2. **Browser-Source eingerichtet?** — Der Link muss als Browser-Quelle in deiner Streaming-Software eingetragen sein
    3. **Quelle sichtbar?** — Ist die Browser-Quelle in der aktiven Szene sichtbar?
    4. **Alert-Typ aktiv?** — Im Bereich **Alerts** der Twitch- bzw. YouTube-Sektion muss der Typ eingeschaltet sein
    5. **Richtiger Link?** — Dort legst du je Typ fest, welcher Overlay-Link ihn zeigt
    6. **"Herunterfahren wenn nicht sichtbar"** — Ist diese Option der Browser-Quelle aktiv, muss die Quelle sichtbar bleiben

    **Quick-Test:** Klicke im Bereich **Alerts** beim jeweiligen Typ auf **Test** — der Alert sollte in der Browser-Source erscheinen.

## YouTube API Quota aufgebraucht

??? question "YouTube meldet 'quota exceeded' — was tun?"
    **Sofort-Maßnahme:** Warte bis Mitternacht Pacific Time — das Quota wird täglich zurückgesetzt.

    **Langfristig:**

    - Botly nutzt nur kostengünstige API-Calls (1 Unit). Normaler Betrieb verbraucht ca. 750 Units/Tag bei 5 Streamern

    Siehe auch: [YouTube Quota](integrationen/youtube.md)

## Twitch AutoMod vs. Botly AutoMod

??? question "Soll ich Twitchs AutoMod oder Botlys nutzen?"
    **Beides!** Die AutoMods ergänzen sich:

    - **Twitchs AutoMod** — Erkennt Beleidigungen, Hassrede, sexuelle Inhalte (ML-basiert)
    - **Botlys AutoMod** — Erkennt Spam, Links, Caps, Duplikate, Emote-Spam

    **Einziger Konflikt:** Der Link-Filter. Wenn du Botlys `!permit` System nutzen willst, deaktiviere Twitchs "Links von unbekannten Nutzern blockieren" und nutze nur Botlys Link-Filter mit Whitelist.

## Wie viele Commands kann ich erstellen?

??? question "Gibt es ein Limit für Commands?"
    **Nein!** Commands sind in jedem Plan unbegrenzt — auch im Free-Plan.

    Limits gelten nur für: Timer (3 im Free), Counter (1 im Free), Reaction Role Panels (1 im Free) und Editoren (1 im Free).

## Werden meine Daten gelöscht wenn ich kündige?

??? question "Was passiert mit meinen Einstellungen nach einer Kündigung?"
    **Nichts.** Deine Einstellungen bleiben gespeichert. Features die den Free-Plan übersteigen werden **deaktiviert**, nicht gelöscht. Wenn du wieder upgradest, ist alles noch da.

    Nur eine explizite **Konto-Löschung** (unter Abonnement → Konto) entfernt deine Daten — nach einer 30-tägigen Widerrufsfrist.
