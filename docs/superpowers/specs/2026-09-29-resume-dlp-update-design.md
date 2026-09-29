# Resume DLP update — Design

Date: 2026-09-29
Status: Approved by user

## Goal
Add the Sangfor Athena SASE DLP test to the resume (one-page constraint) and redeploy `resume.pdf` on the site.

## Change
Replace the final VRCOMM bullet in `C:\Users\User\Desktop\gunny\resume\sudichai_resume_updated.docx`:

Old: "Produced a public technical demo simulating a real NGFW attack scenario, shared on LinkedIn to support brand/partner credibility"

New: "Produced public LinkedIn demos to support brand/partner credibility — an NGFW attack simulation and a SASE DLP test blocking Thai phone-number leaks across browsers, cloud apps, and USB storage"

## Steps
1. Edit `word/document.xml` (single `<w:t>` replacement), rezip docx via python zipfile (relpath from root, forward slashes)
2. LibreOffice → PDF; verify Pages = 1 and visually check layout (page has ~1 inch free at bottom)
3. Copy PDF over `portfolio/resume.pdf`
4. Commit + push; verify live HTTP 200
