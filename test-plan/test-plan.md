# Test Plan — SauceDemo

## 1. Objective

Validate the main e-commerce user journeys in SauceDemo and document test design, execution observations, evidence, and potential defects. This is a portfolio exercise using a public demo application, not a formal certification of the product.

## 2. Scope

### In scope
- Authentication: valid/invalid credentials, locked account, logout and access control.
- Inventory: product listing, product details and sorting.
- Cart: add, remove, view and navigation.
- Checkout: required-field behavior, order summary and completion flow.
- Session-related behavior observed during logout/login.

### Out of scope
- Real payment processing or external payment gateway integration.
- Load, stress, security penetration and performance benchmarking.
- Native mobile application testing and broad cross-browser compatibility.
- Backend/API validation (not covered by the supplied artifacts).

## 3. Test basis and assumptions

The repository does not include formal product requirements or stakeholder-approved acceptance criteria. Therefore, test expectations in the spreadsheet are **portfolio test conditions derived from observable user journeys**, not claims about official SauceDemo requirements. Any expectation that depends on a product decision (for example, cart persistence or postal-code format) must be clarified before a failure is classified as a defect.

Special-purpose SauceDemo accounts may intentionally exhibit abnormal behavior. Their behavior must be reported as a test-account characteristic unless it demonstrates a violation of an applicable requirement.

## 4. Test environment

| Item | Recorded value |
|---|---|
| Application | https://www.saucedemo.com/ |
| Operating system | Windows 11 (recorded in original plan) |
| Browser | Google Chrome (exact version not independently verified) |
| Screen resolution | 1920 × 1080 (recorded in original plan) |
| Test data | `standard_user`, `locked_out_user`, `problem_user`, `performance_glitch_user` |
| Password | `secret_sauce` (demo credentials) |

For future executions, record the actual browser version, execution date, application availability, and tester. Do not infer an exact browser version from an old report.

## 5. Test approach

- Functional testing of core user journeys.
- Positive and negative testing of input and authentication behavior.
- Exploratory checks where behavior is not fully specified.
- Regression testing when a change or fix is available.
- Usability observations, kept separate from functional defects unless a criterion is defined.

## 6. Entry criteria

- Application is reachable.
- Browser and test data are available.
- Test cases and expected results are documented.
- The tester can identify which behaviors are defined requirements and which are assumptions.

## 7. Exit criteria

- All in-scope test cases have an explicit execution status.
- Every failure has reproducible steps and evidence, or is marked as requiring investigation.
- No unresolved critical/high-severity confirmed defect remains (severity is not assigned to unconfirmed observations).
- Results distinguish Pass, Fail, Blocked and Needs review.
- Execution summary and limitations are documented.

A 90% pass-rate target may be used as a project quality indicator, but it does not override unresolved requirements or justify reclassifying test results.

## 8. Risks and mitigation

| Risk | Mitigation |
|---|---|
| Demo application behavior changes | Record execution date and environment; retain screenshots. |
| Special accounts intentionally simulate problems | Separate seeded behavior from product defects. |
| No formal requirements are supplied | Mark assumption-dependent cases as Needs review. |
| Browser/version details are missing | Capture actual version during the next execution. |
| Evidence paths become stale | Use relative repository paths and verify every link. |

## 9. Deliverables

- Test plan.
- Test case workbook.
- Requirements-to-test traceability matrix.
- Defect assessment and observations.
- Execution summary.
- Screenshots and other test evidence.
