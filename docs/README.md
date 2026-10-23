# Yusi Chen — Personal Website

This repository contains the source for Yusi Chen's personal academic website. The site is generated with [Jekyll](https://jekyllrb.com/) and uses a locally customized version of GitHub's Minimal theme.

## How the site is organized

Jekyll reads the files in this directory and turns them into a static website:

```text
docs/
├── _config.yml       # Site title, profile image, plugins, and build settings
├── _layouts/         # HTML page shells; default.html wraps every public page
├── _includes/        # Small reusable HTML fragments included by layouts
├── _sass/            # Local Minimal-theme and syntax-highlighting styles
├── assets/
│   ├── css/          # Sass entry point compiled to assets/css/style.css
│   ├── files/        # CVs, posters, notes, and other downloadable PDFs
│   ├── fonts/        # Locally hosted Noto Sans font files
│   ├── img/          # Profile and other site images
│   └── js/           # Small responsive-layout helper
├── index.md          # Home page
├── lectures.md       # Recommended lectures
├── notes.md          # Research notes
├── projects.md       # Side projects
├── publications.md   # Research topics and publications
├── roadmap.md        # Computational-neuroscience learning roadmap
├── 404.html          # Not-found page
├── Gemfile           # Direct Ruby dependencies used to build the site
└── Gemfile.lock      # Exact dependency versions for reproducible builds
```

Markdown pages start with a short YAML header such as `layout: default`. Jekyll renders the Markdown, inserts it into `_layouts/default.html`, processes the Sass entry point in `assets/css/style.scss`, and copies static files from `assets/` into the generated site.

The generated `_site/` directory and Jekyll cache are intentionally ignored. They are build products, not source files.

## Build locally

From the repository root:

```sh
cd docs
bundle install
bundle exec jekyll build
```

The generated website will be written to `docs/_site/`.

## Preview locally

```sh
cd docs
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Updating the site

- Edit a top-level Markdown file to change page content.
- Add downloadable material under `assets/files/` and link to it with `{{ '/assets/files/example.pdf' | relative_url }}` or a relative Markdown link.
- Update the profile image path, title, or plugins in `_config.yml`.
- Adjust shared HTML in `_layouts/default.html` or `_includes/`.
- Add site-wide styling in `assets/css/style.scss`; the underlying theme sources live in `_sass/`.

After making changes, run `bundle exec jekyll build` from `docs/` and check that it finishes without warnings.
