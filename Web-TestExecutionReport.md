# Test Execution Report

## Cloud-Based HR & Attendance SaaS Platform (Web Admin Dashboard)

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Cloud-Based HR & Attendance SaaS Platform (Web Admin Dashboard) |
| Document | Web Test Execution Report |
| Application Version | 2.0 |
| Author | Dimas Hidayat |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Executive Summary

This document presents the execution results of the manual QA cycle for the 
Cloud-Based HR & Attendance SaaS Platform (Web Admin Dashboard). The objective 
of this cycle was to validate business-critical workflows across authentication, 
employee management, subscription/billing, payment processing, and cloud-to-device 
synchronization prior to production deployment.

A total of **~45 test cases** were executed across 13 functional modules. 
The testing uncovered several business-critical defects (payment gateway 
regression, subscription quota leak, and cloud-to-device data synchronization 
conflicts), of which the majority were resolved and verified through retesting 
prior to this report.

---

# 2. Test Execution Metrics

Unlike a fixed, pre-planned test cycle, this project involved ongoing QA support 
for an already-live application. Testing activities were driven by two primary 
triggers:

1. **User-Reported Issue Investigation** — Testing initiated in response to 
   issues reported by end users or internal stakeholders through the ticketing system.
2. **Version-Based Regression Testing** — Regression testing conducted whenever 
   a new application version/update was deployed, to ensure existing 
   functionality remained stable.

### 2.1 Execution Summary

| Metric | Statistics |
|---|---|
| Engagement Duration | ~1 year 8 months |
| User-Reported Issues Investigated | ~150+ |
| Confirmed Defects (Representative) | 5 |
| Regression Cycles (tied to version releases) | ~35-40 |
| Regression Frequency | 1-3x per month, varying by release cadence |

---

# 3. Test Execution Scope

The following modules were included during this testing cycle:

- Authentication
- Session Management
- Employee Management
- Attendance Management
- Device Registration
- Device Synchronization
- Subscription Management
- Billing
- QRIS Payment
- Virtual Account Payment
- Dashboard
- Reports
- Notifications

---

# 4. Test Environment

| Component | Environment |
|------------|--------------|
| Browser | Google Chrome |
| Operating System | Windows 11 |
| API Validation | Postman |
| Database Validation | MySQL |
| Issue Tracking | Internal Ticketing System |
| Deployment | QA Environment |
| Hardware | Biometric Attendance Device |

---

# 5. Testing Activities

The following activities were completed during this testing cycle:

- Investigated and reproduced issues reported by users/stakeholders via the ticketing system.
- Executed regression testing scoped to affected areas whenever a new version was deployed.
- Performed functional testing on newly implemented features.
- Conducted regression testing before production deployment.
- Verified integrations between cloud services and biometric attendance devices.
- Validated API responses using Postman.
- Verified database consistency using SQL queries.
- Performed Boundary Value Analysis (BVA) and negative testing on critical business workflows.
- Conducted basic security validation, including authentication, session management, and authorization checks.
- Documented identified defects through the Internal Ticketing System.
- Collaborated with developers during defect investigation and verification.
- Performed retesting after defect resolution.
- Executed final regression testing prior to release.

---

# 6. Detailed Defect Summary

The following representative defects were identified and logged into the 
internal ticketing system during this execution cycle:

| Defect ID | Module | Bug Description | Severity | Status |
|---|---|---|---|---|
| **BUG-001** | Subscription | Automatic deduction leak on GPS App quota when accessing Subscription Plan Info page. | **High** | Resolved |
| **BUG-002** | Payment | Severe payment gateway breakdown — multiple VA banks and e-wallets missing post-update. | **High** | Resolved |
| **BUG-003** | Payment | QRIS payment timeout window too short (2–3 minutes), causing high transaction failure rates. | **Medium** | Resolved |
| **BUG-004** | HR Admin | Employee Reference Code field mistakenly locked (Read-Only) for existing users. | **Medium** | Resolved |
| **BUG-005** | IoT Sync/Reports | Data collision on local machine storage leads to overlapping attendance reports. | **High** | Open |

Full defect details are documented in **Web-Bug-Report.md**.

---

# 7. Retesting Activities

After developers implemented fixes, retesting was conducted to verify:

- Defects were resolved successfully.
- Business logic functioned as expected.
- No unintended side effects were introduced.
- Existing functionality remained stable after implementation.

4 of 5 representative defects included in this portfolio were successfully 
verified after resolution. One High-severity defect (cloud-to-device data 
synchronization) remains open at the time of this report.

---

# 8. Regression Testing Result

Regression testing focused on validating high-risk business modules following 
defect resolution and feature deployment.

The primary regression scope included:

- Authentication
- Employee Management
- Attendance Synchronization
- Subscription Management
- Billing
- Payment Processing

Regression testing confirmed that previously working functionality remained 
stable throughout the testing cycle.

---

# 9. Execution Outcome

Testing activities validated the application's critical business workflows 
prior to production deployment. Out of 5 representative defects identified, 
4 were resolved and verified through retesting, while 1 High-severity defect 
(cloud-to-device data synchronization) remains open pending further investigation.

Defects identified during testing were documented, communicated to the 
development team, verified after resolution where applicable, and confirmed 
through regression testing. The overall execution demonstrated the effectiveness 
of structured manual testing in improving software quality and reducing 
production risk.

---

# 10. Related Documents

- Web-Test-Plan.md
- Web-Test-Strategy.md
- Web-QA-Test-Study.md
- Web-Bug-Report.md
- Web-Test-Summary-Report.md

---

## Notes

This document has been created for portfolio purposes based on professional QA 
practices. Company-specific implementation details, execution metrics, and 
internal testing records have been generalized to comply with confidentiality 
obligations while preserving the overall testing workflow and methodology.
