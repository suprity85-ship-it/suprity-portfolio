# Suprity Pramanik — Portfolio Website

Personal portfolio of **Suprity Pramanik**, Product Designer at Rupeezy, Bengaluru.
A single-file, one-page website showcasing UI/UX case studies in fintech, work experience and contact details.

---

## Contents

| File | What it is |
| --- | --- |
| `suprity-pramanik-portfolio.html` | The entire website: HTML, CSS and JavaScript in one file |
| `README.md` | This guide |

No build step, framework or package install is needed. Open the HTML file in any modern browser.

---

## Page structure

| Section | Anchor | What's in it |
| --- | --- | --- |
| First fold | `#top` | Name, one-line intro, tinted portrait, numbered nav, side rails |
| Work | `#work` | Intro paragraph and 6 project cards |
| Experience | `#experience` | Rupeezy (2 roles), Digi Mangoes, Arena Animation, PD Women's College |
| Contact | `#contact` | "Say hello" message, email and both phone numbers |
| Case studies | `#case-…` | A full page for each project, opened from the work cards |

### Case study pages

Each project opens its own page inside the same file. Every page has a direct link you can share:

| Project | Link |
| --- | --- |
| FinAI Tool + Rupeezy MCP Server | `#case-finai` |
| Goal Based Investment Calculator | `#case-goal` |
| Mutual Fund Distributor Page | `#case-mfd` |
| App Home Screen Redesign | `#case-app` |
| Rupeezy Web Promo Landing Page | `#case-web` |
| App Store Creatives | `#case-aso` |

Example: `https://your-domain.com/#case-finai` opens the FinAI case study directly.

---

## Features

- **Page-load intro:** a mint panel slides away, then the header, hero text and side rails fade up in sequence.
- **Scroll reveals:** section labels, headings and text rise into view as you scroll.
- **Work cards:** each image is uncovered by a navy panel wiping to the right, then the tag, title, description and links fade up one by one.
- **Experience accordion:**
  - Desktop: a row opens on hover and closes when the cursor leaves.
  - Phones: tap a row to open or close it.
  - Keyboard: press Enter or Space on a focused row.
- **In-site case studies:**
  - Opening a project shows its page instantly at the top, with no scroll animation.
  - "Back to work" and the browser back button return you to the project you clicked.
  - A "Next project" link at the bottom cycles through all six.
- **Live page links** for FinAI, the goal calculator and the MFD page.
- **Responsive:**
  - Desktop: the portrait sits on the right of the first fold.
  - Mobile: the fold is shorter, the portrait sits at the bottom and is never cropped, and the name and intro overlap it.
- **Accessibility:**
  - Visible keyboard focus.
  - Reduced-motion users get all content without animations.
  - Without JavaScript, content stays visible.

---

## Design tokens

Defined at the top of the `<style>` block in `:root`:

| Token | Value | Used for |
| --- | --- | --- |
| `--navy` | `#0a192f` | Page background |
| `--navy-light` | `#112240` | Cards, description boxes |
| `--white` | `#e6f1ff` | Headings |
| `--slate` | `#8892b0` | Body text |
| `--mint` | `#64ffd9` | Accent, links, labels |
| `--duo` | `#5b64b5` | First-fold background and photo tint |
| `--sans` | Poppins | Headings and body |
| `--mono` | Roboto Mono | Nav numbers, tags, metadata |

Fonts load from Google Fonts. Everything else is inline.

---

## Editing content

All content is plain HTML in `suprity-pramanik-portfolio.html`. Search for these markers:

| To change | Look for |
| --- | --- |
| Name or intro in the first fold | `<div class="hero-content">` |
| Work intro paragraph | `<p class="lede reveal">` inside `id="work"` |
| A project card | `<article class="project">` (6 of them, in display order) |
| A case study page | `<article class="case" id="case-…">` |
| Experience rows | `<div class="job reveal"` |
| Email and phone numbers | `class="c-meta"` (contact), `rail-l` (left rail), `rail-r` (right rail) |

### Adding a project

1. Copy an existing `<article class="project">` block in the work section.
   - Give its image a new id, such as `id="img-newproject"`.
   - Point its links to `#case-newproject`.
   - Add `flip` to the class (`project flip`) to alternate the image side.
2. Copy an existing `<article class="case">` block inside `<div id="cases">`.
   - Set `id="case-newproject"`.
   - Set `data-src-from="img-newproject"` on its hero image.
3. Add `'newproject'` to the `order` list in the script so "Next project" includes it.

### Replacing images

- **Portrait and Rupeezy Web screenshot:** these are embedded in the file as base64 (`data:image/jpeg;base64,…`), so they always load.
- **Other project screenshots:** these load from the Notion page, so they need an internet connection and the Notion page must stay public.

To make the site fully self-contained, save each project image into an `images/` folder next to the HTML file. Then change each `src="https://mountain-boron-7f4.notion.site/image/…"` to `src="images/your-file.jpg"`.

---

## Publishing

Any static host works because it's a single HTML file.

| Host | How |
| --- | --- |
| **Netlify Drop** | Rename the file to `index.html`, then drag the folder onto app.netlify.com/drop |
| **GitHub Pages** | Push `index.html` (and `images/` if used) to a repo, then enable Pages in repo Settings |
| **Vercel** | Import the repo or drag the folder into a new project |

Rename the file to `index.html` before uploading so it opens at your site's root URL.

---

## Notes

- **Case study content:** condensed from Suprity's Notion portfolio. The internal "Notes on Design vs. Spec" sections were left out.
- **Phone links:** "Send Email" and the phone links use `mailto:` and `tel:`, which open the visitor's mail or phone app.
- **Credits:** the layout and motion are modelled on a Webflow portfolio template, rebuilt from scratch with original code. All text, photos and project work are Suprity's own.

---

## Contact

- Email: suprity85@gmail.com
- Phone: +91 81168 02765 · +91 97757 03916
- LinkedIn: [suprity-pramanik](https://in.linkedin.com/in/suprity-pramanik-878842226)
