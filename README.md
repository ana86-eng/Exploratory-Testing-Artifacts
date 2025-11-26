# Exploratory-Testing-Artifacts
### Critical Bug Report: Payment Gateway Fails on Timeout

**Product:** E-Commerce Checkout Module
**Component:** Payment Service Integration (Third-Party Redirect)
**Status:** Open / Needs Dev Triage
**Reported By:** Ana Isofi

---

**Severity:** S1 (Blocker)
**Priority:** P1 (Highest)

**Description:**
If a user is redirected from the site to the external payment gateway and the connection times out (after 30 seconds), the system does not revert the cart status. The application hangs indefinitely on a blank loading screen instead of returning the user to the payment selection page with an error, leading to a blocked checkout flow.

**Steps to Reproduce:**
1. Log in as a registered user (e.g., `testuser@example.com`).
2. Add Item X (e.g., Product ID: 4567) to the shopping cart.
3. Navigate to the Checkout page and confirm shipping details.
4. Select "Credit Card" as the payment method.
5. Click "Proceed to Payment."
6. **[Crucial Step for Expl. Testing]:** While on the external gateway screen, intentionally sever the network connection or simulate a 30-second API timeout (e.g., using browser dev tools or a mock server).

**Expected Result:**
The system should return the user to the "Payment Method Selection" page and display a clear, actionable error message: "Payment Failed: Connection Timeout. Please try again." The shopping cart should remain active.

**Actual Result:**
The browser remains on a blank loading screen indefinitely. The system status for the cart is unclear, and the user cannot recover the transaction without closing the browser, resulting in a critical flow failure.

**Environment:**
* **Browser:** Chrome v120.0 (Latest)
* **OS:** Windows 11
* **Build/Version:** v2.3.1 (Staging)

