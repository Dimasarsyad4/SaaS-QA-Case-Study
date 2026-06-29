# QA Manual Tester Portfolio: Portfolio Case Study
**Platform:** Fingerspot.io (Cloud-Based HR & Attendance SaaS)  
**Role:** QA Manual Tester  
**Platform Type:** Web Application (Admin & HR Dashboard) + IoT Hardware Integration  
**Testing Types:** Functional Testing, Regression Testing, Integration Testing, Boundary Value Analysis, and Usability Testing.  
**Project Artifact:** https://docs.google.com/spreadsheets/d/198XbGm-sGSpqSK7jHHXOpqpWBGx37SyOocW86j-avZo/edit?usp=sharing

---

## 1. Project Overview & Situation
Fingerspot.io is a robust SaaS (Software as a Service) platform designed for online attendance and Human Resource Management (HRM). The platform handles complex enterprise business logic, managing everything from subscription billing and e-commerce packages to data synchronization from physical IoT fingerprint/face-recognition hardware.

When I handled the platform, the product was fully functional and operational (existing project). However, it underwent frequent, rapid updates and feature enhancements. My primary challenge was to ensure that new code deployments did not disrupt the existing core systems (Critical Paths), such as login persistence, payroll data, and payment gateways, especially since there was no pre-existing comprehensive QA documentation legacy.

---

## 2. My Tasks & Responsibilities
*   **Feature Enhancement Validation:** Designing and executing functional test scenarios for brand-new UI elements and calculations (e.g., Auth improvements and shopping cart calculations).
*   **Regression Testing Management:** Conducting comprehensive end-to-end regression testing before production releases to ensure existing sub-modules (such as employee registration and payroll reports) remained unaffected.
*   **Payment Gateway & Checkout Audit:** Verifying third-party payment integration and QRIS timeout behaviors to protect company revenue and minimize user drop-offs.
*   **Hardware-to-Cloud Integration Analysis:** Identifying network, database, payload sync errors, and data collision vulnerabilities between physical attendance machines and the cloud database.

---

## 3. Core Testing Scenarios & Methodologies
I structured my manual testing execution into primary segments, combining positive, negative, and boundary value analysis:

### A. Authentication Module (Login Update)
*   **Scenario:** Validating the newly added "Remember Me" checkbox functionality.
*   **Approach:** Performed session persistence testing. Verified that when a user checked the box and successfully logged in, closing and reopening the browser tab kept the session alive. Conversely, verified that clicking "Logout" successfully flushed all tokens/cookies from the browser storage for security compliance.

### B. E-Commerce & Subscription Billing Module
*   **Scenario:** Testing the dynamic pricing and package scaling calculations in the subscription shopping cart.
*   **Approach:** Conducted Boundary Value Analysis (BVA). Verified that the sub-total dynamically recalculated when increasing the package amount. For negative testing, I input zero (`0`) or negative values to ensure the system gracefully handles the logic by displaying a deletion/cancellation confirmation pop-up instead of generating application errors.

### C. Employee Management (Data Integrity & Unique ID Validation)
*   **Scenario:** Ensuring strict database constraints are enforced during manual web onboarding.
*   **Approach:** Performed negative testing by manually creating a new employee using an Employee ID that already existed in the system. Verified that the system successfully intercepted the request, blocked the registration, and threw a proper unique validation error message.

### D. IoT Hardware Sync & Integration
*   **Scenario:** Verifying offline caching, data fetching resilience, and hardware-level unique ID validation.
*   **Approach:** Simulated hard network drops on physical biometric machines to ensure data was cached locally. Validated API stability during mass data fetches from over 50 physical machines concurrently. Checked unique ID logic synchronization between the hardware local storage and the cloud dashboard.

---

## 4. Defect Discovery & High-Impact Bug Logs
During the testing cycles, I discovered and documented several high-severity defects that could have led to severe revenue leakage or critical user data corruption if released to production:

### 🐛 BUG-001: Quota Leak on Subscription Plan Page
*   **Module:** Subscription
*   **Severity:** High | **Priority:** High
*   **Actual Result:** Every time an admin user clicked to view the subscription plan information page, the system automatically and erroneously decremented the user's GPS App Quota in the database without any real transaction or checkout taking place.
*   **Resolution:** *Resolved.* Isolated the backend query execution to ensure data fetch requests no longer trigger unauthorized database writes.

### 🐛 BUG-002: Complete Outage of Major Payment Gateways Post-Update
*   **Module:** Payment / Checkout
*   **Severity:** High | **Priority:** High
*   **Actual Result:** Following a payment infrastructure update, a critical regression defect occurred. Key payment channels—including major Virtual Accounts (BCA, BRI, BSI) and popular e-wallets (GoPay)—completely disappeared from the user checkout screen, leaving only BNI, Mandiri, and an unoptimized QRIS option. This blocked primary revenue streams.
*   **Resolution:** *Resolved.* Rolled back the regression patch and re-stabilized the third-party payment gateway integrations.

### 🐛 BUG-003: Aggressive QRIS Code Timeout Window
*   **Module:** Payment / Checkout
*   **Severity:** Medium | **Priority:** High
*   **Actual Result:** The newly generated QRIS code automatically expired within 2 to 3 minutes. This unrealistically short window caused high transaction failure rates and triggered continuous customer support complaints.
*   **Resolution:** *Resolved.* Extended the hardcoded expiration window to a standardized 15-minute grace period.

### 🐛 BUG-004: Reference Code Input Field Locked as Read-Only
*   **Module:** HR Admin / Profile Update
*   **Severity:** Medium | **Priority:** Medium
*   **Actual Result:** When modifying an existing employee profile, the "Employee Reference Code" field was incorrectly hard-locked as Read-Only. The system treated the input field as if it only applied to brand-new registrations.
*   **Resolution:** *Resolved.* Corrected front-end data binding to allow seamless profile updates for existing employees.

### 🐛 BUG-005: IoT Data Collision & Overlapping Attendance Reports
*   **Module:** IoT Sync / Reports
*   **Severity:** High | **Priority:** High
*   **Actual Result:** Discovered an architectural synchronization flaw. If an employee is registered via the cloud dashboard using ID `1`, and another employee is simultaneously registered directly on the physical attendance machine using the exact same ID, the cloud correctly flags it for approval. However, the physical hardware's local storage fails to reject the duplicate ID. Consequently, when attendance logs are fetched from that machine, the generated reports become corrupted and display mixed-up log entries between two entirely different employees.
*   **Status:** *Open (Isolated Risk / Mitigation In-Place).* 
*   **Operational Workaround / Impact:** To clear the active collision, the newly registered employee profile must be manually deleted from the system. This action permanently wipes out the attendance history **only for that specific new employee**, while the existing/old employee's profile and historical logs remain completely safe and unaffected.

---

## 5. Key Results & Personal Takeaways
*   **Revenue & Business Protection:** By thoroughly identifying the disappearing payment methods (BUG-002) and premature QRIS timeouts (BUG-003), I successfully prevented high customer drop-off rates and thousands of dollars in lost subscription revenue before release.
*   **Risk Mitigation & Technical Isolation:** Finding the complex IoT data collision bug (BUG-005) allowed me to map out the exact blast radius of the system vulnerability. I helped design an operational SOP that isolated the risk strictly to new entries, preserving years of pristine legacy data for our enterprise clients.
*   **Legacy Documentation Building:** Since the project initially lacked a structured QA framework, the test cases and bug logs I created now serve as the baseline regression testing suite for all future developers and QA engineers onboarding onto the Fingerspot.io team.
