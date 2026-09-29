# Website feedback — rya-sge.github.io

Review of the site content and configuration as of 2026-09-29, based on the repository sources (the site was not built locally). Items are ordered by priority within each section and identified by section number and letter (e.g. `1.a`).

**Status legend:** ✅ Done · 🟡 Partially done · ⬜ Open

**Progress:** 26 done, 2 partially done, 22 open.

## 1. High priority — visible on every page

- **1.a** ✅ **Site title is still the template placeholder.** `_config.yml:12` had `title: "Your Name / Site Title"`, shown in the header on every page and in every browser tab / search result.
  - Done: set to `"Ryan S."`.
- **1.b** ✅ **Site name and description are placeholders.** `_config.yml:14-15` had `name: "Your Name"` and `description: "Your Name's academic portfolio"`, used in the footer, the meta description and social previews.
  - Done: `name: "Ryan S."`; `description: "Security engineer and blockchain developer: CMTAT, tokenization, cross-chain and smart contract security"` (also reused as `og_description`).
- **1.c** ✅ **Repository URL is wrong.** `_config.yml:19` was `https://github.com/rya-sge.github.io`, which is not a valid repo.
  - Done: set to `rya-sge/rya-sge.github.io` (the `owner/name` form expected by the GitHub Pages metadata plugin, matching the git remote).
- **1.d** ✅ **No social preview image.** `og_image` and `teaser` were empty, so links shared on LinkedIn/X had no picture.
  - Done: `og_image: "favicon.jpg"` (same picture as `profile.png`, which is actually a JPEG with a `.png` extension), `twitter.username: "ADCDIII"` (required for X card tags), and `_includes/seo.html` now emits an `og:image` tag and absolute image URLs.
  - Still open: the image is a 400×400 square, so previews show a small thumbnail; a 1200×630 banner would give the large preview.
- **1.e** ✅ **Web manifest still names the template icon.** `images/manifest.json` had `"name": "OOjs UI icon academic-progressive"`, and `_includes/head/custom.html` had a stale comment about the template favicon source.
  - Done: manifest `name` and `short_name` set to `"Ryan S."`; stale comment removed.

## 2. CV page (`_pages/cv.md`)

- **2.a** ✅ **Leftover template text:** "Service and leadership — Currently signed in to 43 different slack teams" (`cv.md:99-101`). Remove the section or replace it (e.g. Y-CTF co-founder, conference talks).
  - Done: "Service and leadership" section removed (Y-CTF is already listed under Education).
- **2.b** ✅ **Empty "Publications" section.** It loops over `site.publications`, but `_publications` is not declared as a collection in `_config.yml`, and the files in it are template placeholders ("Paper Title Number 1…"). The heading therefore renders with nothing under it. Either list the Taurus articles directly (as in `publications.md`) or remove the section.
  - Done: the `site.publications` loop replaced by a link to `/articles/`.
- **2.c** ✅ **Empty "Teaching" section.** `site.teaching` does not exist; remove the section.
  - Done: section removed.
- **2.d** 🟡 **Skills section is thin and oddly structured:** "Solana" sits outside "Smart contract development", and there is nothing on security (audits, pentest, cryptography), tooling (Foundry, Hardhat, Slither, Aderyn) or other chains you present in talks (Tezos, Aztec, Zama FHE, Stellar/Soroban…). This is the section recruiters scan first.
  - Done: skills regrouped into smart contract development (Solidity with Foundry/Hardhat/Truffle, SmartPy, Move, Solana), tokenization and standards, cross-chain and integrations, privacy (Zama FHEVM, Self zero-knowledge identity), security (analysis, pentest, cryptography, Y-CTF) and other languages.
  - Still open: Slither, Aderyn, Aztec and Stellar/Soroban were not added as skills, because nothing in the repository shows hands-on work with them; add them if they apply.
- **2.e** ✅ **Work experience summary is outdated relative to your talks.** The Taurus entry does not mention privacy work (CMTAT-Confidential with FHE, Aztec), the CMTAT audit process, or conference speaking (EthCC, BSA EPFL, Black Alps, CMTA x OpenZeppelin).
  - Done: the Taurus summary now covers the CMTAT security process (audits, static analysis, AI audit tools), partner integrations (Chainlink ACE and CCIP, LayerZero, FIX with Nethermind), privacy (CMTAT-Confidential with Zama FHE, the Aztec version) and conference speaking with a link to `/talks/`; CMTAT-Confidential, CMTAT-ACE, CMTAT-FIX, CMTAT-LayerZero and Smart Wallet 7702 were added to the public projects.
- **2.f** ✅ **Typos / consistency:** "Analyze of smart contracts", lowercase "position:" / "company:", "Duration:" lines duplicating the dates in the headings, "A rust-based application to store password securely".
  - Done: "Analysis of smart contracts", "SmartPy (Tezos)", "Company:" / "Position:" capitalised, duplicate "Duration:" lines removed (Taurus heading now reads "12/2022 - present"), "Rust-based application to store passwords securely".
- **2.g** ⬜ **Consider a downloadable PDF CV** in `files/` linked at the top of the page.

## 3. Home page (`_pages/about.md`)

- **3.a** ✅ **"Main article" section had an orphan sentence:** "Here my main articles on Blockchain:" was followed by nothing.
  - Done: sentence and extra blank lines removed; heading renamed "Main articles".
- **3.b** ⬜ **Duplicated content:** the article lists are copied from `publications.md` but are already out of date (the 2025 Taurus articles on conditional transfers and ERC-1400 are missing). Keep one source of truth: a short "highlights" list on the home page and link to `/publications/`.
- **3.c** ✅ **No mention of talks.**
  - Done: new "Talks" section with EthCC 2026 and Black Alps 2024 (talk page, video and slides links) and a link to `/talks/`.
- **3.d** ✅ **Inconsistent LinkedIn handle:** `about.md` linked to `/in/ryan-sauge`, while the sidebar used `ryan-sge`.
  - Done: both now use `ryan-sge` (`https://www.linkedin.com/in/ryan-sge`); an earlier fix had wrongly switched them to `rya-sge`, which is not a LinkedIn profile.
- **3.e** ⬜ **Tone:** "I hope you can find your happiness among this content" reads oddly; something like "Feel free to reach out on LinkedIn or X" is enough. The first line has a leading space (" Hi there 👋").
- **3.f** ✅ **Twitter/X naming:** the page said "twitter account" and mixed `twitter.com` and `x.com` links.
  - Done: home page says "an X account" and links to `x.com/ADCDIII`; the sidebar link in `_includes/author-profile.html` now points to `x.com`.
- **3.g** ✅ **Tab title** showed "Blockchain - Smart Contract - Security - Your Name / Site Title".
  - Done: resolved by 1.a; now "Blockchain - Smart Contract - Security - Ryan S.".

## 4. Publications page (`_pages/publications.md`)

- **4.a** ⬜ "Token Transfer Management … ERC-1404" has `(ERC-1404)` where the year should be (`publications.md:23`).
- **4.b** ⬜ Talks and slide decks are publications too; add a short "Talks" section linking to `/talks/` or list the four decks.
- **4.c** ⬜ The personal blog section only lists five articles; if some newer ones (e.g. the Bitcoin keys, MPC and Winternitz OTS posts linked from the Black Alps talk page) matter, add them.
- **4.d** ✅ The page title "Publications" with a section "My main personal articles" — consider renaming the nav item to "Articles" since there are no academic papers.
  - Done: page and nav item renamed "Articles", now at `/articles/`; `/publications/` redirects there (`jekyll-redirect-from`).

## 5. Portfolio page (`_pages/portfolio.md`)

- **5.a** ⬜ **Heading levels are inconsistent:** "Smart contract" uses a level-1 `======` heading with `####` projects, while "Rust" uses `##` with `###` projects.
- **5.b** ⬜ **CCIP Sender and IncomeVault have identical durations** (12/2023 — 05/2024); check that this is right.
- **5.c** ⬜ **IncomeVault skills list "Stablecoin"** although it is about dividends/coupons; "Tokenization · Corporate actions" would fit better. "build with CMTAT" → "built with CMTAT"; "Publish a blog post" → "Published a blog post".
- **5.d** ⬜ **Missing recent projects** you present in talks: CMTAT-Confidential (FHE / ERC-7984), CMTAT cross-chain, Aztec version, and the TERC-20 / TERC-721 / TERC-1155A repos listed in the CV.
- **5.e** ⬜ "**Skills:** cryptography security" → "Rust · Cryptography · Security".

## 6. Talks

- **6.a** ⬜ **Talk pages do not show venue and location.** `_layouts/talk.html:38` only prints the "Talk at venue, location" line when `page.talk_type` is set, but all talk files use `type`. Either add `talk_type: "Talk"` to each file or change the layout to test `page.type`.
- **6.b** ⬜ `_config.yml` has `talkmap_link: false` and the talkmap notebook is absent, but `.github/workflows/scrape_talks.yml` still runs on every change to `_talks/` and will fail (it executes `talkmap.ipynb`). Delete the workflow or add the notebook.
- **6.c** ⬜ The Black Alps talk page uses `\-` escaped dashes and two `lnkd.in` short links; replace these with normal bullet lists and the full blog URLs (short links hide the destination and can expire). A stray line break splits the Trezor URL (`_talks/2024-11-07-crypto-wallet.md`).
- **6.d** ⬜ Consider adding a thumbnail (`header.teaser`) per talk for a nicer Talks page.
- **6.e** ⬜ The EthCC 2026 location ("Cannes, France") was not taken from a source in the repo; confirm it.

## 7. Template leftovers still published

- **7.a** ✅ `_pages/markdown.md` → `/markdown/` (template's Markdown guide).
- **7.b** ✅ `_pages/archive-layout-with-content.md` → `/archive-layout-with-content/` (theme demo).
- **7.c** ✅ `_pages/non-menu-page.md` → `/non-menu-page/` ("This is a page not in the menu").
  - Done for 7.a–7.c and the post in 7.d: `sitemap: false` in front matter, so they are excluded from `sitemap.xml` and from the HTML `/sitemap/` page, and `_includes/seo.html` adds `<meta name="robots" content="noindex">` for such pages.
  - Done: all three pages deleted.
- **7.d** ✅ `_posts/2025-11-12-blog-post-1.md` → "Blog Post number 1" tagged "cool posts" (now hidden from sitemaps, see above). The "Blog Posts" nav item still leads to a year archive containing only this post. Replace the nav item with a direct link to `https://rya-sge.github.io/access-denied/`, and delete the post.
  - Done: post deleted; "Blog Posts" in the header now links to `https://rya-sge.github.io/access-denied/`.
- **7.e** ✅ `_publications/` — five placeholder papers ("Paper Title Number 1…").
  - Done: folder deleted.
- **7.f** ✅ `_data/authors.yml` — "Name Name" / "Name2 Name2" placeholders.
  - Done: file deleted (the includes that read it already handle its absence).
- **7.g** ✅ `markdown_generator/` — template scripts with placeholder TSVs; not needed if you write talks by hand.
  - Done: folder deleted.
- **7.h** ✅ `files/paper1.pdf`, `files/slides1.pdf`, `files/bibtex1.bib` — template sample files, publicly downloadable. The two PDFs are now excluded from `sitemap.xml` via `_config.yml` defaults, but still published; delete them.
  - Done: the three files deleted, and their `sitemap: false` defaults removed from `_config.yml`.
- **7.i** ⬜ `images/500x300.png`, `bio-photo.jpg`, `bio-photo-2.jpg`, `editing-talk.png` — template images.
- **7.j** ⬜ `README.md` — still the Academic Pages template README; a short personal README would help visitors of the GitHub repo.

## 8. Privacy / terms page (`_pages/terms.md`)

- **8.a** ✅ It claims the site uses **Disqus comments, Google Analytics and third-party advertisers**, none of which are configured. The page is dated 2016. Either rewrite it to reflect reality (GitHub Pages hosting; GitHub logs IPs; no cookies or analytics) or remove it.
  - Done: rewritten — Disqus, Google Analytics and third-party advertisers removed; the page now describes GitHub Pages hosting, the scripts loaded from cdnjs and jsDelivr, and the theme choice kept in local storage (no cookies).
- **8.b** ✅ Related: `_config.yml` defaults set `comments: true` for posts with no comment provider configured — harmless, but can be set to `false`.
  - Done: set to `false`.

## 9. Technical / SEO

- **9.a** 🟡 `_includes/footer/custom.html` loads **MathJax, Plotly (several MB) and Mermaid on every page**, although no page uses them. Removing them speeds up every page load, and removes the `polyfill` script, which is unnecessary for modern browsers (fewer third-party scripts is also a better look on a security engineer's site).
  - Done: the polyfill script (`cdnjs.cloudflare.com/polyfill/v3/polyfill.min.js`) removed; MathJax 3 does not need it. This is Cloudflare's mirror, not the compromised `polyfill.io` domain, so visitors were not exposed.
  - Still open: MathJax, Plotly and Mermaid are still loaded on every page.
- **9.b** ⬜ `publication_category` in `_config.yml` (Books / Journal Articles / Conference Papers) is unused.
- **9.c** ⬜ The large academic-profile block in `_config.yml` (arxiv, pubmed, scopus…) is empty and can be trimmed for readability.
- **9.d** ⬜ Check that `bluesky: "ad403"` is the right handle (other handles are `AccessDenied404` / `ADCDIII`).
- **9.e** ⬜ Slide PDFs: `2024-blackalps-crypto-wallet.pdf` is 6.6 MB; compressing it would make it faster to open on mobile.

## 10. Suggested next quick wins

1. ✅ Remove "43 slack teams" and the empty Teaching and Publications sections from the CV (2.a–2.c).
2. Add `talk_type` to talks or fix the layout so venue/location appear (6.a).
3. ✅ Delete the template pages, placeholder post, `_publications/` and sample files; point "Blog Posts" to Access Denied (7.a–7.h).
4. Rewrite or remove the Terms page; drop unused MathJax/Plotly/Mermaid scripts (8.a, 9.a).
