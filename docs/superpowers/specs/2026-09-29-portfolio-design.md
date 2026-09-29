# Portfolio Website Design — 2026-09-29

## Goal
Personal portfolio for **Sudichai Suktan** (Cybersecurity Presales Engineer), hosted on GitHub Pages at **https://sudichai.github.io**.

## Locked Decisions
- **Repo:** `sudichai.github.io` (user site, public)
- **Stack:** static HTML + CSS + JS, no build step
- **Sections:** Hero → About → Projects → Experience → Skills → Contact
- **Style:** minimal light, Teal/Cyan accent, Inter font, soft rounded corners, no scroll animations, light mode only
- **Site language:** English (all UI text and content)
- **Content source:** `C:\Users\User\Desktop\gunny\resume\sudichai_resume.docx`
- **Phone number:** excluded (privacy). Contact = email + LinkedIn + GitHub
- **Profile photo:** `profile.jpg` placed by user; fallback = initials "SS" circle

## Architecture
- `index.html` — single page, semantic sections
- `styles.css` — design tokens as CSS variables, mobile-first, responsive
- `script.js` — mobile nav toggle only (progressive enhancement; page fully works without JS)

## Content Mapping
- **Hero:** name, title "Cybersecurity Presales Engineer", CTA buttons (Email / LinkedIn)
- **About:** professional summary from resume
- **Projects:** 1 card — NGFW attack scenario demo (public demo shared on LinkedIn)
- **Experience:** Presales Engineer @ VRCOMM (Nov 2025–Present); System Engineer L1 @ WISE VARY (Jul 2025–Oct 2025), with bullets from resume
- **Skills:** 6 groups — Security Platforms / Cloud (Sangfor HCI — Hyper-Converged Infrastructure, Cloud Computing) / Presales & Delivery / Threat & Risk / Networking / Languages
- **Contact:** sudichai.s@gmail.com, linkedin.com/in/sudichai-suktan, github.com/sudichai

## Edge Cases
- Missing `profile.jpg` → initials avatar fallback
- No JS → static content still readable
- No external CSS/JS dependencies except Google Fonts (with system-font fallback)

## Verification
- Open `index.html` locally in browser, check desktop + mobile (devtools responsive)
- After deploy: https://sudichai.github.io returns 200, all sections visible, HTTPS active
