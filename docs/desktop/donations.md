---
title: Donations
description: Tipeeestream, StreamElements, Streamlabs und Ko-Fi in Botly einrichten.
---

# Donations

Verbinde deine Donation-Plattformen mit Botly und löse Alerts und Action-Chains bei Spenden aus.

## Unterstützte Anbieter

| Anbieter | Verbindung | Echtzeit |
|----------|-----------|----------|
| **Tipeeestream** | API Key | Ja (WebSocket) |
| **StreamElements** | JWT Token | Ja (WebSocket) |
| **Streamlabs** | Socket API Token | Ja (WebSocket) |
| **Ko-Fi** | Webhook | Ja (HTTP) |

## Einrichtung

### Tipeeestream

1. Logge dich bei [Tipeeestream](https://www.tipeeestream.com) ein
2. Gehe zu **API** → kopiere deinen **API Key**
3. In der Desktop App → **Donations** → **Tipeeestream**
4. Füge den API Key ein → **Verbinden**

### StreamElements

1. Logge dich bei [StreamElements](https://streamelements.com) ein
2. Gehe zu **Account** → **Channels** → kopiere den **JWT Token**
3. In der Desktop App → **Donations** → **StreamElements**
4. Füge den Token ein → **Verbinden**

### Streamlabs

1. Logge dich bei [Streamlabs](https://streamlabs.com) ein
2. Gehe zu **Settings** → **API Settings** → kopiere den **Socket API Token**
3. In der Desktop App → **Donations** → **Streamlabs**
4. Füge den Token ein → **Verbinden**

### Ko-Fi

1. Logge dich bei [Ko-Fi](https://ko-fi.com) ein
2. Gehe zu **Settings** → **API** → kopiere den **Webhook Token**
3. Im Botly Dashboard unter **Einstellungen** → trage die **Ko-Fi Webhook URL** ein
4. In der Desktop App → **Donations** → **Ko-Fi** → Token eingeben → **Verbinden**

## Donation als Trigger

Donations können als Trigger in [Action-Chains](action-chains.md) verwendet werden:

| Trigger | Beschreibung |
|---------|-------------|
| **Tipeeestream Donation** | Spende über Tipeeestream |
| **StreamElements Donation** | Spende über StreamElements |
| **Streamlabs Donation** | Spende über Streamlabs |
| **Ko-Fi Donation** | Spende über Ko-Fi |

### Bedingungen

- **Mindestbetrag** — Chain nur ab einem bestimmten Betrag auslösen
- **Cooldown** — Verhindert Spam bei vielen kleinen Spenden

### Verfügbare Variablen

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `{username}` | Name des Spenders | `CoolViewer` |
| `{amount}` | Betrag | `5.00` |
| `{currency}` | Währung | `EUR` |
| `{message}` | Spenden-Nachricht | `Weiter so!` |
| `{provider}` | Anbieter | `tipeeestream` |

!!! info "Premium Feature"
    Donation-Integration ist ab dem Premium-Plan verfügbar (oder mit Desktop Lifetime).
