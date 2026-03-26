# Test Plan - SauceDemo

## Objective

The objective of this test plan is to validate the core functionalities of the SauceDemo e-commerce application and ensure that the system behaves according to expected requirements.

## Scope

### In Scope

* User login and logout
* Product listing and sorting
* Cart operations (add/remove items)
* Checkout process

### Out of Scope

* Payment gateway integration
* Performance testing
* Mobile device testing

## Test Environment

* Application URL: https://www.saucedemo.com/ 
* Browser: Google Chrome
* Operating System: Windows 11
* Screen Resolution: 1920x1080

## Test Data

The following test users will be used:

* standard_user
* locked_out_user
* problem_user
* performance_glitch_user

Password for all users: secret_sauce

## Test Types

The following testing types will be performed:

* Functional Testing
* Regression Testing
* Exploratory Testing
* Negative Testing
* Usability Testing

## Test Types

Test cases were designed to cover end-to-end workflows including positive and negative scenarios.
Priority was assigned based on business impact.

Critical functionalities:

* Login
* Cart operations
* Checkout process


## Entry Criteria

* Application is accessible
* Test environment is ready
* Test cases are documented
* Test data is available

## Exit Criteria

* All critical test cases executed
* No critical bugs open
* Minimum pass rate of 90%
* Test execution report completed

## Risks and Mitigation

| Risk | Mitigation |
|------|------------|
| Test environment instability | Execute tests during low usage periods |
| Unexpected UI behavior | Document findings and retest |
| Lack of requirements | Base tests on expected user behavior |

## Deliverables

* Test Plan
* Test Cases
* Bug Reports
* Execution Report
* Test Evidence