# Test Execution Report — SauceDemo

| Document ID | Version | Review date | Basis |
|---|---:|---|---|
| QA-ER-SD-001 | 1.1 | 2026-11-10 | Full manual rerun reported by tester; workbook and current screenshots reviewed |

## 1. Execution summary

All 36 cases were rerun on 2026-11-10. The tester confirmed the reviewed distribution remained 32 Pass and 4 Fail; the four failing IDs remain TC-007, TC-023, TC-024, and TC-035. Before the earlier evidence review, the workbook showed 31 Pass and 5 Fail; TC-002 was corrected to Pass because its screenshot displays “Sorry, this user has been locked out,” satisfying its stated expected result. The current evidence supports the four recorded observations described below, but does not establish product requirements for classifying them as defects.

| Result | Count |
|---|---:|
| Total cases | 36 |
| Passed | 32 |
| Failed | 4 |
| Blocked | 0 |
| Not executed | 0 |
| Executed (Passed + Failed) | 36 |
| Pass rate | 88.9% |

**Calculation:** Pass Rate = (Passed / Executed) × 100 = (32 / 36) × 100 = **88.9%**. The project target of 90% was not met.

## 2. Environment

| Item | Recorded value | Limitation |
|---|---|---|
| Application | https://www.saucedemo.com/ | Public demo |
| Browser | Google Chrome 157.0.8103.50 (64-bit) | Reported by tester |
| Operating system | Windows 11 | Reported by tester |
| Resolution | Not recorded | Earlier 1920 × 1080 value is not confirmed for this rerun |
| Run date / tester | 2026-11-10 / not identified | Date reported; tester identity not supplied |

## 3. Remaining failed cases

| Case | Recorded result | Review note |
|---|---|---|
| TC-007 | Fail | Current inventory evidence shows the same dog image on multiple products for `problem_user`. The login screenshot and product behavior are linked in BUG-002; whether this seeded-account behavior violates a requirement remains unconfirmed. |
| TC-023 | Fail | Current screenshots show an empty First Name field followed by the checkout overview. They do not show whitespace-only input; no approved required-field rule was supplied. |
| TC-024 | Fail | Current screenshots show `teste` in the postal-code field followed by the checkout overview. No approved country/format validation rule was supplied. |
| TC-035 | Fail | Current screenshots show two products in the cart before login and a cart badge of 2 after login. The test run reports the cart remained; the screenshots do not depict the intervening logout, and no cart-reset requirement was supplied. |

The four failure statuses were reproduced in the rerun against the workbook's test conditions. They remain observations rather than confirmed defects: the relevant expected behavior is not established by approved requirements. Actual-result details for the other passing cases are not individually captured in the current evidence set.

## 4. Defect assessment

The five original BUG records are preserved in the [bug report](../bug-reports/bug-report.md), but none is established as a confirmed defect based on the supplied requirements and evidence.

| Severity | Confirmed defects |
|---|---:|
| Critical | 0 |
| High | 0 |
| Medium | 0 |
| Low | 0 |

No severity distribution can be assigned to confirmed defects because none is confirmed. The historical severity labels attached to the five original reports are withdrawn as current classifications; they are summarized in the bug report for auditability and are not counted as current defects.

Disposition: BUG-001 is expected behavior for the locked account; BUG-002, BUG-003, BUG-004, and BUG-005 remain observations requiring product-rule follow-up. The 2026-11-10 rerun is recorded; no defect severity is assigned to unconfirmed observations.

## 5. Exit criteria

| Criterion | Result | Basis |
|---|---|---|
| All 36 cases have an execution status | Met | Workbook has 36 Pass/Fail statuses |
| No unresolved Critical/High confirmed defect | Met on available evidence | No defect is confirmed; this does not prove defect-free behavior |
| At least 90% Pass | Not met | Reconciled rate is 88.9% |
| Failures are reproducible and evidenced or limitations recorded | Partially met | Four failures retained; evidence/requirement limitations are stated above |
| Report and traceability reconciled to workbook | Met | See [traceability matrix](../traceability-matrix.md) |

## 6. Deliverables and limitations

The deliverables are the [test plan](../test-plan/test-plan.md), [test workbook](../test-cases/test-cases.xlsx), [traceability matrix](../traceability-matrix.md), [bug report](../bug-reports/bug-report.md), and current [screenshots](../evidences/screenshots/). The tester reported the overall rerun outcome, but detailed actual-result notes are still absent for passing cases without individual evidence. Future runs should record each case's observation, tester, resolution, and complete reproduction sequence.
