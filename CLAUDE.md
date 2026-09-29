# CLAUDE.md — obitech-demo

Standing instructions for any Claude Code session working in this repository.
Read this whole file before doing anything. If a task file (such as
`DEMO_PAGE_BRIEF.md`) is also present, read it next. Where the two disagree,
**this file wins** unless the task file explicitly says it overrides a rule here.

> This repository is PUBLIC. Never add pricing, business strategy, account IDs,
> API keys, passwords, email addresses, or any other private information to it.

---

## 1. What this repository is

A single, small web page. It is what someone sees when they scan the **sample**
QR code printed in a presentation book that funeral homes place on their
arrangement table. The people scanning are usually **grieving family members on
a phone**, sometimes a funeral director showing how the QR code works.

The page explains, gently and honestly, what a memorial QR code does. It is a
sample only — it does not belong to any real person or family.

## 2. Hard rules — never break these

1. **Use approved text exactly.** Every word on the page comes from the task
   file, copied verbatim — same spelling, capitalization, and punctuation. Do not
   add, remove, reword, or "improve" any visible text. No extra headings,
   taglines, buttons, or calls to action.
2. **No prices** of any kind, anywhere.
3. **Never imply that CAS Flow hosts memorial content.** The real product's QR
   code opens a page the *family* already has elsewhere (a memorial fund, a
   charity, or a livestream). Do not add or suggest: a tribute page, photo
   gallery, guestbook, condolence form, comment box, sign-up form, or a "hub"
   page listing several links.
4. **Example cards are not links.** They must not be clickable and must not
   point anywhere.
5. **No tracking.** No analytics, cookies, pixels, chat widgets, pop-ups,
   banners, or third-party scripts. The only allowed external requests are
   Google Fonts (`fonts.googleapis.com` and `fonts.gstatic.com`).
6. **No external images and no photos of people.** Icons are inline SVG written
   into the page.
7. **No emoji** anywhere in visible text or code comments shown to users.
8. **Tone:** calm, warm, respectful. Nothing flashy, no animation beyond a very
   subtle fade-in (optional), nothing that moves on its own afterward.
9. **Do not change hosting setup.** Do not add `netlify.toml`, build tools,
   package managers, frameworks, or a build step. The site is plain static
   files served from the repository root.
10. **Do not edit `README.md`** unless the task file says to.

## 3. Brand tokens (match the printed presentation book)

Use these exact values. Define them once as CSS custom properties.

| Token | Value | Use |
|---|---|---|
| `--paper` | `#F7F3EC` | page background |
| `--card` | `#FFFDF9` | card background |
| `--line` | `#E6DED2` | card borders, hairlines |
| `--ink` | `#3A332D` | headings |
| `--body` | `#4E4740` | body text |
| `--gold` | `#B8955A` | accent rules and icon strokes **only** — never for text (contrast too low) |

**Fonts** (Google Fonts, `display=swap`):
- Headings: **Playfair Display**, weight 700. Fallback: `Georgia, "Times New Roman", serif`.
- Body: **EB Garamond**, weights 400 and 400 italic. Fallback: `Georgia, "Times New Roman", serif`.

Request only those weights/styles — nothing else.

**Signature detail:** a short gold horizontal rule (about 64px wide, 1–1.5px
thick) sits under the main headline, centered. This matches every page of the
printed book.

## 4. Quality bar

- **Mobile first.** Design for a 360–430px wide phone screen first, then make
  sure it still looks balanced on tablets and desktops (content column max width
  around 560–640px, centered).
- **Readable:** body text at least 18px on phones; generous line height (about
  1.5–1.6). Small labels, the word "Example", and the footer may be 12–14px as
  the task file specifies; the 18px minimum applies to paragraph text.
- **Accessible:** `<html lang="en">`, one `<h1>`, semantic sections, SVG icons
  marked `aria-hidden="true"` (their card title carries the meaning), text
  contrast meeting WCAG AA (4.5:1 for body text).
- **Fast:** one small HTML file with inline CSS. No JavaScript unless it is
  genuinely needed (it shouldn't be).
- `<meta name="viewport" content="width=device-width, initial-scale=1">`.
- `<meta name="robots" content="noindex">` — this is a sample and should not
  appear in search results.

## 5. How to work

1. Work on a **new branch**, never directly on `main`.
2. When finished, open a **pull request** into `main`. Netlify will create a
   preview link for it automatically.
3. **Do not merge the pull request.** A person reviews the preview and merges.
4. In the pull request description, include the completed checklist from the
   task file, marking each item pass or fail, and say plainly which checks you
   could not run (for example, if no browser was available to test screen sizes).
5. **If anything is unclear or seems to conflict, stop and ask** in the pull
   request description rather than guessing. A correct question is better than
   a confident wrong answer.
