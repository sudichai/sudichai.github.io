# Portfolio Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans (inline, chosen for token efficiency).

**Goal:** Single-page English portfolio for Sudichai Suktan at https://sudichai.github.io

**Architecture:** Static HTML + CSS + JS, no build. One page, semantic sections, progressive enhancement (JS only for mobile nav).

**Tech Stack:** Plain HTML/CSS/JS, Inter via Google Fonts (system fallback).

**Design tokens (per approved spec):**
- Colors: bg `#FAFBFC`, surface `#FFFFFF`, ink `#132A2E`, body `#3D5157`, accent `#0F766E` (teal-700), accent-soft `#CCF3EE`, border `#E3EBEA`
- Type: Inter 400/600/700; H1 clamp(2.2rem→3.5rem); body 1rem/1.7; max line ~70ch
- Shape: radius 14px cards / 999px chips; border 1px solid border-color (no drop shadows)
- Layout: single column max 960px, left-aligned; hero = text left + avatar right (desktop), stacked (mobile)

**Distinctive move (one boldness budget):** hero one-liner framed as his actual job — "demos and POCs that turn products into deals" — plus a quiet platform strip (Sangfor · Sophos · Hillstone · Zscaler · Arista) grounding it in his real world. No ALL-CAPS eyebrows, no numbered markers, no gradient washes, no card-grid sameness.

---

### Task 1: index.html
- Create: `index.html`
- Sections: header nav → hero (name, role, one-liner, CTA Email/LinkedIn, avatar w/ `SS` fallback, platform strip) → About → Selected work (NGFW demo card) → Experience (VRCOMM, WISE VARY) → Skills (6 groups as chips) → Contact → footer
- All content in English from resume; phone excluded

### Task 2: styles.css
- Create: `styles.css`
- Tokens as CSS variables, mobile-first, responsive at 768px; scroll-margin-top on sections; focus-visible styles; reduced-motion not needed (no animations)

### Task 3: script.js
- Create: `script.js` — mobile nav toggle only (~15 lines)

### Task 4: Verify locally
- Open in browser (desktop + mobile devtools), check sections, links, avatar fallback

### Task 5: Deploy
- `git add . && git commit`
- `gh repo create sudichai.github.io --public --source=. --push`
- `gh api repos/sudichai/sudichai.github.io/pages -X POST -f "source[branch]=master" -f "source[path]=/"`
- Expected: site live at https://sudichai.github.io within ~2 min

### Task 6: Verify live
- `gh api repos/sudichai/sudichai.github.io/pages` → status built; curl URL → 200; HTTPS enforced
