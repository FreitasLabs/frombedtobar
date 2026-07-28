# Phase 2A — Plum Jam Reconciliation

**Status:** Owner decision and qualified review required before public promotion
**Repository checkpoint:** `ec0abe6` (contains Phase 1 commit `b0f56da`)
**Reviewed:** July 25, 2026
**Public page:** `https://frombedtobar.com/preserves-plum-jam`

## Boundary

This document inventories what the repository and current public page say. It does **not** declare the recipe safe, validate shelf stability, calculate a replacement formula, approve substitutions, or replace review by a qualified preservation authority.

The public page retrieved on July 25, 2026 matched the repository on the critical yield, ingredient, processing, and storage statements listed below.

## Repository and Live-Page Inventory

### Yield, jar quantity, and jar size

| Value or exact wording | Location | Surface | Conflict |
|---|---|---|---|
| “Makes 5–6 pints.” | `preserves-plum-jam.html:7` | Metadata description | Conflicts with schema half-pint yield and with the 8–10 half-pint alternative. |
| `"recipeYield": "5–6 half-pint jars"` | `preserves-plum-jam.html:43` | Recipe JSON-LD | Conflicts with every visible 5–6 pint statement. |
| “🫙 5–6 pints” | `preserves-plum-jam.html:798` | Visible hero | Conflicts with schema. |
| “5.6 lb pitted plums yields 5–6 pints or 8–10 half-pint jars.” | `preserves-plum-jam.html:1021` | Visible sidebar | Internally inconsistent by volume: 5–6 pints would equal 10–12 half-pints, not 8–10. |
| Same default yield reset string | `preserves-plum-jam.html:1241` | JavaScript-generated visible copy | Repeats the inconsistent sidebar value. |
| Approximate yield formula: `~0.9 pints/lb` and `~1.5 half-pints/lb` | `preserves-plum-jam.html:1188–1194` | JavaScript | Produces two independently rounded ranges that are not guaranteed to be volumetrically equivalent and have no cited source. |
| “Makes 5–6 pints” | `index.html:1288–1289`; `blog.html:1193–1195` | Homepage and blog cards | Repeats one disputed version. |

No repository file records an actual batch yield, filled-jar count, or actual jar size.

### Ingredients and batch scaling

| Field | Exact value or wording | Location | Surface / concern |
|---|---|---|---|
| Plums | `5.6 lb pitted plums` / `5.6 lb (2.54 kg)` | `preserves-plum-jam.html:53`, `831`, `998`, `1149` | Schema, visible copy, and scaler base agree. Actual source and tested batch are undocumented. |
| Sugar | `3.75 lb granulated sugar` / `3.75 lb (1.7 kg)` | `preserves-plum-jam.html:54`, `832`, `999`, `1150` | Schema, visible copy, and scaler base agree. |
| Acid | `Juice of 2 lemons (about 1/4 cup)` | `preserves-plum-jam.html:55`, `833`, `1000`, `1235` | Count and volume are both stated; no bottled/fresh specification or tested source is given. |
| Pectin | No pectin appears in ingredients or instructions | `preserves-plum-jam.html:52–94`, `828–900`, `995–1011` | Non-use is implied, not explicitly explained or sourced. |
| Base optional flavors | `1 cinnamon stick`; `1 tsp vanilla extract` | `preserves-plum-jam.html:56–57`, `834–835` | Schema includes cinnamon and vanilla only. |
| Additional visible flavors | `1/4 tsp almond extract`; `1–2 Tbsp bourbon`; `1 Tbsp fresh grated ginger` | `preserves-plum-jam.html:1003–1011` | Not present in Recipe schema; relationship to a tested canning formula is unknown. |
| Off-heat additions | “Stir in vanilla extract, almond extract, or bourbon if using.” | `preserves-plum-jam.html:886–890` | Public variation advice; qualified reviewer must decide whether any addition is compatible with the approved process. |
| Fruit diversion | “set aside 1 lb” for syrup | `preserves-plum-jam.html:63`, `847–850` | The page does not clarify whether the displayed 5.6 lb is measured before or after this diversion. |
| Scaler | User input `0.5–50 lb`; scales plums, sugar, and lemon proportionally | `preserves-plum-jam.html:978–992`, `1148–1227` | Publicly enables batch-size changes without a documented tested scaling rule. |
| Scaler safety note | “Processing time, headspace, and jar size must follow current USDA guidelines” | `preserves-plum-jam.html:1014–1017` | A caution exists, but it does not establish that the ingredient scaling is tested or approved. |

### Cooking, gel test, canning, cooling, and storage

| Field | Exact wording or value | Location | Surface / conflict |
|---|---|---|---|
| Fruit cook | Medium heat, `15–20 minutes` until soft | `preserves-plum-jam.html:67–68`, `852–857` | Schema and visible copy agree. No tested source. |
| Sugar stage | Add gradually; dissolve; full rolling boil | `preserves-plum-jam.html:71–73`, `859–864` | Schema and visible copy agree. |
| Jam cook | Vigorous boil, `20–35 minutes`; begin testing after 20 | `preserves-plum-jam.html:76–78`, `866–870` | No tested source or batch record. |
| Gel test | Cold-plate wrinkle test; wait 30 seconds; recook 5 minutes if runny | `preserves-plum-jam.html:80–83`, `873–879` | Schema and visible copy agree. |
| Temperature | `220°F (104°C) at sea level` | `preserves-plum-jam.html:83`, `881–884` | Visible copy additionally says reduce 2°F per 1,000 feet; qualified review required. |
| Headspace | `1/4-inch` for canning | `preserves-plum-jam.html:93`, `893–900` | Schema and visible copy agree. |
| Jar size | “half-pint or pint jars” | `preserves-plum-jam.html:898` | Schema names half-pints only; hero/sidebar also claim pints. |
| Processing | Boiling-water bath, `10 minutes` | `preserves-plum-jam.html:93`, `898` | Stated for both half-pints and pints; no direct tested source. |
| Altitude | Above 1,000 ft, “add 1 minute for every 1,000 feet up to 6,000 feet, then 2 minutes per 1,000 feet above that” | `preserves-plum-jam.html:902–905` | Needs qualified verification against the exact approved formula and current authority table. |
| Cooling | Let stand 5 minutes before filling; cool jars undisturbed `12–24 hours` | `preserves-plum-jam.html:88`, `890`, `899` | No tested source. |
| Seal check | “Check seal before opening” | `preserves-plum-jam.html:912–914` | Does not provide a post-cooling band-removal/label/check sequence. |
| Pantry | Sealed, cool/dark, `up to 1 year` | `preserves-plum-jam.html:912–914`; shelf claim at `825` | Shelf-stable claim requires the formula and process to be validated. |
| Refrigerator | Opened, `3–4 weeks` | `preserves-plum-jam.html:915–917` | No instruction for an unsealed jar after processing. |
| Freezer | `up to 1 year`; `1/2-inch` headspace in freezer-safe containers | `preserves-plum-jam.html:918–920` | Freezing route exists, but no separate refrigerator/freezer method is defined. |
| Safety disclaimer | Scaler caution only | `preserves-plum-jam.html:1014–1017` | No statement that the recipe is pending preservation review. |
| Source citation | None on recipe page | Entire `preserves-plum-jam.html` | The audit mentions NCHFP, but the public recipe does not cite or identify an adopted tested recipe. |

### Related claims and calls to action

| Page / section | Exact claim | Classification |
|---|---|---|
| `how-to-harvest-preserve-plums.html:79`, `972` | Plums are high-acid and named plum products are “approved for water-bath canning”; tells readers to use a current USDA-tested recipe. | Broad safety claim; does not validate this recipe. |
| `how-to-harvest-preserve-plums.html:87`, `976` | Properly processed and sealed plum jam lasts one year; opened jam lasts 3–4 weeks. | Conditional storage claim. |
| `how-to-harvest-preserve-plums.html:828–830` | Calls the linked recipe water-bath canned, safe without a pressure canner, and one-year shelf stable. | High-trust cross-page claim. |
| `how-to-harvest-preserve-plums.html:887–922` | Gives pH range, water-bath statements, seal/discard guidance, and names NCHFP without a direct recipe citation. | Useful context but not proof of recipe equivalence. |
| `how-to-harvest-preserve-plums.html:932–935` | Calls the jam page the “full water-bath canning guide.” | Promotes disputed instructions. |
| `index.html:1281–1289` | “full water-bath canning guide… Makes 5–6 pints.” | Repeats disputed yield and promotes canning. |
| `blog.html:1189–1195` | “full water-bath canning guide… altitude adjustments… Makes 5–6 pints.” | Repeats disputed yield and promotes canning. |
| `garden-tips.html:1539–1542` | “Full water-bath canning guide.” | Promotes disputed instructions. |
| `plum-guide.html:1983–1985` | “pantry version of summer,” “all year long,” and “full canning guide.” | Implies shelf stability. |
| `recipes.html:81–85`, `1478–1485` | ItemList/schema and collection card identify the recipe; card image alt says jars are “sealed and ready for the pantry.” | Pantry claim; no yield displayed. |
| `sitemap.xml:142–145` | Includes `/preserves-plum-jam`; last modified `2026-06-12`. | Discovery only; no safety evidence. |

Other repository links in `harvest-hub.html`, `herb-hub.html`, and `plum-guide.html` primarily name or link the recipe. They do not resolve the formula or yield.

## Conflict Table

| ID | Field | Version A | Version B | Sources | Risk | Owner decision | Qualified review | Next action |
|---|---|---|---|---|---|---|---|---|
| PJ-01 | Yield | 5–6 half-pint jars | 5–6 pints | Recipe schema `:43`; metadata/hero/cards `:7`, `:798`, `index.html:1288`, `blog.html:1195` | High trust/consistency | Confirm actual yield and jar size | Yes | Preserve current page unchanged until source and real batch are reconciled. |
| PJ-02 | Yield conversion | 5–6 pints | 8–10 half-pint jars | `preserves-plum-jam.html:1021`, `1241` | High | Confirm actual filled jars | Yes | Replace all yield values from approved evidence in Phase 2B. |
| PJ-03 | Recipe provenance | Page presents a complete shelf-stable recipe | No adopted tested source is named | Recipe page; audit `FROM_BED_TO_BAR_FULL_WEBSITE_AUDIT.md:176–185` | Critical | Identify exact recipe Stephanie used | Yes | Obtain exact source/version and reviewer approval. |
| PJ-04 | Variations | Cinnamon/vanilla in schema | Almond, bourbon, ginger also offered publicly | `:56–57`, `:889`, `:1003–1011` | High | Identify what was actually added and what should remain public | Yes | Separate approved formula from unreviewed flavor ideas. |
| PJ-05 | Scaling | Scaler permits 0.5–50 lb proportional batches | No tested scaling source | `:983–992`, `:1148–1227` | Critical | Keep, constrain, or remove scaler | Yes | Reviewer must approve any batch-size behavior. |
| PJ-06 | Fruit diversion | 5.6 lb recipe | Set aside 1 lb for syrup | `:53`, `:63`, `:849`, `:998` | High | Clarify whether 5.6 lb is before or after diversion | Yes | Reconcile batch input and yield. |
| PJ-07 | Processing/altitude | 10 minutes; custom minute additions | Exact approved table/source absent | `:893–905` | Critical | Select approved shelf-stable or refrigerator/freezer intent | Yes | Use exact qualified source wording in Phase 2B. |
| PJ-08 | Shelf claim | One year pantry | Recipe unverified | `:825`, `:912–920`; related guide `:828–829` | Critical | Decide intended preservation method | Yes | Do not promote as shelf stable until approved. |
| PJ-09 | Authorship | Organization is Recipe author | Stephanie is intended storyteller | `preserves-plum-jam.html:47–48`; About `about.html:1133–1139` | Medium | Confirm author and reviewer credit | Preservation reviewer required for safety review | Implement after authorship and review decisions. |

## Source Assessment

The repository proves:

- The page first appeared through a sequence of uploaded-file commits and was later expanded with schema and a scaler; history does not contain a source note, recipe citation, batch log, or owner statement proving which recipe was used.
- `FROM_BED_TO_BAR_FULL_WEBSITE_AUDIT.md:184` names the National Center for Home Food Preservation page `https://nchfp.uga.edu/how/make-jam-jelly/jams/plum-jam-without-pectin/` as a comparison/review source.
- `how-to-harvest-preserve-plums.html:922` generically names NCHFP as an authority.

The repository does **not** prove:

- that the published formula is the original family recipe;
- that Stephanie actually followed this exact formula;
- that it is copied from or equivalent to the named NCHFP recipe;
- that it is a modified tested recipe;
- that it was independently developed and formally tested;
- what variety/ripeness of plums, jar size, filled-jar count, altitude, or preservation method was actually used.

Similarity of ingredients is not evidence of tested equivalence.

## Smallest Complete Owner Question Set

1. Which exact recipe did Stephanie use? Attach or link the source, edition/version, and any handwritten changes.
2. Was the published `5.6 lb` plum quantity measured before or after setting fruit aside for syrup?
3. What jar size was actually used?
4. How many completely filled jars did the batch actually produce?
5. Was the batch water-bath canned, refrigerated, frozen, or divided among methods?
6. Was pectin used?
7. Were cinnamon, vanilla, almond extract, ginger, bourbon, or any other herbs/spices/extracts/alcohol added? Give amounts and timing.
8. What altitude applies to the actual kitchen?
9. Is the public page intended to provide shelf-stable canning instructions, or should it become a refrigerator/freezer recipe?
10. Who will perform or approve the qualified preservation review, and what credential/organization may be displayed?
11. Should the public batch scaler remain, be limited to an authority-approved batch size, or be removed?

## Implementation-Ready Decision Sheet

| Decision field | Owner answer |
|---|---|
| Exact recipe used (title/source/version/link or attachment) | |
| Stephanie’s modifications to that recipe | |
| Plum weight measured before/after syrup diversion | |
| Actual jar size | |
| Actual number of jars | |
| Actual preservation method | |
| Pectin used? Type/amount? | |
| Lemon juice type and measured amount | |
| Flavor additions, amounts, and timing | |
| Kitchen altitude | |
| Intended public method: shelf-stable / refrigerator / freezer | |
| Qualified reviewer name, credential, and approval method | |
| Approved source citation and link | |
| Approved processing time and altitude table | |
| Approved headspace and jar-size limits | |
| Approved storage claims | |
| Scaler: retain / constrain / remove | |
| Approved author and preservation-review credit | |
| Permission to proceed with Phase 2B implementation | |
