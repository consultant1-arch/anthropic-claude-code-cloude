# Handoff to grokbot: link verification and link fixes (7 September 2026)

**Issued by:** Claude for consultant1@allegiant.co.uk
**Context:** Claude has completed a sitewide link audit of allegiant.co.uk over the WordPress API (`link-audit-2026-09-07.md`). Internal links are already validated. Two jobs remain that need a machine with open internet access and wp-admin: (A) HTTP verification of the external URL list, and (B) wp-admin link fixes in ACF fields and menus. This ADDS to the outstanding items in `grokbot-handoff-v2-2026-09-06.md` and `grokbot-pension-deletion-2026-09-06.md`.

## Ground rules (same as v2)

1. Allegiant is an FCA regulated claims management company. Do not reword customer facing text; where this brief supplies a URL, change ONLY the URL, character for character.
2. If a step does not match what you see, stop that step, note it, move on.
3. Delete nothing. Part B of this brief edits links only.

---

## PART A: verify the external URL list (report only)

Input file: `link-audit-external-urls-2026-09-07.txt` (three sections: A own infrastructure, B third party, C mailto/tel).

1. For every URL in sections A and B run, politely rate limited (1 request per second is fine):
   `curl -sIL --max-time 20 -A "AllegiantLinkAudit/1.0" -o /dev/null -w "%{http_code} %{url_effective}\n" "<URL>"`
2. Record per URL: final HTTP status, final URL after redirects, and whether the domain failed to resolve or the TLS handshake failed.
3. Classify: OK (200), REDIRECTED (200 after 3xx, note the final URL), BROKEN (404/410, connection failure, DNS failure, TLS failure), SUSPECT (403/429/5xx, likely bot blocking; retry once with a browser User-Agent before classifying).
4. Special attention, expected failures worth confirming:
   - `https://register.fca.org.uk.` and `https://register.fca.org.uk./` (trailing dot; expect TLS or handling problems)
   - `https://financial-ombudsman.org` (missing .uk)
   - `http://www.quickquid.couk` (typo domain; QuickQuid itself is defunct, so also check what quickquid.co.uk does now before recommending a fix)
   - `claim.allegiant.co.uk` versus `claims.allegiant.co.uk` (does the singular resolve?)
   - `allegiantportal.co.uk` and `www.allegiantportal.co.uk` versus `portal.allegiant.co.uk` (which is canonical? do both serve the login?)
   - `allegiant.link` short links and `allegiant.diesel-claim.uk` (do the campaign destinations still exist?)
   - the 177 financial-ombudsman.org.uk decision PDF links (the FOS site has restructured before; sample all of them, they are the biggest link rot risk on the site)
5. Section C (mailto/tel): no HTTP check. Confirm with Ric's team that each mailbox is monitored, and flag `tel:+44-116-123` (Samaritans; the correct dial string is 116123).
6. Also confirm in the Simple 301 Redirects plugin whether any rule covers the old `/legal/*` paths. Report yes or no with the rule list.

Deliverable: the input file annotated with a status per URL, plus a shortlist of BROKEN external links for Ric to decide replacements (Claude will apply content fixes over the API).

## PART B: wp-admin link fixes (execute; ACF fields and menus that the API cannot write)

### B1. Homepage (page 3397, ACF)

| Field (Home Banner / Home Card List) | Change from | Change to |
|---|---|---|
| Banner scam claims link | `https://allegiant.co.uk/fraud-scams-and-investments-shams/` | `https://allegiant.co.uk/fraud-scam-form/fraud-scams-and-investments-shams/` |
| Banner write off link | `https://allegiant.co.uk/under-valued-vehicle-write-off-claims/` | `https://allegiant.co.uk/vehicle-write-off-claim/` |
| Card: DCA sub link | `.../car-finance-commission-claims-are-you-owed-compensation-for-hidden-commissions/dca-claims-do-you-have-a-discretionary-commission-arrangement-claim/` | `https://allegiant.co.uk/car-finance-claims/dca-claims-do-you-have-a-discretionary-commission-arrangement-claim/` |
| Card: non-discretionary sub link | `.../non-discretionary-car-finance-commission-claims-were-you-fully-informed/` | AWAIT RIC'S DECISION (page no longer exists; do not guess) |
| Video button | `https://allegiant.co.ukabout-us/` | `https://allegiant.co.uk/about-us/` |
| Trustpilot image (home_banner_trustpilot_code) | `https://allegiant.co.ukwp-content/themes/allegiant-theme/images/home/hero/trustscore.svg` | insert the missing slash after .uk |

### B2. Compliance ACF pages

1. Page 3137 (Terms of Engagement index): change child link `/compliance/terms-of-engagement/terms-of-engagement-fraud-and-scam-claims/` to `/compliance/terms-of-engagement/terms-of-engagement-fsc/`, and `/compliance/terms-of-engagement/terms-of-engagement-insurance-claims/` to `/compliance/terms-of-engagement/terms-of-engagement-vehicle-write-off-claims/`.
2. Pages 821, 25936 and 32922 (Pre Contract Information documents): replace every `https://register.fca.org.uk.` / `https://register.fca.org.uk./` with `https://register.fca.org.uk/s/search?q=836810&type=Companies` (the firm's register entry, FRN 836810), and on 32922 fix `https://www.financial-ombudsman.org.uk.` by removing the trailing dot.
3. Page 25936: fee calculator link points to `/unaffordable-lending-claim-fees`; change to `https://allegiant.co.uk/insurance-claim-fees/`.
4. Page 32933 (ToE Commission Claims): fee link points to `/insurance-claim-fees/`; change to `https://allegiant.co.uk/commission-claim-fees/`.
5. Page 17 (Privacy Policy): three links are Outlook safelinks wrappers (`gbr01.safelinks.protection.outlook.com/...`, each embedding a staff email address in the tracking parameters). Replace with the clean targets: `https://ico.org.uk/`, `https://allegiant.co.uk/compliance/data-protection-complaints-handling/`, `https://allegiant.co.uk/contact-us/`.
6. Page 6017 (fraud and scam thank you): the mailto sends to `pensions@allegiant-finance.co.uk` while the visible text says `scamclaim@allegiant.co.uk`. AWAIT RIC'S CONFIRMATION of the monitored alias, then align the mailto with it.

### B3. Menus (Appearance, Menus)

1. Top menu, "Frequently Asked Questions" item: points at the private page /faqs/ (404 for visitors). Ric to decide: publish the FAQ page or remove the item. If no decision arrives with this brief, remove the item and note it (a nav 404 is worse than a missing item).
2. Top menu, "Home" item: points at the 2017 front page (/the-unaffordable-high-cost-loan-claim-specialists/). Repoint to the site front page https://allegiant.co.uk/.
3. Note (report only): "Customer Login" uses allegiantportal.co.uk and the Landing Page Header "Apply Now" uses www.allegiantportal.co.uk; reconcile per the Part A finding on which portal domain is canonical.

### B4. Publication state (visibility, not deletion)

1. Page 35431 (/qbo-callback/): a published page that redirects to `http://localhost:3000/callback`. Set it to Private (it is also on the v2 noindex list; Private supersedes that for this page).
2. Page 3561 (/service/): published lorem ipsum template. Set to Draft.
3. STILL OUTSTANDING from the pension brief: bin page 3793 (SSP Claims, now at /ssp-claims/) and post 4252 (Quick Read: What is a SIPP). These were missed in the first pass.

### Out of scope for grokbot

Content link fixes on ordinary pages and posts (the missing slash family, quickquid.couk, financial-ombudsman.org, the &amp;amp; register links, Gmail wrappers on 13319, ChatGPT utm parameters, empty anchors, about:blank, http:// internals): Claude fixes these over the API once Ric gives the go ahead, so leave them alone even where you notice them.

## Report lines to add

```
LINK VERIFICATION: [done/partial] - external checked [n of 397] - own infra checked [n of 28] - BROKEN: [list] - SUSPECT: [list] - FOS PDFs broken [n of 177] - /legal/ redirect rule exists [y/n] - portal canonical domain: [...]
LINK FIXES B1 homepage: [n of 6 done] - non-discretionary target [awaiting/set to ...]
LINK FIXES B2 compliance: [n of 6 done] - deviations: ...
LINK FIXES B3 menus: FAQ [published/removed/awaiting], Home repointed [y/n]
LINK FIXES B4 visibility: qbo-callback private [y/n], /service/ draft [y/n], 3793 binned [y/n], 4252 binned [y/n]
```
