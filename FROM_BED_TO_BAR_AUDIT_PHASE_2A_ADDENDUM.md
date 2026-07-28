# From Bed to Bar — Full Website Audit Phase 2A Addendum

**Addendum date:** July 25, 2026
**Original audit:** `FROM_BED_TO_BAR_FULL_WEBSITE_AUDIT.md`
**Phase 1 checkpoint:** `b0f56da`
**Merged main checkpoint:** `ec0abe6`

This addendum supplements rather than replaces the original audit.

## Phase 1 Technical Stabilization

Phase 1 is committed and merged. The following audit findings were resolved:

- **FBTB-001:** `/lavender-simple-syrup` now has one Cloudflare Pages 301 to `/recipe-lavender-syrup`; the duplicate source page was removed.
- **FBTB-002:** the two missing guide-image references were replaced with approved existing assets.
- **FBTB-004:** `/recipes?q=...` initializes and filters the recipe search while preserving SearchAction schema.
- **FBTB-006:** malformed `/ loading=` image markup was corrected across all retained pages.
- **FBTB-007:** the homepage hero is no longer lazy-loaded and has responsive AVIF/WebP delivery with its original fallback preserved.
- **FBTB-009:** targeted images received measured intrinsic dimensions.
- **FBTB-023:** all retained pages now synchronize the mobile-menu accessible label with open/closed state.

The Harvest Hub route decision was corrected during Phase 1 review:

- `/harvest-hub` remains a 200 legacy page.
- `/herb-hub` remains the canonical hub URL.
- No `/harvest-hub` redirect exists.
- Visible labels use “Harvest Hub,” while links and metadata retain `/herb-hub`.

Therefore **FBTB-015 is deferred by owner direction**, not resolved through redirect consolidation.

## Trust Findings Still Unresolved

| Finding | Status after Phase 2A investigation | Required input |
|---|---|---|
| **FBTB-003 — Plum-jam preservation** | Unresolved. Three incompatible yields remain; no adopted tested source, batch record, or reviewer is documented. The public page and live deployment present shelf-stable instructions. | Owner recipe/batch facts plus qualified preservation review. |
| **FBTB-005 — Newsletter privacy layer** | Unresolved. The repository contains 43 static Kit forms plus one separate Kit embed, but no privacy page, form-adjacent notice, retention language, or privacy contact. | Kit-account facts, owner business practices, and legal/privacy review. |
| **FBTB-010 — Seasonal freshness** | Unresolved. The July repository/public page still says “Updated for late May” and contains undated “right now” modules. | Owner governance model, location context, cadence, and update owner. |
| **FBTB-012 — Authorship/dates** | Unresolved. Structured authors vary between Stephanie and the organization; most dates are invisible or absent. | Approved author/publisher/date model and factual credits. |
| **FBTB-013 — Stephanie’s voice** | Partially evidenced, unresolved as governance. The About page and many newer guides use Stephanie’s first-person voice, but organization-authored schema and impersonal pages remain. | Approved public identity, biography, Steve’s role, and page-type credit rules. |
| **FBTB-018 — Third-party Kit script** | Investigated, not changed. Kit script/configuration is repeated widely; account/runtime behavior remains unknown. | Account verification and privacy decision before any loading/analytics changes. |

## Owner Facts Required

1. Exact plum-jam recipe used, actual jar size/yield, method, additions, altitude, and intended public preservation method.
2. Kit double-opt-in, tags, fields, automations, sequences, tracking, cookies, retention, deletion, unsubscribe, integrations, and mailing-address settings.
3. Legal/operator identity, privacy contact, intended regions, minimum age, and newsletter practice.
4. Public location/zone wording, seasonal-update owner, cadence, expiry rule, and archive policy.
5. Stephanie’s approved public name/biography, Steve’s factual role, recipe-testing standard, date format, and modification rules.

## Qualified Review Required

- A qualified preservation reviewer must approve any shelf-stable plum-jam formula, processing time, altitude adjustment, jar/headspace rule, variations, scaling behavior, storage claim, and displayed review credit.
- Legal/privacy review is recommended for the privacy policy, consent language, regional obligations, age treatment, mailing address, retention/deletion language, and cookie requirements.
- Gardening or subject-matter fact-checking may be appropriate for climate/zone claims, but the Phase 2A documents do not invent a credential or mandate one where owners choose qualified evergreen wording.

## Why Phase 2A Made No Public Changes

The unresolved items depend on facts that are not in Git and, in the case of preservation, require expertise Codex cannot supply. Drafting public policy, changing canning instructions, or assigning authorship before those facts are approved would replace one trust problem with unverified claims. Phase 2A therefore created internal decision documents only.

## Recommended Phase 2B Order

1. **Owner answers and evidence collection**
   - Complete `PHASE_2A_OWNER_DECISION_SUMMARY.md`.
   - Attach the exact plum recipe/source and Kit-account evidence.
2. **Qualified preservation review**
   - Resolve formula, method, yield, scaling, processing, altitude, variations, storage, source, and reviewer credit.
3. **Privacy/business/legal decisions**
   - Confirm actual Kit behavior and approve the operator, contact, retention, rights, consent, and cookie treatment.
4. **Seasonal and authorship governance approval**
   - Approve the hybrid or alternate model, location/cadence, public names, roles, dates, and testing/review rules.
5. **Phase 2B implementation**
   - Implement only approved answers.
   - Keep food-safety, privacy, seasonal, and authorship changes in traceable workstreams with focused validation.
6. **Post-implementation review**
   - Preservation reviewer signs off on the exact rendered plum pages.
   - Owners/legal reviewer approve the exact privacy/consent implementation.
   - Repository validation confirms visible copy and structured data agree.

Do not start Phase 2B from recommendations alone; use completed owner fields and reviewer evidence as the implementation contract.
