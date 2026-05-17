# AI Readiness Test

**Status:** v0.1 shipped 2026-05-16 (autonomous workshop block). From `ideas-backlog.md`. Single-file static HTML/JS, no backend, no tracking, no email capture.

## What it does

A 10-question diagnostic for small business owners and team leaders. Returns a 0-30 score, places them in one of 4 tiers (AT RISK / WAKING UP / MOVING / BUILDING THE FUTURE), gives 3 calibrated next-step recommendations, and ends with a CTA to purcellventures.co/consulting.

## Why this is a lead-gen funnel

Each tier's recommendations are explicitly designed to map a user back into Elijah's existing consulting offer:

- **AT RISK** → 2-hour AI Basics for Business session
- **WAKING UP** → 3-hour hands-on (ChatGPT or Marketing)
- **MOVING** → Custom Team Training
- **BUILDING THE FUTURE** → Strategic consult (different conversation, different cadence)

The CTA is honest — explicitly says "no upsell, I'll tell you which session fits or tell you straight up that you don't need one." Same brand voice as the consulting page.

## How to use

Just open `index.html` in a browser. Fully self-contained — no build step, no dependencies.

## How to ship to production

Two paths:

### Path A: drop into purcell-ventures-site (recommended)

Create `app/ai-readiness/page.tsx` and port the markup + JS to a Next.js client component. Same brand colors (already used inline in this file's CSS — matches the warm/Soft Autumn palette).

Add link from the main consulting page hero: "Not sure if you need this? Take the 3-minute AI Readiness Test →"

Live URL would be `purcellventures.co/ai-readiness`. SEO-friendly title + description already in the HTML head.

### Path B: standalone GitHub Pages

Push this dir to a new GitHub repo, enable Pages. Live at `<elijah>.github.io/ai-readiness-test` or a subdomain. Slower to integrate but no PV site coupling.

## Conversion assumptions baked in

- 3 minutes is the time-cost-anchor stated upfront (low friction)
- No email capture — score lives in browser. Removes the typical "lead magnet" friction. Trades email capture for higher completion + share-ability.
- Score visible to user, not to Elijah, by design — this is a real diagnostic, not a sales tool wearing a diagnostic costume.
- CTA at end is the ONLY conversion ask. Single funnel.

## v0.2 ideas (NOT shipped tonight)

- Optional "Email me my report" form post-result (consent-based capture)
- Industry-specific question variants (real estate vs marketing agency vs solo founder)
- "Compare to 1,000 other business leaders" — aggregate scoring requires backend
- A/B test: which CTA copy converts? (Needs analytics)
- Embeddable iframe version for partner sites

## Test it

Open `index.html` in any browser. Answer 10 questions. Verify:
- All 4 tiers reach-able with different answer patterns
- Back button works on questions 2-10
- Start-over link works
- Mobile layout looks clean (max-width 760px container handles small screens)
- All CTAs link to `https://purcellventures.co/consulting`

## Why I (ElijahBot) built this

You asked for "build something new, work on one of my projects." This is one of the bigger backlog ideas that's been sitting since I had visibility — and it's the rare one that's BOTH new infrastructure AND a direct revenue lever for your existing consulting business. Plus it's pure-static so no risk of breaking anything live.
