# Phase 2A — Authorship and Publication-Date Governance

**Status:** Inventory complete; owner approval required
**Repository checkpoint:** `ec0abe6`
**Reviewed:** July 25, 2026

## Executive Findings

- No content page has a conventional visible “By,” “Written by,” “Tested by,” or “Reviewed by” credit.
- The About page visibly identifies Stephanie as the storyteller (`about.html:1133–1139`) and its Person schema calls her only “Stephanie” (`about.html:33–48`).
- Structured content authors are inconsistent:
  - 21 Recipe/Article/BlogPosting/WebPage entities use From Bed to Bar as author.
  - 15 use Stephanie (11 by `#stephanie`, 4 as an inline Person named “Stephanie”).
  - 12 CollectionPage/WebPage entities have no author.
- From Bed to Bar is the structured publisher on 33 content entities; 15 content entities have no publisher.
- 28 content entities have `datePublished`; 16 have `dateModified`; 20 have neither.
- Only the four blog posts display a publication date to readers (`blog-post-1.html:951`, `blog-post-2.html:963`, `blog-post-3.html:959`, `blog-post-4.html:950`). The blog index repeats those dates (`blog.html:1079`, `1094`, `1104`, `1114`).
- Many pages contain strong first-person/family experience while either crediting the organization or showing no visible author.

## Route-by-Route Inventory

Abbreviations: **FBTB** = From Bed to Bar organization; **none** = field absent; **FP** = firsthand/family-experience copy is present. “Header JSON-LD” refers to the first structured-data block near the top of the named file.

| Route/file | Visible author | Structured author | Publisher | Visible published / updated | Structured dates | Firsthand? | Mismatch or decision |
|---|---|---|---|---|---|---|---|
| `/` — `index.html` | None | Site/Organization entities; no content author (`:27–55`) | FBTB (`:48`) | None / none | None | Yes (`:1222–1226`) | Family voice has no named author; homepage may not need a byline, but organizational/editorial ownership should be defined. |
| `/404` — `404.html` | None | None | None | None | None | No | Utility page; no byline recommended. |
| `/about` — `about.html` | Stephanie self-identifies, not a byline (`:1133–1139`) | Person “Stephanie”; AboutPage has no author (`:33–74`) | FBTB via WebSite (`:76–84`) | None | None | Yes | Approved full public name and biography are missing. |
| `/bar-essentials` — `bar-essentials.html` | None | FBTB WebPage (`:40–52`) | FBTB | None | Published `2026-05-29`; modified `2026-06-06` | Limited | Organization as author may be acceptable if this is institutional guidance; owner must decide. |
| `/blog` — `blog.html` | None | None on CollectionPage (`:976–993`) | FBTB | Card dates only | None | No | Collection page needs publisher, not necessarily a byline. |
| `/blog-post-1` — `blog-post-1.html` | None | FBTB BlogPosting (`:42–52`) | FBTB | May 28, 2026 / none (`:951`) | Published `2026-05-28`; modified `2026-05-29` | Light FP (`:955`, `992`) | Organization author conflicts with intended Stephanie voice; structured modified date is invisible. |
| `/blog-post-2` — `blog-post-2.html` | None | FBTB BlogPosting (`:41–51`) | FBTB | May 28, 2026 / none (`:963`) | Published `2026-05-28`; modified `2026-05-29` | Mostly instructional | Same authorship/date visibility issue. |
| `/blog-post-3` — `blog-post-3.html` | None | FBTB BlogPosting (`:41–51`) | FBTB | May 28, 2026 / none (`:959`) | Published `2026-05-28`; modified `2026-05-29` | Seasonal journal voice | Relative “right now” copy makes visible authorship/update governance especially important. |
| `/blog-post-4` — `blog-post-4.html` | None | FBTB BlogPosting (`:41–51`) | FBTB | May 28, 2026 / none (`:950`) | Published `2026-05-28`; modified `2026-05-29` | Mostly instructional | Same issue. |
| `/garden-tips` — `garden-tips.html` | None | None on WebPage (`:1214–1235`) | FBTB | None | None | No named FP | Undated “right now” module has no accountable author or review date. |
| `/harvest-hub` — `harvest-hub.html` | None | None on CollectionPage/WebPage graph (`:20–137`) | FBTB | None | None | Strong FP/family copy | Legacy alias and canonical route share content model; no visible author/date. |
| `/herb-hub` — `herb-hub.html` | None | None on CollectionPage/WebPage graph (`:20–136`) | FBTB | None | None | Strong FP/family copy | Likely editorial page but credited only organizationally. |
| `/planting-guide` — `planting-guide.html` | None | No author on HowTo/WebSite graph (`:20–100`) | Organization entity present | None | None | Mostly instructional | Detailed horticultural guidance lacks author, source, and review date. |
| `/recipes` — `recipes.html` | None | None on CollectionPage (`:25–93`) | None on collection entity | None | None | No | Collection page should show publisher/curation model, not necessarily byline. |
| `/thank-you` — `thank-you.html` | None | None | None | None | None | Minor “we” | Utility/conversion page; no byline recommended. |
| `/disclaimer` — `disclaimer.html` | None | None on WebPage; publisher FBTB (`:832–854`) | FBTB | None | None | Organizational legal voice | Legal effective/update date and operator identity require owner/legal decision, not an editorial byline. |

### Guides

| Route/file | Visible author | Structured author / publisher | Visible dates | Structured dates | Firsthand? | Mismatch or decision |
|---|---|---|---|---|---|---|
| `/basil-guide` — `basil-guide.html` | None | Stephanie / FBTB (`:30–55`, Person `:105–108`) | None | `2026-06-10` / `2026-06-18` | Yes | Schema names only “Stephanie”; dates invisible. |
| `/lavender-guide` — `lavender-guide.html` | None | Stephanie / FBTB (`:35–60`, Person `:110–113`) | None | `2026-06-10` / `2026-06-17` | Yes | Same. |
| `/lemon-balm-guide` — `lemon-balm-guide.html` | None | Stephanie / FBTB (`:29–64`, Person `:126–129`) | None | `2026-06-10` / `2026-06-18` | Strong | Undated “new to us/right now” journal content heightens mismatch. |
| `/mint-guide` — `mint-guide.html` | None | Stephanie / FBTB (`:29–64`, Person `:114–117`) | None | `2026-05-29` / `2026-06-18` | Yes | Same. |
| `/plum-guide` — `plum-guide.html` | None | Stephanie / FBTB (`:29–52`) | None | `2026-06-05` / `2026-06-18` | Strong | Northern California orchard narrative has no visible byline/date. |
| `/rosemary-guide` — `rosemary-guide.html` | None | Stephanie / FBTB (`:35–60`, Person `:110–113`) | None | `2026-06-10` / `2026-06-17` | Yes | Same. |
| `/thyme-guide` — `thyme-guide.html` | None | Stephanie / FBTB (`:35–60`, Person `:110–113`) | None | `2026-06-10` / `2026-06-17` | Strong | Same. |

Several guide files (`basil-guide.html`, `lemon-balm-guide.html`, `mint-guide.html`, `plum-guide.html`) lack a canonical link even though their schema declares a URL; that is an out-of-scope technical observation for a later approved phase.

### Harvest-and-preserve guides

| Route/file | Visible author | Structured author / publisher | Visible dates | Structured dates | Firsthand? | Mismatch or decision |
|---|---|---|---|---|---|---|
| `/how-to-harvest-preserve-basil` — `how-to-harvest-preserve-basil.html` | None | Stephanie / FBTB (`:31–65`) | None | `2026-06-19` / `2026-06-19` | Strong | Personal family copy, no visible byline/date. |
| `/how-to-harvest-preserve-lavender` — `how-to-harvest-preserve-lavender.html` | None | Stephanie / FBTB (`:31–35`) | None | `2026-06-18` / `2026-06-19` | Yes | Same. |
| `/how-to-harvest-preserve-mint` — `how-to-harvest-preserve-mint.html` | None | FBTB / FBTB (`:28–48`) | None | `2026-06-05` / none | Light | Organization author differs from newer guide model. |
| `/how-to-harvest-preserve-plums` — `how-to-harvest-preserve-plums.html` | None | FBTB / FBTB (`:28–48`) | None | `2026-06-05` / none | Light | Food-preservation guidance needs a qualified reviewer/source credit, not a fabricated credential. |
| `/how-to-harvest-preserve-rosemary` — `how-to-harvest-preserve-rosemary.html` | None | Stephanie / FBTB (`:35–61`) | None | `2026-06-18` / `2026-06-18` | Yes | Same as newer guides. |
| `/how-to-harvest-preserve-thyme` — `how-to-harvest-preserve-thyme.html` | None | Stephanie / FBTB (`:31–34`) | None | `2026-06-18` / `2026-06-18` | Strong | Same. |

### Recipes, cocktails, mocktails, and preserves

| Route/file | Visible author | Structured author / publisher | Structured date(s) | Firsthand? | Decision |
|---|---|---|---|---|---|
| `/preserves-plum-jam` — `preserves-plum-jam.html` | None | FBTB / FBTB (`:37–50`) | Published `2026-06-06` | Light | Author plus qualified preservation reviewer/source required before promotion. |
| `/recipe-basil-syrup` — `recipe-basil-syrup.html` | None | Stephanie / FBTB (`:45–57`) | Published `2026-06-20` | Strong | Likely candidate for Stephanie byline after approval. |
| `/recipe-lavender-syrup` — `recipe-lavender-syrup.html` | None | Stephanie / FBTB (`:45–57`) | Published `2026-06-19` | Strong | Same. |
| `/recipe-rosemary-syrup` — `recipe-rosemary-syrup.html` | None | Stephanie / FBTB (`:46–58`) | Published `2026-06-12` | Minimal FP | Same, subject to factual ownership. |
| `/recipe-thyme-syrup` — `recipe-thyme-syrup.html` | None | Stephanie / FBTB (`:46–58`) | Published `2026-06-12` | Yes | Same. |
| `/cocktails-garden-mojito` — `cocktails-garden-mojito.html` | None | FBTB / FBTB (`:42–52`) | Published `2026-06-05` | No | Decide whether Stephanie actually developed/tested it. |
| `/mocktails-sparkling-mint-limeade` — `mocktails-sparkling-mint-limeade.html` | None | FBTB / FBTB (`:42–52`) | Published `2026-06-05` | No | Same. |
| `/mocktails-sparkling-plum-mocktail` — `mocktails-sparkling-plum-mocktail.html` | None | FBTB / FBTB (`:40–50`) | Published `2026-06-05` | No | Same. |
| `/recipe-mint-simple-syrup` — `recipe-mint-simple-syrup.html` | None | FBTB / FBTB (`:43–53`) | Published `2026-06-05` | No | Same. |
| `/recipe-plum-simple-syrup` — `recipe-plum-simple-syrup.html` | None | FBTB / FBTB (`:40–50`) | Published `2026-06-06` | Light | Same. |
| `/cocktails-plum-bourbon-sour` — `cocktails-plum-bourbon-sour.html` | None | FBTB / FBTB (header JSON-LD) | None | Light | No structured publication date. |
| `/recipe-cucumber-mint-gin-tonic` — `recipe-cucumber-mint-gin-tonic.html` | None | FBTB / FBTB (header JSON-LD) | None | Yes | No structured date; factual author unknown. |
| `/recipe-garden-herb-gimlet` — `recipe-garden-herb-gimlet.html` | None | FBTB / FBTB (header JSON-LD) | None | Light | Same. |
| `/recipe-hibiscus-paloma` — `recipe-hibiscus-paloma.html` | None | FBTB / FBTB (header JSON-LD) | None | Yes | Same. |
| `/recipe-lavender-lemon-spritz` — `recipe-lavender-lemon-spritz.html` | None | FBTB / FBTB (header JSON-LD) | None | Light | Same. |
| `/recipe-peach-honey-bourbon-smash` — `recipe-peach-honey-bourbon-smash.html` | None | FBTB / FBTB (header JSON-LD) | None | Yes | Same. |
| `/recipe-rosemary-bourbon-sour` — `recipe-rosemary-bourbon-sour.html` | None | FBTB / FBTB (header JSON-LD) | None | Yes | Same. |
| `/recipe-strawberry-basil-smash` — `recipe-strawberry-basil-smash.html` | None | FBTB / FBTB (header JSON-LD) | None | Yes | Same. |

None of these recipe pages visibly displays `Published`, `Updated`, `Tested by`, or `Reviewed by`. No repository evidence proves who personally developed or tested the organization-authored recipes.

## Proposed Editorial Model for Approval

This model is a recommendation, not an approved fact:

- **Primary author:** Stephanie Freitas
- **Publisher:** From Bed to Bar
- **Contributor/operations credit:** Steve Freitas only where his factual contribution is identified
- **Family contributor:** only for a specific, meaningful, approved contribution
- **Qualified reviewer:** named only after that person has actually reviewed the identified content and approved how their credential is displayed

Why this fits the repository: the About page explicitly identifies Stephanie as the project’s originator and first-person voice (`about.html:7`, `33–48`, `1133–1139`), while the site consistently uses From Bed to Bar as the organization/publisher.

## Page-Type Recommendations

| Page type | Visible fields | Structured fields | Notes |
|---|---|---|---|
| Recipes | “By [approved name]”; Published; Updated when substantive | Recipe `author` Person; `publisher` Organization; dates | Add “Tested by” only if a documented testing protocol and tester exist. |
| Plum jam/preservation | Author; source; “Reviewed by” only after actual qualified review; review date | Recipe/Article author, publisher, dates, reviewer only if schema semantics and facts support it | Do not imply a credential or safety approval that was not given. |
| Herb guides | “Written by” or “By”; Published; Updated | Article author Person; publisher Organization; dates | “Written by” suits narrative/editorial guides; “By” is more compact. Choose one system. |
| Harvest-and-preserve guides | Written by; Published; Updated; reviewer/source when safety-relevant | Article author/publisher/dates; reviewer only if factual | Separate editorial authorship from technical review. |
| Blog posts | By; Published; Updated if substantively revised | BlogPosting author/publisher/dates | Retain original publication dates. |
| Static informational pages | Usually no byline; show effective/updated date where trust/legal relevance requires | WebPage/AboutPage; publisher; optional accountable author | About can foreground Stephanie without a formal byline. |
| Homepage | No byline | WebSite publisher Organization | Dated seasonal modules may show module review date/owner. |
| Collection pages | No byline; optional “Curated by” only if useful | CollectionPage publisher | Dates only if collection freshness is claimed. |

## Date Governance Recommendation

1. Preserve the original `datePublished` forever except to correct a documented factual error.
2. Change `dateModified` only for substantive public-content changes, not formatting, navigation, image compression, or typo-only edits.
3. Display “Updated” only when `dateModified` reflects a substantive review.
4. Keep old blog posts’ original publication dates.
5. Add a separate “Reviewed” date for safety-sensitive content if a qualified review occurs; do not overload `dateModified`.
6. Use one approved display format across the site.

## Owner Decision Sheet

| Decision | Owner answer |
|---|---|
| Stephanie’s approved public name | |
| Stephanie’s approved short biography | |
| Stephanie’s approved long biography | |
| Include public location? Exact wording | |
| Include teaching/science background? Exact verified wording | |
| Steve’s approved public role | |
| When Steve receives a byline | |
| When Steve receives contributor/operations credit | |
| Family contributor rule | |
| Are recipes described as “tested”? Under what documented standard? | |
| Which existing recipes did Stephanie develop/test personally? | |
| Preservation reviewer requirement and approved credential display | |
| “By” versus “Written by” by page type | |
| Date display format | |
| Rule for changing `dateModified` | |
| Keep original dates on old posts? | |
| Create an author page? Route | |
| Add author bio boxes? Which page types? | |
| Permission to implement in Phase 2B | |
