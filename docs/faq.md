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

## OBS-Verbindung schlägt fehl

??? question "Die Desktop App kann sich nicht mit OBS verbinden"
    **Prüfe diese Punkte:**

    1. **OBS läuft?** — OBS muss gestartet sein bevor die Desktop App verbindet
    2. **WebSocket aktiv?** — In OBS: Extras → WebSocket-Server Einstellungen → aktiviert?
    3. **Port korrekt?** — Standard ist `4455`. Prüfe ob der Port in OBS und Desktop App übereinstimmt
    4. **Passwort korrekt?** — Falls ein Passwort gesetzt ist, muss es exakt übereinstimmen
    5. **Firewall** — Lokale Firewall blockiert Port 4455? Ausnahme hinzufügen
    6. **OBS Version** — obs-websocket 5.x ist ab OBS Studio 28 eingebaut. Ältere Versionen brauchen das Plugin manuell

## Alerts werden nicht angezeigt

??? question "Alerts werden ausgelöst, aber im Stream nicht sichtbar"
    **Prüfe diese Punkte:**

    1. **Browser Source in OBS?** — Hast du eine Browser Source mit der Alert-URL erstellt?
    2. **URL korrekt?** — Die URL findest du in der Desktop App unter Alerts → Kanäle
    3. **Quelle sichtbar?** — Ist die Browser Source in OBS sichtbar (Auge-Symbol)?
    4. **Desktop App läuft?** — Die App muss im Hintergrund laufen
    5. **Alert-Kanal** — Ist der Alert dem richtigen Kanal zugewiesen?
    6. **"Herunterfahren wenn nicht sichtbar"** — Diese OBS-Option muss **deaktiviert** sein

    **Quick-Test:** Klicke in der Desktop App auf **Live testen** — der Alert sollte in der Browser Source erscheinen.

## YouTube API Quota aufgebraucht

??? question "YouTube meldet 'quota exceeded' — was tun?"
    **Sofort-Maßnahme:** Warte bis Mitternacht Pacific Time — das Quota wird täglich zurückgesetzt.

    **Langfristig:**

    - Botly nutzt nur kostengünstige API-Calls (1 Unit). Normaler Betrieb verbraucht ca. 750 Units/Tag bei 5 Streamern
    - Falls du CrossChat sehr intensiv nutzt, kann das Quota schneller aufgebraucht sein
    - Erstelle ggf. einen zweiten API Key in der Google Cloud Console

    Siehe auch: [YouTube Quota](integrationen/youtube.md)

## Desktop App startet nicht

??? question "Die Desktop App zeigt einen Fehler beim Start"
    **Häufige Ursachen:**

    1. **Fehlende Module** — Lade die neueste Version herunter und installiere sie neu
    2. **Token ungültig** — Lösche die Config-Datei unter `%LOCALAPPDATA%\BotlyDesktop\config.ini` und starte neu
    3. **Port belegt** — Falls ein anderes Programm Port 4455 nutzt, ändere den OBS-Port
    4. **Windows Defender** — Füge `BotlyDesktop.exe` als Ausnahme hinzu falls sie blockiert wird

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
