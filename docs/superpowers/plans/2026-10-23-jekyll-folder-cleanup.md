# Jekyll Folder Cleanup Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Remove unused Jekyll/theme source clutter while preserving the appearance, routes, content, and downloadable resources of the intended personal website.

**Architecture:** Treat the current clean build as the regression baseline. Remove only files that are generated, operating-system metadata, untouched upstream development scaffolding, or proven unused by the site; keep the local layouts, Sass theme, pages, and referenced assets that determine the rendered website. Rebuild from a clean destination and compare the intended public pages and asset references with the baseline.

**Tech Stack:** Jekyll 4.2.1, Liquid, Kramdown, Sass, Bundler 2.2.28, Ruby 3.0.2

**Spec:** `docs/superpowers/specs/2026-10-23-jekyll-folder-cleanup-design.md`

## Global Constraints

- Preserve the current appearance and the intended public page URLs: `/`, `/lectures.html`, `/notes.html`, `/projects.html`, `/publications.html`, `/roadmap.html`, and `/404.html`.
- Preserve all content and links on those pages.
- Preserve every currently referenced image and PDF.
- Retain historical CVs and research PDFs even when they are not currently linked.
- Do not redesign the site, rewrite research content, or upgrade dependencies.
- Generated output must remain ignored rather than tracked.

## Review Focus

- A source file that appears unused may still be pulled in through Liquid or Sass; verify references recursively before removal.
- Case-sensitive deployment can differ from the local macOS filesystem; verify every generated asset URL matches an exact source filename.
- Removing the local gemspec must not change the resolved Jekyll/plugin versions or generated CSS.
- Cleaning sample pages must not affect the intended public page set or navigation.
- Ignored build output must be recreatable from an empty `_site/` directory.

---

### Task 1: Capture the current website baseline

**Files:**
- Create temporarily: `/tmp/yschen13-jekyll-baseline/`
- Inspect: `docs/_config.yml`
- Inspect: `docs/_layouts/default.html`
- Inspect: `docs/assets/css/style.scss`

**Interfaces:**
- Consumes: the current repository and installed bundle.
- Produces: a clean baseline build plus checksums and link inventories for the intended public pages and compiled CSS.

- [ ] **Step 1: Build the unmodified site into the temporary baseline directory**

Run: `cd docs && bundle exec jekyll build --destination /tmp/yschen13-jekyll-baseline`

Expected: build succeeds; the only known warning is the unused sample About page requesting missing layout `page`.

- [ ] **Step 2: Record regression targets**

Record SHA-256 checksums for `index.html`, `lectures.html`, `notes.html`, `projects.html`, `publications.html`, `roadmap.html`, `404.html`, and `assets/css/style.css`; extract their local `href` and `src` targets.

Expected: all eight outputs exist and every referenced local target maps to a source or generated asset.

### Task 2: Remove code and files that do not serve the personal website

**Files:**
- Create: `.gitignore`
- Modify: `docs/.gitignore`
- Modify: `docs/_config.yml`
- Modify: `docs/Gemfile`
- Regenerate: `docs/Gemfile.lock`
- Delete: `.DS_Store`
- Delete: `docs/.DS_Store`
- Delete: `docs/assets/.DS_Store`
- Delete: `docs/assets/img/.DS_Store`
- Delete: `docs/_site/`
- Delete: `docs/.jekyll-cache/`
- Delete: `docs/docs/`
- Delete: `docs/script/`
- Delete: `docs/jekyll-theme-minimal.gemspec`
- Delete: `docs/LICENSE`
- Delete: `docs/thumbnail.png`
- Delete: `docs/_posts/2021-10-07-welcome-to-jekyll.markdown`
- Delete: `docs/about.markdown`
- Delete: `docs/another-page.md`
- Delete: `docs/_layouts/post.html`
- Delete: `docs/_includes/footer.html`
- Delete: `docs/_includes/links-mobile.html`

**Interfaces:**
- Consumes: Task 1's baseline and reference inventory.
- Produces: a smaller Jekyll source tree with direct runtime dependencies and no theme-author development scaffolding.

- [ ] **Step 1: Verify every deletion candidate is outside the intended public page set and is not referenced**

Run repository-wide exact-name searches, including Liquid includes, layout names, Sass imports, Markdown links, and HTML asset references.

Expected: deletion candidates are either ignored/generated metadata, untouched Minimal-theme development files, or unlinked sample content; no referenced image or PDF appears in the list.

- [ ] **Step 2: Add repository-wide ignore rules**

Add `.DS_Store` at the repository root, keep Jekyll output/cache/vendor rules in `docs/.gitignore`, and exclude `superpowers/` from Jekyll output so the implementation notes are not published as website files.

Expected: newly generated macOS metadata and Jekyll output do not appear in `git status`, and `_site/superpowers/` is not generated.

- [ ] **Step 3: Replace the local theme-package dependency with direct, version-preserving runtime dependencies**

Keep `jekyll` at `4.2.1`, `jekyll-seo-tag` at `2.7.1`, and `webrick` at `1.7.x`; retain the local `_sass/jekyll-theme-minimal.scss` import that controls current styling.

Expected: `bundle check` succeeds without `jekyll-theme-minimal.gemspec`, and the lockfile no longer contains theme-development dependencies.

- [ ] **Step 4: Delete the verified generated, metadata, sample, and upstream development files**

Expected: the intended Markdown pages, layouts, Sass sources, fonts, JavaScript, images, CVs, and research PDFs remain present.

- [ ] **Step 5: Run a clean build**

Run: `cd docs && bundle exec jekyll build --destination /tmp/yschen13-jekyll-cleaned`

Expected: build succeeds without the missing `page` layout warning.

### Task 3: Document and verify the cleaned repository

**Files:**
- Modify: `docs/README.md`
- Inspect: all files under `docs/`
- Compare: `/tmp/yschen13-jekyll-baseline/` and `/tmp/yschen13-jekyll-cleaned/`

**Interfaces:**
- Consumes: the cleaned tree from Task 2 and baseline from Task 1.
- Produces: user-facing repository documentation and evidence that the intended site is unchanged.

- [ ] **Step 1: Rewrite the README for this personal site**

Document the role of `_config.yml`, `_layouts/`, `_includes/`, `_sass/`, `assets/`, the top-level Markdown pages, `Gemfile`, and ignored build output; include the exact local build and preview commands.

Expected: the README describes this repository rather than upstream Minimal-theme development.

- [ ] **Step 2: Compare the intended generated website against the baseline**

Compare SHA-256 checksums for the seven intended HTML pages plus compiled CSS, allowing only deterministic metadata differences if Jekyll emits any.

Expected: intended page HTML and CSS are byte-for-byte identical; if not, inspect and resolve every difference before continuing.

- [ ] **Step 3: Validate internal local links and assets in the cleaned build**

Check all local `href` and `src` targets emitted by the intended pages.

Expected: each target exists with exact filename casing; external links are not modified.

- [ ] **Step 4: Review the final repository state**

Run: `git status --short` and a sorted two-level file listing.

Expected: only planned cleanup, dependency, documentation, design, and plan changes remain; no generated `_site/` or cache file is tracked.
