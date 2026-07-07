# QA Manual Tester: Web SaaS Platform Case Study
**Platform Type:** Cloud-Based HR & Attendance SaaS (Web Admin Dashboard + IoT Hardware Integration)
**Role:** QA Manual Tester & Technical Support
**Testing Types:** Functional Testing, Regression Testing, Integration Testing, Boundary Value Analysis (BVA), Negative Testing, Usability Testing

---

## 1. Project Overview & Situation

This project involved testing a SaaS platform for online attendance and Human Resource Management (HRM), handling enterprise business logic ranging from subscription billing to data synchronization between physical IoT biometric hardware and the cloud database.

The product was a live, actively-used system undergoing frequent feature updates. My primary challenge was ensuring new deployments did not disrupt critical paths — such as authentication, operational data, and payment processing — particularly given the absence of a pre-existing structured QA documentation framework.

---

## 2. My Tasks & Responsibilities

- **Feature Enhancement Validation:** Designed and executed functional test scenarios for new UI elements and business calculations (e.g., authentication improvements, dynamic pricing calculations).
- **Regression Testing Management:** Conducted end-to-end regression testing before production releases to ensure existing modules (employee management, payroll reporting) remained stable.
- **Payment Flow Audit:** Verified third-party payment integration behavior and timeout handling to protect revenue continuity and minimize user drop-off.
- **Hardware-to-Cloud Integration Analysis:** Identified network, database, and data synchronization issues between physical attendance devices and cloud infrastructure.

---

## 3. Core Testing Scenarios & Methodologies

I structured manual testing execution across key modules, combining positive, negative, and boundary value testing approaches:

### A. Authentication Module
- **Scenario:** Validated session persistence functionality ("Remember Me").
- **Approach:** Verified session behavior across browser restarts, and confirmed secure token/cookie clearance upon logout.

### B. Subscription & Billing Module
- **Scenario:** Tested dynamic pricing and package scaling logic in the billing flow.
- **Approach:** Applied Boundary Value Analysis (BVA) to verify recalculation accuracy when adjusting package quantities. Conducted negative testing with zero/invalid inputs to confirm graceful error handling rather than application crashes.

### C. Employee Data Management
- **Scenario:** Verified database constraint enforcement during employee onboarding.
- **Approach:** Performed negative testing by attempting to register duplicate Employee IDs, confirming the system correctly intercepted and blocked invalid entries with appropriate error messaging.

### D. IoT Hardware Sync & Integration
- **Scenario:** Verified offline caching, data fetch resilience, and synchronization stability.
- **Approach:** Simulated network disruptions between physical devices and cloud services to validate local data caching. Tested API stability under concurrent multi-device data fetches.

---

## 4. Defect Discovery — Summary of Findings

During testing cycles, I identified and documented several high-severity defects prior to production release, contributing to platform stability and revenue protection:

| Bug Category | Severity | Outcome |
|---|---|---|
| Billing/quota calculation anomaly on a non-transactional page view | High | Resolved — backend query isolated from unintended write operations |
| Payment channel availability regression after infrastructure update | High | Resolved — rollback and re-stabilization of payment integrations |
| Overly aggressive transaction code expiration window | Medium | Resolved — expiration window extended to industry-standard duration |
| Read-only field lock preventing legitimate data updates | Medium | Resolved — front-end data binding corrected |
| Data synchronization edge case between cloud and local hardware storage under concurrent ID registration | High | Identified, escalated, and mitigated through operational safeguards |

*(Full technical reproduction steps and internal system details are withheld in accordance with confidentiality obligations to the employer. Detailed walkthroughs available upon request during interviews.)*

---

## 5. Key Results & Personal Takeaways

- **Revenue & Business Protection:** Identifying payment flow regressions and transaction timeout issues before release helped prevent customer drop-off and potential revenue loss.
- **Risk Mitigation & Technical Isolation:** Systematic root-cause analysis on hardware-cloud sync issues enabled the team to scope risk accurately and protect existing enterprise client data.
- **Process Contribution:** Since the project initially lacked a structured QA framework, the test cases and documentation practices I introduced helped establish a more repeatable regression testing approach for the team.

---

## Testing Approach Highlights

- Strong focus on **negative testing** and **boundary value analysis** to uncover edge cases beyond standard happy-path testing.
- Practical **root cause isolation techniques** — including network environment isolation (e.g., testing via isolated network connections) to distinguish application-layer issues from infrastructure/network-layer issues.
- Experience escalating cross-team technical issues with clear, structured findings to development teams.
- Comfortable working with both **web/cloud systems** and **physical IoT hardware integration** — a less common but valuable QA skill set.

---

*Note: Company and product names have been generalized, and specific technical reproduction details have been withheld to respect confidentiality obligations to my previous employer. I'm happy to discuss the technical depth of this work directly in an interview setting.*
