---
title: Welcome-Nachrichten
description: Neue Mitglieder automatisch in deinem Discord-Server begrüßen.
---

# Welcome-Nachrichten

Begrüße neue Mitglieder automatisch mit einer personalisierten Nachricht — im Willkommenskanal oder per DM.

## Einrichtung

1. Gehe zu **Discord** → Wähle deinen Server → **Willkommensnachrichten**
2. Wähle den **Willkommenskanal** (z.B. #willkommen)
3. Schreibe deine **Begrüßungsnachricht**
4. Optional: **Verabschiedungs-Nachricht** wenn jemand den Server verlässt
5. Speichern

## Variablen

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `{user}` | @Mention des neuen Mitglieds | @CoolViewer |
| `{username}` | Name ohne Mention | CoolViewer |
| `{server}` | Server-Name | Thymply's Community |
| `{membercount}` | Aktuelle Mitgliederzahl | 1.234 |

### Beispiel

```
Willkommen {user} auf {server}! Du bist Mitglied Nr. {membercount}!
Schau dir unsere Regeln in #regeln an und hol dir deine Rollen in #rollen.
```

!!! tip "Leave-Nachricht"
    Die Verabschiedungs-Nachricht kann im selben oder einem anderen Kanal gepostet werden. Lass sie leer um keine Nachricht zu senden.
