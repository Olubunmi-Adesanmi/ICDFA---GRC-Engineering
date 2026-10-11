# GRC102 Information Security Governance
## Practical Lab 5: Monitoring, Auditing Controls and Executive Reporting
### Security Governance Simulation Report

**Student:** [Olubunmi Adesanmi]  
**Role:** [Security Governance Analyst]  
 


## Table of Contents
1. [Executive Summary](#executive-summary)
2. [Assessment Scope and Evidence Method](#assessment-scope-and-evidence-method)
3. [Part 1: Setting Up a Simulated Environment](#part-1-setting-up-a-simulated-environment)
4. [Part 2: Analysing Security Governance Failures](#part-2-analysing-security-governance-failures)
5. [Equifax Case Study Comparison](#equifax-case-study-comparison)
6. [Part 3: Implementing Security Governance Controls](#part-3-implementing-security-governance-controls)
7. [Part 4: Developing Security Governance Metrics and Reporting](#part-4-developing-security-governance-metrics-and-reporting)
8. [Board-Level Report Summary](#board-level-report-summary)
9. [Metrics Framework](#metrics-framework)
10. [Dashboard User Guide](#dashboard-user-guide)
11. [Priority Action Plan and Residual Risk](#priority-action-plan-and-residual-risk)
12. [Conclusion](#conclusion)
13. [References](#references)
    
   
    ## Executive Summary

This report documents GRC 102 security governance simulation. The practical laboratory  files and outputs  show the preparation of a container-based lab configuration, database initialization files, monitoring-related files, Python scripts for vulnerability scanning and governance analysis, a governance tracker data file, a vulnerability report, a governance failure report, dashboard output, and metric visualisation files.

The supplied vulnerability report contains three checks. The Apache Struts2 S2-045 check was **inconclusive** because the hostname `web_server` could not be resolved. The MySQL check did not detect access using the default credentials tested. The network segmentation check reported a medium-severity finding because the web server could directly access the database server.

The governance failure analysis generated `governance_failure_report_20261011_002329.json` and identified three failures: ineffective implementation of the Patch Management Policy, metrics that were not driving remediation, and insufficient network segmentation. The governance data recorded four policies, eight controls, three open risks, one historical incident, five metrics, and one audit record. The three open risks were rated Critical, High, and Medium.

The dashboard output reported patch compliance of 85% against a 95% target, remediation time of 12 days against a 7-day target, one incident against a target of zero, and two October 2026 values of 100%. Two metrics were incorrectly or inconsistently marked Green despite missing their targets. The October 2026 figures are recorded values, not independently verified outcomes.

The authorised Struts simulation did not complete: the configured image tag returned `manifest unknown`, and the simulation could not resolve `web_server`. The failure-analysis script also printed `No attack log found`. No evidence was supplied of a successful post-remediation scan or retest. The report therefore distinguishes between project artefacts created, results reported by scripts, and control effectiveness that remains unverified.


## Part 1: Setting Up a Simulated Environment

### 1.1 Environment and files

This practical laboratory was conducted in a Kali Linux environment using a container-based configuration. The lab environment comprised a Docker Compose configuration, database initialization files, monitoring-related resources, Python scripts for security testing and governance analysis, governance data files, and generated reports and visualisations. 


### 1.2 Vulnerability assessment


| ID | Check | Result | Severity | Interpretation / next action |
|---|---|---|---|---|
| V-01 | Apache Struts2 S2-045 (CVE-2017-5638) | Inconclusive; name resolution failure | Unknown | Restore the authorised service and repeat the check. Do not treat the result as vulnerable or not vulnerable. |
| V-02 | MySQL default credentials | Default-credential access not detected | N/A | This tests only the credentials checked; separately verify account, privilege and authentication settings. |
| V-03 | Network segmentation | Web server reported able to access database directly | Medium | Review network rules and retest that only required, authorised paths are allowed. |

The scanner summary reported three checks, one Medium finding and one Unknown result, with no High or Critical findings among these checks. This is not proof that the entire environment was free of vulnerabilities; it is only the summary of the tests included in this report.


*Figure 1. Reconstructed dashboard snapshot based on the supplied governance tracker output.

### 1.4 Part 1 evidence gaps

The current work session contains the text of the vulnerability report and dashboard output,Five PNG files existed in `metrics_visualizations/`: `monitoring_coverage.png`, `patch_compliance.png`, `security_incidents.png`, `vuln_remediation.png`, and `policy_compliance.png`. Their actual image contents were not uploaded, so their plotted trends cannot be independently described here as shown in the evidences provided

## Part 2: Analysing Security Governance Failures

### 2.1 Failure analysis output

 `analyze_governance_failures.py`. printed `No attack log found`, then reported completion and saved `governance_failure_report_20261011_002329.json`. The JSON identified three failures.

| ID | Category | Recorded description | Recorded impact | Recommended action |
|---|---|---|---|---|
| GF-01 | Policy Implementation | Patch Management Policy not effectively implemented | Critical vulnerabilities may remain unpatched despite policy | Improve patch process, oversight, ownership, deadlines and tracking. |
| GF-02 | Metrics and Measurement | Security metrics not driving effective remediation | Metrics not leading to security improvements | Set actionable metrics, owners, targets, review intervals and escalation rules. |
| GF-03 | Security Architecture | Insufficient network segmentation | Potential lateral movement and expanded compromise | Apply least privilege segmentation and verify allowed paths. |

These are the precise categories and descriptions in the generated JSON. They are not a substitute for the full technical log evidence. Since no attack log was found and the Struts simulation was blocked, the report does not claim that an attack succeeded.

### 2.2 Governance interpretation

**Policy implementation:** an active policy does not prove effective operation. The dataset contains an active Patch Management Policy, yet the failure analysis reports that its implementation was ineffective. Management needs evidence of patch prioritisation, deadlines, exceptions, deployment success and retesting.

**Metrics and measurement:** performance data must trigger decisions. The supplied dashboard marks remediation time and incident count Green despite their recorded values missing the stated targets. This weakens confidence in automated status reporting and makes metric validation a governance control.

**Security architecture:** the scanner's network-segmentation result and the open High risk in the governance dataset agree that connectivity between the web and database services requires review. The remediation should be proven through connectivity tests, not just a control status label.

### 2.3 Equifax case study comparison

The lab scenario resembles governance weaknesses reported in the 2017 Equifax incident, but the cases must not be treated as identical. A 2018 U.S. House Committee staff report stated that Equifax failed to patch a known critical vulnerability, leaving systems exposed for 145 days, and described a monitoring certificate that had expired for 19 months, weakening visibility into encrypted traffic. It also identified gaps in accountability and management structure (U.S. House of Representatives, Committee on Oversight and Government Reform, 2018). The U.S. Government Accountability Office described shortcomings involving vulnerability identification, detection, database access segmentation and data governance; its report stated that at least 145.5 million individuals' personal information was accessed (U.S. Government Accountability Office, 2018).

| Governance theme | Equifax case lesson | Lab evidence | What can reasonably be concluded |
|---|---|---|---|
| Vulnerability remediation | Known critical weakness was not patched promptly. | Patch-management policy recorded Active; failure analysis says implementation ineffective; a patch script exists but completion is unverified. | Policy and a script alone are insufficient; patch status must be evidenced and retested. |
| Monitoring and detection | Expired certificate impaired monitoring visibility. | Monitoring coverage recorded as 100%, but no operational evidence was provided; no attack log was found. | Recorded coverage should be validated by checking actual log/alert flow and test events. |
| Segmentation | Access control weaknesses contributed to broader database access. | Scanner reported direct web-to-database access; RISK-002 remains Open and High. | Restrict unnecessary pathways and demonstrate denial of unauthorised connections. |
| Accountability and data governance | Gaps in management accountability and data governance contributed to the incident. | Three governance failures and an open risk register were generated. | Assign accountable owners, deadlines and escalation routes; verify closure with evidence. |
| Impact | Large-scale exposure of sensitive information. | The lab uses a simulated environment; no successful lab attack or exfiltration is evidenced. | The lab illustrates governance failure patterns only; do not claim it reproduced the Equifax breach. |

**Lessons learned:** remediation must be time-bound, tracked, escalated and independently verified. Monitoring must be measured by the availability and usefulness of logs and alerts, not only by a percentage in a dataset. Segmentation and database controls should be tested. Finally, executive reporting must accurately show exceptions and residual risk rather than display green statuses that conflict with the metric targets.

## Part 3: Implementing Security Governance Controls

### 3.1 What the evidence shows

The learner reported creating or running `patch_management.py`. The governance dataset records CTL-004 (Automated Patch Management), CTL-005 (Network Segmentation), CTL-006 (Database Security), CTL-007 (Real-time Security Monitoring) and CTL-008 (Executive Security Oversight) as `Implemented`. It also records an automated patch management control and a network segmentation control while the associated Critical and High risks remain Open.

These recorded statuses establish how the JSON describes the controls, but do not prove that the prescribed control implementation workflow completed successfully. The learner did not recall applying a specific patch, changing network rules, performing further database tests, or running a repeat vulnerability scan. The earlier directory listing did not show the official `implement_governance_controls.py` or a controls verification output. Their current presence must be checked before submission.

### 3.2 Control status register

| Control area | Recorded artefact / status | Evidence status | Required verification |
|---|---|---|---|
| Patch management | `patch_management.py`; CTL-004 recorded Implemented | Script existence/creation reported; patch outcome unconfirmed | Capture script execution result, installed patch/version evidence and repeat scan. |
| Network segmentation | CTL-005 recorded Implemented; scanner finding V-03 | Finding present; successful remediation not evidenced | Capture applicable rules and controlled test showing unauthorised web-to-database access blocked. |
| Database security | CTL-006 recorded Implemented; V-02 did not detect default credentials | A single scanner check only | Verify database accounts, authentication policy and least-privilege permissions without disclosing secrets. |
| Security monitoring | CTL-007 recorded Implemented; metric recorded 100% coverage | Operational log/alert test not supplied | Show a known benign test event reaches the monitored log/alert path and document timestamp/result. |
| Executive oversight | POL-004 and CTL-008 recorded Active/Implemented in JSON | Governance record supplied; meeting/reporting evidence not supplied | Attach a redacted reporting or approval artefact and show escalation owner/frequency. |

### 3.3 Retesting and residual risk

No successful post-control retest was recalled or supplied. Therefore:

- Struts2: **inconclusive; retest blocked** by the unavailable image reference and unresolved service hostname.
- Patch management: **implementation outcome unverified**; no repeat scan supplied.
- Network segmentation: **reported finding remains open for assurance purposes**; no successful post-change test supplied.
- Database security: the default-credential check did not detect access, but other database security controls remain unverified.
- Metrics: **validation issue identified** for remediation time and incident count status.

The lab should not describe these controls as successfully verified until test evidence supports that claim. The Critical unpatched-vulnerability risk and High segmentation risk should remain open pending review, remediation and retesting. This is an evidence status, not a conclusion that no changes were made; it means successful change and test results have not been demonstrated in the supplied evidence.

## Part 4: Developing Security Governance Metrics and Reporting

### 4.1 Tracker and dashboard output

Running `governance_tracker.py --dashboard` supplied a dashboard JSON output generated at `2026-10-11T00:30:20`. It reported 4 policies, 8 controls, 3 risks, 1 incident, 5 metrics and 1 audit record. The risk summary contained one Critical, one High and one Medium risk. The incident summary contained one High-severity historical incident.

### 4.2 Metric review

| Metric | Period | Target | Actual | Recorded status | Assessment |
|---|---|---:|---:|---|---|
| Patch Compliance | May 2023 | 95% | 85% | Red | Correctly signals 10 percentage-point shortfall. |
| Vulnerability Remediation Time | May 2023 | 7 days | 12 days | Green | Incorrect/inconsistent: actual is 5 days over the target. Lower is better. |
| Security Incidents | May 2023 | 0 | 1 | Green | Incorrect/inconsistent: a non-zero incident count misses a zero target. |
| Critical Patch Compliance | October 2026 | 100% | 100% | Green | Meets the recorded target; measurement evidence not supplied. |
| Security Monitoring Coverage | October 2026 | 100% | 100% | Green | Meets the recorded target; measurement evidence not supplied. |


### 4.3 Metrics framework

A metric is useful when it has a clear definition, formula, owner, collection source, target, review frequency, status rule and required response. The recommended framework for this lab is:

| Metric | Definition / formula | Target or rule | Owner (proposed) | Required action if outside target |
|---|---|---|---|---|
| Critical patch compliance | Systems with required critical patches applied within 7 days / in-scope systems × 100 | ≥95%; for the defined critical patch metric, 100% within 7 days if that is the approved policy | Security Engineer / IT Manager | Escalate missed patches; track exception, deadline and retest. |
| Critical vulnerability remediation time | Average elapsed days from validated finding to verified remediation | ≤7 days | Security Engineer | Red if >7 days; escalate overdue critical items. |
| Security incidents | Count of validated incidents in reporting period | Target 0; all incidents still require review regardless of target | Security Director | Any incident triggers review, incident handling and lessons learned. |
| Monitoring coverage | Critical assets sending required logs / critical assets in inventory × 100 | 100% | Security Engineer | Investigate missing log sources; test alert delivery. |
| Network segmentation test pass rate | Approved segmentation tests passed / total approved tests × 100 | 100% of mandatory tests pass | Network Engineer | Open corrective action when prohibited connection succeeds. |
| Policy review currency | Policies reviewed by due date / active policies × 100 | 100% | Policy owners / CISO | Assign review actions for overdue policies. |

Targets above are proposed governance rules, except where the supplied dataset explicitly defines a target. They should be approved by the organisation's governance owner before operational use.

### 4.4 Board-level reporting summary

**Current posture:** The dataset records three open risks: one Critical, one High and one Medium. The Critical risk concerns unpatched vulnerabilities; the High risk concerns insufficient network segmentation. These remain unresolved for assurance purposes because no successful remediation evidence was provided.

**Performance exceptions:** May 2023 data reports 85% patch compliance against 95%, 12-day critical vulnerability remediation against a 7-day target, and one incident against a target of zero. The dashboard correctly marks patch compliance Red but incorrectly or inconsistently marks the latter two metrics Green. The status logic should be corrected before this dashboard is used for management decisions.

**Assurance limitation:** The Struts simulation did not complete and no attack log was found. The October 2026 100% patch and monitoring values are reported measurements but do not reconcile fully with open risks and do not have supporting calculations in the supplied evidence.

**Board decisions requested:** (1) retain the Critical and High risks as open until verified; (2) assign deadlines and owners for patch and segmentation remediation; (3) correct dashboard thresholds; (4) require test evidence for patch status, monitoring and database access; and (5) require periodic reporting of overdue actions and accepted exceptions.

### 4.5 Dashboard user guide summary

The supplied `governance_tracker.py --dashboard` option prints a JSON dashboard summary. The shared evidence does not confirm that the separate HTML dashboard described in the official instructions was generated. To use the reporting output safely:

1. Confirm the JSON input is current and validated.
2. Check the reporting period and source for each metric.
3. Recalculate status using the approved threshold rule; confirm lower-is-better versus higher-is-better metrics.
4. Review Critical/High risks, missing evidence and overdue corrective actions before summarising posture.
5. Escalate exceptions and assign an owner, due date and required retest.
6. Export or capture the actual dashboard and keep the source JSON alongside it for traceability.

A dashboard colour is a signal, not proof of control effectiveness. The status logic and underlying evidence must be reviewed.

### 4.6 How reporting supports governance

A validated metrics framework helps leadership see whether controls are being implemented, whether outcomes are improving, and whether risks are being treated within approved deadlines. The dashboard consolidates control status, risk severity, incidents and key metrics so that executives can prioritise remediation and challenge unsupported claims of improvement. In this lab, the mismatched Green statuses show how poor threshold logic can create false assurance; identifying that inconsistency is itself a valuable governance finding.

## Board-Level Report Summary

**Audience:** Senior management / board  
**Reporting date:** 11 October 2026  
**Decision status:** Several material items require follow-up.

1. **Critical exposure:** one Critical risk remains Open in the data, concerning unpatched vulnerabilities.
2. **Architecture exposure:** one High risk remains Open, concerning network segmentation; the scanner reported direct web-to-database access.
3. **Metric quality:** patch compliance is below target. Remediation time and incident metrics are flagged Green despite failing their targets; correct and retest status logic.
4. **Assurance:** no successful post-control retests were supplied. The Struts simulation was blocked, and no attack log was found.
5. **Management actions:** assign accountable owners and due dates; verify patch and segmentation controls; validate database access and monitoring; require objective retest evidence before closing risks.

Management should not report that the simulated environment achieved an improved security posture until the outstanding verification tests have passed and supporting evidence is attached.

## Metrics Framework

The framework should follow six stages: **Define** the objective and formula; **Collect** from identified sources; **Validate** completeness and date; **Analyse** against targets and trends; **Report** to the relevant audience; **Act and review** through assigned corrective actions. Every metric should specify a data owner, reporting period, formula, threshold, escalation rule and evidence source. Status rules must be aligned to metric direction; for example, a lower remediation time is better, while higher patch compliance is better.

## Dashboard User Guide

### Purpose and intended users
The dashboard is intended to support executives, the board, security leadership and technical control owners. Board users should focus on risk severity, target misses, material incidents and overdue actions; operational users should inspect supporting source data and technical test results.

### Reading the current output
The tracker output lists record counts, risk severity counts and five metric statuses. A Green status should be accepted only after checking the value, target, direction, period and supporting evidence. In the supplied output, `Vulnerability Remediation Time` (12 against 7 days) and `Security Incidents` (1 against zero) are Green; both should be treated as exceptions pending logic correction. The two 100% values are recorded for October 2026 but need source evidence.

### Refresh and review steps
1. Validate `governance_data.json` and the input reporting period.
2. Run the approved metrics and dashboard generator within the isolated lab.
3. Confirm the dashboard file is produced and compare totals with the input records.
4. Test threshold handling against known positive, negative and boundary examples.
5. Capture the dashboard, the command output and the source data version.
6. Review open Critical/High risks and assign actions; do not close controls on the basis of a colour alone.

## Priority Action Plan and Residual Risk

| Priority | Action | Proposed owner | Closure evidence |
|---|---|---|---|
| P1 | Resolve the authorised Struts service image/reference issue and verify service networking; keep service isolated | Lab owner / student | Container status and a successful, authorised application health/check output |
| P1 | Confirm patch status for in-scope components and repeat the approved vulnerability check | Security Engineer | Patch/version evidence and post-change scan report |
| P1 | Validate network segmentation and restrict prohibited paths | Network Engineer | Approved rules plus pass/fail test output demonstrating prohibited path blocked |
| P2 | Verify database authentication and least-privilege user access | Database Administrator | Redacted account/privilege review and test outcome; no secrets in screenshots |
| P2 | Correct Green statuses for remediation time and incident count | Metrics owner / Security Director | Formula/threshold tests and corrected dashboard output |
| P2 | Validate monitoring coverage by confirming required events are ingested and alerts route as intended | Security Engineer | Redacted test-event trace and alert receipt timestamp |
| P3 | Review overdue policy dates and complete governance review records | Policy owners / CISO | Updated approval/review record |
| P3 | Attach genuine screenshots and verify repository contents/commit | Student | Screenshot files, README, report and exact commit URL |

**Residual risk position:** the Critical patching and High segmentation risks remain open in the governance dataset. The Struts result remains unknown. Database and monitoring effectiveness are not fully evidenced. Do not mark these risks closed until remediation and retesting outcomes are available and reviewed by an accountable owner.

## Conclusion

The supplied lab outputs support the creation of a baseline vulnerability report, a governance failure analysis report, a governance register and a governance dashboard summary. They identify three governance failures and highlight a medium-severity network-segmentation finding, a Critical unpatched-vulnerability risk and a High segmentation risk in the dataset. The dashboard also has two status classifications that conflict with their recorded targets.

During the practical lab, Struts simulation did not start, no attack log was found, and evidence of successful remediation and post-control verification was not supplied. The report therefore avoids claiming that the controls were successfully verified. The next step is to attach genuine screenshots, confirm the presence and execution of the official controls and metrics deliverables, correct the dashboard logic, and document successful test outcomes in the authorised isolated lab.

## References

ICDFA. (n.d.). *Week 5 Linux Lab Assignment: Simulating and Analyzing Security Governance Scenarios* [Lab instructions]. GitHub. https://github.com/icdfa/grc-engineering-labs/blob/master/phase1/grc102/week8/LAB_INSTRUCTIONS.md

U.S. Government Accountability Office. (2018). *Data protection: Actions taken by Equifax and federal agencies in response to the 2017 breach* (GAO-18-559). https://www.gao.gov/products/gao-18-559

U.S. House of Representatives, Committee on Oversight and Government Reform. (2018). *The Equifax data breach: Majority staff report*. https://oversight.house.gov/wp-content/uploads/2018/12/Equifax-Report.pdf




