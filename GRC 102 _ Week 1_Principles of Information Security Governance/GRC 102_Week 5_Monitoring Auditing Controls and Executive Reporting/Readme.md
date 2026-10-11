# GRC102 Practical Lab5 - Security Governance Simulation

**Course:** GRC102 Information Security Governance  
**Assessment:** Practical Lab 5 - Monitoring, Auditing Controls and Executive Reporting  


## Overview

This report  documents a simulated security governance lab covering container setup, vulnerability assessment, governance failure analysis, control status, security metrics, risk oversight and executive reporting. It is organised in the same four-part order required by the assessment brief.

## Important findings

- The supplied vulnerability report identifies one Medium network-segmentation finding, one MySQL default-credential check that did not detect access, and one inconclusive Struts2 check due to hostname resolution failure.
- The governance failure analysis reports three failures: patch-policy implementation, metrics not driving remediation, and insufficient segmentation.
- The tracker data records three open risks: one Critical, one High and one Medium.
- The dashboard marks remediation time (12 days against a 7-day target) and incidents (1 against target 0) as Green. These classifications conflict with their targets and need correction.
- The Struts simulation did not complete; the configured image reference returned `manifest unknown`, the `web_server` hostname did not resolve, and the analysis tool printed `No attack log found`.
- No successful post-remediation retest was provided.

## Contents

| File/folder | Purpose |
|---|---|
| `report.md` | Full evidence-based report, including the required four parts, Equifax comparison, recommendations and references |
| `GRC102_Lab8_Security_Governance_Report.docx` | Editable formatted report |
| `GRC102_Lab8_Security_Governance_Report.pdf` | PDF evidence report; screenshot placeholders must be replaced before final submission |
| `board_report.md` | Concise board-level report based on the supplied results |
| `equifax_comparison.md` | Standalone Equifax case-study comparison |
| `governance_controls_report.md` | Control status and verification report; unresolved tests are explicit |
| `governance_metrics_framework.md` | Metric definitions, formula, owner, thresholds, review cadence and response rules |
| `dashboard_user_guide.md` | User guidance for interpreting and validating the governance dashboard |
| `SUBMISSION_CHECKLIST.md` | Evidence and submission checklist against the four-part rubric |
| `evidence/figures/` | Report-created visualisations reconstructed from supplied JSON values; they are not original Kali screenshots |
| `evidence/screenshots/` | Folder for genuine screenshots captured from the authorised lab |

## Evidence status by assessment part

| Part | Maximum marks | Current status based on evidence supplied |
|---|---:|---|
| Part 1 - Simulated environment | 30 | Partial: files and vulnerability report supplied; container startup and original screenshot evidence incomplete. |
| Part 2 - Governance failure analysis | 25 | Partial: JSON report supplied and Equifax comparison drafted; attack log absent because simulation did not complete. |
| Part 3 - Control implementation | 25 | Partial: patch management component and recorded control statuses exist; successful implementation and retesting are unverified. |
| Part 4 - Metrics and reporting | 20 | Partial: tracker dashboard output supplied; two status classifications conflict with targets and metrics/HTML dashboard execution is not evidenced. |

## Required original screenshots

Put genuine, redacted captures in `evidence/screenshots/`, for example:

- `01_environment_compose_status.png`
- `02_vulnerability_scan_output.png`
- `03_governance_failure_analysis.png`
- `04_dashboard_output.png`
- `05_control_verification.png` (only after conducting an actual retest)
- `06_metric_visualisations.png` or the original five visualisation files



## References

- [ICDFA GRC102 Week 5 Linux Lab Instructions](https://github.com/icdfa/grc-engineering-labs/blob/master/phase1/grc102/week8/LAB_INSTRUCTIONS.md) - official repository instructions supplied with the assessment brief.
- [U.S. GAO report GAO-18-559](https://www.gao.gov/products/gao-18-559) - Equifax breach response and contributing factors.
- [U.S. House Committee report: The Equifax Data Breach](https://oversight.house.gov/wp-content/uploads/2018/12/Equifax-Report.pdf) - patching, monitoring, accountability and other case-study findings.

