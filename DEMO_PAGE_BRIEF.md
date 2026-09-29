# DEMO_PAGE_BRIEF.md — Build the sample QR demo page

Read `CLAUDE.md` first. All of its rules apply to this task.

## Deliverable

- One file: **`index.html`** at the repository root.
- Inline `<style>` in the `<head>`. No separate CSS file, no JavaScript, no
  images other than inline SVG icons.
- Delivered on a new branch as a pull request into `main` (not merged).
  Suggested branch name: `demo-page`. Suggested PR title: `Add sample QR demo page`.

## Page `<head>`

- `<title>`: `Sample Memorial Link`
- `<meta name="description" content="A sample memorial QR code page.">`
- `<meta name="robots" content="noindex">`
- `<meta name="viewport" content="width=device-width, initial-scale=1">`
- `<meta name="theme-color" content="#F7F3EC">`
- Google Fonts link for Playfair Display 700 and EB Garamond 400 + 400 italic,
  with `preconnect` to `fonts.googleapis.com` and `fonts.gstatic.com`.

## Approved text — copy EXACTLY, in this order

Every visible word on the page is listed below. Nothing else may appear.

1. **Small label** (above the headline):
   `Sample`

2. **Headline** (`<h1>`):
   `A Memorial Link, Shared with Love`

3. **Intro paragraph:**
   `This is a sample. On a real memorial program, this code opens the page the family chooses, so friends near and far can give, send support, or join the service from wherever they are.`

4. **Three example cards.** Each card shows the word `Example`, a title, and one
   line of text:

   | # | Title | Text |
   |---|---|---|
   | 1 | `Memorial Fund` | `Contribute to a fund chosen by the family.` |
   | 2 | `Favorite Charity` | `Give to a cause that mattered to them, in their honor.` |
   | 3 | `Service Livestream` | `Watch the service live, from anywhere.` |

5. **Closing line:**
   `Ask your funeral director about adding a memorial code to your loved one's program.`

6. **Footer** (small):
   `Memorial links by CAS Flow Systems`

Use a real apostrophe (’) or a straight one (') consistently in "loved one's";
either is acceptable, but do not change any other character.

## Layout and styling

Use the brand tokens and fonts from `CLAUDE.md`.

**Overall**
- Background `--paper`, full height. Single centered column, max width about
  600px, side padding about 24px on phones.
- Vertical rhythm: generous white space between sections (roughly 32–48px on
  phones, a little more on desktop). The page should feel calm, never crowded.

**Label ("Sample")**
- Centered, small (about 13–14px), EB Garamond, uppercase with letter-spacing
  about 0.18em, color `--body`. A thin `--line` border pill around it (about 4px
  × 14px padding, fully rounded) is a nice touch but optional.

**Headline**
- Centered, Playfair Display 700, color `--ink`, about 30–34px on phones and
  40–44px on desktop (use `clamp()`). Line height about 1.2.
- Directly below: the **gold rule** — 64px wide, 1.5px thick, `--gold`,
  centered, about 18px gap above and below.

**Intro paragraph**
- Centered, EB Garamond 400, about 19–20px on phones, color `--body`,
  line height about 1.55.

**Example cards**
- Stacked vertically on phones (one per row, full column width). On screens
  wider than about 720px they may sit in a row of three **only if** each card
  stays comfortably readable; stacked is also fine at all sizes.
- Card: background `--card`, 1px `--line` border, radius about 10px, padding
  about 20–24px, very soft shadow at most (for example
  `0 1px 2px rgba(58,51,45,0.06)`). No hover effects that suggest the card can be
  clicked, no pointer cursor, and not wrapped in `<a>` or `<button>`.
- Inside each card, top to bottom:
  - Icon: inline SVG, about 28–32px, stroke `--gold`, stroke width about 1.5,
    no fill, round line caps and joins, `aria-hidden="true"`.
  - `Example`: small uppercase EB Garamond, about 12–13px, letter-spacing about
    0.16em, color `--body`.
  - Title: Playfair Display 700, about 20–22px, color `--ink`.
  - Text: EB Garamond 400, about 18px, color `--body`.
- Card text may be left-aligned or centered; pick one and use it for all three.

**Icons** (simple outline style, hand-written SVG or copied inline from an
openly licensed outline set such as Lucide, ISC license — never loaded from a CDN):
1. Memorial Fund — an outlined **heart**.
2. Favorite Charity — an outlined **open hand holding a small heart**, or a
   simple **ribbon**; choose whichever reads more clearly at 28–32px.
3. Service Livestream — an outlined **screen or monitor with a small play
   triangle** inside.

**Closing line**
- Centered, EB Garamond **italic**, about 19px, color `--body`.

**Footer**
- Centered, small (about 13–14px), EB Garamond, color `--body`, with a thin
  `--line` hairline above it and comfortable space below. Plain text, not a link.

**Motion (optional)**
- At most one subtle fade-in of the whole content on load (under 600ms), and it
  must be disabled under `@media (prefers-reduced-motion: reduce)`.

## Acceptance checklist — include in the PR description, marked pass/fail

Text
- [ ] Every visible word matches the "Approved text" section exactly, in order.
- [ ] No other visible text exists (no extra buttons, links, headings, or notes).
- [ ] No prices anywhere.

Behavior and rules
- [ ] Example cards are not links or buttons and are not clickable.
- [ ] No tracking, cookies, analytics, or third-party scripts.
- [ ] The only external requests are to `fonts.googleapis.com` and `fonts.gstatic.com`.
- [ ] No external images; icons are inline SVG with `aria-hidden="true"`.
- [ ] `<meta name="robots" content="noindex">` is present.
- [ ] No `netlify.toml`, build step, or package files were added; `README.md` is unchanged.

Design
- [ ] Colors and fonts match the brand tokens in `CLAUDE.md` exactly.
- [ ] Gold is used only for the headline rule and icon strokes, never for text.
- [ ] Gold rule sits centered under the headline.

Screens and accessibility
- [ ] No horizontal scrolling at 360px, 390px, 768px, and 1280px widths.
- [ ] Body text is at least 18px on a 390px-wide screen.
- [ ] Body text contrast meets WCAG AA (4.5:1).
- [ ] One `<h1>`; `<html lang="en">` is set.
- [ ] Reduced-motion users see no animation (if any animation was added).
- [ ] State clearly which of these checks could not be run in this environment.
