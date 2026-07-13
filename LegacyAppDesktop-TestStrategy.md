# Test Strategy

## Desktop Attendance Management System & IoT Hardware Integration

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Desktop Attendance Management System & IoT Hardware Integration |
| Document | Legacy App Test Strategy |
| Application Version | v7.4 |
| Document Version | 1.0 |
| Author | Dimas Hidayat |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Introduction

This document outlines the strategic QA approach for testing the Desktop Attendance Management System (v7.4). Testing was conducted at the branch manual QA level, complementing a separate centralized automated QA function. It defines the testing levels, methodologies, data validation pipelines, and root-cause isolation techniques required to ensure the stability of the application's core features, local database synchronization, and legacy biometric IoT hardware connectivity.

---

# 2. Testing Levels & Types

To achieve comprehensive test coverage across both software interfaces and physical hardware touchpoints, the manual QA cycle relies on the following testing classifications:

### 2.1 Integration Testing (Software-to-Hardware)
*   **Focus:** Validating data transmission over network sockets (TCP/IP) between the desktop client and physical biometric terminals (various hardware models/generations).
*   **Key Operations:** Verifying device handshake stability, data packet streaming during user log downloads, and manual/automated terminal discovery.

### 2.2 Functional & Workflow Testing
*   **Focus:** Validating the application’s business logic against administrative operational specifications.
*   **Key Operations:** Employee profile creation, complex roster configurations, master shift definitions, and leave/absence balance adjustments.

### 2.3 Black-Box Regression Testing
*   **Focus:** Ensuring that new build updates or system patches in v7.4 do not degrade existing features.
*   **Key Operations:** Verifying that overnight cross-day shift matrices and data compilation pipelines remain completely uncorrupted.

---

# 3. Specialized QA Tactic & Root Cause Isolation

Given the unique dependencies of a legacy desktop application operating alongside physical local networks and cloud gateways, the following specialized manual QA methodologies are implemented to isolate application-layer bugs from environment-layer limitations:

*   **Network Topology Isolation (Mobile Hotspot):** To isolate bugs caused by complex corporate firewalls or router noise, the QA station and biometric hardware are paired under a controlled Mobile Hotspot. This alternate routing configuration validates cloud gateway synchronization performance under isolated environments.
*   **OS-Level Privilege Elevation:** To differentiate restrictive OS group policies from real software faults, test execution matrices are evaluated under both standard access parameters and elevated operational states (**"Run as Administrator"**). This pinpoints permission-based caching and database write errors.
*   **Device Socket Simulation:** When physical fleet models are strictly unavailable during parallel multi-terminal verification blocks, network socket simulation templates are deployed to mock transactional raw data strings, ensuring continuous script-less integration checks.

---

# 4. Test Design Techniques

Test inputs and operational constraints are derived using standard manual test design methodologies:

*   **Boundary Value Analysis (BVA):** Applied heavily to identity strings (National ID/Employee ID field length thresholds) and quota balance allocations.
*   **Negative Testing:** Designed to evaluate structural sanitization by injecting alphanumerics/special characters into numerical fields and forcing data sync processes while the hardware is actively severed mid-transaction.

---

# 5. Defect Management & Severity Criteria

Discovered faults are logged into the internal ticketing system and prioritized based on the following structural boundaries:

| Severity | Criteria | Example |
| :--- | :--- | :--- |
| **Critical** | Fatal application malfunctions with no viable operational workarounds; data corruption or security/sanitization leaks. | Alphanumeric injection accepted into structured IDs, or the application crashes instantly when deleting active shifts. |
| **High** | Major core feature failure impacting daily operations, but an alternate manual operational path exists. | Overnight cross-day shift matrices failing to compile when a clock-out record is missing, or device sync failing to register. |
| **Medium** | Minor feature issues, logical errors, or missing instructional boundaries that do not stop system workflow. | High-tier machine setup fields lacking inline description labels or missing text guidance for complex credential inputs. |
| **Low** | Aesthetic bugs, cosmetic UI misalignments, or minor formatting issues. | Validation error alerts displaying inaccurate text padding or overlapping boundaries on low-resolution displays. |

---

# 6. Test Data Management

To minimize data decay and maintain testing integrity across the database architecture, the following protocols are observed:
*   **Local State Backups:** Before initializing structural sync calculations or hardware pulls, a copy of the active local database file is archived.
*   **State Reset:** Physical machine transactional logs and user templates are routinely cleared via master factory commands after each complete regression execution block to prevent data contamination.

---

# 7. Suspension & Resumption Criteria

### Suspension Criteria
Testing operations for a specific module or the entire build will be suspended if:
*   The compiled installation build (`Setup.exe`) refuses to initialize or crashes immediately upon startup due to a fatal thread lock.
*   Biometric hardware fails to retrieve/transmit data across all available connection methods (Wi-Fi, LAN, and direct USB), indicating a likely hardware or component-level failure rather than a network/environment issue.

### Resumption Criteria
Testing will resume once:
*   The development team provides a stabilized, debugged installation build.
*   The affected biometric hardware has been repaired, replaced, or otherwise confirmed functional, with successful data retrieval verified across at least one connection method (Wi-Fi, LAN, or USB).

---

# 8. Related Documents

- LegacyAppDesktop-TestPlan.md
- LegacyAppDesktop-StudyCaseTest.md
- LegacyAppDesktop-BugReport.md
- LegacyAppDesktop-TestExecutionReport.md
- LegacyAppDesktop-TestSummaryReport.md

---

## Notes

This document has been created for portfolio purposes based on professional QA practices. Company-specific implementation details, internal system names, and proprietary business logic have been generalized to comply with confidentiality 
obligations while preserving the overall testing workflow and methodology.
