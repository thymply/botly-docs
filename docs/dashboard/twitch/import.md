---
title: Bot-Import
description: Commands, Timer und Einstellungen von Nightbot, Fossabot, Moobot, StreamElements oder Streamlabs importieren.
---

# Bot-Import

Du wechselst von einem anderen Bot zu Botly? Kein Problem — importiere deine bestehenden Commands mit wenigen Klicks.

## Unterstützte Quellen

| Quelle | Methode | Commands | Timer | Regulars | AutoMod |
|--------|---------|:--------:|:-----:|:--------:|:-------:|
| **Nightbot** | OAuth (automatisch) | ✓ | ✓ | ✓ | ✓ |
| **Fossabot** | Datei-Upload (JSON) | ✓ | — | — | — |
| **Moobot** | Datei-Upload (JSON) | ✓ | — | — | — |
| **StreamElements** | Datei-Upload (CSV) | ✓ | — | — | — |
| **Streamlabs Chatbot** | Datei-Upload (CSV) | ✓ | — | — | — |
| **CSV (manuell)** | Datei-Upload (CSV) | ✓ | — | — | — |

---

## Nightbot

Der Nightbot-Import ist der umfangreichste — er holt automatisch alles über OAuth.

### Voraussetzungen

- Du bist bei Nightbot mit dem gleichen Twitch-Account eingeloggt
- Nightbot OAuth ist in Botly konfiguriert (Standard bei botly.thymply.de)

### Schritt für Schritt

1. Gehe zu **Twitch Bot** → **Commands**
2. Klicke auf **Import** (oben rechts)
3. Wähle **Nightbot**
4. Klicke auf **Mit Nightbot verbinden**
5. Du wirst zu Nightbot weitergeleitet — bestätige den Zugriff
6. Zurück in Botly siehst du eine **Vorschau** aller gefundenen Daten:
    - **Commands** mit konvertierten Variablen
    - **Timer** (werden als Auto-Timer-Commands importiert)
    - **Regulars** (deine Stammzuschauer)
    - **Spam Protection** (wird in AutoMod-Einstellungen übernommen)
7. Wähle aus was du importieren möchtest
8. Klicke auf **Importieren**

### Variablen-Konvertierung

Nightbot-Variablen werden automatisch in Botly-Variablen umgewandelt:

| Nightbot | Botly | Beschreibung |
|----------|-------|-------------|
| `$(user)` | `{user}` | Benutzername |
| `$(channel)` | `{channel}` | Kanalname |
| `$(query)` | `{query}` | Text nach dem Command |
| `$(touser)` | `{touser}` | Erwähnter User oder Absender |
| `$(count)` | `{count}` | Aufruf-Zähler (gesamt) |
| `$(uptime)` | `{uptime}` | Stream-Laufzeit |
| `$(title)` | `{title}` | Stream-Titel |
| `$(game)` | `{game}` | Aktuelle Kategorie |
| `$(followage)` | `{followage}` | Follow-Dauer |
| `$(watchtime)` | `{watchtime}` | Zuschauzeit |
| `$(userlevel)` | `{userlevel}` | Berechtigungsstufe |
| `$(urlfetch URL)` | `{urlfetch:URL}` | URL-Abruf |
| `$(urlfetch json URL)` | `{urlfetch_json:URL}` | JSON-URL-Abruf |
| `$(customapi URL)` | `{urlfetch:URL}` | Custom API Abruf |
| `$(time ZONE)` | `{time:ZONE}` | Uhrzeit |
| `$(countdown DATUM)` | `{countdown:DATUM}` | Countdown |

!!! warning "Nicht unterstützte Variablen"
    Folgende Nightbot-Variablen können nicht konvertiert werden und der Command wird beim Import **deaktiviert**:

    - `$(eval ...)` — JavaScript-Ausdrücke
    - `$(random ...)` — Zufallswerte

    Du kannst diese Commands nach dem Import manuell anpassen.

### Permission-Level Mapping

| Nightbot | Botly |
|----------|-------|
| Owner | Broadcaster |
| Moderator / Supermoderator | Mod |
| Twitch VIP | VIP |
| Subscriber | Subscriber |
| Regular | Regular |
| Everyone | Alle |

---

## Fossabot

### Export aus Fossabot

1. Öffne das **Fossabot Dashboard**
2. Gehe zu **Commands**
3. Klicke auf **Export** → Lade die JSON-Datei herunter

### Import in Botly

1. Gehe zu **Twitch Bot** → **Commands** → **Import**
2. Wähle **Fossabot**
3. Lade die JSON-Datei hoch
4. Prüfe die Vorschau — Variablen werden automatisch konvertiert
5. Klicke auf **Importieren**

!!! info "Unterstützte Variablen"
    Fossabot nutzt die gleiche `$(variable)` Syntax wie Nightbot. Die meisten Variablen werden automatisch konvertiert. `$(eval ...)` wird nicht unterstützt.

---

## Moobot

### Export aus Moobot

1. Öffne das **Moobot Dashboard**
2. Gehe zu **Commands**
3. Exportiere die Commands als JSON-Datei

### Import in Botly

1. Gehe zu **Twitch Bot** → **Commands** → **Import**
2. Wähle **Moobot**
3. Lade die JSON-Datei hoch
4. Prüfe die Vorschau
5. Klicke auf **Importieren**

### Variablen-Konvertierung (Moobot)

Moobot nutzt ein eigenes Format mit Unterstrichen:

| Moobot | Botly |
|--------|-------|
| `_USER_` | `{user}` |
| `_CHANNEL_` | `{channel}` |
| `_QUERY_` | `{query}` |
| `_COUNT_` | `{count}` |
| `_UPTIME_` | `{uptime}` |
| `_GAME_` | `{game}` |
| `_TITLE_` | `{title}` |

!!! warning "Nicht unterstützt"
    `_RANDOM_`, `_GAME_FOR_`, `_SUBCOUNT_`, `_VIEWERS_` werden nicht konvertiert.

---

## StreamElements

### Export aus StreamElements

1. Öffne das **StreamElements Dashboard**
2. Gehe zu **Chat Bot** → **Chat Commands**
3. Exportiere die Commands als CSV-Datei

### Import in Botly

1. Gehe zu **Twitch Bot** → **Commands** → **Import**
2. Wähle **StreamElements**
3. Lade die CSV-Datei hoch
4. Prüfe die Vorschau
5. Klicke auf **Importieren**

StreamElements nutzt die `$(variable)` Syntax — die Konvertierung funktioniert wie bei Nightbot.

---

## Streamlabs Chatbot

### Export aus Streamlabs

1. Öffne den **Streamlabs Chatbot**
2. Gehe zu **Commands**
3. Exportiere als CSV-Datei

### Import in Botly

1. Gehe zu **Twitch Bot** → **Commands** → **Import**
2. Wähle **Streamlabs**
3. Lade die CSV-Datei hoch
4. Prüfe die Vorschau
5. Klicke auf **Importieren**

Streamlabs-spezifische Variablen wie `{user.name}` werden automatisch zu `{user}` konvertiert.

---

## Manueller CSV-Import

Du kannst Commands auch aus einer eigenen CSV-Datei importieren.

### CSV-Format

- **Encoding:** UTF-8 (mit oder ohne BOM)
- **Trennzeichen:** Semikolon `;`, Tab oder Komma `,` (wird automatisch erkannt)
- **Maximale Dateigröße:** 2 MB

### Spalten

| Spalte | Alternativen | Pflicht | Beschreibung |
|--------|-------------|:-------:|-------------|
| `command` | `cmd`, `name`, `command_name`, `trigger` | ✓ | Command-Name mit `!` |
| `response` | `message`, `output`, `reply`, `text` | ✓ | Bot-Antwort |
| `cooldown` | `cd` | — | Cooldown in Sekunden (Standard: 5) |
| `userlevel` | `user_level`, `level`, `permission`, `access` | — | Berechtigungsstufe (Standard: everyone) |

### Beispiel

```csv
command;response;cooldown;userlevel
!social;Folge mir auf Twitter: @meinkanal;30;everyone
!discord;Unser Discord: discord.gg/mein-server;10;everyone
!so;Schaut mal bei {touser} vorbei! https://twitch.tv/{touser};5;mod
```

### Beispieldateien herunterladen

Lade diese Vorlagen herunter und passe sie an:

- [commands_beispiel.csv](../../downloads/commands_beispiel.csv) — 5 Beispiel-Commands
- [timer_beispiel.csv](../../downloads/timer_beispiel.csv) — 3 Beispiel-Timer
- [regulars_beispiel.csv](../../downloads/regulars_beispiel.csv) — 5 Beispiel-Regulars

---

## Nach dem Import

- Importierte Commands sind sofort aktiv (außer solche mit nicht konvertierbaren Variablen)
- Prüfe die importierten Commands unter **Custom Commands**
- Deaktivierte Commands haben einen Hinweis warum sie deaktiviert wurden
- Du kannst alle importierten Commands nachträglich bearbeiten
- Im **Import-Verlauf** siehst du eine Übersicht aller durchgeführten Importe

!!! tip "Duplikate"
    Wenn ein Command mit dem gleichen Namen bereits existiert, wird er beim Import **übersprungen** und nicht überschrieben. Du siehst in der Vorschau welche Commands übersprungen werden.
