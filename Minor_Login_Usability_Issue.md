### Minor Bug Report: Ambiguous Error Message on Failed Login

**Severity:** S3 
**Priority:** P3
**Product:** Authentication Module
**Component:** Login Form

---

**Description:**
When a user attempts to log in with either an incorrect username OR an incorrect password, the system displays the same generic error message ("Login failed. Please try again."). This common security practice hinders effective troubleshooting for users and requires additional support overhead.

**Steps to Reproduce:**
1. Navigate to the login page (e.g., `www.mybankingapp.com/login`).
2. **Scenario 1 (Invalid Username):** Enter `notaregisterduser@test.com` and a correct password. Click Login.
3. **Scenario 2 (Invalid Password):** Enter a correct, registered username and an intentionally wrong password. Click Login.

**Expected Result**
* **For Scenario 1 (Invalid Username):** The message should be clear, such as: "The username/email entered is not recognized."
* **For Scenario 2 (Invalid Password):** The message should be: "The password entered is incorrect."

**Actual Result:**
Both scenarios result in the identical message: "Login failed. Please try again." This lack of specificity is frustrating for users and generates unnecessary support tickets.

**Environment:**
* **Browser:** Safari v16
* **OS:** iOS Mobile Emulator
* **Target Audience Focus:** Mobile users who may mistype credentials quickly.

**Stakeholder Impact:**
This is a P3 issue, but addressing it improves user experience (UX) and reduces potential friction during the critical onboarding/login phase.
