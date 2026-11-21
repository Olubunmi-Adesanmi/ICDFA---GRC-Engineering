# RISK MONITORING DASHBOARD AND MANAGEMENT REPORTING
## Northbridge Services – Risk Monitoring Analysis and Supporting Assessment

**Institution:** International Cybersecurity and Digital Forensics Academy (ICDFA)  
**Programme:** GRC Engineering  
**Course:** GRC103 – Risk Assessment and Management Techniques  
**Module:** Module 4 – Risk Monitoring and Reporting  
**Lab:** Lab 2 – Risk Monitoring Dashboard and Management Reporting  
**Student:** Olubunmi Adesanmi 
**Registration Number:** C11/26/CGRCE/17550 
**Report Date:** November 22 
**Version:** 1.0  
**Classification:** Fictional Training Data

Link to workbook: https://docs.google.com/spreadsheets/d/10AIvlG7s5rqDctT5rKbfpA_MAT10eLOG3kjz7UmK6CU/edit?usp=sharing

---

# TABLE OF CONTENTS

1. [Executive Summary](#1-executive-summary)
2. [Introduction and Business Scenario](#2-introduction-and-business-scenario)
3. [Scope and Objectives](#3-scope-and-objectives)
4. [Methodology and Calculation Framework](#4-methodology-and-calculation-framework)
5. [Source Dataset](#5-source-dataset)
6. [Risk Monitoring Results](#6-risk-monitoring-results)
7. [Interpretation of March Performance](#7-interpretation-of-march-performance)
   - 7.1 Endpoint Monitoring Coverage
   - 7.2 Critical-Alert Review
   - 7.3 Backup and Restoration
   - 7.4 Overdue High-Risk Actions
8. [Risk Scoring and Escalation](#8-risk-scoring-and-escalation)
9. [Updated Risk Register](#9-updated-risk-register)
10. [Risk Treatment and Action Plan](#10-risk-treatment-and-action-plan)
11. [Assurance and Control Validation](#11-assurance-and-control-validation)
12. [Management Report – March](#12-management-report--march)
13. [Management Decisions and Recommendations](#13-management-decisions-and-recommendations)
14. [Assumptions and Limitations](#14-assumptions-and-limitations)
15. [Conclusion](#15-conclusion)
16. [References](#16-references)

---

# 1. Executive Summary

This report presents the findings of a three-month risk monitoring and management reporting exercise conducted for the fictional organisation Northbridge Services as part of ICDFA GRC103 Module 4, Lab 2.

The exercise involved analysing a supplied dataset covering January, February and March to evaluate security control performance, identify threshold breaches, assess emerging risks and recommend corrective actions.

Five monitoring indicators were assessed:

1. Endpoint monitoring coverage.
2. Timely critical-alert review.
3. Backup and restoration success.
4. Overdue high-risk treatment actions.
5. Confirmed unauthorised file changes.

The March results indicate that all five indicators had reached Red status. Performance deteriorated across every measure over the three-month reporting period.

The most significant concerns identified were:

- **Endpoint monitoring:** Coverage declined to 90.0%, leaving 12 out of 120 eligible endpoints unmonitored.
- **Critical-alert review:** Only 70.0% of critical alerts were reviewed within 24 hours, leaving 12 of 40 alerts outside the required review period.
- **Backup and restoration:** Restore-test success declined to 80.0%, with two unsuccessful restoration tests out of ten.
- **Overdue treatment actions:** The overdue high-risk action rate increased to 40.0%, representing six overdue actions out of 15 due.
- **Unauthorised changes:** Confirmed unauthorised file changes increased from one in January to five in March.

Four risks were identified and assessed using a likelihood and impact scoring methodology. All four were rated High, with scores ranging from 12 to 16.

Eight proposed risk treatment actions were developed, covering immediate containment and longer-term control improvement. Each action includes a proposed owner, relative target date, required closure evidence and an outcome test.

Management attention is required to approve the immediate containment actions, strengthen endpoint monitoring, improve alert-triage capacity, investigate failed restoration tests and address overdue high-risk treatment activities.

**Data qualification:** All figures and organisational details are fictional. Three monthly observations demonstrate the direction of performance but cannot establish a reliable long-term forecast.

# 2. Introduction and Business Scenario

## 2.1 Background

Northbridge Services is a fictional organisation requiring improved visibility into its security control performance and emerging operational risks.

Management requires a structured monthly reporting process that provides information about control effectiveness, risk exposure, emerging weaknesses and the progress of corrective actions.

In this exercise, the GRC Analyst is responsible for examining the supplied monitoring dataset and translating the results into meaningful risk information for management.

The assessment focuses on the relationship between security monitoring, risk identification, control performance, risk treatment and management oversight.

## 2.2 Business Problem

The organisation's monitoring information indicates that several important security and operational controls are deteriorating.

Weak endpoint monitoring coverage may create blind spots across the organisation's technology environment. Delayed critical-alert reviews may increase the time required to identify and respond to genuine threats. Declining restoration success may affect business continuity, while overdue high-risk actions may allow known exposures to remain unresolved.

Management therefore requires an evidence-based assessment of these weaknesses and practical recommendations to improve control performance.

## 2.3 Assessment Context

The exercise was completed using the fictional dataset provided in the ICDFA GRC103 Module 4 Lab 2 brief.

No live-system access, security infrastructure deployment, Wazuh installation or production data collection was required.

The analysis was conducted using spreadsheet-based calculations, risk assessment and management reporting.

# 3. Scope and Objectives

## 3.1 Scope

The assessment covered the January–March reporting period and evaluated five performance indicators.

The work included:

- Reviewing the supplied monthly dataset.
- Calculating monitoring and risk performance indicators.
- Applying the supplied Green, Amber and Red classification thresholds.
- Examining performance changes across the three reporting periods.
- Identifying three priority concerns in March.
- Updating the risk register with four assessed risks.
- Proposing containment and improvement actions.
- Defining evidence requirements and measurable outcome tests.
- Developing an assurance approach.
- Preparing a management report for the Head of Operations.

## 3.2 Objectives

The objectives were to:

1. Develop a monitoring dashboard containing calculated indicators and trend charts.
2. Identify control performance deterioration and threshold breaches.
3. Interpret monitoring figures in relation to their possible business consequences.
4. Distinguish observed evidence from possible causes and assumptions.
5. Assess identified risks using a 5 × 5 likelihood and impact framework.
6. Establish accountable risk owners and proposed review dates.
7. Develop practical risk treatment actions with measurable outcomes.
8. Communicate the findings and decisions required through management reporting.

# 4. Methodology and Calculation Framework

## 4.1 Data Source

The primary source was the monthly dataset supplied in the ICDFA GRC103 Module 4 Lab 2 course brief.

Each month was treated as a separate reporting period.

The analysis preserves the distinction between:

- Critical alerts generated.
- Critical alerts reviewed within 24 hours.
- Confirmed unauthorised file changes following review.
- Successful restoration tests.
- Restoration tests performed.

Confirmed unauthorised changes are treated as confirmed cases, not as the total number of file-change alerts.

Successful restoration tests are treated as a subset of the total tests performed.

## 4.2 Indicator Calculation Formulas

The following calculations were applied.

| Indicator | Formula |
|---|---|
| Monitoring coverage | Actively monitored endpoints ÷ eligible endpoints × 100 |
| Timely critical-alert review | Critical alerts reviewed within 24 hours ÷ critical alerts generated × 100 |
| Restore-test success | Successful restore tests ÷ restore tests performed × 100 |
| Overdue high-risk actions | Overdue high-risk actions ÷ high-risk actions due × 100 |
| Confirmed unauthorised changes | Use the confirmed case count directly. |

Percentages are displayed to one decimal place.

Classification is performed using the unrounded calculated values.

Where a denominator is zero, the result must be shown as N/A because a meaningful percentage cannot be calculated. A zero denominator must not be presented as zero performance or 100% success.

No denominator in the supplied dataset was zero.

## 4.3 Indicator Thresholds

The following classroom thresholds were used.

| Indicator | Green | Amber | Red |
|---|---|---|---|
| Monitoring coverage | ≥98% | ≥95% and <98% | <95% |
| Timely critical-alert review | ≥95% | ≥85% and <95% | <85% |
| Restore-test success | 100% | ≥90% and <100% | <90% |
| Overdue high-risk actions | ≤10% | >10% and ≤20% | >20% |
| Confirmed unauthorised changes | 0 | 1–2 | ≥3 |

These thresholds were supplied for the exercise. They are not presented as official ICDFA policy.

## 4.4 Risk Scoring Methodology

The four identified risks were assessed using likelihood and impact scores ranging from 1 to 5.

**Risk score = Likelihood × Impact**

| Risk Score | Classification |
|---:|---|
| 1–4 | Low |
| 5–9 | Medium |
| 10–16 | High |
| 17–25 | Critical |

The risk assessment considered the likelihood of the risk occurring and the potential severity of its business consequences.

An indicator's colour is not automatically equivalent to its risk rating. A Red indicator identifies poor control performance against a threshold, while the risk score considers the likelihood and impact of the associated risk event.

# 5. Source Dataset

The following fictional dataset was used throughout the assessment.

| Measure | January | February | March |
|---|---:|---:|---:|
| Eligible endpoints | 100 | 100 | 120 |
| Actively monitored endpoints | 98 | 95 | 108 |
| Critical alerts generated | 20 | 30 | 40 |
| Critical alerts reviewed within 24 hours | 19 | 24 | 28 |
| Confirmed unauthorised file changes | 1 | 3 | 5 |
| Restore tests performed | 10 | 10 | 10 |
| Successful restore tests | 10 | 9 | 8 |
| High-risk actions due in month | 10 | 12 | 15 |
| High-risk actions overdue at month end | 1 | 3 | 6 |

The dataset provides the basis for the monitoring calculations, dashboard classifications, risk register and management recommendations.

# 6. Risk Monitoring Results

## 6.1 Calculated Performance Indicators

The calculations produced the following results.

| Indicator | January | February | March |
|---|---:|---:|---:|
| Monitoring coverage | 98.0% | 95.0% | 90.0% |
| Timely critical-alert review | 95.0% | 80.0% | 70.0% |
| Restore-test success | 100.0% | 90.0% | 80.0% |
| Overdue high-risk actions | 10.0% | 25.0% | 40.0% |
| Confirmed unauthorised changes | 1 | 3 | 5 |

## 6.2 Threshold Classification Results

| Indicator | January | February | March | Overall trend |
|---|---|---|---|---|
| Monitoring coverage | Green | Amber | Red | Deteriorating |
| Timely critical-alert review | Green | Red | Red | Deteriorating |
| Restore-test success | Green | Amber | Red | Deteriorating |
| Overdue high-risk actions | Green | Red | Red | Deteriorating |
| Confirmed unauthorised changes | Amber | Red | Red | Deteriorating |

January recorded four Green indicators and one Amber indicator.

By February, none of the indicators remained Green.

By March, all five indicators were Red.

This indicates a consistent deterioration in the measured control performance throughout the reporting period.

## 6.3 Month-to-Month Changes

| Indicator | January | March | Change |
|---|---:|---:|---:|
| Monitoring coverage | 98.0% | 90.0% | −8.0 percentage points |
| Timely critical-alert review | 95.0% | 70.0% | −25.0 percentage points |
| Restore-test success | 100.0% | 80.0% | −20.0 percentage points |
| Overdue high-risk actions | 10.0% | 40.0% | +30.0 percentage points |
| Confirmed unauthorised changes | 1 | 5 | +4 cases |

## 6.4 Dashboard and Trend Visualisation

The companion Excel workbook contains a dashboard presenting the three-month monitoring results.

The dashboard uses:

- A labelled trend chart for monitoring coverage.
- A labelled trend chart for timely critical-alert review.
- A labelled trend chart for restoration success.
- A separate count chart for confirmed unauthorised changes.
- Eligible versus actively monitored endpoint counts to illustrate the monitoring gap.

The percentage indicators are displayed separately from count-based measures to prevent misleading comparisons between different units.

The dashboard supports management visibility into deteriorating control performance and the indicators requiring investigation or escalation.

# 7. Interpretation of March Performance

Four areas were examined in detail. The first three represent the priority concerns requested in the assessment, while overdue high-risk actions are included as an additional Red indicator.

## 7.1 Endpoint Monitoring Coverage

**Observed evidence**

In March, 108 out of 120 eligible endpoints were actively monitored.

\[
\text{Coverage} = \frac{108}{120}\times100 = 90.0\%
\]

The monitoring coverage gap was:

\[
120-108=12\text{ endpoints}
\]

The trend was:

| Month | Eligible endpoints | Monitored endpoints | Unmonitored endpoints | Coverage |
|---|---:|---:|---:|---:|
| January | 100 | 98 | 2 | 98.0% |
| February | 100 | 95 | 5 | 95.0% |
| March | 120 | 108 | 12 | 90.0% |

**Interpretation**

Although the actively monitored endpoint count increased from 95 in February to 108 in March, the eligible endpoint population increased from 100 to 120.

The increase in monitored endpoints therefore did not represent an improvement in coverage.

The eligible endpoint population grew faster than the monitored endpoint count, causing the coverage rate to decline.

This demonstrates why management should assess both the number of monitored endpoints and the percentage of the eligible estate covered.

**Business consequence**

Unmonitored endpoints may create visibility gaps in the organisation's security monitoring environment.

Unauthorised activity or changes affecting these endpoints may go undetected, potentially delaying investigation and response.

**Possible cause – hypothesis**

New endpoints may have been added without being enrolled in the monitoring environment.

This has not been established by the supplied dataset.

**Recommended validation**

Reconcile the endpoint inventory against the monitoring console and examine the enrolment status and dates of all unmonitored endpoints.

**Performance targets**

- Amber threshold: at least 114 of 120 endpoints monitored (95%).
- Green threshold: at least 118 of 120 endpoints monitored (98%).

## 7.2 Critical-Alert Review

**Observed evidence**

In March, 40 critical alerts were generated and only 28 were reviewed within 24 hours.

\[
\text{Timely Review} = \frac{28}{40}\times100=70.0\%
\]

The number of alerts not reviewed within 24 hours was:

\[
40-28=12\text{ alerts}
\]

| Month | Critical alerts generated | Reviewed within 24 hours | Not reviewed within 24 hours | Timely review |
|---|---:|---:|---:|---:|
| January | 20 | 19 | 1 | 95.0% |
| February | 30 | 24 | 6 | 80.0% |
| March | 40 | 28 | 12 | 70.0% |

Critical-alert volume doubled from 20 in January to 40 in March.

The number of alerts reviewed within 24 hours increased from 19 to 28, but the review rate continued to decline.

Confirmed unauthorised file changes increased during the same period:

\[
1\rightarrow3\rightarrow5
\]

**Business consequence**

Delayed review may allow genuine security threats to remain uninvestigated for longer periods.

This may increase the time required to contain incidents and could allow unauthorised activity to continue.

**Possible cause – hypothesis**

The alert volume may have increased faster than the available alert-triage capacity.

The dataset does not contain staffing information, analyst workloads or triage records, so this explanation requires further investigation.

**Important limitation**

A critical alert is not necessarily a confirmed security incident. The increase in delayed alerts and confirmed unauthorised changes does not establish that delayed reviews caused the increase in unauthorised changes.

**Recommended validation**

Review triage logs, sample the unreviewed alerts and compare alert volume against analyst capacity and available review hours.

## 7.3 Backup and Restoration

**Observed evidence**

In March, eight out of ten restoration tests were successful.

\[
\text{Restore Success}=\frac{8}{10}\times100=80.0\%
\]

Two restoration tests were unsuccessful.

| Month | Restore tests performed | Successful tests | Failed tests | Success rate |
|---|---:|---:|---:|---:|
| January | 10 | 10 | 0 | 100.0% |
| February | 10 | 9 | 1 | 90.0% |
| March | 10 | 8 | 2 | 80.0% |

**Business consequence**

Failed restoration may affect the organisation's ability to recover important systems or data following data loss, corruption, ransomware or another disruption.

If restoration is unsuccessful when required, the organisation may experience prolonged outages, operational disruption or data loss.

**Possible cause – hypothesis**

Potential causes could include backup faults, configuration changes, incomplete backup coverage or systems outside the backup scope.

These causes have not been confirmed by the supplied dataset.

**Recommended validation**

Investigate the failed restoration records, review backup configurations and repeat the failed tests with integrity verification and application-owner confirmation.

## 7.4 Overdue High-Risk Actions

**Observed evidence**

Six out of 15 high-risk actions due in March were overdue.

\[
\text{Overdue Rate}=\frac{6}{15}\times100=40.0\%
\]

| Month | High-risk actions due | Overdue actions | Overdue rate |
|---|---:|---:|---:|
| January | 10 | 1 | 10.0% |
| February | 12 | 3 | 25.0% |
| March | 15 | 6 | 40.0% |

**Business consequence**

When high-risk treatment actions are not completed within their agreed deadlines, identified vulnerabilities and control weaknesses may remain unresolved for longer.

This may increase organisational exposure and delay the reduction of known risks.

**Recommended validation**

Review the action register, confirm the accountable owner for each overdue item, investigate blocked actions and document approved revised deadlines or risk acceptance decisions.

**Data limitation**

The exercise brief does not establish whether the overdue figures include actions carried over from earlier months. The supplied rates are therefore interpreted as provided, without assuming how overdue items are carried forward.

# 8. Risk Scoring and Escalation

## 8.1 Risk Rating Method

The likelihood and impact of each risk were assessed on a scale of 1 to 5.

\[
\text{Risk Score}=\text{Likelihood}\times\text{Impact}
\]

| Score | Rating |
|---:|---|
| 1–4 | Low |
| 5–9 | Medium |
| 10–16 | High |
| 17–25 | Critical |

The likelihood and impact scores reflect proposed professional judgements based on the available evidence and possible business consequences.

They are not mathematically derived from the indicator percentages.

## 8.2 Risk Assessment Summary

| Risk ID | Risk area | Likelihood | Impact | Score | Rating |
|---|---|---:|---:|---:|---|
| R-01 | Endpoint monitoring coverage | 4 | 4 | 16 | High |
| R-02 | Critical-alert triage | 4 | 4 | 16 | High |
| R-03 | Backup and restoration | 3 | 5 | 15 | High |
| R-04 | High-risk treatment actions | 4 | 3 | 12 | High |

No risk was rated Critical because the available information demonstrates deteriorating control performance rather than confirmed catastrophic loss.

## 8.3 Escalation Requirements

Under the exercise rules:

- Every Red indicator must be escalated to its responsible manager within one working day.
- Every High or Critical risk must also receive management escalation.
- All four risks require escalation because their scores fall within the High category.

These escalation arrangements are exercise requirements and are not represented as official ICDFA policy.

# 9. Updated Risk Register

The following register consolidates the four identified risks, their March evidence, existing controls, proposed ratings, accountable owners and review dates.

The existing controls are inferred from the measures being monitored and must be confirmed by the responsible managers.

## 9.1 Risk R-01: Endpoint Monitoring Coverage

| Field | Assessment |
|---|---|
| Risk ID | R-01 |
| Asset / process | Endpoint monitoring coverage |
| Risk statement | If eligible endpoints are not actively monitored, malicious activity or unauthorised changes on those endpoints may go undetected, delaying response and increasing potential impact. |
| March evidence | Coverage was 90.0% (108 of 120 endpoints). The monitoring gap increased from 2 to 5 to 12 endpoints across the three months. |
| Existing control | Monitoring agent deployment and monthly coverage reporting (inferred; confirm). |
| Likelihood | 4 |
| Impact | 4 |
| Risk score | 16 |
| Risk rating | High |
| Accountable owner | Endpoint Security Manager |
| Proposed actions | A-01 and A-02 |
| Review date | RD + 14 days |

**Rating justification**

Likelihood is rated 4 because the monitoring gap currently exists and has widened over two consecutive months.

Impact is rated 4 because approximately 10% of the eligible endpoint population may lack active monitoring.

Impact is not rated 5 because the supplied data does not establish that critical assets are among the unmonitored endpoints.

## 9.2 Risk R-02: Critical-Alert Triage

| Field | Assessment |
|---|---|
| Risk ID | R-02 |
| Asset / process | Critical-alert triage |
| Risk statement | If critical alerts are not reviewed within 24 hours, genuine threats may remain uncontained, increasing dwell time and potential impact. |
| March evidence | Timely review was 70.0% (28 of 40 alerts). Twelve alerts were not reviewed within 24 hours. Confirmed unauthorised changes increased from 1 to 3 to 5. |
| Existing control | Critical-alert review procedure with a 24-hour target (inferred; confirm). |
| Likelihood | 4 |
| Impact | 4 |
| Risk score | 16 |
| Risk rating | High |
| Accountable owner | Security Operations Manager |
| Proposed actions | A-03 and A-04 |
| Review date | RD + 14 days |

**Rating justification**

Likelihood is rated 4 because timely review has remained below the Amber threshold for two months while alert volume and delayed reviews have increased.

Impact is rated 4 because late reviews could allow genuine threats to remain active for longer.

Impact is not rated 5 because not all critical alerts represent incidents.

## 9.3 Risk R-03: Backup and Restoration

| Field | Assessment |
|---|---|
| Risk ID | R-03 |
| Asset / process | Backup and restoration |
| Risk statement | If restoration fails when needed, systems or data may not be recovered in time, prolonging outages or causing data loss. |
| March evidence | Restoration success was 80.0% (8 of 10 tests). Failed tests increased from 0 to 1 to 2. |
| Existing control | Scheduled backups and monthly restoration tests (inferred; confirm). |
| Likelihood | 3 |
| Impact | 5 |
| Risk score | 15 |
| Risk rating | High |
| Accountable owner | Backup and Recovery Manager |
| Proposed actions | A-05 and A-06 |
| Review date | RD + 14 days |

**Rating justification**

Likelihood is rated 3 because restoration failures are increasing, although an actual restoration requirement during the reporting period is not established.

Impact is rated 5 because failed restoration could result in severe and prolonged service disruption or data loss.

## 9.4 Risk R-04: High-Risk Treatment Actions

| Field | Assessment |
|---|---|
| Risk ID | R-04 |
| Asset / process | High-risk treatment actions |
| Risk statement | If high-risk treatment actions are not completed on time, known exposures may remain open for longer and other risks may remain above tolerance. |
| March evidence | The overdue action rate reached 40.0% (6 of 15 actions), increasing from 10.0% to 25.0% and then 40.0%. |
| Existing control | High-risk action tracking with due dates (inferred; confirm). |
| Likelihood | 4 |
| Impact | 3 |
| Risk score | 12 |
| Risk rating | High |
| Accountable owner | Risk and Compliance Manager |
| Proposed actions | A-07 and A-08 |
| Review date | RD + 30 days |

**Rating justification**

Likelihood is rated 4 because the overdue rate has increased consistently and has reached 40%.

Impact is rated 3 because delays extend known exposures, although the precise effects depend on which actions are overdue and are not identified in the supplied data.

# 10. Risk Treatment and Action Plan

## 10.1 Treatment Strategy

The action plan contains two treatment stages for each risk:

- **Containment:** Immediate measures intended to address the current exposure.
- **Improvement:** Longer-term measures intended to strengthen the control environment and reduce the likelihood of recurrence.

All eight actions are proposed. None is marked as completed.

Target dates are calculated relative to the report date (RD).

## 10.2 Action Register

| ID | Risk | Type | Proposed action | Owner | Target |
|---|---|---|---|---|---|
| A-01 | R-01 | Containment | Reconcile the endpoint inventory with the monitoring console. Enrol every unmonitored endpoint, isolate it or document an approved exception. | Endpoint Security Manager | RD + 7 days |
| A-02 | R-01 | Improvement | Make agent enrolment mandatory during endpoint provisioning and introduce a weekly eligible-versus-monitored reconciliation alert. | Endpoint Security Manager | RD + 60 days |
| A-03 | R-02 | Containment | Triage every critical alert older than 24 hours. Review each confirmed unauthorised change for containment and root cause. | Security Operations Manager | RD + 2 days |
| A-04 | R-02 | Improvement | Review triage capacity, rota arrangements and alert tuning against the doubled alert volume. Introduce a daily 24-hour review dashboard. | Security Operations Manager | RD + 45 days |
| A-05 | R-03 | Containment | Investigate the failed March restoration tests, correct identified root causes and repeat the tests. | Backup and Recovery Manager | RD + 10 days |
| A-06 | R-03 | Improvement | Extend restoration testing to critical systems on a risk basis and record recovery times against system targets. | Backup and Recovery Manager | RD + 60 days |
| A-07 | R-04 | Containment | Review every overdue high-risk action, confirm its owner, assign an approved revised date or documented risk acceptance, and escalate blocked items. | Risk and Compliance Manager | RD + 5 days |
| A-08 | R-04 | Improvement | Introduce a weekly overdue-action review and a seven-day early-warning process before action deadlines, with reporting to the Head of Operations. | Risk and Compliance Manager | RD + 45 days |

## 10.3 Action Closure Evidence and Outcome Tests

Completion of an activity alone is not sufficient evidence that a risk has been reduced.

Each action must have documented evidence and an outcome test.

| ID | Evidence required for closure | Outcome test |
|---|---|---|
| A-01 | List of all unmonitored endpoints showing the outcome for each; monitoring console export showing the active endpoint count. | Coverage reaches at least 98% (118 of 120) at the next month end. |
| A-02 | Updated provisioning procedure and four consecutive weekly reconciliation reports. | Coverage remains at or above 98% for two consecutive month ends. |
| A-03 | Triage log showing a disposition for every alert; case records showing containment status. | No critical alert remains unreviewed after 24 hours during daily checks over five working days. |
| A-04 | Capacity review note, approved rota changes where applicable and evidence of the dashboard in use. | Timely critical-alert review reaches at least 95% for two consecutive month ends. |
| A-05 | Root-cause investigation note and restoration retest records containing integrity checks and application-owner confirmation. | Each repeated restoration test is successful, passes integrity checks and is confirmed usable by the application owner. |
| A-06 | Updated restoration test schedule, recovery-time results and confirmation that backup scope has been checked against the endpoint inventory. | The next two monthly test cycles achieve 100% verified success, and one critical-system restoration meets its recovery target. |
| A-07 | Updated action register showing the owner, revised date and approving authority for every overdue action. | No overdue action lacks a documented management decision; no action remains more than 30 days overdue without documented acceptance. |
| A-08 | Weekly review minutes and early-warning reports. | Overdue action rate decreases to 10% or less at the next two month ends. |

## 10.4 Action Accountability

The proposed accountable roles are:

| Role | Responsibilities |
|---|---|
| Endpoint Security Manager | Address endpoint monitoring gaps and ensure enrolment controls are strengthened. |
| Security Operations Manager | Restore timely critical-alert review and improve triage capacity. |
| Backup and Recovery Manager | Investigate restoration failures and strengthen recovery testing. |
| Risk and Compliance Manager | Resolve overdue risk treatment actions and improve action tracking. |
| Head of Operations | Provide management oversight, approve required resources and support escalation. |

The owners are proposed roles and must be confirmed by the Head of Operations.

# 11. Assurance and Control Validation

## 11.1 Purpose of Assurance

The assurance approach is designed to establish whether proposed risk treatment actions have produced measurable improvements.

Evidence of activity completion must be supported by evidence that the intended control outcome has been achieved.

Examples include:

- Endpoint monitoring coverage recalculated using a monitoring console export.
- Critical alerts reviewed within the required 24-hour period.
- Successful restoration confirmed through integrity checks.
- Overdue actions reduced to the agreed threshold.

## 11.2 Independent Verification

Action closure should be reviewed by someone other than the action owner.

The proposed independent reviewer is a GRC Analyst.

The reviewer should:

1. Examine the evidence submitted by the action owner.
2. Confirm that the evidence supports the claimed action completion.
3. Check that the relevant outcome test has been satisfied.
4. Record any outstanding weaknesses or exceptions.
5. Recommend closure only when sufficient evidence is available.

## 11.3 Ongoing Monitoring

The organisation should continue monitoring the five indicators monthly.

The proposed success criteria include:

| Indicator | Desired outcome |
|---|---|
| Monitoring coverage | At least 98%. |
| Timely critical-alert review | At least 95%. |
| Restore-test success | 100%. |
| Overdue high-risk actions | 10% or less. |
| Confirmed unauthorised changes | Zero confirmed cases. |

Because the available dataset contains only three monthly observations, sustained improvement should be assessed using at least two consecutive month-end readings where specified in the action plan.

A single improved reading should not automatically be treated as evidence of sustained control effectiveness.

# 12. Management Report – March

**To:** Head of Operations  
**From:** [Full Name], GRC Analyst  
**Registration Number:** [Enter registration number]  
**Report Date:** [Enter report date]  
**Reporting Period:** January–March  
**Data Classification:** Fictional Training Data

## 12.1 March Risk Monitoring Status

The March monitoring results indicate that all five performance indicators are Red.

In January, four indicators were Green and one was Amber. By February, no indicators remained Green. Every indicator deteriorated across the reporting period.

| Indicator | January | February | March | March status | Green threshold |
|---|---:|---:|---:|---|---|
| Monitoring coverage | 98.0% | 95.0% | 90.0% | Red | ≥98% |
| Timely critical-alert review | 95.0% | 80.0% | 70.0% | Red | ≥95% |
| Restore-test success | 100.0% | 90.0% | 80.0% | Red | 100% |
| Overdue high-risk actions | 10.0% | 25.0% | 40.0% | Red | ≤10% |
| Confirmed unauthorised changes | 1 | 3 | 5 | Red | 0 |

## 12.2 Three Priority Concerns

### Priority 1: Endpoint Monitoring Blind Spots

Monitoring coverage declined to 90.0%, representing 108 monitored endpoints out of 120 eligible endpoints.

Twelve endpoints were not actively monitored, compared with five in February and two in January.

Although monitored endpoint numbers increased from 95 to 108, the eligible estate expanded from 100 to 120. The growth in eligible endpoints therefore exceeded the growth in monitored endpoints.

This creates potential monitoring blind spots where malicious activity or unauthorised changes may go undetected.

One possible explanation is that new endpoints were added without being enrolled. This requires confirmation through inventory reconciliation.

### Priority 2: Delayed Critical-Alert Review

Only 70.0% of critical alerts were reviewed within 24 hours in March.

Twelve of 40 critical alerts were not reviewed within the required period.

Confirmed unauthorised changes increased from one in January to five in March.

Delayed review may allow genuine threats to remain uncontained for longer. However, the dataset does not establish that delayed review caused the increase in confirmed unauthorised changes.

A possible explanation is that triage capacity did not increase sufficiently to match the doubling of alert volume from 20 to 40.

### Priority 3: Failed Restoration

Restore-test success declined to 80.0%, with eight successful tests out of ten in March.

The number of failed tests increased from zero in January to one in February and two in March.

This may affect the organisation's ability to recover important systems or data when restoration is required.

Potential causes include backup faults, configuration changes or incomplete backup coverage. These explanations require investigation through failed-test records and repeated restoration testing.

### Additional Red Indicator: Overdue High-Risk Actions

The overdue action rate reached 40.0%, with six of 15 actions overdue.

This represents a growing treatment backlog and may allow known exposures to remain unresolved.

## 12.3 Decisions and Resources Requested

Management approval and support are requested for the following:

**1. Approve immediate containment actions**

Approve A-01, A-03, A-05 and A-07, and authorise the responsible managers to begin work within their proposed deadlines.

**2. Provide temporary alert-triage capacity**

Agree temporary additional alert-triage capacity, with the required resource level to be confirmed by the Security Operations Manager.

This arrangement should remain in place until timely critical-alert review reaches at least 95% for two consecutive month ends.

**3. Strengthen endpoint provisioning**

Sponsor mandatory security monitoring agent enrolment as part of the endpoint provisioning process.

**4. Improve overdue-action oversight**

Support a weekly review of overdue high-risk treatment actions, including early warnings seven days before deadlines.

## 12.4 Owners, Escalation and Next Review

| Risk | Proposed accountable owner | Next review |
|---|---|---|
| R-01 – Endpoint monitoring coverage | Endpoint Security Manager | RD + 14 days |
| R-02 – Critical-alert triage | Security Operations Manager | RD + 14 days |
| R-03 – Backup and restoration | Backup and Recovery Manager | RD + 14 days |
| R-04 – High-risk treatment actions | Risk and Compliance Manager | RD + 30 days |

All Red indicators should be escalated to their responsible managers within one working day.

All four risks have High risk scores and require management escalation under the exercise rules.

The next review should evaluate evidence of corrective action and progress against the defined outcome tests, including endpoint coverage of at least 98% and verified restoration success.

**Management conclusion:** Northbridge Services requires immediate attention to deteriorating control performance. Approval of the proposed containment measures and continued management oversight are necessary to address the identified exposures.

**Reporting qualification:** The dataset is fictional. Three monthly observations show the direction of performance but cannot establish a reliable long-term forecast.

# 13. Management Decisions and Recommendations

The assessment supports the following management priorities.

| Priority | Recommendation | Expected benefit |
|---|---|---|
| Immediate | Approve and initiate containment actions A-01, A-03, A-05 and A-07. | Addresses current monitoring, alert-review, restoration and treatment weaknesses. |
| Short term | Investigate all unreviewed critical alerts and failed restoration tests. | Improves visibility into unresolved issues and supports timely containment. |
| Short term | Reconcile all unmonitored endpoints and overdue actions. | Identifies ownership gaps and outstanding exposures. |
| Medium term | Make endpoint monitoring enrolment part of the provisioning process. | Reduces the likelihood of future monitoring gaps. |
| Medium term | Review security operations capacity and introduce daily alert-triage monitoring. | Improves timeliness and consistency of alert reviews. |
| Ongoing | Conduct risk-based restoration tests and monitor recovery targets. | Strengthens recovery assurance. |
| Ongoing | Introduce weekly overdue-action reviews and independent closure verification. | Improves accountability and risk treatment effectiveness. |

Management should review the action register regularly and require supporting evidence before recording any action as completed.

# 14. Assumptions and Limitations

## 14.1 Observed Information

The following information is directly supported by the supplied dataset and calculations:

- Monthly eligible and monitored endpoint numbers.
- Critical alerts generated and reviewed within 24 hours.
- Confirmed unauthorised file-change counts.
- Restoration tests performed and successfully completed.
- High-risk actions due and overdue.
- Calculated percentages, gaps, trends and threshold classifications.

## 14.2 Assumptions

The following elements involve proposed professional judgement or assumptions:

- Existing controls have been inferred from the measures being monitored and require confirmation.
- Likelihood and impact scores are proposed assessments.
- Possible root causes have not been confirmed.
- Accountable owners are proposed roles rather than named individuals.
- Action deadlines are relative to the report date.
- Resource requirements are subject to management review and approval.

## 14.3 Limitations

1. The dataset contains only three monthly observations.
2. The figures are fictional and do not represent actual organisational performance.
3. Three months of results are insufficient to establish a reliable long-term trend forecast.
4. Classroom indicator thresholds are not presented as official ICDFA policy.
5. The data does not identify individual endpoints, alert records, restoration failure causes or action-level ownership.
6. The dataset does not prove that delayed alert review caused the increase in unauthorised changes.
7. The analysis does not establish whether overdue actions include items carried forward from earlier months.
8. The assessment does not constitute a live security audit or technical validation of Northbridge Services infrastructure.

These limitations have been considered when interpreting the results and developing the proposed recommendations.

# 15. Conclusion

The GRC103 Module 4 Lab 2 assessment demonstrates how structured risk monitoring and performance measurement can support organisational decision-making.

The January–March analysis identified a consistent deterioration in all five monitored indicators. March recorded Red status across endpoint monitoring coverage, critical-alert review, backup restoration, overdue high-risk actions and confirmed unauthorised file changes.

Four associated risks were assessed and rated High. The findings were translated into eight proposed treatment actions, each with accountable ownership, relative deadlines, closure evidence and measurable outcome tests.

The assessment also demonstrates the importance of distinguishing between observed evidence, professional judgement and possible causes. A monitoring indicator provides valuable information about control performance, but additional investigation and assurance are necessary before management can conclude that a specific cause or risk event has been established.

The central recommendation is to strengthen management oversight, prioritise immediate containment, improve control processes and require independent verification of treatment outcomes.

Effective GRC monitoring is not simply about reporting figures. It involves using evidence to identify weaknesses, understand their potential business consequences, assign accountability and verify that corrective actions achieve their intended results.

# 16. References

International Cybersecurity and Digital Forensics Academy. (n.d.). *GRC103 Module 4: Risk Monitoring and Reporting, Lab 2 – Risk Monitoring Dashboard and Management Reporting*. Course brief.

International Organization for Standardization. (2018). *ISO 31000:2018 Risk management – Guidelines*. Geneva: ISO.

International Organization for Standardization and International Electrotechnical Commission. (2022). *ISO/IEC 27001:2022 Information security, cybersecurity and privacy protection – Information security management systems – Requirements*. Geneva: ISO/IEC.

International Organization for Standardization and International Electrotechnical Commission. (2016). *ISO/IEC 27004:2016 Information technology – Security techniques – Information security management – Monitoring, measurement, analysis and evaluation*. Geneva: ISO/IEC.

National Institute of Standards and Technology. (2008). *NIST Special Publication 800-55 Revision 1: Performance Measurement Guide for Information Security*. Gaithersburg, MD: NIST.

National Institute of Standards and Technology. (2010). *NIST Special Publication 800-34 Revision 1: Contingency Planning Guide for Federal Information Systems*. Gaithersburg, MD: NIST.

Link to workbook: https://docs.google.com/spreadsheets/d/10AIvlG7s5rqDctT5rKbfpA_MAT10eLOG3kjz7UmK6CU/edit?usp=sharing

---


**Document classification:** Fictional Training Data  
**Programme:** ICDFA GRC Engineering  
**Course:** GRC103 – Risk Assessment and Management Techniques  
**Module:** Module 4 – Risk Monitoring and Reporting  
**Lab:** Lab 2 – Risk Monitoring Dashboard and Management Reporting
