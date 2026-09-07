# Handoff to grokbot: pension page deletion (addendum to the v2 brief)

**Issued:** 6 September 2026, by Claude for consultant1@allegiant.co.uk
**Context:** Ric has decided Allegiant's pension claims line is in run off and ALL pension related pages are to be deleted. Claude has already moved 25 of the 149 to the Bin over the API; this brief covers the remaining 124 pages plus 1 blog post. This ADDS to `grokbot-handoff-v2-2026-09-06.md` and amends it as listed at the end.

## Rules

1. **Move to Bin only. Never delete permanently.** Everything must stay recoverable for 30 days.
2. **Bin ONLY what is listed below.** If a listed page cannot be found, or a page you find looks ambiguous, skip it and note it in the report. Never bin anything not on this list.
3. The Bin will already contain 25 pension pages Claude removed today; that is expected.

## Method

The precise way: open each page directly by ID at `/wp-admin/post.php?post=<ID>&action=edit` and use Move to Bin. The faster way for the bulk of them: Pages, Screen Options, set 200 items per page, then search "SIPP Compensation Claims" and bulk Move to Bin everything matching the list, then search "Pension Transfer Claim" and repeat, then pick off the firm name profiles individually against the table. Both methods are fine; the table below is the source of truth either way.

## A. Respondent and transfer profiles to bin (108)

All live under /pension-claims/pension-respondent-profiles/.

| ID | Title |
|---|---|
| 2832 | Blueinfinitas and Auhua Clean Energy SIPP Compensation Claims (a deletion prompt for this one was declined by mistake earlier; it IS to be binned) |
| 2836 | CFD Investments SIPP Compensation Claims |
| 5560 | Channel One Financial Planning LLP, trading as Channel One Financial Services |
| 2791 | Cherish Wealth Management SIPP Compensation Claims |
| 2840 | Cool Blue Samui SIPP Compensation Claims |
| 2842 | Corran Resort & Spa SIPP Compensation Claims |
| 2794 | Cumulus Investment Management SIPP Compensation Claims |
| 2899 | Curtis Banks SIPP Compensation Claims |
| 5572 | DAC Pensions Ltd |
| 5488 | Designed 4 Life Ltd |
| 2844 | DFM Portfolios SIPP Compensation Claims |
| 3066 | Dolphin Pension Trust Transfer Claim |
| 2799 | Douglas Baillie LTD SIPP Compensation Claims |
| 2846 | Eastbridge Investments SIPP Compensation Claims |
| 3055 | Electricity Supply Pension Transfer Claim |
| 2943 | Elysian Fuels SIPP Compensation Claims |
| 4903 | Estate Matters Financial Limited (EMFL / Pension Matters) Transfer Claim |
| 2941 | Ethical Forestry SIPP Compensation Claims |
| 5309 | Fiducia Wealth Solutions, formerly Regen Investments Ltd |
| 3036 | Ford Pension Transfer Claim |
| 2802 | Foreman Financial Services SIPP Compensation Claims |
| 5514 | Forthplus Pensions Ltd |
| 5294 | Fortuna Wealth Management Ltd, Previously Fidelis Wealth Management Ltd, AWG Financial Ltd |
| 2848 | Freedom Bay St Lucia SIPP Compensation Claims |
| 2907 | Freedom SIPP SIPP Compensation Claims |
| 2892 | Glenmuir Investments Ltd and Venture Oils SIPP Compensation Claims |
| 2850 | Gravity Child Care SIPP Compensation Claims |
| 3064 | Greater Manchester Pension Fund Transfer Claim |
| 2822 | Green Oil Plantations Limited SIPP Compensation Claims |
| 2852 | Greyfriars Asset Management and Greyfriars 'Portfolio Six' SIPP Compensation Claims |
| 2930 | Guardian Pension Consultants SIPP Compensation Claims |
| 2909 | Guinness Mahon Trust Corporation SIPP Compensation Claims |
| 5679 | Hamilton Rose Wealth Management Ltd |
| 2804 | HBFS Financial Services SIPP Compensation Claims |
| 5779 | Heritage Pensions Limited |
| 5298 | Hyde Financial Management Ltd, formerly Imperial Wealth Management Ltd |
| 2854 | Hydrology PLC SIPP Compensation Claims |
| 5311 | Independent Benefit Consultancy Ltd |
| 5848 | Integrity IFA Ltd |
| 5313 | Intuitive Associates Ltd trading as Intuitive Financial Associates |
| 2812 | InvestUS SIPP Compensation Claims |
| 3032 | Jaguar Land Rover Pension Transfer Claim |
| 5719 | John Dyer Limited |
| 5929 | Juno Moneta Capital Management Ltd |
| 5825 | Keywood Olley & Associates Ltd, trading as North East Mortgages, EMH Financial Planning |
| 2825 | Kingsway Wealth Management and Cyprus One Limited SIPP Compensation Claims |
| 5484 | Kynaston-Carnoustie Financial Consultancy Ltd |
| 2934 | Liberty SIPP Compensation Claims |
| 3051 | Local Authority Pension Transfer Claim |
| 3053 | Local Authority Pension Transfer Claim (duplicate page, slug ends -2) |
| 2923 | London & Colonial and STM Group SIPP Compensation Claims |
| 2856 | Los Pandos SIPP Compensation Claims |
| 5315 | Mansion Park Ltd, trading as Mansion Park Scotland, David Head MPL, Michael J Alexander |
| 3069 | Marks & Spencer Pension Transfer Claim |
| 2925 | Merchant Investors SIPP Compensation Claims |
| 3071 | Merseyside Pension Fund Transfer Claim |
| 3061 | Mineworkers Pension Scheme Transfer Claim |
| 2896 | Montpelier Pension Administration SIPP Compensation Claims |
| 3077 | Nestle Pension Transfer Claim |
| 2858 | New Earth Recycling SIPP Compensation Claims |
| 3027 | NHS (National Health Service) Pension Transfer Claim |
| 2866 | North West Landfill SIPP Compensation Claims |
| 3080 | Northern Foods Pension Transfer Claim |
| 5317 | Omega Financial Solutions Ltd |
| 2951 | Park First SIPP Compensation Claims |
| 5319 | Pembrokeshire Mortgage Centre Ltd trading as County Financial Consultants |
| 5786 | Philip Griffin & Associates |
| 3044 | Police Pension Transfer |
| 5480 | Portal Financial Services LLP |
| 2870 | Premier Children Services SIPP Compensation Claims |
| 3082 | Premier Foods Pension Transfer Claim |
| 2819 | Premier New Earth Solutions SIPP Compensation Claims |
| 5566 | PWH Financial Planning Ltd |
| 2810 | Quadris Environmental Forestry Fund SIPP Compensation Claims |
| 3049 | Railway Pension Transfer Claim |
| 2878 | Reyker Securities SIPP Compensation Claims |
| 2945 | Rimondi Grand Hotel SIPP Compensation Claims |
| 3039 | Rolls Royce Pension Transfer Claim |
| 2927 | Rowanmoor SIPP Compensation Claims |
| 3030 | Royal Mail / Post Office Pension Transfer Claim |
| 2947 | Salina Seas SIPP Compensation Claims |
| 5795 | SDSC Ltd |
| 5321 | S&M Hughes Limited t/a Crescent Financial |
| 2932 | Stadia Trustees Limited SIPP Compensation Claims |
| 2885 | Stirling Mortimer SIPP Compensation Claims |
| 2887 | Store First SIPP Compensation Claims |
| 2814 | Store First Limited Storage Pods SIPP Compensation Claims |
| 2882 | Strand Capital SIPP Compensation Claims |
| 3085 | Strathclyde Pension Fund Transfer Claim |
| 2816 | Sustainable AgroEnergy SIPP Compensation Claims |
| 2890 | SVS Securities SIPP Compensation Claims |
| 2808 | TailorMade Independent SIPP Compensation Claims |
| 3047 | Teacher Pension Transfer Claim |
| 2911 | The Lifetime SIPP Company SIPP Compensation Claims |
| 5323 | The Ntrust Group Ltd, formerly Ntrust Limited; KBS Financial Planning Ltd and KBS Oakes Financial Planning Limited |
| 2953 | The Resort Group SIPP Compensation Claims |
| 3090 | Tobacco Company Pension Transfer Claim |
| 2806 | Topps Rogers Financial Management SIPP Compensation Claims |
| 5325 | Tramway Financial Management Ltd |
| 3042 | Transport for London (TfL) Pension Transfer Claim |
| 3057 | Universities Superannuation Scheme Pension Transfer Claim |
| 3034 | Vauxhall Pension Claim Transfer |
| 2937 | Walsall Burial SIPP Compensation Claims |
| 3075 | West Midlands Pension Fund Transfer Claim |
| 5327 | West Wales Financial Services Ltd, trading as IWA Financial Solutions, and Mike Powell Mortgages |
| 3073 | West Yorkshire Pension Fund Transfer Claim |
| 5936 | Westbury Private Clients LLP |
| 5836 | Whitebridge Financial Planning Limited |

## B. Hub, section, stray and compliance pages to bin (16)

Bin the children before the parents, in this order.

| ID | URL |
|---|---|
| 2748 | /pension-claims/sipp-claims/ |
| 3794 | /pension-claims/find-salary-pension-transfer-claims/ |
| 3793 | /pension-claims/ssp-claims/ |
| 4097 | /pension-claims/what-is-the-armed-forces-pension-scandal/ |
| 4461 | /pension-claims/pension-respondent-profiles/ |
| 3779 | /pension-claims/ |
| 3171 | /pension-form/ |
| 3098 | /pension-form-thank-you/ |
| 14172 | /pension-and-investment-claim-fees/ |
| 3889 | /pension-investment-claims-affiliate-scheme/ |
| 3000 | /armed-forces-military-pension-transfer-claims/ |
| 2982 | /final-salary-transfer-claims/ |
| 5306 | /bartholomew-hawkins-ltd-trading-as-turris-port-wealth-management-ltd/ |
| 3108 | /service-summary-pic/ |
| 3110 | /compliance/pre-contract-information/pre-contract-information-pic/ |
| 3114 | /compliance/terms-of-engagement/pic/ |

## C. Blog post to bin (1)

Posts screen, not Pages: post 4252, "Quick Read: What is a SIPP" (/2021/08/quick-read-what-is-a-sipp/).

## D. While you are in there

1. Appearance, Menus: remove any menu item pointing at Pension Claims or any page above. Note which menus were touched.
2. If the compliance Services Summary index page links to the pension service summary, note it in the report (do not edit content; Claude will fix links over the API).

## Verify

1. The Bin should now hold 149 pension pages in total (your 124 plus Claude's 25) and 1 post.
2. Spot check three of the deleted URLs in a browser and confirm they return 404. Record which three.
3. Resubmit the sitemap in Search Console (/sitemap_index.xml) so the removals are picked up. This replaces nothing in the v2 brief; it is one extra resubmit.

## Amendments to the v2 brief (grokbot-handoff-v2-2026-09-06.md)

- A1 noindex list: REMOVE 3098 (pension-form-thank-you) from the 31; it is deleted instead. The list becomes 30.
- A2 redirects: REMOVE the row redirecting local-authority-pension-transfer-claim-2 to local-authority-pension-transfer-claim; both are deleted.
- B8 (pension estate report): no longer required; the decision is made and executed.
- Everything else in v2 stands.

## Report lines to add to the v2 report

```
PENSION DELETION: [done/partial/blocked] - pages binned [n of 124] - post 4252 binned [y/n] - skipped/not found: [...] - bin total check [n] - 3 URL spot check: [...] - menus touched: [...] - services summary links pension summary [y/n]
```
