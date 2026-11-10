# SauceDemo — Manual Software Testing Portfolio Project

A manual QA portfolio project focused on planning, designing, documenting and reviewing tests for the SauceDemo e-commerce demo application. The repository demonstrates a structured testing workflow and emphasizes evidence-based defect assessment.

> **Project note:** SauceDemo includes special-purpose accounts that intentionally simulate problematic behavior. An observed anomaly is not automatically a product defect. This repository distinguishes confirmed evidence, seeded test-account behavior and cases that require a product requirement or acceptance criterion.

## Project objectives

- Practice test planning and test-case design for core e-commerce journeys.
- Exercise positive, negative and session-related scenarios.
- Record execution evidence and maintain traceability.
- Assess potential defects using reproducible steps and explicit expected results.

## Application under test

- URL: https://www.saucedemo.com/
- Demo accounts used: `standard_user`, `locked_out_user`, `problem_user`, `performance_glitch_user`.
- Demo password: `secret_sauce`.

## Scope

| Area | Coverage |
|---|---|
| Authentication | Valid/invalid login, locked account, logout and protected-page access. |
| Inventory | Product listing, product details and sorting. |
| Cart | Add, remove, view and navigation. |
| Checkout | Required fields, postal-code observation, order summary and completion. |
| Session behavior | Navigation and cart state across logout/login. |

## Test approach

Functional testing, positive and negative testing, exploratory observations, and regression-oriented scenarios. The repository does not contain official product requirements; assumption-dependent expectations are marked **Needs review** rather than being reported as confirmed defects.

## Results at a glance

| Metric | Result |
|---|---:|
| Test cases | 36 |
| Historically recorded as passed | 31 |
| Historically recorded as failed | 5 |
| Original pass rate | 86.1% |
| Current documentation status: Pass | 32 |
| Current documentation status: Needs review | 4 |
| Confirmed defects from evidence review | 0 established |

The current status is a documentation/evidence reassessment, **not a fresh test execution**. TC-002 was corrected based on its screenshot. TC-007, TC-023, TC-024 and TC-035 require clarification. The original 90% exit target was not met. See the [execution summary](execution-report/execution-report.md).

## Repository structure

```text
.
├── README.md
├── test-plan/
│   └── test-plan.md
├── test-cases/
│   ├── test-cases.xlsx
│   └── traceability-matrix.xlsx
├── bug-reports/
│   └── bug-report.md
├── execution-report/
│   └── execution-report.md
└── evidences/
    └── screenshots/
```

## Deliverables

- [Test plan](test-plan/test-plan.md)
- [Test cases — Excel](test-cases/test-cases.xlsx)
- [Traceability matrix — Excel](test-cases/traceability-matrix.xlsx)
- [Defect assessment and observations](bug-reports/bug-report.md)
- [Execution summary](execution-report/execution-report.md)
- [Test evidence screenshots](evidences/screenshots/)

## Tools and skills demonstrated

- Manual software testing and test design.
- Test documentation and execution tracking.
- Defect reproduction and evidence collection.
- Requirements thinking and traceability.
- Microsoft Excel and Git/GitHub documentation.

## Environment

The original plan records Windows 11, Google Chrome and 1920 × 1080 resolution. The exact browser version is not verified in the supplied execution artifacts and should be captured in the next run.

## Author

Nathalia De Bellis Gomes Anselmo — portfolio project focused on Software Quality Assurance (QA) and software testing.
