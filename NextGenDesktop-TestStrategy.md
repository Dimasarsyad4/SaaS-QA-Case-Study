# Test Strategy

## Next-Gen Desktop Attendance & IoT Management Application

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Next-Gen Desktop Attendance & IoT Management Application |
| Document | Test Strategy |
| Application Version | v1.1 – v1.7.4 |
| Document Version | 1.0 |
| Author | Dimas Hidayat |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Introduction

This document outlines the manual Quality Assurance (QA) strategy for testing the **Next-Gen Desktop Attendance & IoT Management Application**. The application is a desktop-based workforce management platform that integrates biometric attendance devices with cloud synchronization services.

The strategy defines the testing levels, methodologies, defect management process, and troubleshooting approaches used to ensure software stability, accurate attendance processing, reliable hardware communication, and consistent business workflows throughout multiple application releases.

---

# 2. Testing Levels & Types

To ensure comprehensive test coverage across desktop software, hardware integration, and business workflows, the following testing levels were applied.

## 2.1 Functional Testing

**Focus**

Validate application functionality against approved business requirements.

**Key Operations**

- Employee Registration & Management
- Shift & Schedule Configuration
- Leave Management
- Attendance Processing
- Device Configuration
- User Input Validation

---

## 2.2 Integration Testing (Desktop ↔ Device ↔ Database)

**Focus**

Verify stable communication between the desktop application, biometric attendance devices, local databases, and cloud synchronization services.

**Key Operations**

- Device Registration
- Device Authentication
- Device Discovery
- Attendance Synchronization
- Network Communication
- Database Synchronization

---

## 2.3 Regression Testing

**Focus**

Ensure application updates (v1.1 – v1.7.4) do not introduce regressions to existing functionality.

**Key Operations**

- Employee Management
- Attendance Calculation
- Shift Configuration
- Device Synchronization
- Network Communication

---

## 2.4 Environment Validation

**Focus**

Verify application stability under different operating systems, network configurations, and deployment scenarios.

**Key Operations**

- Fresh Installation Testing
- Application Startup Validation
- Offline Operation
- Network Switching
- Multi-Device Compatibility

---

# 3. Specialized QA Techniques & Root Cause Isolation

Because the application depends on desktop infrastructure, physical biometric devices, and local network communication, specialized troubleshooting techniques were applied to distinguish application defects from environmental issues.

## Network Isolation Testing

Testing was performed using both Local Area Network (LAN) and Mobile Hotspot configurations to determine whether synchronization failures originated from the application or external network infrastructure.

---

## Privilege-Based Execution Testing

The application was executed under both standard user privileges and **Run as Administrator** mode to identify permission-related issues affecting installation, database access, and device communication.

---

## Device Compatibility Validation

Testing was performed across multiple biometric device models to verify consistent communication behavior and hardware compatibility.

---

## Installation & Startup Validation

Fresh installation scenarios were repeatedly executed to validate installation success, startup stability, and first-launch behavior after deployment.

---

## Intermittent Issue Monitoring

Intermittent defects that could not be reproduced consistently were monitored across multiple application versions and deployment environments before final verification and closure.

---

# 4. Test Design Techniques

The following manual testing techniques were applied throughout testing activities.

## Boundary Value Analysis (BVA)

Applied to validate field boundaries such as Employee ID length, numeric validation, and configuration value limits.

---

## Negative Testing

Performed by entering invalid inputs, incorrect credentials, unsupported configurations, and unexpected user actions to verify application validation and error handling.

---

## Positive Testing

Executed using valid data and expected business workflows to ensure application functionality behaved as intended.

---

## Regression Testing

Performed after bug fixes and software updates to verify previously working functionality remained unaffected.

---

## Exploratory Testing

Conducted during defect verification and post-fix validation to identify unexpected side effects outside predefined test scenarios.

---

# 5. Defect Management & Severity Criteria

All identified defects were recorded using the Internal Ticketing System and classified according to business impact.

| Severity | Criteria | Example |
| :--- | :--- | :--- |
| **Critical** | Application crash, data corruption, or complete business process failure with no available workaround. | Application crashes while editing or deleting an active shift configuration. |
| **High** | Major functionality failure significantly affecting daily operations. | Device synchronization failure, application freeze during startup, authentication failure. |
| **Medium** | Functional issues with available workarounds or limited business impact. | Employee ID accepts invalid characters or missing validation rules. |
| **Low** | Cosmetic defects or usability improvements with minimal business impact. | Default configuration values are not automatically populated or minor UI inconsistencies. |

---

# 6. Test Data Management

To maintain testing consistency and data integrity throughout the testing lifecycle, the following practices were applied.

- Dedicated QA employee accounts were used during functional testing.
- Sample attendance records were prepared for shift and leave validation.
- Local database records were verified after synchronization testing.
- Device attendance logs were cleared after regression testing to prevent duplicate records.
- Test environments were restored whenever required to maintain consistent execution results.

---

# 7. Suspension & Resumption Criteria

## Suspension Criteria

Testing activities were temporarily suspended when:

- The application could not be installed or launched successfully.
- Critical application crashes prevented further testing.
- Required biometric devices were unavailable.
- Network communication failures prevented synchronization testing.

---

## Resumption Criteria

Testing resumed when:

- A stable application build became available.
- Blocking defects had been resolved.
- Required biometric devices were operational.
- Network connectivity had been restored.
- Test environment stability had been verified.

---

# 8. Related Documents

- NextGenDesktop-TestPlan.md
- NextGenDesktop-StudyCaseTest.md
- NextGenDesktop-BugReport.md
- NextGenDesktop-TestExecutionReport.md
- NextGenDesktop-TestSummaryReport.md

---

## Notes

This document has been prepared for portfolio purposes based on professional manual QA practices performed in an enterprise desktop application environment.

All company names, product names, proprietary workflows, hardware models, customer information, and implementation details have been generalized to comply with Non-Disclosure Agreement (NDA) obligations while preserving the actual testing methodology, troubleshooting approach, and quality assurance processes.
