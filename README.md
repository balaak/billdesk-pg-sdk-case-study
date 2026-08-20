# BillDesk Payment SDK — Case Study

**Live:** https://balaak.github.io/billdesk-pg-sdk-case-study/

A hiring-facing case study on the BillDesk Payment SDK: a pre-built payment
screen merchants embed in their own app and brand as their own, rebuilt across
five platforms. Design lead, 2023–2026.

---

## What's in here

| Path | What it is |
|---|---|
| `index.html` | The whole site. One file, no build step, no dependencies. |
| `media/` | Screen recordings and stills embedded in the page. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is. |

The page is static: no framework, no bundler, no JavaScript beyond a single
`IntersectionObserver` that plays each video while it's on screen and pauses it
when it isn't.

## Hosting

GitHub Pages, published from the `main` branch at the repository root. Pushing
to `main` redeploys — usually live within a minute.

## How the page is produced

The source of truth is a small in-browser CMS (`case-study-workbench.html`,
kept outside this repo) where the copy is edited and the media slots are
filled. `build-site.py` reads that file plus an exported manifest and emits
this directory:

```bash
python3 build-site.py pgsdk-manifest-YYYY-MM-DD.json
```

It strips the editing chrome, applies the text edits, drops hidden sections,
copies the matching media files in, and wraps the result in a standalone HTML
document. The stylesheet is carried over verbatim, so the spacing rhythm and
type scale are identical to what was signed off in the workbench.

## Design notes

- BillDesk UI light-v2 tokens, used as-is — light only, committed rather than defaulted.
- Heading-to-subtext gap is 8px throughout, desktop and mobile.
- Content column caps at 1180px inside a wider container.
- Eleven layout patterns (split, statement, evidence, triad, bento, sequence)
  carry the variety; the argument sections share one consistent left spine.

---

© Bala Kumaran · [hello@91pixels.com](mailto:hello@91pixels.com)
