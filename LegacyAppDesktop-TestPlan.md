# Test Plan

## Desktop Attendance Management System & IoT Hardware Integration

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Desktop Attendance Management System & IoT Hardware Integration |
| Document | Legacy App Test Plan |
| Application Version | v7.4 |
| Document Version | 1.0 |
| Author | Dimas Hidayat |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Purpose

This document defines the scope, approach, environment, and criteria for manual 
testing of the Desktop Attendance Management System — a desktop-based attendance management application integrating local physical biometric hardware with cloud database infrastructure.

The primary objective is to ensure new deployments do not disrupt critical business 
paths, including attendance report generation, local network handshakes, and 
database synchronization stability.

---

# 2. Scope

## In Scope

| Module Code | Module |
|---|---|
| REG | Employee Registration & Data Management |
| SCH | Shift & Schedule Management |
| LEV | Leave Management |
| DEV | Biometric Hardware / Device Synchronization |
| NET | Network Communication & Cloud Gateway Integration |

## Out of Scope

- Performance Testing
- Load Testing
- Stress Testing
- Full Security Penetration Testing
- Automation Testing (manual testing only for this project scope; automation 
  not implemented due to project timeline/resource constraints)

---

# 3. Test Environment

| Component | Environment |
|------------|--------------|
| Operating System | Windows 7 SP1 – Windows 11 |
| Hardware | Legacy Biometric Attendance Terminal |
| Network Simulation | Mobile Hotspot (for network isolation testing) |
| Database Validation | Local SQL-based database |
| Issue Tracking | Internal Ticketing System |
| Deployment | QA / Staging Environment |

---

# 4. Testing Approach

Testing was conducted manually, combining positive, negative, and boundary 
value testing across all in-scope modules. Key techniques applied:

- Functional Testing on core UI workflows (employee data entry, scheduling, 
  leave requests)
- Regression Testing before major version deployments to ensure legacy 
  hardware-fetching processes remained stable
- Boundary Value Analysis (BVA) on data entry fields (e.g., national ID length limits)
- Negative Testing on input validation (numeric fields, duplicate ID handling)
- Integration Testing between desktop application, local biometric hardware, 
  and cloud database
- Root cause isolation using network environment isolation (e.g., mobile 
  hotspot testing) and OS-level privilege elevation to distinguish 
  application-layer issues from network/infrastructure-layer issues

---

# 5. Entry Criteria

- Test environment (desktop application + biometric hardware simulation) is 
  available and stable
- Application build for the target version has been deployed to the QA environment
- Test cases have been designed and reviewed for in-scope modules

---

# 6. Exit Criteria

- All planned test cases for REG, SCH, LEV, DEV, and NET modules have 
  been executed
- No open Critical severity defects remain unresolved
- All High severity defects have been resolved or have a documented, 
  approved workaround
- Regression testing confirms no degradation to previously stable functionality

---

# 7. Risks & Mitigation

| Risk | Mitigation |
|------|------------|
| Limited access to physical biometric hardware for repeated testing | Simulated device responses/socket behavior where physical hardware was unavailable |
| Network-layer issues masking application-layer defects | Used network isolation techniques (mobile hotspot, alternate routing) to isolate root cause |
| Silent failures in cloud-to-device synchronization going undetected | Manually cross-verified database records against expected sync results after each test cycle |
| Restrictive client network/firewall environments affecting reproducibility | Used OS privilege elevation (Run as Administrator) and alternate network paths to isolate environment-specific issues |

---

# 8. Roles & Responsibilities

| Role | Responsibility |
|------|-----------------|
| QA Engineer / Tester | Test design, execution, defect documentation, retesting, root cause isolation |
| Developer | Defect investigation, fix implementation |
| Technical Support | Field-level issue triage, escalation of client-reported issues |

---

# 9. Related Documents

- LegacyAppDesktop-TestStrategy.md
- LegacyAppDesktop-StudyCaseTest.md
- LegacyAppDesktop-BugReport.md
- LegacyAppDesktop-TestExecutionReport.md
- LegacyAppDesktop-TestSummaryReport.md

---

## Notes

This document has been created for portfolio purposes based on professional QA 
practices. Company-specific implementation details, internal system names, and 
proprietary business logic have been generalized to comply with confidentiality 
obligations while preserving the overall testing workflow and methodology.
