# TODO — Visual assets

Outstanding work to replace placeholders on the marketing site. Everything else
(forms, GA4, newsletter, install CTAs, legal, deploy workflow) is already wired.

Layout container is `max-w-7xl` (~1216px content width); source sizes below are
sized for retina (2×). Tip: the demo store at **carmenspartdepot.com** runs SPT —
capture the storefront/admin screenshots there instead of mocking them.

---

## 1. Customer / brand logos  (~8 unique, reused in both strips)
- Box: **96 × 32 px** (3:1; logo sits within, max-height 32px)
- Format: **SVG preferred**, or transparent **PNG @3× (288 × 96 px)**
- Rendered at `opacity-50` → monochrome / single-color reads best
- Locations: `src/pages/index.astro:114`, `src/pages/customers/index.astro:29`

Logos extracted from each customer's site header, normalized to 288×96 (96×32 @3×)
transparent PNGs in `public/logos/`, rendered monochrome via CSS (grayscale, inverted
in dark mode) with full brand color on hover. Wired through `src/components/LogoWall.astro`
as a full-width revolving carousel — 6 logos at a time (3 on tablet, 2 on mobile) with
‹ / › buttons that rotate through all logos seamlessly.

- [x] Schultz Mfg — schultzmfgco.com
- [x] All World Auto — allworldauto.com
- [x] BSD Automotive — bsdsale.com
- [x] Filterheads — filterheads.com
- [x] FCW Auto Parts — fcwautoparts.com
- [x] Metrix Premium Parts — metrixpremiumparts.com
- [x] MOCA Auto Parts — shop.mocaautoparts.com
- [x] NRS Brakes — nrsbrakes.com
- [x] InMotion Parts — inmotionparts.com
- [x] Aires para Autos — airesparaautos.com
- [x] CatalyticConverter.net — catalyticconverter.net
- [x] Wire the logos into the trust strips (replace the gray placeholder `<li>`s) — `LogoWall.astro` in both strips, each logo links to its site (new tab)
- [ ] autopartes646.com — skipped (no wordmark logo; header uses a generic parts stock photo)

## 2. Homepage screenshots — "See it in production"
- Aspect **4:3** → source **1200 × 900 px PNG**
- Location: `src/pages/index.astro:310`

- [x] YMM search on a category page → `public/screenshots/ymm_category_search.png`
- [x] Fitment table on a product detail page → `public/screenshots/buyers_guide.png`
- [x] Fitment confirmed in the cart → `public/screenshots/cart_fitment.png`
- [x] Wire the 3 images into the section (replace gradient placeholders)

## 3. Feature-page hero screenshots
- Aspect **5:4** → source **1200 × 960 px PNG**
- Rendered by `src/layouts/FeaturePageLayout.astro` (the `lg:col-span-5` figure)

- [ ] **ymm-search** — YMM widget: empty, mid-selection, and with results
- [ ] **catalog-sync** — Admin sync run with counts: created / updated / skipped / errored
- [ ] **pdp-enrichment** — PDP with fitment banner, attribute table, Buyer's Guide, specs tabs
- [ ] **in-cart-fitment** — Cart with fitment block + Shopify admin order detail (fitment highlighted)
- [ ] **price-inventory-sync** — P&I run log: timestamps, file source, updated SKU count
- [ ] **order-export** — Admin destinations list + a sample exported file
- [ ] Update `FeaturePageLayout.astro` to render a real image (currently a placeholder div)

## 4. Open Graph / social images  (optional)
- Default `public/og-default.png` (1200 × 630) already exists and is used site-wide.
- [ ] Optional: per-page OG overrides via `ogImage` — **1200 × 630 px PNG/JPG**

## 5. Blog hero images  (optional)
- `heroImage` is in the schema but no post sets it and the blog template doesn't render it.
- [ ] Optional: add hero rendering to the blog template + images — **1200 × 675 px (16:9)**

---

## Done — no action (reference)
- [x] favicon.svg + favicon.ico (32 × 32)
- [x] og-default.png (1200 × 630, site-wide default)
- [x] Logo wordmark — inline text/CSS mark, no image file needed

## Specs quick-reference
| Asset | Pieces | Source size | Aspect | Format |
|---|---|---|---|---|
| Customer logos | ~8 | ≤288×96 (box 96×32) | 3:1 | SVG / transparent PNG |
| Homepage screenshots | 3 | 1200×900 | 4:3 | PNG |
| Feature hero screenshots | 6 | 1200×960 | 5:4 | PNG |
| Per-page OG (optional) | per page | 1200×630 | 1.91:1 | PNG/JPG |
| Blog heroes (optional) | per post | 1200×675 | 16:9 | PNG/JPG |

**Minimum to clear every visible placeholder: 8 logos + 9 screenshots.**
