# Portfolio Project — Notes for Agents

Personal portfolio of **Sudichai Suktan** (Presales Engineer, cybersecurity/networking/cloud, Bangkok).

## Deploy
- Static site, **no build**. Hosted on GitHub Pages: repo `sudichai.github.io`, branch `master`, deploy from root.
- Workflow: edit files → `git add -A; git commit; git push` → live at https://sudichai.github.io in ~1-2 min.
- Verify live: `Invoke-WebRequest https://sudichai.github.io/` → HTTP 200. Browser cache: tell user to Ctrl+F5.
- `gh` CLI is logged in as `sudichai`. Git identity already configured.

## Files
- `index.html` — single page: Hero → About → Selected work → Experience → Skills → Certifications → Contact
- `styles.css` — design tokens: light minimal, teal accent `#0F766E`, Inter font, radius 14px chips/999px, **no animations**, light mode only
- `script.js` — mobile nav toggle only
- `resume.pdf` — one page, **no phone number** (spam concern); source docx: `..\resume\sudichai_resume_updated.docx` (original `sudichai_resume.docx` untouched)
- `img/logos/` — vendor + company logos (sangfor/sophos/zscaler/arista = small favicons; hillstone/wisevary/vrcomm = official SVG/PNG)
- `docs/superpowers/` — design spec + implementation plan + session log

## Content rules (user-approved)
- **English only** on the site; communicate with user in **Thai**, concise (token-saving preference)
- Phone number excluded everywhere on the site
- GitHub link removed from Contact (profile is empty)
- Impact numbers sourced from `C:\Users\User\Desktop\VR_Material`: 60+ client engagements (37 Sangfor + 25 Sophos folders), 30+ POC evaluations, 10+ POC playbooks, 10+ battlecards, 2 partner trainings, 15+ certifications
- **Trellix = working knowledge only** (dashed soft chip), never listed as demoed; demoed vendors: Sangfor (incl. HCI), Sophos, Hillstone; Zscaler/Arista = hands-on engineering (soft chips in hero)
- Certifications section kept deliberately quiet — not a highlight
- Post links: NGFW demo https://lnkd.in/p/ewcS6thK · DLP test https://lnkd.in/p/ddw8HBdU

## Tooling notes (this machine, Windows)
- LibreOffice at `C:\Program Files\LibreOffice\program\soffice.exe` — convert docx→pdf directly (the docx skill's soffice.py wrapper fails on Windows; call soffice.exe with `-env:UserInstallation=file:///C:/Users/User/AppData/Local/Temp/opencode/lo_profile`)
- `pandoc` NOT installed. Python 3.13 available. Rezip docx with python zipfile (relpath from source root, forward slashes)
- browser-use CLI 3.0 = Python-pipe mode; needs Chrome remote-debugging approval popups — user uses **Edge**; prefer letting the user verify visuals themselves
- docx skill: `C:\Users\User\.agents\skills\docx` (merge_runs.py, validate.py useful)
