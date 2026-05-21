# Kavrochori Property Website

Static FSBO (for-sale-by-owner) landing page for a residential property in Καβροχώρι, Γάζι, Ηράκλειο. Single `index.html` file with inline CSS and vanilla JS. No build step, no backend, no dependencies.

Deployed as a static site at kavrochori.gr (GitHub Pages via CNAME).

## Deliberate non-features

This is a single-property landing page with low change frequency and no commercial
processing. The following are intentionally absent — do **not** propose adding them
without a clear new reason:

- **Analytics / tracking pixels.** No GA, no GTM, no Plausible. Privacy + simplicity
  + avoids needing a cookie banner. Owner does not need traffic stats.
- **Cookie banner.** Direct consequence of "no analytics" — there are no consent-
  required cookies to disclose.
- **Service Worker / PWA / `manifest.json`.** One static page; offline value is zero.
  Adds cache-invalidation footguns in exchange for nothing.
- **Booking flow / calendar / payment integration.** This is a sale, not a rental.
  Conversion is "buyer emails owner."
- **AI chat widget.** Vendor-skewed selection bias on serious property inquiries;
  buyers want a human at this price point.
- **`Review` JSON-LD on first-party content.** Google's 2019 self-serving-review
  rule disallows it. The existing `RealEstateListing` schema is the right type.
- **Test suite, CI, Lighthouse-CI, error tracking.** Single page, ~weekly edits,
  visual regression noticed on next visit. Premature for the scope.
- **`llms.txt`.** Bot logs show ~zero fetches; low signal.
- **Multiple HTML pages.** `/privacy.html` and `/404.html` are the only exceptions.
  Anything new should fit on the index or be argued for explicitly.

## Agent workflow

Default to read-only inspection unless the user explicitly asks for edits.

Before making changes:
- Read the relevant file/range first and preserve the static, no-build nature of the site.
- Keep the site privacy-first: do not add analytics, tracking, cookies, or third-party widgets unless explicitly justified.
- Do not add backend dependencies, build tooling, CI, tests, service workers, or extra pages without a clear new reason.
- Do not deploy, push, or change repository remotes without explicit user approval.

When editing:
- Keep changes minimal and localized.
- Preserve multilingual variants (`/en`, `/de`, `/nl`, `/he`, `/fr`) when content or SEO changes affect the public page.
- Validate HTML/JSON-LD syntax where relevant.
- Summarize changed files and any follow-up risks clearly.

Communication:
- Prefer concise Greek replies unless the user asks otherwise.
- State assumptions explicitly when context is incomplete.
