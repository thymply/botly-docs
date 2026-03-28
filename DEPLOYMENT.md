# Botly Docs — Deployment

## Hosting

Die Docs werden über **Cloudflare Pages** gehostet.
Domain: https://botly-docs.thymply.de

## Automatisches Deployment

Jeder Push auf `main` triggert automatisch einen Build bei Cloudflare Pages.

**Build command:** `pip install mkdocs-material && mkdocs build`
**Output:** `site/`
**Dauer:** ~30 Sekunden

## Lokale Entwicklung

```bash
pip install mkdocs-material
mkdocs serve
# → http://localhost:8000
```

## Cloudflare Pages Einstellungen

| Einstellung | Wert |
|-------------|------|
| Projekt | botly-docs |
| Repository | thymply/botly-docs |
| Branch | main |
| Framework | None |
| Build command | `pip install mkdocs-material && mkdocs build` |
| Output directory | `site` |
| Root directory | `/` |
| Custom Domain | botly-docs.thymply.de |
| Environment | PYTHON_VERSION = 3.12 |

## Cloudflare Pages einrichten (einmalig)

### 1. Projekt erstellen

1. Öffne https://dash.cloudflare.com
2. Gehe zu **Workers & Pages** → **Pages**
3. Klicke **Create a project** → **Connect to Git**
4. GitHub Account verbinden (falls nötig)
5. Repository auswählen: `thymply/botly-docs`
6. Klicke **Begin setup**

### 2. Build-Einstellungen

- **Framework preset:** None
- **Build command:** `pip install mkdocs-material && mkdocs build`
- **Build output directory:** `site`
- **Root directory:** `/`
- **Environment variables:** `PYTHON_VERSION` = `3.12`

### 3. Deployment starten

Klicke **Save and Deploy**. Cloudflare baut die Seite und deployed sie.
Du bekommst eine URL wie: `botly-docs.pages.dev`

### 4. Custom Domain

1. Im Cloudflare Pages Projekt → **Custom domains**
2. **Set up a custom domain**
3. Eingeben: `botly-docs.thymply.de`
4. Cloudflare erstellt automatisch den DNS-Eintrag (CNAME zu pages.dev)
5. SSL-Zertifikat wird automatisch erstellt

### 5. Testen

https://botly-docs.thymply.de → Docs-Seite sichtbar?

## Workflow

1. Markdown-Dateien in `docs/` bearbeiten
2. `git push`
3. Cloudflare baut automatisch (~30 Sekunden)
4. Live unter https://botly-docs.thymply.de
