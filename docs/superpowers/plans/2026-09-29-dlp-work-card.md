# DLP Work Card Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add the Sangfor Athena SASE DLP LinkedIn post as a second card in the portfolio's Selected work section.

**Architecture:** Static single-page site (plain HTML/CSS, no build, no test framework). One markup edit, one CSS rule, one doc note. Verification is visual + deployed HTTP 200 check.

**Tech Stack:** HTML5, CSS grid.

**Spec:** `docs/superpowers/specs/2026-09-29-dlp-work-card-design.md`

---

### Task 1: Wrap work cards and add the DLP card

**Files:**
- Modify: `index.html:85-95` (Selected work section)

- [ ] **Step 1: Wrap both cards in `.work-list` and append the new card**

Replace the section body so it reads (existing NGFW card unchanged, inside the new wrapper):

```html
    <section class="section section-tinted" id="work">
      <div class="container">
        <h2>Selected work</h2>
        <div class="work-list">
          <article class="work-card">
            <h3>Live NGFW attack simulation</h3>
            <p>A public technical demo simulating a real-world attack scenario against next-generation firewall protections — built to show detection and blocking in action, and shared on LinkedIn to support brand and partner credibility.</p>
            <p class="work-stack"><strong>Stack:</strong> Sangfor NGFW · attack simulation · live walkthrough</p>
            <a class="text-link" href="https://lnkd.in/p/ewcS6thK" target="_blank" rel="noopener">Watch the demo on LinkedIn</a>
          </article>
          <article class="work-card">
            <h3>DLP test on Sangfor Athena SASE</h3>
            <p>A public test of data loss prevention on Sangfor Athena SASE — a custom rule catches Thai phone-number patterns (mobile, landline, +66, with or without separators) across Word, Excel, and text files. Sharing is blocked on browsers, cloud apps, and USB storage, with an instant user alert and a real-time incident log on the management dashboard.</p>
            <p class="work-stack"><strong>Stack:</strong> Sangfor Athena SASE · DLP · PDPA data privacy</p>
            <a class="text-link" href="https://lnkd.in/p/ddw8HBdU" target="_blank" rel="noopener">Read the test on LinkedIn</a>
          </article>
        </div>
      </div>
    </section>
```

- [ ] **Step 2: Verify markup**

Open `index.html` in a browser. Expected: two cards under "Selected work", new card below the NGFW card, its link points to `https://lnkd.in/p/ddw8HBdU`.

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "Add DLP test card to Selected work"
```

### Task 2: Add `.work-list` spacing rule

**Files:**
- Modify: `styles.css:315-323` (Work section)

- [ ] **Step 1: Add the rule**

Immediately before `.work-card {` in the `/* ---------- Work ---------- */` block, insert:

```css
.work-list {
  display: grid;
  gap: 1rem;
}
```

- [ ] **Step 2: Verify spacing**

Reload `index.html`. Expected: clear vertical gap (~1rem) between the two cards; single-card layout elsewhere unchanged.

- [ ] **Step 3: Commit**

```bash
git add styles.css
git commit -m "Add work-list grid spacing"
```

### Task 3: Record the link and deploy

**Files:**
- Modify: `AGENTS.md:26`

- [ ] **Step 1: Update the link line**

Replace:
`- Demo post link: https://lnkd.in/p/ewcS6thK`

With:
`- Post links: NGFW demo https://lnkd.in/p/ewcS6thK · DLP test https://lnkd.in/p/ddw8HBdU`

- [ ] **Step 2: Commit and push**

```bash
git add AGENTS.md
git commit -m "Note DLP post link in AGENTS.md"
git push
```

- [ ] **Step 3: Verify live**

Run: `Invoke-WebRequest https://sudichai.github.io/ -UseBasicParsing | Select-Object -ExpandProperty StatusCode`
Expected: `200`. Then confirm the new card text appears in the response body (allow ~1-2 min for Pages deploy, Ctrl+F5 for browser cache).
