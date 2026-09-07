# Handoff: Run Your Search — Marketing Site

## Overview
Single-page marketing/signup site for "Run Your Search," an async 1:1 job search coaching service for experienced software engineers, run by Dan Johnson. Repositions his existing "Run The Ladder" brand/design language around a simpler offer: $399/month, cancel anytime, weekly personally-written job search routine.

## About the Design Files
The bundled file (`Run Your Search.dc.html`) is a **design reference built in HTML** — a working prototype showing the intended look, copy, and layout. It is not production code to paste as-is. Recreate it in the target codebase's existing environment (React, Next.js, etc.) using that codebase's own component and styling conventions — or choose an appropriate framework if none exists yet.

## Fidelity
**High-fidelity.** Colors, type, spacing, and copy are final. Recreate pixel-for-pixel where practical.

## Screens / Views
One single-page scrolling site, in this order:

1. **Sticky header** — wordmark left ("Run Your Search," Archivo 800, 15px, uppercase, letter-spacing .14em), single CTA button right ("Start Your Search," links to Calendly intro call: `https://calendly.com/danielljohnson/intro`). Wraps on narrow viewports instead of overflowing.
2. **Hero** — full-bleed section with the uploaded mountain illustration as a background image (faded via a bottom-heavy linear-gradient overlay from ~55% to solid background color so text stays legible), two-column grid (text left, photo of Dan right on ≥768px, stacks on mobile).
   - Eyebrow pill: "Async 1:1 job search coaching for software engineers"
   - H1 (Anton, uppercase, ~clamp(46px,7vw,88px)): "Your job search needs a **routine.**" (routine in accent red #C3402B)
   - Body paragraph, then a bold standalone line: "You put in the reps. I program the training."
   - CTA button + "$399/month" text
   - Small print: "Not an AI tool. Not a course. Not a community. An opinionated approach to running your job search from someone who's actually done it before."
   - Photo card: Dan's photo, aspect-ratio 4/5, with an overlapping label chip "Dan Johnson · your coach"
3. **How It Works** — tinted background band (#EFEBE3). Eyebrow "How it works," heading "Six steps, then it loops," and a step-summary line "Assess → Kickoff → Routine → Reps → Review → Repeat." Below: a 6-cell responsive grid (1px hairline borders forming a table look) — Assess, Kickoff, Get your routine, Put in the reps, Review, Repeat (last cell dark/inverted #17160F). Below the grid: 3 short callout lines with a left accent border, each ending "The routine changes."
4. **Why Dan** — two-column: bio copy left (credentials verbatim from runtheladder.co: Netflix engineer, founding engineer, director of engineering, instructor, 5 years interviewing at Netflix, ski academy/Olympic-athlete training background), stat tiles right (20+ years, Netflix, 5 yrs interviewing, 90+ engineers coached) in a 1px-bordered grid.
5. **Testimonials** — dark section (#17160F background, cream text). 4 testimonial cards in a responsive grid, each a quote + role/company caption. All testimonial text is verbatim (or verbatim-shortened) from the existing Run The Ladder site — do not alter wording.
6. **Compared to 1:1 coaching** — tinted band (#EFEBE3). Two side-by-side cards: "Typical 1:1 coaching" (light card, muted/negative framing) vs "Run Your Search" (dark card, $399/month, positive framing). Closing accent-bordered line about optional $99 calls.
7. **Pricing** — two-column: price block left ($399, "/ month", CTA), included-features checklist card right (8 line items) plus a footer row for "Optional additional 30-minute 1:1 calls · $99."
8. **Footer** — dark (#17160F). Wordmark + tagline "Routine beats luck." left; links right: Start Your Search (Calendly), LinkedIn (`https://www.linkedin.com/in/danielljohnson/`), email (`hello@runtheladder.co`).

## Interactions & Behavior
- All primary CTAs ("Start Your Search") link out to the Calendly intro call URL — there is intentionally no on-page signup form (removed per client request; they don't want webforms).
- Anchor links use `scroll-behavior: smooth`.
- Buttons/links have hover states (darken to #17160F, or brighten to cream on dark backgrounds) — see inline `style-hover` attributes in the source for exact values.
- Fully responsive: grids use `repeat(auto-fit, minmax(...))`; header wraps rather than overflowing; no fixed-width elements outside the max-width:1120px content container.

## State Management
None — this is a static marketing page. No client-side state, no forms, no data fetching.

## Design Tokens
**Colors**
- Background (paper): `#F5F2EC`
- Background alt/tint band: `#EFEBE3`
- Card surface: `#FFFCF7`
- Ink (text/dark sections bg): `#17160F`
- Cream text on dark: `#FFF9F2`
- Accent red: `#C3402B`
- Accent peach (used on dark bg for eyebrow labels/links): `#E8836A`
- Hairline borders: `rgba(23,22,15,.12)` to `rgba(23,22,15,.22)` depending on emphasis

**Typography**
- Body/UI: Archivo (400/500/600/700/800), via Google Fonts
- Display headlines (short, punchy only — H1, step titles, stat numbers, big price): Anton, uppercase, tight/normal letter-spacing
- Sentence-length headings (e.g. multi-clause H2s) stay in Archivo 700 — Anton was found illegible/awkward for long sentences, only use it for short phrases
- Eyebrow labels: Archivo 800, 11px, letter-spacing .2em, uppercase, accent red

**Spacing/Layout**
- Content max-width: 1120px, horizontal padding 24px (20px in header)
- Section vertical padding: ~76–84px top/bottom
- Card/grid gaps: 1px hairline grid pattern for step/stat blocks (background color shows through as the border), 20–28px gaps elsewhere
- Border radius: 2px only (buttons, inputs) — intentionally sharp/architectural, not rounded-card style

## Assets
- `assets/hero-background.png` — user-supplied mountain/autumn illustration, used as hero section background image beneath a gradient overlay.
- Dan's headshot is currently hot-linked from `https://www.runtheladder.co/dan.jpeg` — replace with a locally hosted asset in production.

## Files
- `Run Your Search.dc.html` — full page source (all markup + inline styles + minimal logic class, no external CSS files; everything is inline style attributes by design-tool convention — feel free to extract to a stylesheet/theme in the real implementation).
