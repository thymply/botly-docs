---
title: Berechtigungen
description: Welche Berechtigungen Botly auf Discord, Twitch und YouTube benötigt und warum.
---

# Berechtigungen

Botly fordert nur die Berechtigungen an die tatsächlich für bestimmte Features gebraucht werden — keine Administrator-Rechte.

## Discord

### Bot-Berechtigungen

Beim Einladen des Bots wirst du nach folgenden Berechtigungen gefragt:

| Berechtigung | Feature | Ohne diese Berechtigung... |
|---|---|---|
| **Kanäle ansehen** | Grundvoraussetzung | ...kann der Bot keinen Kanal sehen oder darauf reagieren. |
| **Nachrichten senden** | Chat, Welcome, Ankündigungen, Tickets | ...kann der Bot keine Nachrichten schreiben — weder Willkommen, noch Ankündigungen oder Ticket-Antworten. |
| **Nachrichten verwalten** | AutoMod, `/wipe` Command | ...kann der AutoMod regelwidrige Nachrichten nur melden aber nicht löschen. Der `/wipe` Command funktioniert nicht. |
| **Nachrichtenverlauf lesen** | `/wipe` Command | ...kann der `/wipe` Command keine älteren Nachrichten finden und löschen. |
| **Embed-Links** | Alle Embeds (Ankündigungen, Welcome, etc.) | ...werden Embeds nicht dargestellt. Der Bot kann nur einfachen Text senden. |
| **Dateien anhängen** | Bilder in Embeds | ...können keine Bilder in Embeds eingebettet werden. |
| **Reaktionen hinzufügen** | Reaction Roles | ...kann der Bot keine Reaktionen zu Nachrichten hinzufügen. Reaction Roles funktionieren nicht. |
| **Externe Emojis verwenden** | Reaction Roles mit Server-Emojis | ...kann der Bot nur Standard-Emojis für Reaction Roles verwenden, keine Custom-Emojis von anderen Servern. |
| **Rollen verwalten** | Reaction Roles, Live-Rolle | ...kann der Bot keine Rollen vergeben oder entfernen. Reaction Roles und die automatische Live-Rolle funktionieren nicht. |
| **Kanäle verwalten** | Temp-Voice | ...kann der Bot keine temporären Voice-Kanäle erstellen, umbenennen oder löschen. |
| **Verbinden** | Temp-Voice | ...kann der Bot dem Voice-Kanal nicht beitreten um temporäre Kanäle zu verwalten. |
| **Mitglieder verschieben** | Temp-Voice | ...kann der Bot Mitglieder nicht in den neuen temporären Voice-Kanal verschieben. |
| **Mitglieder kicken** | AutoMod Eskalation | ...kann der AutoMod bei wiederholten Verstößen Mitglieder nicht vom Server kicken. Timeouts funktionieren weiterhin. |
| **Mitglieder moderieren** | AutoMod Eskalation | ...kann der AutoMod keine Timeouts vergeben. Nachrichten können weiterhin gelöscht werden. |
| **Threads verwalten** | Thread-Unterstützung | ...kann der Bot keine Threads erstellen oder moderieren. |
| **In Threads schreiben** | Thread-Unterstützung | ...kann der Bot nicht in Threads antworten. |

### OAuth2 Scopes

| Scope | Bedeutung |
|---|---|
| `bot` | Ermöglicht dem Bot, deinem Server beizutreten |
| `applications.commands` | Ermöglicht Slash Commands (`/vcname`, `/wipe`, etc.) |

!!! warning "Rollenhierarchie"
    Die Botly-Rolle muss in den Server-Einstellungen **über** allen Rollen stehen die sie verwalten soll. Sonst können Reaction Roles und AutoMod-Aktionen gegen Mitglieder mit höheren Rollen nicht ausgeführt werden.

---

## Twitch

### Bot-Account Scopes

Wenn du einen Twitch-Account als Bot verbindest, fordert Botly folgende Berechtigungen an:

| Scope | Feature | Beschreibung |
|---|---|---|
| `chat:read` | Chat lesen | Bot kann Chat-Nachrichten lesen um auf Commands zu reagieren |
| `chat:edit` | Chat schreiben | Bot kann Antworten und Nachrichten im Chat senden |
| `moderator:manage:banned_users` | AutoMod | Bot kann User bannen oder entbannen (Eskalation) |
| `moderator:manage:chat_messages` | AutoMod | Bot kann einzelne Nachrichten löschen |
| `moderator:manage:chat_settings` | AutoMod | Bot kann Chat-Einstellungen anpassen (z.B. Slow Mode) |
| `moderator:read:chatters` | Viewer-Liste | Bot kann die aktuelle Chatter-Liste lesen |

!!! info "Bot als Moderator"
    Der Bot-Account muss in deinem Twitch-Kanal als **Moderator** eingetragen sein (`/mod botly` im Chat), damit die Moderations-Scopes wirksam werden.

---

## YouTube / Google

### OAuth Scopes

Beim Verbinden deines YouTube-Accounts fordert Botly folgende Google-Berechtigungen an:

| Scope | Feature | Beschreibung |
|---|---|---|
| `youtube` | Kanal lesen | Kanal-Informationen und Livestream-Status abrufen |
| `youtube.force-ssl` | Chat schreiben | Nachrichten im Live-Chat senden und User bannen (AutoMod) |
| `openid` | Login | Sichere Identifikation deines Google-Accounts |
| `email` | Login | E-Mail-Adresse für Account-Zuordnung |
| `profile` | Login | Anzeigename und Profilbild |

!!! tip "Was Botly NICHT kann"
    Botly hat **keinen** Zugriff auf:

    - Video-Upload oder -Löschung
    - Kanal-Einstellungen ändern
    - Abonnenten oder Analytics einsehen
    - YouTube Studio Funktionen

!!! success "Von Google verifiziert"
    Botly wurde von Google überprüft und als vertrauenswürdige App verifiziert. Du siehst beim Login keinen "Unverified App" Warnbildschirm.

---

## Daten & Datenschutz

- Botly speichert nur die Daten die für den Bot-Betrieb nötig sind
- OAuth-Tokens werden verschlüsselt gespeichert
- Du kannst jederzeit alle Verknüpfungen im Dashboard unter **Einstellungen** lösen
- Vollständige Datenlöschung ist unter **Einstellungen** → **DSGVO** möglich
- Details in der [Datenschutzerklärung](../rechtliches/datenschutz.md)
