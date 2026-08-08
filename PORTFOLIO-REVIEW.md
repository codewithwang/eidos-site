# PORTFOLIO REVIEW — `eidos-site`

*Reviewed 2026-08-08, against the working hypothesis: "personal data → agentic synthesis → owned, governed media surfaces." All claims below are verifiable from this repo or from the live site.*

---

## 1. What it is

This is the holding page for eidos.id — a custom domain served by GitHub Pages. The entire site is one hand-written HTML file showing a logo, the wordmark "eidos.id," and the words "Coming soon." There is no application, no content, and no code beyond that single page.

## 2. Honest assessment

**What genuinely impresses.** The craft-per-byte is high for what it is. The page is completely self-contained: the brand font (a 36 KB WOFF2 subset of Petrona) and the logo (a 7 KB PNG) are inlined as data URIs, there is zero JavaScript, and there are zero external references of any kind — the whole site renders from exactly one HTTP request. It's deployed on an owned domain with a `noindex` meta tag, which is the right call for a placeholder: dark until there's something to find. The commit history also shows brand discipline — two of the five commits exist solely to replace a wrong logo mark with the correct one.

**What a skeptical senior engineer critiques.** There is nothing to be skeptical *about*, and that's the critique: this repo makes no technical claims, so it can't back any. No build system, no tests, no CI — defensible for 37 lines of HTML, but it means the repo demonstrates taste, not engineering. The 7 KB logo PNG is embedded twice (identical base64 for favicon and body image), a ~9 KB duplication that a build step would have caught — a small tell that this was hand-assembled, not tooled. The commit log shows CNAME delete/recreate churn within a single day, i.e. DNS/Pages setup was figured out live in production. And operationally, "uptime" here is GitHub Pages' uptime; the repo owns none of it.

**Ratings.**
- **As a product prototype: 1/10.** It does not prototype a product. It reserves a name. Nothing about the eventual product's behavior, data model, or UX can be inferred from this repo.
- **As a proof-of-concept: 4/10.** If the concept is "I control an owned, branded surface and can ship to it," that is proven: real domain, live deployment, deliberate presentation. If the concept is anything more — governed publishing, a content pipeline, synthesis output — none of it is here yet. It's a proven front door to an empty room.

## 3. Proof points

All verified from the repo and the live site on 2026-08-08:

1. **Live in production**: `https://eidos.id` returns HTTP 200 from GitHub Pages, serving exactly this repo's 68,117-byte `index.html` (ETag matches file size).
2. **Radically self-contained**: 0 JavaScript, 0 external requests. Font (35,964 bytes WOFF2) and logo (7,076 bytes PNG) are inlined; first paint costs one HTTP request.
3. **Minimal by any measure**: 2 files in the repo, 37 lines of HTML, 5 commits total — shipped from first commit to live custom domain in 2 days (Jul 28–29, 2026).
4. **Deliberately unlisted**: `<meta name="robots" content="noindex">` keeps the placeholder out of search until launch.

## 4. Portfolio material

**One-line pitch:** The owned front door for eidos — a live, zero-dependency landing page on a custom domain, holding the surface where synthesized personal media will eventually be published.

**What it does:** eidos-site serves the eidos.id domain via GitHub Pages. It presents the brand — logo, wordmark, typeface — in a single self-contained HTML file with no scripts, no trackers, and no external requests, and it stays out of search indexes until there's something behind it. That's the full feature list, and it is honest about being exactly that.

**Place in the stack (hypothesis test):** The hypothesis is "personal data → agentic synthesis → owned, governed media surfaces." This repo sits at the far right of that arrow — it *is* the owned surface, or will be. But tested honestly: **this project does not yet demonstrate the hypothesis.** It contains no personal data, no synthesis, and no governance mechanism — no pipeline delivers anything to it, and nothing in the repo connects it to the life-os system where the first two stages actually live. What it proves is the precondition: the surface is owned (custom domain, own repo, no platform intermediary beyond static hosting) and deployable. In a portfolio, present it as the claim staked, not the claim proven — the hypothesis gets tested the day life-os publishes its first synthesized artifact here, and not before.

## 5. Screenshots to take

1. **The live page at `https://eidos.id`** in a desktop browser with the address bar visible — the custom domain plus rendered lockup is the whole proof that it runs.
2. **DevTools Network panel on a hard reload** of eidos.id — one document request, zero subresources, ~68 KB. This is the "zero-dependency, self-contained" claim made visible in a single frame.
3. **The same page on a phone-width viewport** — the flexbox-centered lockup holds up at mobile sizes, showing the one page it has was actually finished.
