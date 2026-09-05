# Allegiant WordPress SEO Review (via WordPress MCP)

**Site:** https://allegiant.co.uk
**Review date:** 5 September 2026
**Method:** Read only review through the WordPress MCP connection. The full published page inventory (360 pages), all 79 posts, categories, tags, menus, site settings and the 100 most recent media items were analysed. No changes were made to the live site.

**Limitations:** live crawling of allegiant.co.uk is blocked by this environment's network policy, and Rank Math stores its titles, descriptions and noindex flags in meta fields that are not exposed over the REST API. So canonical tags, robots.txt, the XML sitemap, structured data, Core Web Vitals and per page meta could not be verified directly. Those checks are listed at the end for a follow up pass with Search Console access. Everything else below is verified from site data.

---

## Summary

The commercial core of the site is in decent shape: the claim service hubs are well structured under logical parents, the July 2025 car finance lender build out is consistent and internally linked, and Rank Math Pro is in place. The problems are accumulation and duplication. The site carries roughly 120 stale pension pages from 2021 and 2022, a tail of published test, payment and journey pages that have no business being indexable, at least eight overlapping vehicle write off landing pages, duplicate lender profiles competing across two sections, and a set of quality defects (a published page with no title, junk numeric slugs, a typo in a page title, a weak homepage title). For a site whose rankings depend on Google trusting it as an authority on regulated claims, this tail is dead weight.

---

## 1. Index bloat: pages that should not be indexable

**1.1 (P1) Test pages are live.** "Forms test" (/forms-test/, published 2019), "pensions test" (/pensions-test/, 2021) and "Pay New &#8211; Testing" (/make-payment/, 2020) are published pages. A page titled "Testing" on a payment URL is also a trust problem for any customer who lands on it. Delete or unpublish all three.

**1.2 (P1) Journey and utility pages are published as ordinary pages.** The inventory includes an OAuth callback page ("Finishing QuickBooks sign in" at /qbo-callback/, published 5 September 2026), payment confirmation and failure pages, at least eight thank you pages, "Yoti Success", "Signature Success", "Consent Confirmed", "Address Confirmation", "Unsubscribed", "Application Declined", GC_mandate and GC_mandate_complete. These are conversion plumbing. Each one that gets indexed dilutes the site and can surface in search results in embarrassing ways ("Payment Failed" ranking for the brand name). Verify each carries a Rank Math noindex; any that do not should be set to noindex now. Thank you pages should also be excluded from the sitemap so conversion tracking stays clean.

**1.3 (P2) The pension estate needs a decision.** Around 120 pension respondent profile and pension transfer pages were last touched in late 2021 or early 2022 and are absent from the main navigation. If pension claims are no longer an active service line this is both an SEO and a CMCOB problem, since stale pages invite claims for a service that may not be offered on those terms any more. Either refresh and re-link the section, or consolidate: keep the strongest hub pages, 301 the long tail into them, and retire the rest. Do the same assessment for Tax Claims, Rent To Buy Claims (published 2019, never modified) and the 2018 payday guide page.

---

## 2. Duplication and keyword cannibalisation

**2.1 (P1) Vehicle write off landing pages: eight pages, one intent.** The canonical hub is /vehicle-write-off-claim/ (updated July 2026). Competing with it are /write-off-claims/, /tdc/, /caranalytics/, /wofc/, /vehicle-write-off-total-loss-claims/, /unfair-vehicle-write-off-claims/ and /stolen-vehicle-write-off-claims-nw/. Some are clearly campaign or partner landers. Every one of these that is indexable splits link equity and confuses Google about which page should rank for the write off terms Allegiant is investing in. Pick the canonical page, noindex the campaign landers, and 301 any that are genuine duplicates.

**2.2 (P1) Lender profiles duplicated across sections.** Moneybarn, BMW, Blue Motor, Startline and Santander each have a profile under /unaffordable-lending-claims/unaffordable-claim-profiles/ and a second under /car-finance-claims/. The two page types serve different claim routes, which is legitimate, but Moneybarn even reuses the identical slug "moneybarn-claims" in both trees and Santander has three live pages. Differentiate titles explicitly (affordability claim vs commission claim), cross link each pair, and merge where the content does not genuinely differ.

**2.3 (P2) Straight duplicates to canonicalise.** Two Affiliates pages (/affiliates/ and /affiliates-2/). "Installments" and "Instalments" as separate payment pages. Two identical "Bartholomew Hawkins" pages, one orphaned at the root. Two "Local Authority Pension Transfer Claim" pages. "About Us" and "Who we are". The old front page ("The Unaffordable High Cost Loan Claim Specialists.") and an orphaned "Car Finance Claims: Claim Back What Was Yours." at /32608-2/ are both still live. Each pair needs a canonical choice and a 301 with the Simple 301 Redirects plugin already installed.

**2.4 (P2) Two pre contract trees.** /compliance/pre-contract-information/ holds the ULC, commission, pension and fraud pre contract documents, while /compliance/pre-contractual-information/ holds the tax and vehicle write off ones. Two parallel trees for the same document class is confusing for users, for Google and for whoever maintains them. Consolidate under one parent with redirects. Likewise the fees pages: /our-fees/ (titled "No Cash, No Fee.") and /compliance/our-fees-2/ ("Our Fees") should become one canonical fees hub linking out to the per service fee pages.

---

## 3. On page defects

**3.1 (P1) A published page has no title at all.** Page 35238 at /easy-for-everyone/ has an empty title. It will render as a blank browser tab and Google will invent its own title for it. Give it a title or unpublish it.

**3.2 (P1) A page title contains a typo.** "Claim with Allegiant Finance Servies" at /claims/. That title feeds the SERP snippet for a conversion page. Fix to "Services".

**3.3 (P2) Junk numeric slugs on real pages.** Capital One lives at /7688-2/, Tesco Bank at /13319-2/, plus /32608-2/, /unaffordable-loans-2/, /credit-limit-increases-2/ and /affiliates-2/. The "-2" suffix means the clean slug was already taken when the page was created, which is itself a duplication signal. Rename the slugs (with redirects) or fold the pages into their originals.

**3.4 (P2) Homepage title and tagline.** The homepage title is "Allegiant | A CMC" and the site tagline is " Irresponsible Lending, Car Finance Claim &amp; More." with a leading space. "A CMC" is a term customers do not search for. A title along the lines of "Allegiant: Car Finance, Irresponsible Lending and Write Off Claims" targets the actual queries. Fix the tagline's stray space and singular "Claim" at the same time.

**3.5 (P3) Boilerplate titles on the car finance lender set.** All twenty or so lender pages use the pattern "Lender &#8211; Claim Compensation for Undisclosed Commission Arrangements". The pattern is over 70 characters so the distinctive part survives but the message truncates in results, and every page reads identically. A tighter pattern such as "Lender Car Finance Commission Claims" leaves room for a differentiator.

---

## 4. Taxonomy hygiene

**4.1 (P2) The default category is "Press Releases".** Category 1, the WordPress default that catches any post published without a category, has been renamed "Press Releases" and holds 27 posts. Recent opinion and guide posts (for example "Hard done by? A reality check for the lending industry" and the FCA redress rules explainers) have landed in it, so consumer guides present as company press releases in category archives and feeds. Create a proper default such as "News and Views", or make category selection a publishing checklist item, and recategorise the misfiled posts.

**4.2 (P3) Tag sprawl.** 74 tags exist and 57 of them are attached to one post or none. There are near duplicates ("unaffordable lending", "unaffordable", "irresponsible lending") and a tag whose slug ("write-off") collides with a category slug. Thin tag archives are classic low quality pages. Prune to roughly a dozen meaningful tags, merge the duplicates, and confirm Rank Math sets tag archives to noindex (its default, but worth verifying).

---

## 5. Media and image search

**5.1 (P2) Alt text coverage on editorial images is patchy.** Of the 100 most recent images, around half are decorative icon sets where empty alt text is acceptable. Among the roughly 45 content bearing images, about 18 lack alt text, including blog featured images, FCA logo images, BBC coverage screenshots and homepage hero banners. The July 2025 lender image batch shows the team can do this well (every lender image has descriptive alt text, though note "comission" is misspelt in the Startline alt). Backfill the editorial gaps and fix the typo. This serves accessibility obligations as well as image search.

**5.2 (P3) Filename hygiene.** One live blog image retains an AI generator default filename (Gemini_Generated_Image_...). Rename files descriptively before upload; filenames are an image search signal and appear in page source.

---

## 6. Content strategy

**6.1 (P2) The blog has gone quiet at exactly the wrong moment.** The most recent post is 9 July 2026. The FCA motor finance redress scheme has milestones running through 2026 and 2027, and search demand for eligibility, deadline and payout questions will spike around each one. The March 2026 redress posts show the site can capture these moments. A fortnightly cadence tied to the redress calendar, the write off campaign and the Consumer Duty scams angle is the single highest leverage SEO activity available.

**6.2 (P3) Internal linking for orphaned money pages.** Several conversion relevant pages sit at the root with no parent and no menu presence (PCP Claims, Undervalued Vehicle Write Off Claims variants, the claims packs). Pages Google can only reach through the sitemap rank worse than pages woven into the site. Once the canonical set from section 2 is decided, link each surviving page from its hub.

---

## 7. Checks needing live access (not verifiable via MCP)

A follow up pass with Google Search Console and a browser should confirm: robots.txt contents, XML sitemap coverage and exclusions, per page canonical and noindex status (especially for everything in section 1), Rank Math meta title and description coverage, structured data (Organization, FAQ and Article schema, and Rank Math Pro's schema templates), Core Web Vitals (LiteSpeed Cache and Cloudflare are present, so the plumbing is there), redirect chains from the historic slug changes, and index coverage reports for the pension and utility page tails.

---

## Priority actions

**This week (P1)**
1. Delete the three test pages and title the untitled page at /easy-for-everyone/.
2. Fix the "Servies" typo on /claims/.
3. Verify noindex on every journey, payment, thank you and callback page listed in 1.2.
4. Choose the canonical write off page and noindex or redirect the other seven.
5. Differentiate or merge the duplicated lender profiles.

**This month (P2)**
6. Decide the pension estate's future and implement the consolidation redirects.
7. Canonicalise the straight duplicates (affiliates, instalments, about, fees, pre contract trees) with 301 redirects.
8. Rename junk numeric slugs with redirects.
9. Rewrite the homepage title and tagline.
10. Fix the default category and recategorise misfiled posts. Backfill editorial alt text.
11. Run the Search Console pass in section 7.

**Ongoing (P3)**
12. Restart the blog on a fortnightly redress calendar cadence.
13. Prune tags, tighten lender title patterns, enforce filename and alt text standards on upload.
