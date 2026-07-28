# Phase 2A — Owner Decision Summary

**For:** Steve and Stephanie
**Purpose:** Complete these decisions before Phase 2B changes public content.
**Detailed evidence:** See the four companion Phase 2A workstream documents.

## Required Before Public Promotion

### 1. Plum Jam

| Decision | Why it matters | Current site condition | Options | Recommendation | Steve/Stephanie answer | Review needed | Later files |
|---|---|---|---|---|---|---|---|
| PJ-1 — Intended preservation method | Determines whether shelf-stable instructions may remain | Page teaches water-bath canning and one-year pantry storage | Shelf-stable canning / refrigerator / freezer | Do not promote until exact method is approved | | Qualified preservation review | `preserves-plum-jam.html`, related cards/guides/schema |
| PJ-2 — Exact recipe source | Similar ingredients do not prove tested equivalence | No adopted source is cited | Family recipe / exact authority recipe / documented modified recipe / independently developed | Attach the exact recipe/version Stephanie used | | Qualified preservation review | Plum recipe copy, citation, Recipe JSON-LD |
| PJ-3 — Actual batch facts | Public yields conflict | 5–6 half-pints, 5–6 pints, and 8–10 half-pints all appear | Record actual jar size/count and input weight | Use real batch log plus reviewer-approved yield wording | | Yes | Recipe, homepage, blog, collections |
| PJ-4 — Formula and additions | Acidity/process may depend on exact formula | Plums, sugar, lemon, cinnamon, vanilla, almond, ginger, bourbon, and a scaler are offered | Approve exact formula/variations or remove unapproved ones | Reviewer approves exact permitted version; separate unreviewed ideas | | Yes | Recipe ingredients/instructions/scaler/schema |
| PJ-5 — Altitude and process | Readers may rely on the process for shelf stability | 10-minute process and custom altitude wording have no direct citation | Approve exact table/source / change method | Use exact reviewer-approved authority guidance | | Yes | Recipe and plum preservation guide |
| PJ-6 — Reviewer | Needed to cross the preservation-review boundary | None identified | Extension educator / qualified preservation professional / other verified reviewer | Name reviewer and document approval | | Yes | Review credit, source note, dates |

### 2. Newsletter Privacy

| Decision | Why it matters | Current site condition | Options | Recommendation | Answer | Review needed | Later files |
|---|---|---|---|---|---|---|---|
| NP-1 — Operator identity/contact | Privacy requests need an accountable operator | No privacy page/contact | Approved legal/operator name and monitored email | Decide before promoting signup | | Legal review recommended | New `/privacy`, footer, forms |
| NP-2 — Kit account verification | Repository cannot see account behavior | 43 inline forms plus one opaque embed | Owner audit / provider support audit | Complete the Kit checklist with screenshots/exports | | Privacy/legal review | Forms, thank-you, privacy page |
| NP-3 — Consent and newsletter promise | Users should know what they will receive | “No spam” and “this month,” but no privacy notice/frequency | Approve cadence/purpose/notice | Plain notice beside every form | | Legal review recommended | 44 signup placements |
| NP-4 — Retention/deletion | Required facts cannot be invented | No public or repository practice | Define schedule/process/owner | Adopt a written internal practice before drafting policy | | Legal review recommended | Privacy page/internal procedure |
| NP-5 — Tracking/cookies | Remote Kit scripts may set storage/tracking | Embedded analytics integrations are null; runtime/account behavior unknown | Disable unnecessary tracking / disclose required tools | Verify first; add cookie controls only if necessary | | Legal review recommended | Privacy/cookie implementation |
| NP-6 — Separate basil embed | Inconsistent embed may collect/configure differently | `76f668a3b6` is opaque in repo | Verify and standardize / document exception | Verify account object, then standardize | | Account review | `how-to-harvest-preserve-basil.html` |

## Required Within 30 Days

### 3. Seasonal Content

| Decision | Why it matters | Current site condition | Options | Recommendation | Answer | Review needed | Later files |
|---|---|---|---|---|---|---|---|
| SC-1 — Governance model | Prevents recurring stale “right now” copy | Dated blog posts coexist with undated current modules | A dated journal / B climate-aware evergreen / C hybrid | **C — Hybrid** | | Owner/editorial | Homepage, garden tips, recipes, guides |
| SC-2 — Public location/climate | Plant/harvest timing is regional | Northern California appears on Plum Guide; other pages omit context | Publish region / zone / both / neither | Publish the minimum accurate context owners are comfortable with | | Gardening fact-check as needed | Guides, seasonal modules, About |
| SC-3 — Update ownership/cadence | “Current” content needs a responsible owner | No review owner or expiry rule | Weekly / biweekly / monthly / no current modules | Monthly minimum; expire “now” copy if missed | | No professional review | Homepage/garden/recipes |
| SC-4 — Visible dates | Readers need context | Only blog posts show dates | Published/Updated by page type | Show dates on editorial/safety pages and dated modules | | Owner/editorial | Articles, recipes, guides |
| SC-5 — “Right now” rule | Relative claims become misleading | Late-May module remains current in July | Allow only with date/context / prohibit | Allow only with visible date, context, owner, and expiry | | No | Metadata, modules, cards |
| SC-6 — “Coming soon” rule | Open-ended promises become stale | Multiple recipe/video placeholders | Roadmap with date / convert to ideas / remove | Publish only owner-backed items; otherwise non-promissory wording | | No | Blog, recipe, rosemary/thyme/lemon balm pages |

### 4. Authorship and Dates

| Decision | Why it matters | Current site condition | Options | Recommendation | Answer | Review needed | Later files |
|---|---|---|---|---|---|---|---|
| AD-1 — Stephanie’s public identity | Schema and voice need one identity | Schema says “Stephanie”; About is first person | Full name / first name / approved professional form | **Stephanie Freitas**, if approved | | Owner confirmation | About, Person schema, bylines |
| AD-2 — Author/publisher model | Organization and person are mixed | 21 content entities use FBTB author; 15 use Stephanie | Organization author / Stephanie author + FBTB publisher / case-by-case | Stephanie author + FBTB publisher for her editorial work | | Owner confirmation | Most articles/recipes/schema |
| AD-3 — Steve’s role | Avoids invented credit | No public role is defined | Operations / contributor / co-author in identified cases | Contributor/operations credit only where factual | | Owner confirmation | About, selected pages |
| AD-4 — Recipe-testing language | “Tested” is a factual claim | No testing protocol or credit | Do not use / define protocol and tester | Do not use until protocol and records exist | | Qualified review for preservation | Recipes/About |
| AD-5 — Date rules | Prevents misleading freshness | Structured dates are inconsistent and mostly invisible | Define published/modified/reviewed system | Preserve original publication date; update `dateModified` only for substantive changes | | Editorial; legal for policy dates | All content/schema |
| AD-6 — Preservation review credit | Safety review differs from authorship | No reviewer exists | Add only after actual review | Display named reviewer, credential, source, and review date after approval | | Qualified reviewer | Plum preservation pages |

## Optional Future Improvements

| Decision | Why it matters | Options | Recommendation | Answer | Later task |
|---|---|---|---|---|---|
| OF-1 — Author page | Gives Stephanie’s work a stable identity | Expand `/about` / add author route | Start with improved About; add author route only if useful | | Author profile implementation |
| OF-2 — Author bio boxes | Reinforces firsthand expertise | All content / selected editorial pages / none | Selected guides, recipes, and blog posts | | Component/content work |
| OF-3 — Terms/site-use page | May complement disclaimer/privacy | Combined / separate / none | Decide with counsel after privacy scope | | Legal content |
| OF-4 — Automated freshness checks | Reduces stale copy | Manual checklist / build-time lint / CMS later | Start with a simple repository check for relative phrases and overdue dates | | Tooling phase |

## Owner Sign-Off

| Owner | Name | Date | Notes |
|---|---|---|---|
| Steve | | | |
| Stephanie | | | |
| Preservation reviewer | | | |
| Legal/privacy reviewer, if used | | | |

## Implementation Mapping

Complete this table after decisions are approved. Do not implement from recommendations alone.

| Decision | Approved answer | Future task | Likely files | Validation |
|---|---|---|---|---|
| PJ-1 to PJ-6 | | Reconcile or reclassify plum recipe; cite and credit review | `preserves-plum-jam.html`, `how-to-harvest-preserve-plums.html`, `index.html`, `blog.html`, `plum-guide.html`, `recipes.html`, JSON-LD | Reviewer sign-off; all yields/process claims agree |
| NP-1 to NP-5 | | Create privacy/consent layer | New `privacy.html`, all footers/forms, `thank-you.html`, sitemap/robots if approved | Link scan; owner/legal sign-off; no unverified claims |
| NP-6 | | Reconcile basil Kit embed | `how-to-harvest-preserve-basil.html` | Same fields/notice/flow as approved standard |
| SC-1 to SC-5 | | Apply seasonal governance and dates | `garden-tips.html`, `recipes.html`, `index.html`, blog cards/posts, metadata, selected guides | No undated “now” claim; context/date checks |
| SC-6 | | Resolve roadmap promises | Blog, recipe video placeholders, rosemary/thyme/lemon-balm pages | Every promise has owner/date or is non-promissory |
| AD-1 to AD-3 | | Normalize authorship | About, Articles, Recipes, BlogPosting/Person schema | Visible author matches schema and factual owner |
| AD-4 | | Add testing language only if approved | Recipes/About | Protocol and records support every claim |
| AD-5 | | Normalize date display/schema | Editorial pages and JSON-LD | Visible/schema dates agree; modification rule followed |
| AD-6 | | Add preservation review credit | Plum pages | Reviewer approves exact displayed credit |
