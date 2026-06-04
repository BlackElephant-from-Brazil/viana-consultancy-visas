# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a complete rebuild of the Viana Consultancy website (visas.vianaconsultancy.com) — a Portuguese immigration law firm run by attorney Patrícia Viana. The site is a single-page landing page targeting remote workers, retirees, and professionals who want to relocate to Portugal via D7 or D8 visas.

The original site was built in WordPress + Elementor; this rebuild is a standalone HTML/CSS/JS static site with the same visual identity.

## Stack

- **Single-page static site**: `index.html` + `style.css` + `script.js`
- No framework, no build tool — plain HTML, CSS, JS
- To preview: open `index.html` in a browser or run `npx serve .`

## Visual Identity

- **Primary color (gold/amber):** `#C9A227` or `#D4A017`
- **Dark navy accent:** `#1B2A4A`
- **Background light:** `#F5F5F5` (sections alternating with white)
- **Text dark:** `#1a1a1a`
- **Font:** Figtree (Google Fonts) + URW Classico (custom, used for display headings)
- **Heading style:** two-tone — first part in gold/amber, second part in dark navy/black
- **Section dividers:** short gold horizontal bar under section titles
- **CTA buttons:** pill-shaped, gold background (`#C9A227`), dark text, with arrow icon

## Page Sections (in order)

1. **Header/Nav** — sticky, logo left, nav links right (Home, Reviews, Why us, Team, Process, Services), burger menu on mobile
2. **Hero** — full-bleed dark background with Patrícia photo, lead form on right (First Name, Last Name, Email, Phone with intl-tel-input), CTA button "Book A Relocation Strategy Session"
3. **Stats bar** — white bg, 3 counters: 200+ Litigations, 500+ Extrajudicial cases, 800+ Happy Clients (with SVG icons)
4. **About** — "We're Not a Visa Agency / We're Immigration Lawyers" — image left (couple photo), text right
5. **Reviews** — "What Our Clients Say" — Google review cards slider (10 real reviews embedded)
6. **Why Us** — 2×2 grid of feature cards with icon + title + divider + description
7. **Team** — "Meet Your Legal Experts" — Patricia Viana (text left, photo right with dark blue corner accent), Bruna Xavier (photo left, text right)
8. **Process** — "How It Works: 3 Stage Process" — 3 cards in a row
9. **Book Now** — Calendly embed (`https://calendly.com/enquiries-vianaconsultancy/relocation-strategy-session`)
10. **Download CTA** — "Need Clarity Before Booking?" — lead-gen form (First, Last, Email + Download button) that opens Google Drive link on submit
11. **Services** — "What We Can Help You With" — 2-column grid of 7 service items with checkmark icons
12. **Final CTA** — dark background with Patrícia photo, "Ready to Make Portugal Your Home?", CTA button
13. **Footer** — logo, email, phone, social icons (Facebook, Twitter, YouTube) | Institutional nav | Services list | Copyright bar (gold bg)

## Key Integrations

- **Calendly:** inline widget embed, URL `https://calendly.com/enquiries-vianaconsultancy/relocation-strategy-session`
- **intl-tel-input v17:** phone field with country selector, default country `pt`
- **Google Reviews:** 10 real reviews hardcoded (no third-party widget needed in rebuild)
- **Google Drive PDF:** on download form submit, opens `https://drive.google.com/file/d/1urP5D4YJqOmlHTXyY3W4Be21gZ4fFjBW/view?usp=sharing`
- **GTM:** `GTM-5DHSWHDP` (include in `<head>`)
- **Contact:** `enquiries@vianaconsultancy.com` | `+351 960 174 940`

## Image Assets

Original images are hosted on the WordPress site. For the rebuild, reference them directly from the original URLs or download and place in `/assets/images/`:
- Logo: `https://visas.vianaconsultancy.com/wp-content/uploads/2025/04/Logo-8-1.png`
- Patrícia (hero/about): `Group-6.png`, `Group-7.png` (with dark corner accent)
- Bruna: `Group-8.png`
- Icons (Law, Courthouse, User-Account, Lawyer, Travel-Visa, Group-Task, Law-Book, Consultation-1, Document, Visa-Stamp, Check-Mark): all under `/wp-content/uploads/2025/04/`

## Anchor IDs

Nav links use these anchors (must match exactly):
- `#contactform` — hero form
- `#reviews`
- `#why-us`
- `#team`
- `#process`
- `#services`
- `#book-now`

## Responsive Behavior

- Mobile breakpoint: 767px
- Tablet breakpoint: 1024px
- Nav collapses to burger at tablet/mobile
- Two-column layouts stack to single column on mobile
- Hero form stacks below hero text on mobile
