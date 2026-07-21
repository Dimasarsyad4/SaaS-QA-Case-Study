# QA Manual Tester: Portfolio Case Study

**Platform Type:** Next-Gen Desktop Attendance & IoT Management Application  
**Role:** QA Manual Tester & Technical Support  
**Testing Types:** Functional Testing, Regression Testing, Integration Testing, Boundary Value Analysis (BVA), Negative Testing, Environment Validation

---

# 1. Project Overview & Situation

This project involved testing a next-generation desktop attendance management application that supports workforce management through employee administration, shift scheduling, leave management, and biometric attendance device integration.

The application combines desktop software, local biometric hardware, and cloud synchronization services to support daily attendance operations across enterprise environments.

As a branch-level QA Manual Tester, my responsibilities included validating new features, reproducing customer-reported issues, executing regression testing before software releases, and verifying stable communication between desktop applications, biometric devices, and cloud services.

Throughout multiple software releases (v1.7.1 – v1.7.4), the primary objective was ensuring application stability while minimizing regression risks across business-critical modules and hardware integrations.

---

# 2. My Tasks & Responsibilities

- Designed and executed manual test scenarios based on functional requirements and business workflows.
- Performed Functional Testing, Regression Testing, Integration Testing, Boundary Value Analysis (BVA), and Negative Testing.
- Validated employee management, shift scheduling, leave management, device registration, synchronization, and application configuration.
- Verified communication between desktop applications and biometric attendance devices across multiple hardware models.
- Performed installation validation, startup verification, and environment testing across supported Windows operating systems.
- Reproduced customer-reported defects, documented findings, verified bug fixes, and monitored recurring issues.
- Collaborated with Technical Support and Developers to investigate root causes, validate fixes, and improve software quality before production deployment.

---

# 3. Core Testing Scenarios & Methodologies

Testing activities focused on validating both business functionality and hardware integration across the application's primary modules.

## A. Employee Management

- Validate employee registration using valid and invalid input.
- Verify mandatory field validation.
- Perform Boundary Value Analysis (BVA) on Employee ID fields.
- Verify employee profile editing and deletion.
- Perform Negative Testing on invalid input formats.

---

## B. Shift & Leave Management

- Validate shift creation, modification, and deletion.
- Verify overnight shift calculation.
- Validate leave type configuration.
- Verify leave quota calculation.
- Execute regression testing after business rule changes.

---

## C. Device Management & Hardware Integration

- Verify biometric device registration.
- Validate device authentication.
- Test automatic device discovery.
- Verify manual device configuration.
- Validate synchronization between desktop applications and biometric devices.
- Verify application behavior when device communication is interrupted.

---

## D. Network & Cloud Synchronization

- Verify attendance synchronization between local devices and cloud services.
- Validate communication using LAN and isolated Mobile Hotspot environments.
- Perform root cause isolation to distinguish software defects from network infrastructure issues.
- Verify synchronization recovery after temporary network failures.

---

## E. Environment Validation

- Validate fresh application installation.
- Verify application startup after installation.
- Execute application using Standard User and Administrator privileges.
- Verify compatibility across multiple Windows versions.
- Validate compatibility across supported biometric device models.

---

# 4. Defect Discovery — Summary of Findings

During multiple testing cycles, eight defects were identified, documented, and tracked throughout the software lifecycle.

| Bug Category | Severity | Status | Summary |
| :--- | :--- | :--- | :--- |
| Application freezes during first launch after fresh installation | High | Partially Resolved | Startup performance has significantly improved, although the issue may still occur intermittently after fresh installations. |
| Socket connection occasionally disconnects during manual device registration | High | Resolved (Monitoring) | The issue has been fixed. Similar reports continue to be monitored based on customer feedback. |
| Employee ID field accepts alphabetic and special characters | Medium | Open | Numeric validation has not yet been implemented and remains under development. |
| Application crashes when editing or deleting an active shift configuration | Critical | Closed | The issue was fixed and successfully verified through regression testing. |
| Incorrect cross-day working hour calculation when the clock-out record is missing | High | Closed | Calculation logic was corrected and verified during retesting. |
| Auto Scan fails to detect all biometric devices on the local network | High | Monitoring | Detection reliability has improved, but ongoing monitoring continues across different deployment environments. |
| Device authentication occasionally rejects valid terminal passwords | High | Monitoring | Authentication stability continues to be monitored across multiple device models and network conditions. |
| Default device password is not automatically populated based on selected device type | Low | Closed | Default values are now automatically populated according to the selected device type, reducing configuration errors. |

### Defect Statistics

| Metric | Total |
|---------|------:|
| Total Defects Identified | **8** |
| Critical | **1** |
| High | **5** |
| Medium | **1** |
| Low | **1** |
| Closed | **3** |
| Partially Resolved | **1** |
| Resolved (Monitoring) | **1** |
| Monitoring | **2** |
| Open | **1** |

> **Detailed bug reproduction steps, internal implementation details, and complete defect logs are intentionally excluded from this public portfolio to comply with Non-Disclosure Agreement (NDA) obligations. These artifacts are available for discussion during technical interviews upon request.**

---

# 5. Key Results & Personal Takeaways

- Improved application stability by performing structured regression testing across multiple software releases.
- Helped identify critical defects before production deployment, reducing operational risks for end users.
- Applied systematic root cause isolation techniques to distinguish application defects from network or environment-related issues.
- Improved confidence in biometric device integration through repeated verification across multiple hardware models and deployment environments.
- Supported Technical Support and Development teams by reproducing customer-reported issues, validating bug fixes, and documenting testing outcomes.
- Contributed to establishing a more structured manual testing process through consistent test execution, regression validation, defect tracking, and issue monitoring.

---

# Testing Approach Highlights

- Manual Functional Testing
- Regression Testing
- Integration Testing
- Boundary Value Analysis (BVA)
- Negative Testing
- Environment Validation
- Installation Testing
- Root Cause Isolation
- Hardware Compatibility Testing
- Defect Verification & Retesting

---

## Related Documents

- NextGenDesktop-TestStrategy.md
- NextGenDesktop-TestPlan.md
- NextGenDesktop-BugReport.md
- NextGenDesktop-TestExecutionReport.md
- NextGenDesktop-TestSummaryReport.md

> **Detailed Test Cases and Bug Log are intentionally excluded from this public repository to comply with Non-Disclosure Agreement (NDA) obligations. These artifacts are available for discussion during technical interviews upon request.**

---

## Notes

This document has been prepared for portfolio purposes based on professional manual Quality Assurance practices performed in an enterprise desktop application environment.

Company names, application names, customer information, hardware models, proprietary workflows, and implementation details have been generalized to comply with Non-Disclosure Agreement (NDA) obligations while preserving the overall testing methodology, quality assurance processes, and technical problem-solving approaches.
