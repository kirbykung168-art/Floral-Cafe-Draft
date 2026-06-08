# FLORAL CAFÉ — June 2026 Herbarium redo · CHANGES

Full rewrite of `index.html` against `BRAND_RESEARCH.md` and `AESTHETIC_COMPARE.md`.

## The signature moment

**The whole site is a digital herbarium / pressed-specimen scrapbook.**
Every photo is mounted on a cream "specimen plate" with a typewritten Linnaean-style label (Plate No., Latin name, Coll. location, year). The hero is a layered pinned bouquet — bougainvillea sprig SVG overlaid on the shopfront photo — that tilts to cursor parallax. Pin SVGs sit at each corner of every plate. The menu is set as a vintage florist invoice with dotted leaders and a "Champa signed this" stamp.

This is brand-true (a florist's specimen book) and does not borrow from any other site in the queue.

## Typography — fully replaced

| Role | Before | After |
|------|--------|-------|
| Display | Cormorant Garamond italic 300 | Fraunces variable (opsz 144, SOFT 60–100, wght 320–420) |
| Body | EB Garamond | Lora variable |
| Mono / labels | system mono | DM Mono (0.3 weight for specimen labels) |
| Thai | Noto Serif Thai | IBM Plex Sans Thai |

Rationale: Lhong Tou shipped Cormorant Upright as its display — using the Garamond cousin here would feel like a sister site. Fraunces (with its SOFT axis dialed to 60–100) gives a contemporary editorial wedge-serif vibe that is wholly unrelated. Lora is a warmer humanist body, far from EB Garamond's classical Roman. DM Mono replaces the system stack and carries the herbarium-label register everywhere. IBM Plex Sans Thai is modern Thai sans — not Noto Serif Thai (previous), not Bai Jamjuree (reserved for Thongyoy).

## Palette — re-sampled from real IG photos (June 2026)

| Token | Before | After | Source |
|------|--------|-------|--------|
| --ink | #2b1d22 aubergine | **#1a1f2e** royal blue-black | Queen Sirikit portrait grid |
| --bougainvillea (new) | — | **#c7396d** hot fuchsia | Shopfront awning |
| --ochre (new primary) | gold #c89856 (accent) | **#c39a4a** dried wheat | Brass candelabra + dried-wheat overhang |
| --jasmine | cream #f8efe6 | #f4ecd8 (slightly warmer) | jasmine wreath highlight |
| --moss | sage #7a8b6e | #5b6b3c climbing-vine | leaf vines in atrium |

Dropped: rose #c14b6a, blush #e7c0c3, blush-light #f3d7d9 — these never appeared in the brand's actual photographs.

## Champa & La Lune — the cats are the brand center

Previously: zero mention. Now:
- Fixed corner **Champa silhouette** SVG that breathes (5.4s) and blinks slowly — visible on every screen, lower-left
- Dedicated **Plate III · Champa & La Lune** section with two custom silhouette SVGs and verbatim quotes:
  - Champa's "owner profile" uses the cafe's own Tripadvisor reply (June 2023): *"Champa, our adorable feline owner, loves meeting new people and adding that extra touch of charm to our cafe."*
  - La Lune's profile pulls Tripadvisor reviewer icaro's "pigeon statues" line as a contextual aside
- The **2nd floor in the Three Plates** section is labeled "La Lune's Café"; the 3rd is "Champa's Hideaway"
- Mobile nav line: "**Champa** & La Lune" treated as a primary nav anchor

## Content — verbatim brand voice

Replaced all generic florist-storybook prose. Now using:
- **Hero deck**: Time Out Bangkok's actual review lede (Wissuta Ploypetch, Sep 2019) verbatim
- **Hero Thai**: The Queen Sirikit jasmine quote *"ขาดทุนของฉัน คือกำไรของแผ่นดิน"* — a recurring photographic motif in their feed
- **Press marquee**: seven real reviewer pull-quotes, attributed (Tripadvisor 2019 — 2025, Time Out 2019)
- **Manifesto pull**: Denise · Rome · Tripadvisor · Nov 2024
- **Champa quote**: cafe's own Tripadvisor management reply, June 2023
- **Menu**: real items with reviewer endorsements ("★ Kate L" on Lemon Poppy Seed; "IG Highlight" on Sunrich Orange — visible in current IG Story Highlight)

## Animations — fully replaced (8 brand-coherent)

| # | Was | Now |
|---|-----|-----|
| 1 | Petal-drift parallax (6 rose petals) | **Cursor parallax on hero specimen plate** (tilt + sprig drift) |
| 2 | Seasonal-installation crossfade | **Specimen pin** dimensionality (radial-gradient brass heads, drop-shadow) |
| 3 | Hero ken-burns | **Specimen photo soft scale-in** on load (1.04 → 1.00) |
| 4 | Bloom-pulse CTA | **CTA arrow translate** on hover — quieter, less florist-y |
| 5 | Marquee receipt-tape (italic Cormorant) | **DM Mono press marquee** with `✦` separators and real attribution |
| 6 | Polaroid lift on hover (random rotation) | **Specimen plate rotate-to-zero + lift** (deterministic, no random jitter) |
| 7 | Hand-drawn nav underlines | **Right-to-left underline draw** under nav anchors |
| 8 | Hero blossom corner ornament | **Champa-silhouette breathe + blink** as the always-present brand mascot |

All gated on `prefers-reduced-motion`.

## Structural — fully replaced (6 + 1)

1. **Hero specimen plate** with cursor parallax, pins, sprig overlay, Linnaean label
2. **Press marquee** with real reviewer attribution (Tripadvisor + Time Out)
3. **Manifesto** rebuilt with real history (Phuwanart, 20+ years, 2018 opening, third floor 2019) + Bite Me Softly bakery delivery — pulled from Siam2nite (2018) + Drink Journal (2024)
4. **Plate III · Champa & La Lune** owner profiles (new section)
5. **Three plates** (Ground / La Lune's / Champa's Hideaway) — renamed from the previous "Ground / Second / Third" labels
6. **Menu as florist invoice** with dotted leaders, "Champa signed this" stamp, "No. 0067" invoice number
7. **Herbarium gallery** with 20 specimen plates (12 brick layout was previous count; now 20 in 12-column grid with mixed widths)

## What stayed

- The 80 already-optimized WebP variants in `/images/optimized/` (all 20 photos × 4 sizes)
- Hours (Daily 09:00 — 19:00 — verified again on IG bio + Tripadvisor 2026)
- Phone +66 99 468 4899
- Address + MRT routing
- JSON-LD schema (updated for new copy)
- Robots, sitemap-equivalent meta, 404, favicon
- Single-page editorial structure

## Mobile

Designed mobile-first inside the desktop CSS — every section collapses to a single column at 880px. Hero specimen rotates straight on mobile. Plates lose their −.6° / +.5° rotation. Three-column herbarium grid collapses to 2-column. Tap targets ≥ 44px.

Mobile audit recorded in `MOBILE_AUDIT_floral.md` after live deploy.

## Diff summary

- `index.html` — full rewrite (1674 lines → ~880 lines, tighter)
- `BRAND_RESEARCH.md` — new
- `AESTHETIC_COMPARE.md` — new
- `CHANGES.md` — this file
- `MOBILE_AUDIT_floral.md` — written after live audit
- `images/` — unchanged
- `vercel.json`, `404.html`, `robots.txt`, `favicon.svg` — unchanged
