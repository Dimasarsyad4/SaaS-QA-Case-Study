# Bug Log — Sample Defects Identified During QA Testing

*The following is a representative sample of defects identified, documented, and tracked during manual QA testing on a cloud-based HR & Attendance SaaS platform. Details have been generalized to respect confidentiality obligations to my previous employer. Only resolved issues are listed here; in-progress or unresolved findings are withheld.*

| Bug ID | Title | Module | Severity | Priority | Status |
|---|---|---|---|---|---|
| BUG-001 | Unintended quota decrement triggered by a non-transactional page view | Subscription | High | High | Resolved |
| BUG-002 | Several primary payment options disappeared after a backend infrastructure update (regression), leaving only a limited subset of payment methods available | Payment | High | High | Resolved |
| BUG-003 | Transaction QR code expiration window too short, causing elevated payment failure rate | Payment | Medium | High | Resolved |
| BUG-004 | Editable field incorrectly locked as read-only for existing user records | Admin / Data Management | Medium | Medium | Resolved |

### Description Format Used in Full Documentation

Each bug entry in my full testing documentation includes:
- **Steps to Reproduce** — clear, numbered reproduction steps
- **Expected vs. Actual Result** — explicit comparison to highlight the deviation
- **Environment** — browser/OS/device context
- **Severity & Priority Classification** — based on business impact and urgency
- **Resolution Notes** — root cause and fix summary once resolved

*Full detailed documentation, including reproduction steps and technical specifics, is available for discussion during an interview but is withheld here in accordance with confidentiality obligations to my former employer.*

---

## Why I Document Bugs This Way

I treat bug documentation as a communication tool, not just a checklist. A well-written bug report should let a developer reproduce the issue without needing to ask follow-up questions, and let a project manager understand business impact at a glance. I prioritize:

- **Clarity over brevity** — enough detail to reproduce, without unnecessary noise
- **Business impact framing** — especially for revenue-affecting modules like payment and subscription
- **Consistent severity/priority logic** — so triage decisions are predictable across the team
