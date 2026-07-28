# Phase 2A — Seasonal Content Inventory and Governance Options

**Repository version:** `ec0abe6`
**Accuracy review date:** July 25, 2026
**Scope:** Inventory and owner decisions only; no public copy was changed.

## Classification Rules

- **Evergreen:** season words describe recurring plant behavior, recipe character, or a general calendar with enough context.
- **Season-specific but acceptable:** explicitly seasonal editorial language that does not claim to describe the present.
- **Date-sensitive:** relative wording depends on publication/review date or reader location.
- **Objectively stale:** the page claims to be current but names a past update window as of this repository review.
- **Potentially misleading without location context:** a current planting/harvest claim is presented universally.

“Currently accurate” below means accurate relative to the repository review date and the context actually printed on the page. It is not a horticultural verification for every climate.

## Priority Inventory

### Undated or current-state modules

| Page / section | Exact wording | Date shown? | Location/climate? | Status on July 25, 2026 | Governance treatment |
|---|---|---:|---:|---|---|
| `garden-tips.html:1313–1315`, “What’s Growing” | “Late May Harvest Window”; “What’s Growing Right Now”; “What to pick today… Updated for late May.” | No | No | **Objectively stale**: a July repository version claims a late-May update is current. | Date the module and review it, or convert it to climate-aware evergreen guidance. |
| `garden-tips.html:1378`, `1387`, `1423` | “Coming soon”; “Plant now” | No | No | **Potentially misleading**; timing cannot be verified without location. | Tie to region/zone and review date, or remove “now.” |
| `garden-tips.html:1526–1527` | “This Season: Plums” and summer plum-harvest framing | No | No | Date-sensitive; may be locally true, but sitewide context is missing. | Pair with a date/location or make the module evergreen. |
| `index.html:1265` | “built around what is ripe right now” | No | No | Date-sensitive marketing claim without a maintained current dataset. | Use dated homepage module or evergreen wording. |
| `recipes.html:767`, `792` | “rooted in what is growing right now”; “In Season Now” | No | No | **Potentially misleading** because `data-inseason` is static, not calculated from date/location. | Define a maintained season model or rename the filter. |
| `recipes.html:896` | “Basil is peak right now. Strawberries are in season late spring through June.” | No | No | **Objectively stale** for July as written; location also absent. | Replace with dated/local context or evergreen availability range. |
| `recipes.html:1224` | “Mint is in full swing. Blueberries are in season now through August.” | No | No | Date-sensitive and location-dependent. | Add date/location or evergreen climate qualifier. |
| `cocktails-garden-mojito.html:13` | “what’s growing in your garden right now” | No | Reader-specific | Cannot be objectively guaranteed. | Reframe as an evergreen conditional claim. |
| `recipe-cucumber-mint-gin-tonic.html:7` | “from what’s growing right now” | No | No | Date-sensitive. | Reframe or date. |
| `index.html:14`, `21` | “what’s growing in your garden right now” | No | Reader-specific | Date-sensitive global metadata. | Align with chosen homepage governance. |
| `about.html:1168`, `1233` | “what’s growing in the garden right now”; “what to grow this season” | No | No | Describes site intent, but currentness depends on ongoing upkeep. | Keep only if a maintained seasonal system exists. |
| `herb-hub.html:1456`; `harvest-hub.html:1457` | “5 Cocktails Right Now” | No | No | Link label strips the article’s visible date context. | Use the article title plus date or evergreen label. |

The current public `garden-tips` page retrieved July 25, 2026 contained the same “Late May,” “Right Now,” and “Updated for late May” claims as the repository.

### Dated seasonal journal content

| Page / section | Exact wording | Visible date | Location/climate | Classification | Treatment |
|---|---|---:|---:|---|---|
| `blog-post-1.html:951`, `955`, `983–984` | Visible date “May 28, 2026”; “what to plant right now — late May”; “It’s late May.” | Yes | No | Season-specific but acceptable as a dated journal; location-dependent advice remains a risk. | Retain original date; add location/zone context and avoid presenting it as today’s universal instruction in cards. |
| `blog-post-1.html:13`, `19`, `21`, `45`; `blog.html:1080` | Metadata/cards say “what to plant right now.” | Card date exists on blog index; metadata date is not visible in search snippets. | No | Date-sensitive. | Pair archive cards with date; consider date-aware titles/descriptions. |
| `blog-post-2.html:963`, `967` | “May 28, 2026”; “Right now, in late May, elderflower is either at peak…” | Yes | “depending on your zone,” but no actual zone | Dated and qualified, yet incomplete geographically. | Keep as journal; add the author’s location or clearer zone guidance. |
| `blog-post-3.html:959`, `962–963` | “May 28, 2026”; “Late May”; “harvestable right now.” | Yes | No | Acceptable dated journal body; claims are not universal. | Keep original date; add location context. |
| `blog-post-3.html:977`, `999` | “blooming right now… this week”; “should be making right now.” | Yes, at page top | No | Date-sensitive within a dated article. | Accept under journal model; avoid undated cross-link labels. |
| `blog-post-3.html:5`, `11–20`, `43–44`; `blog.html:1102–1103`; `recipes.html:1709` | Title/metadata/cards use “What’s Growing Right Now” and “this week.” | Date visible on blog index/post, not always beside every cross-link | No | Date-sensitive distribution risk. | Preserve date in listings/snippets or retitle as a dated late-May article. |

### Place-aware seasonal content

| Page / section | Exact wording | Date shown? | Context | Classification | Treatment |
|---|---|---:|---|---|---|
| `plum-guide.html:14`, `1789`, `1821`, `1851`, `1888` | “By early June in Northern California…” and related orchard narrative | No | Northern California explicitly named in several placements | Season-specific and generally well contextualized; still year/weather dependent. | Keep place context; optionally add “typical” and a review date. |
| `basil-guide.html:75` | “In most temperate climates this means late May or early June.” | No | Temperate climates; anchored to >50°F nights | Climate-aware evergreen. | Retain; temperature/frost cues are stronger than universal calendar dates. |
| `planting-guide.html:1154–1245` | Zone warning plus Spring/Summer/Fall/Winter tasks | No | Zones and microclimate caveat | Climate-aware evergreen foundation. | Retain and govern with reviewed date/source standards. |

### “Coming soon” and roadmap claims

| Page(s) | Instances | Date/context | Classification | Treatment |
|---|---|---|---|---|
| `blog.html:1125`, `1135`, `1145`, `1155` | Four “Coming Soon” cards | None | Date-sensitive product promise | Either add an owner and target date or label as ideas without timing. |
| `index.html:1241`, `1247`, `1253` | Three “Video coming soon” recipe tags | None | Stale-prone promise | Maintain roadmap or remove promise in later implementation. |
| `recipe-garden-herb-gimlet.html:581`; `recipe-lavender-lemon-spritz.html:580`; `recipe-rosemary-bourbon-sour.html:591` | Video placeholders | None | Stale-prone promise | Same as above. |
| `rosemary-guide.html:1798–1799`, `2607–2610`; `how-to-harvest-preserve-rosemary.html:1944–1945`, `2101–2137` | Recipe “Coming soon” strips/links | None | Stale-prone roadmap | Assign owner/date or convert to non-promissory related ideas. |
| `how-to-harvest-preserve-thyme.html:2056–2059`, `2071–2074` | Four “Coming soon” recipe ideas | None | Stale-prone roadmap | Same treatment. |
| `lemon-balm-guide.html:1943`, `1953`, `1963`, `1994` | “Right now… new to us”; “Syrup is coming soon”; “Stay tuned” | No | Personal journal with no visible date | Date the garden note and review promised follow-ups. |

### Shared newsletter promise

The exact sentence “No spam, no filler. Just seasonal recipes, what to plant this month…” appears on **34 pages**, including `index.html:1407`, `about.html:1248`, `garden-tips.html:1577`, `recipes.html:1718`, and most recipe/blog pages. Three guides use the same “this month” promise with “an occasional note” (`lavender-guide.html:2029`, `lemon-balm-guide.html:2072`, `thyme-guide.html:2025`). Other guide/harvest pages use broader “Seasonal recipes, garden notes…” variants.

Classification: **date-sensitive service promise**. It is acceptable only if the newsletter is actually sent with current, region-appropriate monthly guidance. Kit cadence and content are unknown. Governance should align this promise with the approved newsletter program.

## Evergreen Seasonal Coverage

Season words are also used extensively as legitimate recurring guidance or flavor context. The inventory found season terms on these pages:

| Content family | Pages and representative sections | Classification / governance |
|---|---|---|
| Planting calendar | `planting-guide.html:1154–1507`, `1533–1909` | Evergreen, zone-aware calendar. Review horticultural claims annually and retain zone/microclimate caveat. |
| Herb guides | `basil-guide.html`, `lavender-guide.html`, `lemon-balm-guide.html`, `mint-guide.html`, `rosemary-guide.html`, `thyme-guide.html` | Mostly evergreen lifecycle, overwintering, harvest, and seasonal-flavor language. Require climate cues for directive timing; personal “our garden” passages should carry dates under the recommended model. |
| Harvest/preserve guides | All `how-to-harvest-preserve-*.html` | Mostly evergreen preservation and season-transition narrative. Safety claims need their own source/review governance; personal harvest passages should be dated. |
| Recipes | Cocktail, mocktail, syrup, and preserve pages | Mostly acceptable flavor/occasion labels such as “summer drink” or “winter syrup.” “Right now,” “this month,” and “coming soon” require governance. |
| Collection pages | `index.html`, `recipes.html`, `garden-tips.html`, hub pages, `blog.html` | Highest stale-content risk because undated modules look current. |

Raw season-word counts show the largest maintenance surfaces: `planting-guide.html` (85), `basil-guide.html` (61), `recipes.html` (50), `how-to-harvest-preserve-basil.html` (39), `mint-guide.html` (35), `rosemary-guide.html` (34), `recipe-basil-syrup.html` (34), `lavender-guide.html` (29), and `plum-guide.html` (26). Counts include repeated structured/visible wording and are a maintenance signal, not a defect count.

## Governance Options

### Option A — Dated seasonal journal

| Dimension | Approach |
|---|---|
| Benefits | Preserves Stephanie’s personal, in-the-garden voice; makes “right now” honest; supports family storytelling. |
| Risks | Homepage and modules become visibly stale if updates stop; regional relevance remains limited. |
| Workload | High and recurring. |
| Required fields | `Published`, `Updated`, location/zone where relevant, status/archive flag. |
| Cadence | Homepage/current modules weekly or biweekly in growing season; monthly minimum elsewhere. |
| Owner | Named editorial owner, likely Stephanie, with backup. |
| Stale handling | Automatically or manually remove “current” modules after a fixed window; archive journal entries with original dates. |
| Search/trust | Strong when maintained; conspicuously weak when dates age without updates. |

### Option B — Climate-aware evergreen guidance

| Dimension | Approach |
|---|---|
| Benefits | Lower upkeep; useful across regions; temperature/frost/zone cues are more accurate than universal dates. |
| Risks | Less intimate and less immediate; requires careful horticultural sourcing. |
| Workload | Moderate initial rewrite, then annual review. |
| Required fields | Climate/zone caveat, applicable regions, source/review date. |
| Cadence | Annual review plus corrections when guidance changes. |
| Owner | Editorial owner with gardening fact-check support as needed. |
| Stale handling | Flag pages when review date exceeds the approved interval. |
| Search/trust | Durable and useful, but generic if personal experience disappears. |

### Option C — Hybrid model

| Dimension | Approach |
|---|---|
| Benefits | Keeps Stephanie’s timely family/garden voice where it adds value while making core guidance durable and climate-aware. |
| Risks | Requires clear page-type rules so journal and guidance do not blur together. |
| Workload | Moderate; lower than an all-journal site. |
| Required fields | Published/Updated for articles and journal modules; location/zone and review date for guidance; module expiration date for “now.” |
| Cadence | Homepage/journal monthly or during active seasons; guides annually. |
| Owner | Stephanie owns narrative updates; Steve can own calendar/QA operations if approved. |
| Stale handling | Expire undated “now” modules; retain dated posts; convert core advice to climate cues. |
| Search/trust | Best balance: freshness signals on current content and stable answers on guides. |

## Recommendation

**Recommend Option C, the hybrid model**, for a small family editorial site. It protects the warm firsthand voice without requiring every guide to be rewritten every month. Final approval belongs to Steve and Stephanie.

Suggested rule: “Right now,” “today,” “this week,” and “this month” may appear only in content with a visible date, a named location/context where relevant, an assigned owner, and an expiration/review date.

## Owner Decision Sheet

| Decision | Owner answer |
|---|---|
| Governance option: A / B / C | |
| Approved public location wording | |
| USDA zone/climate information to publish | |
| Seasonal-update owner | |
| Backup owner | |
| Realistic homepage/current-module cadence | |
| Core-guide review cadence | |
| Display “Published” on which page types? | |
| Display “Updated” on which page types? | |
| Archive behavior for old seasonal posts | |
| May “right now” appear without a visible date? | |
| Maximum age for a “current” module | |
| Treatment of “coming soon” items | |
| Newsletter seasonal promise and cadence | |
| Permission to implement in Phase 2B | |
