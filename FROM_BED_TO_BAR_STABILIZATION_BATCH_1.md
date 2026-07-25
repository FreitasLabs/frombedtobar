# From Bed to Bar — Stabilization Batch 1 Completion Report

**Completed:** July 25, 2026  
**Branch:** `codex/stabilization-batch-1`  
**Scope:** FBTB-001, FBTB-002, FBTB-004, FBTB-006, FBTB-007, FBTB-009, and FBTB-023; FBTB-015 route consolidation deferred after owner review  
**Result:** The approved technical corrections were implemented. The Harvest Hub legacy route was restored, its redirect was removed, visible hub labels were standardized, and its two remaining technical exceptions were corrected without changing page content, route, metadata, or visual appearance. No implementation commit or production deployment was made.

## Checkpoint and Rollback Reference

- The tracked worktree was clean before editing.
- Pre-existing untracked owner work was preserved:
  - `FROM_BED_TO_BAR_FULL_WEBSITE_AUDIT.md`
  - `output/`
- A dedicated branch, `codex/stabilization-batch-1`, was created before implementation.
- The exact rollback baseline is commit:
  - `ff4451abcfb4a5829afdeafff8a283a63d7f3671`
- No implementation commit was created as part of this batch. To inspect the rollback baseline without discarding work, compare the branch against the commit above.

## Batch A — Redirect Consolidation

### Implementation

A root-level Cloudflare Pages redirect file was added:

- `_redirects`

It contains one permanent redirect:

```text
/lavender-simple-syrup /recipe-lavender-syrup 301
```

This is the current Cloudflare Pages-supported static redirect mechanism. The repository has no Pages Functions, framework build, or other redirect configuration that would supersede `_redirects`. Cloudflare Pages reads this file from the deployed static output directory.

The duplicate lavender source file was removed only after its redirect passed in the Cloudflare Pages local runtime:

- Deleted `lavender-simple-syrup.html`

After owner review, the proposed Harvest Hub redirect was reversed:

- Restored `harvest-hub.html` exactly from rollback baseline `ff4451abcfb4a5829afdeafff8a283a63d7f3671`.
- Removed `/harvest-hub /herb-hub 301` from `_redirects`.
- Deferred the permanent route decision for FBTB-015.
- Standardized visible site labels to **Harvest Hub** while retaining links to `/herb-hub`.
- Kept both `harvest-hub.html` and `herb-hub.html`.
- Left both pages' canonical, Open Graph, and JSON-LD URL values pointing to `/herb-hub`.
- Left the sitemap with `/herb-hub` as its only hub entry.

Following conditional review, two narrowly scoped technical corrections were then applied to the restored legacy page: one malformed image tag was repaired and the mobile-menu accessible label was synchronized with open/closed state. No page content, route, canonical, Open Graph, JSON-LD, or visual styling changed.

### Validation

- Cloudflare Wrangler parsed **1 valid redirect rule**.
- `/lavender-simple-syrup` returned `301` with destination `/recipe-lavender-syrup`.
- `/harvest-hub` returned `200 text/html` without a redirect.
- `/herb-hub` returned `200 text/html`.
- `recipe-lavender-syrup.html` retains its self-referencing canonical.
- `herb-hub.html` retains its self-referencing canonical.
- The restored `harvest-hub.html` declares `/herb-hub` as canonical, matching the baseline.
- `sitemap.xml` already contained only `/recipe-lavender-syrup` and `/herb-hub`; no sitemap edit was required.

## Batch B — Broken Guide Images

### Lavender guide

- File: `lavender-guide.html`
- Removed missing reference:
  - `images/guides/rosemary-guide-continue-the-garden.jpg`
- Replacement approved existing asset:
  - `images/guides/rosemary-guide-beyond-the-herb-bed.jpg`
- Actual and declared dimensions:
  - `1536 × 864`
- Loading:
  - `loading="lazy"`
- Alt text:
  - `Rosemary growing near a rustic garden path in warm afternoon light`
- Preview response:
  - `200 image/jpeg`

### Lemon-balm guide

- File: `lemon-balm-guide.html`
- Removed missing reference:
  - `/images/guides/mint-guide-continue-the-garden.jpg`
- Replacement approved existing asset:
  - `/images/guides/mint-guide-from-our-garden.jpg`
- Actual and declared dimensions:
  - `1672 × 941`
- Loading:
  - `loading="lazy"`
- Alt text:
  - `Fresh mint growing in a galvanized container in warm garden light`
- Preview response:
  - `200 image/jpeg`

Both replacements were manually reviewed in their three-card guide layouts at desktop width. The approved layout and card composition were preserved.

## Batch C — Recipe Query Search

`recipes.html` now initializes its existing search controls from the `q` query parameter using `URLSearchParams`.

Implementation behavior:

- Reads the first `q` value on `DOMContentLoaded`.
- Trims leading and trailing whitespace.
- Assigns the query to the search input through the input’s `value` property.
- Normalizes the filtering value to lowercase.
- Runs the existing filtering function on initial load.
- Leaves empty or missing values unfiltered.
- Keeps the existing manual input, clear button, filter chips, sort controls, results count, and no-results state.
- Does not place query text into HTML and does not use `innerHTML`.
- Adds no framework or dependency.
- Keeps the existing SearchAction structured data unchanged.

### Browser results

| Route | Input initialized | Visible results |
|---|---:|---:|
| `/recipes` | empty | 20 of 20 |
| `/recipes?q=mint` | `mint` | 6 of 20 |
| `/recipes?q=lavender` | `lavender` | 2 of 20 |
| `/recipes?q=plum` | `plum` | 4 of 20 |
| `/recipes?q=nonexistent` | `nonexistent` | 0 of 20 |
| Encoded `mint & <script>alert(1)</script>` query | decoded only into input value | 0 of 20; no execution or error |

Additional interaction checks:

- Manual `MiNt` search returned the same 6 results, confirming case-insensitive matching.
- The clear control restored the unfiltered state.
- The existing Mint filter chip continued to return 6 results.
- Browser console warnings/errors: **0**.

## Batch D — Image Markup and Dimensions

### Malformed tags

- **55 malformed tags were corrected** in the retained HTML pages, including the restored `harvest-hub.html`.
- The deleted lavender legacy source accounted for one additional original occurrence.
- Total audited malformed patterns eliminated from the deployable site: **56**.
- Repository-wide final result for `/ loading=`: **0 matches**.

The correction moved `loading="lazy"` inside each valid image start tag without changing the rendered image, surrounding copy, or CSS.

### Intrinsic dimensions

The audit’s per-file counts total 36 affected image elements even though its headline reported 33. All **36 affected image elements** now have valid measured dimension pairs, adding **72 intrinsic-dimension attributes** where the dimensions were missing or malformed.

Affected files:

| File | Image elements corrected |
|---|---:|
| `how-to-harvest-preserve-basil.html` | 6 |
| `how-to-harvest-preserve-lavender.html` | 5 |
| `lemon-balm-guide.html` | 3 |
| `mint-guide.html` | 4 |
| `plum-guide.html` | 12 |
| `rosemary-guide.html` | 3 |
| `thyme-guide.html` | 3 |
| **Total** | **36** |

The two repaired broken-image references were also checked against their real file dimensions. No targeted image uses invented dimensions. A repository-wide structural scan now finds no `<img>` element missing either `width` or `height`.

## Batch E — Homepage Hero

### Loading correction

The homepage hero:

- No longer has `loading="lazy"`.
- Retains `fetchpriority="high"`.
- Retains the approved `1672 × 941` original fallback dimensions.
- Retains the approved original source:
  - `images/og-image.PNG`
- Retains the same crop, object position, overlay, text, CTAs, and composition.

### Responsive delivery

The hero is now delivered through a `<picture>` element:

1. AVIF responsive sources
2. WebP responsive fallback sources
3. Existing PNG original as the final fallback

Generated files:

- `images/heroes/home-hero-640.avif`
- `images/heroes/home-hero-1024.avif`
- `images/heroes/home-hero-1672.avif`
- `images/heroes/home-hero-640.webp`
- `images/heroes/home-hero-1024.webp`
- `images/heroes/home-hero-1672.webp`

### Byte sizes

| Asset | Bytes | Reduction from original |
|---|---:|---:|
| Original PNG fallback | 2,465,986 | — |
| AVIF 640 | 49,112 | 98.0% |
| AVIF 1024 | 105,701 | 95.7% |
| AVIF 1672 | 213,806 | 91.3% |
| WebP 640 | 64,162 | 97.4% |
| WebP 1024 | 136,402 | 94.5% |
| WebP 1672 | 274,764 | 88.9% |

Visual comparison found no visible composition degradation. Full-size fidelity checks measured approximately:

- WebP: `39.68 dB`
- AVIF: `40.25 dB`

Cloudflare preview responses:

- AVIF: `200 image/avif`
- WebP: `200 image/webp`

The browser selected the responsive AVIF source at both tested viewport widths.

## Batch F — Mobile Menu Accessible Label

All 47 retained HTML pages now:

- Initialize the button as `aria-label="Open navigation menu"`.
- Change it to `Close navigation menu` when open.
- Restore `Open navigation menu` when closed.
- Keep `aria-expanded` synchronized.
- Close on Escape.
- Return focus to the menu button after Escape.
- Preserve the current hamburger appearance and menu classes.

Browser interaction checks covered both navigation implementations:

- Full dropdown navigation on the homepage.
- Alternate recipe navigation on `/recipes`.

The homepage mobile check confirmed:

- Initial label: Open.
- Activated label: Close.
- `aria-expanded`: `false → true`.
- Escape closes the menu.
- `aria-expanded`: returns to `false`.
- Label returns to Open.
- Focus returns to the button.

After the conditional review, the same interaction was repeated specifically on the restored `/harvest-hub` page at 390-pixel width:

- Initial label: `Open navigation menu`.
- Activated label: `Close navigation menu`.
- `aria-expanded`: `false → true`.
- Escape closed the menu.
- Label and `aria-expanded` returned to their initial values.
- Focus returned to the menu button.
- Browser console warnings/errors: **0**.

The accessibility implementation also included a beneficial adjacent expansion: 12 recipe, cocktail, and mocktail pages gained Escape-key closure and explicit focus return in addition to the requested label toggle. Those files are:

- `cocktails-garden-mojito.html`
- `cocktails-plum-bourbon-sour.html`
- `mocktails-sparkling-mint-limeade.html`
- `mocktails-sparkling-plum-mocktail.html`
- `recipe-cucumber-mint-gin-tonic.html`
- `recipe-garden-herb-gimlet.html`
- `recipe-hibiscus-paloma.html`
- `recipe-lavender-lemon-spritz.html`
- `recipe-peach-honey-bourbon-smash.html`
- `recipe-rosemary-bourbon-sour.html`
- `recipe-strawberry-basil-smash.html`
- `recipes.html`

## Required Validation Commands and Results

### Cloudflare Pages runtime

```text
npx --yes wrangler pages dev . --port 8788
```

Result:

- Wrangler 4.114.0 started successfully.
- No Pages Functions were found.
- 1 redirect rule parsed successfully.
- Production-equivalent local preview served the site.
- The preview was restarted from scratch after the conditional review, immediately before the final route and interaction checks.

### Redirect and MIME checks

Representative commands:

```text
curl -sS -I http://localhost:8788/lavender-simple-syrup
curl -sS -I http://localhost:8788/harvest-hub
curl -sS -I http://localhost:8788/images/guides/rosemary-guide-beyond-the-herb-bed.jpg
curl -sS -I http://localhost:8788/images/guides/mint-guide-from-our-garden.jpg
curl -sS -I http://localhost:8788/images/heroes/home-hero-1672.avif
curl -sS -I http://localhost:8788/images/heroes/home-hero-1672.webp
```

Result:

- `/lavender-simple-syrup`: `301` to `/recipe-lavender-syrup`.
- `/harvest-hub`: `200 text/html`, with no redirect or `Location` header.
- `/herb-hub`: `200 text/html`.
- Repaired guide images: `200 image/jpeg`.
- Optimized hero: `200 image/avif` and `200 image/webp`.

### Repository validator

A temporary read-only validation script inspected every retained HTML page, every JSON-LD block, all internal anchor routes, local image references, redirects, canonical URLs, sitemap URLs, initial mobile-menu state, Escape/focus logic, targeted dimensions, hero loading, and visible editorial text against the rollback commit.

Result:

```text
HTML_FILES=47
JSON_LD_BLOCKS=62
LOCAL_IMAGE_REFERENCES=192
SITEMAP_URLS=44
CANONICAL_ELEMENTS=47
UNIQUE_CANONICAL_URLS=46
ERRORS=0
```

Specific final results:

- Broken internal HTML links: **0**
- Missing local image references: **0**
- Invalid local image files: **0**
- JSON-LD parse failures: **0**
- Unexpected canonical/sitemap differences: **0** after accounting for non-indexable utility pages and the restored legacy alias
- Canonical hub URL on both hub files: **`https://frombedtobar.com/herb-hub`**
- Missing image width/height attributes: **0**
- Remaining malformed `/ loading=` patterns: **0**
- Pages without dynamic open/close mobile-menu labels: **0**
- Visible `Herb Hub` labels remaining in HTML: **0**
- Unexpected visible editorial-copy changes: **0**
- Unexpected image-source changes beyond the two approved repairs: **0**
- Browser console warnings/errors on tested routes: **0**

## Manual Route and Screen Review

Reviewed at **390 × 844 mobile** and **1440 × 900 desktop**:

- `/`
- `/recipes?q=mint`
- `/lavender-guide`
- `/lemon-balm-guide`

Results at both widths:

- Horizontal overflow: **none**
- Broken rendered images in reviewed viewports: **none**
- Page H1 present: **yes**
- Existing visual identity and layout preserved: **yes**

Additional manual review:

- `/harvest-hub?route-check=20260725-1517` remained on the legacy route and declared `/herb-hub` as canonical. A unique query was used because the existing browser profile had cached the previously tested permanent redirect; direct fresh HTTP validation of plain `/harvest-hub` returned `200` without `Location`.
- `/herb-hub` remained the canonical hub route.
- Lavender guide “Continue the garden” card grid at desktop width.
- Lemon-balm guide “Continue the Garden” card grid at desktop width.
- Homepage mobile navigation using keyboard activation and Escape.
- Recipes alternate mobile navigation state behavior.
- Homepage responsive hero source selection and settled visual composition.

## Every File Changed

### Added

- `.gitignore`
- `_redirects`
- `images/heroes/home-hero-640.avif`
- `images/heroes/home-hero-1024.avif`
- `images/heroes/home-hero-1672.avif`
- `images/heroes/home-hero-640.webp`
- `images/heroes/home-hero-1024.webp`
- `images/heroes/home-hero-1672.webp`
- `FROM_BED_TO_BAR_STABILIZATION_BATCH_1.md`

### Deleted after redirect validation

- `lavender-simple-syrup.html`

### Modified

- `404.html`
- `about.html`
- `bar-essentials.html`
- `basil-guide.html`
- `blog-post-1.html`
- `blog-post-2.html`
- `blog-post-3.html`
- `blog-post-4.html`
- `blog.html`
- `cocktails-garden-mojito.html`
- `cocktails-plum-bourbon-sour.html`
- `disclaimer.html`
- `garden-tips.html`
- `harvest-hub.html`
- `herb-hub.html`
- `how-to-harvest-preserve-basil.html`
- `how-to-harvest-preserve-lavender.html`
- `how-to-harvest-preserve-mint.html`
- `how-to-harvest-preserve-plums.html`
- `how-to-harvest-preserve-rosemary.html`
- `how-to-harvest-preserve-thyme.html`
- `index.html`
- `lavender-guide.html`
- `lemon-balm-guide.html`
- `mint-guide.html`
- `mocktails-sparkling-mint-limeade.html`
- `mocktails-sparkling-plum-mocktail.html`
- `planting-guide.html`
- `plum-guide.html`
- `preserves-plum-jam.html`
- `recipe-basil-syrup.html`
- `recipe-cucumber-mint-gin-tonic.html`
- `recipe-garden-herb-gimlet.html`
- `recipe-hibiscus-paloma.html`
- `recipe-lavender-lemon-spritz.html`
- `recipe-lavender-syrup.html`
- `recipe-mint-simple-syrup.html`
- `recipe-peach-honey-bourbon-smash.html`
- `recipe-plum-simple-syrup.html`
- `recipe-rosemary-bourbon-sour.html`
- `recipe-rosemary-syrup.html`
- `recipe-strawberry-basil-smash.html`
- `recipe-thyme-syrup.html`
- `recipes.html`
- `rosemary-guide.html`
- `thank-you.html`
- `thyme-guide.html`

No existing original image asset was deleted or overwritten.

`harvest-hub.html` was first restored exactly from the rollback baseline, then received only the two conditionally approved technical corrections described above.

`.gitignore` now excludes `.wrangler/` so the generated local Cloudflare cache cannot be included in a future commit.

## Could Not Be Completed

- Production deployment was not performed in this batch.
- Therefore, the lavender redirect was confirmed in Cloudflare Pages’ production-equivalent local runtime, but not on the public production domain.
- FBTB-015 route consolidation remains deferred: both hub files are retained, `/harvest-hub` is not redirected, and `/herb-hub` remains canonical.
- No implementation commit was created and nothing was deployed.

## Issues Discovered Outside This Batch

These items were recorded without being fixed:

1. The browser requested `/favicon.ico`, which returned `404`. This corresponds to the already-audited favicon/manifest issue and was outside Batch 1.
2. A full dimension-accuracy scan found **48 pre-existing non-targeted editorial image declarations** whose numeric attributes do not match the underlying file dimensions.
3. The same scan found **46 navigation-logo declarations** using the rendered `84 × 84` display size while the source file is `200 × 200`.
The targeted FBTB-009 images corrected in this batch all match their real assets. The broader pre-existing dimension corrections were intentionally left for a separately approved batch.

## Scope Confirmation

This batch did not:

- Redesign the site.
- Change the visual identity.
- Rewrite editorial body copy.
- Change privacy language.
- Change the plum-jam recipe.
- Migrate frameworks.
- Add runtime dependencies.
- Delete large asset groups.
- Begin Phase 2 or perform unrelated cleanup.

The global visible label correction from “Herb Hub” to “Harvest Hub” was limited to labels; lowercase `/herb-hub` links and all hub canonical, sitemap, JSON-LD, and Open Graph URL values were preserved.
