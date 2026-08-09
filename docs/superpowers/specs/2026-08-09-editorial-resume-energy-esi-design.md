# Clean Editorial Resume Redesign + Energy-esi Experience

**Date:** 2026-08-09  
**Status:** Approved for planning  
**Scope:** Single-file `index.html` resume on GitHub Pages

## Goal

Add a new concurrent consulting role at Energy-esi (ADNOC client) and restyle the resume into a sleek single-column “Clean Editorial” layout with tasteful screen-only animations.

## Content

### New work experience (first / most recent)

| Field | Value |
| --- | --- |
| Role | Power BI Developer (Consultant) |
| Dates | Aug 2026 – Present |
| Organization | Energy-esi — ADNOC Client (Remote) |
| Concurrent with | Data Cuentos (Oct 2025 – Present remains unchanged) |

**Bullets:**

1. Built domain fluency in oil & gas operations to frame analytics around ADNOC business needs.
2. Delivered Power BI insights that surface trends and opportunities for stakeholders.
3. Built pixel-perfect reports in Power BI Report Builder with advanced DAX.
4. Connected enterprise data via JDBC/ODBC and wrote SQL for reliable, performant datasets.

### Unchanged content (except placement)

- Existing experience entries, projects, education, certifications, contact, and summary copy stay as-is unless layout forces regrouping.
- Data Cuentos end date is **not** closed; both roles show Present.

## Visual design

### Direction: Clean Editorial (option B)

- **Page chrome:** Soft warm-gray page background behind a centered A4 paper sheet.
- **Paper:** `#faf9f6`
- **Ink:** `#1c1917`
- **Muted text:** `#57534e` / `#78716c`
- **Accent:** Teal `#0f766e` for section labels and organization names
- **Typography:** Google Fonts pairing — **Source Serif 4** for the name (and optional section titles); **Source Sans 3** for body, dates, labels, and controls. Drop Inter.
- **Layout:** Single column; **no dark sidebar**
- **Experience items:** Flat rows with hairline dividers — **no cards** for experience entries
- **Skills / tech / certifications:** Move former sidebar content into compact main-column sections (chips, short lists)
- **Controls:** Keep Print / Download HTML above the page; style to match editorial (quiet borders, teal primary optional)

### Section order (main column)

1. Header (name, headline, contact)
2. Professional Summary
3. Work Experience (Energy-esi first)
4. Projects
5. Education
6. Skills / Tech Stack / Certifications (compact)
7. Additional details / target roles footer

## Motion (screen only)

All three approved:

1. **Fade + stagger on load** — header then sections cascade in lightly.
2. **Link / CTA hover** — soft lift and underline grow on Print/Download and contact links.
3. **Section accent draw** — teal rule under section titles animates when the section scrolls into view (IntersectionObserver or CSS scroll-driven where practical).

### Constraints

- Honor `prefers-reduced-motion: reduce` (instant/static presentation).
- `@media print`: hide controls, disable animations/transforms, exact color adjust for PDF, clean A4 layout.
- Motion is presence/hierarchy only — no decorative noise, no continuous looping effects.

## Architecture

- **Single artifact:** `index.html` (inline CSS + small inline JS).
- **No new framework, build step, or dependencies** beyond existing Font Awesome / Google Fonts (fonts may be swapped for editorial pairing).
- **JS responsibilities:** print, download HTML blob, optional IntersectionObserver for section rules, no SPA routing.

## Non-goals

- Multi-page site or CMS
- Fixing duplicate OCR bullets between Data Cuentos and Datalake Gen AI (out of scope unless requested later)
- Dark mode toggle
- Backend or form handling

## Success criteria

- Energy-esi appears as the top experience entry with correct concurrent dating.
- First viewport reads as one editorial composition (name as hero signal, calm supporting line, contact).
- Print/PDF remains readable and static.
- Animations feel intentional (at least the three listed) and shut off for print / reduced motion.
- Mobile: single column remains usable (`max-width` fluid below A4).

## Implementation notes

- Prefer CSS variables for the new palette.
- Reuse semantic section structure; restyle rather than invent parallel markup systems.
- Keep download filename sensible (e.g. `Jayanth_Kanala_Resume.html`).
