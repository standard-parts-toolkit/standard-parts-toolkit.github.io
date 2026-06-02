# SPT Homepage

The marketing site for **SPT** (Standard Parts Toolkit) — a Shopify app for selling automotive parts.

Live at <https://www.standardpartstoolkit.com> (once deployed).

---

## Quick start

```bash
nvm use 24         # requires Node 24+
npm ci
npm run dev        # http://localhost:4321
```

Other scripts:

| Command | Result |
|---|---|
| `npm run dev`     | Astro dev server with HMR at `:4321` |
| `npm run build`   | Production build → `dist/` (Astro + Pagefind index) |
| `npm run preview` | Serve the production build at `:4322` |

Copy `.env.example` → `.env` and fill in any form / analytics IDs you want to exercise locally.

---

## Stack

- **[Astro 6](https://astro.build)** — static site generator
- **[Tailwind CSS v4](https://tailwindcss.com)** — utility-first styling with a green / orange / yellow brand palette
- **MDX content collections** — blog posts, changelog entries, case studies
- **[Formspree](https://formspree.io)** — contact / demo / newsletter form handling
- **[Pagefind](https://pagefind.app)** — static client-side search index
- **[Partytown](https://partytown.builder.io)** — offloads GA4 to a worker
- **GitHub Pages** — hosting, via GitHub Actions

---

## Repo layout

```
.
├── .github/workflows/deploy.yml   # GH Pages deploy pipeline
├── public/                        # Static assets shipped as-is
│   ├── CNAME                      # www.standardpartstoolkit.com
│   ├── favicon.svg                # SPT green-tile mark
│   ├── og-default.png             # 1200×630 default OG image
│   └── robots.txt
├── src/
│   ├── pages/                     # Astro routes (file = URL)
│   │   ├── index.astro            # Homepage
│   │   ├── features/              # Features overview + 6 sub-pages
│   │   ├── integrations/          # Data sources index + 3 sub-pages
│   │   ├── merchant-of-record.astro
│   │   ├── pricing.astro
│   │   ├── why-shopify.astro      # Comparison vs custom / Magento / BigCommerce
│   │   ├── about.astro
│   │   ├── contact.astro
│   │   ├── demo.astro
│   │   ├── blog/                  # Index + post + tag pages + RSS
│   │   ├── changelog/             # Index + entry + RSS
│   │   ├── customers/             # Index + case study
│   │   ├── legal/                 # Privacy / Terms / Security
│   │   └── 404.astro
│   ├── layouts/                   # BaseLayout, FeaturePageLayout, LegalLayout
│   ├── components/                # Header, Footer, DualCTA, ContactForm,
│   │                              # Analytics, ConsentBanner, JsonLd, …
│   ├── content/                   # MDX source for collections
│   │   ├── blog/                  # 2 placeholder posts
│   │   ├── changelog/             # 2 placeholder release entries
│   │   └── caseStudies/           # 2 placeholder case studies
│   ├── content.config.ts          # Collection schemas (Zod)
│   └── styles/global.css          # Tailwind + design tokens
├── astro.config.mjs               # site URL + integrations
└── package.json
```

---

## The four spec docs in this repo

This repo carries its planning docs alongside the code. Read them in order:

1. **[PROJECT_PROPOSAL.md](./PROJECT_PROPOSAL.md)** — the original implementation brief. Tech stack, audience, site map, brand direction, deployment, open items. Source of truth for "why is this built the way it is."

2. **[CONTENT.md](./CONTENT.md)** — first-pass marketing copy for every page. Headlines, subheads, feature descriptions, FAQs, legal templates. The implementing pages draw from this; if a string seems off, fix it in both places.

3. **[DEPLOYMENT.md](./DEPLOYMENT.md)** — the runbook for pushing this to GitHub Pages: repo setup, DNS, repo Variables, migration plan from the current Wix-style site, rollback procedure, troubleshooting, and a launch checklist.

4. **[overview.html](./overview.html)** — a single self-contained HTML overview that combines the proposal and content drafts in one styled, browsable page. Open in any browser. Useful for sharing with non-technical stakeholders who want to see the spec without skimming markdown.

---

## Adding content

### A new blog post

Drop an `.mdx` file in `src/content/blog/`:

```mdx
---
title: "Your post title"
description: "One sentence that shows up in the index and OG meta."
publishDate: 2026-06-01
author: "SPT"
tags: ["fundamentals"]
draft: false
---

Your post content. Standard Markdown plus MDX components.
```

The blog index, the tag pages, and `/blog/rss.xml` all pick it up automatically.

### A new changelog entry

Drop an `.mdx` file in `src/content/changelog/`:

```mdx
---
version: "1.3.0"
title: "What shipped"
date: 2026-06-15
---

import Section from '../../components/release/Section.astro';

<Section type="new">
- Bullet one
</Section>

<Section type="improved">
- Bullet two
</Section>
```

### A new case study

Drop an `.mdx` file in `src/content/caseStudies/` matching the schema in `src/content.config.ts`.

### A new feature page

Use the shared layout:

```astro
---
import FeaturePageLayout from '../../layouts/FeaturePageLayout.astro';
---
<FeaturePageLayout
  title="…"
  description="…"
  eyebrow="…"
  headline="…"
  subhead="…"
  howItWorks={[ … ]}
  configurable={[ … ]}
  dataSources="…"
  faqs={[ … ]}
/>
```

---

## Operations

For first-time deploy, DNS, env vars, migration, rollback, and troubleshooting see **[DEPLOYMENT.md](./DEPLOYMENT.md)**.

---

## License & attribution

© [year] No Fixed Plans. SPT and Standard Parts Toolkit are trademarks of No Fixed Plans. Not affiliated with Shopify. ACES and PIES are trademarks of the AutoCare Association.
