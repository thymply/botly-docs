---
title: Donations
description: Tipeeestream, StreamElements, Streamlabs und Ko-Fi in Botly einrichten.
---

# Donations

Verbinde deine Donation-Plattformen mit Botly und löse Alerts und Action-Chains bei Spenden aus.

## Übersicht

- **4 Anbieter:** Tipeeestream, StreamElements, Streamlabs, Ko-Fi
- **Nur einer gleichzeitig aktiv** (wähle deinen Haupt-Donation-Dienst)
- **Verbindung läuft lokal** über die Desktop App (nicht über den Botly Server)
- Donations können als Trigger für Alerts und Action-Chains verwendet werden

## Tipeeestream einrichten

1. Logge dich bei [tipeeestream.com](https://www.tipeeestream.com) ein
2. Gehe zu **Dashboard** → **My Api**
3. Kopiere deinen **API Key**
4. In der Desktop App → **Donations** → **Tipeeestream**
5. Füge den API Key ein → **Testen** → **Speichern**

## StreamElements einrichten

1. Logge dich bei [streamelements.com](https://streamelements.com) ein
2. Gehe zu **Account** → **Channels** → **Show secrets**
3. Kopiere den **JWT Token**
4. In der Desktop App → **Donations** → **StreamElements**
5. Füge den Token ein → **Testen** → **Speichern**

## Streamlabs einrichten

1. Logge dich bei [streamlabs.com](https://streamlabs.com) ein
2. Gehe zu **Settings** → **API Settings**
3. Kopiere den **Socket API Token**
4. In der Desktop App → **Donations** → **Streamlabs**
5. Füge den Token ein → **Testen** → **Speichern**

## Ko-Fi einrichten

1. Logge dich bei [ko-fi.com](https://ko-fi.com) ein
2. Gehe zu **Einstellungen** → **API**
3. Kopiere den **Verification Token**
4. Im Botly Dashboard: Ko-Fi **Webhook URL** eintragen
5. In der Desktop App → **Donations** → **Ko-Fi** → Token eingeben → **Speichern**

!!! warning "Ko-Fi Webhook"
    Ko-Fi nutzt Webhooks statt WebSocket. Die Desktop App muss über das Internet erreichbar sein (lokal oder mit Tunnel). Die anderen 3 Anbieter funktionieren komplett lokal.

## Donation als Trigger

Donations können als Trigger in [Action-Chains](action-chains.md) und als Alert-Event im [Alert-Editor](alert-editor.md) verwendet werden.

### Bedingungen

- **Mindestbetrag** — Chain nur ab einem bestimmten Betrag auslösen
- **Nur mit Nachricht** — Nur wenn der Spender eine Nachricht geschrieben hat

### Verfügbare Variablen

| Variable | Beschreibung | Beispiel |
|----------|-------------|---------|
| `{username}` | Name des Spenders | `CoolViewer` |
| `{amount}` | Betrag | `5.00` |
| `{currency}` | Währung | `EUR` |
| `{message}` | Spenden-Nachricht | `Weiter so!` |
| `{provider}` | Anbieter | `tipeeestream` |

!!! info "Premium Feature"
    Donation-Integration ist ab dem Premium-Plan verfügbar.
