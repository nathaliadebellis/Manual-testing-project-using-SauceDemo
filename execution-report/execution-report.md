# Test Execution Report — SauceDemo

| Document ID | Version | Review date | Basis |
|---|---:|---|---|
| QA-ER-SD-001 | 1.2 | 2026-11-10 | Full manual rerun reported by tester; current screenshots reviewed; seeded defects confirmed |

## 1. Execution summary

All 36 cases were rerun on 2026-11-10. The tester confirmed 32 Pass and 4 Fail, and clarified that BUG-002 through BUG-005 are intentionally seeded defects in this educational exercise. Their corresponding failures are therefore classified as confirmed defects against the exercise test oracle. Before the earlier evidence review, the workbook showed 31 Pass and 5 Fail; TC-002 was corrected to Pass because its screenshot displays “Sorry, this user has been locked out,” satisfying its stated expected result. BUG-001 is not a defect.

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

## 3. Failed cases and confirmed defects

| Case | Recorded result | Review note |
|---|---|---|
| TC-007 | Fail | **Confirmed BUG-002.** Current inventory evidence shows the same dog image on multiple products for `problem_user`; the login and product screenshots are linked in the bug report. |
| TC-023 | Fail | **Confirmed BUG-004 for empty input.** Current screenshots show First Name empty followed by the checkout overview. They do not establish whitespace-only input. |
| TC-024 | Fail | **Confirmed BUG-005.** Current screenshots show postal-code value `teste` followed by the checkout overview. |
| TC-035 | Fail | **Confirmed BUG-003.** The rerun confirmed cart persistence. Screenshots show two products before login and badge count 2 afterward; the logout action itself is not pictured. |

The four failures map to confirmed seeded defects per the tester's confirmation of the exercise context. Current screenshots document the observed states; for BUG-003 the tester's rerun confirmation supplements screenshots that do not show the logout action. Actual-result details for the other passing cases are not individually captured in the current evidence set.

## 4. Defect assessment

The five original BUG records are preserved in the [bug report](../bug-reports/bug-report.md). BUG-002 through BUG-005 are confirmed seeded defects; BUG-001 is expected behavior and is not included in defect counts.

| Severity | Confirmed defects |
|---|---:|
| Critical | 0 |
| High | 0 |
| Medium | 2 |
| Low | 2 |

Severity distribution for the four confirmed defects uses the reviewed report assessments: BUG-002 and BUG-003 Medium; BUG-004 and BUG-005 Low. BUG-001's original High label is withdrawn because the evidence demonstrates expected behavior, not a defect.

Disposition: BUG-001 is expected behavior for the locked account; BUG-002 through BUG-005 are confirmed seeded defects. Their screenshots are linked in the [bug report](../bug-reports/bug-report.md) and [traceability matrix](../traceability-matrix.md).

## 5. Exit criteria

| Criterion | Result | Basis |
|---|---|---|
| All 36 cases have an execution status | Met | Workbook has 36 Pass/Fail statuses |
| No unresolved Critical/High confirmed defect | Met | The four confirmed defects are Medium or Low severity |
| At least 90% Pass | Not met | Reconciled rate is 88.9% |
| Failures are reproducible and evidenced or limitations recorded | Partially met | Four failures retained; evidence/requirement limitations are stated above |
| Report and traceability reconciled to workbook | Met | See [traceability matrix](../traceability-matrix.md) |

## 6. Deliverables and limitations

The deliverables are the [test plan](../test-plan/test-plan.md), [test workbook](../test-cases/test-cases.xlsx), [traceability matrix](../traceability-matrix.md), [bug report](../bug-reports/bug-report.md), and current [screenshots](../evidences/screenshots/). Detailed actual-result notes remain absent for passing cases without individual evidence; tester identity and screen resolution were not recorded. The logout action for BUG-003 and whitespace-only input for BUG-004 are not visible in screenshots.
