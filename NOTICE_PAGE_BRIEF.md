# NOTICE PAGE BRIEF — `obitech-demo`

## Task
Add ONE new page to this repo: `notice/index.html`, so it is served at
`https://obitech-demo.netlify.app/notice/`.

This page is where people land when they visit `tributes.casflowsystems.com` directly, or open a
memorial short link that is mistyped or no longer active. Visitors may be grieving family members
or funeral directors. The tone must be calm, quiet, and kind.

This brief explicitly authorizes a second HTML page in this repo. All other rules in `CLAUDE.md`
still apply.

## Scope rules
- Create `notice/index.html` only.
- Do **not** modify, rename, or delete any existing file (`index.html`, `README.md`, `CLAUDE.md`,
  `DEMO_PAGE_BRIEF.md`, this brief).
- Open a pull request. **Never merge.**
- This repo is **public**: no email addresses, phone numbers, pricing, account IDs, or credentials
  anywhere in the page, comments, commit messages, or PR text.

## Page text (use exactly as written; a typographic apostrophe ’ is fine)
1. **Headline:** Memorial Links
2. **Main paragraph:** If you were trying to open a memorial link from a service program, it may
   have been mistyped or may no longer be active. Please reach out to the funeral home that
   provided the program. They'll be glad to help.
3. **Director line** (below a thin divider, smaller and quieter than the main paragraph): Memorial
   programs and QR links for funeral homes, by CAS Flow Systems.
4. **Footer:** Memorial links by CAS Flow Systems

No other visible text. No "Sample" label, no "Example" labels, no cards, no icons, no buttons.

## Design (match the existing demo page `index.html`)
- Colors: page background (paper) `#F7F3EC`, ink (headline) `#3A332D`, body text `#4E4740`,
  divider lines `#E6DED2`, gold `#B8955A` for the short rule under the headline only — gold is
  **never** used for text.
- Fonts: Playfair Display 700 (headline), EB Garamond 400 and 400 italic (everything else), loaded
  from Google Fonts, with serif fallbacks.
- Layout: single centered column, max width about 560px, generous vertical spacing, vertically
  centered or comfortably placed in the upper-middle of the screen.
- Sizes: main paragraph at least 18px. Director line may be 15–16px (italic is fine). Footer may be
  12–14px.
- If `index.html` has a gentle fade-in, a matching one is fine, disabled under
  `prefers-reduced-motion`. Otherwise, no animation.

## Technical requirements
- Single self-contained file: inline CSS, **no JavaScript**, no images, no links of any kind.
- `<meta name="robots" content="noindex">`.
- `<meta name="viewport" content="width=device-width, initial-scale=1">`.
- `<title>Memorial Links</title>`.
- The only external requests allowed are Google Fonts.
- No tracking, no analytics, no cookies.
- No horizontal scrolling on a 375px-wide phone screen.

## Pass/fail checklist (report each item as PASS or FAIL in the PR description)
1. Only `notice/index.html` was added; `git diff` shows no change to any other file.
2. All visible text matches the four items above, word for word, and nothing else is visible.
3. No email addresses, phone numbers, or links anywhere in the file.
4. `noindex`, viewport, and `<title>` tags present.
5. No `<script>` tags; the only external URLs are Google Fonts.
6. Gold `#B8955A` used only on the rule under the headline, never on text.
7. Paragraph text at least 18px; director line 15–16px; footer 12–14px.
8. No horizontal scroll at 375px width.
9. The PR description gives the Netlify deploy-preview address for this page
   (`deploy-preview-N--obitech-demo.netlify.app/notice/`).
