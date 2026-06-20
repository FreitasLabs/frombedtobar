# From Bed to Bar V1.0 Architecture Patch Notes

Conservative HTML-only stabilization patch. No layouts, story text, section order, spacing philosophy, or image placement were intentionally changed.

## Changes Made

1. Lavender syrup URL conflict
   - Updated Lavender Guide links from `lavender-syrup` to `recipe-lavender-syrup`.
   - Updated legacy `lavender-simple-syrup.html` canonical, OG URL, schema IDs, and self-link to point to the current primary `/recipe-lavender-syrup` URL if that legacy file remains deployed.

2. Mint broken mocktail link
   - Updated `mint-guide.html` from `mocktails-mint-limeade` to `mocktails-sparkling-mint-limeade`.

3. Lavender harvest skip-link anchor
   - Updated `how-to-harvest-preserve-lavender.html` main element from `id="main"` to `id="main-content"` to match the existing skip link.

4. Lavender harvest dropdown drift
   - Replaced duplicate Lavender dropdown item with Thyme Guide.

5. Rosemary coming-soon broken links
   - Added an on-page `#coming-soon` anchor to `rosemary-guide.html`.
   - Repointed Rosemary Guide coming-soon links to `#coming-soon` instead of nonexistent recipe pages.
   - Repointed Rosemary Harvest coming-soon links to its existing `#recipes` section instead of nonexistent recipe pages.

6. Recipes OG image path
   - Updated `recipes.html` OG/Twitter image path to `/images/heroes/recipes-hero.png`, matching the page hero reference.

7. Harvest Hub duplicate/orphan handling
   - Added `noindex, follow` to `harvest-hub.html` while preserving its canonical to `/herb-hub`.

8. Sitemap architecture alignment
   - Added missing current production pages:
     - `/how-to-harvest-preserve-rosemary`
     - `/how-to-harvest-preserve-thyme`
     - `/how-to-harvest-preserve-basil`
     - `/how-to-harvest-preserve-lavender`
     - `/recipe-basil-syrup`
     - `/recipe-lavender-syrup`

## Validation

- Checked internal HTML page links and same-page anchors after patching.
- Remaining file/path concerns are image references only; images were not included in the ZIP and were not evaluated per review instructions.
