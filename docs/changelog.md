# Changelog

Änderungen an Botly, chronologisch (neueste zuerst).

## 17.11.2026

- Neuer Bereich **Kanalpunkte** unter Twitch (ab Pro): Belohnungen anlegen, bearbeiten und löschen, je Belohnung Overlay-Alert an oder aus, eigener Alert-Text und optionale Chat-Antwort.
- Overlay-Alerts (Follow, Sub, Raid, Cheer, Kanalpunkte) gibt es jetzt für alle Kanäle mit Pro oder Premium und verbundenem Twitch-Kanal.
- **Auto-Clip** erstellt wieder Clips. Dafür braucht Botly die Twitch-Berechtigung `clips:edit`: Fehlt sie, zeigt dir der Bereich Auto-Clip den Hinweis **Neu verbinden**, sobald du einen Trigger einschaltest.
- **Chat-Log**: Zeiten erscheinen in deiner Zeitzone und Sprache; **Heute** beginnt um Mitternacht bei dir.
- **← Zurück** auf Seiten wie Clips, Profil oder Abo führt zurück an die Stelle im Dashboard, von der du gekommen bist.
- Verlässt du eine Seite mit ungespeicherten Änderungen, fragt Botly selbst nach (Speichern, Verwerfen, Abbrechen) statt der Warnung des Browsers.
- Fehler und Warnungen im Bereich **Commands** bleiben sichtbar im Bereich stehen, statt als kurze Meldung zu verschwinden.
- Neu im Premium-Plan: der [Alert-Editor](dashboard/overlays-alerts.md#alerts-gestalten-alert-editor). Über **Gestalten** stellst du je Alert-Typ Texte mit Variablen, Schrift, Position und Farben ein, lädst ein eigenes Bild und einen eigenen Ton hoch und siehst alles in der Live-Vorschau.
- Zwölf Schriften stehen zur Wahl, darunter Montserrat, Bebas Neue, Press Start 2P und Permanent Marker. Alle liegen auf dem Botly-Server.
- Fehler und Warnungen bleiben jetzt auch in weiteren Bereichen sichtbar stehen, z. B. Giveaway, Counter, Regulars, Mitspieler, Kanalpunkte, Editoren, Overlays, Alerts, Abo und Discord.
- Der Dialog für Editoren öffnet sich unter YouTube und Discord wieder richtig.
- Die [Datenschutzerklärung](https://botly.thymply.de/datenschutz) und die [Nutzungsbedingungen](https://botly.thymply.de/nutzungsbedingungen) beschreiben jetzt, wie Botly hochgeladene Bilder und Töne speichert.

## 16.11.2026

- Alerts: Neu eingerichtete Alert-Typen starten ausgeschaltet — du schaltest im Bereich **Alerts** (Twitch bzw. YouTube) nur die Typen ein, die du im Stream sehen willst, und speicherst. Hattest du schon einen Overlay-Link, bleiben deine Alerts so eingestellt wie bisher.
- Der Bereich **Alerts** zeigt jetzt einen Hinweis mit Link zu **Tools** → **Overlays**, wo du den Overlay-Link für OBS erstellst und kopierst.
- Der **Test**-Knopf eines ausgeschalteten Alert-Typs meldet jetzt einen Hinweis, statt den Test als gesendet anzuzeigen.
- Der Bereich **Bot-Status** heißt jetzt **Bot-Konto** (Twitch und YouTube). Der Absender **Standard** schreibt so, wie es im Bereich **Bot-Konto** eingestellt ist.

## 13.11.2026

- Die Seiten zur eingestellten Desktop App sind entfernt (Installation, Alert-Editor, Custom Alerts, Alert-Kanäle, Action-Chains, Medien, Kanalpunkte, Donations, CrossChat, KI-Assistent; die KI-Einstellungen findest du weiter im Dashboard) — ebenso OBS-Steuerung, die Donation-Integration, die Trigger- und Aktions-Referenz und die Beispiele dazu. Alerts laufen über Overlays als Browser-Source im Dashboard.
- Die [Feature-Übersicht](erste-schritte/feature-uebersicht.md) ist jetzt nach Plattformen sortiert: Plattformübergreifend, Twitch, YouTube, Discord.

## 24.07.2026

- Die Botly Desktop App wird eingestellt — Overlays laufen künftig direkt als Browser-Source im Dashboard (kein Download mehr nötig).
