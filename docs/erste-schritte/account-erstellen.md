---
title: Account erstellen
description: Login mit Twitch, YouTube oder Discord — in wenigen Sekunden zum Botly-Account.
---

# Account erstellen

Du brauchst kein separates Konto. Logge dich einfach mit einer deiner Streaming-Plattformen ein — Botly erstellt deinen Account automatisch.

## Login-Optionen

Botly unterstützt drei OAuth-Anbieter:

| Plattform | Was wird verbunden |
|-----------|-------------------|
| **Discord** | Dein Discord-Account + Server-Zugriff |
| **Twitch** | Dein Twitch-Account + Kanal-Zugriff |
| **Google** | Dein YouTube-Kanal |

!!! tip "Empfehlung: Discord zuerst"
    Starte mit Discord — die meisten Features (Welcome, AutoMod, Reaction Roles, Live-Ankündigungen) laufen über deinen Discord-Server. Twitch und YouTube kannst du danach jederzeit verknüpfen.

## So erstellst du deinen Account

1. Öffne [botly.thymply.de](https://botly.thymply.de)
2. Klicke auf **Login** (oben rechts)
3. Wähle eine Plattform (Discord, Twitch oder Google)
4. Autorisiere Botly auf der Plattform-Seite
5. Du wirst zurück zum Dashboard geleitet — fertig!

<!-- Screenshot: Login-Seite mit drei Buttons -->

## Was passiert beim ersten Login?

Beim ersten Login erstellt Botly automatisch:

- Deinen **Botly-Account** (verknüpft mit der gewählten Plattform)
- Eine **Free-Subscription** (kostenlos, sofort aktiv)
- Die **Bot-Konfiguration** (leere Datenbank für deine Commands, Counter etc.)

Du landest direkt im Dashboard und kannst sofort loslegen.

## Weitere Plattformen verknüpfen

Nach dem ersten Login kannst du weitere Plattformen verknüpfen:

1. Klicke auf dein **Profilbild** (oben rechts)
2. Unter **Verknüpfte Accounts** siehst du alle Plattformen
3. Klicke auf **Verbinden** neben der gewünschten Plattform
4. Autorisiere Botly

!!! info "Ein Account, alle Plattformen"
    Egal mit welcher Plattform du dich einloggst — du landest immer im selben Account. Alle Verknüpfungen bleiben erhalten.

## Berechtigungen (Scopes)

Botly fragt nur die Berechtigungen an, die es braucht:

**Discord:** Server lesen, Nachrichten senden, Rollen verwalten, Mitglieder sehen

**Twitch:** Chat lesen/schreiben, Kanal-Infos lesen, Clips erstellen, Moderations-Aktionen

**YouTube:** Kanal-Infos lesen, Live-Chat lesen/schreiben

!!! note "Datenschutz"
    Botly speichert nur die nötigen Daten (User-ID, Display-Name, Token). Tokens werden verschlüsselt gespeichert. Details in der [Datenschutzerklärung](../rechtliches/datenschutz.md).

## Häufige Fragen

??? question "Kann ich meinen Account löschen?"
    Ja. Unter **Abonnement** → **Konto** findest du die Option "Konto löschen". Die Löschung erfolgt nach einer 30-tägigen Frist, in der du den Vorgang jederzeit widerrufen kannst.

??? question "Was passiert wenn ich eine Plattform entknüpfe?"
    Die Bot-Konfiguration für diese Plattform bleibt erhalten. Du kannst sie jederzeit wieder verknüpfen und deine Einstellungen sind noch da.
