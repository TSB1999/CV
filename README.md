# Tobi Bey — CV

Live: **[tsb1999.github.io/CV](https://tsb1999.github.io/CV/)** · [Download PDF](tobi-bey-cv.pdf)

## Files

| File | Purpose |
|------|---------|
| `index.html` | Hosted CV (GitHub Pages) |
| `tobi-bey-cv.html` | Local working copy (same content) |
| `tobi-bey-cv.pdf` | PDF export |
| `assets/` | Showcase screenshots |
| `DESIGN.md` | Design system notes |

## Export PDF

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="$(pwd)/tobi-bey-cv.pdf" \
  "file://$(pwd)/index.html"
```

## GitHub Pages

Served from `main` branch root. After pushing, enable **Settings → Pages → Deploy from branch `main` / `/ (root)`** if not already on.
