# chrontext.ai — site - v3_18 Jun 2026 README (OLDER version)

A single-page marketing site plus a gated live demo, in the Chrontext design system.

## Files (keep them together)
- `index.html` — the landing page
- `demo.html` — the gated Entity Lens viewer (the page the email gate opens)
- `chrontext-logo.png` — the brand mark (used in both headers/footers)
- `favicon.png` — browser-tab icon

Drop all four onto any static host (Netlify, Vercel, Cloudflare Pages, GitHub Pages, S3, etc.). No build step.

## Go-live: set 3 values
Open `index.html`, scroll to the `CONFIG` block near the bottom of the file, and fill in:

1. **`WEB3FORMS_KEY`** — to actually email demo-gate submissions to `info@chrontext.ai`.
   - Sign up free at https://web3forms.com, set the receiving address to `info@chrontext.ai`, copy the access key, paste it here.
   - Left blank, the gate still validates the email and opens the demo — it just won't send the notification email yet.
2. **`CALENDLY_URL`** — your scheduler link for design-partner calls. Blank = the "Book a call" button falls back to an email link.
3. **Emails** — `INFO_EMAIL` (demo notifications + footer), `PARTNER_EMAIL` (the design-partner "Get in touch" link and the "Book a call" email fallback), and `EXPLORE_EMAIL` (the "Explore Chrontext" / interested-customer "Get in touch" link). Currently `info@`, `partner@`, and `explore@` at `chrontext.ai` — all pre-filled; change only if your routing differs.

## Two things to know
- **The email check is format-only.** Client-side JS can confirm an address is *well-formed*, not that it's deliverable. Real deliverability shows up as bounces in whatever inbox the form service delivers to.
- **The demo gate is soft lead-capture, not hard access control.** `demo.html` is a normal page and is directly reachable by URL/sharing. That's the right trade for a top-of-funnel demo. If you ever want true gating, it needs a server-side step (issue a token on submit, verify it before serving the demo) — easy to add later.

## When the Chron spec goes public
Two spots are marked with `EDIT LATER` comments in `index.html` (search for it): the OSS badge in section 05 and the spec language in the footer. Swap the "public release coming" badge for a real link to the repo/spec.

## Browser tab
Tab title is set to `01> | chrontext.ai` — the "01>" being the ASCII echo of the logo (dot, bar, chevron). Change the `<title>` in each file's `<head>` if you'd prefer something else.

## Swapping the logo
`chrontext-logo.png` is the mark lifted straight from the deck. To replace it, drop in a new PNG/SVG at the same filename (or update the `<img src>` references in both HTML files).
