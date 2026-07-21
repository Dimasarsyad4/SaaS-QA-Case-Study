# Test Plan

## Next-Gen Desktop Attendance & IoT Management Application

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Next-Gen Desktop Attendance & IoT Management Application |
| Document | Test Plan |
| Application Version | v1.7.1 – v1.7.4 |
| Document Version | 1.0 |
| Author | Dimas Hidayat |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Purpose

This document defines the scope, approach, environment, and criteria for manual testing of the Next-Gen Desktop Attendance & IoT Management Application — the successor platform to a legacy desktop attendance system, integrating local 
physical biometric hardware with cloud database infrastructure.

The primary objective is to ensure new version releases do not disrupt critical business paths, including employee data integrity, shift/leave calculation accuracy, and biometric device synchronization stability.

---

# 2. Scope

## In Scope

| Module Code | Module |
|---|---|
| REG | Employee Registration & Data Management |
| SCH | Shift & Schedule Management |
| LEV | Leave Management |
| DEV | Device & Hardware Integration |
| NET | IoT / Network Communication |
| ENV | Environment & Non-Functional Validation |

## Out of Scope

- Performance Testing
- Load Testing
- Stress Testing
- Full Security Penetration Testing
- Automation Testing (manual testing only for this project scope; automation not implemented due to project timeline/resource constraints)

---

# 3. Test Environment

| Component | Environment |
|------------|--------------|
| Operating System | Windows 10 – Windows 11 |
| Hardware | Biometric Attendance Terminal (various models/generations) |
| Network Simulation | Mobile Hotspot (for network isolation testing) |
| Database Validation | Local SQL-based database |
| Issue Tracking | Internal Ticketing System |
| Deployment | QA / Staging Environment |

---

# 4. Testing Approach

Testing was conducted manually, combining positive, negative, and boundary 
value testing across all in-scope modules. Key techniques applied:

- Functional Testing on core UI workflows (employee data entry, scheduling, leave configuration)
- Regression Testing across version releases (v1.7.1 through v1.7.4) to ensure previously stable features remained unaffected by new updates
- Boundary Value Analysis (BVA) on data entry fields (e.g., character length thresholds on Name/ID fields)
- Negative Testing on input validation (alphabetic input into numeric fields, special character injection)
- Integration Testing between desktop application, local biometric hardware, and cloud database
- Non-functional/environment testing, including application startup behavior, offline resiliency, and network topology isolation (Mobile Hotspot vs. standard LAN)

---

# 5. Entry Criteria

- Application build for the target version has been deployed to the QA environment
- Test cases have been designed and reviewed for in-scope modules
- Test devices (biometric hardware) are connected and accessible

---

# 6. Exit Criteria

- All planned test cases for REG, SCH, LEV, DEV, NET, and ENV modules have been executed
- No open Critical severity defects remain unresolved
- All High severity defects have been resolved or have a documented, approved workaround
- Regression testing confirms no degradation to previously stable functionality

---

# 7. Risks & Mitigation

| Risk | Mitigation |
|------|------------|
| Limited access to physical biometric hardware for repeated testing | Simulated device responses where physical hardware was unavailable |
| Network-layer issues masking application-layer defects | Used network isolation techniques (Mobile Hotspot, alternate routing) to isolate root cause |
| Recurring defects across version releases going undetected without formal regression tracking | Maintained a persistent bug log across versions to track recurrence and monitor previously reported issues |
| Silent failures (no error alerts) affecting data integrity undetected | Manually cross-verified database records and generated reports after each test cycle |

---

# 8. Roles & Responsibilities

| Role | Responsibility |
|------|-----------------|
| QA Engineer / Tester | Test design, execution, defect documentation, retesting, root cause isolation |
| Developer | Defect investigation, fix implementation |
| Technical Support | Field-level issue triage, escalation of client-reported issues |

---

# 9. Related Documents

- NextGenDesktop-TestStrategy.md
- NextGenDesktop-StudyCaseTest.md
- NextGenDesktop-BugReport.md
- NextGenDesktop-TestExecutionReport.md
- NextGenDesktop-TestSummaryReport.md

---

## Notes

This document has been created for portfolio purposes based on professional QA practices. Company-specific implementation details, internal system names, and proprietary business logic have been generalized to comply with confidentiality 
obligations while preserving the overall testing workflow and methodology.
