# Traceability Matrix — SauceDemo

## Basis

All 36 test cases were rerun on 2026-11-10; the tester reported 32 Pass and 4 Fail. The tester confirmed BUG-002 through BUG-005 as seeded defects in this educational exercise. BUG-001 is expected behavior: its message clearly identifies the locked account. No formal product requirements document was provided; the expected results for these defect scenarios are the exercise-specific test oracle.

“Not supplied” indicates that no case-specific screenshot is available. Related BUG IDs identify confirmed defects unless explicitly marked otherwise. Current screenshots document the failing scenarios; evidence limitations are stated in the bug report.

| Functionality | Test case | Execution result | Related defect | Evidence |
|---|---|---|---|---|
| Authentication | TC-001 — Valid login | Pass | — | Not supplied |
| Authentication | TC-002 — Locked user login | Pass | BUG-001 — not a defect; expected locked-account response | [Locked-user screenshot](evidences/screenshots/bug-001-locked-user.png) |
| Authentication | TC-003 — Invalid password | Pass | — | Not supplied |
| Authentication | TC-004 — Empty login fields | Pass | — | Not supplied |
| Authentication | TC-005 — Empty password | Pass | — | Not supplied |
| Authentication | TC-006 — Non-existent user | Pass | — | Not supplied |
| Inventory | TC-007 — `problem_user` product images | Fail | BUG-002 — confirmed, Medium | [Problem-user login form](evidences/screenshots/bug-002-problem-user-images%20%282%29.png); [repeated product image](evidences/screenshots/bug-002-problem-user-images.png) |
| Authentication / performance observation | TC-008 — `performance_glitch_user` login | Pass | — | Not supplied |
| Authentication | TC-009 — Logout | Pass | — | Not supplied |
| Access control | TC-010 — Direct inventory access while logged out | Pass | — | Not supplied |
| Inventory | TC-011 — Product listing | Pass | — | Not supplied |
| Inventory | TC-012 — Sort by name A–Z | Pass | — | Not supplied |
| Inventory | TC-013 — Sort by name Z–A | Pass | — | Not supplied |
| Inventory | TC-014 — Sort by price low-to-high | Pass | — | Not supplied |
| Inventory | TC-015 — Sort by price high-to-low | Pass | — | Not supplied |
| Inventory | TC-016 — Product details | Pass | — | Not supplied |
| Cart | TC-017 — Add one product | Pass | — | Not supplied |
| Cart | TC-018 — Add multiple products | Pass | — | Not supplied |
| Cart | TC-019 — Remove product from inventory | Pass | — | Not supplied |
| Cart | TC-020 — View cart | Pass | — | Not supplied |
| Cart | TC-021 — Remove product from cart | Pass | — | Not supplied |
| Cart | TC-022 — Continue shopping | Pass | — | Not supplied |
| Checkout | TC-023 — First-name validation | Fail | BUG-004 — confirmed for empty input, Low | [Checkout form](evidences/screenshots/bug-004-first-name-space-step1.png); [checkout overview](evidences/screenshots/bug-004-first-name-space-step2.png) |
| Checkout | TC-024 — ZIP/postal-code validation | Fail | BUG-005 — confirmed, Low | [Checkout form](evidences/screenshots/bug-005-invalid-zip-code-step1.png); [checkout overview](evidences/screenshots/bug-005-invalid-zip-code-step2.png) |
| Checkout | TC-025 — Missing last name | Pass | — | Not supplied |
| Checkout | TC-026 — Cancel checkout information | Pass | — | Not supplied |
| Checkout | TC-027 — Order summary | Pass | — | Not supplied |
| Checkout | TC-028 — Total calculation | Pass | — | Not supplied |
| Checkout | TC-029 — Finish order | Pass | — | Not supplied |
| Cart / checkout | TC-030 — Cart after order completion | Pass | — | Not supplied |
| Checkout | TC-031 — Back home after completion | Pass | — | Not supplied |
| Checkout | TC-032 — Cancel order summary | Pass | — | Not supplied |
| Authentication | TC-033 — Logout through menu | Pass | — | Not supplied |
| Authentication / access control | TC-034 — Browser back after logout | Pass | — | Not supplied |
| Cart / session | TC-035 — Cart reset after login | Fail | BUG-003 — confirmed, Medium | [Cart before login](evidences/screenshots/bug-003-cart-before-login.png); [inventory after login](evidences/screenshots/bug-003-cart-after-login.png) |
| Navigation | TC-036 — Menu options | Pass | — | Not supplied |

## Evidence and traceability limitations

- There are no formal requirement or acceptance-criteria IDs; BUG-002 through BUG-005 use the tester-confirmed exercise oracle.
- The BUG-003 screenshots show two products before login and a cart badge of two afterward, but do not show the logout action. The tester confirms the complete rerun sequence.
- BUG-004 screenshots establish that an empty First Name is accepted; they do not establish behavior for whitespace-only input.
- Actual-result details for passing cases without evidence are not individually captured in the repository.
