# Website feedback — rya-sge.github.io

Review of the site content and configuration as of 2026-09-29, based on the repository sources (the site was not built locally). Items are ordered by priority within each section.

## 1. High priority — visible on every page

- **Site title is still the template placeholder.** `_config.yml:12` has `title: "Your Name / Site Title"`. It appears in the top-left of the header on every page and in every browser tab / search result (`<title>Talks - Your Name / Site Title</title>`). Suggested: `"Ryan Sauge"` or `"Ryan S. - AccessDenied404"`.
- **Site name and description are placeholders.** `_config.yml:14-15` (`name: "Your Name"`, `description: "Your Name's academic portfolio"`). The description is used as the default meta description and in social previews (LinkedIn, X). Suggested: `"Security engineer and blockchain developer — CMTAT, tokenization, smart contract security"`.
- **Repository URL is wrong.** `_config.yml:19` is `https://github.com/rya-sge.github.io`, which is not a valid repo URL; it should be `https://github.com/rya-sge/rya-sge.github.io`.
- **No social preview image.** `og_image` and `teaser` are empty, so links shared on LinkedIn/X have no picture. Set `og_image: "profile.png"` (or a dedicated 1200×630 banner).
- **Web manifest still names the template icon.** `images/manifest.json` has `"name": "OOjs UI icon academic-progressive"`; rename to the site name. The comment in `_includes/head/custom.html` about the favicon source is also stale since the favicon was changed.

## 2. CV page (`_pages/cv.md`)

- **Leftover template text:** "Service and leadership — Currently signed in to 43 different slack teams" (`cv.md:99-101`). Remove the section or replace it (e.g. Y-CTF co-founder, conference talks).
- **Empty "Publications" section.** It loops over `site.publications`, but `_publications` is not declared as a collection in `_config.yml`, and the files in it are template placeholders ("Paper Title Number 1…"). The heading therefore renders with nothing under it. Either list the Taurus articles directly (as in `publications.md`) or remove the section.
- **Empty "Teaching" section.** `site.teaching` does not exist; remove the section.
- **Skills section is thin and oddly structured:** "Solana" sits outside "Smart contract development", and there is nothing on security (audits, pentest, cryptography), tooling (Foundry, Hardhat, Slither, Aderyn) or other chains you present in talks (Tezos, Aztec, Zama FHE, Stellar/Soroban…). This is the section recruiters scan first.
- **Work experience summary is outdated relative to your talks.** The Taurus entry does not mention privacy work (CMTAT-Confidential with FHE, Aztec), the CMTAT audit process, or conference speaking (EthCC, BSA EPFL, Black Alps, CMTA x OpenZeppelin).
- **Typos / consistency:** "Analyze of smart contracts" → "Analysis of smart contracts"; "position:" / "company:" lowercase vs "Company:" / "Position:" elsewhere; "Duration: 12/2022 -" duplicates the date already in the heading; "A rust-based application to store password securely" → "Rust-based application to store passwords securely".
- **Consider a downloadable PDF CV** in `files/` linked at the top of the page.

## 3. Home page (`_pages/about.md`)

- **"Main article" section has an orphan sentence:** "Here my main articles on Blockchain:" is followed by nothing (`about.md:26`). Also "Main article" → "Main articles" and "Here my" → "Here are my".
- **Duplicated content:** the article lists are copied from `publications.md` but are already out of date (the 2025 Taurus articles on conditional transfers and ERC-1400 are missing). Keep one source of truth: a short "highlights" list on the home page and link to `/publications/`.
- **No mention of talks.** You have four talks, including EthCC; a "Recent talks" line with links to `/talks/` would be the strongest credibility signal on the page.
- **Inconsistent LinkedIn handle:** `about.md` links to `/in/ryan-sauge`, while the sidebar (`_config.yml:66`) uses `ryan-sge`. Check which is correct and use one.
- **Tone:** "I hope you can find your happiness among this content" reads oddly; something like "Feel free to reach out on LinkedIn or X" is enough. The first line has a leading space (" Hi there 👋").
- **Twitter/X naming:** the page says "twitter account" and links to `twitter.com` in one place and `x.com` in another; harmonise on X.
- **Title "Blockchain - Smart Contract - Security"** is fine, but combined with the placeholder site title it shows as "Blockchain - Smart Contract - Security - Your Name / Site Title" in the tab.

## 4. Publications page (`_pages/publications.md`)

- "Token Transfer Management … ERC-1404" has `(ERC-1404)` where the year should be (`publications.md:23`).
- Talks and slide decks are publications too; add a short "Talks" section linking to `/talks/` or list the four decks.
- The personal blog section only lists five articles; if some newer ones (e.g. the Bitcoin keys, MPC and Winternitz OTS posts linked from the Black Alps talk page) matter, add them.
- The page title "Publications" with a section "My main personal articles" — consider renaming the nav item to "Articles" since there are no academic papers.

## 5. Portfolio page (`_pages/portfolio.md`)

- **Heading levels are inconsistent:** "Smart contract" uses a level-1 `======` heading with `####` projects, while "Rust" uses `##` with `###` projects.
- **CCIP Sender and IncomeVault have identical durations** (12/2023 — 05/2024); check that this is right.
- **IncomeVault skills list "Stablecoin"** although it is about dividends/coupons; "Tokenization · Corporate actions" would fit better. "build with CMTAT" → "built with CMTAT"; "Publish a blog post" → "Published a blog post".
- **Missing recent projects** you present in talks: CMTAT-Confidential (FHE / ERC-7984), CMTAT cross-chain, Aztec version, and the TERC-20 / TERC-721 / TERC-1155A repos listed in the CV.
- "**Skills:** cryptography security" → "Rust · Cryptography · Security".

## 6. Talks

- **Talk pages do not show venue and location.** `_layouts/talk.html:38` only prints the "Talk at venue, location" line when `page.talk_type` is set, but all talk files use `type`. Either add `talk_type: "Talk"` to each file or change the layout to test `page.type`.
- `_config.yml:97` has `talkmap_link: false` and the talkmap notebook is absent, but `.github/workflows/scrape_talks.yml` still runs on every change to `_talks/` and will fail (it executes `talkmap.ipynb`). Delete the workflow or add the notebook.
- The Black Alps talk page uses `\-` escaped dashes and two `lnkd.in` short links; replace these with normal bullet lists and the full blog URLs (short links hide the destination and can expire). A stray line break splits the Trezor URL (`_talks/2024-11-07-crypto-wallet.md`).
- Consider adding a thumbnail (`header.teaser`) per talk for a nicer Talks page.

## 7. Template leftovers still published

These pages are live and indexed in the sitemap even though they are not in the menu:

- `_pages/markdown.md` → `/markdown/` (template's Markdown guide)
- `_pages/archive-layout-with-content.md` → `/archive-layout-with-content/` (theme demo)
- `_pages/non-menu-page.md` → `/non-menu-page/` ("This is a page not in the menu")
- `_posts/2025-11-12-blog-post-1.md` → "Blog Post number 1" tagged "cool posts". The "Blog Posts" nav item leads to a year archive containing only this post. Replace the nav item with a direct link to `https://rya-sge.github.io/access-denied/`, and delete the post.
- `_publications/` — five placeholder papers ("Paper Title Number 1…").
- `_data/authors.yml` — "Name Name" / "Name2 Name2" placeholders.
- `markdown_generator/` — template scripts with placeholder TSVs; not needed if you write talks by hand.
- `files/paper1.pdf`, `files/slides1.pdf`, `files/bibtex1.bib` — template sample files, publicly downloadable.
- `images/500x300.png`, `bio-photo.jpg`, `bio-photo-2.jpg`, `editing-talk.png` — template images.
- `README.md` — still the Academic Pages template README; a short personal README would help visitors of the GitHub repo.

## 8. Privacy / terms page (`_pages/terms.md`)

- It claims the site uses **Disqus comments, Google Analytics and third-party advertisers**, none of which are configured. The page is dated 2016. Either rewrite it to reflect reality (GitHub Pages hosting; GitHub logs IPs; no cookies or analytics) or remove it.
- Related: `_config.yml` defaults set `comments: true` for posts with no comment provider configured — harmless, but can be set to `false`.

## 9. Technical / SEO

- `_includes/footer/custom.html` loads **MathJax, Plotly (several MB) and Mermaid on every page**, although no page uses them. Removing them speeds up every page load, and removes the `polyfill` script, which is unnecessary for modern browsers (fewer third-party scripts is also a better look on a security engineer's site).
- `publication_category` in `_config.yml` (Books / Journal Articles / Conference Papers) is unused.
- The large academic-profile block in `_config.yml` (arxiv, pubmed, scopus…) is empty and can be trimmed for readability.
- Check that `bluesky: "ad403"` is the right handle (other handles are `AccessDenied404` / `ADCDIII`).
- Slide PDFs: `2024-blackalps-crypto-wallet.pdf` is 6.6 MB; compressing it would make it faster to open on mobile.

## 10. Suggested quick wins (≈30 min)

1. Fix `title`, `name`, `description`, `repository`, `og_image` in `_config.yml`.
2. Remove "43 slack teams", the empty Teaching and Publications sections from the CV.
3. Fix the orphan sentence on the home page and add a "Recent talks" line.
4. Add `talk_type` to talks (or fix the layout) so venue/location appear.
5. Delete template pages, placeholder post, `_publications/`, sample files; point "Blog Posts" to Access Denied.
6. Rewrite or remove the Terms page; drop unused MathJax/Plotly/Mermaid scripts.
