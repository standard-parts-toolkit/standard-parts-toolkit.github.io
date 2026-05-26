# SPT — Draft Marketing Copy

> First-pass copy for every page described in `PROJECT_PROPOSAL.md`. Treat as a strong starting draft, not final. Items in `[BRACKETS]` are placeholders the owner must fill or confirm. All claims, stats, customer names, version numbers, and dates are placeholders unless explicitly confirmed.
>
> Voice: confident, technically credible, plain-English, manufacturer-aware, retailer-inclusive. No exclamation points. No hype words ("revolutionary," "best-in-class," "game-changer"). Specifics beat adjectives.

---

## Global / Reusable Microcopy

### Button labels
- Primary CTA: **Book a Demo** (Schedule a Demo Today — alternate phrasing inherited from current site)
- Secondary CTA: **Install on Shopify**
- Tertiary CTA: **View Demo Site** (links to `https://carmenspartdepot.com`)
- Tertiary / inline links: **See how it works** · **Knowledge Base** · **Talk to sales** · **See pricing**

### Top nav order
Features ▾ · Integrations · Merchant of Record · Pricing · Customers · Blog · Knowledge Base ↗ · About

### Form button states
- Idle: **Send message** / **Request a demo** / **Subscribe**
- Submitting: **Sending…**
- Success: **Thanks — we'll be in touch within one business day.**
- Error: **Something went wrong. Email us at [hello@standardpartstoolkit.com] and we'll sort it out.**

### Cookie consent banner
**Title:** Cookies
**Body:** We use Google Analytics to understand how the site is used. No marketing or advertising trackers. You can accept or decline — the site works either way.
**Buttons:** *Accept* · *Decline*

### Header announcement bar (optional, rotating)
1. New: ShowMeTheParts API support — see what's shipped → /changelog
2. Manufacturers: sync your ACES/PIES catalog to Shopify in days, not quarters → /features/catalog-sync
3. Now on the Shopify App Store → [App Store URL]

---

## Homepage (`/`)

### Hero
**Eyebrow:** Built for automotive parts on Shopify

**Headline:**
**Your fitment data, live on every Shopify storefront that sells your parts.**

**Subhead:**
**SPT** — the Standard Parts Toolkit — turns ACES/PIES, ShowMeTheParts, or CSV data into a fast, configurable Year-Make-Model search, an enriched product catalog, in-cart fitment that follows the shopper to checkout, and the price, inventory, and order plumbing your business already runs on. Built for parts manufacturers. Friendly to single-store retailers. Built to reduce "didn't fit" returns and increase buyer confidence.

**CTAs:** [Book a Demo]  [Install on Shopify]  [View Demo Site →]

**Hero visual:** Annotated screenshot of the YMM search widget with sample results below.

### Compatibility badge row
*A single thin band immediately under the hero:*
**Shopify Online Store 2.0 compatible · No custom dev work required · Powered by ShowMeTheParts (1,000+ supplier brands)**

### Trust strip
*Trusted by manufacturers and retailers selling automotive parts on Shopify.*
*Logo wall: 8 placeholder logos (grayscale silhouettes until real ones land).*

### Six-feature grid
> Section heading: **One toolkit, six jobs done right.**
> Subheading: Every module is configurable on its own, and every module reads from the same source of truth.

1. **YMM Fitment Search + VIN Lookup**
   Let shoppers narrow to parts that fit their vehicle. Year-Make-Model dropdowns, persistent garage, VIN lookup, and license-plate lookup (where supported).

2. **Catalog Parts Sync**
   Push your authoritative catalog into Shopify products, variants, and metafields. Includes Product Description, Product Specs, Buyer's Guide, and Item Attributes. Full or incremental. Scheduled or on demand.

3. **PDP Product Information**
   Render fitment, attributes, specs, notes, and Buyer's Guide content on every product page — themed to match your store.

4. **In-Cart Fitment & Fulfillment Handoff**
   The shopper's vehicle and fitment selection follow them through cart and checkout, and surface to your fulfillment team on the order — so you ship the right part the first time.

5. **Price & Inventory Sync**
   Pull P&I updates from FTP drops or email attachments on the schedule you already use.

6. **Order Export**
   Push orders to Email, FTP, or API destinations. Same format your warehouse, ERP, or 3PL already expects.

### Data-source row
**Bring the data you already have.**
ACES/PIES XML · ShowMeTheParts API · CSV upload. Swap sources later without rebuilding your storefront.

### Reduce-returns band
> Section heading: **Stop refunding parts that didn't fit.**
>
> Generic Shopify search doesn't know which serpentine belt fits a 2014 Silverado. SPT does — and it carries that knowledge from the search box, to the product page, to the cart, to the order your warehouse pulls. Real fitment verification at every step means fewer returns, fewer chargebacks, and shoppers who trust your store the second time.

### Manufacturer vs Retailer split
> Section heading: **Two audiences, one toolkit.**

**For parts manufacturers**
You already maintain a clean catalog in ACES/PIES. SPT gets it onto Shopify — yours or your dealers' — without a custom development project. Sync at the cadence you control, syndicate to multiple stores from one source, and export orders back to the systems you already run.
*CTA:* See it for manufacturers → /features/catalog-sync

**For automotive retailers**
You sell parts. Your customers need to find the one that fits their truck. Plug in a CSV, ShowMeTheParts, or your supplier's ACES/PIES feed, and your storefront ships with proper fitment search, fitment-aware product pages, and price/inventory sync in days.
*CTA:* See it for retailers → /features/ymm-search

### Screenshots row
Three captioned product screenshots (placeholders), plus a "View the live demo store" link to `https://carmenspartdepot.com`:
1. *YMM search on a category page.*
2. *Fitment table on a product detail page.*
3. *Order detail in Shopify admin showing the fulfillment-team fitment record.*

### By the numbers
**1,000+** part brands available · **24/7** updates · **0 hours** spent managing your own fitment data.

### Testimonial (real)
> "Vertical Development has been ingesting and publishing my content for years. Plugging their ShowMeTheParts API service directly into Shopify via Standard Parts Toolkit is a brilliant way to leverage the strengths of both worlds — like chocolate and peanut butter."
> — **Luke Smith, CEO, Momentum USA, Inc.**

### Merchant of Record callout
> **Selling across state lines? We can be your merchant of record.**
> Outsource sales tax collection, remittance, and reporting so you can focus on growing your parts business.
> *CTA:* Learn about MoR → /merchant-of-record

### Final CTA band
**See it on your data.**
We'll run a short demo against a sample of your ACES/PIES file, ShowMeTheParts feed, or CSV — so you can see real fitment results before you decide.
[Book a Demo]  [Install on Shopify]  [View Demo Site →]

---

## Features Overview (`/features/`)

### Hero
**Headline:** Everything a parts store on Shopify needs, in one toolkit.

**Subhead:** SPT covers the five jobs that turn a generic Shopify store into a real automotive parts store — fitment search, catalog sync, product detail enrichment, price/inventory ingestion, and order export. Use the whole toolkit or pick the modules you need.

### Content
Repeat the five-feature grid from the homepage, but each card is expanded to a short paragraph and includes a "Learn more" link to its sub-page.

### Closing band
**Configurable down to the dropdown.** Every module exposes settings for layout, styling, behavior, and data mapping — so the toolkit fits your store rather than the other way around.

---

## Feature Sub-Pages

### YMM Fitment Search (`/features/ymm-search/`)

**Hero**
*Eyebrow:* Fitment search
*Headline:* **A fitment search shoppers actually finish.**
*Subhead:* Year, Make, Model — plus Sub-Model, Engine, and the other qualifiers your catalog needs. Configurable order, configurable styling, persistent garage. Built to be fast on storefronts with hundreds of thousands of SKUs.
*CTAs:* [Book a Demo]  [Install on Shopify]  [View Demo Site →]
*Visual:* Annotated screenshot of the YMM widget in three states (empty, mid-selection, with results).

**How it works**
1. **Connect your data** — ACES/PIES, ShowMeTheParts, or CSV.
2. **Choose the qualifiers** — pick which attributes appear as dropdowns and in what order.
3. **Drop the widget in** — install on category pages, the home page, or any block your theme supports.

**Three ways to find the right part**
- **Year-Make-Model dropdowns.** The standard. Predictable order, fast filtering, persistent garage.
- **VIN Lookup.** Worried shoppers won't know their year, make, or model? They can paste in a VIN and we'll resolve it to the right vehicle automatically (where the underlying data source supports VIN decoding — ShowMeTheParts and most ACES/PIES vendor feeds do).
- **License-plate lookup.** Even faster for shoppers who only know the state and plate. Data-source dependent — available where your data source provides a plate-to-VIN service.

**What you can configure**
- Dropdown order, labels, and required vs optional qualifiers
- Garage: save vehicles, restore on return, multi-vehicle support
- VIN entry: visible by default, behind a toggle, or hidden
- License-plate entry: visible by default, behind a toggle, or hidden
- Layout: inline, modal, sidebar, sticky
- Styling: colors, typography, spacing — driven by your theme tokens
- Result behavior: filter the current collection, redirect to a fitment-aware results page, or both
- "No fit" handling: hide, dim, or label products that don't match

**Powered by your data source of choice**
ACES/PIES XML · ShowMeTheParts API · CSV. Switch sources later — your storefront configuration carries over.

**FAQ**
- **How fast is it on a large catalog?** The search index is precomputed at sync time, so dropdown population and result filtering are constant-time on the storefront regardless of catalog size.
- **Can shoppers save more than one vehicle?** Yes. Multi-vehicle garage is built in and persists across sessions for signed-in customers.
- **Does it work with my existing theme?** Yes. The widget is a Shopify block; it inherits theme tokens by default and exposes its own settings for any overrides.
- **What happens when a shopper picks a vehicle and lands on a product that doesn't fit?** Configurable: hide, dim with a fitment warning, or surface a "shop for this vehicle" link.
- **Does it support VIN decoding?** Yes, when your underlying data source provides VIN-to-vehicle resolution (ShowMeTheParts and ACES/PIES vendor feeds typically do; pure CSV does not).

**Final CTA:** Same band as homepage.

---

### Catalog Parts Sync (`/features/catalog-sync/`)

**Hero**
*Eyebrow:* Catalog sync
*Headline:* **Your authoritative catalog, faithfully reproduced in Shopify.**
*Subhead:* Push parts, variants, attributes, and fitment from the system of record into Shopify products and metafields — on a schedule, on demand, or driven by changes in the source.
*CTAs:* [Book a Demo] [Install on Shopify]
*Visual:* Admin screenshot of a sync run with counts (created / updated / skipped / errored).

**How it works**
1. **Point at the source** — ACES/PIES file, ShowMeTheParts account, or CSV.
2. **Map fields** — choose how source attributes land in Shopify products, variants, and metafields.
3. **Run it** — full first sync, then incremental on the cadence you choose.

**What you can configure**
- Full vs incremental sync
- Schedule (hourly, daily, weekly) and on-demand runs
- Field mapping: any source attribute to any Shopify field or metafield
- Conflict resolution: source-wins, Shopify-wins, or per-field rules
- Tagging and collection rules driven by source attributes
- Image handling: source URLs, hosted assets, or skip
- Dry-run mode for previewing diffs before write

**Powered by**
ACES/PIES XML · ShowMeTheParts API · CSV. The same connector that drives YMM search drives catalog sync — one source of truth.

**FAQ**
- **How long does a first sync take?** Depends on catalog size and image policy. As a rough guide, a [100,000-SKU] catalog without image hosting completes in [under an hour]; with image hosting it is bound by Shopify's image upload throughput.
- **Will it overwrite manual edits I make in Shopify?** Only fields you've configured as source-wins. Anything not under sync control is left alone.
- **What if a SKU disappears from the source?** Configurable: archive, draft, mark out-of-stock, or no-op.
- **Can I run sync against a development store first?** Yes — install on a dev store, dry-run against your file, review the diff, then promote.
- **Do you support multi-store / Shopify Plus deployments?** Yes. One source can drive multiple stores with per-store overrides.

**Final CTA:** Same band.

---

### PDP Product Information (`/features/pdp-enrichment/`)

**Hero**
*Eyebrow:* Product detail pages
*Headline:* **Every product page, fully informed. Fewer "didn't fit" returns.**
*Subhead:* Fitment tables, item attributes, specs, notes, and Buyer's Guide content rendered on the product detail page — themed to match your store and driven by the same data that powers your YMM search. Real-time product data means shoppers see the most accurate fitment info, so they buy with confidence and you process fewer returns.
*CTAs:* [Book a Demo]  [Install on Shopify]
*Visual:* Annotated PDP screenshot highlighting the fitment block, attribute table, Buyer's Guide, and notes.

**How it works**
1. **Sync your data** — once via Catalog Sync, every PDP gets the same enrichment.
2. **Choose your blocks** — fitment table, Product Item Attributes, Buyer's Guide, notes, related fitment.
3. **Style to match** — blocks read from theme tokens and expose their own settings.

**What you can configure**
- Which blocks appear, and in what order
- **Buyer's Guide block** — render the manufacturer's buying guidance directly on the PDP
- **Product Item Attributes** — structured attributes grouped and styled per product type
- Fitment table grouping (by vehicle, by engine, collapsed-by-default, etc.)
- Attribute templates per product type
- Notes display: inline, footnoted, or expandable
- "Other vehicles this fits" cross-sell block
- Show/hide behavior based on whether a shopper has selected a vehicle

**The returns angle**
Most "didn't fit" returns come from incomplete product data. PDP enrichment fixes that by rendering the manufacturer's authoritative fitment, attributes, and Buyer's Guide on every product page — kept current automatically because it reads from the same data feed that powers your search. No manual updates. No "data went stale a year ago" PDPs.

**Powered by**
The same connector and catalog sync that feed YMM search. Configure once.

**FAQ**
- **Does this require a custom theme?** No. Blocks install through Shopify's theme editor.
- **What about theme upgrades?** Blocks are app-managed and survive theme version changes.
- **Can I show fitment for the shopper's selected vehicle only?** Yes. With a vehicle selected from YMM search, the fitment block can collapse to the matching rows and surface a "see all fitment" toggle.

**Final CTA:** Same band.

---

### In-Cart Fitment & Fulfillment Handoff (`/features/in-cart-fitment/`)

**Hero**
*Eyebrow:* In-cart fitment
*Headline:* **The shopper's vehicle follows the order all the way to the warehouse.**
*Subhead:* The vehicle a shopper selected in YMM search travels with them through the product page, the cart, and the checkout — and lands on the order so your fulfillment team can see it before they pick and pack. Ship the right part the first time.
*CTAs:* [Book a Demo] [Install on Shopify]
*Visual:* Annotated screenshot showing the fitment block in cart, plus a Shopify admin order detail with the fitment record highlighted.

**How it works**
1. **Capture at search.** When a shopper picks a vehicle in YMM search, that selection is bound to the session.
2. **Persist through checkout.** Vehicle info is attached as Shopify line-item properties and order metafields, so it shows up in cart, on the order summary, and in the Shopify admin.
3. **Hand off to fulfillment.** Your fulfillment team sees the exact vehicle on the order — visible in the admin and (optionally) rendered on the packing slip via a theme app extension.

**What you can configure**
- Which fitment qualifiers travel with the order (vehicle only, or vehicle + engine + sub-model + notes)
- Whether the fitment record renders on the customer-facing order confirmation
- Whether the fitment record renders on the printed packing slip
- Whether shoppers can edit the captured vehicle from the cart
- Whether the captured vehicle blocks checkout if the cart contains non-fitting items (or just warns)

**Powered by**
The same data layer as YMM Search and Catalog Sync.

**FAQ**
- **Does this work with Shopify's standard checkout?** Yes. Fitment data is attached as line-item properties and order metafields — standard Shopify primitives, no checkout customization required.
- **Will my 3PL see it on order export?** Yes. Order Export carries the fitment record through to any destination you configure.
- **What if a shopper changes their mind in cart?** Configurable — you can let them edit the captured vehicle in place, or require them to clear the cart and re-search.

**Final CTA:** Same band.

---

### Price & Inventory Sync (`/features/price-inventory-sync/`)

**Hero**
*Eyebrow:* Price & inventory
*Headline:* **Price and inventory updates from the channels your suppliers already use.**
*Subhead:* Drop a file on FTP. Send an email with an attachment. SPT picks it up, validates it, and updates Shopify on the cadence you choose.
*CTAs:* [Book a Demo] [Install on Shopify]
*Visual:* Admin screenshot of a P&I run log with timestamps, file source, and updated SKU count.

**How it works**
1. **Pick a channel** — FTP/SFTP or a dedicated inbound email address.
2. **Map the format** — CSV columns or a fixed-width template to Shopify price and inventory fields.
3. **Schedule or trigger on arrival** — your call.

**What you can configure**
- Source: SFTP, FTP, or email attachment
- Pickup schedule, or trigger-on-arrival for email
- File format mapping (CSV, fixed-width, tab-delimited)
- Multi-location inventory destination
- Cost vs price vs compare-at price fields
- Error reporting: email digest, webhook, or both
- Held-back updates: thresholds for "too big a change" to apply automatically

**Powered by**
Independent of your catalog data source. P&I can come from a different supplier than your fitment data.

**FAQ**
- **What if the file format changes mid-week?** Mappings are versioned; you can pin a mapping or roll back.
- **What about line-level errors?** Errors are isolated per row — a malformed line does not block the rest of the file.
- **Can I dry-run a new mapping?** Yes. Upload once in dry-run mode, review the diff, then enable.

**Final CTA:** Same band.

---

### Order Export (`/features/order-export/`)

**Hero**
*Eyebrow:* Order export
*Headline:* **Send orders to the warehouse, ERP, or 3PL the way they already expect them.**
*Subhead:* Push every paid order to Email, FTP/SFTP, or an HTTP API endpoint, formatted to match the system on the other side. Retries, deduplication, and an audit trail included.
*CTAs:* [Book a Demo] [Install on Shopify]
*Visual:* Admin screenshot of the export destinations list and a sample exported file/payload.

**How it works**
1. **Define destinations** — one or more Email, FTP, or API endpoints.
2. **Map the payload** — Shopify order fields to your destination's format.
3. **Choose triggers** — on paid, on fulfilled, on tag, or scheduled.

**What you can configure**
- Destination type: Email, FTP/SFTP, HTTP API
- Format: CSV, XML, JSON, or fixed-width
- Trigger condition: order paid, fulfilled, tagged, in a specific channel
- Per-line-item routing (split a single order to multiple destinations)
- Retry policy and backoff
- Manual replay from the run log

**Powered by**
Independent of catalog and P&I. Use any combination of modules you need.

**FAQ**
- **Will it retry if my endpoint is down?** Yes, with exponential backoff and a manual replay option.
- **Can I split one Shopify order across two destinations?** Yes, by line item, vendor, location, or any tag rule you define.
- **Do you keep an audit trail?** Every export attempt is logged with the rendered payload, response, and timestamp.

**Final CTA:** Same band.

---

## Integrations (`/integrations/`)

### Hero
*Eyebrow:* Data sources & channels
*Headline:* **Bring the data you have. Plug into the channels you already run.**
*Subhead:* SPT is data-source agnostic. Pick the catalog source that matches how you operate today, and connect to the ingestion and export channels your supply chain already speaks.
*CTAs:* [Book a Demo] [Install on Shopify]

### Primary data sources (three tiles)
1. **ACES/PIES** — Industry-standard XML for fitment and product information. The most common source for parts manufacturers.
   *Link:* See ACES/PIES details → /integrations/aces-pies

2. **ShowMeTheParts** — API-based fitment and parts data. Good fit for retailers without their own ACES/PIES feed.
   *Link:* See ShowMeTheParts details → /integrations/showmetheparts

3. **CSV** — Bring your own spreadsheet or export. The fastest path for stores with a small or custom catalog.
   *Link:* See CSV details → /integrations/csv

### Ingestion & export channels (row)
- **SFTP / FTP** — drops for catalog, P&I, and orders
- **Inbound email** — attachment pickup for P&I
- **HTTP API** — outbound order delivery to ERPs, 3PLs, and homegrown systems

### Closing line
Switch sources later without rebuilding your storefront. The configuration that drives your YMM search, PDP, and catalog sync is decoupled from the underlying connector.

---

### ACES/PIES (`/integrations/aces-pies/`)
**Headline:** **ACES and PIES, on Shopify, without a custom build.**
**Subhead:** Drop your ACES (fitment) and PIES (product information) files onto FTP, and SPT handles parsing, validation, and sync to Shopify products, variants, and metafields.

**What's supported**
- ACES 3.x and 4.x fitment
- PIES 6.x and 7.x product information, including descriptions, attributes, packaging, and digital assets
- Full and incremental updates
- File-level and record-level error reporting
- Mapping overrides for non-standard PCdb or PAdb usage

**Who this fits**
Parts manufacturers and large retailers who already maintain ACES/PIES feeds. If you publish to AutoCare's standards, you can publish to Shopify with SPT.

**CTA:** [Book a Demo against your ACES/PIES file]

---

### ShowMeTheParts (`/integrations/showmetheparts/`)
**Headline:** **ShowMeTheParts data, live on your Shopify storefront.**
**Subhead:** Connect your ShowMeTheParts account and SPT will sync the parts, vehicles, and fitment your store needs — without an ACES/PIES file of your own.

**What's supported**
- Parts and fitment sync via API
- VIN and license-plate lookup, where ShowMeTheParts provides it
- Daily incremental updates by default; on-demand sync available

**Who this fits**
Retailers and aftermarket sellers who don't maintain their own catalog data but want manufacturer-grade fitment.

**CTA:** [Book a Demo using ShowMeTheParts]

---

### CSV (`/integrations/csv/`)
**Headline:** **A spreadsheet is enough to get started.**
**Subhead:** If you have a CSV of parts, vehicles, and fitment, you have everything SPT needs to power YMM search, catalog sync, and PDP enrichment.

**What's supported**
- Separate or combined files for parts, vehicles, and fitment
- Configurable column mapping
- Re-upload to update; full or partial replacement
- Validation report on each upload

**Who this fits**
Single-store retailers, niche/specialty sellers, and anyone piloting before investing in ACES/PIES.

**CTA:** [Book a Demo with your CSV]

---

## Merchant of Record (`/merchant-of-record/`)

> Distinct from the Shopify-app modules — this is a separately offered service. Faithful port of the existing `/merchant-of-record` page on the current site, refreshed to match the new design system.

### Hero
*Eyebrow:* Merchant of Record
*Headline:* **Sales tax, simplified.**
*Subhead:* Reduce sales tax headaches so you can focus on growing your automotive parts business. SPT becomes the seller of record on your store — we collect, remit, and report sales tax across US jurisdictions; you receive consolidated monthly payouts.
*CTA:* [Book a Demo]

### What is a Merchant of Record?
Using a Merchant of Record service effectively outsources the transaction process. Your customer purchases from us; we then pay you as the supplier, minus our fees. The entire customer experience stays branded as your company.

**Three-step flow:**
1. **Collection.** We facilitate checkout, calculating and collecting the necessary sales tax.
2. **Remittance.** We remit the sales tax owed through our entity. Your business stays free of sales tax reporting and payment obligations.
3. **Payment.** We send you order payouts, minus payment processing and service fees.

### Benefits
1. **Tracking & Reporting.** We monitor sales-tax-rule changes and keep tax collection up to date. Reports are generated to match state requirements.
2. **Simplicity.** We pay state sales taxes on behalf of our entity, ensuring timely and accurate remittance. You receive recurring payments — less fees and sales tax — with no reporting obligations, from a single customer: us.
3. **Reduced Liability.** Your existing businesses and services remain isolated from additional tax obligations you'd incur by selling online directly. Internal processes and accounts stay the same.

### Powered by
Shopify · BigCommerce · Stripe

### FAQ
- **Who is providing the merchant services when using your Merchant of Record service?** We use Shopify (via Shop Pay). If any third parties are involved, we'll confirm.
- **What payment methods are available?** Credit cards are enabled by default. Additional Shopify-supported payment methods can be added.
- **Will there be reports on payments made to my store?** Yes. We provide a monthly reconciliation report that details sales, sales tax, and fees.
- **Who do customers actually pay?** Customers pay us, SPT, directly. We then remit one consolidated payment to you along with the reconciliation report. Similar to how eBay works if you sell through eBay.
- **Who collects and remits payments?** We handle collection, processing fees, and sales tax — then remit a single monthly payment with a reconciliation report.
- **Will customers receive an invoice for their purchase?** Customers receive an order receipt by email from Shopify.

### Final CTA
**Talk to us about taking sales tax off your plate.**
[Book a Demo]

---

## Pricing (`/pricing/`)

> Confirm with owner whether to publish tiers or use "Contact for pricing." Draft below assumes a three-tier published model, with a manufacturer/enterprise tier as the largest. Replace `$[X]` with confirmed prices.

### Hero
**Headline:** **Pricing that scales with your catalog, not with your sales.**
**Subhead:** Pick the plan that matches your data source and catalog size. Switch any time. All plans include the full toolkit — modules aren't sold separately.

### Tier 1 — Starter
**$[X] / month**
For single-store retailers piloting YMM search.
- CSV data source
- YMM Fitment Search
- Catalog sync (manual + scheduled)
- PDP enrichment
- Up to [N] SKUs
- Email support

### Tier 2 — Growth
**$[X] / month** *(Most popular)*
For multi-channel retailers and small manufacturers.
- ShowMeTheParts or CSV data source
- Everything in Starter
- Price & inventory sync
- Order export (1 destination)
- Up to [N] SKUs
- Priority email support

### Tier 3 — Manufacturer
**Contact us**
For parts manufacturers and large multi-store operations.
- ACES/PIES data source
- Everything in Growth
- Multi-store / multi-destination order export
- Unlimited SKUs
- Dedicated onboarding
- SLA, named contact, and security review

### FAQ band
- **Do you charge per SKU?** No. SKU counts gate tiers but there is no per-SKU usage fee.
- **What's included in onboarding?** Configuration of your data source, dry-run of catalog sync, and a working YMM search on a staging store before you go live.
- **Can I switch tiers?** Yes, at any time, prorated.
- **Is there a free trial?** Yes, on Starter and Growth. The Manufacturer tier is sold with an onboarding engagement.

**Final CTA:** [Book a Demo] [Install on Shopify]

---

## Customers (`/customers/`)

### Hero
**Headline:** **Manufacturers and retailers running on SPT.**
**Subhead:** From catalog-of-record sync to single-store fitment search, here's how teams are using the toolkit.

### Logo wall
*Eight placeholder logos with a small "and more" caption.*

### Case study grid (two placeholder cards)

**Card 1 — Manufacturer**
*[Acme Performance Parts] cuts time-to-storefront from [quarters to weeks].*
[Acme Performance Parts] used SPT to push their ACES/PIES catalog to a Shopify Plus storefront without rebuilding their data infrastructure.
*Read the case study →*

**Card 2 — Retailer**
*[Northbound Truck & Off-Road] launches YMM search across [50,000 SKUs] in [under two weeks].*
A specialty truck and off-road retailer used SPT's CSV connector and YMM search to give shoppers vehicle-specific results without engineering work.
*Read the case study →*

---

### Case Study Template (`/customers/[slug]/`)

> Use this template for both placeholder case studies. Replace bracketed values with real data when available.

**Hero**
*Eyebrow:* Case study
*Headline:* **[One-line outcome — e.g., How [Company] launched ACES/PIES-backed fitment on Shopify in [N] weeks.]**
*Subhead:* [One-sentence summary of the customer and the result.]

**At a glance**
- **Industry:** [Aftermarket performance / Truck & off-road / OE replacement / etc.]
- **Catalog size:** [N SKUs]
- **Data source:** [ACES/PIES / ShowMeTheParts / CSV]
- **Modules used:** [List]
- **Outcome:** [Headline metric]

**The challenge**
[2–3 paragraphs describing the customer's situation before SPT. Be specific about the pain — slow manual updates, missing fitment, custom dev costs, etc.]

**The solution**
[2–3 paragraphs describing which modules were configured and how. Reference the data source and the channels used.]

**The result**
[2–3 paragraphs with concrete outcomes. Avoid vague "transformative" language; favor specifics like time-to-launch, SKU counts, sync cadence, or operational savings.]

**In their words**
> "[Pull quote — 1–2 sentences.]"
> — [Name], [Title], [Company]

**Final CTA:** [Book a Demo] [Install on Shopify]

---

## Blog

### Blog index (`/blog/`)
**Headline:** **Notes from the parts-on-Shopify trenches.**
**Subhead:** Practical writing for parts manufacturers and automotive retailers selling on Shopify. Fitment, data, operations, and the occasional opinion.

### Placeholder Post 1 — `understanding-aces-pies-for-shopify-merchants.md`

```
---
title: "Understanding ACES and PIES for Shopify merchants"
description: "A plain-English guide to the two data standards behind automotive parts ecommerce — and what they mean if you sell on Shopify."
publishDate: 2026-05-15
author: "SPT"
tags: ["data", "aces-pies", "fundamentals"]
draft: false
---
```

**Introduction**
If you sell automotive parts on Shopify, sooner or later you'll bump into two acronyms: ACES and PIES. They're the two data standards that quietly run the aftermarket parts industry. This post explains what each one is, why it exists, and what it means if your storefront lives on Shopify.

**What is ACES?**
ACES — short for the Aftermarket Catalog Exchange Standard — is the answer to the question, "Which vehicles does this part fit?" Maintained by the AutoCare Association, ACES is an XML format that ties part numbers to vehicle applications using a controlled vocabulary called the VCdb (Vehicle Component Database) and the PCdb (Parts Component Database). When a manufacturer publishes an ACES file, every line is, in plain English, "this part fits this engine in this submodel of this model in this year."

**What is PIES?**
PIES — the Product Information Exchange Standard — answers "what is this part?" Where ACES describes fitment, PIES describes the part itself: descriptions, attributes, packaging, hazardous-materials flags, digital assets, marketing copy. The two formats are designed to be used together — ACES for *fits what*, PIES for *what is it*.

**Why this matters on Shopify**
Shopify wasn't built for the aftermarket. It has products, variants, and metafields. It does not natively understand "this brake pad fits the 2018–2022 F-150 with the 6.2L engine." Bridging that gap — turning ACES fitment and PIES content into Shopify products, variants, metafields, and a fitment-aware search experience — is exactly the gap SPT closes.

**If you don't have ACES/PIES**
That's fine. Most retailers don't. ShowMeTheParts gives you API-driven fitment without maintaining your own files, and a clean CSV will get you a working fitment search faster than most teams expect.

**Closing**
Whatever shape your data is in today, the path to a real parts-store experience on Shopify is shorter than it used to be. [Book a demo](/demo) and we'll run a sample of your data through the toolkit so you can see what it looks like.

---

### Placeholder Post 2 — `why-ymm-search-matters.md`

```
---
title: "Why YMM search is the difference between a parts store and a Shopify store"
description: "Year-Make-Model search isn't a nice-to-have for automotive parts — it's the only way most shoppers know how to find the right product."
publishDate: 2026-05-01
author: "SPT"
tags: ["ymm", "ux", "fundamentals"]
draft: false
---
```

**Introduction**
A shopper walks into your Shopify store looking for a serpentine belt. They don't know the part number. They don't know the OEM cross-reference. They know it's for a 2014 Silverado 1500 with the 5.3L V8. If your store can't take that input and return only the parts that fit, you've already lost them — usually to a competitor that can.

**The "fits what" problem**
General-purpose ecommerce search is built around words: titles, descriptions, tags. Parts ecommerce is built around relationships: a part fits a vehicle. No amount of keyword search will reliably narrow "brake pads" down to "brake pads for the front of a 2014 Silverado 1500 6-lug." You need a structured filter — Year, Make, Model, and usually a few more qualifiers — driven by real fitment data.

**What good YMM looks like**
- **Predictable order.** Year → Make → Model → Sub-model → Engine, in the order shoppers expect.
- **Persistent garage.** Once a shopper picks their vehicle, every page knows it.
- **Honest "no fit" handling.** If a product doesn't fit, say so clearly. Don't hide it silently and don't show it without warning.
- **Fast.** Dropdowns populating in a quarter-second is the bar. Anything slower and shoppers will second-guess their selection.

**What gets it wrong**
- Forcing shoppers to pick a vehicle before they can browse at all.
- Letting them pick a vehicle, then showing them products that don't fit anyway.
- Resetting the garage on every page navigation.

**Closing**
YMM search isn't a feature on a parts store; it's the floor. Once you've got it right, the rest of the catalog experience — PDPs, cross-sells, search — gets easier. [See how it works](/features/ymm-search), or [book a demo](/demo) against your own data.

---

## Changelog (`/changelog/`)

### Index
**Headline:** **What's new in SPT.**
**Subhead:** Release notes, in plain language. Subscribe via [RSS](/changelog/rss.xml) or check back any time.

### Placeholder entry 1 — `v1-2-0.md`

```
---
version: "1.2.0"
date: 2026-05-10
title: "ShowMeTheParts API connector + multi-destination order export"
---
```

**New**
- **ShowMeTheParts as a primary data source.** Connect your ShowMeTheParts account, and catalog sync, YMM search, and PDP enrichment all read from it.
- **Multi-destination order export.** Send a single Shopify order to multiple destinations (Email + FTP + API in any combination), with per-line-item routing rules.

**Improved**
- Sync run logs now show per-field diffs on updated SKUs.
- YMM widget loads ~30% faster on first paint via deferred dropdown hydration.

**Fixed**
- Resolved an edge case where ACES `BaseVehicle` records without engine qualifiers were skipped during incremental sync.

---

### Placeholder entry 2 — `v1-1-0.md`

```
---
version: "1.1.0"
date: 2026-04-05
title: "Inbound email for price & inventory + multi-vehicle garage"
---
```

**New**
- **Inbound email channel for P&I sync.** Dedicated inbound address per store; attachments are picked up and processed automatically.
- **Multi-vehicle garage.** Shoppers can save more than one vehicle and switch between them from the header.

**Improved**
- CSV upload validator now flags duplicate fitment rows before sync.
- Admin sync log adds a "replay" action on failed runs.

**Fixed**
- Corrected an off-by-one in the year-range expansion when ACES `MinYear == MaxYear`.

---

## About (`/about/`)

### Hero
**Headline:** **We build the plumbing automotive parts ecommerce has been missing.**
**Subhead:** SPT is a focused team on one thing: making the boring, hard, structural parts of selling automotive parts on Shopify actually work.

### Who we are
**SPT** (short for *Standard Parts Toolkit*) is a product of **[No Fixed Plans](https://nofixedplans.xyz/)**.

We support several parts-data sources out of the box — including **[ShowMeTheParts](https://info.showmetheparts.com/)** (operated by Vertical Development), ACES/PIES files you provide, and CSV uploads — so merchants can use whichever feed matches how they already operate.

*[Owner: confirm exact wording before publish.]*

### Story
Most ecommerce tooling assumes a clean catalog and a simple "search for a t-shirt" UX. Automotive parts don't work that way. The catalog is huge, the fitment relationships are messy, the data lives in ACES/PIES files most platforms don't understand, and the order flow has to land in warehouses and ERPs that were written before the modern web.

We built SPT because the gap between "automotive parts" and "Shopify" was being filled — store by store — by custom development projects that took quarters and broke on every theme upgrade. The toolkit replaces that custom build with a configurable, supported app.

### Values
- **Specifics over slogans.** We write copy, build features, and answer support tickets with the actual details.
- **Configurable, not opinionated.** Your store, your catalog, your workflow. We expose settings; you make the calls.
- **Boring is beautiful.** Sync runs that just work. Forms that submit cleanly. Audit trails that say what happened. We're not chasing novelty.

### Where to find us
**1449 S Michigan Ave STE 13288, Chicago, IL 60605**

### Team
*[Placeholder team grid — names, roles, photos. Fill when ready.]*

### CTA
**Want to see if we're a fit?**
[Book a Demo]

---

## Contact (`/contact/`)

### Hero
**Headline:** **Get in touch.**
**Subhead:** Questions about the toolkit, your data, or whether we're a fit? Send a message and we'll respond within one business day.

### Contact form
Fields:
- Name *
- Company *
- Email *
- Message *

Submit button: **Send message**
Success state: *"Thanks — we'll be in touch within one business day."*

### Other ways to reach us
- **Email:** [hello@standardpartstoolkit.com]
- **Support email:** [support@standardpartstoolkit.com]
- **Mailing address:** 1449 S Michigan Ave STE 13288, Chicago, IL 60605
- **Knowledge Base:** [https://kb.standardpartstoolkit.com](https://kb.standardpartstoolkit.com)
- **Shopify App Store:** [App Store URL]

---

## Demo (`/demo/`)

### Hero
**Headline:** **See it on your data.**
**Subhead:** A demo isn't a sales call with slides. We run a sample of your ACES/PIES file, ShowMeTheParts feed, or CSV through the toolkit, then walk you through the resulting YMM search and product pages — typically in 30 minutes.

### Demo request form
Fields:
- Name *
- Company *
- Role *
- Work email *
- Shopify store URL (if you have one)
- Primary data source (ACES/PIES / ShowMeTheParts / CSV / Not sure yet) *
- Approximate catalog size (SKUs) *
- Primary goal (free text) *
- Anything else we should know? (optional)

Submit button: **Request a demo**
Success state: *"Thanks — we'll be in touch within one business day to schedule a time and let you know what data sample to share."*

### Reassurance line under the form
We won't add you to a marketing drip. We won't share your data with anyone. If we're not a fit, we'll tell you.

---

## Legal Pages

> ⚠️ Drafts only. **All three legal pages must be reviewed by qualified counsel before launch.** Replace bracketed placeholders with confirmed company details.

### Privacy Policy (`/legal/privacy/`)

**Effective date:** [DATE]

**Who we are.** SPT ("Standard Parts Toolkit", "we", "us") is operated by [LEGAL ENTITY] at [REGISTERED ADDRESS]. You can reach us at [privacy@standardpartstoolkit.com].

**What this policy covers.** This policy describes how we collect, use, and disclose information when you visit our marketing website at [standardpartstoolkit.com] or fill out a form on it. Our handling of data inside the Shopify app itself is covered by the in-app privacy disclosures and our agreement with the merchant.

**Information we collect on the website**
- **Information you give us via forms.** Name, company, email, and any free-text you submit through our contact, demo, or newsletter forms.
- **Information collected automatically.** We use Google Analytics 4 to understand how the site is used. GA4 sets cookies and processes your IP and basic device information. See "Cookies" below.

**How we use it**
- To respond to your inquiry.
- To send you the newsletter, if you subscribed.
- To understand aggregate usage of the site and improve it.

**Who we share it with**
- **Formspree** processes form submissions on our behalf.
- **Google Analytics** processes site usage data on our behalf.
- We do not sell personal information.

**Cookies and tracking**
We use Google Analytics cookies only after you accept the cookie banner. We do not use advertising or remarketing cookies. You can change your choice at any time via the "Cookies" link in the footer.

**Your rights**
Depending on where you live, you may have rights to access, correct, delete, or port your data, and to opt out of certain processing. Email [privacy@standardpartstoolkit.com] and we'll respond within [30] days.

**Data retention**
We retain form submissions for as long as needed to respond to your inquiry and, where relevant, to maintain a customer relationship. Analytics data is retained according to our GA4 retention settings, currently [14 months].

**Changes to this policy**
We'll update this page when our practices change. The effective date at the top reflects the most recent update.

---

### Terms of Service (`/legal/terms/`)

**Effective date:** [DATE]

**Acceptance.** By installing or using the SPT Shopify app, or by using the standardpartstoolkit.com website, you agree to these Terms.

**The service.** SPT is a Shopify app for automotive parts merchants. It provides fitment search, catalog sync, PDP enrichment, price/inventory sync, and order export, configured per merchant.

**Your account.** You're responsible for the actions taken under your Shopify store and any sub-users you grant access to.

**Acceptable use.** You won't use the service to violate the law, infringe others' rights, or interfere with the service.

**Customer data.** You own your data. We process it on your behalf to provide the service. Our Privacy Policy and (where applicable) Data Processing Addendum govern how.

**Fees.** Plans and fees are described on our [Pricing page](/pricing). We may change pricing prospectively; existing subscriptions are honored until renewal.

**Service availability.** We aim for high availability but do not promise uninterrupted service except where a separate SLA applies.

**Termination.** Either party may terminate at any time. On termination, we'll provide reasonable assistance with data export and will delete or return your data per our agreement and applicable law.

**Disclaimers and limitation of liability.** [Standard SaaS limitation-of-liability language — to be drafted by counsel.]

**Governing law.** These Terms are governed by the laws of [JURISDICTION].

**Contact.** Questions: [legal@standardpartstoolkit.com].

---

### Security & Data Handling (`/legal/security/`)

**Last updated:** [DATE]

We work with merchant catalogs, customer order data, and supplier feeds. Here's how we handle them.

**Hosting and data residency**
The SPT service runs on [PROVIDER] in [REGION(S)]. Customer data is stored in [REGION] unless we've agreed otherwise in writing.

**Encryption**
- **In transit:** All connections to the service and between the service and Shopify use TLS 1.2 or higher.
- **At rest:** Data at rest is encrypted using [AES-256 or provider-managed equivalent].

**Authentication and access**
- Merchant access is via Shopify's OAuth flow; we don't store Shopify passwords.
- Internal access to production systems is restricted to a small number of engineers and requires SSO with MFA.
- We log production access and review the logs periodically.

**Customer data**
- We process catalog data, fitment data, price/inventory data, and order data on behalf of the merchant.
- We do not sell customer data.
- We do not use customer data to train machine-learning models.

**Third-party processors**
We use the following sub-processors:
- **[Hosting provider]** — infrastructure
- **[Database provider]** — managed database
- **Google Analytics 4** — website analytics (marketing site only, not the app)
- **Formspree** — marketing site form submissions
- *[Add others as applicable]*

**Backups and disaster recovery**
- Encrypted backups are taken [daily] with a [N-day] retention window.
- We test restore procedures [quarterly].

**Vulnerability management**
- Dependencies are monitored continuously and patched on a defined cadence based on severity.
- Production infrastructure is scanned [monthly]; findings are tracked to resolution.

**Incident response**
We maintain an incident response process. In the event of a confirmed incident affecting customer data, we notify affected merchants without undue delay and follow up with a written summary.

**Questions or a coordinated disclosure**
- General: [security@standardpartstoolkit.com]
- Coordinated vulnerability disclosure: [security@standardpartstoolkit.com] — please give us a reasonable window to respond before any public disclosure.

---

## 404 Page (`/404`)

**Headline:** **That page doesn't fit.**
**Subhead:** We couldn't find what you were looking for. Try one of these instead:
- [Homepage](/)
- [Features](/features/)
- [Integrations](/integrations/)
- [Blog](/blog/)
- [Contact us](/contact/)

*(Optional: a small line of self-aware copy — "We promise our fitment search is more reliable than our URL routing.")*

---

## Footer Microcopy

**Newsletter prompt:**
*Headline:* The toolkit changelog, monthly.
*Subhead:* Release notes, the occasional deep-dive post, no marketing fluff.
*Field placeholder:* you@company.com
*Button:* Subscribe
*Success:* Thanks — you're subscribed.

**Attribution line (above copyright):**
SPT is a product of [No Fixed Plans](https://nofixedplans.xyz/).

**Address line:**
1449 S Michigan Ave STE 13288, Chicago, IL 60605

**Knowledge Base link** (in the Company column of the footer): [Knowledge Base ↗](https://kb.standardpartstoolkit.com)

**Copyright line:**
© [YEAR] No Fixed Plans. SPT and Standard Parts Toolkit are trademarks of No Fixed Plans. Not affiliated with Shopify. ACES and PIES are trademarks of the AutoCare Association.

---

## Open Copy Decisions for the Owner

Before this content goes live, the owner should resolve:

1. **Legal entity name** — current footer uses "No Fixed Plans"; confirm the registered entity that owns the IP and signs contracts. Needed in Privacy, Terms, Security, and the copyright line.
2. **Organizational wording** — confirm "a product of No Fixed Plans" as the canonical phrase for the About page and footer. ShowMeTheParts (operated by Vertical Development) appears only as one of the supported data sources, not as a partner or co-operator of SPT.
3. **Real domain** — used throughout `[standardpartstoolkit.com]` placeholders. Assumes the new site replaces the current site at the same domain (migration plan needed).
4. **Email addresses** — `hello@`, `support@`, `privacy@`, `legal@`, `security@`.
5. **Pricing model and dollar figures** — or switch the pricing page to "Contact for pricing." Also: Merchant of Record pricing.
6. **Capability alignment** — every module beyond what the current site advertises (CSV, direct ACES/PIES, multi-vehicle garage, P&I sync, order export, multi-store) must be operational at launch or framed as "coming soon." Misalignment between copy and reality is the biggest risk.
7. **BigCommerce mention on the MoR page** — confirm whether MoR supports BigCommerce stores while the app is Shopify-only.
8. **Real testimonial usage rights** — Luke Smith / Momentum USA quote is on the current site; confirm it can carry into the new site.
9. **Live demo store** — confirm `https://carmenspartdepot.com` stays accessible and is OK to link as a "View Demo Site" CTA.
10. **Knowledge Base** — confirm `https://kb.standardpartstoolkit.com` stays live and is the canonical help destination.
11. **Real customer names and case study facts** — placeholders are flagged in `[BRACKETS]`.
12. **Real version numbers and dates** — the placeholder changelog entries use illustrative 1.2.0 / 1.1.0 and May/April 2026 dates.
13. **Stat claims** — the "1,000+ part brands" and "24/7 updates" stats are taken from the current site and are safe; any number written as `[N]` or `[X]` still needs confirmation.
14. **Trademark line in the footer** — confirm correct attribution language with counsel.
15. **Demo promise wording** — the homepage and `/demo` page promise "we'll run a sample of your data." Confirm operational readiness before launching with that commitment.
16. **Existing blog content** — `/blog` exists on the current site. Should those posts be ported into the new MDX-based blog, or does the new site launch with placeholder posts only?
17. **Existing Privacy Policy** — preserve / refresh the current `/privacy-policy` content as the starting point for the new policy.
