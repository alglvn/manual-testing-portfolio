## 🎯 Test Strategy & Scope

This section outlines the strategic approach used to verify the authentication module. The focus was to ensure high security, data integrity, and a seamless user experience across different setups.

### 1. In Scope 
*   **Functional Testing:** Valid and invalid login combinations, password masking, error message triggers, and session persistence.
*   **UI/UX Testing:** Alignment of input fields, responsiveness of button elements, typography visibility, and screen zoom behavior.
*   **Boundary Value Analysis (BVA):** Character limits for email input fields and extreme password lengths.

### 2. Out of Scope 
*   Performance testing under peak user traffic simulation.
*   Multi-Factor Authentication (MFA) via live hardware security keys.
*   Database-level encryption verification.

### 3. Test Environment
*   **Operating System:** Windows 11 Home
*   **Browser:** Google Chrome (Desktop Version)
*   **Network:** Broadband Wi-Fi (Standard domestic connection)

### 4. Defect Triage & Severity Criteria
*   **Critical:** Application crashes, server-side dynamic breakdowns, or security leaks.
*   **High:** Core flows blocked with no alternative workaround (e.g., dynamic password locks).
*   **Medium:** Secondary feature malfunction with operational workarounds available.
*   **Low:** Visual misalignment, font truncation, or localization spelling mistakes.


### 📊 Executed Test Cases

*   **TC_001: Verify successful login with valid credentials (Happy Path)**
    *   **Component:** Login
    *   **Pre-conditions:** User has a registered and active account.
    *   **Test Steps:**
        1. Navigate to LinkedIn login page.
        2. Enter valid email address.
        3. Enter valid matching password.
        4. Click "Sign In" button.
    *   **Test Data:** `valid_user@email.com` / `ValidPass123!`
    *   **Expected Result:** User is successfully authenticated and redirected to the home feed dashboard.
    *   **Actual Result:** Authentication fails, keeping the user on the login section with the error message: “That’s not the right password.”
    *   **Status:** **FAILED** ❌ *(See Bug Report #1 under Issues)*

*   **TC_002: Verify error message when entering an incorrect password (Negative Path)**
    *   **Component:** Login
    *   **Pre-conditions:** User has a registered and active account.
    *   **Test Steps:**
        1. Navigate to LinkedIn login page.
        2. Enter valid email address.
        3. Enter an incorrect password.
        4. Click "Sign In" button.
    *   **Test Data:** `valid_user@email.com` / `WrongPassword999`
    *   **Expected Result:** Login fails. User remains on the page, and an inline error message "That's not the right password" is displayed.
    *   **Actual Result:** Same as expected.
    *   **Status:** **PASSED** ✅

*   **TC_003: Verify validation triggers when submitting empty credentials (Negative Path)**
    *   **Component:** Login
    *   **Pre-conditions:** None
    *   **Test Steps:**
        1. Navigate to LinkedIn login page.
        2. Leave Email and Password fields empty.
        3. Click "Sign In" button.
    *   **Test Data:** None
    *   **Expected Result:** Form submission is blocked. Red validation errors appear under both fields: "Please enter an email address or phone number" and "Please enter a password".
    *   **Actual Result:** Same as expected.
    *   **Status:** **PASSED** ✅

*   **TC_004: Verify Sign-In button layout rendering at high zoom levels**
    *   **Component:** UI Responsive
    *   **Pre-conditions:** None
    *   **Test Steps:**
        1. Navigate to LinkedIn login page.
        2. Change browser layout zoom level to 175%.
        3. Inspect the primary Sign-in button.
    *   **Test Data:** Browser Zoom = 175%
    *   **Expected Result:** The button text container dynamically adjusts alignment and keeps font scaling fully centered without content clipping.
    *   **Actual Result:** The button width stays fixed. The text overflows the blue container boundaries, extending into the landing page background and getting cut off vertically at the baseline.
    *   **Status:** **FAILED** ❌ *(See Bug Report #2 under Issues)*
