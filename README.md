# SauceDemo — Manual QA Portfolio

Manual testing portfolio for the public [SauceDemo](https://www.saucedemo.com/) e-commerce demo. The repository documents test planning, 36 test cases, the 2026-11-10 rerun, confirmed seeded defects, and screenshot evidence.

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

All 36 cases were re-executed on 2026-11-10. The reported environment was Windows 11 and Google Chrome 157.0.8103.50 (64-bit). The tester confirmed the four seeded defects described in BUG-002 through BUG-005; current screenshots document their observed behavior.

| Measure | Reviewed record |
|---|---:|
| Total cases | 36 |
| Pass | 32 |
| Fail | 4 |
| Blocked | 0 |
| Not executed | 0 |
| Executed (Pass + Fail) | 36 |
| Pass rate | 88.9% |
| Confirmed defects | 4 |
| Defects by severity | 2 Medium, 2 Low |

The four failures are TC-007, TC-023, TC-024, and TC-035, each linked to a confirmed defect and current screenshot evidence. BUG-001 is not a defect: its screenshot shows a clear locked-account message. The original 90% pass-rate target was not met. See the [execution report](execution-report/execution-report.md) for details.

## Repository contents

| Path | Purpose |
|---|---|
| [test-plan/test-plan.md](test-plan/test-plan.md) | Versioned test plan, scope, approach, criteria, and risks |
| [test-cases/test-cases.xlsx](test-cases/test-cases.xlsx) | 36 test cases with execution data and evidence references |
| [traceability-matrix.md](traceability-matrix.md) | Functionality, case status, confirmed defect, and screenshot mapping |
| [bug-reports/bug-report.md](bug-reports/bug-report.md) | Preserved BUG-001 through BUG-005 with reviewed dispositions |
| [execution-report/execution-report.md](execution-report/execution-report.md) | Reconciled metrics and exit-criteria evaluation |
| [evidences/screenshots/](evidences/screenshots/) | Current rerun screenshots referenced by the reports |

## Main quality findings

- The locked-user screenshot contains “Sorry, this user has been locked out.” The claim that the message does not identify the reason is not supported.
- The tester confirms BUG-002 through BUG-005 are intentionally seeded defects in this educational SauceDemo exercise; their current evidence is linked in the bug report and matrix.
- The cart screenshots show two products before login and a badge count of two afterward; the tester also confirmed the logout/login rerun. The logout action itself is not visible in the screenshots.
- BUG-004 evidence establishes acceptance of an empty First Name, not whitespace-only input.
- The ZIP evidence filenames were correct on disk but the Markdown referenced nonexistent BUG-004 filenames; the references are corrected to BUG-005.
- The workbook and report distinguish confirmed defect failures from expected behavior; detailed actual-result notes remain limited for passing cases without individual screenshots.

## Technical learnings

The project demonstrates reproducible test design, separation of preconditions from test data, evidence review, execution metrics, defect triage, and traceability. It also highlights that a failed test condition is not automatically a confirmed defect, as illustrated by BUG-001.

## Limitations and follow-up

Formal product requirements are not included. The tester supplied the project context that these seeded behaviors are defects; BUG-001 remains excluded because its screenshot meets the documented locked-account message expectation. The 2026-11-10 run used Windows 11 and Chrome 157.0.8103.50 (64-bit); resolution and tester identity were not recorded. The logout action for BUG-003 and whitespace-only input for BUG-004 are not depicted in the evidence.

## Author

Nathalia De Bellis Gomes Anselmo — portfolio project focused on Software Quality Assurance.
