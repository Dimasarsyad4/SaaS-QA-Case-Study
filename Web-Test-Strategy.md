# Test Strategy

## Cloud-Based HR & Attendance SaaS Platform (Web Admin Dashboard)

---

## Document Information

| Item | Description |
|------|-------------|
| Project | Cloud-Based HR & Attendance SaaS Platform (Web Admin Dashboard) |
| Document | Web Test Strategy |
| Application Version | 2.0 |
| Author | Dimas Hidayat |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Purpose

This document describes the testing strategy used to validate the Cloud-Based HR & Attendance SaaS Platform (Web Admin Dashboard).

The strategy outlines the testing methods, design techniques, execution approach, and defect management process to ensure software quality before production deployment.

---

# 2. Testing Objectives

The testing strategy aims to:

- Validate application functionality against business requirements.
- Detect defects before production deployment.
- Minimize regression risks after feature enhancements.
- Verify data consistency between application components.
- Validate critical business workflows.
- Improve release quality and system reliability.

---

# 3. Testing Approach

The following testing approaches are applied throughout the project.

- Functional Testing
- Regression Testing
- Integration Testing
- Boundary Value Analysis (BVA)
- Negative Testing
- Basic Security Validation
- API Validation
- Database Validation
- Usability Testing

---

# 4. Testing Strategy

## 4.1 Functional Testing

Functional testing is performed to verify that every feature behaves according to the functional requirements.

The following modules are covered:

- Authentication
- Session Management
- Employee Management
- Attendance Management
- Subscription Management
- Billing
- QRIS Payment
- Virtual Account Payment
- Dashboard
- Reports
- Notifications

---

## 4.2 Regression Testing

Regression testing is conducted before every production deployment to ensure that newly implemented features do not negatively affect existing functionality.

Primary regression focus includes:

- Login
- Employee Management
- Attendance Synchronization
- Subscription
- Billing
- Payment Processing

---

## 4.3 Integration Testing

Integration testing verifies communication between interconnected system components.

The following integrations are validated:

- Web Application ↔ Database
- Web Application ↔ API Services
- Cloud Platform ↔ Biometric Attendance Device
- Payment Gateway ↔ Application

---

## 4.4 Boundary Value Analysis (BVA)

Boundary Value Analysis is used to validate system behavior at minimum, maximum, and edge input values.

Examples include:

- Employee limits
- Subscription quantity
- Numeric input validation
- Character length validation

---

## 4.5 Negative Testing

Negative testing verifies how the application handles invalid or unexpected user input.

Typical scenarios include:

- Invalid login credentials
- Empty mandatory fields
- Duplicate Employee IDs
- Invalid subscription values
- Invalid form submissions

---

## 4.6 Basic Security Validation

Basic security validation is incorporated into manual testing activities to identify common security-related issues.

Validation includes:

### Authentication

- Invalid login attempts
- Incorrect password validation
- Empty credentials

### Session Management

- Remember Me functionality
- Logout validation
- Session persistence after browser restart

### Authorization

- Unauthorized page access
- Access validation after logout
- Role permission validation

### Input Validation

- Duplicate records
- Invalid characters
- Boundary inputs
- Basic SQL Injection validation (where applicable)
- Basic Cross-Site Scripting (XSS) validation (where applicable)

---

## 4.7 API Validation

API behavior is verified using Postman.

Validation includes:

- HTTP Status Codes
- Response Body
- Error Handling
- Data Accuracy
- API Response Consistency

---

## 4.8 Database Validation

Database verification is performed using SQL queries.

Validation includes:

- Data insertion
- Data updates
- Duplicate record validation
- Data synchronization
- Referential integrity

---

## 4.9 Usability Testing

Basic usability testing is performed to ensure users can efficiently interact with the application.

Validation includes:

- Navigation flow
- Form usability
- Error message clarity
- Button behavior
- General user experience

---

# 5. Test Design Techniques

The following test design techniques are applied:

- Positive Testing
- Negative Testing
- Boundary Value Analysis (BVA)
- Equivalence Partitioning
- Error Guessing
- Risk-Based Testing

---

# 6. Test Execution Strategy

Testing activities are executed using the following workflow:

1. Review business requirements.
2. Prepare test scenarios and test cases.
3. Execute manual testing.
4. Record testing results.
5. Report identified defects through the Internal Ticketing System.
6. Collaborate with developers during defect analysis.
7. Perform retesting after fixes.
8. Conduct regression testing before production deployment.
9. Prepare Test Summary Report.

---

# 7. Defect Severity Classification

| Severity | Description |
|----------|-------------|
| Critical | System unavailable or major business process cannot continue. |
| High | Core functionality is affected with no acceptable workaround. |
| Medium | Feature functions incorrectly but has an acceptable workaround. |
| Low | Cosmetic issues or minor usability defects. |

---

# 8. Risk-Based Testing

Testing priority is determined based on business impact.

## High Priority

- Authentication
- Attendance Synchronization
- Subscription
- Billing
- Payment Processing

## Medium Priority

- Employee Management
- Reports
- Dashboard

## Low Priority

- Notifications
- User Profile
- Minor UI Enhancements

---

# 9. Test Data Strategy

Testing is performed using representative test data, including:

- Valid user accounts
- Invalid credentials
- Duplicate employee records
- Boundary value inputs
- Sample attendance records
- Sample subscription data

Production data is not used during testing.

---

# 10. Related Documents

- 01-Web-Test-Plan.md
- 03-Web-QA-Testing-Case-Study.md
- 04-Web-Bug-Report.md
- 05-Web-Test-Execution-Report.md
- 06-Web-Test-Summary-Report.md

---

## Notes

This document is created for portfolio purposes based on professional QA practices.

Company-specific implementation details have been generalized to comply with confidentiality obligations while preserving the testing methodology and overall QA workflow.
