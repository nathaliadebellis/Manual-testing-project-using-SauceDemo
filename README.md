# SauceDemo — Manual QA Portfolio

Manual testing portfolio for the public [SauceDemo](https://www.saucedemo.com/) e-commerce demo. The repository documents test planning, 36 test cases, historical execution results, evidence, and a cautious assessment of reported anomalies.

## Project objective

Demonstrate a practical QA workflow: define test conditions, execute functional scenarios, retain evidence, assess observations against available requirements, and maintain traceability. This is a portfolio exercise, not a certification of SauceDemo.

## Application and scope

The application under test is SauceDemo. The recorded demo accounts include `standard_user`, `locked_out_user`, `problem_user`, and `performance_glitch_user`; the documented demo password is `secret_sauce`.

| Area | Coverage |
|---|---|
| Authentication | Valid and invalid credentials, locked account, logout, and protected-page access |
| Inventory | Product listing, product details, sorting, and product images |
| Cart | Add, remove, view, navigation, and observed state across logout/login |
| Checkout | Customer information, postal-code observation, order summary, and order completion |
| Session | Logout and browser-back behavior |

Performance benchmarking, security testing, payment integration, API/backend testing, mobile applications, and broad cross-browser coverage were not performed.

## Test approach and tools

Manual functional, positive/negative, and exploratory testing. Evidence and case tracking are maintained in Microsoft Excel and Markdown; Git/GitHub is used for version control and portfolio presentation. No automated test framework or CI run is part of this repository.

## Execution indicators

All 36 cases were re-executed on 2026-11-10, with the same overall distribution as the reviewed workbook. The reported environment was Windows 11 and Google Chrome 157.0.8103.50 (64-bit). Current screenshots were added for the reported scenarios; detailed actual-result notes remain limited to cases with supporting evidence.

| Measure | Reviewed record |
|---|---:|
| Total cases | 36 |
| Pass | 32 |
| Fail | 4 |
| Blocked | 0 |
| Not executed | 0 |
| Executed (Pass + Fail) | 36 |
| Pass rate | 88.9% |
| Confirmed defects | 0 established |
| Observations requiring investigation | 4 |

The four failures are TC-007, TC-023, TC-024, and TC-035. They record outcomes against test conditions, not four confirmed product defects. The original 90% pass-rate target was not met. See the [execution report](execution-report/execution-report.md) for calculation, evidence, and limitations.

## Repository contents

| Path | Purpose |
|---|---|
| [test-plan/test-plan.md](test-plan/test-plan.md) | Versioned test plan, scope, approach, criteria, and risks |
| [test-cases/test-cases.xlsx](test-cases/test-cases.xlsx) | 36 test cases with execution data and evidence references |
| [traceability-matrix.md](traceability-matrix.md) | Case-to-functionality, result, observation, and evidence mapping |
| [bug-reports/bug-report.md](bug-reports/bug-report.md) | Preserved BUG-001 through BUG-005 with reviewed dispositions |
| [execution-report/execution-report.md](execution-report/execution-report.md) | Reconciled metrics and exit-criteria evaluation |
| [evidences/screenshots/](evidences/screenshots/) | Original screenshots referenced by the reports |

## Technical learnings

The project demonstrates reproducible test design, separation of preconditions from test data, evidence review, execution metrics, requirement-aware defect triage, and traceability. It also highlights that a failed test condition is not automatically a confirmed defect.

## Limitations and follow-up

Formal product requirements and acceptance criteria were not supplied. The 2026-11-10 run used Windows 11 and Chrome 157.0.8103.50 (64-bit). Product-rule decisions are still needed for cart lifecycle, first-name validation, and postal-code format.

## Author

Nathalia De Bellis Gomes Anselmo — portfolio project focused on Software Quality Assurance.
