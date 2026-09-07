# Handoff to grokbot v2: FULL wp-admin brief for allegiant.co.uk

**Issued:** 6 September 2026
**Issued by:** Claude (working for consultant1@allegiant.co.uk over the WordPress REST API)
**SUPERSEDES** `grokbot-handoff-2026-09-06.md` in full. Work only from this document. If any v1 task was already completed, mark it done in the report rather than repeating it.
**Report:** complete the report template at the end and return it to Ric, who passes it to Claude for verification against the live site.

## Ground rules

1. Use a named admin login, not a shared account. Remove or downgrade it when the job is done.
2. Allegiant is an FCA regulated claims management company (CMCOB applies). Do not write or reword any customer facing text. Where a task supplies text, paste it verbatim.
3. Part A tasks: execute. Part B tasks: investigate and REPORT ONLY, take no action. Nothing outside this document.
4. Do not edit page or post content, titles or excerpts (Claude manages those over the API), except where a Part A task explicitly says otherwise.
5. Do not DELETE anything. Deactivating is allowed where instructed; deletion is not.
6. If a step does not match what you see, stop that step, note it in the report, move on. No improvised workarounds.

---

## PART A: EXECUTE

### A1. Noindex 31 pages (Rank Math PRO bulk action)

Pages, All Pages, tick the pages below, Bulk Actions, Rank Math "Set to noindex". Rank Math drops them from the XML sitemap automatically. Background: these were noindexed under Yoast years ago and the flags were lost in the Yoast to Rank Math migration.

| ID | Slug |
|---|---|
| 35431 | qbo-callback |
| 2545 | make-payment |
| 3559 | pay |
| 2538 | payment-confirmation |
| 2539 | payment-failed |
| 1138 | thank-you-for-the-payment |
| 6273 | provident-payment |
| 5806 | taxhero-payment-information |
| 2722 | instalments |
| 2700 | installments |
| 2724 | gc_mandate |
| 2726 | gc_mandate_complete |
| 23524 | thank-you |
| 3098 | pension-form-thank-you |
| 6017 | fraud-scam-form-thank-you |
| 3195 | bdetails-thank-you |
| 4606 | car-commissions-thank-you |
| 33344 | scam-claim-thank-you |
| 33329 | unaffordable-thank-you |
| 4586 | unaffordable-lending-claims-thank-you |
| 33348 | write-off-claim-thank-you |
| 28374 | yoti-success |
| 25948 | signature-success |
| 28165 | consent-confirmed |
| 5942 | address-confirmation |
| 282 | opt-out |
| 6276 | fraud-scam-declined |
| 3194 | bdetails |
| 27433 | stolen-vehicle-write-off-claims-nw |
| 35069 | caranalytics |
| ? | tdc (find it by searching "tdc" in the admin Pages search, it matches the slug) |

**Verify:** view source on three of them and confirm the robots meta contains noindex. Record which three.

### A2. Redirects and slug fixes (Simple 301 Redirects plugin, installed)

Core redirects:

| From | To |
|---|---|
| /write-off-claims/ | /vehicle-write-off-claim/ |
| /vehicle-write-off-total-loss-claims/ | /vehicle-write-off-claim/ |
| /unfair-vehicle-write-off-claims/ | /vehicle-write-off-claim/ |
| /car-finance-claims/santander-finance-claims-reclaim-redress-for-hidden-commission/ | /car-finance-claims/santander-claims/ |
| /32608-2/ | /car-finance-claims/ |
| /pension-claims/pension-respondent-profiles/local-authority-pension-transfer-claim-2/ | /pension-claims/pension-respondent-profiles/local-authority-pension-transfer-claim/ |

Slug renames (edit the page slug in wp-admin, then add a 301 from the old path):

| Page | Old slug | New slug (only if free) |
|---|---|---|
| 7688 (Capital One profile) | 7688-2 | capital-one |
| 13319 (Tesco Bank profile) | 13319-2 | tesco-bank |

**Before the Santander redirect:** check with marketing whether any paid campaign points at the old URL; if so it must be repointed at the same time. Note the answer.

**Do NOT redirect** /tdc/, /caranalytics/, /stolen-vehicle-write-off-claims-nw/ (live campaign landers, noindex only), /wofc/ (stays indexed), or /instalments/ and /installments/ (live payment plumbing, noindex only, never redirect).

**Verify:** `curl -sI` each redirect, confirm 301 plus correct Location. Record the response lines.

### A3. Banner fix: Cookiebot badge overlapping the mobile sticky bar

On mobile the Cookiebot renewal badge sits bottom left and covers the sticky bottom bar's text, pushing the call to action visually off centre. Apply ONE fix:

1. Preferred: in the Cookiebot dashboard move the widget to the bottom right corner, or hide the badge and rely on the footer renew consent link.
2. Otherwise CSS via the theme or a WPCode snippet: `#CookiebotWidget { left: auto !important; right: 12px !important; }` and if the badge then covers the bar's button, add right padding to the bar at mobile widths.

The route to renew or withdraw consent must stay reachable (PECR requires withdrawal to be as easy as consent). **Verify:** load the homepage at a 390px wide viewport and confirm the bar's text and button are fully visible. Note which fix was used.

### A4. Settings (no judgement calls)

1. Settings, General: Timezone to Europe/London (currently unset, so the site runs on UTC).
2. Settings, General: Tagline currently reads " Irresponsible Lending, Car Finance Claim &amp; More." with a leading space. Replace verbatim with: `Irresponsible Lending, Car Finance Claims & More.`
3. Settings, Discussion: untick "Allow people to submit comments on new posts" and untick both pingback/trackback options.

Do NOT change the Site Title. That is a pending decision for Ric (Part B7).

### A5. Rank Math housekeeping

1. Paste these meta descriptions into Rank Math (page edit screen, Rank Math snippet editor). They override the excerpt fallback already in place.
   - Homepage: `FCA regulated claims specialists. Check car finance commission, unaffordable lending and vehicle write off claims on a no win, no fee basis.`
   - Each of the 19 lender commission pages under /car-finance-claims/ (Black Horse, Blue Motor, BMW FS, CA Auto, Clydesdale, Close Brothers, Ford Credit (FCE Bank), Hyundai Capital, Mercedes-Benz FS, Moneybarn, Northridge, PSA, RCI, Santander, Startline, Toyota FS, Vauxhall, Volkswagen FS, MotoNovo), replacing {Lender}: `Think {Lender} charged hidden commission on your car finance? Check if you can claim under the FCA redress scheme. No win, no fee.`
2. Rank Math, Titles and Meta, Taxonomies: confirm tag archives are set to noindex (the Rank Math default). Record yes or no.
3. Rank Math, Sitemap settings: confirm tag archives are excluded from the sitemap. Record yes or no.

### A6. Security, reversible actions only

1. Plugins: DEACTIVATE (do not delete) these six: Better Search Replace; All-in-One WP Migration; All-in-One WP Migration Unlimited Extension; Download Plugins and Themes from Dashboard; Simple Export Import for ACF Data; ACF Theme Code Pro; and WP Data Logger. If the site misbehaves after any single deactivation, reactivate that one and note it.
2. Search wp-content (including uploads and ai1wm-backups) for `.wpress` files and any full site export archives. Do not delete; list every file found with its path, size and date in the report. These contain the full database and are a breach risk if crawlable.
3. Note in the report the last Wordfence scan date and whether it reported issues. Do not change Wordfence settings.

### A7. Google Search Console

1. URL Inspection, Request Indexing for: the homepage, /car-finance-claims/, /vehicle-write-off-claim/, /2026/09/car-finance-redress-scheme-suspended/, /2026/03/fca-car-finance-redress/, the Black Horse guide (/2025/06/... blackhorse), /2025/08/supreme-court-car-finance-claims/, /2025/08/commission-two-types-of-claims-for-compensation-explained/, /2025/12/car-finance-compensation/, and /unaffordable-lending-claims/unaffordable-claim-profiles/moneybarn-claims/.
2. Resubmit the sitemap at /sitemap_index.xml (picks up the 41 retitled lender profiles and the noindex removals without individual requests).
3. Export the Coverage/Indexing report and attach it to your report, so the pension page tail and utility pages can be reviewed against reality.

---

## PART B: CHECK AND REPORT ONLY (no changes without Ric's named approval)

### B1. Consent cold browser test (PECR)
Fresh browser profile, load the homepage, decline consent, and record whether any of these fire anyway: Clarity, Mouseflow, Google Ads/GTM marketing tags, Meta, TikTok. Repeat once after accepting. Report what fired in each state.

### B2. Users
List every account with its role and last login. Flag: all eight accounts are currently administrators, including the shared "Claims Team" (sales@allegiant-finance.co.uk) login from 2017. Recommend a role per account for Ric to approve. Change nothing.

### B3. Session replay tools
Both Microsoft Clarity and Mouseflow are active on a site handling claims enquiries. Report which is actually used by the team, whether input masking is on in each, and recommend which to keep. Change nothing.

### B4. Duplicate compliance and content pages (canonical decisions needed)
Report current state of each pair so Ric can pick canonicals, then redirects happen in a later pass: /compliance/pre-contract-information/ vs /compliance/pre-contractual-information/ trees; /our-fees/ vs /compliance/our-fees-2/; /affiliates/ vs /affiliates-2/; About Us vs Who We Are; the two QuickQuid pages (22887 and 212); the old front page and any other orphaned landers you find. These are regulatory documents, so no bot chooses the surviving version.

### B5. Drafts and trash inventory
List the 14 draft pages, 5 private pages, and everything in trash, with ages. Recommend keep or delete per item. Delete nothing.

### B6. Admin notification email
Settings, General shows sales@allegiant-finance.co.uk (legacy domain, generic alias). Report it and ask Ric which monitored alias should replace it. Change nothing.

### B7. Site title decision
Site Title is "Allegiant | A CMC." and is appended to every rendered page title, which now discloses CMC status twice on the rewritten pages. Options for Ric: shorten to "Allegiant", or leave as is. Report only.

### B8. Pension estate
Roughly 120 pension profile pages last touched 2021 to 2022. Report the count and whether the pension claims line is still marketed, so Ric can decide refresh versus consolidate.

---

## Decisions parked for Ric (grokbot must not action these)

1. Publish sign off for draft post 35653 ("not owed" decisions explainer), plus a featured image choice.
2. /pcp-commission-claimspack/: keep indexable or add to the noindex list.
3. Site title (B7), admin email alias (B6), Clarity vs Mouseflow (B3), user roles (B2), compliance canonicals (B4), drafts/trash deletions (B5), pension estate (B8).
4. Permanent deletion of the six deactivated plugins once a fortnight passes without issues.

## Report template (return completed)

```
GROKBOT REPORT v2, allegiant.co.uk, [date/time]
A1 noindex: [done/partial/blocked] - [n of 31] - tdc id=____ - spot check (3 URLs + robots line): ...
A2 redirects: [done/partial/blocked] - curl results: ... - slug renames: [7688 y/n, 13319 y/n] - paid campaign on old Santander URL: [none/repointed/flagged]
A3 banner fix: [fix 1/fix 2/blocked] - 390px check: ...
A4 settings: timezone [y/n], tagline [y/n], comment defaults [y/n]
A5 rank math: meta descriptions [n of 20 pasted], tag archives noindex [y/n], sitemap excludes tags [y/n]
A6 security: plugins deactivated [list], issues after deactivation [none/...], export files found [list with paths/sizes/dates], wordfence last scan [date/result]
A7 search console: [n URLs requested], sitemap resubmitted [y/n], coverage export attached [y/n]
B1 consent test: declined state fired [...], accepted state fired [...]
B2 users: [table: account/role/last login] + recommendations
B3 replay tools: [findings + recommendation]
B4 duplicates: [state of each pair]
B5 drafts/trash: [inventory + recommendations]
B6 admin email: [current value]
B7 site title: [noted]
B8 pensions: [count + marketing status]
Deviations: ...
Login used: [name] - removed/downgraded: [y/n]
```
