# Sitewide link audit, allegiant.co.uk, 7 September 2026

**Scope:** every published page (207) and post (80) on allegiant.co.uk, all 7 navigation menus (66 items), plus tag and category archives. Every URL in every item's content was extracted and recorded (1,150 or so link instances; 438 unique external targets). Internal links were validated against the live URL inventory pulled the same day.

**Method and limits:** this environment cannot make HTTP requests to the live site or to external domains (network policy), so the audit ran over the WordPress REST API. Internal links are therefore validated with certainty against the actual page and post inventory (publish, private, draft and trash statuses all checked). External links could not be HTTP checked from here; the full deduplicated list is packaged for grokbot to verify with curl (see `grokbot-link-verification-2026-09-07.md`). Two smaller caveats: links held in ACF fields beyond the API's 200 meta key cap on 9 builder pages may not all have been captured (the homepage's known link fields were captured in full), and links rendered by the theme itself (footer, widgets) are outside the API's reach except where they duplicate menu items, which were checked.

A cross check was run with server side content search for every high risk pattern (pension paths, the missing slash URL family, old fee paths); the search results matched the extraction exactly, so confidence in coverage is high.

---

## Priority 1: broken internal links (live 404s for visitors)

### 1.1 The non-discretionary commission page does not exist, and 21 pages link to it

Every one of the 20 car finance commission lender pages under /car-finance-claims/ links to:

`/car-finance-claims/non-discretionary-car-finance-commission-claims-were-you-fully-informed/`

and the homepage links to the same page under its old hub slug. **No page with this slug exists in any status, including trash.** Every "non-discretionary commission" link in the site's main commercial cluster 404s.

Affected: homepage 3397 (card sub link, ACF) plus pages 33400 (MotoNovo), 33427 (Close Brothers), 33449 (Black Horse), 33455 (RCI), 33613 (Blue Motor), 33620 (BMW), 33628 (CA Auto), 33634 (Clydesdale), 33638 (Ford Credit), 33643 (Hyundai), 33647 (Mercedes-Benz), 33652 (Northridge), 33658 (Moneybarn), 33663 (PSA), 33669 (Santander), 33672 (Startline), 33677 (Toyota), 33680 (Volkswagen), 33683 (Vauxhall), 33400 to 33683 all in page content (fixable over the API).

**Decision needed from Ric:** point these at (a) the /car-finance-claims/ hub, (b) the explainer post /2025/08/commission-two-types-of-claims-for-compensation-explained/, or (c) recreate the missing page. Once decided, the 20 lender page links can be fixed over the API in one pass; the homepage copy of the link needs wp-admin (ACF).

### 1.2 Homepage (ACF, wp-admin fixes)

| Broken link on the front page | Correct target |
|---|---|
| `/fraud-scams-and-investments-shams/` (banner/card) | /fraud-scam-form/fraud-scams-and-investments-shams/ |
| `/under-valued-vehicle-write-off-claims/` (banner) | /vehicle-write-off-claim/ |
| `/car-finance-commission-claims-are-you-owed-compensation-for-hidden-commissions/dca-claims-do-you-have-a-discretionary-commission-arrangement-claim/` | /car-finance-claims/dca-claims-do-you-have-a-discretionary-commission-arrangement-claim/ |
| the non-discretionary sub link (see 1.1) | per Ric's decision |
| `https://allegiant.co.ukabout-us/` (video button, missing slash) | https://allegiant.co.uk/about-us/ |
| `https://allegiant.co.ukwp-content/themes/.../trustscore.svg` (Trustpilot image, missing slash) | add the slash |

Six broken or malformed links on the front page alone; all sit in ACF fields, so they are wp-admin fixes (added to the grokbot brief).

### 1.3 Terms of Engagement index page (3137) links to two regulatory documents at wrong slugs

- links `/compliance/terms-of-engagement/terms-of-engagement-fraud-and-scam-claims/`; the real page is `/compliance/terms-of-engagement/terms-of-engagement-fsc/` (6965)
- links `/compliance/terms-of-engagement/terms-of-engagement-insurance-claims/`; the real page is `/compliance/terms-of-engagement/terms-of-engagement-vehicle-write-off-claims/` (25929)

These are customer journeys to regulatory documents (CMCOB relevance), and the index is an ACF page: wp-admin fix.

### 1.4 The old /legal/ tree (site restructured to /compliance/ years ago)

- Page 16 (Website Acceptable Use Policy): links `/legal/privacy-policy/` and `/legal/cookies/`
- Page 17 (Privacy Policy): links `/legal/cookies/`
- Page 6239 (ToE Car Finance Claims): displays `/legal/cancellation` and `/legal/complaints`
- Page 962 (Pre Contractual Information): missing slash variants `co.uklegal/cancellation` and `co.uklegal/complaints`

Unless a legacy 301 covers /legal/* (grokbot to confirm in the redirects plugin), all of these 404. Correct targets: /compliance/privacy-policy/, /compliance/cookies/, /compliance/cancellation/, /compliance/complaints-resolution/. Pages 16, 962 and 6239 are fixable over the API; page 17's instances sit inside Outlook safelinks wrappers in ACF (see 4.1).

### 1.5 Navigation menus

- **Top menu "Frequently Asked Questions" points at page 28 (/faqs/), which is private.** Every visitor clicking it gets a 404. Either publish the FAQ page or remove the menu item.
- **Top menu "Home" points at page 2, the 2017 front page** (/the-unaffordable-high-cost-loan-claim-specialists/), not the current front page. Visitors clicking Home land on a nine year old page which itself carries a malformed link.
- Landing Page Header "Apply Now" and Top "Customer Login" use `allegiantportal.co.uk` / `www.allegiantportal.co.uk` while pages elsewhere use `portal.allegiant.co.uk`; grokbot to verify both domains resolve and agree which is canonical.

### 1.6 Other hard 404s

- Page 5904 (/unaffordable-fee-calculator/) embeds `/band-fee-calculator/embed/`; no band-fee-calculator page exists in any status, so the embed renders broken.
- Post 4252 (the leftover SIPP post) links `/pension-claims/sipp-claims/` (deleted). Moot once 4252 is binned per the pension brief; it is the only remaining content link into the deleted pension estate, which is a clean result.
- Page 35431 (/qbo-callback/) links and JavaScript redirects to `http://localhost:3000/callback`. This is a developer artefact on a published page; noindex (already briefed) is not enough, it should be made private or deleted from public view.

## Priority 2: malformed URLs (missing slash family and typo domains)

All of the following render as literal broken domains (`allegiant.co.ukapply-online` is a non existent domain, not a path):

| URL as published | Where |
|---|---|
| `https://allegiant.co.ukour-process/` | page 2 (old front page) |
| `https://allegiant.co.ukapply-online/` | page 11 (About Us) and post 196 |
| `https://allegiant.co.uklenders/sunny-compensation-claim/` (plus embed variant) | page 188 (oEmbed cache in meta) |
| `https://allegiant.co.ukwp-content/uploads/...300x200.jpeg` | page 324 (guide page image) |
| `https://allegiant.co.uklegal/cancellation` and `.../complaints` | page 962 |
| `https://allegiant.co.ukabout-us/` and `...co.ukwp-content/...trustscore.svg` | homepage 3397 (ACF) |
| `http://www.quickquid.couk` (missing dot) | post 241 |
| `https://financial-ombudsman.org` (missing .uk) | page 6239 (ToE Car Finance) |
| `mailto:helpdesk@allegiant-financeco.uk` (missing dot) | pages 16 and 290; complaints and helpdesk routes on legal pages |
| `https://register.fca.org.uk.` and `https://register.fca.org.uk./` (trailing dot) | pages 821, 25936, 32922; all three are Pre Contract Information documents |
| `https://www.financial-ombudsman.org.uk.` (trailing dot) | page 32922 |
| `tel:+44-116-123` (Samaritans; correct dial string is 116123) | post 5711 |

The FCA register trailing dot links can fail TLS certificate checks in some browsers, and they sit on regulatory disclosure documents; worth fixing promptly. The three PCI pages are ACF (wp-admin); the rest are content (API fixable).

## Priority 3: wrong target links (work, but go to the wrong place)

- Page 6017 (fraud and scam claim thank you): visible text says `scamclaim@allegiant.co.uk` but the mailto actually sends to `pensions@allegiant-finance.co.uk`, a pension alias on the legacy domain, for a service line that no longer exists. Ric to confirm the right alias, then a one line fix.
- Page 32933 (ToE Commission Claims) links its fee schedule to `/insurance-claim-fees/` instead of `/commission-claim-fees/`; page 25936 (PCI Vehicle Write Off) links its fee calculator to `/unaffordable-lending-claim-fees` instead of `/insurance-claim-fees/`. Fee disclosures pointing at the wrong service's fees is a CMCOB accuracy issue.
- Post 34994: the clickable href is right but the visible text shows a different URL (missing the /2024/12/ prefix). Cosmetic.
- Page 32608 links `claim.allegiant.co.uk` where everything else uses `claims.allegiant.co.uk`; grokbot to verify whether the singular host resolves.

## Priority 4: hygiene (not broken, but should not be live)

- **Outlook safelinks wrappers on the Privacy Policy (page 17, ACF):** three links are wrapped in `gbr01.safelinks.protection.outlook.com/...` redirect URLs pasted from email, and each wrapper embeds a staff email address in its tracking parameters. A privacy policy publishing a staff identifier inside tracking URLs is a poor look under UK GDPR; replace with the clean underlying URLs (ico.org.uk, /compliance/data-protection-complaints-handling/, /contact-us/).
- **Gmail redirect wrappers on page 13319 (Tesco Bank):** three FOS decision links are `google.com/url?q=...` Gmail paste artefacts; replace with the direct FOS PDFs.
- **ChatGPT citation artefacts:** six external links carry `?utm_source=chatgpt.com` (five on the Glossary 28241, one on post 35077). They work, but they advertise pasted AI output; strip the parameter.
- **Empty anchors:** post 33813 has four `<a>` tags with no href, post 35089 has five (the insurer write off claim anchors); they render as links but do nothing.
- **about:blank hrefs** on the Shout 85258 text lines (page 28428 and post 5711).
- **http:// internal links** on pages 17, 282, 290 and post 430 (redirect to https, but should be https at source).
- **bit.ly shortener** on page 33348 (write off thank you); shorteners on a regulated journey obscure the destination.
- Page 3561 (/service/) is a published lorem ipsum template page with placeholder links; unpublish.
- Page 28241 (Glossary) and both E-Sign pages give contact details as plain text on the legacy allegiant-finance.co.uk domain.

## Links on the redirect plan (work today, update once 301s land)

- `/write-off-claims/` linked from posts 26045, 26123, 33790
- `/unfair-vehicle-write-off-claims/` linked from page 35135 (Admiral)

Both targets still exist as published pages, so nothing is broken today; once the v2 redirect set goes in, update these four links to /vehicle-write-off-claim/ so they do not chain through a 301.

## External links: 397 unique URLs for grokbot to verify

Cannot be HTTP checked from this environment. Breakdown of the biggest hosts: financial-ombudsman.org.uk 177 (mostly decision PDFs, a known link rot risk since the FOS site restructure), fca.org.uk 39, register.fca.org.uk 7, citizensadvice.org.uk 5, asa.org.uk 5, plus long tail. A further 28 URLs point at Allegiant's own off site infrastructure (portal.allegiant.co.uk 9, unaffordable.allegiant.co.uk 5, claims.allegiant.co.uk 5, allegiant.link 2, allegiantportal.co.uk 3, diesel-claim.uk 1, claim.allegiant.co.uk 1, my.allegiant.co.uk 1, writeoffrefunds.co.uk 1); these carry live claim journeys, so they are first in the verification order. Full list: `link-audit-external-urls-2026-09-07.txt`; verification job: `grokbot-link-verification-2026-09-07.md`.

## Pension deletion snapshot (observed during the audit)

The estate is gone from the published site (207 published pages, none with pension slugs) with two leftovers from the kill list: **page 3793 (SSP Claims) is still published**, now surfacing at /ssp-claims/ because its binned parent no longer prefixes its permalink, and **post 4252 (Quick Read: What is a SIPP) is still published**. Both remain on grokbot's list.

## Fix routing summary

| Route | Items |
|---|---|
| Fixable over the API by Claude (content), on Ric's go ahead | pages 2, 11, 16, 290, 324, 962, 6239, 32933, 32608; posts 196, 241, 1119, 24832, 34994, 5711; page 13319 wrappers; the 20 lender page links once the target is decided |
| wp-admin (ACF/menus/settings), added to grokbot brief | homepage 3397 (6 links), ToE index 3137, PCI pages 821, 25936, 32922, Privacy Policy 17, page 6017 mailto, Top menu FAQ and Home items, portal domain check, qbo-callback visibility, page 3793 and post 4252 binning |
| Decisions for Ric | non-discretionary link target (1.1); right alias for 6017; publish or remove FAQ page; unpublish /service/ and page 2 |
| grokbot verification | 397 external URLs + 28 own infrastructure URLs + /legal/* redirect check |

**Zero fetch errors; all 287 published items were read in full.** No links to the 25 pages Claude binned earlier were found anywhere except post 4252, and no staging URLs are linked in any published content (the 46.101.20.99 staging host appears only in internal guid fields, which visitors never see).
