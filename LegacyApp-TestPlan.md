# Test Plan & Test Case Matrix: Personnel Attendance Management System

---

## Document Information

| Item | Description |
|------|-------------|
| Project | Personnel Attendance Management System |
| Document | Master Test Plan & Test Case Matrix |
| Author | Dimas Hidayat |
| Version | 7.4 |
| Testing Type | Manual Testing (Software-to-Hardware) |
| Methodology | Agile / Scrum |

---

# 1. Purpose

This document defines the overall testing plan and test case matrix for validating the **Personnel** desktop-based attendance management system across iterative releases (v1.1 to v1.4) before client-side deployment.

The testing process aims to verify desktop application stability, local database data-type sanitization, dynamic work shift scheduling, local-to-hardware data alignment, and dual-method biometric IoT hardware provisioning while minimizing deployment risks.

---

# 2. Test Objectives

The objectives of this testing cycle are:

- Validate personnel data registration and profile management.
- Verify biometric machine connectivity routines (Automatic & Manual methods).
- Ensure synchronization of attendance logs between machine and application.
- Validate shift and roster scheduling integrity.
- Detect regression in core shift systems after leave management additions.
- Validate local database data-type sanitization and consistency.
- Verify hardware-to-software authentication handshakes.
- Ensure system resilience under local network isolation scenarios.

---

# 3. Scope

## In Scope

The following modules and features are included:

- User Authentication (Local Access)
- Personnel/Employee Profile Management
- Text Input Validation & Character Constraints
- Machine/Device Registration (Manual & Auto-Scan)
- Attendance Data Synchronization (Pull/Download Logs)
- Shift & Master Schedule Management
- Roster & Schedule Mapping
- Overtime & Overnight (Cross-Day) Shift Calculations
- Leave Type Configurations (v1.4 Dynamic Masters)
- Leave Quota Allocation & Balance Adjustments
- Payroll Data Consolidation (WageConnect Payload Streaming)
- Device Offline Standalone Mode Validation
- Local Database Management

---

## Out of Scope

The following testing activities are excluded from this testing cycle:

- Cloud-based Subscription Management
- Online Payment Gateways (QRIS/Virtual Account)
- Live Server/Cloud Load Balancing
- Web/Browser-based Interface Testing

---

# 4. Test Environment

| Component | Environment |
|------------|-------------|
| Client Desktop OS | Windows 7 (SP1), Windows 10, Windows 11 |
| Database | Local (SQL-based Architecture) |
| Network Topology | Isolated Shared Local Network Router (Wi-Fi/LAN) |
| Issue Tracking | Internal Ticketing System |
| Deployment | QA Staging Middleware Builds (v1.1 – v1.4) |
| Hardware Under Test | Revo Series Fleet & Premium Enterprise Biometric Terminals |

---

# 5. Testing Approach

Testing will be performed using:

- Functional Testing
- Regression Testing
- Hardware Integration Testing (Software-to-Hardware Data Streams)
- Boundary Value Analysis (BVA)
- Exploratory Testing (UX & Missing Guidance Evaluation)
- Negative Testing (Data Injections & Network Cut-offs)
- Local Network Connection Testing

Detailed testing techniques are documented in **Personnel-TestStrategy.md**.

---

# 6. Entry Criteria

Testing starts when:

- Development is completed and Installation package (Setup.exe) is ready.
- Release changelogs and database migration files are accessible.
- Test data templates (Employee names, shift parameters) are prepared.
- Biometric testing hardware devices are cleared, reset, and connected to the local network router.

---

# 7. Exit Criteria

Testing is completed when:

- All planned test cases (REG, SCH, LEV, PAY, DEV, NET modules) are fully executed within the single master matrix.
- Critical and High-severity defects (e.g., UI freeze, App crash) are completely resolved and verified.
- Regression testing passes, proving new features haven't degraded older core features.
- User Acceptance testing/Validation is approved.

---

# 8. Risks

| Risk | Mitigation |
|------|------------|
| Physical biometric hardware fleet scarcity | Leverage simulated socket responses for bulk testing while reserving physical Revo terminals for final integration passes |
| Erratically dropped discovery packets during auto-scans | Enforce strict network requirements keeping both testing laptop and devices on an isolated local router sub-mask |
| Missing instruction boundaries for high-tier machine logins | Maintain an internal QA device log detailing factory default parameters to bypass app documentation gaps |
| Intermittent local network instability | Validate local fallback logging profiles to ensure offline records preserve data strings correctly |

---

# 9. Core Testing Scenarios & Methodologies (Test Case Matrix)

The following master table highlights the complete set of test cases executed during the manual QA cycle across continuous deployments (v1.1 – v1.4):

| Test Case ID | Module | Test Scenario | Test Steps | Expected Result | Actual Result | Severity | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-REG-001** | Core Performance | Verify UI responsiveness and loading behavior during initial application launch | 1. Launch desktop application.<br>2. Observe loading screen duration.<br>3. Monitor thread activity. | Application launches smoothly within acceptable thresholds (< 3 seconds). | **The UI thread freezes completely** on the initial loading screen due to synchronous execution. | **High** | **Failed** |
| **TC-REG-002** | Form Validation | Verify mandatory field presence validation triggers when required data is left blank | 1. Navigate to Employee Registration.<br>2. Clear 'Employee Name' and 'Employee ID' fields.<br>3. Click 'Save'. | System blocks submission and displays explicit inline warnings. | System successfully blocks submission and displays accurate inline validation warnings. | **Low** | **Passed** |
| **TC-REG-003** | Form Validation | Evaluate length constraint threshold behavior for 'Employee Name' input field | 1. Open Registration form.<br>2. Input 1 character into Name field and save.<br>3. Test with 2, then 3 characters. | Submissions with < 3 characters are blocked; names with ≥ 3 characters are accepted. | System rejects 1 and 2 characters accurately, and successfully saves records with 3+ characters. | **Low** | **Passed** |
| **TC-REG-004** | Data Validation | Validate data type data sanitization on the structured Employee ID field | 1. Open Employee Registration form.<br>2. Inject alphanumeric characters and special symbols (`@`, `#`).<br>3. Click 'Save'. | System intercepts the input, rejects submission, and prompts for numeric data only. | **System silently accepts letters and symbols** into the database without validation alerts. | **Critical** | **Failed** |
| **TC-SCH-001** | Shift Management | Verify Master Shift data creation and structural constraint integrity | 1. Navigate to Shift Settings.<br>2. Define a new shift with specific clock-in/out times.<br>3. Save master shift. | Master shift is created successfully with correct time formats and stored locally. | System successfully creates and stores the master shift parameters with precise time attributes. | **Medium** | **Passed** |
| **TC-SCH-002** | Employee Roster Mapping | Validate employee schedule assignment using pre-defined master shifts | 1. Access Schedule Mapping module.<br>2. Select active personnel.<br>3. Assign shift to their calendar.<br>4. Save assignment. | Employee roster is updated seamlessly, and scheduling data is mapped correctly. | Roster mapping functions flawlessly; schedules are perfectly assigned to targeted personnel. | **High** | **Passed** |
| **TC-SCH-003** | Shift Management | Validate stability when modifying or deleting an existing shift name | 1. Navigate to Shift Settings.<br>2. Select an active shift name.<br>3. Perform an edit or delete operation.<br>4. Save. | System updates or removes the shift data cleanly and updates associated employee rosters. | **Application crashes immediately** when a user attempts to edit or delete a shift name. | **Critical** | **Failed** |
| **TC-SCH-004** | Attendance Calculation | Verify overnight cross-day shift calculations (past midnight) with missing clock-out data | 1. Insert a shift roster that crosses midnight.<br>2. Input "Clock-In" log only.<br>3. Trigger attendance calculation. | System calculates hours worked up to cutoff or flags missing clock-out accurately. | **Calculations fail or distort hours worked** when a cross-day shift only contains a clock-in log. | **High** | **Failed** |
| **TC-LEV-001** | Leave Management (New v1.4) | Verify admin capability to dynamically create custom leave/absence types | 1. Navigate to Leave Configuration.<br>2. Click 'Add New Leave Type'.<br>3. Input custom parameters.<br>4. Save. | Custom leave type is created successfully and instantly populated across all forms. | System successfully processes, stores, and renders the newly created custom leave types dynamically. | **High** | **Passed** |
| **TC-LEV-002** | Leave Management (New v1.4) | Validate Leave Quota Allocation functionality and boundary constraint handling | 1. Open Leave Quota Adjustment menu.<br>2. Select targeted personnel.<br>3. Input numerical value for quota.<br>4. Save. | Quota allocation is saved accurately, establishing the baseline threshold. | Quota configurations are successfully assigned to employee profiles and stored without data loss. | **High** | **Passed** |
| **TC-PAY-001** | Payroll Integration | Verify end-to-end data pipeline streaming to the WageConnect payroll module | 1. Open Payroll Linkage settings.<br>2. Run attendance data consolidation.<br>3. Stream payload to WageConnect. | Attendance summaries bridge smoothly to payroll processing engine. | Integration pipe functions flawlessly; attendance logs accurately map into WageConnect. | **High** | **Passed** |
| **TC-DEV-001** | IoT Data Sync | Validate download behavior when clicking employee data fetch button multiple times rapidly | 1. Connect IoT terminal.<br>2. Navigate to Download Personnel.<br>3. Click 'Download' button rapidly. | System queues requests or disables button to prevent redundant, overlapping downloads. | **Data duplication occurs** across the local storage database due to lack of button debouncing. | **High** | **Failed** |
| **TC-DEV-002** | IoT Integration | Verify system resiliency and operational continuity when IoT device is switched to offline mode | 1. Connect device.<br>2. Sever active cloud network connection.<br>3. Perform scans.<br>4. Re-verify app connectivity. | Application seamlessly supports offline mode, storing logs locally without interruption. | System successfully handles local data logging and maintains device compatibility in offline mode. | **High** | **Passed** |
| **TC-DEV-003** | IoT Integration (New v1.4) | Validate the functionality of the 'Device Connection Test' feature | 1. Navigate to Devices menu.<br>2. Select active terminal.<br>3. Click 'Test Connection'. | System pings device and returns explicit, real-time connection status (Success/Failed). | The system successfully triggers hardware pinging and renders connection status accurately. | **High** | **Passed** |
| **TC-DEV-004** | IoT Integration | Validate local hardware automatic discovery scanning protocol (Shared Network Method) | 1. Ensure laptop and hardware are on the same Wi-Fi/LAN.<br>2. Trigger automated device scan.<br>3. Monitor discovery rate. | Application rapidly discovers and populates active biometric terminals detected on the shared network. | **Device scanning lags or drops discovery packets** intermittently, making hardware detection highly unstable. | **High** | **Failed** |
| **TC-DEV-005** | Hardware Compatibility | Validate system behavior and error handling when connecting unsupported/legacy terminals | 1. Attempt to connect legacy machine or unverified new model.<br>2. Trigger synchronization. | System detects hardware profile, restricts communication, and throws "Unsupported Model" exception. | System successfully enforces compatibility constraints, preventing unauthorized hardware setup. | **High** | **Passed** |
| **TC-DEV-006** | Device Authentication | Evaluate credential verification via local Device Password injection (Revo Series Focus) | 1. Scan/Register a Revo Series machine.<br>2. Input mandatory 'Device Password'.<br>3. Save and initialize data bridge. | Application securely authenticates terminal using password string and opens data streaming pipe. | **Authentication fails intermittently or rejects valid strings** on Revo models during v1.1-v1.4. | **High** | **Failed** |
| **TC-DEV-007** | Device Authentication | Evaluate credential validation and UX guidance clarity for high-tier biometric machine logins | 1. Connect premium high-tier device.<br>2. Navigate to fields requiring Machine Username and Device Password.<br>3. Observe guidelines. | UI displays clear inline contextual descriptions explaining what credentials to input. | **Critical instructions are entirely missing** in v1.1-v1.4, leaving users with no explanation. | **Medium** | **Failed** |
| **TC-NET-001** | Network Connectivity | Validate manual hardware provisioning stability under standard non-cloud networks (Manual Input Method) | 1. Open manual registration page.<br>2. Input IP Address, Machine Name, Device Type, and Port manually.<br>3. Save and connect. | System processes manual parameters and registers the non-cloud local machine successfully. | **Connection drops or fails intermittently** during manual terminal parameter mapping. | **High** | **Failed** |

---

# 10. Deliverables

The testing process will produce:

- Test Strategy (`Personnel-TestStrategy.md`)
- Test Cases (`Personnel-TestCaseStudy.md`)
- Bug Report (`Personnel-BugReport.md`)
- Test Execution Report (`Personnel-TestExecutionReport.md`)
- Test Summary Report (`Personnel-TestSummaryReport.md`)

---

# 11. Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| QA Engineer | Set up hardware connections, plan, and execute manual testing modules |
| Developer | Resolve thread locks, form bugs, and app crash defects |
| User / Admin | Validate payroll and attendance workflow reports |

---

## Notes

This document has been created for portfolio purposes based on professional QA practices.

Company-specific implementation details have been generalized to comply with confidentiality obligations while preserving testing methodology and overall QA workflow.
