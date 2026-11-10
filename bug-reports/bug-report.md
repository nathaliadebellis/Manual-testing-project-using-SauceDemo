# Bug Reports and Observation Register — SauceDemo

## Review basis

This register preserves all five original IDs and evidence. The tester confirmed that BUG-002 through BUG-005 are intentionally seeded defects in this SauceDemo educational exercise; their test conditions are treated as the exercise-specific oracle. BUG-001 is retained as expected behavior because its screenshot explicitly identifies the locked account and satisfies TC-002's expected result.

All 36 test cases were rerun on 2026-11-10; the tester reported 32 Pass and 4 Fail. The four failures remain TC-007, TC-023, TC-024, and TC-035. Reported environment: Windows 11 and Google Chrome 157.0.8103.50 (64-bit). Tester identity and display resolution were not recorded. The screenshots below are from the current run where indicated; evidence gaps are called out rather than inferred.

| ID | Reviewed disposition | Severity | Priority |
|---|---|---:|---:|
| BUG-001 | Expected behavior; not a defect | — | — |
| BUG-002 | Confirmed seeded defect: incorrect images | Medium | Medium |
| BUG-003 | Confirmed seeded defect: cart persists after logout/login | Medium | High |
| BUG-004 | Confirmed seeded defect: checkout accepts empty First Name | Low | Low |
| BUG-005 | Confirmed seeded defect: checkout accepts non-standard postal value | Low | Low |

BUG-001's original High/High labels are withdrawn. The other four reports retain their original severity/priority assessments as current classifications, now supported by the tester's confirmation of the exercise-specific defect oracle and the rerun evidence. Severity describes impact; priority indicates urgency.

## BUG-001 — Locked-user message already identifies the account as locked

**Disposition:** Expected behavior / no defect established.

- **Description:** The original report said that the locked-account message was unclear. The supplied screenshot contradicts that claim: the message explicitly states that the user has been locked out.
- **Preconditions:** SauceDemo is reachable; use the `locked_out_user` demo account.
- **Test data:** Username `locked_out_user`; password `secret_sauce`.
- **Steps to reproduce:**
  1. Open https://www.saucedemo.com/.
  2. Enter the username and password above.
  3. Select **Login**.
- **Expected result:** Login is denied and the message identifies that the account is locked.
- **Actual result:** “Epic sadface: Sorry, this user has been locked out.”
- **Original severity / priority:** High / High; withdrawn because the reported usability failure is not supported.
- **Current severity / priority:** Not applicable; no defect established.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Locked-user screenshot](../evidences/screenshots/bug-001-locked-user.png).
- **Impact:** No adverse user impact established by this evidence; the message communicates the lockout reason.

## BUG-002 — Incorrect product images displayed with `problem_user`

**Disposition:** Confirmed seeded defect.

- **Description:** The tester confirmed that the `problem_user` scenario intentionally exercises an image defect. Current evidence shows the same dog image on multiple inventory products.
- **Preconditions:** SauceDemo is reachable; user is not logged in.
- **Test data:** `problem_user` / `secret_sauce`.
- **Steps to reproduce:**
  1. Open https://www.saucedemo.com/.
  2. Sign in as `problem_user`.
  3. Inspect the product images on the inventory page and compare them with the product names.
- **Expected result:** Each inventory product displays its corresponding product image. This is the exercise-specific expected behavior confirmed by the tester, not a claim about a supplied formal product specification.
- **Actual result:** The current inventory screenshot shows the same dog image for multiple named products. The accompanying login screenshot shows `problem_user` entered; the tester confirms the login and rerun.
- **Severity / priority:** Medium / Medium.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Problem-user login form](../evidences/screenshots/bug-002-problem-user-images%20%282%29.png); [inventory with repeated product image](../evidences/screenshots/bug-002-problem-user-images.png).
- **Impact:** Misleading product imagery makes it harder for users to identify and compare items.

## BUG-003 — Cart is not cleared after logout and new login

**Disposition:** Confirmed seeded defect.

- **Description:** The tester confirmed that the exercise expects the cart to be empty after logging out and logging in again. The rerun showed the same two cart items remained. The screenshots show the before and after states; the intervening logout action is not pictured.
- **Preconditions:** SauceDemo is reachable; use the same demo account for both logins.
- **Test data:** `standard_user` / `secret_sauce`; the original report refers to two products, but the screenshots do not prove a matching pre-logout cart state.
- **Steps to reproduce:**
  1. Sign in as `standard_user`.
  2. Add products to the cart and record the product names and cart count.
  3. Use the application menu to log out.
  4. Sign in again as the same user.
  5. Open the cart and compare its contents with the recorded pre-logout state.
- **Expected result:** For this exercise, the cart is empty after logout and the subsequent login.
- **Actual result:** The rerun failed this condition. The before-login screenshot shows Backpack and Bike Light in the cart; after login, the inventory cart badge shows 2. The tester confirms the logout/login sequence; the transition itself is not visible in the screenshots.
- **Severity / priority:** Medium / High.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Cart before login](../evidences/screenshots/bug-003-cart-before-login.png); [inventory after login](../evidences/screenshots/bug-003-cart-after-login.png).
- **Impact:** A user may encounter previously selected items in a new login and could unintentionally continue with an unexpected cart.

## BUG-004 — Checkout accepts an empty First Name

**Disposition:** Confirmed seeded defect for an empty value. Whitespace-only input was not evidenced.

- **Description:** The current rerun shows that checkout proceeds when First Name is empty. The tester confirmed that the exercise treats accepting an empty required name as a seeded defect. The original whitespace-only claim is not supported by these screenshots.
- **Preconditions:** SauceDemo is reachable; user is logged in and has at least one product in the cart.
- **Test data:** `standard_user` / `secret_sauce`; empty First Name; the screenshots show `teste` in Last Name and `00000-000` in the postal-code field.
- **Steps to reproduce:**
  1. Sign in as `standard_user` and add a product.
  2. Open the cart and select **Checkout**.
  3. Leave First Name empty; enter the recorded Last Name and postal-code values if reproducing the screenshot.
  4. Select **Continue**.
- **Expected result:** For this exercise, First Name must be provided; an empty value is rejected and checkout does not advance.
- **Actual result:** In the current run, the screenshot shows First Name empty while Last Name and postal code contain values; the follow-up screenshot shows the checkout overview. The evidence supports empty input, not whitespace-only input.
- **Severity / priority:** Low / Low.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Checkout form](../evidences/screenshots/bug-004-first-name-space-step1.png); [checkout overview](../evidences/screenshots/bug-004-first-name-space-step2.png).
- **Impact:** Checkout may proceed with incomplete customer information.

## BUG-005 — Checkout accepts a non-standard ZIP/postal-code value

**Disposition:** Confirmed seeded defect.

- **Description:** The tester confirmed that the non-standard postal-code value used in this exercise is an invalid test value and that checkout should reject it. The screenshot shows checkout proceeding after `teste` is entered.
- **Preconditions:** SauceDemo is reachable; user is logged in and has at least one product in the cart.
- **Test data:** `standard_user` / `secret_sauce`; First Name `teste`, Last Name `teste`, postal-code value `teste` as shown in the supplied screenshots.
- **Steps to reproduce:**
  1. Sign in as `standard_user` and add a product.
  2. Open the cart and select **Checkout**.
  3. Enter the values above in the customer-information fields.
  4. Select **Continue**.
- **Expected result:** For this exercise, the invalid postal-code input is rejected and checkout does not advance.
- **Actual result:** In the current run, all three customer-information fields show `teste`; after Continue, the screenshot shows the checkout overview.
- **Severity / priority:** Low / Low.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Checkout form with non-standard value](../evidences/screenshots/bug-005-invalid-zip-code-step1.png); [checkout overview](../evidences/screenshots/bug-005-invalid-zip-code-step2.png).
- **Impact:** Invalid shipping information may be accepted into the order flow.

## Follow-up needed

BUG-002 through BUG-005 are confirmed for this educational exercise. Remaining evidence limitations: the BUG-003 captures do not show the logout action; BUG-004's captures establish an empty field but not a whitespace-only value; and BUG-002's login capture shows the username entered rather than the submitted login. These limitations are disclosed without changing the tester-confirmed rerun outcomes.
