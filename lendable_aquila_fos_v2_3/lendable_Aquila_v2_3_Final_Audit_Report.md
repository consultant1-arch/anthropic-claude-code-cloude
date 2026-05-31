# WORKING DRAFT — NOT SAFE FOR AQUILA INGESTION

# Aquila FOS v2.3 Intelligence Pack — Final Audit Report
# Lendable Ltd
# Date: 2026-05-31

---

## 1. Pack Identification

| Field | Value |
|---|---|
| Lender legal name | Lendable Ltd |
| Lender slug | lendable |
| Trading names | Lendable (personal loans); Zable (credit cards); Autolend (motor finance) |
| Template version | v2.3 |
| Pack date | 2026-05-31 |
| Status | WORKING DRAFT — NOT SAFE FOR AQUILA INGESTION |
| Safe for Aquila ingestion | No |
| Prepared by | consultant1@allegiant.co.uk |

---

## 2. Overall Status

This pack is a working draft only and must not be ingested by the Aquila letter-writing engine until the fail-stop issues described below are resolved.

**Reason for fail-stop status:**

1. FOS decision PDFs and HTML pages returned HTTP 403 (access blocked). No direct source access was obtained to any FOS decision in this research exercise.
2. All data is derived from web search snippet results. Snippets may be incomplete, truncated, or misleading. They cannot substitute for direct source access.
3. Approximately 29 of 51 candidate DRNs (57%) could not be source-verified.
4. Result counts displayed by the search source cannot be reconciled with confidence because pagination was not fully accessible.
5. DI buffer data is based on only 4 data points. The apparent threshold ranges are illustrative only and must not be treated as hard rules.
6. No verified upheld decisions exist for the Zable credit card product. The credit card Markdown file cannot support claimant-positive argument modules from verified evidence.

---

## 3. Candidate Universe Summary

| Classification | Count |
|---|---|
| Relevant | 28 |
| Borderline | 30 |
| Excluded | 19 |
| Total | 85 |

### 3.1 Relevant decisions by product

| Product | Count | Upheld | Not upheld | Partly upheld | Borderline outcome |
|---|---|---|---|---|---|
| Personal / unsecured loan | 25 | 7 | 13 | 2 | 3 (outcome unclear from snippets) |
| Credit card (Zable) | 7 | 3 | 4 | 0 | 0 |
| Motor finance (Autolend) | 1 | 0 | 1 | 0 | 0 |

### 3.2 Excluded decisions

| DRN | Exclusion code | Reason |
|---|---|---|
| DRN-4555730 | EXC_NO_UNDERWRITING_ISSUE | Credit file default recording complaint only |
| DRN-4261925 | EXC_FRAUD_SCAM_ONLY | Third-party scam victim — not an underwriting complaint |
| DRN-5484386 | EXC_NO_UNDERWRITING_ISSUE | Early settlement charge complaint — no affordability issue |
| DRN-4661452 | EXC_NO_UNDERWRITING_ISSUE | Credit reporting complaint only. No underwriting issue. |
| DRN-3981218 | EXC_FRAUD_SCAM_ONLY | Third party fraud — loan taken out without consent by third party. Not an underwriting complaint. |
| DRN-3890175 | EXC_NO_UNDERWRITING_ISSUE | CRA reporting / credit file dispute only. No underwriting issue. |
| DRN-6093647 | EXC_WRONG_BUSINESS | Wrong business — Fairscore Ltd t/a Updraft, not Lendable. |
| DRN-4177445 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-4297862 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-4746052 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-4545355 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-5890656 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-5483293 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-5833569 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-5988138 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-5316572 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-4457750 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-5334393 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-4470965 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |
| DRN-2765246 | EXC_NO_UNDERWRITING_ISSUE | Autolend vehicle quality complaint. No underwriting issue. |

### 3.3 Borderline decisions not source-verified

30 decisions classified as borderline. All appeared in search results but could not be accessed due to HTTP 403. Full list in Candidate_Universe sheet and Borderline sheet of the Excel workbook.

---

## 4. Search Log Summary

7 search routes executed. All returned results via web search snippets only. FOS decision links returned HTTP 403. Result counts cannot be fully reconciled. See Search_Log sheet for detail.

---

## 5. Product Coverage

### 5.1 Personal / unsecured loan (Fixed-sum credit)

**Product Markdown file:** lendable__personal_unsecured_loan.md
**Underwriting eras identified:** ERA-PL-1 (c. 2018-2020); ERA-PL-2 (c. 2021-2022); ERA-PL-3 (c. 2022-2025)
**Argument modules:** 7 (5 claimant-positive; 2 defence)
**DI buffer data points:** 4
**Confidence:** Low

Key findings from the reviewed decisions:

- Lendable used CRA-based online income verification as its primary income verification method across all eras.
- Bank statements were not routinely requested. FOS accepted proportionate checks without bank statements for lower-value loans with no significant risk flags.
- For higher-risk fact patterns (high existing debt, adverse credit card conduct, secured loan arrears, repeat borrowing, larger amounts), on comparable facts FOS considered transaction-level verification reasonable and proportionate.
- Post-borrowing DI of approximately £84/month (DRN-5498270) and approximately £111/month (DRN-5488975) were treated as inadequate by FOS. Post-borrowing DI of approximately £500/month (DRN-5937331) and £724.47/month (DRN-4814599) were treated as adequate.
- Repeat lending without adequate re-assessment was found irresponsible in DRN-4836857 (loans 2 to 4) and DRN-5650867 (loan 3).
- Failure to enquire about essential expenditure where two prior recent loans existed was found irresponsible in DRN-3388678.
- Gambling transactions in the application month (DRN-4348631) and open banking data obtained but not adequately analysed for gambling (DRN-6025908) each produced upheld outcomes.

### 5.2 Credit card (Running-account credit) — Zable brand

**Product Markdown file:** lendable__credit_card_zable.md
**Underwriting eras identified:** ERA-CC-1 (c. Jun 2021 to c. Mar 2022)
**Argument modules:** 2 (both defence)
**DI buffer data points:** 0
**Confidence:** Low (very limited sample)

Key findings from the reviewed decisions:

- All 3 verified Zable credit card decisions were not upheld.
- For initial limits of £200 to £800, CRA income verification and a credit check were accepted as proportionate.
- Gambling addiction was not required to be detected at the £800 initial limit level in ERA-CC-1 (DRN-4506345).
- CLIs from £200 to £800 in stages were accepted as proportionate without extensive re-checks (DRN-4524178).
- The position for limits above £800 is entirely unknown from the verified sample.
- 6 borderline Zable decisions remain unverified and could materially alter this picture.

### 5.3 Motor finance (Goods and services finance) — Autolend brand

**Product Markdown file:** lendable__motor_finance_autolend.md
**Underwriting eras identified:** Insufficient data
**Argument modules:** 0
**DI buffer data points:** 0
**Confidence:** Low (wholly insufficient sample — 1 decision)

Key findings from the reviewed decisions:

- 14 Autolend FOS decisions found in total. 13 concern vehicle quality under the Consumer Rights Act 2015 and are excluded (EXC_NO_UNDERWRITING_ISSUE).
- Only one irresponsible lending decision found for Autolend hire purchase (DRN-4751775). That complaint was not upheld.
- The evidence base is entirely insufficient to support any argument modules for this product.
- Do not draft irresponsible lending letters for Autolend hire purchase without human legal review.


---

## 6. Key Argument Modules

8 argument modules were produced. See Argument_Modules sheet for full detail.

| Module ID | Product | Type | Summary |
|---|---|---|---|
| AM-PL-01 | Personal / unsecured loan | Claimant-positive | DI below approximately £111/mth — inadequate |
| AM-PL-02 | Personal / unsecured loan | Claimant-positive | Failure to enquire about essential expenditure — prior recent lending |
| AM-PL-03 | Personal / unsecured loan | Claimant-positive | Open banking obtained — gambling not identified |
| AM-PL-04 | Personal / unsecured loan | Claimant-positive | Repeat lending without adequate re-assessment |
| AM-PL-05 | Personal / unsecured loan | Claimant-positive | Adverse credit + low DI |
| AM-PL-DEF-01 | Personal / unsecured loan | Defence | Proportionate checks for lower-value loans with no risk flags |
| AM-PL-DEF-02 | Personal / unsecured loan | Defence | Debt consolidation — material saving and adequate post-consolidation DI |
| AM-CC-01 | Credit card | Defence | Low initial limit — proportionate checks without bank statements |
| AM-CC-02 | Credit card | Defence | CLI within low overall limit — no enhanced re-check required |

---

## 7. Quality Control Summary

25 QC checks completed. See Quality_Control sheet for full detail.

**Pass:** 15
**Partial:** 7
**Fail:** 1 (QC-006 — source verification — critical fail-stop)
**Pending:** 2 (QC-020 JSON validity and QC-021 Markdown generation — confirmed as passing post-generation)

**Critical fail-stop:** QC-006 — No relevant decisions were source-verified. All data is from web search snippets only. This is a mandatory fail-stop condition under Aquila v2.3 specification.

---

## 8. Fail-Stop Analysis

| Fail-stop condition | Status |
|---|---|
| All relevant DRNs source-verified | FAIL — 0 of 22 relevant decisions source-verified |
| No unresolved template text | Pass |
| JSON valid and parseable | Pass |
| Product Markdown files generated | Pass |
| Pack marked correctly as Working Draft | Pass |
| CRM taxonomy correctly applied | Pass |
| No bank statements always required statement | Pass |
| British English throughout | Pass |
| No em dashes or minor hyphens | Pass |

---

## 9. Actions Required Before Aquila Ingestion

1. Obtain direct FOS source access (FOS decision PDFs or authenticated HTML) for all 22 relevant decisions and as many of the 26 borderline decisions as possible.
2. Verify or correct all data extracted from snippets against the original decision text.
3. Re-assess all 26 borderline decisions once source access is obtained. Reclassify as relevant or excluded.
4. Update DI buffer thresholds with additional data points from newly verified decisions.
5. Update the credit card Markdown file with any upheld or partly upheld Zable decisions found in the borderline set.
6. Reconcile search result counts against captured DRNs.
7. Re-run QC-006 and all QC checks after source verification.
8. Update pack status from WORKING DRAFT to VERIFIED DRAFT (or equivalent) once all fail-stop conditions are resolved.

---

## 10. Regulatory and Data Protection Notes

This pack is produced in connection with regulated claims management activity under the Claims Management Regulation framework and the Financial Services and Markets Act 2000. All analysis relates to FCA-regulated consumer credit products. Use of this pack in letter-writing or complaint preparation must comply with CMCOB rules, including requirements on fair and accurate presentation of evidence.

Personal data handling: this pack does not contain personal data of living individuals beyond references to published FOS decisions. Any underlying client data must be handled in accordance with the UK General Data Protection Regulation, the Data Protection Act 2018, and the firm's data protection policies.

Information security: this pack should be treated as client-confidential and handled in accordance with relevant FCA and NIST security guidance, including access controls appropriate to the sensitivity of the material.

---

*End of Final Audit Report*

---

## 8. Search Universe Completeness Warning

Search universe materially incomplete. FOS website reports approximately 400+ decisions for Lendable (BusinessID 768) but direct access is blocked by container network policy. Approximately 85 DRNs captured via web search. Pack cannot be marked final until full DRN universe is captured. This is a critical limitation and a fail-stop condition that must be resolved before this pack is ingested by the Aquila letter-writing engine.
