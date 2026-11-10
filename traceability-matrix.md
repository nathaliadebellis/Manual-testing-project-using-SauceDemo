# Traceability Matrix — SauceDemo

## Basis and limitations

No formal requirement IDs or approved acceptance criteria were supplied. This matrix maps the functional areas represented by the workbook—not invented requirements—to all 36 cases. The 2026-11-10 rerun was reported as 32 Pass and 4 Fail; the four failed IDs are TC-007, TC-023, TC-024, and TC-035. Current evidence is linked where available.

An item in the “Related record” column indicates a corresponding observation in the bug register, not a confirmed defect. “Not supplied” means the repository contains no case-specific evidence file.

| Functionality | Test case | Execution result | Related record | Evidence |
|---|---|---|---|---|
| Authentication | TC-001 — Valid login | Pass | — | Not supplied |
| Authentication | TC-002 — Locked user login | Pass | — (BUG-001 reclassified as expected behavior) | [Locked-user screenshot](evidences/screenshots/bug-001-locked-user.png) |
| Authentication | TC-003 — Invalid password | Pass | — | Not supplied |
| Authentication | TC-004 — Empty login fields | Pass | — | Not supplied |
| Authentication | TC-005 — Empty password | Pass | — | Not supplied |
| Authentication | TC-006 — Non-existent user | Pass | — | Not supplied |
| Inventory | TC-007 — `problem_user` product images | Fail | BUG-002 (observation; requirement needs confirmation) | [Login screenshot](evidences/screenshots/bug-002-problem-user-images%20%282%29.png); [product-image screenshot](evidences/screenshots/bug-002-problem-user-images.png) |
| Authentication / performance observation | TC-008 — `performance_glitch_user` login | Pass | — | Not supplied |
| Authentication | TC-009 — Logout | Pass | — | Not supplied |
| Authentication / access control | TC-010 — Direct inventory access while logged out | Pass | — | Not supplied |
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
| Checkout | TC-023 — First-name validation | Fail | BUG-004 (empty-value observation; validation rule not supplied) | [Checkout form](evidences/screenshots/bug-004-first-name-space-step1.png); [checkout overview](evidences/screenshots/bug-004-first-name-space-step2.png) |
| Checkout | TC-024 — ZIP/postal-code validation | Fail | BUG-005 (validation rule not supplied) | [Checkout form](evidences/screenshots/bug-005-invalid-zip-code-step1.png); [checkout overview](evidences/screenshots/bug-005-invalid-zip-code-step2.png) |
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
| Cart / session | TC-035 — Cart reset after login | Fail | BUG-003 (cart-lifecycle observation; requirement not supplied) | [Cart before login](evidences/screenshots/bug-003-cart-before-login.png); [inventory after login](evidences/screenshots/bug-003-cart-after-login.png) |
| Navigation | TC-036 — Menu options | Pass | — | Not supplied |

## Traceability gaps

- There are no formal requirement or acceptance-criteria identifiers to map to these cases.
- The overall rerun outcomes were reported by the tester, but detailed actual-result notes are still unavailable for cases without individual evidence.
- The four failed scenarios need requirement and/or evidence follow-up. Their related BUG IDs are observations, not confirmed defects.
- BUG-003 screenshots show two products before login and a badge count of two after login, but do not show the intervening logout action.
