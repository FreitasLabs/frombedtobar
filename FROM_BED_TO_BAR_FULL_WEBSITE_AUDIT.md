# From Bed to Bar - Full Website Audit

**Audit date:** July 24, 2026  
**Repository:** `FreitasLabs/frombedtobar`  
**Branch / commit reviewed:** `main` / `ff4451abcfb4a5829afdeafff8a283a63d7f3671`  
**Live site checked:** `https://frombedtobar.com/`  
**Audit type:** Read-only repository, browser, content, and production review

> **Important:** This is an audit, not legal, medical, food-safety, or accessibility certification. No site files were changed as part of the audit. The only new project files are this requested report and its PDF edition.

# Audit Scope and Method

The audit covered all 48 HTML files, 151 image files, `robots.txt`, `sitemap.xml`, Git history and deployment signals, every local link and image reference, all JSON-LD blocks, all newsletter forms, representative desktop and mobile rendering, the live production routes, and production response headers.

Non-destructive checks included:

- Repository and Git inventory
- HTML parsing and document-structure checks
- Internal-link and image-reference validation
- Route, canonical, sitemap, and indexing comparison
- Metadata and JSON-LD extraction
- Form, label, consent, and third-party-script inspection
- Asset size, duplication, and zero-byte checks
- Desktop browser review at 1440 x 900
- Mobile browser review at 390 x 844
- Mobile navigation keyboard and Escape-key testing
- Live-route checks for duplicates, search behavior, and missing assets
- Production header and cache inspection
- Review of the project’s earlier production report against the current repository

No dependency installation, form submission, vulnerability exploitation, or destructive testing was performed. There is no package manifest, build command, linter configuration, type checker, or automated test suite to run.

---

# 1. Executive Summary

## Overall condition

From Bed to Bar has a distinctive visual identity, a clear garden-to-glass premise, a substantial first library of useful content, extensive structured data, good basic mobile behavior, and unusually thoughtful internal linking for an early-stage family site. The live homepage is attractive, understandable within seconds, and visually aligned with the brand line, “Rooted in the garden. Raised around the table.”

The site is **usable but not ready for broad public promotion without a focused stabilization pass**. The largest risks are not a failed build or broken primary navigation. They are trust, duplication, performance, maintainability, and content-governance problems:

1. A second live lavender-syrup URL publishes substantially duplicate content without a redirect or `noindex`.
2. Two editorial images referenced by live guide pages return the branded 404 page.
3. The homepage advertises a query-based site search in structured data, but the recipe page ignores the query parameter.
4. The newsletter appears on 44 pages but there is no privacy policy, consent explanation, or nearby privacy link.
5. The home hero is a 2.47 MB PNG marked both high priority and lazy-loaded; the full image library is 167 MB and contains extensive duplicate files.
6. The plum-jam page presents shelf-stable canning instructions with inconsistent yield data and no source citation to a tested preservation authority.
7. Seasonal copy says “what’s growing right now” and “updated for late May” on a live site reviewed in late July.
8. The implementation is 48 hand-maintained HTML documents containing 1.57 MB of inline CSS and 299 KB of inline JavaScript. Shared corrections must be repeated across nearly every page.

## Strongest aspects

- **Brand premise:** The garden, table, family, preserving, and drink themes connect naturally.
- **Visual identity:** Playfair Display, Lora, DM Mono, cream, bark, moss, sage, terracotta, and warm photography form a recognizable editorial system.
- **Content depth:** The herb hubs, harvest-and-preserve guides, and recipe clusters provide genuine practical value.
- **Internal linking:** Plum, mint, rosemary, lavender, and related recipe clusters are well connected.
- **Baseline accessibility:** Every HTML page has a main landmark and skip link; the mobile menu exposes `aria-expanded`, closes with Escape, and returns focus.
- **SEO foundations:** Canonicals, descriptions, social metadata, sitemap, robots file, and JSON-LD are broadly present.
- **Safety awareness:** The disclaimer includes alcohol, raw egg, plant identification, allergies, and general health warnings.
- **Mobile baseline:** Tested homepage and lavender guide showed no horizontal overflow at 390 px.

## Largest risks

- **Trust and compliance:** Newsletter data collection is not paired with a privacy policy; food-preservation content needs qualified review and source attribution.
- **Performance:** Oversized PNGs, duplicated images, missing dimensions on 33 image instances, and a lazy-loaded LCP image create avoidable Core Web Vitals risk.
- **SEO integrity:** Duplicate live routes, overlong metadata, inconsistent authorship, and an unsupported SearchAction weaken otherwise strong implementation.
- **Freshness:** Seasonal pages and blog posts do not expose a reliable visible publication/update system.
- **Maintainability:** Copying complete CSS, navigation, footer, newsletter form, and scripts into every HTML file has already produced drift and malformed markup.

## Public-launch readiness

**Status: Conditional / stabilization required.**

The site can remain online for quiet review and limited sharing. Before active promotion, search-engine outreach, a newsletter campaign, partnerships, or paid traffic, complete the Phase 1 launch blockers in this report.

## Five most important actions

1. **Resolve duplicate and broken public content:** Redirect `/lavender-simple-syrup`, redirect or remove `/harvest-hub`, and repair the two missing guide images.
2. **Complete the trust layer:** Publish a privacy policy, link it next to every newsletter form, describe Kit as the email processor, and obtain owner/legal review of consent language.
3. **Review the plum-jam page with a preservation authority:** Reconcile yield, use a tested formula, add a direct source, and verify altitude instructions before promoting it.
4. **Fix search and seasonal accuracy:** Either implement `?q=` on `/recipes` or remove SearchAction schema; refresh “right now” and “late May” copy.
5. **Reduce image weight and centralize shared site code:** Convert large content images to modern responsive formats and move shared CSS/JS/navigation/footer/form patterns out of 48 separate documents.

---

# 2. Website and Technical Inventory

| Item | Finding |
|---|---|
| Framework | None detected. Static HTML/CSS/JavaScript site. |
| Framework version | Not applicable. |
| Rendering | Server-delivered static HTML with client-side enhancements for menus, FAQs, recipe filtering, and newsletter forms. |
| Public HTML files | 48, including `404.html`, `thank-you.html`, two duplicate/legacy routes, and 44 sitemap-indexable routes. |
| Repository HTML size | 3,220,389 bytes. |
| Inline CSS | 1,571,457 bytes across 45 distinct style blocks. |
| Inline JavaScript | 298,861 bytes across 68 distinct inline script blocks. |
| Image library | 151 files totaling 167,102,300 bytes. |
| Routing | Extensionless links such as `recipes`, served in production by the host’s clean-URL behavior. No routing configuration is checked into the repository. |
| Content sources | Page copy and data are embedded directly in individual HTML files. No CMS, content collection, front matter, database, or shared JSON source. |
| Components | No component layer. Header, navigation, footer, forms, styles, and behavior are copied into pages. |
| Styling | Per-page inline `<style>` blocks; shared palette and typography are repeated manually. |
| Fonts | Google Fonts: Playfair Display, Lora, and DM Mono. |
| JavaScript | Vanilla JavaScript only; no bundle or module system. |
| Build scripts | None. |
| Package manifest | None. |
| Automated tests | None. |
| Lint/type checks | None configured. |
| Environment variables | None detected. |
| Deployment configuration | None checked in. Production responses identify Cloudflare, but the origin/deploy process is not documented in the repository. |
| Analytics | No site analytics or error monitoring detected. Kit’s embedded options explicitly contain null analytics integrations. |
| Forms | 44 Kit newsletter forms posting to form ID `9503567`; no contact form. |
| Form data destination | `https://app.kit.com/forms/9503567/subscriptions`. |
| Spam controls | Kit configuration shows reCAPTCHA disabled. Provider-side protections could not be verified without submitting a form. |
| Search | Client-side recipe search and filters on `/recipes`; no site-wide search. Query parameter `?q=` is ignored. |
| Structured data | WebSite, Organization, Person, Article, BlogPosting, Recipe, HowTo, FAQPage, CollectionPage, and related nodes. |
| Sitemap | 44 URLs. It excludes `thank-you`, `404`, `harvest-hub`, and `lavender-simple-syrup`. |
| Robots | Allows the site, disallows `/search` and `/thank-you`, and names the sitemap. |
| Security review | No committed secret-like credentials found. No unsafe `target="_blank"` links found. Production has `X-Content-Type-Options` and `Referrer-Policy`, but no observed CSP, HSTS, Permissions-Policy, or anti-framing policy. |
| Production caching | Homepage HTML: revalidated on every request. Hero PNG: 4-hour cache and 2,465,986-byte transfer. |

## Architecture assessment

There is a clear conceptual separation in the writing—guides, recipes, blog posts, hubs—but not in the implementation. Layout, components, content, styling, utilities, configuration, and data are all interleaved inside each HTML file. That is workable for a handful of pages but already expensive and error-prone at 48 pages.

The site does not need an enterprise platform. A small static-site generator with shared layouts and Markdown or structured content would provide the needed separation while keeping hosting simple.

---

# 3. Scorecard

| Category | Score | Evidence |
|---|---:|---|
| Brand clarity | 8/10 | The premise and tagline are immediate and memorable. “Herb Hub” versus visible “Harvest Hub” and generic “journey” copy create some drift. |
| Content quality | 7/10 | Guides and recipes are detailed and useful. Seasonal freshness, visible sourcing, yield inconsistency, and impersonal voice reduce trust. |
| User experience | 7/10 | Strong start paths, related content, recipe filters, 404 recovery, and clear content cards. No site-wide search, stale seasonal framing, and missing media create dead moments. |
| Navigation | 8/10 | Primary, dropdown, mobile, and footer navigation work. Two navigation variants and legacy/orphan routes should be consolidated. |
| Mobile readiness | 8/10 | Homepage and lavender guide had no overflow at 390 px; mobile menu and Escape behavior worked. Untested long tables and missing dimensions remain risks. |
| Accessibility | 7/10 | Main landmarks, skip links, focus return, accessible form names, reduced-motion rules on 47 pages, and descriptive links are strong. Missing form consent context, unchanged menu label, 33 missing image dimensions, and no full assistive-technology audit remain. |
| SEO | 7/10 | Broad metadata, sitemap, canonicals, social tags, and schema are strong. Duplicate route, broken SearchAction, 15 overlong metadata pairs, inconsistent authorship, and missing visible dates hold it back. |
| Performance | 4/10 | 167 MB image library, 2.47 MB lazy LCP image, extensive duplicates, and third-party form script on 44 pages. No measured Lighthouse score was available. |
| Technical health | 5/10 | The live site renders and core JS works, but there is no build/test/lint system and bulk-edit markup errors exist on all pages. |
| Security | 7/10 | Small static attack surface, no secrets found, HTTPS, `nosniff`, and safe external-link handling. Security headers and dependency governance for third-party scripts are incomplete. |
| Legal and trust readiness | 4/10 | A detailed disclaimer exists, but no privacy policy, newsletter consent notice, affiliate policy, contact method, or cited/qualified canning review is present. |
| Maintainability | 3/10 | Shared code is copied into 48 files; 45 unique style blocks and 68 script blocks make drift inevitable. |
| Growth readiness | 5/10 | Topic clusters and clean URLs are a good base, but structured content, categories/tags, author/date governance, downloads, analytics, and commerce boundaries are missing. |

---

# 4. Detailed Findings

## FBTB-001 - Duplicate lavender syrup is live at two URLs

- **Category:** SEO / Routing
- **Severity:** High
- **Evidence:** `lavender-simple-syrup.html:8` canonicals to `/recipe-lavender-syrup`; `recipe-lavender-syrup.html:8` uses the same canonical. Both live URLs return 200, share the title “Lavender Simple Syrup | Peace in a Glass,” and share the H1 “Peace in a Glass.” The legacy URL has no `noindex`.
- **File path:** `lavender-simple-syrup.html`, `recipe-lavender-syrup.html`
- **Route/component:** `/lavender-simple-syrup`, `/recipe-lavender-syrup`
- **Why it matters:** A canonical is a hint, not a substitute for consolidation. Duplicate live pages split signals, complicate analytics, and create two maintainable copies.
- **Recommended action:** Choose `/recipe-lavender-syrup` as the permanent URL, add a server-side 301 from the old URL, and remove the duplicate file after the redirect is verified.
- **Estimated effort:** Small
- **Blocks launch:** Yes

## FBTB-002 - Two live guide images return 404

- **Category:** Images / UX
- **Severity:** High
- **Evidence:** `lavender-guide.html:1885` references `images/guides/rosemary-guide-continue-the-garden.jpg`; `lemon-balm-guide.html:2003` references `/images/guides/mint-guide-continue-the-garden.jpg`. Neither file exists. The first production URL returned the branded 404 HTML page.
- **File path:** `lavender-guide.html`, `lemon-balm-guide.html`
- **Route/component:** Related-content image cards
- **Why it matters:** Broken editorial imagery makes otherwise polished guide pages look unfinished and sends a full HTML 404 response into an image element.
- **Recommended action:** Point each card to an existing approved image or add the intended asset; verify natural dimensions and production response type.
- **Estimated effort:** Quick
- **Blocks launch:** Yes

## FBTB-003 - Plum-jam preservation instructions require qualified review

- **Category:** Food Safety / Trust
- **Severity:** High
- **Evidence:** `preserves-plum-jam.html:43` says “5–6 half-pint jars,” while lines 798 and 1021 say “5–6 pints,” and line 1021 also says “8–10 half-pint jars.” The page provides a shelf-stable formula, processing time, altitude adjustment, and one-year storage claim at lines 893–920 without citing a tested recipe. It also offers off-heat additions.
- **File path:** `preserves-plum-jam.html`
- **Route/component:** `/preserves-plum-jam`
- **Why it matters:** Readers may rely on preservation instructions for shelf-stable food. A tested source should govern ingredient ratios, jar sizes, processing time, altitude, and permitted variations.
- **Recommended action:** Have the entire recipe reviewed against a tested source or by a qualified preservation educator. Reconcile yield everywhere, cite the exact tested recipe, separate flavor ideas that are not approved for shelf-stable canning, and link directly to the authority. The National Center for Home Food Preservation’s tested plum-jam recipe is at `https://nchfp.uga.edu/how/make-jam-jelly/jams/plum-jam-without-pectin/`.
- **Estimated effort:** Medium
- **Blocks launch:** Yes, for promoting this page

## FBTB-004 - Structured search action points to behavior that does not exist

- **Category:** SEO / Search
- **Severity:** High
- **Evidence:** `index.html:37–39` declares `https://frombedtobar.com/recipes?q={search_term_string}`. `recipes.html:1875–1877` only listens for user input and never reads `location.search` or `URLSearchParams`. Live testing of `/recipes?q=mint` left the field empty and all 20 cards visible.
- **File path:** `index.html`, `recipes.html`
- **Route/component:** WebSite JSON-LD and recipe search
- **Why it matters:** The site makes an unsupported machine-readable claim and shared/deep search links do not work.
- **Recommended action:** Initialize the recipe search from `q`, filter on load, and optionally keep the URL in sync; or remove SearchAction until supported.
- **Estimated effort:** Small
- **Blocks launch:** Yes

## FBTB-005 - Newsletter data collection lacks a privacy layer

- **Category:** Privacy / Forms
- **Severity:** High
- **Evidence:** 44 pages post email addresses to Kit. No privacy policy exists, no form contains consent/privacy language, and the footer links only to About, Blog, and Disclaimer. The existing disclaimer does not explain subscriber data, retention, processors, rights, or contact.
- **File path:** Representative example `index.html:1393–1419`; repeated on 43 other pages
- **Route/component:** Newsletter form and footer
- **Why it matters:** A user cannot make an informed decision about how their email address will be used. This is a trust gap and may be a compliance gap depending on audience and jurisdiction.
- **Recommended action:** Publish an owner-reviewed privacy policy; add a short plain-language notice and privacy link at every form; identify Kit as the email service provider; clarify double opt-in, unsubscribe, retention, and contact practices.
- **Estimated effort:** Medium
- **Blocks launch:** Yes, before actively collecting/promoting subscriptions

## FBTB-006 - Bulk edit produced malformed image markup on every HTML page

- **Category:** Technical Health / Accessibility
- **Severity:** Medium
- **Evidence:** All 48 HTML files contain markup such as `width="84" height="84" / loading="lazy"`; 56 instances were found. Examples: `index.html:1156`, `index.html:1195`, `basil-guide.html:1481`, and `basil-guide.html:1508`.
- **File path:** All HTML files
- **Route/component:** Image tags
- **Why it matters:** Browsers currently recover, but the markup is invalid, fragile under minification/transformation, and evidence that global edits are not validated.
- **Recommended action:** Correct to valid HTML attribute order, validate all documents, and add an automated HTML/link check.
- **Estimated effort:** Small
- **Blocks launch:** No

## FBTB-007 - Homepage LCP image is oversized and lazy-loaded

- **Category:** Performance
- **Severity:** High
- **Evidence:** `index.html:1189–1195` marks the hero `fetchpriority="high"` but also `loading="lazy"`. The live hero is a 2,465,986-byte PNG. Browser inspection confirmed the hero’s `loading` property is `lazy`.
- **File path:** `index.html`
- **Route/component:** Homepage hero
- **Why it matters:** Lazy-loading the above-the-fold LCP candidate can delay the most important visual; the transfer is large for mobile.
- **Recommended action:** Remove lazy loading from the hero; produce responsive AVIF/WebP sources with a small fallback; preserve explicit dimensions and high fetch priority.
- **Estimated effort:** Small
- **Blocks launch:** Yes, before paid or high-volume promotion

## FBTB-008 - Image library is extremely heavy and duplicated

- **Category:** Performance / Cleanup
- **Severity:** High
- **Evidence:** 151 files total 167.1 MB. Many 1672 x 941 PNGs are 2.2–2.7 MB. Identical files exist in top-level and categorized directories; `herb-hub-hero.png`, `herb-hub.png`, `heroes/herb-hub-hero.png`, and `heroes/herb-hub.png` are byte-identical. Similar duplication affects home, about, blog, drinks, guides, recipes, preserves, syrups, and logo assets.
- **File path:** `images/`
- **Route/component:** Site-wide media
- **Why it matters:** Repository size, deploy time, cache efficiency, image governance, and page weight all suffer.
- **Recommended action:** Build a verified asset manifest, choose one canonical path per image, convert display assets to responsive modern formats, and remove duplicates only after reference and deploy verification.
- **Estimated effort:** Large
- **Blocks launch:** Yes for performance-focused promotion; not for quiet review

## FBTB-009 - Thirty-three image instances lack dimensions

- **Category:** Performance / Layout Stability
- **Severity:** Medium
- **Evidence:** Missing width or height occurs in `how-to-harvest-preserve-basil.html` (6), `how-to-harvest-preserve-lavender.html` (5), `lemon-balm-guide.html` (3), `mint-guide.html` (4), `plum-guide.html` (12), `rosemary-guide.html` (3), and `thyme-guide.html` (3). The total includes the two broken references.
- **File path:** Seven guide files listed above
- **Route/component:** Editorial images and cards
- **Why it matters:** Browsers cannot reserve reliable space, increasing cumulative layout shift.
- **Recommended action:** Add correct intrinsic dimensions and verify responsive CSS.
- **Estimated effort:** Small
- **Blocks launch:** No

## FBTB-010 - Seasonal promise is stale in late July

- **Category:** Content / Trust
- **Severity:** High
- **Evidence:** `garden-tips.html:1315` says “Updated for late May.” Blog posts use late-May timing, and the homepage describes “what’s in season” while featuring spring-led content. There is no visible date system explaining when content was last reviewed.
- **File path:** `garden-tips.html`, `index.html`, `blog-post-1.html` through `blog-post-4.html`
- **Route/component:** Seasonal modules and editorial archive
- **Why it matters:** “Right now” is a core brand promise. Stale seasonal framing quickly undermines credibility.
- **Recommended action:** Either update seasonal modules on a documented cadence or make the language evergreen and zone-aware. Display published and updated dates.
- **Estimated effort:** Medium
- **Blocks launch:** Yes

## FBTB-011 - Fifteen route metadata sets are overlong

- **Category:** SEO
- **Severity:** Medium
- **Evidence:** 15 pages exceed 60 characters for title or 160 for description. Examples: `basil-guide.html` title 74 / description 205; `how-to-harvest-preserve-thyme.html` 80 / 245; `thyme-guide.html` 84 / 257.
- **File path:** Basil, herb/harvest hub, four harvest guides, six herb guides, and three syrup files listed in the route table
- **Route/component:** `<title>` and meta description
- **Why it matters:** Search snippets may truncate and the earlier production report’s statement that these were fixed is no longer accurate.
- **Recommended action:** Write page-specific, natural titles and descriptions within practical display ranges without keyword stuffing.
- **Estimated effort:** Small
- **Blocks launch:** No

## FBTB-012 - Authorship and dates are inconsistent and mostly invisible

- **Category:** Editorial / AI Search / SEO
- **Severity:** Medium
- **Evidence:** Herb guides identify Stephanie in JSON-LD, while blog posts and many recipes name the Organization. Nine recipe schema blocks have no publication date, no recipe has `dateModified`, and no route uses a visible `<time>` element. Users cannot see who tested a recipe or when it was reviewed.
- **File path:** Blog posts, recipes, and guide JSON-LD blocks
- **Route/component:** Byline, publication/update metadata, Recipe/Article schema
- **Why it matters:** Firsthand experience, currentness, and consistent identity are important for human trust and modern answer/search systems.
- **Recommended action:** Establish one author model; display byline, published date, updated date, and “tested/reviewed by” where truthful; make schema match visible content.
- **Estimated effort:** Medium
- **Blocks launch:** No

## FBTB-013 - Primary brand voice is not consistently Stephanie’s first person

- **Category:** Content / Brand
- **Severity:** Medium
- **Evidence:** Nineteen pages contain two or fewer visible first-person tokens after navigation/footer removal, including Bar Essentials, all four blog posts, Garden Tips, Planting Guide, Recipes, several core recipes, and both legacy/system routes. The homepage says “From Bed to Bar began…” instead of speaking personally (`index.html:1213`). “Journey” appears repeatedly despite the owner’s avoidance list.
- **File path:** Site-wide, especially `index.html`, `about.html`, `blog*.html`, `garden-tips.html`, `planting-guide.html`, and older recipe pages
- **Route/component:** Visible editorial copy
- **Why it matters:** The site sometimes reads like a polished content brand rather than Stephanie talking from family experience.
- **Recommended action:** Prioritize homepage, About, blog, Garden Tips, Planting Guide, and top recipes for a restrained voice pass. Add specific family/garden context where true; do not rewrite all pages at once.
- **Estimated effort:** Large
- **Blocks launch:** No

## FBTB-014 - “Herb Hub” route and “Harvest Hub” page identity conflict

- **Category:** Brand / Navigation
- **Severity:** Medium
- **Evidence:** Navigation and URL say Herb Hub; `herb-hub.html:7` title and line 934 H1 say Harvest Hub. `harvest-hub.html` duplicates the same identity.
- **File path:** `herb-hub.html`, `harvest-hub.html`, shared navigation
- **Route/component:** `/herb-hub`, `/harvest-hub`
- **Why it matters:** Visitors and search systems receive two names for the same primary destination.
- **Recommended action:** Choose Herb Hub or Harvest Hub as the public label, use it consistently, and redirect the retired slug.
- **Estimated effort:** Small
- **Blocks launch:** No

## FBTB-015 - Legacy Harvest Hub remains a complete live page

- **Category:** Routing / Cleanup
- **Severity:** Medium
- **Evidence:** `/harvest-hub` returns 200 and is orphaned. It has `noindex, follow` and canonicalizes to `/herb-hub`, but still duplicates an entire page.
- **File path:** `harvest-hub.html`
- **Route/component:** `/harvest-hub`
- **Why it matters:** A redirect gives users and crawlers a clearer permanent signal and removes a second maintenance copy.
- **Recommended action:** Add a 301 to the chosen hub URL, then remove the duplicate file after verification.
- **Estimated effort:** Quick
- **Blocks launch:** No

## FBTB-016 - Shared site code is copied across 48 documents

- **Category:** Maintainability / Architecture
- **Severity:** High
- **Evidence:** 1.57 MB of inline CSS across 45 distinct blocks; 299 KB of inline JS across 68 blocks; complete navigation, newsletter, disclaimer strip, and footer repeated on most pages. Two navigation variants already exist across 36 and 12 pages.
- **File path:** All HTML files
- **Route/component:** Global layout and behavior
- **Why it matters:** Every global change is a multi-file migration. Drift, invalid markup, inconsistent accessibility, and regression risk grow with each new article.
- **Recommended action:** Move to shared layouts/includes and content files in a simple static generator. Keep current visual design; migrate by content type, not by broad redesign.
- **Estimated effort:** Large
- **Blocks launch:** No, but blocks efficient growth

## FBTB-017 - No reproducible validation or deployment contract

- **Category:** Technical Health
- **Severity:** Medium
- **Evidence:** No `package.json`, test suite, lint config, HTML validator config, link checker, image manifest, or deployment config. Clean URL behavior exists only in production and is not documented.
- **File path:** Repository root
- **Route/component:** Development and deployment process
- **Why it matters:** A future contributor cannot reproduce checks or know how extensionless links and redirects are configured.
- **Recommended action:** Add a small documented validation workflow: HTML parse, internal links, image existence, JSON-LD parse, duplicate canonical check, and a production smoke test. Document host and redirect rules.
- **Estimated effort:** Medium
- **Blocks launch:** No

## FBTB-018 - Third-party Kit script is loaded on 44 pages

- **Category:** Performance / Privacy
- **Severity:** Medium
- **Evidence:** `https://f.convertkit.com/ckjs/ck.5.js` is embedded on every page with a form; the current script is about 47 KB before downstream behavior. Kit form configuration has reCAPTCHA disabled and analytics integrations null.
- **File path:** 44 form-bearing HTML pages
- **Route/component:** Newsletter section
- **Why it matters:** The script adds third-party network, privacy, availability, and interaction cost to nearly every page.
- **Recommended action:** Load the provider script only when the form approaches the viewport or use a lightweight native form integration if Kit supports it. Document the processor in the privacy policy.
- **Estimated effort:** Medium
- **Blocks launch:** No

## FBTB-019 - Security headers are incomplete

- **Category:** Security
- **Severity:** Medium
- **Evidence:** Production returned HTTPS, `X-Content-Type-Options: nosniff`, and `Referrer-Policy: strict-origin-when-cross-origin`. No observed Content-Security-Policy, Strict-Transport-Security, Permissions-Policy, or frame restriction.
- **File path:** Hosting configuration, not present in repository
- **Route/component:** Production HTTP responses
- **Why it matters:** A static site has a small attack surface, but a CSP and related headers reduce third-party and injection impact.
- **Recommended action:** Add a report-only CSP first, inventory Google Fonts and Kit requirements, then enforce. Add HSTS after confirming all subdomains are HTTPS. Add a frame policy and minimal Permissions-Policy.
- **Estimated effort:** Medium
- **Blocks launch:** No

## FBTB-020 - No analytics, conversion events, or error monitoring

- **Category:** Analytics / Growth
- **Severity:** Opportunity
- **Evidence:** No analytics provider or error monitor found. Kit’s embedded analytics integrations are null.
- **File path:** Site-wide
- **Route/component:** Measurement
- **Why it matters:** The owners cannot tell which topics create return visits, newsletter signups, broken outbound paths, or client-side errors.
- **Recommended action:** Add a privacy-conscious analytics provider only after the privacy decision. Measure page views, newsletter form starts/success, recipe search use, outbound clicks, 404s, and key downloads. Avoid collecting sensitive or unnecessary data.
- **Estimated effort:** Medium
- **Blocks launch:** No

## FBTB-021 - Recipe search/filter state is not shareable or persistent

- **Category:** UX / Search
- **Severity:** Low
- **Evidence:** Search, type, season, and sort state live only in page variables; URLs do not change and browser reload loses state.
- **File path:** `recipes.html:1766–2001`
- **Route/component:** Recipe finder
- **Why it matters:** Visitors cannot share “mint mocktails” or return to a filtered collection.
- **Recommended action:** After FBTB-004, serialize useful state into query parameters and restore it on load.
- **Estimated effort:** Medium
- **Blocks launch:** No

## FBTB-022 - Homepage uses large inline style and event-handler blocks

- **Category:** Maintainability / Security
- **Severity:** Low
- **Evidence:** `index.html:1249–1311` implements a major seasonal grid with inline CSS plus `onmouseover` and `onmouseout` handlers.
- **File path:** `index.html`
- **Route/component:** Seasonal Harvest
- **Why it matters:** Inline handlers complicate CSP adoption, keyboard parity, reusable styling, and maintenance.
- **Recommended action:** Move the card style and hover/focus behavior to shared classes and CSS.
- **Estimated effort:** Small
- **Blocks launch:** No

## FBTB-023 - Menu state label does not change

- **Category:** Accessibility
- **Severity:** Low
- **Evidence:** Mobile browser testing confirmed `aria-expanded` changes and Escape returns focus, but the button retains `aria-label="Open navigation menu"` while open.
- **File path:** Shared navigation scripts and markup
- **Route/component:** Mobile menu
- **Why it matters:** Screen-reader users receive a slightly inaccurate action label.
- **Recommended action:** Toggle the accessible label between “Open navigation menu” and “Close navigation menu.”
- **Estimated effort:** Quick
- **Blocks launch:** No

## FBTB-024 - No favicon or web manifest

- **Category:** Brand / Polish
- **Severity:** Low
- **Evidence:** No favicon, Apple touch icon, or manifest reference exists in the HTML.
- **File path:** Global head
- **Route/component:** Browser and saved-site identity
- **Why it matters:** Tabs, bookmarks, and mobile shortcuts lose a small but useful brand signal.
- **Recommended action:** Create favicon sizes from the approved mark and reference them globally.
- **Estimated effort:** Small
- **Blocks launch:** No

## FBTB-025 - Asset ownership and licensing are undocumented

- **Category:** Legal / Media
- **Severity:** Opportunity
- **Evidence:** 151 images include polished garden, kitchen, and cocktail scenes, but the repository contains no asset register, source, photographer, model/property release, or AI-generation record.
- **File path:** `images/`
- **Route/component:** Editorial media library
- **Why it matters:** Future products, printables, ads, and commercial partnerships require confidence that images can be reused.
- **Recommended action:** Create a private media register with source, owner, creation date, permitted uses, and release/license notes.
- **Estimated effort:** Medium
- **Blocks launch:** Owner decision

## FBTB-026 - Positive security and link-health result

- **Category:** Security / Technical Health
- **Severity:** Opportunity
- **Evidence:** No committed secret-like credentials were detected; JSON-LD parsed successfully on all pages; no broken internal HTML links were found; no unsafe `_blank` links were found.
- **File path:** Site-wide
- **Route/component:** Repository
- **Why it matters:** The core static surface is relatively small and understandable.
- **Recommended action:** Preserve these checks in the future validation workflow.
- **Estimated effort:** Small
- **Blocks launch:** No

---

# 5. Route-by-Route Review

Legend: **Keep** = retain; **Improve** = retain and remediate; **Redirect** = consolidate to another URL; **System** = functional utility page. “SEO” summarizes readiness, not only metadata presence.

| Route | Page / purpose | Status and content | Navigation / SEO / mobile | Recommendation |
|---|---|---|---|---|
| `/` | Homepage / brand entry | Strong visual identity; seasonal copy is stale; generic third-person story language | Primary nav; strong schema; LCP image risk; mobile tested without overflow | **Improve** - fix hero delivery, seasonal module, voice, and SearchAction |
| `/404` | Recovery page | Branded and useful; concise | Not indexed; recovery links work; no reduced-motion rule | **System / Keep** |
| `/about` | Family and brand story | One of the strongest trust pages; add more verifiable specifics and contact path | Primary/footer nav; AboutPage/Person schema; one decorative image | **Improve** |
| `/bar-essentials` | Equipment guide | Detailed and useful but impersonal | Primary/footer nav; WebPage schema; responsive structure | **Improve** voice and affiliate/disclosure readiness |
| `/basil-guide` | Basil hub | Very deep, specific, family-voiced content | Dropdown/footer; metadata overlong; invalid image markup | **Improve** metadata and validation |
| `/blog` | Blog index | Only four posts; archive is visually complete but not current | Primary/footer nav; CollectionPage schema; visible dates absent | **Improve** freshness and taxonomy |
| `/blog-post-1` | Garden bed cocktail starter | Useful practical evergreen guide with late-May framing | Linked from blog; BlogPosting schema; author Organization | **Improve** byline, visible date, seasonal note |
| `/blog-post-2` | Elderflower syrup | Useful but plant identification and seasonal timing need visible sourcing | Linked from blog; BlogPosting schema | **Improve** safety/source notes and authorship |
| `/blog-post-3` | Five current cocktails | Strong discovery post but “right now” is date-sensitive | Linked from blog; BlogPosting schema | **Improve** visible date and seasonal/zone context |
| `/blog-post-4` | Fresh juice guide | Strong practical content; assertive claims should be softened or sourced | Linked from blog; BlogPosting schema | **Improve** author/date and evidence |
| `/cocktails-garden-mojito` | Mojito recipe | Complete recipe | Recipe collection/internal links; Recipe schema | **Keep / Improve** visible author/date |
| `/cocktails-plum-bourbon-sour` | Plum cocktail | Complete, strong orchard cluster | Recipe links; Recipe schema lacks published date | **Keep / Improve** author/date |
| `/disclaimer` | Legal/safety notice | Thorough alcohol, egg, plant, allergy, liability, copyright sections | Footer/mobile nav; no Privacy or Terms substitutes | **Keep**, then add separate privacy policy |
| `/garden-tips` | Gardening advice and seasonal view | Useful but explicitly “Updated for late May” | Primary/footer nav; WebPage schema; currentness risk | **Improve before promotion** |
| `/harvest-hub` | Legacy duplicate hub | Full duplicate; orphaned; noindex; canonical to Herb Hub | Not in sitemap; still live 200 | **Redirect** to chosen hub URL |
| `/herb-hub` | Main herb discovery hub | Strong guide map; visible name says Harvest Hub | Primary/footer nav; Collection/FAQ schema | **Improve** naming consistency |
| `/how-to-harvest-preserve-basil` | Basil preservation | Strong family/editorial content; 6 images lack dimensions | Internally linked; long metadata | **Improve** dimensions, metadata, source/safety notes |
| `/how-to-harvest-preserve-lavender` | Lavender preservation | Strong content; 5 images lack dimensions; no newsletter form | Internally linked; very long description | **Improve** metadata and dimensions |
| `/how-to-harvest-preserve-mint` | Mint preservation | Detailed and well linked | Linked from mint cluster; strong schema | **Keep / Improve** visible author/date |
| `/how-to-harvest-preserve-plums` | Plum harvest/preserve | Detailed orchard cluster content | Strong internal links and schema | **Keep / Improve** sources and dates |
| `/how-to-harvest-preserve-rosemary` | Rosemary preservation | Deep content; one decorative/related image lacks useful alt | Linked from rosemary cluster; long metadata | **Improve** metadata and image review |
| `/how-to-harvest-preserve-thyme` | Thyme preservation | Deep content; 3 images lack dimensions | Linked from thyme cluster; very long metadata | **Improve** metadata and dimensions |
| `/lavender-guide` | Lavender hub | Strong editorial guide; one related image is broken | Dropdown/footer; metadata overlong | **Improve before promotion** |
| `/lavender-simple-syrup` | Duplicate lavender syrup | Substantially duplicates canonical recipe | Orphaned; not in sitemap; live 200; no noindex | **Redirect** to `/recipe-lavender-syrup` |
| `/lemon-balm-guide` | Lemon balm hub | Strong, personal guide; one related image broken | Dropdown/footer; metadata overlong | **Improve before promotion** |
| `/mint-guide` | Mint hub | One of the strongest pages; very deep and personal | Dropdown/footer; 4 images lack dimensions; metadata long | **Improve** metadata/dimensions |
| `/mocktails-sparkling-mint-limeade` | Mint mocktail | Complete and approachable | Recipe collection/internal links; Recipe schema | **Keep / Improve** visible author/date |
| `/mocktails-sparkling-plum-mocktail` | Plum mocktail | Complete and well connected | Plum cluster; Recipe schema | **Keep / Improve** visible author/date |
| `/planting-guide` | Cocktail-garden guide | Very detailed but impersonal and hard to maintain in one HTML file | Primary/footer nav; HowTo schema; no visible update date | **Improve** voice, date, and structure |
| `/plum-guide` | Plum hub | Richest topic cluster; strong practical material | Dropdown/footer; 12 images lack dimensions; metadata long | **Improve** dimensions and metadata |
| `/preserves-plum-jam` | Shelf-stable plum jam | Useful but yield conflicts and canning authority review required | Strong plum links; Recipe schema conflicts with visible yield | **Improve before promotion** |
| `/recipe-basil-syrup` | Basil syrup | Strong personal/editorial content | Recipe cluster; metadata description long | **Improve** metadata/date-modified |
| `/recipe-cucumber-mint-gin-tonic` | Cocktail recipe | Complete, detailed, and useful | Recipes index; Recipe/FAQ schema; no published date | **Keep / Improve** authorship/date |
| `/recipe-garden-herb-gimlet` | Cocktail recipe | Complete and useful | Homepage/recipes; Recipe/FAQ schema; no published date | **Keep / Improve** authorship/date |
| `/recipe-hibiscus-paloma` | Cocktail recipe | Complete and detailed | Recipes index; Recipe/FAQ schema; no published date | **Keep / Improve** source and authorship |
| `/recipe-lavender-lemon-spritz` | Seasonal cocktail | Strong seasonal recipe | Homepage/recipes; Recipe/FAQ schema; no published date | **Keep / Improve** visible date/season |
| `/recipe-lavender-syrup` | Canonical lavender syrup | Strong personal content | Internal links; Recipe/FAQ schema; duplicate legacy route | **Keep** after redirecting duplicate |
| `/recipe-mint-simple-syrup` | Mint syrup | Complete but impersonal | Mint/plum clusters; Recipe schema | **Improve** voice and visible authorship |
| `/recipe-peach-honey-bourbon-smash` | Cocktail recipe | Complete and detailed | Recipes index; Recipe/FAQ schema; no published date | **Keep / Improve** author/date |
| `/recipe-plum-simple-syrup` | Plum syrup | Strong cluster support; minimal personal voice | Plum cluster; Recipe schema | **Improve** voice and visible date |
| `/recipe-rosemary-bourbon-sour` | Cocktail recipe | Complete and useful | Homepage/recipes; Recipe/FAQ schema; no published date | **Keep / Improve** author/date |
| `/recipe-rosemary-syrup` | Rosemary syrup | Personal notes help brand voice | Rosemary cluster; one image alt string contains stray `width=` text | **Improve** markup/alt and dates |
| `/recipe-strawberry-basil-smash` | Cocktail recipe | Complete and useful | Recipes/blog cluster; Recipe/FAQ schema; no published date | **Keep / Improve** author/date |
| `/recipe-thyme-syrup` | Thyme syrup | Strong Stephanie note and useful variations | Thyme/rosemary cluster; title omits brand suffix | **Improve** title consistency and dates |
| `/recipes` | Recipe index/search/filter | Strong collection and 20 cards; query deep links fail | Primary/footer; Collection/ItemList schema; one H2 only | **Improve before promotion** |
| `/rosemary-guide` | Rosemary hub | Rich, personal, well organized | Dropdown/footer; 3 image-dimension issues; metadata long | **Improve** metadata/images |
| `/thank-you` | Newsletter confirmation | Clear utility page | Noindex and disallowed; intentional conversion destination | **System / Keep** and measure success |
| `/thyme-guide` | Thyme hub | Rich and personal | Dropdown/footer; 3 images lack dimensions; longest description | **Improve** metadata/images |

## Orphan and routing summary

- **Intentional/acceptable orphan:** `/thank-you` is reached through Kit’s external redirect.
- **Legacy orphan:** `/harvest-hub` should redirect.
- **Duplicate orphan:** `/lavender-simple-syrup` should redirect.
- **Broken navigation links:** None detected among internal HTML links.
- **Navigation links without local destinations:** None detected.
- **Draft content visibly exposed:** No explicit “draft” flags found, but “Video coming soon” appears on homepage cards.

---

# 6. Content and Brand Review

## Strong content

- The mint, basil, rosemary, thyme, lavender, lemon balm, and plum hubs contain specific growing, harvesting, storage, and usage details.
- The plum cluster demonstrates an excellent topic model: grow the fruit, harvest it, preserve it, make syrup, make a cocktail, and offer a nonalcoholic version.
- Small practical statements—contain mint, harvest before bolting, store basil stems in water, use fresh citrus—make the site useful.
- Family phrases in newer guide and syrup pages feel closest to the desired voice.
- The disclaimer is unusually thoughtful for an early site and covers alcohol, raw egg, plant identification, medication, allergies, and copyright.

## Weak or risky content

- Seasonal words such as “right now,” “this week,” and “late May” have no visible date context.
- Several older pages speak in an anonymous authority voice rather than Stephanie’s lived first person.
- “Journey” is overused and appears prominently on the homepage despite the avoidance list.
- Some claims are absolute: “hard to kill,” “there is no excuse,” “everything it touches,” “works across almost every category.” These can feel generic or overconfident.
- Canning and foraging pages do not consistently link the reader to primary authorities.
- Blog posts identify the organization as author in schema, weakening the family-person identity.

## Missing content

- Privacy policy
- Contact method
- Visible author biographies/bylines on articles and recipes
- Visible publication and update dates
- Clear editorial/testing policy for recipes and preservation instructions
- Zone/location context for seasonal recommendations
- Image and recipe source register
- Affiliate/ad policy before monetization
- Terms/site-use notice if the owners want one separate from the disclaimer

## Representative voice recommendations

Do not rewrite the whole site. Start with the pages that establish identity:

- **Homepage:** Replace “From Bed to Bar began with a desire…” with a truthful first-person family detail.
- **About:** Add concrete place, family routine, garden scale, or origin detail that Stephanie approves.
- **Blog:** Add “By Stephanie,” the date, and one sentence grounding each post in what was actually happening in the family garden.
- **Garden Tips:** State the location/zone or explain how readers should translate timing to their own climate.
- **Recipes:** Add a brief “why we make this” or “what happened at our table” note only where genuine.

## Repetitive language and structures

- “Garden-to-glass” is central and appropriate, but appears so often that secondary phrases should carry more of the writing.
- “Journey” is repeated in the homepage brand story and start-here content.
- Newsletter and responsibility copy is repeated almost verbatim across 43–44 pages.
- Many pages share the same architecture: eyebrow, large headline, generalized introduction, card grid, newsletter, responsibility strip. Shared layout is good; repeated generic introductions are not.

## Topic gaps

- A clear “start here by season” page
- Nonalcoholic collection independent of cocktail alternatives
- A tested-preservation resource page with primary sources
- Family hospitality stories beyond recipes
- Searchable categories: herb, fruit, syrup, preserve, cocktail, mocktail, season
- “What we are growing now” with a date and location/zone
- Printable guide strategy with version dates

## Internal-linking opportunities

- Add breadcrumb paths to guides and recipes and matching BreadcrumbList schema.
- Link every ingredient-focused recipe back to its growing/harvest guide.
- Create permanent seasonal collection pages rather than changing undated “right now” modules.
- Link blog posts to the relevant hub and recipe cards with descriptive anchor text.
- Provide “next best page” at the end of every article before the newsletter.

---

# 7. Technical Debt and Cleanup

## Dead or duplicate files

- `lavender-simple-syrup.html` duplicates the canonical recipe.
- `harvest-hub.html` duplicates the main hub.
- Many images are byte-identical across top-level and categorized folders.
- Two zero-byte files exist: `images/thyme-rosemary-syrup.jpeg` and `images/tomato-water-bloody-mary.jpeg`.
- Several `.gitkeep` files remain in populated asset directories; harmless but unnecessary.

## Unused assets

Static reference analysis found numerous unused duplicates and alternates, including top-level hero images, category duplicates, and older recipe copies. Do not delete solely from this list: CSS background URLs, social URLs, and future/draft use need a final manifest review. The clearest cleanup candidates are byte-identical duplicates and zero-byte files after production references are verified.

## Duplicate patterns

- Global navigation and dropdown
- Mobile navigation behavior
- Footer groups
- Newsletter provider script and form
- Responsibility strip
- Font links
- Print rules
- Reduced-motion rules
- Color tokens and typography
- FAQ toggles

## Structural inconsistencies

- 36 pages use the full dropdown navigation variant; 12 recipe-oriented pages use a shorter variant.
- Image paths mix top-level and categorized directory structures.
- Some pages use Organization authors, others Person/Stephanie.
- Some recipe schema blocks use `@graph`; others embed standalone `@context`.
- Some content pages have forms; two newer harvest pages do not.
- Titles use both full brand suffixes and route-specific variations.

## Simplification opportunity

Use a small static generator and keep the current front end:

```text
site config
  -> shared head / navigation / footer / newsletter
  -> content collections (guides, recipes, posts, pages)
  -> shared design tokens and components
  -> generated HTML, sitemap, feeds, schema, and redirects
```

This is sufficient for the foreseeable site. A headless CMS or enterprise commerce stack is unnecessary now.

---

# 8. Launch Readiness

## Must complete before public promotion

1. FBTB-001 - Redirect the duplicate lavender syrup route.
2. FBTB-002 - Repair the two missing guide images.
3. FBTB-003 - Review and reconcile the plum-jam preservation page.
4. FBTB-004 - Implement query search or remove SearchAction.
5. FBTB-005 - Publish privacy/consent information before promoting signups.
6. FBTB-007 - Correct homepage hero loading and reduce its file size.
7. FBTB-010 - Refresh or reframe seasonal content.

## Should complete within 30 days

- Correct malformed image markup.
- Add image dimensions to the seven affected guides.
- Shorten 15 metadata sets.
- Establish visible author/date/update fields.
- Redirect the legacy Harvest Hub.
- Add a minimal validation workflow and deployment documentation.
- Begin image deduplication and responsive conversion.
- Add CSP in report-only mode and review other security headers.
- Add privacy-conscious analytics after the privacy decision.

## Can complete later

- Static-generator migration by content type
- Shareable filter URLs beyond basic `q`
- Favicon and manifest
- Breadcrumb UI and schema
- Media-rights register
- Printable guide versioning
- Categories, tags, author archive, and update archive
- Affiliate and commerce modules after owner policy decisions

---

# 9. Prioritized Remediation Roadmap

## Phase 1 - Stabilize

| Priority | Exact scope | Relevant files | Dependencies | Expected outcome | Effort | Validation |
|---:|---|---|---|---|---|---|
| P0 | Redirect old lavender syrup URL | Host redirects, `lavender-simple-syrup.html` | Owner confirms canonical URL | One permanent recipe URL | Small | Check 301, final URL, sitemap, canonical |
| P0 | Repair two missing images | `lavender-guide.html`, `lemon-balm-guide.html`, approved assets | Owner approves replacements | No broken editorial media | Quick | Local reference scan and live 200/image MIME |
| P0 | Preservation review and yield reconciliation | `preserves-plum-jam.html` | Owner plus qualified preservation source/reviewer | Trustworthy, consistent canning page | Medium | Compare every ratio/time/yield to cited tested source |
| P0 | Make `?q=` work or remove SearchAction | `index.html`, `recipes.html` | None | Honest structured search behavior | Small | Load `/recipes?q=mint`; verify field/cards/schema |
| P0 | Add privacy policy and form notices | New privacy page, all forms/footer | Owner/legal/privacy decisions | Informed newsletter signup | Medium | Link scan; keyboard/mobile review; owner signoff |
| P0 | Fix homepage LCP image | `index.html`, hero asset(s) | Approved image conversion | Faster first visual | Small | Confirm no lazy attribute; test responsive sources |
| P0 | Refresh seasonal promises | `index.html`, `garden-tips.html`, `blog*.html` | Stephanie/Steve content decision | Current or evergreen seasonal framing | Medium | Owner review and date/zone check |
| P1 | Redirect legacy Harvest Hub | Host redirects, `harvest-hub.html`, `herb-hub.html` | Naming decision | One hub name and URL | Quick | 301 test; canonical/sitemap check |

## Phase 2 - Strengthen

| Priority | Exact scope | Relevant files | Dependencies | Expected outcome | Effort | Validation |
|---:|---|---|---|---|---|---|
| P1 | Correct malformed image tags | All 48 HTML files | Clean Git checkpoint | Valid, predictable markup | Small | HTML parser/validator; visual spot checks |
| P1 | Add 33 missing image dimensions | Seven guide files | Asset dimensions | Lower CLS risk | Small | Automated dimension scan |
| P1 | Shorten overlong metadata | 15 affected routes | Owner keyword/voice review | Cleaner search snippets | Small | Length report and uniqueness check |
| P1 | Standardize author/date/update model | Guides, recipes, blog posts, About | Stephanie’s approved author bio | Better trust and AI/search clarity | Medium | Visible/schema parity check |
| P1 | Convert high-impact images | Homepage, hubs, top recipes | Approved visual QA | Lower page weight | Large | Byte budget, responsive screenshots, Lighthouse |
| P1 | Add validation workflow | Repository tooling/docs | Tool choice | Repeatable quality gate | Medium | Intentionally fail each check once |
| P2 | Add security headers | Cloudflare/host config | Host access; Kit/font allowlist | Reduced browser risk | Medium | Header scan and CSP report review |
| P2 | Add privacy-conscious measurement | Global layout/host | Privacy policy and provider choice | Useful launch data | Medium | Real-time event test without PII |

## Phase 3 - Grow

| Priority | Exact scope | Relevant files | Dependencies | Expected outcome | Effort | Validation |
|---:|---|---|---|---|---|---|
| P2 | Introduce shared static layouts | Site-wide | Phase 1 clean state | One source for global code | Large | Full route diff and regression test |
| P2 | Move content into collections | Recipes, guides, posts | Layout migration | Easier taxonomy, dates, authors, feeds | Large | Schema/content parity check |
| P2 | Add category/season/tag pages | Generated collections | Structured content | Better discovery and internal linking | Large | Route inventory and noindex rules |
| P2 | Create printable guide system | Selected guides | Version/date/content review | Consistent downloads and lead magnets | Medium | Print QA and version metadata |
| P3 | Prepare affiliate/product policy | Bar Essentials and future store | Owner/legal decisions | Transparent monetization | Medium | Disclosure placement review |
| P3 | Add lightweight commerce only when needed | Future products/downloads | Product and fulfillment decisions | Growth without premature complexity | Large | Purchase/privacy/refund flow test |

---

# 10. Quick Wins

The ten highest-value changes likely under two hours each:

1. Remove `loading="lazy"` from the homepage hero and preserve high priority.
2. Repair the two missing guide image references.
3. Add a redirect for `/harvest-hub`.
4. Add a redirect for `/lavender-simple-syrup`.
5. Remove SearchAction until query-based search works.
6. Reconcile the three conflicting plum-jam yield statements pending full safety review.
7. Change “Updated for late May” to current, dated, zone-aware copy.
8. Correct the 56 malformed `/ loading=` image tags.
9. Toggle the mobile menu label between Open and Close.
10. Add approved favicon assets and global references.

---

# 11. Questions Requiring Owner Decisions

1. Is the public hub name **Herb Hub** or **Harvest Hub**?
2. Is `/recipe-lavender-syrup` the permanent lavender syrup URL?
3. Who is the named author: Stephanie alone, Stephanie and Steve, or the From Bed to Bar organization?
4. What truthful location or growing-zone detail can be published?
5. How often can the family realistically refresh seasonal modules?
6. Should seasonal content be live-updated, date-stamped, or written evergreen by zone?
7. Who will perform the qualified review of canning and preservation instructions?
8. Are all images family-owned, licensed, commissioned, or AI-generated, and where are those records?
9. What data does the newsletter collect beyond email, how long is it kept, and which Kit settings are enabled?
10. Is double opt-in enabled in Kit?
11. What contact address or form should privacy, copyright, and correction requests use?
12. Will the site use affiliate links or advertising in the next year?
13. Which analytics tradeoff is acceptable: no tracking, simple privacy-conscious traffic, or fuller event analytics?
14. Should “Video coming soon” remain visible before a video schedule exists?
15. Which pages are already approved copy and must not receive a voice edit?
16. Is the site intended only for U.S. readers, or should alcohol/privacy language support a wider audience?
17. What future product is most likely first: printable guide, journal, digital download, affiliate collection, or physical product?

---

# 12. Minimal Measurement Plan

After the privacy decision, use the smallest plan that answers business questions:

| Question | Event / dimension |
|---|---|
| What content attracts readers? | Page view by route and content type |
| What keeps them exploring? | Internal related-content click |
| What do they want? | Recipe search term category, with no personal data |
| What builds an audience? | Newsletter form view, start, success |
| Where are dead ends? | 404 route/referrer and client error |
| What may lead to revenue? | Download and outbound affiliate click, clearly disclosed |

Do not send email addresses, recipe notes, exact form field values, or unnecessary identifiers to analytics.

---

# 13. Future Readiness

## Suitable with modest restructuring

- Larger article library
- Herb and ingredient guides
- Recipe and seasonal collections
- Printables and journals
- Email newsletters
- Digital downloads
- Affiliate links
- Author and updated-date pages
- Search, categories, and tags

## Not yet ready without policy and architecture work

- Physical-product store
- Customer accounts
- Personalized recommendations
- Paid membership
- Large-scale ad network
- Multiple authors without editorial workflow

The recommended path is intentionally simple: static content collections, shared layouts, generated metadata/schema, a media manifest, and a documented deploy/redirect process.

---

# 14. Confirmed Positives and Items Not Verified

## Confirmed positives

- No broken internal page links detected.
- No exposed credentials detected.
- All JSON-LD blocks parsed as JSON.
- All HTML pages have an H1, main landmark, and skip link.
- Mobile homepage and lavender guide had no horizontal overflow at 390 px.
- Mobile navigation opened, updated `aria-expanded`, closed on Escape, and returned focus.
- Production uses HTTPS and Cloudflare.
- Thank-you and 404 pages are noindex.
- `thank-you` is disallowed in robots.
- Sitemap contains 44 intended indexable canonical routes.

## Not verified

- Actual email delivery, double opt-in, spam protection, provider retention, or subscriber deletion flow
- Form error messages with real provider responses
- Full WCAG 2.2 AA conformance with screen readers and keyboard-only testing on every route
- Color contrast for every state and image-overlay combination
- Measured Lighthouse or field Core Web Vitals
- Production redirect configuration because none is checked in
- Copyright, releases, or license status of images
- Legal sufficiency of disclaimer/privacy language
- Food-safety validity of preservation content
- Cloudflare account configuration, origin configuration, backups, or deploy rollback

---

# 15. Recommended Next Codex Prompt - Phase 1 Only

```text
Implement Phase 1 of the From Bed to Bar website audit only.

Use FROM_BED_TO_BAR_FULL_WEBSITE_AUDIT.md as the source of truth. Address these findings:

- FBTB-001: duplicate lavender syrup route
- FBTB-002: two broken guide images
- FBTB-003: plum-jam preservation review and yield consistency
- FBTB-004: unsupported recipe SearchAction / ?q= behavior
- FBTB-005: newsletter privacy and consent layer
- FBTB-007: homepage LCP image delivery
- FBTB-010: stale seasonal framing
- FBTB-015: legacy Harvest Hub redirect, after the owner naming decision

Before changing anything:

1. Confirm the worktree state.
2. Create a clean Git checkpoint or backup. Do not overwrite uncommitted owner work.
3. Ask for only the owner decisions that materially block Phase 1:
   - permanent lavender URL
   - Herb Hub versus Harvest Hub
   - approved replacement images
   - privacy-policy facts and contact method
   - qualified preservation source/reviewer decision
   - current seasonal wording or update cadence
4. Preserve all approved content and visuals unless a finding specifically requires a change.

Implementation rules:

- Work in small, reviewable batches.
- Validate after every batch.
- Do not perform a broad redesign.
- Do not upgrade dependencies unnecessarily.
- Do not migrate frameworks in Phase 1.
- Do not invent legal, privacy, family, or food-safety facts.
- Do not publish an unreviewed canning formula.
- Use permanent server-side redirects where the host supports them; document any host configuration.
- Keep the canonical route in the sitemap and remove duplicate URLs.
- For search, either correctly initialize from ?q= and verify the filtered state or remove SearchAction until it is supported.
- For the homepage hero, retain the approved image composition and dimensions while removing lazy loading and supplying optimized responsive formats.

Required validation:

- Internal link and image scan
- JSON-LD parse and canonical/sitemap comparison
- Desktop and 390 px mobile visual checks
- Mobile menu keyboard check
- Live or preview redirect checks
- /recipes?q=mint behavior check if SearchAction remains
- Newsletter form accessible-name and privacy-link check without submitting real data
- Production/preview content-type check for repaired images

At the end, produce an implementation summary containing:

- Findings completed
- Files changed
- Owner decisions applied
- Validation results
- Anything deferred and why
- Rollback/checkpoint reference
```

---

## Appendix A - Primary Evidence References

- Current homepage source: `index.html`
- Recipe search: `recipes.html:1766–2001`
- Lavender duplicate canonical: `lavender-simple-syrup.html:8`
- Canonical lavender recipe: `recipe-lavender-syrup.html:8`
- Legacy hub indexing: `harvest-hub.html:9–10`
- Broken rosemary card image: `lavender-guide.html:1885`
- Broken mint card image: `lemon-balm-guide.html:2003`
- Plum-jam schema yield: `preserves-plum-jam.html:43`
- Plum-jam visible yield and process: `preserves-plum-jam.html:798`, `893–920`, `1021`
- Newsletter example: `index.html:1393–1419`
- Existing disclaimer: `disclaimer.html:914–1027`
- Seasonal stale date: `garden-tips.html:1315`
- National Center for Home Food Preservation, tested plum jam: `https://nchfp.uga.edu/how/make-jam-jelly/jams/plum-jam-without-pectin/`

## Appendix B - Asset Facts

- Total image files: 151
- Total image bytes: 167,102,300
- Largest files: approximately 2.4–2.7 MB each
- Zero-byte files:
  - `images/thyme-rosemary-syrup.jpeg`
  - `images/tomato-water-bloody-mary.jpeg`
- Missing referenced files:
  - `images/guides/rosemary-guide-continue-the-garden.jpg`
  - `images/guides/mint-guide-continue-the-garden.jpg`
- Image instances lacking width or height: 33
- Files containing malformed image-loading markup: 48
- Malformed image-loading instances: 56

## Appendix C - Print Review Checklist

Use this checklist when reviewing the PDF:

- [ ] Confirm the permanent hub name
- [ ] Confirm the permanent lavender syrup URL
- [ ] Mark approved versus editable copy
- [ ] Assign a preservation reviewer
- [ ] Decide privacy-policy facts and contact method
- [ ] Decide seasonal update cadence
- [ ] Identify approved replacement images
- [ ] Choose the first seven Phase 1 tasks
- [ ] Assign owner and target date to each
