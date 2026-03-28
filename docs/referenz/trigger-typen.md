---
title: Trigger-Typen
description: Alle verfügbaren Trigger für Action-Chains — mit Parametern und Variablen.
---

# Trigger-Typen

Vollständige Referenz aller Trigger die eine Action-Chain auslösen können.

## Twitch-Trigger

| Trigger | Beschreibung | Variablen |
|---------|-------------|-----------|
| **Follow** | Neuer Follower | username |
| **Subscription** | Neues Abo / Resub | username, tier, months, message |
| **Gift Sub** | Geschenk-Abo | username, amount, tier |
| **Bits / Cheer** | Bits-Spende | username, amount, message |
| **Raid** | Eingehender Raid | username, amount (Viewer) |
| **Channel Points** | Kanalpunkt-Einlösung | username, reward_name, input |
| **Chat Command** | Bestimmter Befehl im Chat | username, message |
| **Chat Message** | Nachricht mit Keyword | username, message |
| **Hype Train** | Hype Train Start/Ende | level |
| **Ad Break** | Werbepause Start/Ende | duration |

## YouTube-Trigger

| Trigger | Beschreibung | Variablen |
|---------|-------------|-----------|
| **New Member** | Neues Kanalmitglied | username, level |
| **Super Chat** | Super Chat Spende | username, amount, currency, message |
| **Super Sticker** | Super Sticker | username, amount, currency |
| **Chat Message** | Nachricht mit Keyword | username, message |

## Discord-Trigger

| Trigger | Beschreibung | Variablen |
|---------|-------------|-----------|
| **Member Join** | Neues Server-Mitglied | username, membercount |
| **Reaction** | Reaktion auf Nachricht | username, emoji, channel |

## Donation-Trigger

| Trigger | Beschreibung | Variablen |
|---------|-------------|-----------|
| **Tipeeestream** | Spende über Tipeeestream | username, amount, currency, message |
| **StreamElements** | Spende über StreamElements | username, amount, currency, message |
| **Streamlabs** | Spende über Streamlabs | username, amount, currency, message |
| **Ko-Fi** | Spende über Ko-Fi | username, amount, currency, message |

## System-Trigger

| Trigger | Beschreibung | Variablen |
|---------|-------------|-----------|
| **Timer** | Zeitgesteuert (alle X Minuten) | — |
| **Hotkey** | Tastenkombination | — |
| **Manuell** | Nur über "Jetzt auslösen" | — |
| **App-Start** | Beim Starten der Desktop App | — |
