# QA Manual Testing Portfolio — Cloud-Based SaaS & Desktop Application Testing

> **Role:** QA Manual Tester
> **Testing Types:** Functional, Regression, Integration, Security (Basic), Usability, Environment & Non-Functional
> **Tools Used:** Internal Ticketing System, Postman, SQL/MySQL, Google Workspace

---

## About This Repository

This repository documents my manual QA testing work across two distinct systems:

1. **Cloud-Based SaaS Platform (Web)** — A web admin dashboard for HR and attendance management, including subscription/billing flows, employee data management, and third-party payment gateway integrations.
2. **Desktop Application with IoT Hardware Integration** — A legacy desktop application bridging physical biometric attendance devices with cloud-based HR infrastructure, covering data synchronization, device management, and OS environment testing.

> *Company and product names have been generalized to respect confidentiality obligations to my previous employer.*

---

## Repository Contents

### Case Study #1 — Web SaaS Platform

| File | Description |
|---|---|
| [Web-TestPlan.md](./Web-TestPlan.md) | Test plan — objectives, scope, environment, risks, and testing approach |
| [Web-TestStrategy.md](./Web-TestStrategy.md) | Test strategy — methodology, testing types, entry/exit criteria, and tools |
| [Web-TestCaseStudy.md](./Web-TestCaseStudy.md) | Test case study — detailed test scenarios and test cases per module |
| [Web-TestExecutionReport.md](./Web-TestExecutionReport.md) | Test execution report — execution results per test case with pass/fail status |
| [Web-TestSummaryReport.md](./Web-TestSummaryReport.md) | Test summary report — overall quality assessment and release recommendation |
| [Web-BugReport.md](./Web-BugReport.md) | Bug report — representative defects identified, documented, and tracked |

### Case Study #2 — Desktop Application & IoT Hardware Integration

| File | Description |
|---|---|
| [LegacyAppDesktop-TestPlan.md](./LegacyAppDesktop-TestPlan.md) | Test plan — scope, environment, entry/exit criteria, risks |
| [LegacyAppDesktop-TestStrategy.md](./LegacyAppDesktop-TestStrategy.md) | Test strategy — methodology, root cause isolation techniques, severity criteria |
| [LegacyAppDesktop-StudyCaseTest.md](./LegacyAppDesktop-StudyCaseTest.md) | Case study — key findings and testing contribution summary |
| [LegacyAppDesktop-TestExecutionReport.md](./LegacyAppDesktop-TestExecutionReport.md) | Test execution report — execution metrics and defect breakdown |
| [LegacyAppDesktop-TestSummaryReport.md](./LegacyAppDesktop-TestSummaryReport.md) | Test summary report — overall assessment and QA recommendation |
| [LegacyAppDesktop-BugReport.md](./LegacyAppDesktop-BugReport.md) | Bug report — representative defects with severity/priority |

---

## Case Study #1 — Web SaaS Platform

**System:** Cloud-based HR & attendance management web application

**Testing Highlights:**
- 13 modules tested — Authentication, Session Management, Employee Management, Attendance Management, Device Registration, Device Synchronization, Subscription Management, Billing, QRIS Payment, Virtual Account Payment, Dashboard, Reports, Notifications
- Critical bugs identified — including payment gateway regression and subscription activation anomalies with direct business/revenue impact
- Methodologies — Boundary Value Analysis (BVA), Negative Testing, Regression Testing, API Integration Testing, Basic Security Testing (brute force, invalid credential validation)
- Full documentation cycle — Test Plan → Test Strategy → Test Cases → Execution Report → Summary Report → Bug Report
- Tools — Internal Ticketing System, Postman, SQL

---

## Case Study #2 — Desktop Application & IoT Hardware Integration

**System:** Legacy desktop attendance application with biometric device synchronization

**Testing Highlights:**
- 6 test categories covered — Cloud Integration, Shift & Leave Management, Employee Management, Device Management, Device Sync/IoT Integration, Environment & Infrastructure Validation
- 17 test cases executed — 11 Pass, 6 Fail
- QA conducted at branch/manual level, complementing a separate centralized automated QA function
- Critical bugs identified — including input validation gap causing data corruption and silent data overwrite during IoT sync conflict

---

## Skills Demonstrated

- Designing and executing structured test cases and test scenarios
- Writing comprehensive test plans, test strategies, and test summary reports
- Identifying and documenting defects with clear severity/priority classification
- Communicating findings with business impact context, not just technical details
- API testing and database-level validation alongside UI testing
- Basic security testing (negative testing, invalid input validation)
- Regression testing across multiple release cycles
- Environment & non-functional testing across OS configurations and network setups
- Root cause isolation using network and environment diagnostic techniques
- Cross-team escalation with structured findings and diagnostic logs
- Collaborating within a distributed QA structure (branch-level manual QA alongside centralized automated QA)

---

## Contact

Feel free to reach out if you'd like to discuss the technical depth of this work or review full documentation in an interview setting.

**Dimas Arsyad Hidayat**  
Dimasarsyad04@gmail.com  
www.linkedin.com/in/dimas-hidayat-911683120
