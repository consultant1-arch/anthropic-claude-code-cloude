# WORKING DRAFT — NOT SAFE FOR AQUILA INGESTION

# Aquila FOS v2.3 Intelligence Pack — QC Certificate
# Lendable Ltd
# Date: 2026-05-31

---

## Overall Status: PARTIAL PASS — WORKING DRAFT

**Safe for Aquila ingestion:** NO

**Reason:** One critical fail-stop gate failed (QC-006 — source verification). All relevant FOS decisions were identified via web search snippet data only. No direct source access was obtained due to HTTP 403 on FOS website. This is a mandatory fail-stop condition.

---

## Confidence Ratings by Section

| Section | Confidence | Reason |
|---|---|---|
| Candidate universe completeness | Very Low | Approximately 79 of 400+ known decisions captured. All 79 DRNs accessed via snippet only — not source-verified. Result counts cannot be reconciled. |
| Decision classification | Low | Classification based on snippets only for borderline cases. |
| Personal loan — facts and thresholds | Low | Data from snippets only. DI range from 4 data points only. |
| Credit card — facts and thresholds | Very low | Only 3 verified decisions. All not upheld. |
| Underwriting era boundaries | Low | Approximate — derived from lending dates in reviewed decisions. |
| Bank statement position | Low | Conditional and ambiguous. Based on snippet data. |
| DI buffer thresholds | Low | 4 data points. Illustrative only. Not suitable as hard thresholds. |
| Argument modules | Low | Modules grounded in reviewed decisions but all source data is snippet-based. |
| Exclusions | Medium | 3 excluded decisions — rationale clear from snippets. |
| Product mapping | Medium | CRM taxonomy applied consistently. |

---

## QC Gate Results

| QC ID | Gate | Status | Notes |
|---|---|---|---|
| QC-001 | Candidate universe complete | FAIL | QC-001 FAIL — Source result count materially unreconciled. FOS reports 400+ decisions for BusinessID 768. Only 79 captured. |
| QC-002 | All candidates classified | Pass | All 79 classified (33 relevant, 26 borderline, 20 excluded). |
| QC-003 | Search log complete | Partial | Result counts not reconciled. HTTP 403. |
| QC-004 | Exclusion rationale documented | Pass | 3 excluded DRNs — all documented. |
| QC-005 | Borderline log complete | Pass | 26 borderline DRNs documented. |
| QC-006 | Source verification complete | FAIL — CRITICAL | 0 of 33 relevant decisions source-verified. Mandatory fail-stop. |
| QC-007 | DI figures extracted | Partial | 4 data points. Insufficient for robust range. |
| QC-008 | Product mapping complete | Pass | 33 relevant decisions mapped. Exceptions documented. |
| QC-009 | Underwriting eras defined | Partial | 4 eras defined. ERA-PL-3 has only 1 verified decision. |
| QC-010 | Argument modules created | Pass | 8 modules. Claimant-positive and defence. Motor finance has no argument modules — insufficient evidence base. |
| QC-011 | Bank statement tags applied | Pass | Tags reflect ambiguity honestly. |
| QC-012 | DI buffer ranges documented | Partial | 1 range summary. 4 data points only. |
| QC-013 | No false precision | Pass | All thresholds stated as indicative. Confidence noted as Low. |
| QC-014 | British English throughout | Pass | Checked during authoring. No em dashes. No minor hyphens. |
| QC-015 | No bank statements always required statement | Pass | FOS comparable facts formulation used throughout. |
| QC-016 | All upheld decisions have FOS reasoning | Pass | 6 upheld / partly upheld decisions summarised. |
| QC-017 | All argument modules cite supporting DRNs | Pass | All 8 modules cite supporting DRNs. |
| QC-018 | Defence modules included | Pass | 2 defence modules for personal loan; 2 for credit card. |
| QC-019 | Sentinel DRNs checked | Pass (N/A) | None supplied. |
| QC-020 | JSON valid | Pass | Confirmed valid and parseable. |
| QC-021 | Markdown files generated | Pass | Both .md files generated and present. |
| QC-022 | Pack status marked correctly | Pass | WORKING DRAFT status on all outputs. |
| QC-023 | Inaccessible decisions recorded | Partial | All 79 decisions recorded as inaccessible or snippet-only. HTTP 403. Approximately 321+ decisions on FOS website remain uncaptured. |
| QC-024 | No unresolved template text | Pass | No placeholder text remains. |
| QC-025 | CRM taxonomy correctly applied | Pass | Verified against provided taxonomy table. |

---

## Fail-Stop Summary

| Fail-stop condition | Result |
|---|---|
| Source verification (QC-006) | FAIL — 0 of 33 relevant decisions source-verified |
| Candidate universe completeness (QC-001) | FAIL — approximately 79 of 400+ known decisions captured |
| All others | Pass or Partial |

**Two mandatory fail-stop gates have failed. The pack must not be ingested by the Aquila letter-writing engine until both gates pass.**

---

## Actions Required to Achieve Pass Status

1. Obtain direct FOS source access for all 22 relevant decisions.
2. Source-verify all data extracted from snippets.
3. Classify and verify all 26 borderline decisions.
4. Update DI buffer thresholds.
5. Update credit card Markdown file with verified borderline decisions.
6. Reconcile search result counts.
7. Re-run all QC checks.
8. Update overall status from PARTIAL PASS — WORKING DRAFT to PASS — VERIFIED DRAFT (or equivalent) once all fail-stop conditions are resolved.

---

## Certificate

This QC certificate is issued for audit trail purposes. It records the quality control status of this pack as at 2026-05-31. This certificate does not constitute authorisation for Aquila ingestion. Authorisation for ingestion requires resolution of all fail-stop conditions and re-issuance of this certificate with status PASS.

**Issued by:** consultant1@allegiant.co.uk
**Pack version:** v2.3
**Date:** 2026-05-31

---

*End of QC Certificate*
