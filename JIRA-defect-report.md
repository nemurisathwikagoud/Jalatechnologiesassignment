# JIRA defect report pack — Magnus

## Inspection boundary
The public page was inspected using a read-only web view on 27 Oct 2026. It exposes the login screen, recovery page, and admin-login page content. This inspection does not submit forms or authenticate, and it cannot confirm server-side validation behavior. The assignment's shared training credentials are displayed on the public login page; that is an observed design/security concern, but it may be intentional for a shared training environment. Confirm with the coordinator before filing as a defect.

## DEF-01 — Shared training credentials are displayed on the public login page
- **Status:** Observed in public page text; confirm whether intended before filing.
- **Suggested type/priority:** Security / Medium (subject to application policy)
- **Environment:** Public Magnus login page, inspected 27 Oct 2026.
- **Steps:** 1. Open https://magnus.jalatechnologies.com/. 2. Inspect the explanatory text above the sign-in form.
- **Observed:** Page displays a training email and password in plain text.
- **Expected:** If these are live reusable credentials, they should be handled according to the training environment's security policy; preferably credentials should be distributed privately or the account should be restricted/rotated.
- **Evidence:** Capture a screenshot of the page, avoiding sharing it outside the assignment context.
- **Note:** Since the assignment email itself distributes the same training credentials, ask the coordinator whether this is expected behavior before raising a formal bug.

## DEF-02 — Empty login submission does not show required-field validation
- **Status:** Candidate only — not verified.
- **Priority:** Medium if reproduced.
- **Steps:** Open login page; leave both inputs empty; click Sign In.
- **Expected:** Required-field validation is shown and authentication does not occur.
- **Actual:** Record the exact live result. File only if it differs from expected.
- **Evidence:** Screenshot of result.

## DEF-03 — Invalid password is accepted
- **Status:** Candidate only — not verified.
- **Priority:** Critical only if reproduced; otherwise do not file.
- **Steps:** Enter the training email and an incorrect password; click Sign In.
- **Expected:** Authentication is rejected and user remains unauthenticated.
- **Actual:** Record the exact live result. Never claim success without reproducing.
- **Evidence:** Screenshot without exposing credentials.

## DEF-04 — Malformed email is not validated or safely rejected
- **Status:** Candidate only — not verified.
- **Priority:** Low/Medium if reproduced.
- **Steps:** Enter `not-an-email` as email, a dummy password, and submit.
- **Expected:** Malformed input is rejected client-side or the login attempt is safely rejected.
- **Actual:** Record the exact live result.
- **Evidence:** Screenshot of validation/result.

## DEF-05 — Forgot Password action does not work
- **Status:** Candidate only — page exists, action not tested.
- **Priority:** Medium if reproduced.
- **Steps:** Open login page; click Forgot Password; enter a test email only if authorized; submit Get Password.
- **Expected:** Recovery flow responds clearly without exposing whether an account exists in a way that violates policy.
- **Actual:** Record exact result, including any error or dead-end.
- **Evidence:** Screenshot of the result page.

## Required JIRA fields
Summary; Issue Type = Bug; Priority; Environment; Preconditions; Steps to Reproduce; Expected Result; Actual Result; Attachments; Labels (`magnus`, `selenium`). Only file the candidate items after reproduction.
