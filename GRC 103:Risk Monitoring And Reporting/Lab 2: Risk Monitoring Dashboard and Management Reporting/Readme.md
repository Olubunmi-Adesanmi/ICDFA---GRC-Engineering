# GRC103 Module 4 – Lab 2: Risk Monitoring Dashboard and Management Reporting

## Northbridge Services | Risk Monitoring and Management Reporting

![Status](https://img.shields.io/badge/Project-GRC103-blue)
![Module](https://img.shields.io/badge/Module-4-informational)
![Lab](https://img.shields.io/badge/Lab-2-orange)
![Focus](https://img.shields.io/badge/Focus-Risk%20Monitoring-purple)
![Data](https://img.shields.io/badge/Data-Fictional-lightgrey)

## 1. Project Overview

This project documents the completion of **GRC103 Module 4, Lab 2: Risk Monitoring Dashboard and Management Reporting**, delivered as part of the International Cybersecurity and Digital Forensics Academy (ICDFA) GRC Engineering programme.

The exercise focuses on applying Governance, Risk and Compliance (GRC) principles to monitor security control performance, identify emerging risks, assess business exposure and communicate risk-related findings to management.

Working in the role of a GRC Analyst at the fictional organisation Northbridge Services, I analysed a three-month dataset covering January, February and March. The analysis evaluated five key risk and control performance indicators, identified deteriorating control performance, updated the organisational risk register and proposed corrective and improvement actions.

The project demonstrates how monitoring information can be transformed into measurable risk insights, accountable treatment plans and management-level reporting.

**Important:** All organisational information, metrics, risks and scenarios used in this exercise are fictional training data. No production environment, live organisation or real security infrastructure was assessed.

## 2. Scenario and Business Context

Northbridge Services requires a monthly view of its security control performance and emerging operational risks.

Management needs to understand whether existing security controls are operating effectively, whether identified weaknesses are increasing, and what actions should be prioritised to reduce organisational exposure.

The supplied dataset covers five monitoring areas:

- Endpoint monitoring coverage.
- Critical security alert review within 24 hours.
- Backup and restoration success.
- Overdue high-risk treatment actions.
- Confirmed unauthorised file changes.

The objective was to evaluate the January–March performance trend, identify March threshold breaches and recommend practical risk treatment measures with accountable owners and measurable outcomes.

## 3. Project Objectives

The main objectives were to:

1. Develop a risk monitoring dashboard using the supplied monthly dataset.
2. Calculate and classify five security and risk performance indicators.
3. Analyse three months of monitoring results and identify deteriorating trends.
4. Identify three priority concerns requiring management attention.
5. Update the risk register using likelihood and impact assessments.
6. Develop an action and assurance plan with owners, deadlines and closure evidence.
7. Prepare a management report communicating March performance, priority risks and decisions required.
8. Demonstrate evidence-based GRC reporting and risk escalation.

## 4. Scope of Work

The exercise covered the following activities:

| Area | Activities |
|---|---|
| Data analysis | Reviewed January, February and March monitoring data. |
| Indicator calculations | Calculated coverage, timely review, restore success and overdue action rates. |
| Threshold classification | Applied the supplied Green, Amber and Red thresholds. |
| Dashboard development | Presented three-month indicator trends and unauthorised-change counts separately. |
| Risk assessment | Identified four risks and assessed likelihood, impact and overall scores. |
| Risk treatment | Proposed containment and longer-term improvement actions. |
| Assurance | Defined closure evidence, independent review and outcome tests. |
| Management reporting | Prepared a March management report for the Head of Operations. |

**Scope limitation:** This was a spreadsheet-based assessment. The exercise did not require Wazuh deployment, endpoint access, vulnerability scanning, security testing or live-system monitoring.

## 5. Monitoring Indicators

Five indicators were evaluated using the formulas and thresholds supplied in the ICDFA lab brief.

| Indicator | Calculation | Green | Amber | Red |
|---|---|---:|---:|---:|
| Monitoring coverage | Actively monitored ÷ eligible endpoints × 100 | ≥98% | ≥95% and <98% | <95% |
| Timely critical-alert review | Alerts reviewed within 24 hours ÷ critical alerts × 100 | ≥95% | ≥85% and <95% | <85% |
| Restore-test success | Successful restore tests ÷ tests performed × 100 | 100% | ≥90% and <100% | <90% |
| Overdue high-risk actions | Overdue actions ÷ actions due × 100 | ≤10% | >10% and ≤20% | >20% |
| Confirmed unauthorised changes | Confirmed cases following review | 0 | 1–2 | ≥3 |

The classification was based on unrounded values, while percentages were displayed to one decimal place.

Where a denominator is zero, the indicator must be reported as N/A rather than zero performance or 100% success.

## 6. Key Findings

The analysis identified a deterioration in all five indicators by March.

### March monitoring position

| Indicator | January | February | March | March status |
|---|---:|---:|---:|---|
| Monitoring coverage | 98.0% | 95.0% | 90.0% | Red |
| Timely critical-alert review | 95.0% | 80.0% | 70.0% | Red |
| Restore-test success | 100.0% | 90.0% | 80.0% | Red |
| Overdue high-risk actions | 10.0% | 25.0% | 40.0% | Red |
| Confirmed unauthorised changes | 1 | 3 | 5 | Red |

### Three priority concerns

**1. Endpoint monitoring blind spots**

Monitoring coverage decreased to 90.0% in March, with 108 of 120 eligible endpoints actively monitored. This left 12 endpoints outside active monitoring, compared with two in January and five in February.

**2. Delayed critical-alert review**

Only 70.0% of critical alerts were reviewed within 24 hours in March. Twelve of 40 alerts were not reviewed within the required period. Confirmed unauthorised changes also increased from one in January to five in March.

**3. Failed restoration**

Restore-test success declined to 80.0% in March, with two failed tests out of ten. This raises concerns about the organisation's ability to recover systems or information when restoration is required.

An additional concern was the increase in overdue high-risk actions to 40.0%, representing six overdue actions out of 15 due.

## 7. Risk Register Summary

Four risks were assessed using the supplied 5 × 5 likelihood and impact methodology.

| Risk ID | Risk area | Likelihood | Impact | Score | Rating |
|---|---|---:|---:|---:|---|
| R-01 | Endpoint monitoring coverage | 4 | 4 | 16 | High |
| R-02 | Critical-alert triage | 4 | 4 | 16 | High |
| R-03 | Backup and restoration | 3 | 5 | 15 | High |
| R-04 | High-risk treatment actions | 4 | 3 | 12 | High |

All four risks were assessed as High. The indicator status and risk score were considered separately because a Red performance indicator does not automatically mean that the associated risk is Critical.

## 8. Proposed Risk Treatment Actions

Eight proposed actions were developed across the four risks.

| Risk | Action IDs | Treatment focus |
|---|---|---|
| R-01 | A-01, A-02 | Reconcile and enrol unmonitored endpoints; strengthen provisioning controls. |
| R-02 | A-03, A-04 | Address overdue critical alerts; improve triage capacity and monitoring. |
| R-03 | A-05, A-06 | Investigate failed restoration tests; strengthen restore assurance. |
| R-04 | A-07, A-08 | Resolve overdue actions; introduce weekly oversight and early warnings. |

The plan distinguishes immediate containment from longer-term improvement. Every action remains **Proposed** until approved, implemented and independently verified.

## 9. Management Recommendations

The following decisions were requested from the Head of Operations:

- Approve the four proposed containment actions: A-01, A-03, A-05 and A-07.
- Authorise the responsible managers to begin immediate remediation.
- Agree temporary critical-alert triage capacity until timely review reaches at least 95% for two consecutive month ends.
- Sponsor mandatory endpoint agent enrolment during provisioning.
- Support a weekly review of overdue high-risk treatment actions.
- Require evidence-based closure and independent assurance of completed actions.

## 10. Project Deliverables

The project is supported by the following artefacts:

| Deliverable | Description |
|---|---|
| Risk monitoring workbook | Contains the supplied dataset, calculations, threshold classifications and dashboard charts. |
| Consolidated Markdown report | Combines the submission report and supporting analysis. |
| PDF submission report | Presentation-ready report containing the risk register, action plan and management report. |
| README | Project overview, methodology, key findings and deliverables. |

### Suggested repository structure

```text
GRC103-Module-4-Lab-2/
│
├── README.md
│
├── reports/
│   ├── GRC103_Module4_Lab2_Risk_Monitoring_Analysis.md
│   └── GRC103_Module4_Lab2_Risk_Monitoring_Report.pdf
│
├── workbook/
│   └── GRC103_Lab2_Risk_Monitoring_Workbook.xlsx
│
└── evidence/
    └── supporting-analysis/
```

Update the paths above to match the actual filenames and folders uploaded to the repository.

## 11. GRC Competencies Demonstrated

This exercise demonstrates practical understanding of:

- Governance, Risk and Compliance (GRC) principles.
- Security control monitoring and performance measurement.
- Risk identification and assessment.
- Likelihood and impact scoring.
- Risk register development and maintenance.
- Risk treatment planning and accountability.
- Control effectiveness and assurance.
- Key Risk Indicators (KRIs) and Key Performance Indicators (KPIs).
- Management reporting and risk escalation.
- Evidence-based decision-making.
- Excel-based risk analysis and dashboard reporting.

## 12. Assumptions and Limitations

The analysis distinguishes supplied observations from assumptions and proposed actions.

- The dataset is fictional and reflects a classroom exercise.
- Existing controls are inferred from the measures provided and require confirmation.
- Risk likelihood and impact ratings represent proposed assessments, not measured probabilities.
- Possible causes are hypotheses requiring investigation.
- Accountable owners are proposed roles, not confirmed individuals.
- Action deadlines are relative to the report date.
- Three months of observations show the direction of performance but cannot establish a reliable long-term forecast.
- Classroom thresholds are not represented as official ICDFA organisational policy.

## 13. Conclusion

The Northbridge Services exercise demonstrates the importance of consistent security control monitoring and timely risk management.

The March results show deterioration across all five indicators, with significant concerns relating to endpoint monitoring coverage, critical-alert review, restoration capability and overdue risk treatment actions.

The risk register and proposed action plan translate these findings into accountable remediation activities, measurable closure requirements and management oversight.

The central GRC lesson is that monitoring should not end with calculating percentages or assigning Red, Amber and Green statuses. Effective risk management requires understanding the business consequences, prioritising exposure, assigning responsibility and verifying whether corrective actions have improved control performance.

## 14. References

1. International Cybersecurity and Digital Forensics Academy (ICDFA). (n.d.). *GRC103 Module 4: Risk Monitoring and Reporting, Lab 2 – Risk Monitoring Dashboard and Management Reporting*. Course brief.
2. International Organization for Standardization. (2018). *ISO 31000:2018 Risk management – Guidelines*. ISO.
3. International Organization for Standardization and International Electrotechnical Commission. (2022). *ISO/IEC 27001:2022 Information security, cybersecurity and privacy protection – Information security management systems – Requirements*. ISO/IEC.
4. International Organization for Standardization and International Electrotechnical Commission. (2016). *ISO/IEC 27004:2016 Information technology – Security techniques – Information security management – Monitoring, measurement, analysis and evaluation*. ISO/IEC.
5. National Institute of Standards and Technology. (2008). *NIST Special Publication 800-55 Revision 1: Performance Measurement Guide for Information Security*. NIST.
6. National Institute of Standards and Technology. (2010). *NIST Special Publication 800-34 Revision 1: Contingency Planning Guide for Federal Information Systems*. NIST.

---

**Project classification:** Fictional training exercise  
**Programme:** ICDFA GRC Engineering  
**Module:** GRC103 – Module 4  
**Lab:** Lab 2 – Risk Monitoring Dashboard and Management Reporting
