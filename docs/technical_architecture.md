# Flora Chao — Technical Architecture

**Version:** 1.0
**Status:** Draft
**Architecture:** Static HTML
**Primary Runtime:** The browser, from the files in this folder
**Package Manager:** None
**Host:** None configured

**Related:** [product_architecture.md](product_architecture.md) · [sprint.md](sprint.md)

---

# 1. Overview

This repository delivers Flora Chao’s portfolio as a static page. Open `index.html` in a browser. There is no build step.

The system provides:

- One HTML document
- A stylesheet
- A theme choice stored in the browser
- A mailto link

There is no application API, no database, no package manager, and no host configuration. The information architecture is in the product document. This document describes how that page is built.

---

# 2. Repository

```text
chao-portfolio-/
│
├── docs/
│   ├── product_architecture.md
│   ├── technical_architecture.md
│   └── sprint.md
│
├── index.html       copy, nav, theme script
├── styles.css       layout and tokens
├── favicon.svg      “FC” mark
├── README.md
├── LICENSE
└── .gitignore
```

Copy lives in `index.html`. It is not split into content modules.

---

# 3. How the page is served

```text
index.html
    │
    ├── inline script     theme before first paint
    ├── styles.css        layout and colour
    └── favicon.svg       icon

Open the file, or serve the folder as static files.
There is no compile step and no dist/ directory.
```

Fonts are loaded from Google Fonts: Fraunces for headings and the wordmark, Source Sans 3 for body text. If those requests fail, the page falls back to Palatino for headings and Segoe UI for body text.

---

# 4. Theme

`index.html` reads `localStorage` key `flora-theme` before the body is painted and sets `data-theme` on the document element. Allowed values are `light`, `dark`, and `system`. Anything else is ignored. If storage is unavailable, the choice still applies for that visit and the default is `system`.

`setFloraTheme` writes the choice and sets `aria-pressed` on the matching header button.

`styles.css` maps each theme to tokens. `system` follows `prefers-color-scheme`. A short style block in `index.html` sets the paper background before the stylesheet arrives, so the first paint matches the saved choice.

---

# 5. Tokens

```text
--paper          page background
--ink            text
--muted          secondary text
--line           rules
--accent         focus and emphasis
--surface        cards
--placeholder    the dashed social-link note
--measure        68ch reading width
--wrap           70rem page width
```

Light paper is `#f4f0e7` with ink `#1c1915`. Dark paper is `#1a1714` with ink `#f4f0e7`.

---

# 6. Layout

The header, hero, sections, and footer share one width. The header is sticky. Below 760px the header and hero stack.

`prefers-reduced-motion: reduce` turns off smooth scrolling. Focus uses a 2px accent outline.

Landmarks in the document: skip link, `header`, `nav`, `main`, `footer`. The document language is English. The theme group is labeled. The contact placeholder is visible text, not colour alone.

---

# 7. Contact

Mail is the visitor’s own mail program.

```text
<a href="mailto:Chaokiteria@gmail.com">
```

There is no form, no honeypot, and no host inbox. Social links are the only placeholder. They stay empty until real URLs are provided.

---

# 8. Assets and secrets

The favicon is an original “FC” mark in `favicon.svg`. There is no Open Graph image.

No API keys belong in this repository. The email address is public because it is the contact method on the page.

---

# 9. What is out of scope

```text
A package manager
A compiler or bundler
A test runner
A contact form
A server
A configured host or public URL
```

A public URL can be added later by putting these same files on a static host. That does not require a new application.
