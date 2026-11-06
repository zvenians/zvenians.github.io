# Contributing

This repository is a static front-end concept.

- Keep HTML semantic, CSS organized, and JavaScript predictable.
- Ensure menus and links work with keyboard, touch, and pointer input.
- Test narrow screens, focus indicators, contrast, and reduced-motion settings.
- Preserve the educational nature of the project and third-party asset credits.
- Avoid unverified product specifications or misleading claims of affiliation.

## Review

Run the static-page and JavaScript checks:

```sh
node --test tests/static-site.test.mjs
node --check js/script.js
```

The CI workflow also runs Chromium browser smoke tests. To reproduce those locally, install the CI-pinned Playwright version and Chromium:

```sh
npm install --no-save --no-package-lock playwright@1.62.1
npx playwright install chromium
node tests/browser-smoke.mjs
```

Browser checks cover five pages at mobile and desktop widths, including the mobile navigation menu, horizontal overflow, and uncaught JavaScript errors. Check third-party asset attribution and real-device behavior separately; record checks not performed.
