# Test Plan

## Cloud-Based HR & Attendance SaaS Platform

---

## Document Information

| Item | Description |
|------|-------------|
| Project | Cloud-Based HR & Attendance SaaS Platform |
| Document | Master Test Plan |
| Author | Dimas Hidayat |
| Version | 2.0 |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Purpose

This document defines the overall testing plan for validating a cloud-based HR & Attendance SaaS platform before production deployment.

The testing process aims to verify application functionality, business workflows, cloud-to-device integration, subscription management, and payment processing while minimizing production risks.

---

# 2. Test Objectives

The objectives of this testing cycle are:

- Validate newly developed features.
- Verify critical business workflows.
- Ensure cloud and biometric device synchronization.
- Detect regression after software updates.
- Verify payment processing integrity.
- Validate API communication.
- Verify database consistency.
- Ensure release readiness.

---

# 3. Scope

## In Scope

The following modules are included.

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

## Out of Scope

The following testing activities are excluded from this testing cycle.

- Performance Testing
- Load Testing
- Stress Testing
- Security Penetration Testing
- Automation Testing
- Accessibility Testing

---

# 4. Test Environment

| Component | Environment |
|------------|-------------|
| Browser | Google Chrome |
| Operating System | Windows 11 |
| API Validation | Postman |
| Database Validation | MySQL |
| Issue Tracking | Internal Ticketing System |
| Deployment | QA Environment |
| Hardware | Biometric Attendance Device |

---

# 5. Testing Approach

Testing will be performed using:

- Functional Testing
- Regression Testing
- Integration Testing
- Boundary Value Analysis
- Negative Testing
- Basic Security Validation
- API Validation
- Database Validation

Detailed testing techniques are documented in **Web-TestStrategy.md**.

---

# 6. Entry Criteria

As this project involved ongoing QA support for an already-live application, 
testing was initiated when:

- A user-reported issue or ticket is received and requires investigation.
- A new application version/update is scheduled for deployment, requiring 
  regression testing.
- QA environment/staging access is available to reproduce the reported issue.
- Test accounts and relevant test data are available for reproduction.
- Test devices (biometric hardware) are connected, for issues involving 
  device synchronization.

---

# 7. Exit Criteria

Testing is considered complete for a given cycle when:

- All reported issues under investigation have been reproduced, root-caused, 
  and documented.
- Critical defects are resolved.
- High severity defects are resolved or have a documented, accepted workaround.
- Regression testing for the affected release passes.
- Product Owner / stakeholder approves the release.

---

# 8. Risks

| Risk | Mitigation |
|------|------------|
| Payment gateway failure | Validate using sandbox environment |
| Cloud-device synchronization issues | Repeated synchronization testing |
| API communication failure | Verify API responses with Postman |
| Duplicate employee records | Validate database using SQL |
| Network instability | Perform testing under different network conditions |

---

# 9. Deliverables

The testing process will produce:

- Test Strategy
- Test Cases
- Test Execution Report
- Bug Report
- Test Summary Report

---

# 10. Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| QA Engineer | Plan and execute testing |
| Developer | Resolve defects |
| Product Owner | Clarify requirements |
| Technical Support | Validate production issues |

---

# 11. Related Documents

- Web-TestStrategy.md
- Web-TestCaseStudy.md
- Web-BugReport.md
- Web-TestExecutionReport.md
- Web-TestSummaryReport.md

---

## Notes

This document has been created for portfolio purposes based on professional QA practices.

Company-specific implementation details have been generalized to comply with confidentiality obligations while preserving testing methodology and overall QA workflow.
