# Test Execution Report

## Desktop Attendance Management System & IoT Hardware Integration

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Desktop Attendance Management System & IoT Hardware Integration |
| Document | Legacy App Test Execution Report |
| Application Version | v7.4 |
| Document Version | 1.0 |
| Author | Dimas Hidayat |
| Execution Period | August 2024 – Late October 2025 |
| Testing Type | Manual Testing |

---

# 1. Executive Summary

This document presents the execution results for the manual QA cycle of the Desktop Attendance Management System (v7.4). The objective of this cycle was to validate cloud integration stability, employee data integrity, device management workflows, and IoT synchronization reliability, alongside infrastructure-level environment validation.

A total of **17 test cases** were executed across 5 functional modules (`INT`, `SCH`, `EMP`, `DEV`, `SYNC`) and 1 environment/infrastructure category (`ENV`). Testing uncovered 6 defects, including 2 Critical-severity issues involving silent data corruption and identity mapping loss, while confirming the effectiveness of specialized environment isolation techniques (Mobile Hotspot routing, OS privilege elevation).

---

# 2. Test Execution Metrics

### 2.1 Execution Summary Dashboard

| Metric | Statistics | Percentage |
| :--- | :--- | :--- |
| **Total Test Cases Planned** | 17 | 100% |
| **Total Test Cases Executed** | 17 | 100% |
| **Passed Status** | 11 | 64.7% |
| **Failed Status** | 6 | 35.3% |
| **Blocked Status** | 0 | 0.0% |

### 2.2 Defect Breakdown by Severity

| Severity | Opened Bugs | Resolved | Remaining Open |
| :--- | :--- | :--- | :--- |
| **Critical** | 2 | 0 | 2 |
| **High** | 3 | 0 | 3 |
| **Medium** | 1 | 0 | 1 |
| **Low** | 0 | 0 | 0 |
| **Total** | **6** | **0** | **6** |

---

# 3. Module-Based Execution Breakdown

| Module | Planned | Executed | Passed | Failed | Success Rate (%) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **INT** (Cloud Integration) | 4 | 4 | 1 | 3 | 25.0% |
| **SCH** (Shift & Leave) | 2 | 2 | 2 | 0 | 100.0% |
| **EMP** (Employee Mgmt) | 5 | 5 | 4 | 1 | 80.0% |
| **DEV** (Device Mgmt) | 1 | 1 | 1 | 0 | 100.0% |
| **SYNC** (Device Sync / Error Handling) | 2 | 2 | 0 | 2 | 0.0% |
| **ENV** (Environment/Infrastructure) | 3 | 3 | 3 | 0 | 100.0% |

---

# 4. Detailed Defect Summary

| Defect ID | Associated TC | Module | Bug Description | Severity | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **BUG-P01** | TC-EMP-004 | Employee Data / Reporting | Insufficient input validation allows alphabetic characters into a structured numeric ID field, causing downstream report generation failures. | **Critical** | Reported — Root Cause Identified |
| **BUG-P02** | TC-INT-002 | Cloud Integration / Data | Absence of database schema validation allows mismatched parameters to save silently, breaking data routing without system alerts. | **High** | Reported — Mitigation Proposed |
| **BUG-P03** | TC-SYNC-001 | Device Connectivity / UX | Local network communication timeout triggers an un-cancelable sequence of 5 consecutive alert pop-ups, locking the primary application interface thread. | **High** | Reported — UX Flaw Identified |
| **BUG-P04** | TC-SYNC-002 | IoT Integration / Sync | Missing user ID collision verification during profile uploads to local biometric devices triggers a silent overwrite, scrambling profile mappings on the physical terminal. | **Critical** | Reported — Risk Analysis Attached |
| **BUG-P05** | TC-INT-004 | Cloud Integration / Sync | Cloud integration gateway encounters intermittent connection drops and data-fetching sync delays during prolonged automated streaming cycles. | **High** | Identified & Escalated to Development Team |
| **BUG-P06** | TC-INT-001 | Cloud Integration / UX | No built-in connection test mechanism available on cloud control panels — users cannot pre-validate API reachability before initiating data routing. | **Medium** | Reported — Feature Gap Identified |

Full defect details, including reproduction steps and mitigation notes, are documented in **LegacyAppDesktop-BugReport.md**.

---

# 5. Environmental QA Isolation Insights

Environment/infrastructure validation (`ENV` category) confirmed the effectiveness of specialized isolation techniques used throughout this testing cycle:

- **Network Infrastructure Comparison:** Confirmed hardwired LAN connections yield significantly higher stability and lower latency than Wi-Fi, informing recommendations for client deployment environments.
- **OS Privilege Elevation:** Confirmed that certain device sync failures are caused by Windows UAC restrictions rather than application defects; running the application with elevated Administrator privileges resolved the handshake failure.
- **Mobile Hotspot Network Isolation:** Confirmed this technique effectively isolates application-layer bugs from client-side network/firewall issues, directing appropriate escalation to client Network Administrators when needed.

---

# 6. Conclusion & Recommendation

The deployment of version **v7.4** exhibits notable instability within its cloud integration layer (`INT`) and IoT device synchronization layer (`SYNC`), with **2 unresolved Critical bugs** (silent NIK data corruption causing blank reports, and silent profile overwrite scrambling biometric identity mapping) alongside **3 High-severity bugs**, none of which had been resolved at the time of reporting.

This build **does not meet** the Exit Criteria established in the Master Test Plan. It is recommended to withhold client-side production deployment until these defects — particularly the Critical-severity data integrity issues — are resolved and re-verified through another regression pass.

Note: All defects listed remained open at the time of the author's departure from the project. Retesting and resolution verification were not completed within this employment period.

---

# 9. Related Documents

- LegacyAppDesktop-TestStrategy.md
- LegacyAppDesktop-StudyCaseTest.md
- LegacyAppDesktop-BugReport.md
- LegacyAppDesktop-TestExecutionReport.md
- LegacyAppDesktop-TestSummaryReport.md

---

## Notes

This document has been created for portfolio purposes based on professional QA practices. Company-specific implementation details, internal system names, and proprietary business logic have been generalized to comply with confidentiality obligations while preserving the overall testing workflow and methodology.
