# Test Execution Report

## Next-Gen Desktop Attendance & IoT Management Application

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Next-Gen Desktop Attendance & IoT Management Application |
| Document | Test Execution Report |
| Application Version | v1.7.1 – v1.7.4 |
| Document Version | 1.0 |
| Author | Dimas Hidayat |
| Execution Period | Late October 2025 - February 2026 |
| Testing Type | Manual Testing |

---

# 1. Executive Summary

This document presents the execution results for the manual QA cycle of the 
Next-Gen Desktop Attendance & IoT Management Application (v1.7.1–v1.7.4). 
The objective of this cycle was to validate employee data integrity, shift/leave 
calculation accuracy, device management workflows, and IoT/network reliability 
across successive version releases.

A total of **19 test cases** were executed across 5 functional modules 
(`REG`, `SCH`, `LEV`, `DEV`, `NET`) and 1 environment/non-functional category 
(`ENV`). Testing uncovered 8 defects spanning Low to Critical severity, 
including one application crash and several silent validation failures.

---

# 2. Test Execution Metrics

### 2.1 Execution Summary Dashboard

| Metric | Statistics | Percentage |
| :--- | :--- | :--- |
| **Total Test Cases Planned** | 19 | 100% |
| **Total Test Cases Executed** | 19 | 100% |
| **Passed Status** | 11 | 57.9% |
| **Failed Status** | 8 | 42.1% |
| **Blocked Status** | 0 | 0.0% |

### 2.2 Defect Breakdown by Severity

| Severity | Opened Bugs |
| :--- | :--- |
| **Critical** | 2 |
| **High** | 5 |
| **Medium** | 0 |
| **Low** | 1 |
| **Total** | **8** |

---

# 3. Module-Based Execution Breakdown

| Module | Planned | Executed | Passed | Failed | Success Rate (%) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **REG** (Employee Mgmt) | 3 | 3 | 2 | 1 | 66.7% |
| **SCH** (Schedule/Shift) | 4 | 4 | 2 | 2 | 50.0% |
| **LEV** (Leave) | 2 | 2 | 2 | 0 | 100.0% |
| **DEV** (Device & Integration) | 6 | 6 | 3 | 3 | 50.0% |
| **ENV** (Environment/Non-Functional) | 4 | 4 | 2 | 2 | 50.0% |

---

# 4. Detailed Defect Summary

| Defect ID | Associated TC | Module | Bug Description | Severity | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **BUG-001** | TC-ENV-001 | Employee Mgmt | Application occasionally freezes on the splash screen during first launch after a fresh installation. | **High** | Partially Resolved |
| **BUG-002** | TC-ENV-003 | IoT | Socket connection occasionally disconnects during manual device registration. | **High** | Resolved (Monitoring) |
| **BUG-003** | TC-REG-003 | Employee Mgmt | Employee ID field accepts alphabetic and special characters without validation. | **Critical** | Open |
| **BUG-004** | TC-SCH-003 | Schedule/Shift | Application crashes when editing or deleting an active shift configuration. | **Critical** | Closed |
| **BUG-005** | TC-SCH-004 | Schedule/Shift | Incorrect cross-day working hour calculation when the clock-out record is missing. | **High** | Closed |
| **BUG-006** | TC-DEV-003 | Device & Integration | Auto Scan fails to detect all biometric devices on the local network. | **High** | Monitoring |
| **BUG-007** | TC-DEV-005 | Device & Integration | Device authentication occasionally rejects valid terminal passwords. | **High** | Monitoring |
| **BUG-008** | TC-DEV-006 | Device & Integration | Device password configuration does not automatically populate the default password based on device type. | **Low** | Closed |

Full defect details are documented in **NextGenDesktop-BugReport.md**.

---

# 5. Regression & Version Tracking Insights

Because this testing cycle spanned multiple version releases (v1.7.1–v1.7.4), 
several defects required tracking across versions rather than single-cycle 
verification:

- **BUG-002** was marked resolved in the version it was originally reported, 
  but similar cases resurfaced in user reports for v1.7.4, requiring continued 
  monitoring rather than full closure.
- **BUG-001**, **BUG-006**, and **BUG-007** show partial improvement across 
  versions but have not been fully eliminated, indicating intermittent or 
  environment-dependent root causes rather than a single deterministic bug.
- This pattern reinforced the value of maintaining a persistent, version-aware 
  bug log rather than treating each release as an isolated testing cycle.

---

# 6. Conclusion & Recommendation

Testing across versions v1.7.1–v1.7.4 identified 8 defects, including 1 
Critical-severity application crash (since resolved and verified) and 5 
High-severity issues, of which several remain under active monitoring due to 
intermittent recurrence across releases.

While the majority of defects have reached Closed or Monitoring status, it is 
recommended that the 1 remaining Open defect (Employee ID input validation) be 
prioritized for resolution, and that intermittent High-severity issues 
(device authentication, auto-scan detection) continue to be tracked across 
future version releases to confirm full resolution rather than temporary 
improvement.

---

# 7. Related Documents

- NextGenDesktop-TestPlan.md
- NextGenDesktop-TestStrategy.md
- NextGenDesktop-StudyCaseTest.md
- NextGenDesktop-BugReport.md
- NextGenDesktop-TestSummaryReport.md

--


## Notes

This document has been created for portfolio purposes based on professional QA 
practices. Company-specific implementation details, internal system names, and 
proprietary business logic have been generalized to comply with confidentiality 
obligations while preserving the overall testing workflow and methodology.
