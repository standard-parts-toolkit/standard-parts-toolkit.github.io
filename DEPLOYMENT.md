# SPT Homepage — Deployment Spec

> Operational runbook for deploying `standardpartstoolkit.com` from this Astro project to GitHub Pages. Written for someone with shell access to the repo and admin rights on the GitHub org + the DNS registrar. Follow top-to-bottom for first-time deploy; jump to §5 for ongoing operations.

---

## 1. Architecture

```
   ┌──────────────────────────────────────────────────────────────┐
   │ Developer                                                    │
   │   $ git push origin main                                     │
   └──────────────────────────────┬───────────────────────────────┘
                                  │
                                  ▼
   ┌──────────────────────────────────────────────────────────────┐
   │ GitHub Actions: .github/workflows/deploy.yml                 │
   │   1. checkout                                                │
   │   2. setup Node 24  + npm ci                                 │
   │   3. npm run build       (Astro → dist/)                     │
   │   4. pagefind --site dist (search index → dist/pagefind/)    │
   │   5. actions/upload-pages-artifact                           │
   │   6. actions/deploy-pages                                    │
   └──────────────────────────────┬───────────────────────────────┘
                                  │
                                  ▼
   ┌──────────────────────────────────────────────────────────────┐
   │ GitHub Pages (deploy target: github-pages environment)       │
   │   Serves dist/ at https://<org>.github.io/  or custom domain │
   └──────────────────────────────┬───────────────────────────────┘
                                  │  CNAME file in dist/ contains
                                  │  www.standardpartstoolkit.com
                                  ▼
   ┌──────────────────────────────────────────────────────────────┐
   │ DNS: standardpartstoolkit.com                                │
   │   Apex  A     → 185.199.108.153, 109, 110, 111               │
   │   www   CNAME → <org>.github.io                              │
   └──────────────────────────────────────────────────────────────┘
```

**Canonical URL:** `https://www.standardpartstoolkit.com` (the `www` subdomain). The apex redirects to `www` via GitHub Pages' built-in apex→www redirect once the apex A records and the `www` CNAME are both configured and the custom-domain field in repo settings says `www.standardpartstoolkit.com`.

---

## 2. Prerequisites

Before kicking off:

| Need | Where | Why |
|---|---|---|
| GitHub org or user account | github.com | Owns the repo |
| Public repo *OR* Pro/Team/Enterprise account | n/a | GitHub Pages from private repos requires a paid plan |
| Admin access to the DNS registrar for `standardpartstoolkit.com` | wherever it's registered | Apex A + www CNAME records |
| Node 24+ locally | nvm / homebrew | Run `npm run build` to verify locally before pushing |
| Formspree account (3 forms) | formspree.io | Contact, Demo, Newsletter form endpoints |
| GA4 property | analytics.google.com | Measurement ID `G-XXXXXXXXXX` |
| Shopify App Store listing | partners.shopify.com | URL for the "Install on Shopify" CTA |

---

## 3. One-time setup

### 3.1 Create the GitHub repo

```bash
# From the repo root (/Users/gcaprio/source/spt-homepage)
# Make sure your working tree is clean and the build succeeds first
npm ci
npm run build   # should finish with "[build] Complete!"

# Initialize git and push (replace <ORG> and adjust if not gh CLI)
git init -b main
git add .
git commit -m "Initial SPT homepage scaffold + content"

# Either use gh CLI:
gh repo create <ORG>/spt-homepage --public --source . --push

# Or manually:
git remote add origin git@github.com:<ORG>/spt-homepage.git
git push -u origin main
```

> **Note on visibility:** GitHub Pages from a private repo requires GitHub Pro / Team / Enterprise. If you're on Free, the repo must be public.

### 3.2 Enable GitHub Pages

In the new repo:

1. **Settings → Pages**
2. **Build and deployment → Source:** select **GitHub Actions** (do *not* select "Deploy from a branch").
3. Leave the workflow file as-is — `.github/workflows/deploy.yml` will be picked up automatically.

### 3.3 Configure repo Variables (not Secrets)

The build script reads these as `PUBLIC_*` Vite env vars. Use **repository Variables**, not Secrets — they're embedded in the public site at build time and are not sensitive.

**Settings → Secrets and variables → Actions → Variables → New repository variable**

| Variable | Example | Required for |
|---|---|---|
| `PUBLIC_FORMSPREE_CONTACT_ID`    | `xqkwabcd` | `/contact` form |
| `PUBLIC_FORMSPREE_DEMO_ID`       | `xpzbabcd` | `/demo` form |
| `PUBLIC_FORMSPREE_NEWSLETTER_ID` | `xpzbefgh` | Footer newsletter |
| `PUBLIC_GA4_ID`                  | `G-XXXXXXXXXX` | GA4 analytics (loads only after consent) |
| `PUBLIC_SHOPIFY_APP_URL`         | `https://apps.shopify.com/spt` | "Install on Shopify" CTA buttons |

Until each variable is set, the relevant feature degrades gracefully:
- Forms show a clearly-marked "Form not configured yet" banner and don't submit.
- GA4 / consent banner doesn't render if `PUBLIC_GA4_ID` is empty.
- "Install on Shopify" buttons fall back to the in-page `#install-on-shopify` anchor.

### 3.4 DNS configuration

The `public/CNAME` file (already in the repo) contains `www.standardpartstoolkit.com`. After the first deploy succeeds you'll wire up DNS to match.

At the DNS registrar for `standardpartstoolkit.com`:

**Apex (`@`) — four A records pointing at GitHub Pages:**

```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```

If your registrar supports `ALIAS` or `ANAME` for the apex, use one of:

```
ALIAS  @   <ORG>.github.io
```

…instead of the four A records (some registrars handle this better).

**`www` subdomain — CNAME to the GH Pages domain:**

```
CNAME  www   <ORG>.github.io
```

(Replace `<ORG>` with the GitHub username or org name that owns the repo.)

**Propagation:** DNS changes take 5 minutes to several hours. Verify with:

```bash
dig +short www.standardpartstoolkit.com
dig +short standardpartstoolkit.com
```

### 3.5 Lock in the custom domain in GitHub

Once DNS has propagated:

1. **Settings → Pages → Custom domain:** enter `www.standardpartstoolkit.com`, save.
2. Wait for the green "DNS check successful" indicator.
3. Tick **Enforce HTTPS** (this lights up once Let's Encrypt has issued a cert — usually within 5 minutes).

The repo's `public/CNAME` file and the custom-domain field in Settings must match. GitHub will rewrite the CNAME if you change the field; don't fight it.

### 3.6 First deploy

Pushing to `main` triggers the workflow automatically. If you've already pushed and want to re-run:

- **Actions → Deploy to GitHub Pages → Run workflow** (workflow_dispatch is enabled).

Successful run shows:

- `build` job: green check, "Astro build → 35 pages in ~900ms, Pagefind indexed 35 pages."
- `deploy` job: green check, with the deployed URL surfaced as the job output.

Browse `https://www.standardpartstoolkit.com` and click around. Things to spot-check:

- Header dropdowns (Products + Features) open and close.
- The Pricing table renders both tiers clearly.
- A Lighthouse run on the homepage scores ≥95 across Performance / A11y / Best Practices / SEO.
- `/blog/rss.xml` and `/changelog/rss.xml` load and validate as RSS.
- `/sitemap-index.xml` lists every page.

---

## 4. Migration from the current Wix-style site

The existing site at `standardpartstoolkit.com` has these URLs:

| Current URL | New URL | Action |
|---|---|---|
| `/` | `/` | Same |
| `/merchant-of-record` | `/merchant-of-record/` | Same (trailing slash handled) |
| `/blog` | `/blog/` | Same |
| `/blog/<slug>` | `/blog/<slug>/` | **Manual port or redirect** — see §4.2 |
| `/privacy-policy` | `/legal/privacy/` | **Needs a redirect** |

### 4.1 Pre-cutover checklist

Don't swap DNS until *all* of these are green:

- [ ] All 5 repo Variables set (Formspree × 3, GA4, Shopify App URL).
- [ ] DNS propagation verified.
- [ ] HTTPS cert issued (green padlock at `https://www.standardpartstoolkit.com`).
- [ ] Forms submit successfully (test Contact + Demo end-to-end; check Formspree dashboard for the entry).
- [ ] GA4 fires on first session after accepting the cookie banner (verify in GA4 Realtime).
- [ ] Lighthouse on homepage and one feature page both score ≥95.
- [ ] Mobile spot-check at 375px width.
- [ ] Dark mode spot-check (`data-theme="dark"` on `<html>`).
- [ ] Existing blog posts decision made: ported to MDX in `src/content/blog/`, or accepted as broken links.
- [ ] Legal pages reviewed by counsel and bracketed placeholders filled.
- [ ] Real placeholders swapped (or accepted as known issues): customer logos, screenshots, case study facts, changelog versions.

### 4.2 Redirect map

GitHub Pages doesn't run server-side redirects. The clean solution is a tiny HTML stub at each legacy URL doing a meta-refresh + canonical link. Drop these into `public/` so they ship as-is:

**`public/privacy-policy/index.html`**

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Redirecting…</title>
  <link rel="canonical" href="https://www.standardpartstoolkit.com/legal/privacy/" />
  <meta http-equiv="refresh" content="0; url=/legal/privacy/" />
  <meta name="robots" content="noindex" />
</head>
<body>
  <p>Redirecting to <a href="/legal/privacy/">/legal/privacy/</a>…</p>
  <script>location.replace('/legal/privacy/');</script>
</body>
</html>
```

Repeat per legacy URL that doesn't already match a new route. If the existing `/blog/<slug>` URLs are being abandoned (not ported), either accept the 404s or stub each one. If they're being ported, copy them into `src/content/blog/` as `.mdx` files with matching slugs — same URL, no redirect needed.

### 4.3 DNS cutover

Once the pre-cutover checklist is green:

1. **Lower TTL** on the existing apex + www records to 300 seconds (5 min) at least 24 hours before cutover. This makes the actual switch reversible quickly.
2. **Update the apex A records** (or ALIAS/ANAME) to the GitHub Pages IPs (§3.4).
3. **Update the `www` CNAME** to `<ORG>.github.io`.
4. **Wait** for propagation (`dig +short www.standardpartstoolkit.com` should return GitHub IPs from `185.199.*`).
5. **Verify** the live site loads from the new infra (View Source → check for SPT brand mark / footer attribution).
6. **Raise TTL** back to 3600 (or your normal value) a day or two after cutover.

### 4.4 Post-cutover verification

- [ ] Apex + www both resolve and load.
- [ ] Apex redirects to `www` (GitHub Pages handles this automatically when the custom domain field is set to the www form).
- [ ] HTTPS works on both apex and www.
- [ ] Every legacy URL either loads (matches a new route) or 301/302/meta-refreshes to the new equivalent.
- [ ] Google Search Console: submit the new sitemap and request a fetch for the homepage.
- [ ] Smoke test the Contact + Demo forms with a real submission and confirm receipt in Formspree.
- [ ] Confirm GA4 sees Realtime traffic.

---

## 5. Ongoing operations

### 5.1 Standard deploy

```bash
# On a feature branch
git checkout -b feat/<short-description>

# Edit, save. Optionally run the dev server to verify:
npm run dev   # http://localhost:4321

# When ready
git add -A
git commit -m "feat: <short description>"
git push -u origin feat/<short-description>

# Open a PR. After review + merge to main, the deploy workflow fires
# automatically. ~2 minutes later the change is live at
# https://www.standardpartstoolkit.com.
```

### 5.2 Preview a PR before merge

Optional but recommended once traffic grows. Two options:

1. **Local build** — `npm run build && npm run preview` then visit `http://localhost:4322`. Cheapest.
2. **Per-PR preview deploys** — Cloudflare Pages or Netlify can ingest the same repo and produce a preview URL per PR. Out of scope for this spec but a sensible v1.x addition.

### 5.3 Rollback

GitHub Pages keeps every deployment. To roll back:

1. **Settings → Pages → Deployment history** (or the **Actions → Deploy to GitHub Pages** run history).
2. Find the last good deployment.
3. **Re-run** that workflow run. The artifact gets re-published, restoring the previous build.

Or, if the bad change is already in `main`:

```bash
git revert <bad-sha>
git push origin main
```

…which triggers a fresh deploy with the reverted state. This is the cleanest rollback because it leaves an audit trail.

### 5.4 Build script details

`package.json` build step:

```
"build": "astro build && pagefind --site dist"
```

`astro build` produces static HTML/CSS/JS in `dist/`. `pagefind --site dist` post-processes the build, generating a search index in `dist/pagefind/`. The deploy workflow uploads the entire `dist/` as the Pages artifact.

If the Pagefind step fails the whole build fails — by design. The site never publishes without a working search index.

---

## 6. Local development

```bash
# Once
nvm install 22                  # or fnm / volta / etc.
nvm use 22
npm ci

# Day-to-day
npm run dev                     # dev server with HMR at :4321
npm run build                   # production build
npm run preview                 # serve dist/ at :4322 to verify production output
```

Environment variables: copy `.env.example` → `.env` and fill in the IDs you want to test locally. The forms and analytics behave the same locally as in production — forms post to Formspree if the ID is set, GA4 loads after consent if `PUBLIC_GA4_ID` is set.

---

## 7. Troubleshooting

### 7.1 The deploy workflow fails

Open the failing run in the **Actions** tab.

- **`npm ci` exits non-zero** — usually a `package-lock.json` mismatch. Locally: `rm -rf node_modules package-lock.json && npm install`, commit, push.
- **`astro build` fails** — read the error. Most build errors are TypeScript/MDX issues from a recently-added file. Try the build locally first.
- **`pagefind` step missing** — confirm `pagefind` is in `package.json` dependencies and `node_modules/pagefind/` exists.
- **`actions/upload-pages-artifact` rejects** — the artifact is over 1 GB or contains forbidden files. Check the `dist/` size locally.
- **`actions/deploy-pages` fails with permission denied** — confirm **Settings → Pages → Source = GitHub Actions** and that the workflow has `permissions: pages: write, id-token: write` (already set).

### 7.2 The site loads but DNS is wrong

```bash
dig +short www.standardpartstoolkit.com
dig +short standardpartstoolkit.com
```

Expected:
- `www` returns `<ORG>.github.io` (and chained IPs).
- Apex returns one of `185.199.108-111.153`.

If results don't match, the registrar hasn't propagated yet, or the records weren't updated. Wait 15 minutes, then escalate to the registrar.

### 7.3 HTTPS doesn't work / "Custom domain" stuck on "DNS check pending"

- Wait. Let's Encrypt cert issuance takes up to 24 hours in the worst case (usually under 10 minutes).
- If still stuck after a day: in repo Settings → Pages, clear the custom-domain field, save, re-enter it, save. This re-runs the verification.
- Confirm the `public/CNAME` file contents exactly match the custom-domain field.

### 7.4 Forms submit but go nowhere

- Confirm the form's repo Variable (`PUBLIC_FORMSPREE_*_ID`) is set on the **`main` branch's last build**. Variables added after the most recent deploy don't apply until the next deploy.
- Check the Formspree dashboard inbox for the form ID — submissions usually show within seconds.
- If still nothing: the form may be hitting Formspree's spam filter. Look for blocked submissions in the Formspree spam folder.

### 7.5 GA4 doesn't show data

- Open the site, click **Accept** on the cookie banner.
- Open browser devtools → Network and confirm a request to `https://www.googletagmanager.com/gtag/js?id=G-...` fires after acceptance.
- If not: confirm `PUBLIC_GA4_ID` is set and the current build was deployed *after* it was set.
- GA4 Realtime takes ~30 seconds for the first event to appear.

### 7.6 Pagefind search returns no results

The Pagefind UI isn't wired into the header yet (see open items in `PROJECT_PROPOSAL.md`). The index exists at `/pagefind/` after deploy — verify with `curl -I https://www.standardpartstoolkit.com/pagefind/pagefind.js` returning 200.

---

## 8. Launch checklist (consolidated)

Before announcing the new site:

**Infrastructure**
- [ ] Repo created and on the right org/visibility
- [ ] Workflow has run successfully at least once on `main`
- [ ] `Settings → Pages` shows the custom domain with green DNS check + enforced HTTPS
- [ ] Apex resolves to GitHub Pages IPs; `www` resolves to `<ORG>.github.io`
- [ ] All 5 repo Variables set

**Content + assets**
- [ ] Real customer logos in place (or accepted-as-known-issue)
- [ ] Real product screenshots (or accepted)
- [ ] Real case studies (or placeholders explicitly approved)
- [ ] Changelog real version numbers + dates
- [ ] Legal pages (Privacy / Terms / Security) counsel-reviewed and bracketed values filled
- [ ] Real testimonial (Luke Smith / Momentum USA) usage rights confirmed
- [ ] Demo store link (`carmenspartdepot.com`) confirmed accessible
- [ ] Knowledge Base (`kb.standardpartstoolkit.com`) confirmed live

**Conversion plumbing**
- [ ] All three Formspree forms tested end-to-end (submission → email → reply within 1 business day)
- [ ] Shopify App Store URL points at the real listing
- [ ] GA4 fires after consent acceptance
- [ ] Cookie banner respects decline (no GA load)

**SEO + crawlability**
- [ ] Sitemap submitted to Google Search Console
- [ ] `robots.txt` allows all
- [ ] Open Graph image renders correctly in Slack/Twitter/iMessage previews
- [ ] At least one page indexed by Google search

**Migration**
- [ ] Redirect stubs in place for any legacy URLs that don't match new routes
- [ ] Existing `/blog` posts decision committed (ported or abandoned)
- [ ] TTLs lowered before cutover, raised after

**QA**
- [ ] Lighthouse ≥95 on homepage AND one feature page
- [ ] Manual mobile pass at 375px
- [ ] Dark mode pass
- [ ] Keyboard nav works (tab through header → main → footer with visible focus rings)
- [ ] No console errors on any page

---

## 9. Reference: file locations

| File | Purpose |
|---|---|
| `.github/workflows/deploy.yml` | The deploy pipeline |
| `astro.config.mjs` | `site: 'https://www.standardpartstoolkit.com'` — update if domain changes |
| `package.json` | `build` script: `astro build && pagefind --site dist` |
| `public/CNAME` | `www.standardpartstoolkit.com` — must match GitHub Pages custom-domain field |
| `public/robots.txt` | Allow all; points to sitemap |
| `public/favicon.svg` | SPT green-tile mark |
| `public/og-default.png` | 1200×630 default social share image |
| `.env.example` | Lists every env var the build accepts |
| `src/components/Analytics.astro` | GA4 boot (gated by consent) |
| `src/components/ConsentBanner.astro` | Cookie consent UI |
| `src/components/ContactForm.astro` | Shared Formspree-backed form |

---

*Updates to this spec should be committed to `main` alongside any infrastructure change that affects deploy behavior. Keep it accurate; future-you will thank present-you.*
