# Bug Reports and Observation Register — SauceDemo

## Review basis

This register preserves all five original IDs and their evidence while distinguishing confirmed defects from behaviors that are expected or need investigation. No approved product requirements or acceptance criteria were supplied. A test failure or unexpected appearance alone is not sufficient to confirm a defect.

All 36 test cases were rerun on 2026-11-10; the tester reported 32 Pass and 4 Fail. The four failures remain TC-007, TC-023, TC-024, and TC-035. Reported environment: Windows 11 and Google Chrome 157.0.8103.50 (64-bit). Tester identity and display resolution were not recorded. The screenshots below are from the current run where indicated; evidence gaps are called out rather than inferred.

| ID | Reviewed disposition | Original severity / priority | Current severity / priority |
|---|---|---|---|
| BUG-001 | Expected behavior; not a defect | High / High | Not assigned; classification withdrawn |
| BUG-002 | Observed behavior; investigate account/product-image expectation | Medium / Medium | Not assigned |
| BUG-003 | Observed behavior; investigate cart lifecycle requirement and sequence | Medium / High | Not assigned |
| BUG-004 | Observed behavior; clarify required-name/whitespace rule | Low / Low | Not assigned |
| BUG-005 | Observed behavior; clarify supported ZIP/postal-code rule | Low / Low | Not assigned |

The original labels are retained here only as historical information, not as current defect severities or priorities. No report is currently classified as a confirmed defect.

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

## BUG-002 — Same product image displayed for multiple products with `problem_user`

**Disposition:** Observed behavior requiring investigation; not a confirmed defect.

- **Description:** Current evidence shows the same dog image on multiple inventory products while signed in as `problem_user`. A separate current screenshot shows the login form with that username entered. The repository does not establish whether the account is intended to seed anomalous behavior or what image behavior is required for it.
- **Preconditions:** SauceDemo is reachable; user is not logged in.
- **Test data:** `problem_user` / `secret_sauce`.
- **Steps to reproduce:**
  1. Open https://www.saucedemo.com/.
  2. Sign in as `problem_user`.
  3. Inspect the product images on the inventory page and compare them with the product names.
- **Expected result:** No approved product-image acceptance criterion is available. The original expectation that every image match its product is retained as a test condition, not an established requirement.
- **Actual result:** The current inventory screenshot shows the same dog image for multiple named products. The current login screenshot shows `problem_user` entered but does not itself show the login submission.
- **Original severity / priority:** Medium / Medium; retained as historical labels only.
- **Current severity / priority:** Not assigned pending confirmation of the account's intended behavior and product requirement.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Problem-user login form](../evidences/screenshots/bug-002-problem-user-images%20%282%29.png); [inventory with repeated product image](../evidences/screenshots/bug-002-problem-user-images.png).
- **Potential impact:** Product identification may be impaired if the displayed images violate the intended behavior. Business/user impact is not established without the account requirement.

## BUG-003 — Cart contents observed after logout/login

**Disposition:** Observation requiring investigation; not a confirmed defect.

- **Description:** The 2026-11-10 rerun reports that the cart contents remained after logout/login. No supplied requirement says whether the cart must be cleared or persist for the same user. Current screenshots show two products before login and a cart badge of 2 after login, but do not show the intervening logout action.
- **Preconditions:** SauceDemo is reachable; use the same demo account for both logins.
- **Test data:** `standard_user` / `secret_sauce`; the original report refers to two products, but the screenshots do not prove a matching pre-logout cart state.
- **Steps to reproduce:**
  1. Sign in as `standard_user`.
  2. Add products to the cart and record the product names and cart count.
  3. Use the application menu to log out.
  4. Sign in again as the same user.
  5. Open the cart and compare its contents with the recorded pre-logout state.
- **Expected result:** Undetermined. No cart-clearing or cart-persistence requirement was supplied.
- **Actual result:** The rerun result is Fail against the workbook's empty-cart test condition. The current before-login screenshot shows Backpack and Bike Light in the cart; the after-login inventory screenshot shows a cart badge of 2. This is consistent with persistence, but the images alone do not prove the logout action or that the same account/session was used.
- **Original severity / priority:** Medium / High; retained as historical labels only.
- **Current severity / priority:** Not assigned pending requirement and sequence confirmation.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Cart before login](../evidences/screenshots/bug-003-cart-before-login.png); [inventory after login](../evidences/screenshots/bug-003-cart-after-login.png).
- **Potential impact:** Unintended retention or loss could affect a user if it violates the defined cart lifecycle. No such impact can be established without the requirement and a verified sequence.

## BUG-004 — Checkout proceeds with an empty first name

**Disposition:** Observed behavior requiring a business rule; not a confirmed defect.

- **Description:** The historical title claimed that the First Name field accepts blank spaces. The supplied first screenshot shows the field empty, not whitespace-only input. The following screenshot shows checkout proceeding to the order overview. The evidence supports an empty-value observation but does not support the original whitespace-specific claim.
- **Preconditions:** SauceDemo is reachable; user is logged in and has at least one product in the cart.
- **Test data:** `standard_user` / `secret_sauce`; empty First Name; the screenshots show `teste` in Last Name and `00000-000` in the postal-code field.
- **Steps to reproduce:**
  1. Sign in as `standard_user` and add a product.
  2. Open the cart and select **Checkout**.
  3. Leave First Name empty; enter the recorded Last Name and postal-code values if reproducing the screenshot.
  4. Select **Continue**.
- **Expected result:** No approved rule states whether First Name is required or whether whitespace-only values must be rejected. The original validation expectation is not established.
- **Actual result:** In the current run, the screenshot shows First Name empty while Last Name and postal code contain values; the follow-up screenshot shows the checkout overview. The evidence supports empty input, not whitespace-only input.
- **Original severity / priority:** Low / Low; retained as historical labels only.
- **Current severity / priority:** Not assigned pending an approved required-field and whitespace policy.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Checkout form](../evidences/screenshots/bug-004-first-name-space-step1.png); [checkout overview](../evidences/screenshots/bug-004-first-name-space-step2.png).
- **Potential impact:** Incomplete customer information may matter if the application requires it; that requirement and downstream impact have not been established.

## BUG-005 — Checkout proceeds with a non-standard ZIP value

**Disposition:** Observed behavior requiring a business rule; not a confirmed defect.

- **Description:** The screenshots show checkout proceeding after the value `teste` is entered in the postal-code field. No approved requirement defines the supported country, postal-code format, or validation rules. It is not justified to assume ZIP codes must contain only digits.
- **Preconditions:** SauceDemo is reachable; user is logged in and has at least one product in the cart.
- **Test data:** `standard_user` / `secret_sauce`; First Name `teste`, Last Name `teste`, postal-code value `teste` as shown in the supplied screenshots.
- **Steps to reproduce:**
  1. Sign in as `standard_user` and add a product.
  2. Open the cart and select **Checkout**.
  3. Enter the values above in the customer-information fields.
  4. Select **Continue**.
- **Expected result:** Undetermined. No postal-code format or invalid-value handling requirement was supplied.
- **Actual result:** In the current run, all three customer-information fields show `teste`; after Continue, the screenshot shows the checkout overview.
- **Original severity / priority:** Low / Low; retained as historical labels only.
- **Current severity / priority:** Not assigned pending an approved postal-code rule.
- **Environment:** Current run: Google Chrome 157.0.8103.50 (64-bit), Windows 11; reported run date 2026-11-10.
- **Evidence:** [Checkout form with non-standard value](../evidences/screenshots/bug-005-invalid-zip-code-step1.png); [checkout overview](../evidences/screenshots/bug-005-invalid-zip-code-step2.png).
- **Potential impact:** Incorrect shipping data could matter if the value is invalid under the intended market rules; neither the supported format nor shipping impact is established.

## Follow-up needed

Before any of BUG-002 through BUG-005 can be confirmed or assigned severity/priority, obtain the applicable product/account behavior and acceptance criteria. For BUG-003, capture the logout action and account context in the same sequence. For BUG-004, clarify whether empty and whitespace-only inputs are both prohibited. For BUG-005, define the supported country/format and validation rule. Preserve the current screenshots and add requirement-linked evidence if the rules are confirmed.
