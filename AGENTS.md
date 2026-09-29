# Agent guide — rya-sge.github.io

> **Note — keep in sync:** `AGENTS.md` and `CLAUDE.md` must always be **identical**. Any edit to one must be applied verbatim to the other.

> **Note — commit messages:** After each group of modifications or each feature added, always provide a **one-line GitHub commit message** (Conventional-Commits style, e.g. `feat: ...`, `fix: ...`, `docs: ...`, `content: ...`).
>
> **Never put `!` in a commit message** — not as the breaking-change marker (`feat!: ...`), not anywhere else. In an interactive bash, `!` inside double quotes triggers history expansion, so `git commit -m "feat!: ..."` aborts with `bash: !: unrecognized history modifier`. Signal a breaking change with an uppercase `BREAKING CHANGE:` line in the commit body instead, and keep the subject line free of `!`.

> **Note — no tool names in the changelog:** never name an assistant tool, skill or slash command in `CHANGELOG.md`. The changelog records what changed in *this project*, for readers who have no idea what tooling produced it. A line ending "the `<some-skill>` skill gained the corresponding check" documents the author's toolbox rather than the release, and it rots independently of the repository — the tool can be renamed or deleted, leaving a dangling reference to something the reader could never have seen. Describe the change and its effect; if the tooling matters, record it in the audit or analysis report instead.
>
> This is about **tool identities, not the word "Claude"**: files committed to the repository — `CLAUDE.md`, `AGENTS.md`, `CLAUDE_AUDIT.md`, `CLAUDE_ANALYSIS*.md` — are cited freely, because a reader can open them.

> **Note — do not hard-wrap prose in `CHANGELOG.md`:** one line per bullet or paragraph, and let the editor soft-wrap. Markdown collapses a single newline into a space, so a hard-wrapped bullet renders identically — the cost is invisible in the published changelog and paid entirely in the repository. Changing one word reflows every following line, so a one-word correction arrives as a multi-line diff in which a reviewer cannot see what actually changed; and because the wrap column depends on whoever wrote the entry, the file drifts into a mix of styles that reads as damage. Keep the line structure only where it is semantic: fenced code blocks, tables and blockquotes.

> **Note — long changelog entries get sub-bullets:** past roughly three sentences, a bullet stops being scannable — the defect, its blast radius, the fix, the precedent and the caveat all run together, so a reader looking for any one of them has to parse all five. Lead with one sentence naming *what changed*, then one sub-bullet per distinct claim: impact, fix, behaviour-change warning, cost, migration note. A useful trigger is length — compare against the file's own median bullet and split anything several times longer, since that length almost always means several claims in one paragraph. Sub-bullets follow the same no-hard-wrap rule: one line each.

## What this project is

Personal portfolio website of Ryan S. (AccessDenied404 — security engineer / blockchain developer), served by GitHub Pages at `https://rya-sge.github.io`. It is a Jekyll site built from the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template (a Minimal Mistakes fork); `README.md` is still the template's upstream README. The blog itself lives elsewhere (`https://rya-sge.github.io/access-denied/`), so this repo holds mainly the about page, CV, publications, portfolio and talks.

## Key concepts

- **Content vs. theme:** personal content lives in `_pages/`, `_talks/`, `_config.yml` (author sidebar) and `_data/navigation.yml`. Everything in `_layouts/`, `_includes/`, `_sass/`, `assets/` is template code — change it only when the task is about layout/styling.
- **Home page:** `_pages/about.md` has `permalink: /` (redirects from `/about/`).
- **Collections:** only `talks` is declared in `_config.yml` (`output: true`, layout `talk`). `_publications/` still contains the template's placeholder papers and is not declared as a collection; `_pages/publications.md` is written by hand instead.
- **Header menu:** order and entries come from `_data/navigation.yml` (Publications, Talks, Portfolio, Blog Posts, CV).
- **Front-matter defaults:** set per type (posts / pages / talks) in `_config.yml` `defaults`; new pages normally only need `title`, `permalink`, `layout: archive` or default `single`.
- **Files:** anything in `files/` is published at `/files/<name>` (e.g. slide PDFs linked from talks). The PDFs currently at repo root are untracked.
- **GitHub Pages safe mode:** only whitelisted plugins work (`jekyll-feed`, `jekyll-gist`, `jekyll-paginate`, `jekyll-sitemap`, `jekyll-redirect-from`, `jemoji`). Do not add other plugins.
- **`_config.yml` is not hot-reloaded** by `jekyll serve`; restart after editing it.
- **JS bundle:** `assets/js/main.min.js` is generated from `assets/js/_main.js` + plugins via `npm run build:js`; edit the source, then rebuild.

## File tree

```
_config.yml              # site settings, author sidebar, collections, defaults, plugins
_config_docker.yml       # overrides url for Docker runs
_data/
  navigation.yml         # header menu
  authors.yml, ui-text.yml
_pages/
  about.md               # home page (permalink /)
  cv.md                  # CV (/cv/), lists site.publications and site.talks
  publications.md        # hand-written publications list
  portfolio.md           # projects (e.g. CMTAT)
  talks.html             # talks index, iterates site.talks
  year-archive.html, category-archive.html, tag-archive.html, sitemap.md, 404.md, terms.md, …
_talks/
  2024-11-07-crypto-wallet.md   # Black Alps 2024 talk
_posts/                  # 2025-11-12-blog-post-1.md (template placeholder)
_publications/           # template placeholder papers (not a declared collection)
_drafts/                 # post-draft.md
_layouts/                # single, archive, talk, cv-layout, splash, default, compress
_includes/               # author-profile, masthead, head/custom.html, footer/custom.html, seo, …
_sass/                   # include/, layout/, theme/ (default|air, light|dark), vendor/
assets/                  # css/main.scss, js/_main.js, js/main.min.js, fonts
files/                   # downloadable files served at /files/
images/                  # profile.png, favicons, manifest.json, themes/
markdown_generator/      # template scripts/notebooks generating talks/publications from TSV
```

## Other important files

- `Gemfile` — `github-pages`, `jekyll` + plugins, `webrick ~> 1.8`, `connection_pool 2.5.0` (`Gemfile.lock` is gitignored).
- `package.json` — JS build scripts (`uglify-js`, `onchange`) and deps (`jquery`, `fitvids`, `jquery-smooth-scroll`).
- `Dockerfile` (ruby:3.2, bundler 2.3.26), `docker-compose.yaml`, `.devcontainer/devcontainer.json`.
- `.github/workflows/scrape_talks.yml` — runs `talkmap.ipynb` on changes to `_talks/`; that notebook does not exist in this repo.
- No `CHANGELOG.md` exists yet.

## Common commands

```bash
bundle install                               # install Ruby deps
bundle exec jekyll serve -l -H localhost     # local preview at localhost:4000
docker compose up                            # alternative: preview via Docker
npm install && npm run build:js              # rebuild assets/js/main.min.js
```

## Conventions

- Talks: `_talks/YYYY-MM-DD-slug.md` with front matter `title`, `collection: talks`, `type`, `permalink: /talks/YYYY-MM-DD-slug`, `venue`, `date`, `location`.
- Keep links to the external blog as absolute URLs under `https://rya-sge.github.io/access-denied/`.
- GitHub Pages builds the site from the pushed branch (`master` is the main branch); preview locally before pushing.
