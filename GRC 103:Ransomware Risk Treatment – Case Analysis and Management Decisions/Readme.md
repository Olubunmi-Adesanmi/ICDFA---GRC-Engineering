# Ransomware Risk Treatment – Case Analysis and Management Decisions

![Domain](https://img.shields.io/badge/Domain-Cybersecurity%20GRC-blue)
![Module](https://img.shields.io/badge/Module-GRC103%20%7C%20Module%203-purple)
![Project](https://img.shields.io/badge/Project-Risk%20Treatment-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Assessment](https://img.shields.io/badge/Assessment-Case%20Analysis-lightgrey)

## Project Overview

This project was completed as part of the International Cybersecurity and Digital Forensics Academy (ICDFA) GRC103 – Module 3: Risk Treatment Strategies.

The exercise examines how a fictional healthcare provider, **Northbridge Community Health**, can identify, assess, prioritise and treat ransomware-related business risks within a first-year cybersecurity budget of **$100,000**.

Using the documented 2021 ransomware incident involving Ireland's Health Service Executive (HSE) as a real-world reference, the assessment evaluates risk treatment strategies, financial exposure, insurance limitations, business continuity and management decision-making.

The project also considers a simulated change in circumstances: a failed backup restoration test, limited paper-based booking capacity and an increase in the cost of implementing Multi-Factor Authentication (MFA).

The objective was to develop a practical risk treatment strategy that balances cybersecurity investment, financial constraints, patient information protection and essential healthcare service availability.

---

## Learning Objectives

The project demonstrates the ability to:

- Identify and prioritise business risks associated with ransomware.
- Develop an initial risk register using likelihood and impact assessments.
- Evaluate risk avoidance, mitigation, transfer and acceptance.
- Select appropriate security treatments within a fixed financial budget.
- Calculate insurance payments, deductibles and retained financial losses.
- Reassess treatment decisions following changes in business circumstances.
- Evaluate proposed residual risks.
- Develop a 30-day risk treatment and implementation plan.
- Communicate risk decisions through a management and board briefing.

---

## Case Study Background

### Real-World Reference: 2021 HSE Ransomware Incident

The assessment draws on the 2021 ransomware attack against Ireland's Health Service Executive.

The official HSE account documents that:

- An initial phishing email attachment was opened in March 2021.
- Ransomware was triggered in May 2021.
- Files were encrypted and information was accessed and copied.
- The HSE confirmed that no ransom was paid.

These facts demonstrate the importance of phishing awareness, access protection, incident response, information security and operational resilience in healthcare environments.

**Official case source:** [Health Service Executive – Cyber-attack and HSE response](https://www2.hse.ie/services/cyber-attack/what-happened/)

### Fictional Exercise Scenario

Northbridge Community Health is a fictional healthcare provider operating three clinics.

The organisation faces four identified security and business concerns:

1. An unused supplier workflow remains enabled.
2. Backup restoration has not been tested.
3. Phishing reports have no clearly assigned escalation owner.
4. Essential patient bookings must continue during security incidents.

**Important:** Northbridge Community Health, its operational weaknesses, treatment costs, financial losses, insurance conditions and scenario changes are fictional classroom assumptions. They are not documented facts about the HSE incident.

---

## Risk Assessment

Four principal business risks were identified and prioritised using a qualitative risk assessment methodology.

### Risk Scoring Methodology

Risk Score = Likelihood × Impact

Both likelihood and impact are scored from 1 to 5.

| Score | Risk Classification |
|---|---|
| 1–4 | Low |
| 5–9 | Medium |
| 10–16 | High |
| 17–25 | Critical |

### Initial Risk Register

| Risk ID | Identified Risk | Likelihood | Impact | Score | Classification |
|---|---|---:|---:|---:|---|
| R1 | Healthcare service disruption | 4 | 5 | 20 | Critical |
| R2 | Sensitive patient information exposure | 4 | 5 | 20 | Critical |
| R3 | Unnecessary supplier exposure | 3 | 4 | 12 | High |
| R4 | Delayed incident detection | 4 | 4 | 16 | High |

### Key Risk Considerations

- **R1 – Service Availability:** Ransomware could disrupt patient bookings and essential clinic operations.
- **R2 – Information Confidentiality:** Unauthorised access could expose sensitive patient information.
- **R3 – Supplier Exposure:** An unused supplier workflow creates unnecessary potential access exposure.
- **R4 – Incident Detection:** Unassigned phishing escalation responsibilities could delay incident investigation.

Critical risks were identified as requiring further treatment and could not be accepted under the exercise rules.

---

## Risk Treatment Strategies

Four risk treatment approaches were evaluated.

| Treatment Strategy | Application to Northbridge |
|---|---|
| Avoidance | Retire the unused supplier workflow. |
| Mitigation | Implement MFA, protected backups, restoration testing and phishing awareness. |
| Transfer | Evaluate illustrative cyber insurance for eligible financial losses. |
| Acceptance | Consider conditional, time-limited acceptance of residual risk with formal approval. |

The assessment recognises that outsourcing security services or purchasing insurance does not remove organisational accountability.

---

## Initial Treatment Portfolio

The initial treatment portfolio was developed against a first-year budget of $100,000.

| Option | Treatment | Cost |
|---|---|---:|
| A | Retire unused supplier workflow | $5,000 |
| B | MFA rollout and account access review | $25,000 |
| C | Protected backups, restoration tests and recovery plan | $30,000 |
| E | Targeted awareness training and reporting process | $10,000 |
| G | Illustrative cyber insurance | $20,000 |
| | **Total** | **$90,000** |

**Initial budget summary:**

- Approved budget: $100,000
- Selected treatments: $90,000
- Remaining budget: $10,000

Options D (managed detection) and F (network segmentation) were deferred to prioritise immediate recovery, access protection and awareness requirements.

---

## Insurance and Financial Exposure Analysis

An illustrative insurance policy was evaluated using the following fictional terms:

| Insurance Component | Amount |
|---|---:|
| Annual premium | $20,000 |
| Deductible | $25,000 |
| Maximum insurer payment | $250,000 |

### Insurance Calculation Formula

```text
Insurer Payment =
MIN(MAX(Total Loss - Deductible, 0), Policy Limit)

Retained Loss =
Total Loss - Insurer Payment

Total First-Year Outlay =
Retained Loss + Annual Premium
```

### Financial Scenarios

| Scenario | Covered Loss | Insurer Payment | Retained Loss | Total First-Year Outlay |
|---|---:|---:|---:|---:|
| Scenario 1 | $180,000 | $155,000 | $25,000 | $45,000 |
| Scenario 2 | $400,000 | $250,000 | $150,000 | $170,000 |
| Excluded claim | $180,000 | $0 | $180,000 | $200,000 |
| Excluded claim | $400,000 | $0 | $400,000 | $420,000 |

The calculations demonstrate that insurance does not eliminate financial exposure. Deductibles, policy limits and exclusions can leave substantial losses with the organisation.

---

## Revised Risk Treatment Decisions

### Simulated Change in Circumstances

Following the initial treatment decision, the scenario introduced three changes:

- A backup restoration test failed.
- Clinics could maintain paper-based bookings for only four hours.
- The cost of Option B (MFA and account access review) increased from $25,000 to $35,000.

These changes required management to reassess its original treatment portfolio.

### Revised Treatment Portfolio

| Option | Treatment | Revised Cost |
|---|---|---:|
| A | Retire unused supplier workflow | $5,000 |
| B | MFA rollout and account access review | $35,000 |
| C | Protected backups, restoration tests and recovery plan | $30,000 |
| E | Targeted awareness training and reporting process | $10,000 |
| | **Total** | **$80,000** |

### Revised Budget Summary

| Budget Item | Amount |
|---|---:|
| Total available budget | $100,000 |
| Revised treatment expenditure | $80,000 |
| Remaining budget | $20,000 |

Cyber insurance was deferred to prioritise operational recovery and preventive security controls.

Managed detection and network segmentation also remained deferred, requiring continued management oversight.

### Proposed Residual Risk Register

| Risk ID | Risk | Proposed Residual Likelihood | Impact | Score | Classification |
|---|---|---:|---:|---:|---|
| R1 | Healthcare service disruption | 5 | 5 | 25 | Critical |
| R2 | Sensitive patient information exposure | 4 | 5 | 20 | Critical |
| R3 | Unnecessary supplier exposure | 1 | 4 | 4 | Low |
| R4 | Delayed incident detection | 3 | 4 | 12 | High |

The residual ratings are proposed estimates, not verified control outcomes. In particular, the failed restoration test means recovery effectiveness cannot yet be demonstrated.

---

## 30-Day Risk Treatment Plan

A 30-day implementation plan was developed to guide the revised treatment portfolio.

| Action | Responsible Owner | Target Period | Budget |
|---|---|---|---:|
| Retire unused supplier workflow | IT Manager | Days 1–5 | $5,000 |
| Implement MFA and review accounts | IT Manager | Days 1–10 | $35,000 |
| Improve protected backups and validate restoration | IT Manager / Operations Director | Days 1–15 | $30,000 |
| Deliver phishing awareness training and reporting process | Information Security Manager | Days 5–20 | $10,000 |
| Review control evidence and outstanding risks | Information Security Manager | Days 21–25 | Included |
| Present progress and residual risks to management | Operations Director | Days 26–30 | Included |

The effectiveness of each treatment must be demonstrated through documented testing, verification and management review.

---

## Key Management Recommendations

The assessment recommends that Northbridge Community Health:

1. Prioritise successful backup restoration and recovery readiness.
2. Strengthen identity and access management through MFA.
3. Remove unnecessary supplier access and workflows.
4. Establish clear phishing reporting and escalation responsibilities.
5. Maintain board oversight of critical and high residual risks.
6. Review insurance coverage and exclusions before reconsidering financial risk transfer.
7. Strengthen business continuity arrangements for all three clinics.

The organisation should not treat the purchase or implementation of a security control as proof of effectiveness.

---

## Deliverables and Evidence

The practical assessment produces the following evidence:

| Deliverable | Description |
|---|---|
| Initial Risk Register | Identification and prioritisation of four ransomware-related business risks |
| Treatment Selection Table | Initial treatment options, justification and budget allocation |
| Insurance Calculations | Deductible, insurer payment, retained loss and premium calculations |
| Initial Decision Record | Original treatment portfolio and acceptance considerations |
| Revised Decision Record | Updated portfolio following the scenario changes |
| Revised Risk Register | Proposed residual risk ratings |
| 30-Day Treatment Plan | Actions, owners, costs, target dates and effectiveness tests |
| Board Memo | Management decisions, budget request and unresolved risks |

---

## Skills Demonstrated

- Cybersecurity Governance, Risk and Compliance (GRC)
- Enterprise Risk Assessment
- Ransomware Risk Analysis
- Risk Treatment and Risk Acceptance
- Risk Register Development
- Business Impact Analysis
- Business Continuity and Disaster Recovery
- Third-Party and Supplier Risk
- Identity and Access Management (IAM)
- Multi-Factor Authentication (MFA)
- Cyber Insurance and Financial Risk Analysis
- Residual Risk Assessment
- Security Governance and Board Reporting
- Risk-Based Decision-Making

---

## Frameworks and References

The assessment draws on risk management and information security principles, including:

- ISO 31000:2018 – Risk Management Guidelines.
- ISO/IEC 27001:2022 – Information Security Management Systems.
- Health Service Executive – Official 2021 Cyber-attack Account.

### References

Health Service Executive. (n.d.). *Cyber-attack and HSE response*. https://www2.hse.ie/services/cyber-attack/what-happened/

International Organization for Standardization. (2018). *ISO 31000:2018 Risk management – Guidelines*. https://www.iso.org/standard/65694.html

International Organization for Standardization. (2022). *ISO/IEC 27001:2022 Information security management systems – Requirements*. https://www.iso.org/standard/27001

---

## Disclaimer

This project was completed as an academic case analysis under the ICDFA GRC103 Module 3 Risk Treatment Strategies practical assessment.

Northbridge Community Health is fictional. All organisational details, risk scenarios, treatment costs, insurance terms, financial losses and management changes are illustrative classroom assumptions.

The project does not represent an actual security assessment, insurance purchase or engagement with the Health Service Executive.

---

## Author

**Cybersecurity GRC | GRC Engineering in Training**

Interested in cybersecurity governance, risk management, compliance, AI governance and security engineering.

**Open for collaboration.**
