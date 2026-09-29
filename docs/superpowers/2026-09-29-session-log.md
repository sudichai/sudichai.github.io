# Session Log — 2026-09-29 (Portfolio launch day)

## What was built
Single-page portfolio deployed live at **https://sudichai.github.io** (repo `sudichai.github.io`, branch `master`, GitHub Pages from root, HTTPS enforced).

## Interview decisions (user-approved)
- Repo: `sudichai.github.io` user site (clean URL) · stack: plain HTML/CSS/JS, no build
- Sections: Hero → About → Selected work → Experience → Skills → Certifications → Contact
- Tone: minimal light, teal accent (#0F766E), Inter, soft rounded, **no animations**, light only, **English content**
- Position title: **Presales Engineer** + "Specialized in Cybersecurity & Networking & Cloud Computing"
- Phone excluded (spam); GitHub link removed (empty profile); profile photo = `profile.jpg` with "SS" initials fallback

## Experience section (final shape, after several iterations)
Each job = title → company/period (+ logo) → 1-line summary → **Vendors in scope** chips row (full-width, standalone) → duty blocks (Live demos per-vendor lines / POC / Proposals / Partner enablement) in 2 columns on desktop.
- VRCOMM: chips Sangfor/Sophos/Hillstone (+ dashed chip "Trellix — Endpoint Security / DLP / NDR (working knowledge)")
- Sangfor demo line now includes **HCI**
- WISE VARY: chips Zscaler/Arista
- Hero: "Products I demo" = Sangfor/Sophos/Hillstone; "Also hands-on with" = Zscaler/Arista (dashed)

## Impact numbers (counted from `C:\Users\User\Desktop\VR_Material`)
- 60+ client engagements (37 Sangfor + 25 Sophos folders)
- 30+ POC evaluations · 10+ POC playbooks · 10+ battlecards · 2 partner trainings
- Used in site bullets AND in the resume

## Resume update (resume.pdf on site = one page, no phone)
- Edited a copy of `sudichai_resume.docx` via docx skill (unzip → merge_runs → edit document.xml → python zipfile rezip → validate → LibreOffice PDF)
- One-page achieved by: removing phone, trimming summary tail + 2 bullets, margins 1440→720 twips
- Saved as `..\resume\sudichai_resume_updated.docx`; original untouched. Hero + Contact have "Download résumé" buttons.

## Recruiter review fixes (all done)
1. Resume download button (hero + contact) 2. Open Graph tags (og:image = profile.jpg) 3. Demo card links to real LinkedIn post (lnkd.in/p/ewcS6thK) 4. Impact numbers 5. Bangkok, Thailand in hero 6. Certifications section (quiet): Sangfor SCTA/SCTP, Sophos Architect & Technical (Endpoint/Firewall), Trellix Specialists + ePO, **Hillstone HCSA (NGFW)** 7. GitHub link removed

## Logos (img/logos/)
- Official: hillstone.svg (hillstonenet.com), wisevary.svg (wisevary.com), vrcomm.png (vrcomm.net)
- Favicons (vendor sites blocked scraping): sangfor.png, sophos.png, zscaler.png, arista.png, trellix.png
- Chips show logo via `<img class="chip-logo">` with `onerror="this.remove()"` fallback

## Bugs hit & fixed (lessons)
- Duplicate `.job-summary` after restructuring job head — check for orphaned old elements after edits
- CSS specificity: removed `.job ul` rule that overrode `.chips` flex (chips stacked vertically)
- `--jq` flag quoting fails in PowerShell gh api — pipe raw JSON + Select-String instead
- `Expand-Archive` needs .zip extension; docx rezip must keep folder structure (relpath from source root, forward slashes)
- browser-use 3.0 needs Chrome remote-debugging approval — user is on Edge, skip browser automation

## Ideas for later
- Vendor logos are favicons for sangfor/sophos/zscaler/arista/trellix — replace with hi-res official files if user provides
- Zscaler/Arista hands-on: could add a small "engineering background" note section
- og:image uses profile.jpg (688KB) — could compress for faster share-card loading
