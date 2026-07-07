# CV Design System — Tobi Bey

Vanilla base shared by **Senior RN** and **Staff / Lead** variants.

## Philosophy

1. **Greyscale first** — prove hierarchy, spacing, and type before adding colour.
2. **Experience leads** — left column opens with work history; sidebar supports.
3. **Print-native** — A4, Chrome print-to-PDF, no reliance on screen-only effects.
4. **Variant-ready** — swap profile, tagline, and bullet order; never rewrite layout.

---

## Typography

### Font stack

| Role | Family | Weight | Why |
|------|--------|--------|-----|
| **Display** (name only) | [Source Serif 4](https://fonts.google.com/specimen/Source+Serif+4) | 600 | Authority without startup-logo energy. Reads well at large sizes in PDF. |
| **UI + body** | [Source Sans 3](https://fonts.google.com/specimen/Source+Sans+3) | 400, 600 | Designed for interfaces and long text. Clear at 9–10pt. Neutral, professional. |
| **Meta / dates** | Source Sans 3 | 400 | `font-variant-numeric: tabular-nums` for aligned dates. |

**Rejected for now**

| Font | Reason |
|------|--------|
| Inter | Fine but generic — every AI CV uses it. |
| JetBrains Mono | Dates don't need monospace; feels dev-cv cliché. |
| Helvetica/Arial only | Safe but flat; weak differentiation. |
| Fraunces / display serifs | Too editorial for engineering CV. |

### Type scale (pt)

```
--text-display:  24pt   Name
--text-lead:     10pt   Tagline
--text-body:     9.5pt  Main column bullets
--text-small:    8.5pt  Sidebar, meta
--text-caption:  7pt    Section labels (uppercase)
```

### Line height

```
--leading-tight:  1.25   Name
--leading-body:   1.45   Body, profile
--leading-loose:  1.5    Sidebar blocks
```

### Section labels

- Uppercase, letter-spacing `0.14em`, weight 600
- Greyscale only: `--g600` text, `--g200` underline
- No colour accent until phase 2

---

## Colour (greyscale phase)

```
--g900  #0a0a0a   Primary ink (name)
--g800  #1a1a1a   Body text
--g600  #525252   Secondary (company, org)
--g400  #737373   Tertiary (dates, links)
--g200  #e5e5e5   Rules, dividers
--g100  #f5f5f5   Sidebar background
--g000  #ffffff   Paper
```

**Phase 2 (later):** single accent token `--accent` for section labels + bullet markers only.

---

## Layout

### Page

- **Format:** A4 (210 × 297 mm)
- **Print margins:** 10 mm top/bottom, 12 mm left/right
- **Screen preview:** centred card with subtle shadow

### Grid

```
┌─────────────────────────────────────────────────────┐
│  HEADER (full width)                                │
│  Name · Tagline                                     │
├──────────────────────────────┬──────────────────────┤
│  MAIN  ~70%                  │  ASIDE  ~30%         │
│                              │  (g100 background)   │
│  Experience                  │  Contact             │
│  Personal Projects           │  Profile             │
│  Education                   │  Core Skills         │
└──────────────────────────────┴──────────────────────┘
```

- Column gap: 0 (sidebar abuts rule)
- Main padding-right: 20px
- Sidebar padding: 14px 14px 14px 16px
- Vertical rhythm: 12px between sections, 10px between roles

---

## Components

| Class | Purpose |
|-------|---------|
| `.cv` | Document root |
| `.cv__header` | Name + tagline |
| `.cv__grid` | Two-column wrapper |
| `.cv__main` | Left narrative column |
| `.cv__aside` | Right sidebar |
| `.cv-section` | Logical block (Experience, etc.) |
| `.cv-section__title` | Uppercase label |
| `.cv-role` | Single job entry |
| `.cv-role__head` | Title + date row |
| `.cv-role__title` | Job title |
| `.cv-role__date` | Date range |
| `.cv-role__org` | Company line |
| `.cv-contact__item` | Sidebar contact line |
| `.cv-profile` | Sidebar summary |
| `.cv-skill` | Skill category block |
| `.cv-project` | Project line |
| `.cv-edu` | Education entry |

---

## Variants (content only)

| Token | Vanilla (shared) | Senior tweak | Staff tweak |
|-------|------------------|--------------|-------------|
| Tagline | Senior React Native Engineer · … | Same | Staff / Lead Mobile Engineer · … |
| Profile | Balanced IC + founder | Ship-focused | Architecture + leadership |
| Zapp bullet #1 | CI/CD | CI/CD | Architecture / standards |
| App Next Day bullets | Platform + delivery | RN + integrations | Org-level ownership |

Files:

- `tobi-bey-cv.html` — vanilla base (this)
- `tobi-bey-senior.html` — fork when ready
- `tobi-bey-staff.html` — fork when ready

---

## PDF export

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="/Users/wizard/Documents/cv/tobi-bey-cv.pdf" \
  "file:///Users/wizard/Documents/cv/tobi-bey-cv.html"
```

Settings if printing manually: A4, default margins, **background graphics on**.

---

## Build phases

| Phase | Focus |
|-------|--------|
| **1 (now)** | Greyscale, typography, 2-column, vanilla content |
| **2** | Accent colour (one hue), bullet refinement |
| **3** | Senior + Staff content forks |
| **4** | 1-page squeeze variant if needed |
