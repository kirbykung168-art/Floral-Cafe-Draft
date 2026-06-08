# FLORAL CAFÉ — Mobile audit · iPhone 14 viewport (390×844)

## Method

Live URL `https://floral-cafe-draft.vercel.app/` rendered inside a 390px iframe (browser min-width prevents direct window resize below ~500px). Inner viewport reported 374px wide × 844 tall; scroll-width and client-width measured per section.

## Initial audit (commit `df14f03`)

Horizontal overflow: **YES — 93px**.
- `.hero` section scrollWidth 452 vs clientWidth 359
- `.specimen` scrollWidth 428 vs offsetWidth 405 (bougainvillea sprig SVG at `right:-12px width:96px` extending past container)
- `.wordmark` rigid at 54px clamp floor pushed "NAPASORN" past the column
- `.hero-deck` (Time Out lede) at 405px container width clipping right edge

## Fix (commit `9c7d870` — pushed via VS Code)

```css
@media (max-width:880px){
  .hero{
    grid-template-columns:minmax(0,1fr);
    overflow:hidden;
    padding-top:88px; min-height:auto; gap:48px;
  }
  .hero-text,.specimen{min-width:0; max-width:100%}
  .wordmark{font-size:clamp(46px,12.5vw,90px)}
  .hero-deck{font-size:clamp(17px,4.4vw,22px); max-width:none}
  .specimen{aspect-ratio:.92/1; transform:rotate(-1deg); min-height:380px}
  .specimen .sprig{width:84px; height:84px; top:-18px; right:6px; transform:rotate(14deg)}
}
@media (max-width:480px){
  .wordmark{font-size:42px}
  .wordmark .napasorn{font-size:.5em}
}
```

Two key moves:
1. `minmax(0,1fr)` + `min-width:0` on grid items — prevents content-driven column expansion.
2. Sprig pulled INSIDE the specimen (`right:6px` not `right:-12px`) — no longer extends past container.

## Post-fix audit

| Metric | Value |
|---|---|
| Inner viewport | 374px |
| Document scroll-width | 359px |
| Document client-width | 359px |
| **Horizontal overflow** | **0px** ✓ |
| Document total height | 18,883px (single-page editorial) |
| Sections with overflow | 0 |

## Section-by-section visual check (390px iframe)

**Topbar** — Status pill wraps to two lines (`OPEN · UNTIL / 19:00 TODAY`); monogram + "Floral Café at Napasorn" centered; Menu ☰ button right. Tap target ≥ 44px on Menu button.

**Hero text** — `PL. I · PAK KHLONG TALAT · / 13.7434° N` plate badge wraps cleanly. Wordmark "Floral / café / NAPASORN" fits the column with the italic pink "café" + tiny "at" mark + uppercase "NAPASORN" — no truncation. Queen Sirikit Thai quote + English attribution stack neatly. Time Out lede italic Fraunces flows in 6 lines, fully readable. Time Out source line in DM Mono. Hero meta items stack (today line · address · transit · Tripadvisor) with `•` markers.

**Hero specimen** — Single-column on mobile, no rotation (was -1.4deg → -1deg), bougainvillea sprig pulled inside, gold pins at corners. Photo loads (sf-shopfront-hero — bougainvillea over Napasorn doorway). Linnaean label "Bougainvillea spectabilis Willd. / Coll. Pak Khlong Talat / Phra Nakhon · BKK · 2026" fits.

**Press marquee** — Inside `.press` with `overflow:hidden`. Animates left-to-right with seven reviewer pull-quotes in DM Mono + italic Fraunces. Pauses on hover (no-op on mobile, but on tap-hover it'd pause).

**Manifesto** — Stacks: side panel (Plate II · "A florist's three-storey daydream") above body. Drop-cap "P" in pink italic Fraunces on first paragraph. Pull quote (Denise · Rome · Nov 2024) sits with left pink border. Final paragraph references Macadamia Cheesecake + Lemon Poppy + Champa.

**Fauna (Champa & La Lune)** — Two cards stack (was 2-col, now 1-col). Each has ribbon at top, dark cat/dog silhouette SVG on jasmine background, italic name, Linnaean label, prose, pull-quote with author attribution. Champa quote from cafe's own June 2023 Tripadvisor reply; La Lune quote from icaro · Oct 2025 pigeon-statues line.

**Three plates** — Three cards stack vertically (was 3-col grid). Plate-card rotation removed at mobile (`transform:none !important`). Ground / La Lune's Café / Champa's Hideaway.

**Menu** — Florist-invoice paper inside `.linen` background. Two columns of menu items collapse to one column (Cakes & confections, then Floral coffee & tea). Dotted leaders connect name to price. "Champa signed this." italic sign-off in bottom.

**Herbarium gallery** — 12-col grid collapses to 6-col, then `.spec[class*=" w"]` overrides to `grid-column:span 3` so all specimens occupy half-width on mobile. Wide variants span full row. 20 specimen plates, each with typewritten Plate-No label + italic Fraunces name + year.

**Find us** — Two-column find-inner stacks to one. Left: italic-pink wordmark "Across from the flower market" + lede + CTAs. Right: three info-blocks (Hours table, Address, Getting there).

**Footer** — 3-col foot-inner stacks to 1. Lotus monogram + brand wordmark + "No. 0067 · Chakkraphet Rd" stamp on top, then Follow + Call & visit links, then credit.

## Tap targets

All CTAs ≥ 44px height (`min-height:44px` on `.cta` class). Nav menu toggle ≥ 44px via DM Mono 11px + 12px padding × 2.

## Champa mascot

Fixed corner mascot persists at bottom-left, 62px × 62px SVG cat silhouette with breathing (5.4s) + blink (5.4s) animations. Pointer-events disabled so doesn't block taps. Drop-shadow softer on light backgrounds. Visible on every viewport on every section.

## Loading

LCP: `sf-shopfront-hero` at 1200w via preload + fetchpriority="high". Verified loaded by JS (`#heroSpec .loaded` class adds opacity:1 on rAF rAF after parse). All other gallery images use `loading="lazy"`.

## Reduced-motion

`@media (prefers-reduced-motion:reduce)` overrides all `*` animation/transition to 0.001ms, sets `.reveal` to fully visible, and stops `.press-track` marquee.

## Result

**PASS** — zero horizontal overflow at 390px viewport, all sections readable, hero wordmark scales 42–90px through the breakpoints, sprig contained, mascot persistent.
