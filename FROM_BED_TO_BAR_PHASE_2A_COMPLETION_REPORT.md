# From Bed to Bar — Phase 2A Completion Report

**Completed:** July 25, 2026
**Phase:** Trust and Accuracy Decision Pack
**Result:** Investigation and owner-decision documents completed; no public website files changed

## Starting Point

- Phase 1 implementation commit: `b0f56da` — `Phase 1`
- Phase 1 merge commit on `origin/main`: `ec0abe6` — `Merge pull request #1 from FreitasLabs/codex/stabilization-batch-1`
- Phase 1 commit containment was verified with Git.
- Local `main` was fast-forwarded to `ec0abe6`.
- Worktree was clean before Phase 2A.
- Starting branch: `main`
- New branch: `codex/phase-2a-trust-decisions`

Phase 2A did not begin from the original audit baseline `ff4451abcfb4a5829afdeafff8a283a63d7f3671`.

## Files Created

1. `PHASE_2A_PLUM_JAM_RECONCILIATION.md`
2. `PHASE_2A_NEWSLETTER_PRIVACY_REQUIREMENTS.md`
3. `PHASE_2A_SEASONAL_CONTENT_INVENTORY.md`
4. `PHASE_2A_AUTHORSHIP_AND_DATES.md`
5. `PHASE_2A_OWNER_DECISION_SUMMARY.md`
6. `FROM_BED_TO_BAR_AUDIT_PHASE_2A_ADDENDUM.md`
7. `FROM_BED_TO_BAR_PHASE_2A_COMPLETION_REPORT.md`

## Repository and Public Sources Reviewed

### Repository-wide

- All 47 retained root HTML files.
- All 62 JSON-LD blocks, with focused extraction of Recipe, Article, BlogPosting, Person, Organization, WebPage, CollectionPage, WebSite, and HowTo entities.
- `sitemap.xml`
- `robots.txt`
- `_redirects`
- `.gitignore`
- `FROM_BED_TO_BAR_FULL_WEBSITE_AUDIT.md`
- `FROM_BED_TO_BAR_STABILIZATION_BATCH_1.md`
- Git history for the plum-jam page, form-bearing HTML, Phase 1 branch, and merged main.

### Focused plum review

- `preserves-plum-jam.html`
- `index.html`
- `plum-guide.html`
- `how-to-harvest-preserve-plums.html`
- `recipes.html`
- `garden-tips.html`
- `blog.html`
- `herb-hub.html`
- `harvest-hub.html`
- `sitemap.xml`
- Related Recipe/FAQ/Article/ItemList JSON-LD and all repository references to the page.

### Focused newsletter review

- 43 static inline Kit forms.
- The separate Kit embed in `how-to-harvest-preserve-basil.html`.
- The newsletter-only section without a form in `how-to-harvest-preserve-lavender.html`.
- `thank-you.html`, `robots.txt`, sitemap treatment, footer links, and disclaimer.

### Public read-only checks

The current public plum-jam, garden-tips, About, and robots resources were fetched without submitting forms or changing external state.

- The public plum page matched the repository on the conflicting yields and trust-critical claims.
- The public garden-tips page still displayed “Late May,” “Right Now,” and “Updated for late May” on July 25, 2026.
- The public About page exposed the same Kit signup structure and no privacy link.
- The public site shell appeared not to include the merged Phase 1 “Harvest Hub” visible-label update at review time. This deployment observation is outside Phase 2A scope and was not changed.

## Findings Confirmed

### Plum jam

- Three incompatible yield representations:
  - 5–6 half-pint jars;
  - 5–6 pints;
  - 8–10 half-pint jars.
- The page offers a shelf-stable process, altitude rule, variations, a public scaler, and one-year pantry storage without identifying an adopted tested recipe.
- Git history does not document the actual recipe source, real batch yield, jar size, altitude, or qualified approval.
- The audit’s NCHFP link is a review lead, not proof that the public formula is equivalent.

### Newsletter/privacy

- 43 pages have static Kit form ID `9503567`, UID `08e54ce9b8`, required email only, and redirect to `/thank-you`.
- One additional page loads opaque Kit embed UID `76f668a3b6`.
- No repository privacy page, form-adjacent privacy link, retention/deletion language, privacy contact, or unsubscribe explanation exists.
- Embedded analytics integrations are null and reCAPTCHA is marked false, but account/runtime behavior is not proven.

### Seasonal content

- The main objectively stale module is `garden-tips.html:1313–1315`.
- Undated “right now,” “in season now,” “plant now,” and “coming soon” language appears across homepage, recipe collections, metadata, cards, and guides.
- The four blog posts have visible dates, making their relative seasonal narrative materially better contextualized.
- The Plum Guide provides useful Northern California context; the Planting Guide provides zone/microclimate framing.
- A hybrid dated-journal plus climate-aware evergreen model is the recommended fit, subject to owner approval.

### Authorship/dates

- No conventional visible byline exists.
- 21 content entities use From Bed to Bar as author; 15 use Stephanie; 12 have no author.
- 28 content entities have a structured publication date; 16 have a modification date; 20 have neither.
- Only the blog posts expose publication dates to readers.
- Strong first-person family content frequently lacks visible authorship.

## Conflicts Identified

1. Plum-jam yield and jar-size conflict.
2. Plum formula/source/process versus unsupported shelf-stability presentation.
3. Recipe schema versus visible yield and variation content.
4. Public scaler versus absence of a documented approved scaling rule.
5. Confirmation-oriented Kit copy versus unknown account-level double-opt-in.
6. Standard static Kit form versus separate opaque basil embed.
7. “Right now” promise versus undated/static seasonal data.
8. Dated blog journal content versus undated cross-link and metadata presentation.
9. Stephanie’s first-person editorial voice versus organization-authored schema.
10. Structured dates versus invisible or missing reader-facing dates.

## Owner Decisions Required

- Exact plum recipe/source, batch facts, method, additions, altitude, intended public method, scaler treatment, and reviewer.
- Operator/legal identity, privacy contact, regions, minimum age, newsletter frequency/purpose, retention, deletion, exports, and data recipients.
- Kit double opt-in, fields, tags, automations, sequences, tracking, cookies, unsubscribe/suppression, spam controls, and mailing address.
- Seasonal governance model, public location/zone, owner, cadence, visible dates, archive/expiry rule, and “coming soon” policy.
- Stephanie’s approved public name/biography, Steve’s role, factual authorship by page, testing language, reviewer credit, and date rules.

## Qualified Reviews Required

- **Preservation:** required before promoting or affirming the shelf-stable plum-jam process.
- **Legal/privacy:** recommended before publishing policy/consent language or deciding cookie/region treatment.
- **Gardening fact-check:** advisable where directive seasonal timing cannot be responsibly framed through owner location/zone and existing evidence.

## Repository Unknowns

- The exact plum recipe Stephanie used and whether it was modified.
- Actual jam jar size, yield, method, ingredients/additions, and kitchen altitude.
- Whether Kit double opt-in and tracking are enabled.
- Account tags, fields, automations, sequences, exports, retention, deletion, suppression, integrations, and mailing address.
- The operator/legal identity and privacy contact to publish.
- Which recipes Stephanie personally developed/tested.
- Steve’s factual editorial/operations contribution.
- Whether any external reviewer has already reviewed preservation content.

No unknown was filled by assumption.

## Validation — No Public Website Change

Compared with merged checkpoint `ec0abe6`:

- Tracked HTML changes: **0**
- Image changes: **0**
- `_redirects` changes: **0**
- `sitemap.xml` changes: **0**
- `robots.txt` changes: **0**
- JSON-LD changes: **0**
- Public copy changes: **0**
- Form submissions: **0**
- External account changes: **0**
- New files: **7 Markdown documents only**
- `git diff --check`: **pass**

## Recommended Next Prompt Scope for Phase 2B

Do not start Phase 2B until the owner summary has completed answers and reviewer evidence.

Recommended prompt:

> Implement From Bed to Bar Phase 2B using only the approved answers in `PHASE_2A_OWNER_DECISION_SUMMARY.md` and attached reviewer evidence. Separate the work into: (1) qualified plum-preservation reconciliation, (2) owner/legal-approved privacy and Kit consent layer, (3) approved seasonal governance changes, and (4) approved authorship/date normalization. Do not invent missing facts, credentials, review claims, legal language, recipe ratios, or account settings. Preserve Phase 1 routing and technical stabilization. Validate visible copy against structured data and produce a Phase 2B completion report.

Phase 2B was not started.
