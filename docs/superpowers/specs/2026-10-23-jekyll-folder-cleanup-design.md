# Jekyll Folder Cleanup Design

## Intent

Turn the repository from a lightly modified copy of the Minimal theme into a clearer personal-site repository, while preserving the current appearance, public page URLs, and referenced research files.

## Goals

- Remove generated output, operating-system metadata, sample content, and unused theme-development files.
- Remove unreferenced theme fragments and simplify overly verbose custom CSS without changing the visible design.
- Fix the existing missing-layout build warning.
- Replace the upstream theme README with concise instructions for this website and an overview of its folder structure.
- Keep the site buildable with the existing Ruby/Jekyll setup.

## Non-goals

- No visual redesign or rewriting of research content.
- No URL changes to the current public pages or linked PDFs.
- No dependency upgrades unless they are required for the cleanup.
- No removal of historical CVs or research PDFs solely because they are not currently linked.

## Constraints

- GitHub Pages is configured around the `docs/` site source and the current `gh-pages` branch.
- Existing user content and downloadable research files must be preserved conservatively.
- Generated folders remain ignored rather than tracked.

## Approaches considered

1. Conservative cleanup: remove only caches and `.DS_Store` files. Lowest risk, but leaves the repository looking like a theme source checkout.
2. Moderate cleanup (selected): also remove demonstrably unused sample/theme-development material, simplify dead CSS, fix the layout warning, and document the actual site. This gives a clear repository without changing the website's design or URLs.
3. Deep restructure: replace the local theme package, reorganize content and assets, and modernize dependencies. Cleaner in theory, but introduces unnecessary deployment and URL risk.

## Planned changes

- Remove tracked `.DS_Store` files and ensure they are ignored repository-wide.
- Remove the generated `_site/` and `.jekyll-cache/` working directories from the local workspace.
- Remove the sample Jekyll post, sample pages, upstream theme contributor documents, release scripts, theme thumbnail, and unused includes/layouts.
- Remove only image assets proven unreferenced; retain all CV and research PDFs as archives.
- Reduce `assets/css/style.scss` to styles actually used by the current site.
- Give the About page a valid layout or remove it if it contains only untouched sample text; no published personal content will be lost.
- Rewrite `README.md` for this repository and describe how Jekyll processes each important directory.
- Run a clean Jekyll build and inspect the resulting pages and internal asset references.

## Success criteria

The repository is easier to understand, the current public content and URLs remain intact, and `bundle exec jekyll build` finishes without layout warnings.
