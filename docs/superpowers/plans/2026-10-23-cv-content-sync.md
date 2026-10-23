# CV Content Sync Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Synchronize the existing Jekyll website with the September 2026 CV without changing its design, structure, research narrative, or contact email.

**Architecture:** Make targeted content edits in the existing Markdown and layout files, add one versioned PDF asset, and leave all CSS, images, and unrelated pages untouched. Treat the supplied CV as the factual source for publications, preprints, awards, and service, with the unchanged-email instruction as an explicit override.

**Tech Stack:** Jekyll 4.2.1, Markdown, Liquid, Bundler

**Spec:** `docs/superpowers/specs/2026-10-23-cv-content-sync-design.md`

## Global Constraints

- Keep `chenyusi151201@@gmail.com (remove @ before emailing)` unchanged in `docs/index.md`.
- Preserve the current layout, CSS, images, homepage structure, and research-topic prose.
- Do not add invited talks, teaching, mentoring, education, or skills from the CV.
- Use a versioned filename for the September 2026 CV PDF and update the single global CV link to it.
- Do not edit or overwrite the supplied DOCX.

## Review Focus

- Publication status: the Nature paper must not remain duplicated under Preprints.
- Source fidelity: author order, year, title, venue, and co-first notation must match the CV.
- Contact stability: the website email must remain byte-for-byte unchanged.
- Asset integrity: the new PDF link, portrait image, logo preload, and other local links must resolve with exact casing.
- Build output: a clean Jekyll build must contain the updated content without warnings.

---

### Task 1: Synchronize CV-derived content

**Files:**
- Create: `docs/assets/files/CV_academia_Sept2026.pdf`
- Modify: `docs/_layouts/default.html`
- Modify: `docs/publications.md`
- Verify unchanged: `docs/index.md`

**Interfaces:**
- Consumes: `/Users/Yusi/Library/Mobile Documents/com~apple~CloudDocs/Documents/ION/CV_academia_Sept2026.docx`
- Produces: a versioned CV PDF and updated Markdown/HTML source consumed by Jekyll

- [ ] **Step 1: Record baseline invariants**

Run exact-text checks for the existing email, portrait path, and logo path. Save the expected strings for post-edit comparison.

- [ ] **Step 2: Verify current publication details from primary sources**

Confirm the official Nature title, year, citation, and paper URL, and retain existing links for unchanged papers and preprints.

- [ ] **Step 3: Generate the versioned CV PDF**

Convert the supplied DOCX to `docs/assets/files/CV_academia_Sept2026.pdf` with the bundled document runtime; do not modify the DOCX.

- [ ] **Step 4: Update the global CV link**

Change only the CV filename in `docs/_layouts/default.html` from `CV_academia_Dec2025.pdf` to `CV_academia_Sept2026.pdf`.

- [ ] **Step 5: Update Publications content**

Move the 2026 Nature paper into Selected Publications; replace the stale in-preparation entries with the four Preprints entries in the CV; add the 2024 Washington Research Foundation finalist entry; and synchronize the professional-service list to the CV.

- [ ] **Step 6: Run focused source assertions**

Assert that the new PDF exists and is non-empty, the new link occurs once, the old link occurs zero times, the Nature paper occurs once, and the homepage email matches the baseline exactly.

- [ ] **Step 7: Commit the content update**

Commit the PDF, layout, and Publications changes together with a message describing the CV synchronization.

### Task 2: Build and regression-check the site

**Files:**
- Verify: `docs/_site/index.html`
- Verify: `docs/_site/publications.html`
- Verify: `docs/_site/assets/files/CV_academia_Sept2026.pdf`

**Interfaces:**
- Consumes: the Jekyll sources produced by Task 1
- Produces: a verified local site build suitable for browser preview

- [ ] **Step 1: Run the clean Jekyll build**

Run `bundle exec jekyll clean` and `bundle exec jekyll build` from `docs/`; expect exit code 0 and no warnings.

- [ ] **Step 2: Check generated content and assets**

Verify that `_site/index.html` retains the email and portrait, `_site/publications.html` contains the updated sections exactly once, and `_site/assets/files/CV_academia_Sept2026.pdf` is non-empty.

- [ ] **Step 3: Audit local references**

Check every root-relative and relative local link in generated HTML against `_site`, including exact filename casing; expect zero missing targets.

- [ ] **Step 4: Verify the live preview**

Serve the site at `http://127.0.0.1:4000/` and visually inspect the homepage and Publications page, including portrait/logo rendering and the CV link target.

- [ ] **Step 5: Confirm repository state**

Run `git status --short` and `git diff --check`; expect no uncommitted implementation changes and no whitespace errors.

