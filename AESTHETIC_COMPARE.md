# FLORAL CAFÉ — AESTHETIC COMPARE (current live vs brand truth)

Read against `BRAND_RESEARCH.md`. Every drift in the current site listed below — all must be addressed in the redo.

## Drift #1 — Wordmark + typography is the wrong register
Current: Cormorant Garamond italic display, EB Garamond body, "FLORAL" + italic gold "cafe" — pure European storybook serif.
Truth: Brand wordmark is a delicate **sans-serif** condensed grotesque + a lotus-petal "n" monogram. Logo is white-on-black circular. Display has no italic flourish.
Action: Replace Cormorant Garamond with **Fraunces** (variable, opsz 144, SOFT 100). Body to **Lora**. Specimen labels to **DM Mono**. Thai to **IBM Plex Sans Thai**.

## Drift #2 — Champa + La Lune (the cats!) are completely absent
Current: Zero mention of the cafe's two animal residents, even though they are 2 of 5 Story Highlights and Champa is officially the "feline owner" who responds to Tripadvisor reviews.
Truth: Champa (cat) is essentially the cafe mascot; La Lune is the second animal.
Action: Add a dedicated **Champa & La Lune** section. Add a fixed corner **Champa silhouette mascot** that blinks slowly. Use the cafe's own quote *"Champa, our adorable feline owner…"* verbatim.

## Drift #3 — Palette skewed too rose/blush; missed bougainvillea + indigo + wheat
Current: rose `#c14b6a`, blush `#e7c0c3`, sage `#7a8b6e`, gold `#c89856`, cream `#f8efe6`.
Truth: Bougainvillea is the dominant outdoor pink (more magenta, more saturated: `#c7396d`). Hero royal portraits give a **deep indigo** (`#1a1f2e`) NOT aubergine. Dried-wheat ochre (`#c39a4a`) is a primary, not an accent.
Action: Replace `--ink` `#2b1d22` → `#1a1f2e`. Replace `--rose` `#c14b6a` → `--bougainvillea` `#c7396d`. Add `--ochre` `#c39a4a` as a primary. Drop blush/blush-light entirely.

## Drift #4 — Wrong flowers
Current: Rose petals everywhere (six SVG petal-drift layer; "polaroid" rose halos; "ink-bleed" rose CTA glow).
Truth: The flowers are bougainvillea (hot pink/magenta), white jasmine (wreath form), and dried wheat/pampas. There are no rose petals drifting in their photos.
Action: Strip the petal-drift entirely. Replace with **pinned-specimen** layout. Bougainvillea sprigs are static, mounted, photographed — not floating petals.

## Drift #5 — Polaroid gallery is Wallflowers' signature
Current: 12 hand-arranged polaroids with random −4° to +4° rotation.
Truth: This is Wallflowers' move (per Kirby's directive). Floral Cafe needs its own gallery framing.
Action: Replace polaroids with **specimen plates** — each photo on a cream paper card with a typewritten Linnaean-style label (e.g., "Pl. III · Champa, calico, ฿0 · Phra Nakhon 2026"). Card edges are paper-textured, no rotation jitter (sit straight on a botanical grid).

## Drift #6 — Three-storey strip labels miss the real floor narrative
Current: "Ground · The Florist", "Second · The Cafe", "Third · The Daydream"
Truth: Per IG Story Highlights — the floors are real, distinct spaces. 2nd floor is the LA LUNE space (pet-honoring), 3rd floor is named.
Action: Re-label as **"Plate I · The Florist"**, **"Plate II · La Lune's Café (2nd)"**, **"Plate III · Champa's Hideaway (3rd)"** — folded into the herbarium-plate framing.

## Drift #7 — The hero copy is generic florist-storybook prose
Current (paraphrased from previous build): "A storybook entrance above a 20-year flower shop — antique lamps glow against white-washed brick…"
Truth: Real reviewers use specific, vivid phrases — *"flower power coffee for the stressed to relax"*, *"a chic escape from the chaos of bangkok"*, *"homey and exotic at the same time"*, *"almost like walking into a magazine shoot"*.
Action: Replace hero deck with verbatim Time Out + reviewer pull-quotes. Add the **Queen Sirikit jasmine quote** *"ขาดทุนของฉัน คือกำไรของแผ่นดิน"* as a Thai gloss (with English translation in fine print) — this is a recurring photographic motif in their feed.

## Drift #8 — Animations don't match brand
Current: Petal-drift (rose), ink-bleed wordmark reveal, polaroid lift on hover, bloom-pulse CTA halo, hand-drawn vine grow.
Truth: Brand-coherent motions should be:
- Cursor-parallax on pinned specimens (mouse-tilt 2–5° per layer)
- Watercolor-wash SVG mask section transitions (like ink seeping into damp paper)
- Champa silhouette breathe + slow blink (fixed corner)
- Specimen labels drawn-in (handwritten path animation)
- Sparing bougainvillea petal drop on intersection (not constant)
- Section dividers as string-light strands (small bulb dots, glow on hover) — flower-shop awning detail
Action: Replace ALL eight animations.

## Drift #9 — Missing pigeon-statue interior detail
Tripadvisor reviewer mentioned "statues of pigeons" as a bonus.
Action: Add a small caption mention in the interior section ("listen for the pigeons — they're porcelain"). Detail.

## Drift #10 — Hours are right but topbar phrasing is rote
Action: Keep "Daily 09:00–19:00" but rephrase status pill to brand voice (e.g., "Open today · jasmine on the third floor").

## Drift #11 — Apostrophe-style typography needs the lotus monogram
Current: No use of the actual circular black "n" lotus monogram from the brand's IG profile.
Action: Add an SVG of the lotus-petal monogram next to the wordmark — and use the monogram favicon style (already correct).

## Drift #12 — Press marquee should pull from real Tripadvisor + Time Out
Current: "italic Cormorant ticker with gold ❀ separators"
Action: Replace with real reviewer pull-quotes (Time Out 2019, Tripadvisor 2023–2025) in DM Mono small caps, with • separators. Eight quotes minimum, attributed.

## What gets to stay
- The hours discrepancy resolution (9–19 daily) — verified again on IG bio and Tripadvisor 2026
- The phone number +66 99 468 4899 — verified Tripadvisor 2026
- The address + MRT routing
- The brand-coherent decision to single-page editorial
- The JSON-LD schema (will be edited for the new copy)
