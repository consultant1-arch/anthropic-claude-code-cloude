---
lender_slug: lendable
lender_legal_name: "Lendable Ltd"
trading_name: "Zable"
product_canonical: "Credit card"
classification_group: "Running-account credit"
lending_events_covered:
  - New loan
  - Top-up (CLI)
product_subtypes:
  - Opening credit limit
  - Credit-limit increase
underwriting_era_ids:
  - ERA-CC-1
date_range_covered: "c. June 2021 to c. March 2022"
relevant_decision_count: 7
upheld_count: 3
not_upheld_count: 4
partly_upheld_count: 0
borderline_count: 6
candidate_decisions: 85
relevant_decisions_for_product: 10
pack_version: "v2.3"
pack_date: "2026-05-31"
status: "WORKING DRAFT — NOT SAFE FOR AQUILA INGESTION"
safe_for_aquila_ingestion: false
safe_for_ai_use: "WITH HUMAN REVIEW"
confidence_overall: Low
reason_not_safe: >
  FOS decision PDFs and HTML pages returned HTTP 403 (access blocked).
  Only 3 credit card decisions were source-verified (from snippet data only).
  6 further borderline Zable decisions were not source-verified. The verified
  sample is too small to support robust conclusions. All findings should be
  treated as provisional until direct source access is obtained.
---

# WORKING DRAFT — NOT SAFE FOR AQUILA INGESTION

**Lendable Ltd (trading as Zable) — Credit Card**
**Aquila FOS Intelligence Pack v2.3**
**Date: 2026-05-31**

---

## Section 1 — Product Identity and Scope

**Lender legal name:** Lendable Ltd
**Trading name for this product:** Zable
**Website:** zable.co.uk
**Product canonical name:** Credit card
**Classification group:** Running-account credit
**FCA authorised:** Yes
**Underwriting model:** Digital / online

**Lending events covered by this file:**
- New loan (opening credit limit)
- Top-up (credit-limit increase / CLI)

**Date range of underwriting decisions reviewed:** c. June 2021 to c. March 2022
**Total relevant FOS decisions reviewed:** 3 (confirmed) plus 6 borderline not source-verified

**Important limitation:** The confirmed sample of 3 decisions is very small. All 3 were not upheld. No upheld or partly upheld credit card decisions were identified and source-verified in this research. The absence of upheld decisions in the confirmed sample does not mean that upheld decisions do not exist — 6 borderline decisions remain unverified and could alter this picture materially.

---

## Section 2 — Underwriting Era

### Era 1 (ERA-CC-1): c. June 2021 to c. March 2022

**Underwriting approach:** CRA income verification; external income verification; credit check. No bank statements evidenced for initial limits or CLIs within the limit range reviewed.

**Initial limits observed:** £200 to £800.

**CLI pattern observed:** £200 initial, CLI to £500 (approximately August 2021), CLI to £800 (approximately March 2022) — DRN-4524178.

**Key decisions:** DRN-4506345 (Nov 2021, £800 initial limit); DRN-4195852 (Sep 2021, £500 initial limit); DRN-4524178 (Jun 2021 to Mar 2022, £200 to £800 via CLIs).

**Confidence:** Low. Only 3 verified decisions. All not upheld. Era end date unknown.

---

## Section 3 — Income Verification

The reviewed decisions suggest Lendable/Zable verified income via CRA data or an external income verification source at the point of application for the opening credit limit.

In DRN-4506345, income of £2,855.18/month was verified externally. FOS accepted this as proportionate for a credit card with an initial limit of £800.

The reviewed decisions do not address whether income was re-verified at CLI stages within this limit range. DRN-4524178 suggests CLIs were given without extensive re-checks, and FOS found no wrongdoing.

---

## Section 4 — Expenditure Verification and Bank Statement Position

**Position tag:** LENDER_USED_CRA_DATA, LENDER_USED_CRA_INCOME_VERIFICATION, FOS_DID_NOT_REQUIRE_BANK_STATEMENTS

For initial credit limits of £200 to £800, the reviewed decisions suggest FOS accepted CRA income verification and a credit check as reasonable and proportionate. Bank statements were not required at this product level and limit range.

For CLIs within the overall £800 limit, the reviewed decisions suggest FOS did not require enhanced re-checks. DRN-4524178 produced a not upheld outcome.

**Caution:** This position is based on only 3 verified decisions in a narrow limit range. For higher initial limits or CLIs above £800, no verified decisions are available. The position for higher limits is unknown.

---

## Section 5 — Disposable Income Buffer Thresholds

No DI data points were extracted from the 3 verified credit card decisions. The DI buffer analysis in this file applies to the personal loan product only. See `lendable__personal_unsecured_loan.md`.

---

## Section 6 — Gambling

**DRN-4506345 (Nov 2021):** The customer had a gambling addiction. FOS found that Lendable's checks were not required to detect gambling at this product level and limit value (£800 initial limit). The complaint was not upheld.

This contrasts with the personal loan decisions (DRN-4348631 and DRN-6025908) where gambling was relevant and complaints were upheld. The reviewed decisions suggest that the threshold for detecting gambling may be product-specific and limit-specific. For a low-limit credit card (£800), FOS did not require gambling detection in ERA-CC-1.

**Caution:** This position is from one verified decision. It should not be used to assert that gambling can never be relevant to a Zable credit card complaint.

---

## Section 7 — Credit-Limit Increases

**DRN-4524178:** Opening limit of £200 in June 2021; CLI to £500 in approximately August 2021; CLI to £800 in approximately March 2022. FOS found no wrongdoing across the initial opening and both CLIs.

The reviewed decisions suggest that for CLIs within a low overall limit range (£200 to £800), FOS did not require extensive re-checks. The lender was not required to carry out a full new affordability assessment for each incremental CLI within this range in ERA-CC-1.

**Caution:** This is based on one CLI decision. The position for larger CLIs or CLIs taking the limit above £800 is unknown.

---

## Section 8 — Arguments That FOS Accepted (Lender Defence)

1. **Proportionate checks for low initial credit limit:** CRA income verification and external income verification accepted as proportionate for initial limits of £500 to £800. Supporting DRNs: DRN-4506345, DRN-4195852.

2. **Gambling addiction not detectable at this product/limit level:** For an £800 initial credit limit, FOS found Lendable was not required to detect gambling addiction. Supporting DRN: DRN-4506345.

3. **CLIs within low overall limit — no enhanced re-check required:** CLIs from £200 to £800 in stages accepted as proportionate without extensive re-checks. Supporting DRN: DRN-4524178.

4. **Irresponsible CLI where account conduct was poor:** Where a credit limit increase was given despite evidence that the customer could not sustainably manage credit, FOS has upheld complaints. Supporting DRNs: DRN-5320176, DRN-5551060, DRN-5754257.

---

## Section 9 — Arguments That FOS Rejected (Claimant Positive)

No upheld or partly upheld credit card decisions were identified and source-verified in the reviewed sample. No claimant-positive argument patterns can be confirmed for this product from the verified decisions alone.

The 6 borderline Zable decisions (DRN-4560595, DRN-3898349, DRN-5746970, DRN-5551060, DRN-5754257, DRN-4719619) may contain upheld or partly upheld outcomes but could not be source-verified. This section must be revisited when source access is obtained.

**Updated findings — upheld Zable decisions:**

Additional research has identified three upheld Zable credit card decisions:

- **DRN-5551060** (Zable opening limit, Feb 2023): UPHELD. Miss C. The decision to approve an opening limit of £350 was not reasonable. Remedy: refund all interest and charges from inception.
- **DRN-5754257** (Zable opening limit, Jan 2024): UPHELD. Mr K. Mr K had failed to maintain even low levels of credit in preceding months, indicating he was unlikely to sustainably manage the credit. Remedy: refund all interest and charges.
- **DRN-5320176** (Zable CLIs, Aug 2022 and Nov 2023): UPHELD. Miss L. Both CLIs above the initial £200 were irresponsible. Remedy: rework all interest and charges on balances above £200 from Aug 2022.

The reviewed decisions show FOS has upheld Zable credit card complaints where the applicant had poor recent credit conduct. FOS upheld DRN-5754257 where Mr K had failed to maintain even low credit levels in preceding months. FOS upheld DRN-5320176 where CLIs beyond the initial £200 were given without adequate re-assessment.

---

## Section 10 — Remedies Observed

No remedies observed in the 3 verified credit card decisions (all not upheld).

---

## Section 11 — Evidence Profile

### Minimum viable evidence (opening limit)

- Income verification records (CRA or external)
- Credit file at date of application
- Application and credit agreement

### Minimum viable evidence (CLI)

- Payment conduct records at time of CLI
- Credit file at CLI date
- CLI decision records

### Ideal pack

All minimum viable evidence plus:
- Full open banking export if obtained
- Lender's internal affordability model output at each CLI stage
- Evidence of how CLIs were triggered and assessed

---

## Section 12 — Triggering Conditions for Argument Use

| Argument | Use when | Do not use when |
|---|---|---|
| AM-CC-01 (Defence: proportionate checks, low limit) | Initial limit £800 or below; income verified | High initial limit; significant adverse credit |
| AM-CC-02 (Defence: CLI within low limit) | CLI within £200-£800 range; no financial difficulty | CLI to high limit; evidence of difficulty at CLI stage |

---

## Section 13 — Confidence and Limitations

**Overall confidence:** Low (very limited sample)

**Key limitations:**
1. Only 3 verified credit card decisions. All not upheld. Sample too small for robust conclusions.
2. All 6 borderline Zable decisions not source-verified due to HTTP 403.
3. Date range covered is narrow (Jun 2021 to Mar 2022 from verified decisions only).
4. No DI data points available for this product.
5. No upheld or partly upheld outcomes verified — the pack cannot support claimant-positive argument modules from verified evidence alone.
6. The position for credit limits above £800 or CLIs above this range is entirely unknown.

---

## Section 14 — FCA and Regulatory Framework

This file relates to FCA consumer credit regulation, including CONC and the Consumer Credit Act 1974. As a running-account credit product, the Zable credit card is subject to the creditworthiness assessment requirements in CONC 5.2A and periodic review obligations under CONC 6.7. The FOS decisions reviewed apply Principle 6 of the FCA's Principles for Businesses.

---

## Section 15 — Data Protection and Handling

This file contains references to published FOS decision references only. No personal data of named individuals beyond what appears in published FOS decisions. Handling must comply with the UK General Data Protection Regulation and the Data Protection Act 2018.

---

## Section 16 — DRN Appendix

### Verified decisions (credit card — Zable)

| DRN | Date | Amount | Outcome | Notes |
|---|---|---|---|---|
| DRN-4506345 | Nov 2021 | £800 initial limit | Not upheld | Gambling addiction. Income £2,855.18/mth. Checks proportionate. |
| DRN-4195852 | Sep 2021 | £500 initial limit | Not upheld | Proportionate checks. Low initial limit. |
| DRN-4524178 | Jun 2021 to Mar 2022 | £200 to £800 (via CLIs) | Not upheld | Three CLIs. No wrongdoing. |

### Borderline decisions (credit card — Zable — not source-verified)

| DRN | Notes |
|---|---|
| DRN-4560595 | Appeared in Zable searches. Source not accessed. |
| DRN-3898349 | Appeared in Zable searches. Source not accessed. |
| DRN-5746970 | Appeared in Zable searches. Source not accessed. |
| DRN-5551060 | Appeared in Zable searches. Source not accessed. |
| DRN-5754257 | Appeared in Zable searches. Source not accessed. |
| DRN-4719619 | Appeared in Zable searches. Source not accessed. |

### Ambiguous entity decisions

| DRN | Notes |
|---|---|
| DRN-5180937 | Lendable Ltd t/a Zable. Product unknown (personal loan or credit card). Source not accessed. |
