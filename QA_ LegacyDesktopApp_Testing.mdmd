# QA Manual Tester Portfolio: Portfolio Case Study

**Platform Type:** Desktop Attendance Management System & IoT Hardware Integration  
**Role:** QA Manual Tester & Technical Support  
**Testing Types:** Functional Testing, Regression Testing, Integration Testing, Boundary Value Analysis (BVA), Negative Testing, Usability Testing

---

## 1. Project Overview & Situation

This project involved testing **Fingerspot Personnel**, a desktop-based attendance and payroll management application that handles enterprise business logic ranging from employee shift scheduling to data synchronization between local physical biometric hardware and cloud database infrastructures.

The product was an actively-used desktop system undergoing key version updates. My primary challenge was ensuring new deployments did not disrupt critical paths—such as attendance report generation, local network handshakes, and database synchronization stability—particularly given the initial absence of a pre-existing structured QA documentation framework.

> 📊 **Artifact Link:** [Download Full Test Cases & Bug Report Spreadsheet (Excel)](Fingerspot_Personnel_TestDocs.xlsx)

---

## 2. My Tasks & Responsibilities

* **Feature Enhancement Validation:** Designed and executed functional test scenarios for desktop UI interactions, rapid input keyboard navigation shortcuts, and complex corporate shift/leave management calculation engines.
* **Regression Testing Management:** Conducted end-to-end regression testing before major software updates to ensure legacy biometric data-fetching processes and existing system modules remained completely stable.
* **Cloud Sync Audit:** Monitored API data streaming behaviors, validated database schema routing parameters, and inspected error-handling telemetry on cloud configuration panels to ensure seamless background data flow.
* **Hardware-to-Desktop Integration Analysis:** Identified network communication, local port data packet drops, and user identity overwrite synchronization conflicts between physical biometric attendance terminals and the desktop application.

---

## 3. Core Testing Scenarios & Methodologies

I structured manual testing execution across key modules, combining positive, negative, and boundary value testing approaches:

### A. Employee Management Module
* **Shortcut Entry Testing:** Verified rapid employee profile generation using down-arrow keyboard navigation shortcuts to ensure efficient continuous row creation.
* **Data Sanitization Checks:** Conducted negative testing on critical numeric input boxes, discovering a flaw where alphabetic characters could bypass standard UI fields and break downstream reporting queries.
* **Boundary Value Analysis:** Validated character length limitations on national identification forms to prevent data truncation or background database buffer errors.

### B. Hardware Synchronization (IoT) & Networking Module
* **Conflict Resolution Auditing:** Tested user database matching constraints during bulk profile uploads to local devices, uncovering missing collision validations that could lead to overlapping user identities on biometric terminals.
* **Error Handling & UI Thread Resiliency:** Simulated network communication timeout failures, identifying a critical interface bug where un-cancelable duplicate alert notification loops blocked the main application thread.
* **Network Environment Isolation:** Engineered structural diagnostic steps using alternative data routing (Mobile Hotspots) and operating system permission elevation patches (Run as Administrator) to systematically isolate software defects from restrictive client network firewalls.

### C. Cloud Gateway Integration Module
* **Data Feed Telemetry Checks:** Evaluated the visibility of the system status within cloud synchronization controls, isolating critical design flaws where database schema mismatches resulted in completely silent integration failures.
* **API Payload Resilience Testing:** Monitored high-volume data packet streaming across remote endpoints to observe data-fetching latency and maintain information integrity.

---

## 4. Defect Discovery — Summary of Findings

During testing cycles, I identified and documented several high-severity defects prior to production release, contributing to platform stability and data integrity protection:

| Bug Category | Severity | Outcome |
| :--- | :--- | :--- |
| Weak input validation on NIK field allowing alphabetic bypass via keyboard navigation | Critical | Documented error flow; designed validation workaround to block local reporting database corruption |
| Missing user ID collision validation during profile uploads to biometric hardware terminals | Critical | Mitigated through field deployment safeguards to prevent irreversible biometric identity scrambling |
| Hardcoded un-cancelable duplicate alert loop triggering connection timeout failures | High | Isolated frontend UI thread lock; recommended event handling refactor to optimize notification loops |
| Silent integration failure allowing incorrect database schemas to be saved without alerts | High | Escalated backend validation gap to core engineering team for immediate schema check implementations |
| Cloud integration gateway connection lag causing random data-fetching synchronization delays | High | Identified, packaged network logs, and escalated directly to Central HQ QA for remote server updates |
| Absent connection telemetry utility or "Test Connection" toggle on cloud control panels | Medium | Recommended integration of an explicit connectivity test module to maximize visibility of system status |

*(Full technical reproduction steps and internal system details are withheld in accordance with confidentiality obligations to the employer. Detailed walkthroughs available upon request during interviews.)*

---

## 5. Key Results & Personal Takeaways

* **Data Integrity & Operational Protection:** Identifying input validation bypasses and silent database schema mismatches before release helped prevent data corruption and potential loss of historical employee attendance reports.
* **Risk Mitigation & Technical Isolation:** Systematic root-cause analysis on hardware-desktop sync issues—using network isolation (Mobile Hotspots) and Windows privilege elevation patches (Run as Administrator)—enabled the team to map environment risks accurately and protect existing client data.
* **Process Contribution:** Since the project initially lacked a structured QA framework, the test cases, environment isolation procedures, and documentation practices I introduced helped establish a more repeatable regression testing approach for the deployment and technical support teams.

---

## Testing Approach Highlights

* **Strong focus on negative testing and boundary value analysis** to uncover edge cases beyond standard happy-path testing.
* **Practical root cause isolation techniques**—including network environment isolation (e.g., testing via isolated network connections) to distinguish application-layer issues from infrastructure/network-layer issues.
* **Experience escalating cross-team technical issues** with clear, structured findings to development teams.
* **Comfortable working with both web/cloud systems and physical IoT hardware integration**—a less common but valuable QA skill set.

---

*Note: Company and product names have been generalized, and specific technical reproduction details have been withheld to respect confidentiality obligations to my previous employer. I'm happy to discuss the technical depth of this work directly in an interview setting.*
