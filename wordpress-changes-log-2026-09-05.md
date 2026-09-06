# WordPress Changes Log: 5 September 2026

Actions taken on allegiant.co.uk through the WordPress MCP connection, implementing the P1 items from the SEO review as approved by consultant1@allegiant.co.uk. All deletions used trash, not permanent deletion, so every change is recoverable.

## Changes made

| # | Action | Page or item | Detail |
|---|---|---|---|
| 1 | Trashed | "Forms test" (page 653, /forms-test/) | Test form stub published since 2019. Recoverable from trash. |
| 2 | Trashed | "pensions test" (page 2732, /pensions-test/) | Contained only a form shortcode. Recoverable from trash. |
| 3 | Retitled | "Pay New &#8211; Testing" (page 2545, /make-payment/) | Retitled to "Make a Payment". NOT deleted: the page runs a live Stripe payment template and the URL may be in circulation in customer emails. See open item 2 below. |
| 4 | Retitled and unpublished | Untitled page (page 35238, /easy-for-everyone/) | Empty title and empty content. Titled "Easy for Everyone" and set to draft so it no longer renders publicly. Restore by publishing if it was a work in progress. |
| 5 | Fixed typo | "Claim with Allegiant Finance Servies" (page 33768, /claims/) | Title corrected to "Claim with Allegiant Finance Services". |
| 6 | Fixed alt text typo | Startline Motor Finance image (media 33675) | "comission" corrected to "commission". |

## Not possible via the API: noindex

Rank Math stores its robots directives in the `rank_math_robots` meta key, which is not registered for REST API writes, so noindex could not be set through the MCP connection (confirmed by a test write that the API ignored). This needs two minutes in wp-admin.

**How:** Pages &gt; All Pages, tick the pages below, then use the Rank Math bulk action "Set to noindex" (in the Bulk Actions dropdown, provided by Rank Math PRO). Once noindexed, Rank Math drops them from the XML sitemap automatically.

**Pages to noindex (28):**

| ID | URL | Page |
|---|---|---|
| 35431 | /qbo-callback/ | Finishing QuickBooks sign in |
| 2545 | /make-payment/ | Make a Payment |
| 3559 | /pay/ | Payment |
| 2538 | /payment-confirmation/ | Payment Confirmation |
| 2539 | /payment-failed/ | Payment Failed |
| 1138 | /thank-you-for-the-payment/ | Payment Received. Thank You |
| 6273 | /provident-payment/ | Provident Payment |
| 5806 | /taxhero-payment-information/ | TaxHero Payment Information |
| 2722 | /instalments/ | Instalments |
| 2700 | /installments/ | Installments (also a duplicate: see SEO review 2.3) |
| 2724 | /gc_mandate/ | GC mandate |
| 2726 | /gc_mandate_complete/ | GC mandate complete |
| 23524 | /thank-you/ | Thank You |
| 3098 | /pension-form-thank-you/ | Thank you for your enquiry (pensions) |
| 6017 | /fraud-scam-form-thank-you/ | Thank you for your enquiry (fraud) |
| 3195 | /bdetails-thank-you/ | Thank You. Your Details Have Been Received. |
| 4606 | /car-commissions-thank-you/ | Car Finance Commissions Claim Thank You |
| 33344 | /scam-claim-thank-you/ | Scam &amp; Fraud Claim Thank You |
| 33329 | /unaffordable-thank-you/ | Unaffordable Claim Thank You |
| 4586 | /unaffordable-lending-claims-thank-you/ | Unaffordable Lending Claims Thank You |
| 33348 | /write-off-claim-thank-you/ | Vehicle Write Off Claim Thank You |
| 28374 | /yoti-success/ | Yoti Success |
| 25948 | /signature-success/ | Signature Success |
| 28165 | /consent-confirmed/ | Consent Confirmed |
| 5942 | /address-confirmation/ | Address Confirmation |
| 282 | /opt-out/ | Unsubscribed |
| 6276 | /fraud-scam-declined/ | Application Declined |
| 3194 | /bdetails/ | Details |

### Audit result (6 September 2026): all 28 confirmed indexable, and the reason found

A write of `rank_math_robots` was re-tested on 6 September and the API ignored it again, so the bulk action above stands as the fix. The Rank Math robots meta was then read for every page in the table (readable in edit context even though not writable). Findings:

- **None of the 28 carries a Rank Math noindex.** Every page is either explicitly empty (falls back to the sitewide default, index) or has no robots meta at all. The one partial exception is /instalments/ (2722), which carries nofollow only.
- **The intent to noindex existed and was lost in the Yoast to Rank Math migration.** /make-payment/ (2545) and /opt-out/ (282) still hold orphaned Yoast noindex flags (`_yoast_wpseo_meta-robots-noindex = 1`) that Rank Math never imported and no longer act on. /instalments/ and /pension-form-thank-you/ (3098) hold Yoast nofollow flags, of which only the first was imported. So these journey pages were noindexed years ago and the protection silently fell away when the SEO plugin changed. Worth checking whether anything else was lost in that migration (Rank Math has a re-run importer under Tools).
- Three of the thank you and confirmation pages (23524, 25948, 28165) have custom Rank Math meta descriptions, so someone has actively done SEO on pages that should not be in Google at all. The bulk noindex does not remove descriptions and nothing further is needed there.
- Write off landers from the consolidation map: /stolen-vehicle-write-off-claims-nw/ is page 27433 and /caranalytics/ is page 35069, both on dedicated landing page templates. Their ACF meta is too large for the API to page through to the robots key, and /tdc/ has no searchable text content (ACF built), so check and noindex those three in the same wp-admin pass (in the admin Pages list, searching "tdc" matches the slug).

## Second wave: ranking improvements (same day, approved by consultant1@allegiant.co.uk)

### Title rewrites (live)

The homepage and all 19 car finance commission lender pages were retitled to match real search language. Slugs and URLs are unchanged. Rank Math appends the site name to browser titles automatically, so no brand suffix was included.

| Page | Old title | New title |
|---|---|---|
| Homepage (3397) | Allegiant \| A CMC | Car Finance, Unaffordable Lending &amp; Write Off Claims \| Claims Management Company |
| 19 lender pages under /car-finance-claims/ | "{Lender} &#8211; Claim Compensation for Undisclosed Commission Arrangements" | "{Lender} Commission Claims \| Claims Management Company" or "{Lender} Car Finance Commission Claims \| Claims Management Company" (Black Horse, Blue Motor, BMW FS, CA Auto, Clydesdale, Close Brothers, Ford Credit (FCE Bank), Hyundai Capital, Mercedes-Benz FS, Moneybarn, Northridge (NIIB), PSA, RCI, Santander, Startline, Toyota FS, Vauxhall, Volkswagen FS, MotoNovo) |

Revised the same day at the owner's request: every rewritten title carries the spelled out "Claims Management Company" suffix so the firm's regulatory status is explicit in the title itself (CMCOB status disclosure, and avoiding any impression a lender named page belongs to the lender). The search phrase stays at the front of each title. Note for the team: the site name "Allegiant \| A CMC." is also appended to rendered browser titles by Rank Math, so titles currently disclose twice; if that reads as cluttered in search results, the site title in Settings, General could become simply "Allegiant" now that pages carry the disclosure themselves. That is a team decision, not made here.

### Taxonomy fixes (live)

Created the category "News &amp; Views" (news-views) for opinion and commentary. Moved "Hard done by? A reality check for the lending industry" into it, and moved the two March 2026 redress explainers out of Press Releases into Car Finance Claims (Commission). Post URLs are date based, so nothing changed URL.

### Alt text backfill (live)

Descriptive alt text added to 15 editorial images: the Consumer Duty scams featured image, Hybrid Scams, both March redress images, the write off blog covers, both BBC coverage screenshots, both hero banners, the Car Analytics logos, the Allegiant white logo, the FCA logo, and the Trustpilot stars (which also had a typo, "starts").

### New blog post (PUBLISHED 6 September 2026 on the owner's instruction, comments and pings closed; live at /2026/09/car-finance-redress-scheme-suspended/)

Post 35458, "Car Finance Redress Scheme Suspended: What It Means for Your Claim", drafted in the house plain English voice. Covers the 2 July 2026 partial suspension, the December 2026 / February 2027 Upper Tribunal hearing, what is paused versus what continues, and the 31 August 2027 claim deadline. It states that consumers can complain to their lender directly for free. Facts sourced from FCA statements PS26/3 and "Motor finance scheme partially suspended" plus trade press. DO NOT publish without compliance sign off.

### Write off consolidation decision (for the team to action)

Canonical page: **/vehicle-write-off-claim/** (page 28568). It is the most recently maintained, sits in the main menu, and parents the insurer profiles.

Redirect or noindex map for the rest (redirects via the installed Simple 301 Redirects plugin):

| URL | Action |
|---|---|
| /write-off-claims/ | 301 to /vehicle-write-off-claim/ (duplicate intent) |
| /vehicle-write-off-total-loss-claims/ | 301 to /vehicle-write-off-claim/ (duplicate intent) |
| /unfair-vehicle-write-off-claims/ | 301 to /vehicle-write-off-claim/ (duplicate intent) |
| /stolen-vehicle-write-off-claims-nw/ | Campaign lander: keep live but noindex |
| /tdc/ | Campaign lander: keep live but noindex |
| /caranalytics/ | Partner lander: keep live but noindex |
| /wofc/ | Keep indexed (distinct fact check content) but link it prominently from the canonical page |

Lender duplicates: keep both versions only where the affordability page and the commission page genuinely differ; the commission page under /car-finance-claims/ is canonical for commission searches. Cross link each pair. Merge and redirect the Moneybarn, BMW, Blue Motor and Startline affordability profiles into their commission pages only if the team confirms the affordability route is no longer marketed for those lenders.

### Search snippet disclosure via excerpts (live)

Rank Math's own description meta is not writable over the REST API (confirmed by a second ignored test write). To get the claims management company disclosure into the snippet Google shows, page excerpts were set on the homepage and all 19 lender pages. Rank Math's default description template for pages falls back to the excerpt when no custom description is set, so these should surface as the meta description on the next crawl. Pattern used: "Think {Lender} charged hidden commission on your car finance? Allegiant, an FCA authorised claims management company, can help you claim. No win, no fee." Homepage: "Allegiant is an FCA authorised claims management company. Check car finance commission, unaffordable lending and vehicle write off claims. No win, no fee."

Team verification: check one page in Rank Math (wp-admin) to confirm no custom description overrides the excerpt, and after recrawl spot check a snippet in Google. If a custom Rank Math description already exists on any page, it wins over the excerpt and should be edited there instead. Google may still substitute its own snippet for some queries; the title disclosure covers those cases.

### Paste-ready meta descriptions (Rank Math, wp-admin)

Homepage: "FCA regulated claims specialists. Check car finance commission, unaffordable lending and vehicle write off claims on a no win, no fee basis."

Lender pages, pattern (replace {Lender}): "Think {Lender} charged hidden commission on your car finance? Check if you can claim under the FCA redress scheme. No win, no fee."

### September 2026 SEO context applied

Current guidance emphasises: E-E-A-T signals now gate competitive rankings, especially for finance (YMYL) content; almost all AI Overview citations come from pages already in the top 20, so traditional rankings remain the prerequisite; passage level quality and question format structure win citations; Core Web Vitals still separate sites. Actions for Allegiant beyond this session's changes: named author profiles with credentials on every post, visible "reviewed on" dates on regulated pages, FAQ schema via Rank Math on question heavy pages, and continued FOI based data journalism for links.

### Third wave: internal linking and content accuracy (live)

- The March 2026 "Final Rules" redress explainer (post 35282) had no internal links to any commercial page. Two contextual links to /car-finance-claims/ were added.
- The December 2025 "Car Finance Compensation: Your Questions Answered" post (35126) still presented the scheme as a proposal, quoting the superseded &pound;700 average, 14.2 million agreements and 35% threshold, and predated the July suspension. A dated update box now sits at the top correcting those figures and linking to the final rules explainer, and an unaffordable lending hub link was added. A fuller rewrite is recommended when convenient.
- The June 2026 write off post (35388) also had no internal links; two contextual links to /vehicle-write-off-claim/ were added.
- Two zero use tags were deleted ("Payday Loan Claims Company", "Alliance of Claims Companies").
- Noted for the team: post 35282 embeds its own &lt;style&gt; block that restyles the page body (max-width, margins). It should be moved into the theme or removed, as global CSS inside a post can distort the whole page template.

### Fourth wave: sitewide blog internal linking sweep (live)

49 further published posts now carry one or two contextual links to their matching claim hub, on top of the three done earlier, so 52 posts in total now feed authority to the commercial pages. Roughly 56 links were inserted. Targets used: /car-finance-claims/ (plus deep links to the Black Horse and Clydesdale lender pages), /vehicle-write-off-claim/ (plus the Admiral profile), /fraud-scam-form/fraud-scams-and-investments-shams/, /unaffordable-lending-claims/ (plus deep links to the payday, doorstep, high cost, catalogue, gambling borrowing, repeat loan, car finance and Moneybarn and Morses profile pages), the Amigo Scheme FAQ, /pension-claims/sipp-claims/, /about-us/ and /compliance/services-summary/.

Method: each insertion anchored to exact existing text, so a phrase already inside a link cannot match, which prevented double linking (the "How to Challenge" guide was correctly skipped for already linking to the hub). Deliberately skipped: the formal CP25/27 consultation response, the DSAR explainer, the customer support notice, two opinion essays with no natural anchor, the second charge mortgages post (no mortgage hub exists) and the FSCS explainer. If a mortgage claims hub page is ever created, the second charge post should link to it.

### Fifth wave: car finance commission section fixes and further alt text (live)

Car finance commission hub (/car-finance-claims/):
- Linked the previously dead "reading our blog here" reference to the final rules explainer, and linked the FCA policy statement mention to PS26/3.
- Corrected the outdated Key Facts bullet (was "14 million agreements, proposed scheme"; now the final rules figure of 12.1 million, confirmed scheme).
- Corrected "The FCA is consulting on a potential redress scheme" to reflect the confirmed scheme and the 2 July 2026 partial suspension, keeping the message that consumers can and should still complain now.
- Set an excerpt (search snippet) carrying the claims management company disclosure. Same for the DCA page and the Unfair Commission page.

Unfair Commission page (/car-finance-claims/unfair-commission-claims-car-finance/):
- Fixed a staging domain leak: the fees link pointed at staging.allegiant.co.uk and now points at the live /commission-claim-fees/ page.
- Fixed the title typo ("Car Finance ?" to "Car Finance?").
- Corrected "is consulting on a compensation scheme, but this won't begin until 2026 and details remain unclear" to reflect the confirmed scheme and the tribunal suspension.

Further prudent alt text (18 images): MotoNovo, Black Horse commission and second charge mortgage images, the two accident scene photos on the DVLA post, the GDPR image on the DSAR post, two family images on lending pages, social icons (LinkedIn, X, Facebook x2, YouTube), Trustpilot logo and a second "4 starts" typo fix, and the two PCP icons that carried filename alts. Decorative icon sets were deliberately left with empty alt text, which is correct accessibility practice.

Team notes: footnote 2 on the hub still cites the October 2025 press release next to the corrected 12.1 million figure; worth a tidy in wp-admin.

### Sixth wave: H1 fix and Santander duplicate neutralised (live)

- The commission hub's embedded body H1 was demoted to an H2. The write off hub uses the same template (sectors.php) and carries no body H1, confirming the template renders the page title as the H1, so the embedded one was a duplicate.
- The Santander duplicate page (/car-finance-claims/santander-finance-claims-reclaim-redress-for-hidden-commission/) was found to be a paid landing page frozen in early 2025: it still described the FCA investigation as ongoing, referenced the April 2025 Supreme Court hearing as pending and the December 2025 complaint pause as current, cited three competitor claims firms' websites as references, made aggressive claims ("maximum compensation potential", "nothing to lose and thousands to gain"), and used an FCA register link with a different firm ID (0010X00004MND0QQAX) from the one used elsewhere on the site (0010X00004QBAvNQAX). Its content was replaced with a short, current, compliant notice pointing to the canonical Santander page and the fees page, and it was retitled "Santander Car Finance Claims Update" so it no longer competes for the same searches. TEAM ACTIONS: (1) still add the 301 to /car-finance-claims/santander-claims/ in Simple 301 Redirects, which remains the clean fix; (2) check whether any paid campaigns point at this URL and repoint them at the canonical page; (3) verify which FCA register firm ID is correct for Allegiant and correct the wrong one wherever it appears.

### Seventh wave: FCA register links keyed to the footer FRN (live)

The firm confirmed the authoritative FRN is the one shown in the site footer, 836810. The two remaining FCA register links on the site used a Salesforce record ID rather than the FRN, and the FCA website cannot be reached from this environment to verify record IDs, so both were repointed to the durable FRN keyed register search URL (https://register.fca.org.uk/s/search?q=836810&type=Companies). That URL always resolves to the firm bearing the footer FRN whatever the register's internal record IDs are, and it survives FCA platform changes better than record ID links have.

- Post 24832 ("Who are Allegiant? 5 ways to find out"): the link appeared twice (href and visible text) and both were updated.
- Post 1119 ("Allegiant Finance Services: Full FCA Authorisation Granted", January 2020): this one still used the pre 2019 register URL format (register.fca.org.uk/ShPo_FirmDetailsPage?id=...), which the FCA retired when the register moved to its current platform. The href was updated. The visible link text "https://register.fca.org.uk" was left unchanged and remains accurate.

The second record ID found during the review (0010X00004MND0QQAX, on the old Santander lander only) already has zero live occurrences after that page's content was replaced, so team action (3) from the sixth wave is now closed. No page or post on the site links to the register by record ID any more.

### Open item: Cookiebot badge overlaps the sticky bottom bar on mobile

On mobile the Cookiebot consent renewal badge sits bottom left and covers the sticky bottom bar's text, which also makes the call to action button look pushed to the left. This is a theme level clash that predates this session's work (no change made in this session touches the bar, the badge or any CSS) and it cannot be fixed over the REST API. Two fixes, either works:

1. In the Cookiebot dashboard, move the widget to the bottom right corner, or hide the badge entirely and rely on the existing footer link for renewing consent.
2. Add CSS via the theme or a WPCode snippet: `#CookiebotWidget { left: auto !important; right: 12px !important; }`. If the badge then sits over the bar's button on small screens, also give the bar some right padding at mobile widths.

Keep the renew consent route reachable whichever fix is used, since PECR requires withdrawing consent to be as easy as giving it.

## Open items for the team

1. **Complete the noindex bulk action above** (wp-admin, Rank Math PRO bulk action).
2. **Decide on /make-payment/**: it runs the stripe-custom-3d payment template with no page content. If the URL is no longer referenced in customer emails, invoices or the CRM, trash it; /pay/ appears to be the current payment page. If it is still referenced, keep it and rely on the noindex.
3. **Decide on the "Easy for Everyone" draft** (page 35238): publish with real content or delete the draft.
4. After the noindex pass, spot check two or three of the pages in a browser: view source and confirm the robots meta tag says noindex.
5. **Fix the Cookiebot badge overlap** on the mobile sticky bottom bar (see the open item section above).
6. **Spot check the two repointed register links** (posts 24832 and 1119) in a browser and confirm the FRN search lands on Allegiant Finance Services Ltd, FRN 836810.
