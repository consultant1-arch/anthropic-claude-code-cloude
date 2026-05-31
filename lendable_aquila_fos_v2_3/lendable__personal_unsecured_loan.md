---
lender_slug: lendable
lender_legal_name: "Lendable Ltd"
trading_names:
  - "Lendable"
  - "Autolend"
product_canonical: "Personal / unsecured loan"
classification_group: "Fixed-sum credit"
lending_events_covered:
  - New loan
  - Repeat loan
  - Debt consolidation loan
product_subtypes:
  - Standard personal loan
  - Debt consolidation loan
  - Repeat personal loan
underwriting_era_ids:
  - ERA-PL-1
  - ERA-PL-2
  - ERA-PL-3
date_range_covered: "c. January 2018 to c. August 2025"
relevant_decision_count: 19
upheld_count: 6
not_upheld_count: 10
partly_upheld_count: 2
borderline_count: 3
candidate_decisions: 85
relevant_decisions_for_product: 25
pack_version: "v2.3"
pack_date: "2026-05-31"
status: "WORKING DRAFT — NOT SAFE FOR AQUILA INGESTION"
safe_for_aquila_ingestion: false
confidence_overall: Low
reason_not_safe: >
  FOS decision PDFs and HTML pages returned HTTP 403 (access blocked).
  Source verification of individual decisions was limited to web search
  snippet data. Approximately 29 of 51 candidate DRNs could not be
  source-verified. All findings should be treated as provisional until
  direct source access is obtained.
---

# WORKING DRAFT — NOT SAFE FOR AQUILA INGESTION

**Lendable Ltd — Personal / Unsecured Loan**
**Aquila FOS Intelligence Pack v2.3**
**Date: 2026-05-31**

---

## Section 1 — Product Identity and Scope

**Lender legal name:** Lendable Ltd
**Trading name for this product:** Lendable
**Website:** lendable.co.uk
**Product canonical name:** Personal / unsecured loan
**Classification group:** Fixed-sum credit
**FCA authorised:** Yes
**Underwriting model:** Digital / online, automated income verification

**Lending events covered by this file:**
- New loan (standard personal loan)
- New loan (debt consolidation purpose)
- Repeat loan (subsequent loan to existing customer)

**Date range of underwriting decisions reviewed:** c. January 2018 to c. August 2025
**Total relevant FOS decisions reviewed:** 19 (including 3 with borderline or unclear outcome)

---

## Section 2 — Underwriting Eras

### Era 1 (ERA-PL-1): c. January 2018 to c. December 2020

**Underwriting approach:** CRA-based online income verification tool; credit check; declared income and expenditure. No bank statements routinely requested or evidenced.

**Loan amounts observed:** £1,625 to £7,500.

**Key decisions:** DRN-5290895 (Jan 2018 and Jun 2021); DRN-5252228 (Jun 2019 and Jul 2020); DRN-3388678 (Oct 2020); DRN-4814599 (date not stated).

**Confidence:** Low. Era boundaries are derived from lending dates within reviewed decisions and are approximate.

### Era 2 (ERA-PL-2): c. January 2021 to c. December 2022

**Underwriting approach:** CRA income verification (online tool or automated); credit check; declared income and expenditure. Open banking evidenced in some but not all cases from this era. Larger loan amounts observed.

**Loan amounts observed:** £1,625 to £20,000.

**Key decisions:** DRN-3388217 (Aug 2021); DRN-5369927 (Aug 2021); DRN-5470166 (Sep 2021); DRN-5939888 (Apr 2021); DRN-5488975; DRN-5498270 (Oct 2022); DRN-5735269 (Jul 2022); DRN-4334156 (Mar 2022); DRN-5724292; DRN-4348631 (Jul 2022); DRN-4836857; DRN-5650867; DRN-5937331; DRN-5090740.

**Confidence:** Low. Open banking transition within this era not precisely dated.

### Era 3 (ERA-PL-3): c. 2022 to c. August 2025

**Underwriting approach:** Open banking data obtained and used in underwriting. CRA income verification also evidenced.

**Key decisions:** DRN-6025908 (Aug 2025).

**Confidence:** Very low. Only one verified decision from this era. Findings from ERA-PL-3 should not be relied upon without further source-verified decisions.

---

## Section 3 — Income Verification

### What the reviewed decisions suggest

Lendable's primary income verification method across all eras was an online/automated income verification tool drawing on CRA data. Declared income was taken from the application. In later cases, open banking provided supplementary or primary income data.

In DRN-5290895, bank statements were reviewed as part of the FOS assessment and showed average income of £2,350/month, slightly below declared income. FOS did not treat this discrepancy as determinative. The reviewed decisions suggest that minor income discrepancies do not in themselves render checks disproportionate.

In DRN-3388678 (Oct 2020), income was verified at £6,728/month via an online tool. FOS upheld the complaint because the lender failed to enquire about essential expenditure despite the customer having taken out two short-term loans in the preceding weeks. The failure was characterised as a failure to gather expenditure information, not a failure in income verification.

**What FOS appeared to accept:** CRA-based income verification was generally accepted as proportionate for lower-value loans with no significant risk flags.

**What FOS appeared to require additionally:** Where the customer had recently taken out multiple loans, carried high existing debt, or showed signs of financial difficulty, the reviewed decisions suggest FOS expected the lender to gather further information, including enquiries about essential expenditure or review of transaction-level data.

---

## Section 4 — Expenditure Verification

### What the reviewed decisions suggest

Lendable did not routinely request bank statements. Expenditure appears to have been taken from declared figures or modelled.

In DRN-5498270 (Oct 2022), the FOS investigator reviewed three months of bank statements, finding income of £2,063/month and expenditure of £1,979/month, leaving post-borrowing disposable income of approximately £84/month. The complaint was upheld. The reviewed decisions do not conclusively establish that Lendable obtained those bank statements; the investigator may have obtained them independently as part of the FOS process.

In DRN-3388678 (Oct 2020), FOS upheld the complaint because Lendable had not asked about essential expenditure (living costs, accommodation, bills). This suggests FOS expected at minimum some form of expenditure enquiry, even if not full bank statements, where the risk profile was elevated.

**On comparable facts, FOS considered transaction-level verification reasonable and proportionate where:** the customer had high existing debt, persistent adverse credit card conduct, arrears on a secured loan in the past 24 months, or had taken out multiple loans in the recent past.

---

## Section 5 — Disposable Income Buffer Thresholds

The reviewed decisions provide four data points. These should be treated as indicative only. FOS applied context-sensitive proportionality, not a mechanical threshold.

| DRN | DI (£/mth) | Outcome | Context |
|---|---|---|---|
| DRN-5498270 | ~£84 | Upheld | £3,000 loan, Oct 2022. Credit cards at limit, secured loan arrears. |
| DRN-5488975 | ~£111 | Upheld | Debt consolidation. Cycle of borrowing. |
| DRN-5937331 | ~£500 (post-consolidation) | Not upheld | Saving ~£425/mth. Net DI ~£500/mth. |
| DRN-4814599 | £724.47 | Not upheld | Standard loan. Partial overdraft use. |

**Apparent inadequate range:** £84/month to £111/month or below.
**Apparent adequate range:** Approximately £500/month and above, where a positive debt consolidation benefit is demonstrated.
**Grey zone:** £112/month to £499/month — insufficient data to characterise.

Do not state these as hard thresholds. The reviewed decisions suggest FOS considered the full fact pattern, including existing financial commitments, credit card conduct, and the purpose of the loan.

---

## Section 6 — Bank Statement and Open Banking Position

### ERA-PL-1 (c. 2018-2020)

**Position tag:** LENDER_USED_CRA_DATA, LENDER_USED_CRA_INCOME_VERIFICATION, FOS_DID_NOT_REQUIRE_BANK_STATEMENTS

For lower-value loans in this era (e.g. £1,625 — DRN-3388217), the reviewed decisions suggest FOS accepted CRA income verification and a credit check as proportionate. Bank statements were not required.

For DRN-3388678 (£7,500, Oct 2020), the complaint was upheld but the failure identified was the absence of expenditure enquiry, not the absence of bank statements per se.

### ERA-PL-2 (c. 2021-2022)

**Position tag:** BANK_STATEMENT_POSITION_AMBIGUOUS, FOS_EXPECTED_TRANSACTION_LEVEL_DATA (higher-risk cases)

For standard lower-risk loans, the reviewed decisions suggest FOS did not universally require bank statements. For higher-risk fact patterns (high existing debt, adverse credit, repeat borrowing, larger amounts), on comparable facts FOS considered transaction-level verification reasonable and proportionate.

Open banking was emerging in this era. DRN-4348631 (Jul 2022) suggests that ~£20,000 in gambling transactions in the application month should have been identified.

### ERA-PL-3 (c. 2022-2025)

**Position tag:** LENDER_OBTAINED_OPEN_BANKING, FOS_EXPECTED_TRANSACTION_LEVEL_DATA

DRN-6025908 (Aug 2025): open banking data was obtained but gambling transactions were not identified within that data. FOS upheld. This suggests that obtaining open banking data is not sufficient — it must be adequately analysed.

---

## Section 7 — Repeat Lending

The reviewed decisions contain two partly upheld outcomes involving repeat lending sequences.

**DRN-4836857:** Miss B received four loans from Lendable. FOS found that loans 2, 3, and 4 should not have been given. The complaint was partly upheld. The remedy was removal of interest and charges from loans 2 to 4. Loan 1 was not challenged.

**DRN-5650867:** Miss K received three loans. Loan 3 was upheld as unaffordable. FOS found that Lendable had sufficient information at the loan 3 stage to know it would likely be unaffordable.

**Not upheld counterexamples:** DRN-5290895 (two loans, Jan 2018 and Jun 2021) and DRN-5252228 (two loans, Jun 2019 and Jul 2020) were both not upheld. The reviewed decisions suggest that repeat lending is not automatically challengeable — the position depends on the adequacy of re-assessment at each stage and the customer's financial position at the time of each application.

---

## Section 8 — Debt Consolidation

Debt consolidation loans appear frequently in the reviewed decisions.

**Upheld (DRN-5488975):** Lendable calculated post-borrowing DI of approximately £111/month. FOS found this insufficient to cover discretionary and unexpected costs. A cycle of borrowing was identified. The complaint was upheld despite the consolidation purpose.

**Not upheld (DRN-5937331):** Saving approximately £425/month, net DI approximately £500/month post-consolidation. Checks were found adequate.

**Not upheld (DRN-4334156, DRN-5090740):** Standard debt consolidation outcomes where checks were found adequate.

The reviewed decisions suggest that the consolidation purpose does not automatically support a finding that lending was responsible. FOS considered whether the consolidation produced a meaningful and durable saving and whether post-consolidation DI was sufficient.

---

## Section 9 — Gambling

**DRN-4348631 (Jul 2022):** Approximately £20,000 in gambling transactions in the month of application. Complaint upheld. Remedy: all interest and charges removed from the outset.

**DRN-6025908 (Aug 2025):** Open banking data obtained. Gambling transactions present but not identified or flagged by Lendable's system. Complaint upheld.

The reviewed decisions suggest that where gambling transactions are present in the data available to the lender (whether via open banking or bank statements), FOS may expect the lender to have identified and acted on this. The failure in DRN-6025908 was at the analysis stage, not the data-gathering stage.

---

## Section 10 — Arguments That FOS Accepted (Lender Defence)

1. **Proportionate checks for lower-value loans:** CRA income verification and credit check accepted as proportionate for loans of approximately £1,625 to £5,000 with no significant adverse credit or risk flags. Supporting DRNs: DRN-3388217, DRN-5369927, DRN-5470166, DRN-5939888.

2. **Debt consolidation — material saving and adequate DI:** Where consolidation produced a saving of approximately £425/month and post-consolidation DI of approximately £500/month, FOS accepted checks as adequate. Supporting DRN: DRN-5937331.

3. **DI of £724.47/month adequate:** Not upheld. Partial overdraft use not indicative of financial difficulty. Supporting DRN: DRN-4814599.

4. **Repeat loans — adequate re-assessment at each stage:** Where checks at each repeat application were adequate, FOS did not find the repeat lending irresponsible. Supporting DRNs: DRN-5290895, DRN-5252228.

5. **Minor income discrepancy not determinative:** Average bank statement income slightly below declared income did not render checks disproportionate. Supporting DRN: DRN-5290895.

---

## Section 11 — Arguments That FOS Rejected (Claimant Positive)

1. **DI of ~£111/month adequate:** Rejected. DI insufficient for discretionary and unexpected costs in a debt consolidation context. Supporting DRN: DRN-5488975.

2. **DI of ~£84/month adequate:** Rejected. DI insufficient on 3 months bank statements, with multiple adverse credit card indicators. Supporting DRN: DRN-5498270.

3. **Online income verification alone sufficient — no need to ask about essential expenditure:** Rejected where two or more recent prior loans existed. Supporting DRN: DRN-3388678.

4. **Open banking data obtained — adequate check completed:** Rejected where gambling present in data but not identified. Supporting DRN: DRN-6025908.

5. **Repeat lending re-assessments adequately completed:** Rejected for loans 2, 3, and 4 in a sequence where adequate re-assessment was not demonstrated. Supporting DRNs: DRN-4836857, DRN-5650867.

6. **~£20,000 gambling transactions in application month not detectable:** Rejected. Remedy: all interest and charges removed. Supporting DRN: DRN-4348631.

---

## Section 12 — Remedies Observed

- **DRN-4836857:** Removal of interest and charges from loans 2, 3, and 4.
- **DRN-4348631:** Removal of all interest and charges from the outset.
- **DRN-5498270:** Not stated in detail from snippet. Loan treated as not sustainably affordable.
- **DRN-5488975:** Not stated in detail from snippet.
- **DRN-3388678:** Not stated in detail from snippet.
- **DRN-6025908:** Not stated in detail from snippet.

---

## Section 13 — Evidence Profile

### Minimum viable evidence (claimant-positive case)

- Lender affordability assessment records or CRA income verification output
- Credit file at date of application (showing adverse indicators where present)
- Bank statements or open banking export (3 months minimum) — particularly for higher-risk fact patterns
- Schedule of debts at application date
- Loan agreement(s) and payment schedule

### Ideal pack

All minimum viable evidence plus:
- Full open banking export where obtained by lender
- Lender's internal affordability model output
- Prior loan applications and checks where repeat lending alleged
- Evidence of gambling transactions where gambling issue raised

---

## Section 14 — Triggering Conditions for Argument Use

| Argument | Use when | Do not use when |
|---|---|---|
| AM-PL-01 (Low DI) | Post-borrowing DI below ~£111/mth | DI at or above ~£500/mth with consolidation saving |
| AM-PL-02 (No expenditure enquiry) | Two or more prior loans in preceding weeks | Single first loan; no prior loans |
| AM-PL-03 (Open banking/gambling) | Open banking obtained; gambling present | No gambling; open banking not obtained |
| AM-PL-04 (Repeat lending) | Three or more loans in sequence without re-assessment | First loan only |
| AM-PL-05 (Adverse credit + low DI) | Credit cards at limit, secured loan arrears, DI ~£84/mth | Adverse credit alone without low DI |
| AM-PL-DEF-01 (Defence: proportionate) | Loan below ~£5,000; no risk flags; income verified | DI below ~£111/mth; multiple adverse indicators |
| AM-PL-DEF-02 (Defence: debt consolidation) | Material saving ~£425/mth+; DI ~£500/mth+ post-consolidation | No material saving; DI below ~£111/mth |

---

## Section 15 — Confidence and Limitations

**Overall confidence:** Low

**Key limitations:**
1. FOS website returned HTTP 403 for all direct decision links. No decision PDFs or HTML pages were directly accessed.
2. All findings are based on web search snippet data. Snippets may be incomplete, truncated, or misleading.
3. Approximately 29 of 51 candidate DRNs were not source-verified.
4. DI data points are limited (4 data points). The apparent threshold ranges are illustrative only.
5. Underwriting era boundaries are approximate and derived from lending dates within reviewed decisions.
6. ERA-PL-3 has only one verified decision (DRN-6025908). Findings from this era should not be relied upon without further verification.

---

## Section 16 — FCA and Regulatory Framework

All analysis in this file relates to FCA consumer credit regulation, in particular the Consumer Credit Act 1974 (as amended), the Consumer Credit sourcebook (CONC), and the FCA Handbook principles applicable to consumer credit lending. Lendable Ltd is FCA-authorised and subject to CONC affordability requirements.

The FOS decisions reviewed apply the FCA's standards for creditworthiness assessment under CONC 5 and the overarching obligation to treat customers fairly under Principle 6 of the FCA's Principles for Businesses.

---

## Section 17 — Data Protection and Handling

This file contains references to Financial Ombudsman Service decision references, which are published public documents. No personal data of named individuals is included in this file beyond what appears in published FOS decisions. Handling of this file and any underlying client data must comply with the UK General Data Protection Regulation and the Data Protection Act 2018.

---

## Section 18 — DRN Appendix

### Upheld or partly upheld decisions (personal loan)

| DRN | Date | Amount | Key issue | Outcome |
|---|---|---|---|---|
| DRN-5488975 | Not stated | Not stated | DI ~£111/mth — debt consolidation — cycle of borrowing | Upheld |
| DRN-5498270 | Oct 2022 | £3,000 | DI ~£84/mth — credit cards at limit — secured loan arrears | Upheld |
| DRN-3388678 | Oct 2020 | £7,500 | Essential expenditure not enquired about — two prior recent loans | Upheld |
| DRN-6025908 | Aug 2025 | £4,000 | Open banking obtained — gambling not identified | Upheld |
| DRN-4348631 | Jul 2022 | £3,000 | ~£20,000 gambling transactions in application month | Upheld |
| DRN-4836857 | Not stated | Not stated | Repeat lending — loans 2-4 — inadequate re-assessment | Partly upheld |
| DRN-5650867 | Not stated | Not stated | Repeat lending — loan 3 unaffordable | Partly upheld |

### Not upheld decisions (personal loan)

| DRN | Date | Amount | Key issue | Outcome |
|---|---|---|---|---|
| DRN-3388217 | Aug 2021 | £1,625 | Standard — checks proportionate | Not upheld |
| DRN-5290895 | Jun 2021 | £5,000 (x2) | Repeat loans — checks adequate | Not upheld |
| DRN-5252228 | Jul 2020 | £7,000 / £7,500 | Repeat loans — minimum payments — low utilisation | Not upheld |
| DRN-5369927 | Aug 2021 | £4,500 | Defaults — checks proportionate | Not upheld |
| DRN-5470166 | Sep 2021 | £5,000 | No adverse — all payments made | Not upheld |
| DRN-5939888 | Apr 2021 | £5,650 | Standard — checks reasonable | Not upheld |
| DRN-4814599 | Not stated | Not stated | DI £724.47/mth — partial overdraft | Not upheld |
| DRN-5937331 | Not stated | Not stated | Debt consolidation — DI ~£500/mth — saving ~£425/mth | Not upheld |
| DRN-4334156 | Mar 2022 | £5,000 | Debt consolidation — checks adequate | Not upheld |
| DRN-5090740 | Not stated | Not stated | Debt consolidation — automated income verification | Not upheld |
| DRN-5724292 | Not stated | £5,000 | Marketing email 85% — checks noted as not proportionate but not decisive | Not upheld |

### Borderline decisions (personal loan — outcome unclear)

| DRN | Date | Amount | Notes |
|---|---|---|---|
| DRN-5735269 | Jul 2022 | £20,000 | 21 active accounts; debts ~£35,128; missed payments. Outcome unclear from snippets. |
| DRN-5767395 | Aug 2020 | £6,500 | Debt consolidation. Mr W. Outcome unclear. |
| DRN-5228543 | Not stated | Not stated | Mrs W. Credit cards minimum payments. Investigator upheld. Ombudsman outcome unclear. |
