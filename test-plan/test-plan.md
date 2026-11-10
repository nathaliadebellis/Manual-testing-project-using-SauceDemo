# Test Plan — SauceDemo

| Document ID | Version | Review date | Status |
|---|---:|---|---|
| QA-TP-SD-001 | 1.1 | 2026-11-10 | Updated after full manual rerun |

## 1. Objective

Define the scope, approach, data, and completion criteria for manual functional testing of core SauceDemo shopping journeys. This plan supports a portfolio exercise; it is not a product acceptance or compliance assessment.

## 2. Scope

### In scope

- Authentication: valid and invalid credentials, locked-account response, logout, and protected-page access.
- Inventory: product listing, product details, sorting, and images.
- Cart: add/remove, contents, navigation, and observed state across logout/login.
- Checkout: customer information, postal-code behavior, order summary, completion, and post-completion navigation.
- Session behavior: logout and browser-back behavior.

### Out of scope

- Real payment processing, payment-provider integration, or shipping fulfillment.
- Load, stress, performance benchmarking, security penetration, and API/backend testing.
- Native mobile applications and broad cross-browser compatibility.
- Requirements validation or certification against an unavailable product specification.

## 3. Test basis and data

No formal product requirements, approved acceptance criteria, or stakeholder decisions are included. Expected results in the workbook are test conditions authored for this exercise, not evidence of official product requirements. Behaviors dependent on an unresolved rule must remain observations, not confirmed defects.

Recorded demo accounts: `standard_user`, `locked_out_user`, `problem_user`, and `performance_glitch_user`; documented password: `secret_sauce`. The workbook's additional test values define reproducible test conditions; they do not prove the exact inputs used in the rerun unless supported by its evidence.

## 4. Test environment

| Item | Recorded information | Qualification |
|---|---|---|
| Application | https://www.saucedemo.com/ | Public demo application |
| Operating system | Windows 11 | Reported for the 2026-11-10 rerun |
| Browser | Google Chrome 157.0.8103.50 (64-bit) | Reported for the 2026-11-10 rerun |
| Resolution | Not recorded for the rerun | Earlier plan recorded 1920 × 1080; do not assume unchanged |
| Accounts | Demo accounts listed above | Do not use for production |

The rerun date and browser/OS were reported. Tester identity and display resolution were not recorded.

## 5. Test strategy and types

- Manual, black-box functional testing of documented user journeys.
- Positive and negative input testing for authentication and checkout.
- Exploratory observation of special-purpose demo accounts and session behavior.
- Regression testing only when a change/fix is available; no regression run is evidenced here.
- Usability observations are separated from functional defects unless an applicable criterion is defined.

Each case should state preconditions, test data, numbered steps, and an observable expected result. Record the actual result and link evidence during execution. Preserve historical status unless supplied evidence establishes a specific inconsistency.

## 6. Entry criteria

- The application is reachable and the test environment is available.
- The test case workbook and demo credentials are available.
- The tester can distinguish stated test conditions from approved requirements.
- Any requirement-dependent behavior has an identified owner or is explicitly flagged for clarification.

## 7. Exit criteria

- All 36 in-scope cases have a recorded execution status.
- Every failure has reproducible steps and evidence, or its evidentiary limitation is documented.
- No unresolved Critical/High confirmed defect remains.
- Results distinguish test failures from confirmed defects and unresolved observations.
- The execution report and traceability matrix reconcile to the workbook.
- The portfolio target of at least 90% Pass is reported separately from the other exit criteria.

## 8. Severity and priority criteria

Severity describes the demonstrated impact of a **confirmed** defect; priority describes the urgency to address it. Neither should be assigned to an unconfirmed observation. The workbook's existing Critical/High/Medium/Low labels are retained as historical test priorities; they are not defect severity ratings.

| Level | Severity guidance | Priority guidance |
|---|---|---|
| Critical | Core service unavailable, data loss/exposure, or essential journey cannot proceed with no reasonable workaround | P1: immediate response; blocks release/use |
| High | Major user journey materially impaired, broad impact, or significant incorrect outcome | P2: resolve before release where feasible |
| Medium | Limited functionality or a workaround exists; impact is contained | P3: schedule for a planned fix |
| Low | Minor impact, cosmetic issue, or low-frequency inconvenience | P4: address when practical |

Assessments require a confirmed requirement violation, reproducible behavior, and evidence. Potential impact alone does not establish severity.

## 9. Risks and mitigation

| Risk | Mitigation |
|---|---|
| Demo application or seeded-account behavior changes | Record run date, exact environment, account, and evidence; distinguish intentional test behavior from product defects |
| Missing requirements make expected behavior ambiguous | Obtain an acceptance criterion; keep the observation unconfirmed until resolved |
| Historical actual results and execution metadata are incomplete | Mark missing information explicitly; do not reconstruct it |
| Screenshot context does not prove the full sequence | Capture each relevant state and action during a witnessed rerun |
| Repository-relative evidence links become stale | Check paths and links during review |

## 10. Deliverables

- This test plan.
- [36-case test workbook](../test-cases/test-cases.xlsx).
- [Traceability matrix](../traceability-matrix.md).
- [Reviewed bug report and observation register](../bug-reports/bug-report.md).
- [Execution report](../execution-report/execution-report.md).
- Original supplied screenshots under `evidences/screenshots/`.
