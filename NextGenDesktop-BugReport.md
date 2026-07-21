# Bug Report

## Next-Gen Desktop Attendance & IoT Management Application

---

## Document Information

| Item | Description |
|------|--------------|
| Project | Next-Gen Desktop Attendance & IoT Management Application |
| Document | Bug Report |
| Application Version | v1.7.1 – v1.7.4 |
| Document Version | 1.0 |
| Author | Dimas Hidayat |
| Testing Type | Manual Testing |
| Methodology | Agile / Scrum |

---

# 1. Purpose

The following report summarizes representative defects identified, documented, and tracked during manual QA testing of a next-generation desktop attendance management application integrated with biometric attendance devices and cloud synchronization services.

To comply with Non-Disclosure Agreement (NDA) obligations, company names, product names, proprietary workflows, and detailed reproduction procedures have been generalized. Only information suitable for public portfolio purposes is included.

---

# 2. Representative Bug Log

| Bug ID | Title | Module | Severity | Priority | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **BUG-001** | Application occasionally freezes during the first launch after a fresh installation. | Employee Management | High | High | Partially Resolved |
| **BUG-002** | Socket connection occasionally disconnects during manual device registration. | IoT | High | High | Resolved (Monitoring) |
| **BUG-003** | Employee ID field accepts alphabetic and special characters. | Employee Management | Medium | Medium | Open |
| **BUG-004** | Application crashes when editing or deleting an active shift configuration. | Schedule / Shift | Critical | High | Closed |
| **BUG-005** | Incorrect cross-day working hour calculation when the clock-out record is missing. | Schedule / Shift | High | High | Closed |
| **BUG-006** | Auto Scan fails to detect all biometric devices on the local network. | Device & Integration | High | High | Monitoring |
| **BUG-007** | Device authentication occasionally rejects valid terminal passwords. | Device & Integration | High | High | Monitoring |
| **BUG-008** | Device password configuration does not automatically populate the default password based on the selected device type. | Device & Integration | Low | Medium | Closed |

---

# 3. Documentation Format Used in Full Documentation

Each bug entry in the complete testing documentation includes the following information:

- **Steps to Reproduce** — Clear, numbered steps describing how to reproduce the issue consistently.
- **Expected Result** — The intended system behavior based on functional requirements.
- **Actual Result** — The behavior observed during testing.
- **Test Environment** — Operating system, application version, hardware model, and network configuration used during testing.
- **Severity & Priority Classification** — Defects categorized according to business impact and implementation urgency.
- **Resolution / Mitigation Notes** — Summary of implemented fixes, workarounds, or root cause observations.
- **Retest Result** — Verification outcome after fixes were delivered by the development team.

> **Detailed reproduction steps, screenshots, log files, and technical implementation details are intentionally excluded from this public repository to comply with Non-Disclosure Agreement (NDA) obligations. Complete documentation is available for discussion during technical interviews upon request.**

---

# 4. Why I Document Bugs This Way

I consider bug documentation to be more than simply recording defects—it is an essential communication tool that supports collaboration between QA Engineers, Developers, Technical Support, and Project Stakeholders.

A well-written bug report should allow developers to reproduce issues efficiently, help stakeholders understand business impact, and provide sufficient context for future regression testing.

When documenting defects, I consistently prioritize:

- **Clarity over quantity** — Writing concise yet complete defect descriptions that are easy to understand and reproduce.
- **Reproducibility** — Providing structured reproduction steps and clear comparisons between expected and actual results.
- **Business impact assessment** — Prioritizing defects based on operational impact, data integrity, and user experience rather than technical complexity alone.
- **Consistent severity and priority classification** — Applying standardized criteria to support predictable defect triage and release planning.
- **Root cause awareness** — Recording observations that assist developers during investigation while supporting future regression testing.
- **Verification after fixes** — Performing retesting and regression validation to confirm that implemented fixes resolve reported issues without introducing new defects.

This documentation approach helps improve communication efficiency, supports faster issue resolution, and contributes to maintaining software quality throughout the application lifecycle.

---

# Related Documents

- NextGenDesktop-TestStrategy.md
- NextGenDesktop-TestPlan.md
- NextGenDesktop-TestExecutionReport.md
- NextGenDesktop-TestSummaryReport.md

> **Detailed Test Case and Bug Log spreadsheets are intentionally excluded from this public repository due to Non-Disclosure Agreement (NDA) obligations. These documents are available for discussion during technical interviews upon request.**

---

## Notes

This document has been prepared for portfolio purposes based on professional manual Quality Assurance practices performed in an enterprise desktop application environment.

Company names, application names, customer information, hardware models, proprietary workflows, and implementation details have been generalized to comply with Non-Disclosure Agreement (NDA) obligations while preserving the overall testing methodology, defect management process, and quality assurance practices.
