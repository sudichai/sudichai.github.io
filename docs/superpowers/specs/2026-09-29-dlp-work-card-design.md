# DLP work card — Design

Date: 2026-09-29
Status: Approved by user

## Goal
Add the new Sangfor Athena SASE DLP LinkedIn post to the portfolio's **Selected work** section as a second work card, matching the existing card's style.

## Source
LinkedIn post: https://lnkd.in/p/ddw8HBdU — "Testing DLP on Sangfor Athena SASE: Preventing Phone Number Leaks" (featured in the post: 3-step setup — detection rule, target files, policy enforcement; result — instant block, user alert, dashboard incident log).

## Changes

### 1. `index.html`
- Wrap both work cards in a new `<div class="work-list">` container (between `<h2>Selected work</h2>` and the cards).
- Existing NGFW card stays first; new card added after it:

```html
<article class="work-card">
  <h3>DLP test on Sangfor Athena SASE</h3>
  <p>A public test of data loss prevention on Sangfor Athena SASE — a custom rule
     catches Thai phone-number patterns (mobile, landline, +66, with or without
     separators) across Word, Excel, and text files. Sharing is blocked on
     browsers, cloud apps, and USB storage, with an instant user alert and a
     real-time incident log on the management dashboard.</p>
  <p class="work-stack"><strong>Stack:</strong> Sangfor Athena SASE · DLP · PDPA data privacy</p>
  <a class="text-link" href="https://lnkd.in/p/ddw8HBdU" target="_blank" rel="noopener">Read the test on LinkedIn</a>
</article>
```

### 2. `styles.css`
- In the Work section, add: `.work-list { display: grid; gap: 1rem; }` so the two cards have spacing.

### 3. `AGENTS.md`
- Add the DLP post link next to the existing demo post link.

## Constraints
- English content only on the site; existing design tokens unchanged; no animations.
- No other sections touched.

## Verification
- Local: open `index.html` — two cards render with consistent spacing; new link opens the LinkedIn post.
- Deployed: commit + push, then HTTP 200 check on https://sudichai.github.io/.
