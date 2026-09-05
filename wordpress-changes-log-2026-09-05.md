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

## Open items for the team

1. **Complete the noindex bulk action above** (wp-admin, Rank Math PRO bulk action).
2. **Decide on /make-payment/**: it runs the stripe-custom-3d payment template with no page content. If the URL is no longer referenced in customer emails, invoices or the CRM, trash it; /pay/ appears to be the current payment page. If it is still referenced, keep it and rely on the noindex.
3. **Decide on the "Easy for Everyone" draft** (page 35238): publish with real content or delete the draft.
4. After the noindex pass, spot check two or three of the pages in a browser: view source and confirm the robots meta tag says noindex.
