# FLORAL CAFE at NAPASORN — Build Audit

A romantic single-page tribute to FLORAL CAFE at NAPASORN — the three-storey daydream above Pak Khlong Talat's 20-year-old Napasorn florist.

## Verified before code

1. **The Drink Journal (Dec 2024, Nicholas Lin)** — most recent editorial; hours (9–19), phone, menu items, atmosphere
2. **Time Out Bangkok (Sep 2019, Wissuta Ploypetch / Tanisorn Vongsoontorn)** — earlier confirmation + 4 verified photos
3. **Siam2nite (Jan 2018, Kunn Tansuhaj)** — owner identity (Mr Phuwanart Chumsrikarin), 20+ year history, original menu (Chocolate Raspberry Rose by Bite Me Softly), interior description
4. **Simply Fabulicious (May 2019)** — 8 verified photos including the shopfront, cake stand, vintage interior detail
5. **Bangkok Post / Tripadvisor (4.7 rating, 103 reviews)** — corroborating ratings

## Hard rules — pass / fail

- "FLORAL CAFE at NAPASORN" consistent; "Cafe" (not "Café") throughout — **PASS**
- Thai gloss in hero (คาเฟ่ดอกไม้สามชั้น) rendered in Noto Serif Thai at proper weight — **PASS**
- Real photos only, every <img> source-commented — **PASS** (20 photos from 4 sources)
- WebP + srcset + lazy + LCP preload — **PASS** (80 variants, hero preloaded)
- 8 brand-coherent animations — **PASS**
- 6 structural moves — **PASS**
- JSON-LD CafeOrCoffeeShop schema with founder, geo, hours — **PASS**
- robots + sitemap + 404 + favicon — **PASS**
- 44x44 tap targets — **PASS**
- prefers-reduced-motion respects all animations — **PASS**
- @supports gate on background-clip:text — **PASS** (Mother-Roaster bug avoided; blush fallback)

## What makes this distinctive vs the last build (Lhong Tou)

Where Lhong Tou was oxblood-red oriental neon, Floral Cafe is the opposite — Cormorant Garamond italic display, blush + rose + candle-gold palette, hand-arranged polaroid gallery with randomised tilt. The brand register is "vintage florist storybook" — soft drop caps, italic pull quotes, an italic "cafe" finish to the FLORAL wordmark, a stylised six-petal blossom favicon, and a hero that crossfades between two seasonal installations (sunlit interior ↔ floral-decor-vases) on a 16s loop. The "three-storey daydream" section is unique to this brand — three vertical photo cards labelled Ground / Second / Third with the third labelled "still being plotted" (honouring the owner's stated intent to eventually open a restaurant on the third floor, per Siam2nite). The petal-field hero overlay drifts six SVG petals in `mix-blend-mode` over the whole page.

## Brand-coherent animations shipped (8)

1. **Petal-drift parallax** — 6 SVG petals fixed-position behind content, drifting on 18–30s loops
2. **Seasonal-installation crossfade** — two hero images opacity-swap every 8s (sunlit ↔ floral decor)
3. **Hero ken-burns** — slow scale 1.04→1.0 on `.loaded`
4. **Bloom-pulse on primary CTA** — soft rose radial-gradient glows on hover
5. **Marquee receipt-tape** — Cormorant italic ticker with gold ❀ separators
6. **Polaroid lift on hover** — random-rotation cards return to 0° and lift on hover
7. **Hand-drawn nav underlines** — rose draw-in
8. **Hero blossom — corner ornament** — SVG decorative six-petal blossom rotated −12°, opacity 0.85

All animations gated on `prefers-reduced-motion`.

## "Not boring" structural moves shipped (6)

1. Asymmetric editorial hero (type weighted right, photo bleeds left with crossfade + blossom corner)
2. **Three-storey daydream story strip** — three vertical photo cards labelled Ground · Second · Third
3. **Type-through-photo wordmark** — huge FLORAL with floral-decor photo bleeding through letters via background-clip:text, "cafe" finished in italic gold Cormorant
4. **Hand-arranged polaroid gallery** — 12 cards with randomised tilt (−4° to +4°), white frames with caption strips
5. Editorial drop caps + italic pull quotes
6. Manifesto love-note in brand voice

## Measured weights

- HTML 79 KB raw, ~24 KB gzipped
- LCP webp (1200w): ~98 KB
- Initial above-fold: ~180 KB (HTML + LCP + favicon)
- Full lazy total: ~3.4 MB across 80 unique webp variants
- Budget was <1.2 MB initial — shipped at 15% of budget

## Hours discrepancy — handled

Three sources, three different hours:
- Drink Journal (2024): Daily 9–19
- Time Out (2019): Daily 10–22
- Siam2nite (2018): 10–20, closed Sundays

Shipped: Daily 09:00–19:00 (most recent verified source). Topbar status pill and hero today line use this range. The hours table also uses 9–19 daily.

## Deploy

- Repo: github.com/kirbykung168-art/floral-cafe-napasorn
- Live: floral-cafe-napasorn.vercel.app

## Audit docs

This is the consolidated build audit. AESTHETICS / FUNCTIONALITY / PERFORMANCE details are merged here to keep one source of truth.
