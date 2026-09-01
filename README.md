Test Strategy & Scope

This section outlines the strategic approach used to verify the authentication module. The focus was to ensure high security, data integrity, and a seamless user experience across different setups.

### 1. In Scope 
*   **Functional Testing:** Valid and invalid login combinations, password masking, error message triggers, and session persistence.
*   **UI/UX Testing:** Alignment of input fields, responsiveness of button elements, typography visibility, and screen zoom behavior.
*   **Boundary Value Analysis (BVA):** Character limits for email input fields and extreme password lengths.

### 2. Out of Scope 
*   Performance testing under peak user traffic simulation.
*   Multi-Factor Authentication (MFA) via live hardware security keys.
*   Database-level encryption verification.
*   ### 3. Test Environment
*   **Operating System:** Windows 11 Home
*   **Browser:** Google Chrome (Desktop Version)
*   **Network:** Broadband Wi-Fi (Standard domestic connection)

### 4. Defect Triage & Severity Criteria
*   **Critical:** Application crashes, server-side dynamic breakdowns, or security leaks.
*   **High:** Core flows blocked with no alternative workaround (e.g., dynamic password locks).
*   **Medium:** Secondary feature malfunction with operational workarounds available.
*   **Low:** Visual misalignment, font truncation, or localization spelling mistakes.
