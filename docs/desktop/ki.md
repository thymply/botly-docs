---
title: KI-Assistent
description: Lokale KI mit Ollama oder Cloud-KI mit OpenAI und Anthropic nutzen.
---

# KI-Assistent

Nutze KI für Chat-Moderation, automatische Antworten und kreative Interaktionen — lokal oder in der Cloud.

## Optionen

| Option | Anbieter | Kosten | Privatsphäre |
|--------|---------|--------|-------------|
| **Lokal** | Ollama | Kostenlos | Daten bleiben auf deinem PC |
| **Cloud** | OpenAI, Anthropic | Eigener API Key | Daten an Anbieter |

## Lokal mit Ollama

[Ollama](https://ollama.ai) lässt dich KI-Modelle lokal auf deinem PC ausführen.

### Einrichtung

1. Installiere **Ollama** von [ollama.ai](https://ollama.ai)
2. Lade ein Modell: `ollama pull llama3`
3. In der Desktop App → **KI** → Anbieter: **Ollama**
4. URL: `http://localhost:11434` (Standard)
5. Modell: `llama3` (oder ein anderes installiertes Modell)

!!! tip "Empfohlene Modelle"
    - **llama3** — Gutes Allround-Modell
    - **mistral** — Schnell, gut für Chat
    - **phi3** — Klein und effizient

## Cloud (OpenAI / Anthropic)

### Einrichtung

1. Erstelle einen API Key beim Anbieter:
   - [OpenAI](https://platform.openai.com/api-keys)
   - [Anthropic](https://console.anthropic.com/)
2. In der Desktop App → **KI** → Anbieter wählen
3. **API Key** einfügen
4. **Modell** wählen (z.B. GPT-4, Claude 3.5 Sonnet)

### Kosten

Die Kosten hängen vom Anbieter und der Nutzung ab. Für Chat-Moderation und Antworten rechne mit 1-5 EUR/Monat bei normaler Nutzung.

## KI-Funktionen

### Chat-Moderation

Die KI bewertet jede Chat-Nachricht auf einer Skala von 1-10 und kann automatisch:

- Nachrichten löschen (bei hohem Score)
- User warnen
- Timeout geben

### Auto-Antwort

Die KI antwortet auf bestimmte Trigger-Wörter im Chat. Konfiguriere:

- **Trigger** — Wörter die eine KI-Antwort auslösen (kommagetrennt)
- **System-Prompt** — Wie sich die KI verhalten soll

!!! info "KI Add-on erforderlich"
    Alle KI-Funktionen erfordern das **KI Add-on** (4,99 EUR/Monat, eigener API-Key erforderlich).
