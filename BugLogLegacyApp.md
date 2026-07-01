## Bug Log — Desktop Application & IoT Hardware Integration Testing

The following is a representative sample of defects identified, documented, and tracked during manual QA testing on a desktop-based attendance management application with biometric hardware integration. Details have been generalized to respect confidentiality obligations to my previous employer. Only findings suitable for public disclosure are listed here.

| Bug ID | Title | Module | Severity | Priority | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **BUG-P01** | Insufficient input validation allows alphabetic characters into a structured numeric NIK field via keyboard shortcuts, causing downstream report generation failures | Employee Data / Reporting | Critical | High | Reported — Root Cause Identified |
| **BUG-P02** | Absence of database schema validation on cloud configuration panel allows mismatched parameters to save silently, breaking data routing without throwing system alerts | Cloud Integration / Data | High | High | Reported — Mitigation Proposed |
| **BUG-P03** | Local network communication timeout triggers an un-cancelable sequence of 5 consecutive alert pop-ups, temporarily locking the primary application interface thread | Device Connectivity / UX | High | High | Reported — UX Flaw Identified |
| **BUG-P04** | Missing user ID collision verification during bulk profile uploads to local biometric devices triggers a silent overwrite, scrambling profile mappings on the physical terminal | IoT Integration / Sync | Critical | High | Reported — Risk Analysis Attached |
| **BUG-P05** | Cloud integration gateway encounters intermittent connection drops and data-fetching sync delays during prolonged automated continuous data streaming cycles | Cloud Integration / Sync | High | High | In Progress — Escalated to Core Eng |
| **BUG-P06** | No built-in connection test mechanism or telemetry utility available on cloud control panels — users cannot pre-validate API reachability before initiating data routing | Cloud Integration / UX | Medium | High | Reported — Feature Gap Identified |

### Description Format Used in Full Documentation
Each bug entry in my full testing documentation includes:
* **Steps to Reproduce** — clear, numbered reproduction steps
* **Expected vs. Actual Result** — explicit comparison to highlight the deviation
* **Environment** — OS version, device model, and network configuration context
* **Severity & Priority Classification** — based on business impact and urgency
* **Resolution / Mitigation Notes** — root cause analysis and fix summary once resolved

*Full detailed documentation, including exact reproduction steps and technical specifics, is available for discussion during an interview but is withheld here in accordance with confidentiality obligations to my former employer, as the underlying system remains in active production use.*

---

## Why I Document Bugs This Way

I treat bug documentation as a communication tool, not just a checklist. A well-written bug report should let a developer reproduce the issue without needing to ask follow-up questions, and let a project manager understand business and operational impact at a glance. I prioritize:

* **Clarity over brevity** — enough detail to reproduce, without unnecessary noise.
* **Risk and impact framing** — especially for issues affecting data integrity across connected hardware and cloud systems (e.g., identity scrambling on terminal overwrites and report formatting drops).
* **Consistent severity/priority logic** — so triage decisions are predictable across the team.
* **Practical mitigation thinking** — proposing operational workarounds (such as specific data purges or infrastructure environment switching) when an immediate code fix isn't feasible.
