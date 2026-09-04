# Goereese Honing

Landingspagina voor goereesehoning.nl — statische HTML, geen build.

## Structuur

- `index.html` — de pagina (alle CSS inline in de `<style>`)
- `assets/` — beelden die de pagina gebruikt; WebP met PNG-fallback
- `vercel.json` — cache-headers voor `/assets/`
- `design/` — bron uit Claude Design (`.dc.html` + runtime) en ongebruikte beelden.
  Wordt niet meegedeployed (zie `.vercelignore`).

## Lokaal bekijken

    python3 -m http.server 8931

Daarna http://localhost:8931

## Deployen

Push naar `main`. Vercel bouwt niets — het is statisch — en publiceert de root.

## Beelden

WebP is aangemaakt met:

    cwebp -q 82 -alpha_q 90 -m 6 bron.png -o doel.webp

Dat scheelde 84% (3,7 MB → 577 KB). Vervang je een beeld, maak dan beide
formaten aan; `index.html` verwijst via `<picture>` naar allebei.
