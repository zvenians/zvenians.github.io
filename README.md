# Zvenians — Product Presentation Study

**A multi-page frontend study of editorial product storytelling and responsive interface composition.**

Built with HTML, CSS, and Bootstrap's navigation components, this project explores large-format hero layouts, visual rhythm, compact navigation, and product-oriented page hierarchy.

[View the site](https://zvenians.github.io/) · [Source repository](https://github.com/zvenians/zvenians.github.io)

[![Static site checks](https://github.com/zvenians/zvenians.github.io/actions/workflows/static-site.yml/badge.svg)](https://github.com/zvenians/zvenians.github.io/actions/workflows/static-site.yml)

> **Independent design study.** This website is not affiliated with, endorsed by, or operated by Apple Inc. Product names and images belong to their respective rights holders. It is not an official store or sales channel.

---

## Project brief

The exercise focuses on the parts of a product website that are easy to get wrong: scale, spacing, image placement, typography, and the transition between a large hero and smaller supporting sections.

Rather than assembling unrelated components, the pages reuse a small set of layout patterns with consistent spacing and navigation behavior. The project is a frontend demonstration, not a commerce platform.

## Site map

| Page | Content | Source |
| --- | --- | --- |
| **Home** | Product-led hero compositions and a brief presentation of the design direction | [`index.html`](index.html) |
| **Mac** | Product narrative, image/text combinations, and detail sections | [`mac.html`](mac.html) |
| **Store** | Retail discovery *concept*, without actual checkout processing | [`store.html`](store.html) |
| **Biodata** | Editorial profile and creator information | [`biodata.html`](biodata.html) |
| **Contact** | Links to public creator and portfolio destinations | [`contact_us.html`](contact_us.html) |

Navigation uses Bootstrap 5's collapsible component on smaller screens. The previously unused custom navigation script is not part of the current site.

## Design system

### Typography

A system-font stack with native Apple font fallback is used for the general typographic treatment. No proprietary font package is distributed in this repository.

### Layout

- Wide product heroes with separate copy and image regions.
- Alternating dark and light presentation sections.
- Container widths and spacing rules shared across pages.
- Responsive stacking to keep content readable on narrower screens.
- Simple inline text links rather than controls pretending to initiate a purchase.

### Visual language

| Token | Intent |
| --- | --- |
| `#f5f5f7` | Quiet background for product information |
| `#1d1d1f` | Primary body and heading text |
| `#000000` | Dark campaign surfaces |
| `#ffffff` | Open, high-contrast presentation areas |
| `#0071e3` | Link and action color |

See [`css/styles.css`](css/styles.css) for the implemented CSS variables and layout rules. These values describe this study; they are not a claim of compliance with an external brand specification.

## Technical architecture

```text
Browser
  ├─ HTML pages                  Content and semantic landmarks
  ├─ css/styles.css              Shared typography, navigation, layout
  ├─ Bootstrap CSS and JS        Responsive navigation component
  └─ assets/images/              Product presentation images
```

There is no application server, account database, product catalog API, payment service, or order-processing backend in this repository.

## Folder layout

```text
.
├── index.html                     Homepage
├── mac.html                       Product presentation
├── store.html                     Store design concept
├── biodata.html                   Profile
├── contact_us.html                Contact links
├── css/styles.css                 Responsive visual system
├── assets/images/                 Presentation imagery
└── tests/
    ├── static-site.test.mjs       Markup, links, and assets
    └── browser-smoke.mjs          Chromium mobile/desktop checks
```

## Local preview

```bash
git clone https://github.com/zvenians/zvenians.github.io.git
cd zvenians.github.io
python -m http.server 8000
```

Open [`http://localhost:8000`](http://localhost:8000). The layout loads Bootstrap from a CDN, so the browser needs network access for its external assets.

## Checks

```bash
node --test tests/static-site.test.mjs
```

The static suite checks semantic landmarks, heading structure, internal fragment targets, missing local resources, and placeholder links. Browser smoke checks cover the five pages at phone and desktop widths and the mobile navigation interaction.

To run the Chromium test locally:

```bash
npm install --no-save --no-package-lock playwright@1.62.1
npx playwright install chromium
node tests/browser-smoke.mjs
```

GitHub Actions uses Node.js 24 for these checks. A passing CI run is a useful regression signal, not a blanket accessibility or visual certification.

## Hosting

This repository is intended to be served through GitHub Pages at [zvenians.github.io](https://zvenians.github.io/). Static files can also be hosted on any server that respects the same relative paths.

Before publishing, verify the selected branch/folder in repository Pages settings and check all public navigation destinations. Do not assume a merged README change automatically validates the live site's content.

## Image rights and attribution

`assets/images/` contains Apple-related promotional imagery used for this personal educational presentation study. Those files are not presented as original product photography. Copyright, trademarks, and publicity rights remain with their respective owners. Use replacement imagery with appropriate licensing for commercial work.

## Boundaries and further work

The store page demonstrates interface composition only. Functional checkout, authenticated accounts, stock synchronization, and payment handling are **out of scope**. Any implementation of those features would require a separate architecture and security review.

---

**Developed as a frontend study by [@zvenians](https://github.com/zvenians).** Independent of Apple Inc.
