# Phase 2A — Newsletter Privacy and Subscriber-Data Requirements

**Status:** Repository facts confirmed; Kit-account, business, and legal facts require owner verification
**Reviewed:** July 25, 2026
**No form was submitted during this review.**

## Repository-Proven Facts

### Signup placement and implementation

- **44 pages present a newsletter/signup mechanism.**
  - **43 pages** contain a static inline Kit form posting to `https://app.kit.com/forms/9503567/subscriptions`.
  - `how-to-harvest-preserve-basil.html:2195–2199` loads a separate opaque Kit embed from `https://frombedtobar.kit.com/76f668a3b6/index.js`; its generated fields and account behavior are not contained in the repository.
  - `how-to-harvest-preserve-lavender.html:2028–2031` contains newsletter-styled copy but no form or signup script.
- The 43 static forms use:
  - Kit form ID `9503567`;
  - UID `08e54ce9b8`;
  - `POST` to `https://app.kit.com/forms/9503567/subscriptions`;
  - script `https://f.convertkit.com/ckjs/ck.5.js`;
  - redirect to `https://frombedtobar.com/thank-you`.
- A representative complete implementation is `index.html:1404–1423`. Equivalent markup appears on the 42 other pages listed below.

### Fields and visible language

| Fact | Repository evidence | What is proven |
|---|---|---|
| Email field | `index.html:1416` and equivalent markup on 43 pages | `email_address`, `type="email"`, and `required`. |
| Name field | Search of all 43 static forms | No first-name or last-name input is present in repository markup. |
| Hidden fields | Search of the static form markup | No `<input type="hidden">` appears in the repository forms. Kit may add request fields at runtime; that is not proven here. |
| Submit label | `index.html:1418–1421` | “Subscribe.” |
| Primary promise | `index.html:1406–1407` and shared variants | “Recipes in your inbox, in season.” and “No spam, no filler…” |
| Consent language | All form-adjacent sections | No explicit consent statement, frequency statement, privacy link, or processor disclosure appears next to the forms. |
| Unsubscribe language | Repository-wide search | None found on signup pages or `thank-you.html`. Email-footer behavior is account-level and unknown. |
| Retention/deletion language | Repository-wide search | None found. |
| Privacy policy/link | No `privacy.html`; no `/privacy` in sitemap or footers | No public privacy destination is implemented in the repository. |
| Error container | `index.html:1413` | Kit error list exists; the messages themselves are provider/runtime behavior. |
| Success behavior | `index.html:1411` | Embedded setting says redirect after subscribe; success-message text says “check your email to confirm.” |
| Confirmation page | `thank-you.html:7–9`, `879–881` | Page is `noindex, follow`; tells the user a confirmation email was sent. |
| Robots | `robots.txt:1–6` | `/thank-you` is disallowed; `thank-you.html:7` independently requests `noindex`. |
| Sitemap | `sitemap.xml` | Neither `/thank-you` nor `/privacy` is listed. |

The “check your email to confirm” text suggests an intended confirmation step, but **does not prove that Kit double opt-in is enabled** in the account.

### Embedded configuration visible in the repository

The `data-options` value on the 43 static forms contains:

- `after_subscribe.action = redirect`;
- success URL `https://frombedtobar.com/thank-you`;
- provider integrations for Google, Fathom, Facebook, Segment, Pinterest, SparkLoop, and Google Tag Manager set to `null`;
- `recaptcha.enabled = false`;
- provider “powered by” setting marked `show: true`;
- modal, slide-in, and sticky-bar configuration values, even though the checked pages visibly use inline forms.

Example: `index.html:1411`.

These embedded values prove only what the checked-in embed requests. They do not prove the current Kit-account settings, provider-side changes, email tracking, link tracking, subscriber automations, or cookies set by Kit’s remote JavaScript.

### Other analytics and cookie evidence

- No first-party Google Analytics, Google Tag Manager, Fathom, Meta Pixel, Segment, Pinterest, or SparkLoop script was found in repository HTML.
- The site loads Kit’s remote JavaScript on 43 pages and the separate Kit-hosted embed on one page.
- The repository does not contain a cookie banner, consent manager, cookie policy, or code that documents which cookies those remote scripts set.
- Cookie behavior before or after submission therefore remains **unknown** without runtime/provider review.

### Pages with the static form

| Group | Pages |
|---|---|
| Core/static | `about.html`, `bar-essentials.html`, `disclaimer.html`, `garden-tips.html`, `harvest-hub.html`, `herb-hub.html`, `index.html`, `planting-guide.html`, `recipes.html`, `blog.html` |
| Blog posts | `blog-post-1.html` through `blog-post-4.html` |
| Guides | `basil-guide.html`, `lavender-guide.html`, `lemon-balm-guide.html`, `mint-guide.html`, `plum-guide.html`, `rosemary-guide.html`, `thyme-guide.html` |
| Harvest/preserve | `how-to-harvest-preserve-mint.html`, `how-to-harvest-preserve-plums.html`, `how-to-harvest-preserve-rosemary.html`, `how-to-harvest-preserve-thyme.html` |
| Cocktails/mocktails | `cocktails-garden-mojito.html`, `cocktails-plum-bourbon-sour.html`, `mocktails-sparkling-mint-limeade.html`, `mocktails-sparkling-plum-mocktail.html` |
| Recipes | `preserves-plum-jam.html`, all `recipe-*.html` files currently in the root |

`404.html`, `thank-you.html`, and `how-to-harvest-preserve-lavender.html` do not submit to Kit. The basil harvest page uses the separate Kit embed described above.

## Facts Requiring Kit-Account Verification

The repository cannot establish any of the following. Steve or Stephanie must inspect the live Kit account and record evidence:

- [ ] Double opt-in status for form `9503567`.
- [ ] Identity and configuration of embed UID `76f668a3b6`.
- [ ] Subscriber tags applied by each form.
- [ ] Custom fields stored on subscriber profiles.
- [ ] Automations triggered by signup.
- [ ] Sequences entered and their sending cadence.
- [ ] Confirmation-email sender, subject, content, and destination.
- [ ] Incentive/lead-magnet email and file, if any.
- [ ] Subscriber export practices and storage locations.
- [ ] Retention period for active, unsubscribed, bounced, and suppressed contacts.
- [ ] Access/deletion request process.
- [ ] Suppression and unsubscribe handling.
- [ ] Kit tracking setting.
- [ ] Link-click tracking setting.
- [ ] Email-open tracking setting.
- [ ] Cookies or local storage created before submission.
- [ ] Spam controls and whether reCAPTCHA is disabled account-side.
- [ ] Physical mailing address used in email footers.
- [ ] Any third-party integrations or data sharing beyond Kit.

## Business Facts Requiring Owner Decisions

- Legal/operator name to identify publicly.
- Business or privacy contact email.
- Public physical or mailing address versus legally permitted alternative.
- Countries/regions intentionally targeted.
- Minimum subscriber age, if any.
- Newsletter purpose and realistic frequency.
- Whether subscriber data is used only for the newsletter or for additional marketing/segmentation.
- Who can export subscriber data and where exports may be stored.
- Retention/deletion timetable.
- Response owner and timeframe for privacy requests.
- Whether any provider besides Kit receives subscriber data.

## Page-Placement Recommendation for Phase 2B

This is structural guidance, not final legal language.

1. **`/privacy` page**
   - Identify the operator.
   - List data collected.
   - Explain purposes and lawful/consent basis as approved by counsel.
   - Name Kit as processor/service provider and link to appropriate provider information.
   - Describe tracking/cookies only after runtime/account verification.
   - State retention practice.
   - Explain unsubscribe, access, correction, and deletion paths.
   - Give the approved contact method.
   - State effective and updated dates.

2. **Footer**
   - Add “Privacy” on every public page.
   - Optionally add “Terms” or “Site Use” only if owners/counsel approve a separate document.

3. **Adjacent to every signup**
   - One short, plain-language notice.
   - Link to `/privacy`.
   - State expected email content/frequency and unsubscribe availability.
   - Do not claim double opt-in until verified.

4. **Contact route**
   - Provide a monitored contact method for access/deletion questions.

5. **Cookie notice**
   - Implement only if the verified tools, targeting, and applicable legal review require it. Do not add a generic banner without knowing the actual tracking behavior.

## Representative Placeholder Structures

### Form-adjacent structure

> By subscribing, you agree to receive [frequency/type of email]. We use Kit to process subscriptions. You can unsubscribe [method]. See [Privacy].

Bracketed facts must be replaced with approved facts and legal wording.

### Privacy-page structure

1. Who operates the site
2. Information collected
3. Why it is collected
4. Providers that process it
5. Cookies/tracking actually used
6. Retention and deletion
7. Unsubscribe and suppression
8. Access/correction/deletion requests
9. Children/minimum age, if applicable
10. International/region-specific disclosures, if applicable
11. Contact information
12. Effective and updated dates

## Owner Decision Sheet

### Known repository facts

| Field | Recorded fact |
|---|---|
| Static form count | 43 |
| Separate Kit embed count | 1 |
| Static Kit form ID | `9503567` |
| Static UID | `08e54ce9b8` |
| Collected static field | Required email only |
| Static redirect | `/thank-you` |
| Static embedded reCAPTCHA setting | `false` |
| Repository privacy page | None |
| Form-adjacent privacy link | None |

### Kit-account answers

| Question | Owner answer / evidence |
|---|---|
| Is double opt-in enabled? | |
| What is embed `76f668a3b6` and what fields does it collect? | |
| Tags/custom fields | |
| Automations/sequences | |
| Confirmation/incentive email | |
| Open/link/Kit tracking | |
| Cookies before submission | |
| Spam/reCAPTCHA settings | |
| Unsubscribe/suppression behavior | |
| Data exports and retention | |
| Third-party integrations | |
| Mailing address in emails | |

### Business decisions

| Decision | Owner answer |
|---|---|
| Legal/operator name | |
| Privacy contact | |
| Newsletter purpose and frequency | |
| Intended regions | |
| Minimum age | |
| Retention schedule | |
| Deletion-request process/owner | |
| Other data recipients | |

### Legal-review questions

| Question | Counsel/reviewer answer |
|---|---|
| Required consent wording | |
| Required regional disclosures | |
| Whether a cookie banner is required | |
| Required age language | |
| Mailing-address/privacy-contact treatment | |
| Approved retention and request language | |

### Phase 2B implementation tasks after approval

- Create `/privacy`.
- Add footer privacy links.
- Add approved form-adjacent notices to all 44 signup placements.
- Reconcile the separate basil embed with the standard implementation.
- Update `thank-you.html` wording only if account flow differs.
- Add contact method and optional terms route if approved.
- Add cookie controls only if verified tools and legal review require them.
