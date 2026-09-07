# Handoff to grokbot: wp-admin tasks for allegiant.co.uk

**Issued:** 6 September 2026
**Issued by:** Claude (working for consultant1@allegiant.co.uk over the WordPress REST API)
**Scope:** ONLY the tasks below. They all need wp-admin, which Claude cannot reach. Claude is separately completing title, excerpt and internal linking work over the API; do not edit page titles, excerpts or post content, or you will collide with that work.
**Report:** complete the report template at the end and return it to Ric, who will pass it to Claude for verification against the live site.

## Ground rules

1. Use a named admin login, not a shared account. If a new login is created for you, it must be removed or downgraded when this job is done.
2. Make no changes beyond this list. In particular: do not install, remove or update plugins, do not change user accounts, do not publish, edit or delete any content. Those need human sign off.
3. Allegiant is an FCA regulated claims management company. Nothing in this job changes customer facing wording, and you must not improvise any.
4. If a step does not match what you see (missing plugin, missing bulk action, page count different), stop that step, note it in the report, and move on. Do not improvise a workaround.

## Task 1: noindex 28 utility pages (Rank Math PRO bulk action)

In wp-admin go to Pages, All Pages. Select the 28 pages below (search by slug if needed), then in the Bulk Actions dropdown choose the Rank Math action "Set to noindex" and apply. Rank Math will drop them from the XML sitemap automatically.

Background you may need: these pages were noindexed years ago under Yoast, and the flags were lost when the site migrated to Rank Math. Two pages (282 and 2545) still carry dead Yoast noindex meta, which is expected and needs no action.

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

Then noindex these two campaign landers the same way, and find the third by searching "tdc" in the admin Pages search (it matches the slug):

| ID | Slug |
|---|---|
| 27433 | stolen-vehicle-write-off-claims-nw |
| 35069 | caranalytics |
| ? | tdc |

**Verify:** open three of the pages in a browser, view the page source, and confirm the robots meta tag contains noindex. Record which three you checked.

## Task 2: 301 redirects (Simple 301 Redirects plugin, already installed)

Add these redirects. Source paths are relative, destinations are full paths on the same site.

| From | To |
|---|---|
| /write-off-claims/ | /vehicle-write-off-claim/ |
| /vehicle-write-off-total-loss-claims/ | /vehicle-write-off-claim/ |
| /unfair-vehicle-write-off-claims/ | /vehicle-write-off-claim/ |
| /car-finance-claims/santander-finance-claims-reclaim-redress-for-hidden-commission/ | /car-finance-claims/santander-claims/ |

Do NOT redirect /tdc/, /caranalytics/, /stolen-vehicle-write-off-claims-nw/ or /wofc/. The first three are live campaign landers (noindex only, Task 1) and /wofc/ stays indexed.

**Verify:** for each redirect run `curl -sI https://allegiant.co.uk<from-path>` and confirm HTTP 301 with the correct Location header. Record the four response lines.

**Flag before doing the Santander redirect:** check with marketing whether any paid campaign still points at the old Santander URL. If one does, the campaign must be repointed at the same time. Note the answer in the report.

## Task 3: Cookiebot badge overlapping the mobile sticky bar

On mobile the Cookiebot consent renewal badge sits bottom left and covers the sticky bottom bar. Fix with ONE of:

1. Cookiebot dashboard: move the widget to the bottom right corner, or hide the badge and rely on the existing footer renew consent link. Preferred.
2. CSS via the theme or a WPCode snippet: `#CookiebotWidget { left: auto !important; right: 12px !important; }` and, if the badge then covers the bar's button, add right padding to the bar at mobile widths.

Whichever fix is used, the route to renew or withdraw consent must remain reachable (PECR requires withdrawing consent to be as easy as giving it). **Verify:** load the homepage on a mobile viewport and confirm the sticky bar text and button are fully visible. Note which fix was applied.

## Task 4: two quick settings (no judgement calls)

1. Settings, General: set Timezone to Europe/London (it is currently unset, so WordPress runs on UTC).
2. Settings, Discussion: untick "Allow people to submit comments on new posts" and untick the two pingback/trackback options. Existing content is already closed; this only changes the default for future content.

## Task 5: Search Console recrawl requests

In Google Search Console (property allegiant.co.uk), use URL Inspection and Request Indexing for these updated URLs:

- https://allegiant.co.uk/
- https://allegiant.co.uk/car-finance-claims/
- https://allegiant.co.uk/2026/09/car-finance-redress-scheme-suspended/
- https://allegiant.co.uk/2026/03/fca-car-finance-redress/
- https://allegiant.co.uk/2025/06/blackhorse-finance-claims-2025-pcp-compensation/
- https://allegiant.co.uk/2025/08/supreme-court-car-finance-claims/
- https://allegiant.co.uk/2025/08/commission-two-types-of-claims-for-compensation-explained/
- https://allegiant.co.uk/2025/12/car-finance-compensation/
- https://allegiant.co.uk/car-finance-claims/moneybarn-claims/
- https://allegiant.co.uk/unaffordable-lending-claims/unaffordable-claim-profiles/moneybarn-claims/

Also resubmit the XML sitemap (Rank Math generates it at /sitemap_index.xml) so the noindex removals from Task 1 are picked up.

## Explicitly out of scope for grokbot

- User account changes, plugin removals and the session replay tool decision (security review P1 items; humans decide these).
- The site title "Allegiant | A CMC." simplification (pending an owner decision).
- Any content, title or excerpt edit (Claude is doing these over the API).

## Report template (return this, completed)

```
GROKBOT REPORT, allegiant.co.uk, [date/time]
Task 1 noindex: [done/partial/blocked] - pages actioned: [n of 28] - landers: [27433 y/n, 35069 y/n, tdc id=____ y/n] - spot check (3 URLs + robots line seen): ...
Task 2 redirects: [done/partial/blocked] - curl -sI results (4 lines): ... - paid campaign on old Santander URL: [none found / repointed / flagged to marketing]
Task 3 cookiebot: [fix 1/fix 2/blocked] - mobile check result: ...
Task 4 settings: timezone [done], comment defaults [done]
Task 5 search console: [n URLs submitted, sitemap resubmitted y/n]
Deviations or anything unexpected: ...
Login used: [account name] - removed/downgraded after job: [y/n]
```
