
# GRC103 Module 3 – Technical Risk Treatment Lab

## Implementing and Validating Security Controls

### Organisation
Northbridge Services (Fictional Scenario)

### Student Information
- Full Name: Olubunmi Adesanmi
- Registration Number: [C11/26/CGRCE/17550]
- Programme: GRC103 – Risk Assessment and Management Techniques
- Module: Module 3 – Risk Treatment Strategies
- Platform: Ubuntu Server 24.04 LTS and Kali Linux

---

## 1. Project Overview

This laboratory demonstrates the practical implementation and
validation of technical risk treatments within a controlled
Linux environment.

The fictional Northbridge Services document server initially
exposed an unnecessary legacy service and an archive containing
dummy training records.

The exercise involved identifying the exposures, implementing
security controls, validating permitted and blocked access,
testing backup recovery and evaluating residual risk.

## 2. Laboratory Environment

| Component | Configuration |
|---|---|
| Target server | Ubuntu Server 24.04 LTS |
| Testing machine | Kali Linux |
| Web server | Nginx |
| Firewall | UFW |
| Scripting/service | Python 3 |
| Network scanner | Nmap |
| HTTP testing | curl |
| Backup utility | tar |
| Integrity tool | SHA-256 |

All tests were performed in an isolated
laboratory VMs using fictional data.

## 3. Objectives

- Establish the original exposed-service baseline.
- Identify and assess the associated risks.
- Retire the unnecessary legacy service.
- Protect the archive directory.
- Restrict incoming traffic using source-based firewall rules.
- Validate authorised and unauthorised access.
- Correlate application and firewall logs.
- Back up and restore a deleted portal file.
- Verify recovered file integrity.
- Evaluate the four risk-treatment strategies.
- Calculate treatment costs and illustrative ALE.
- Document residual risks and monitoring requirements.

## 4. Laboratory Execution and Evidence

### Step 1 – Baseline Assessment
Evidence folder: `01_Baseline_Assessment/`

Contains:
- Original Nmap scan
- Baseline web responses
- Archive directory listing
- Dummy-record retrieval
- Legacy endpoint response
- Baseline listening ports

### Step 2 – Avoidance
Evidence folder: `02_Avoidance/`

Contains:
- Systemd service status
- Updated Nmap scan
- Failed legacy endpoint request
- Approved portal continuity test

### Step 3 – Archive Protection
Evidence folder: `03_Archive_Protection/`

Contains:
- Final Nginx configuration
- Archive directory permissions
- HTTP 403 responses
- Approved portal HTTP 200 response

### Step 4 – Firewall Validation
Evidence folder: `04_Firewall_Validation/`

Contains:
- UFW configuration
- Source-based access rule
- Approved-source test
- Blocked-source test

### Step 5 – Logging
Evidence folder: `05_Logging/`

Contains:
- Nginx access log extracts
- Nginx error log extracts, where relevant
- UFW blocked-packet log extracts, if collected
- Control-validation table

### Step 6 – Backup and Recovery
Evidence folder: `06_Backup_Recovery/`

Contains:
- Backup archive evidence
- Original file hash
- Simulated deletion evidence
- Failed access check
- Restoration result
- SHA-256 verification
- Recovery timestamps

### Step 7 – Risk Treatment and Cost Analysis
Evidence folder: `07_Risk_Treatment/`

Contains:
- Initial risk register
- Residual risk register
- Treatment decision records
- Cost analysis
- ALE calculations

### Step 8 – Change Management
Evidence folder: `08_Change_Management/`

Contains:
- Change records
- Simulated approvals
- Validation results
- Planned and executed rollback records

## 5. Treatment Strategy Summary

| Strategy | Laboratory application |
|---|---|
| Avoidance | Retirement of unnecessary legacy endpoint |
| Mitigation | Archive protection, firewall restrictions and recovery controls |
| Transfer | Assessment of fictional managed-backup arrangement |
| Acceptance | Temporary, limited HTTP risk acceptance |

## 6. Important Limitations

- The environment contains fictional records only.
- The laboratory is isolated from public networks.
- Risk ratings are classroom assessment judgements.
- Financial estimates are based on the supplied assumptions.
- The same-host backup does not protect against complete host loss.
- Management approvals and acceptance decisions are simulated.

## 7. Evidence Integrity

All command outputs and screenshots are intended to represent
tests performed during the laboratory.

Uncollected or unsuccessful evidence is identified rather
than fabricated.


