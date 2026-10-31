# Quantitative Cybersecurity Risk Assessment Report

## SecureBank Financial — SecureMobile Banking Platform

| Document control | Details |
|---|---|
| **Prepared by** | Lead GRC Analyst |
| **Prepared for** | Chief Information Security Officer (CISO) and Chief Financial Officer (CFO) |
| **Assessment purpose** | Quantify financial risk, evaluate proposed controls, and recommend risk treatments |
| **Evaluation period** | Three years |
| **Version** | 1.0 |
| **Classification** | Internal — Academic Case Study |

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Introduction](#2-introduction)
3. [Assessment Objectives and Scope](#3-assessment-objectives-and-scope)
4. [System Context and Assessment Data](#4-system-context-and-assessment-data)
5. [Methodology and Modelling Assumptions](#5-methodology-and-modelling-assumptions)
6. [Phase 1: Risk Exposure Calculation](#6-phase-1-risk-exposure-calculation)
7. [Phase 2: Security Control Evaluation](#7-phase-2-security-control-evaluation)
8. [Phase 3: Executive Dashboard and Reporting](#8-phase-3-executive-dashboard-and-reporting)
9. [Risk Treatment Plan and Implementation Timeline](#9-risk-treatment-plan-and-implementation-timeline)
10. [Monitoring, Measurement and Assurance](#10-monitoring-measurement-and-assurance)
11. [Limitations and Key Assumptions](#11-limitations-and-key-assumptions)
12. [Conclusion and Management Recommendations](#12-conclusion-and-management-recommendations)
13. [References](#13-references)
    

---

## 1. Executive Summary

### 1.1 Overview

SecureBank Financial's SecureMobile banking platform was assessed following a penetration test and vulnerability assessment that identified three security weaknesses: API authentication bypass, database injection, and session hijacking. These weaknesses may affect the confidentiality, integrity, and availability of banking services, customer information, and financial transactions.

SecureMobile supports **500,000 active customers** and processes approximately **50,000 transactions per day**, with an average transaction value of **$2,500**. Indicative daily transaction throughput is therefore:

`50,000 × $2,500 = $125,000,000`

This is transaction value processed, not the amount necessarily lost in an incident.

The assessment estimates financial exposure, prioritises risks, evaluates three proposed controls, and recommends risk treatment. Calculations use the quantitative formulas provided in the supplied study guide.

### 1.2 Key Findings

The combined modelled annual loss exposure is **$35,000,000** under the assumptions in this report. Database injection is the largest contributor, with a modelled ALE of $31,250,000. Session hijacking has the highest supplied exploit probability (40%) and a modelled ALE of $3,000,000. API authentication bypass has a modelled ALE of $750,000 but could still cause material harm through unauthorised transfers.

| Vulnerability | SLE | Assumed annual probability / ARO proxy | Modelled ALE | Priority |
|---|---:|---:|---:|---|
| API authentication bypass | $5,000,000 | 15% / 0.15 | $750,000 | High |
| Database injection | $125,000,000 | 25% / 0.25 | $31,250,000 | Critical |
| Session hijacking | $7,500,000 | 40% / 0.40 | $3,000,000 | High |
| **Total** | — | — | **$35,000,000** | — |

The supplied probabilities have no specified time period. They are treated as annual occurrence-rate proxies for this laboratory exercise, not as verified incident frequencies or forecasts.

### 1.3 Proposed Security Investment

| Proposed control | Initial investment | Annual maintenance | Modelled annual risk reduction | Residual ALE |
|---|---:|---:|---:|---:|
| Advanced API Security Gateway | $350,000 | $50,000 | $675,000 | $75,000 |
| Web Application Firewall (WAF) | $150,000 | $25,000 | $23,437,500 | $7,812,500 |
| MFA enhancement | $200,000 | $30,000 | $2,850,000 | $150,000 |
| **Total** | **$700,000** | **$105,000** | **$26,962,500** | **$8,037,500** |

If all three controls achieve their assumed effectiveness against their assigned scenarios, the model estimates a **77.04%** reduction in annual loss exposure.

### 1.4 Financial Evaluation

Over three years, the combined lifecycle cost is **$1,015,000**: $700,000 initial investment plus $315,000 maintenance. Gross modelled loss avoided is $80,887,500, and net modelled benefit is $79,872,500. The resulting portfolio ROI is approximately **7,869.2%**.

These figures are expected-loss estimates, not guaranteed cash savings. The unusually high WAF ROI depends heavily on the assumed $125 million database-injection loss and the assumed application of WAF effectiveness to that scenario. Both must be validated before real budget approval.

### 1.5 Executive Recommendation

Prioritise direct remediation of database injection, supported by WAF deployment. Address API authentication and session-management weaknesses through the API Security Gateway and MFA enhancement, respectively. Proceed with staged deployment, technical testing, documented ownership, and ongoing residual-risk monitoring. Validate financial assumptions and control applicability before relying on the modelled benefits.

---

## 2. Introduction

Cybersecurity vulnerabilities can cause financial loss, regulatory exposure, operational disruption, and loss of customer trust. For a banking platform, authentication, authorisation, database security, and session management are essential because the application processes transactions and sensitive customer information.

Qualitative ratings communicate relative severity. Quantitative risk analysis adds a financial perspective by estimating loss from a single event and applying an assumed occurrence rate to estimate annualised exposure. NIST SP 800-30 provides guidance for information security risk assessments and risk-treatment decisions (NIST, 2012).

This report applies a simplified quantitative method to the supplied SecureBank laboratory scenario and evaluates proposed controls using the formulas in the supplied study guide.

### 2.1 Background

The assessment considers:

- **API authentication bypass:** could enable unauthorised fund transfers.
- **Database injection:** could expose or alter customer and financial information.
- **Session hijacking:** could enable account takeover and unauthorised transactions.

### 2.2 Purpose

The report aims to:

- Calculate SLE and ALE for each vulnerability.
- Prioritise risks by financial exposure and business consequence.
- Evaluate proposed controls, costs, and stated effectiveness.
- Calculate modelled risk reduction and residual risk.
- Calculate three-year ROI and estimated payback.
- Provide executive dashboard metrics and chart-ready data.
- Recommend phased treatment actions, owners, and measures.

---

## 3. Assessment Objectives and Scope

### 3.1 Objectives

The assessment estimates the financial consequences of the identified weaknesses, evaluates proposed security investments, and supports treatment prioritisation. It also identifies residual risks and recommends actions for immediate, short-term, and long-term risk management.

### 3.2 In Scope

| Area | Assessment coverage |
|---|---|
| API security | Authentication bypass and unauthorised transaction processing |
| Database security | Injection, potential data exposure, and customer-record impact |
| Session security | Session hijacking and account takeover |
| Financial exposure | Single-event loss, ALE, and expected risk reduction |
| Security controls | API Security Gateway, WAF, and MFA enhancement |
| Investment analysis | Initial implementation, maintenance, ROI, and payback |
| Executive reporting | Risk prioritisation, residual risk, and treatment timeline |

### 3.3 Out of Scope

The supplied scenario does not provide enough data to quantify actual historical fraud or incident frequency, verified past losses, incident response/legal/forensic costs, business interruption, insurance recoveries, customer attrition, reputational loss, independently tested control effectiveness, or a formal budget ceiling. These items are not invented or added to the model.

---

## 4. System Context and Assessment Data

### 4.1 System Context

| Attribute | Supplied value |
|---|---:|
| Active customers | 500,000 |
| Average transaction value | $2,500 |
| Daily transactions | 50,000 |
| Indicative daily transaction throughput | $125,000,000 |
| Currency | USD |

Daily throughput is calculated as `50,000 × $2,500`. It indicates the approximate transaction value processed each day and is not an expected loss amount.

### 4.2 Vulnerability Assessment Data

| Vulnerability | Supplied exploit probability | Potential impact | Financial input |
|---|---:|---|---|
| API authentication bypass | 15% | Unauthorised fund transfers | Maximum single-incident loss: $5,000,000 |
| Database injection | 25% | Exposure of personal and financial information | 500,000 records × $250 per record |
| Session hijacking | 40% | Account takeover | 5,000 accounts/sessions × $1,500 average loss |

### 4.3 Proposed Security Controls

| Control | Initial cost | Stated effectiveness | Annual maintenance |
|---|---:|---:|---:|
| Advanced API Security Gateway | $350,000 | 90% reduction in API vulnerabilities | $50,000 |
| Web Application Firewall (WAF) | $150,000 | 75% reduction in web vulnerabilities | $25,000 |
| MFA enhancement | $200,000 | 95% reduction in account takeover | $30,000 |


---

## 5. Methodology and Modelling Assumptions

### 5.1 Quantitative Risk Method

- **Single Loss Expectancy (SLE):** estimated financial loss from one successful incident.
- **Annual Rate of Occurrence (ARO):** expected number of incidents per year.
- **Annualised Loss Expectancy (ALE):** `SLE × ARO`.
- **Residual risk:** modelled risk remaining after a control is applied.
- **Risk reduction:** current ALE minus residual ALE.
- **ROI:** percentage return comparing modelled benefit with relevant cost.
- **Payback period:** estimated time for modelled annual net benefit to recover initial investment.

### 5.2 Probability and ARO Assumption

The supplied probabilities (15%, 25%, 40%) do not specify a time period. For this exercise, they are interpreted as assumed annual probabilities and used as ARO proxies:

| Scenario | Probability | ARO proxy |
|---|---:|---:|
| API authentication bypass | 15% | 0.15 |
| Database injection | 25% | 0.25 |
| Session hijacking | 40% | 0.40 |

### 5.3 Control Mapping Assumptions

| Control | Assigned primary scenario | Effectiveness applied |
|---|---|---:|
| Advanced API Security Gateway | API authentication bypass | 90% |
| WAF | Database injection | 75% |
| MFA enhancement | Session hijacking/account takeover | 95% |

Each control is assigned to one primary scenario to avoid double-counting benefits. The mapping requires validation: WAF protection depends on rules and architecture and does not replace parameterised queries; an API gateway does not replace application-level authorisation; MFA does not necessarily stop reuse of a stolen active session token.

### 5.4 Financial Evaluation Assumptions

- Evaluation period: three years.
- Initial investment is paid once at implementation.
- Annual maintenance is incurred in each of the three years.
- Annual risk reduction remains constant.
- Three-year gross benefit equals annual risk reduction multiplied by three.
- Lifecycle cost equals initial investment plus three years of maintenance.
- Future benefits are not discounted.
- Inflation, tax, insurance recoveries, and changes in exposure are excluded.
- No budget cap was supplied; the base case evaluates all three controls together.

### 5.5 Risk Priority Method

Financial exposure is the principal prioritisation measure, supplemented by likelihood, operational impact, and data sensitivity. For this exercise, Critical is ALE of $10 million or more; High is $1 million to below $10 million or a significant weakness requiring timely treatment; Medium is below $1 million unless other factors justify a higher rating. These are scenario-specific thresholds, not universal standards.

---

## 6. Phase 1: Risk Exposure Calculation

### 6.1 Single Loss Expectancy (SLE)

SLE estimates the financial impact of one successful incident.

#### API Authentication Bypass

The supplied maximum single-incident loss is $5,000,000.

`SLE_API = $5,000,000`

#### Database Injection

Assuming all 500,000 records are affected at $250 per record:

`SLE_DB = 500,000 × $250 = $125,000,000`


#### Session Hijacking

Assuming 5,000 accounts/sessions are affected at $1,500 average loss per account:

`SLE_Session = 5,000 × $1,500 = $7,500,000`

### 6.2 Annual Rate of Occurrence (ARO)

The supplied probabilities are used as annual ARO proxies: 0.15, 0.25, and 0.40 respectively. 

### 6.3 Annualised Loss Expectancy (ALE)

Formula:

`ALE = SLE × ARO`

| Vulnerability | SLE | ARO proxy | Calculation | ALE |
|---|---:|---:|---|---:|
| API authentication bypass | $5,000,000 | 0.15 | $5,000,000 × 0.15 | $750,000 |
| Database injection | $125,000,000 | 0.25 | $125,000,000 × 0.25 | $31,250,000 |
| Session hijacking | $7,500,000 | 0.40 | $7,500,000 × 0.40 | $3,000,000 |
| **Total** | — | — | Sum of scenario ALEs | **$35,000,000** |

### 6.4 Risk Prioritisation

| Rank | Vulnerability | ARO proxy | SLE | ALE | Priority | Business justification |
|---:|---|---:|---:|---:|---|---|
| 1 | Database injection | 0.25 | $125,000,000 | $31,250,000 | Critical | Largest modelled exposure; potential compromise of customer and financial data |
| 2 | Session hijacking | 0.40 | $7,500,000 | $3,000,000 | High | Highest supplied probability; potential account takeover |
| 3 | API authentication bypass | 0.15 | $5,000,000 | $750,000 | High | Unauthorised transfers threaten transaction integrity and customer funds |

Although API authentication bypass has the lowest ALE, its direct impact on banking transactions warrants prompt treatment.

### 6.5 Risk Heat Map

Assessment bands:

| Category | Low | Medium | High |
|---|---|---|---|
| Likelihood | Below 10% | 10% to below 30% | 30% or above |
| Single-event impact | Below $5M | $5M to below $20M | $20M or above |

| Vulnerability | Likelihood | Impact | Heat-map rating |
|---|---|---|---|
| API authentication bypass | Medium | Medium | Medium |
| Database injection | Medium | High | High |
| Session hijacking | High | Medium | High |

The heat map and financial priority table serve different purposes. The heat map combines likelihood and event impact; the priority table also considers modelled annual financial exposure.

### 6.6 Risk Distribution

Risk share is calculated as `Scenario ALE ÷ Total ALE × 100`.

| Vulnerability | ALE | Share of total ALE |
|---|---:|---:|
| API authentication bypass | $750,000 | 2.14% |
| Database injection | $31,250,000 | 89.29% |
| Session hijacking | $3,000,000 | 8.57% |
| **Total** | **$35,000,000** | **100.00%** |

---

## 7. Phase 2: Security Control Evaluation

### 7.1 Calculation Method

For this exercise, current risk is represented by the assigned scenario ALE.

`Residual ALE = Current ALE × (1 − Control Effectiveness)`

`Risk Reduction = Current ALE − Residual ALE`

Effectiveness percentages are converted to decimals before calculation.

### 7.2 Advanced API Security Gateway

- Initial investment: $350,000
- Annual maintenance: $50,000
- Stated effectiveness: 90%
- Assigned scenario ALE: $750,000

`Residual ALE = $750,000 × (1 − 0.90) = $75,000`

`Annual risk reduction = $750,000 − $75,000 = $675,000`

The gateway may provide authentication enforcement, request validation, rate limiting, transaction monitoring, and central logging. Validate the control through testing and ensure it does not become a single point of failure. Complement it with server-side authorisation, transaction ownership and amount validation, and suspicious-transaction alerting.

### 7.3 Web Application Firewall (WAF)

- Initial investment: $150,000
- Annual maintenance: $25,000
- Stated effectiveness: 75%
- Assigned scenario ALE: $31,250,000

`Residual ALE = $31,250,000 × (1 − 0.75) = $7,812,500`

`Annual risk reduction = $31,250,000 − $7,812,500 = $23,437,500`


### 7.4 MFA Enhancement

- Initial investment: $200,000
- Annual maintenance: $30,000
- Stated effectiveness: 95%
- Assigned scenario ALE: $3,000,000

`Residual ALE = $3,000,000 × (1 − 0.95) = $150,000`

`Annual risk reduction = $3,000,000 − $150,000 = $2,850,000`

MFA should be supported by secure session-token generation and storage, session rotation, appropriate idle and absolute timeouts, suspicious-session revocation, and reauthentication for sensitive actions. Theft or disclosure of a valid session identifier may permit impersonation (OWASP Foundation, n.d.-b).

### 7.5 Combined Residual Risk

| Vulnerability | Current ALE | Control | Modelled reduction | Residual ALE |
|---|---:|---|---:|---:|
| API authentication bypass | $750,000 | API Security Gateway | $675,000 | $75,000 |
| Database injection | $31,250,000 | WAF | $23,437,500 | $7,812,500 |
| Session hijacking | $3,000,000 | MFA enhancement | $2,850,000 | $150,000 |
| **Total** | **$35,000,000** | **Three assigned controls** | **$26,962,500** | **$8,037,500** |

`Percentage reduction = $26,962,500 ÷ $35,000,000 × 100 = 77.04%`

This portfolio assumes scenario losses are additive and control benefits do not overlap. Reassess if a single incident could create losses across multiple scenarios.

### 7.6 Investment Breakdown

| Control | Initial investment | Annual maintenance | Three-year maintenance | Three-year lifecycle cost |
|---|---:|---:|---:|---:|
| Advanced API Security Gateway | $350,000 | $50,000 | $150,000 | $500,000 |
| WAF | $150,000 | $25,000 | $75,000 | $225,000 |
| MFA enhancement | $200,000 | $30,000 | $90,000 | $290,000 |
| **Total** | **$700,000** | **$105,000/year** | **$315,000** | **$1,015,000** |

### 7.7 Return on Investment (ROI)

For consistent comparison, the report uses a three-year evaluation period.

`Three-year gross benefit = Annual risk reduction × 3`

`Three-year lifecycle cost = Initial investment + (Annual maintenance × 3)`

`ROI = (Gross benefit − Lifecycle cost) ÷ Lifecycle cost × 100`

| Control | Annual risk reduction | Three-year gross benefit | Three-year cost | Net modelled benefit | ROI |
|---|---:|---:|---:|---:|---:|
| API Security Gateway | $675,000 | $2,025,000 | $500,000 | $1,525,000 | 305.0% |
| WAF | $23,437,500 | $70,312,500 | $225,000 | $70,087,500 | 31,150.0% |
| MFA enhancement | $2,850,000 | $8,550,000 | $290,000 | $8,260,000 | 2,848.3% |
| **Combined portfolio** | **$26,962,500** | **$80,887,500** | **$1,015,000** | **$79,872,500** | **7,869.2%** |


### 7.8 Payback Period

`Payback (months) = Initial investment ÷ (Annual risk reduction − Annual maintenance) × 12`

| Control | Initial investment | Annual risk reduction | Annual maintenance | Annual net modelled benefit | Estimated payback |
|---|---:|---:|---:|---:|---:|
| API Security Gateway | $350,000 | $675,000 | $50,000 | $625,000 | 6.72 months |
| WAF | $150,000 | $23,437,500 | $25,000 | $23,412,500 | 0.08 months |
| MFA enhancement | $200,000 | $2,850,000 | $30,000 | $2,820,000 | 0.85 months |

The WAF payback estimate is less than one day under the simplified model and must not be interpreted as a guaranteed real-world cost recovery period.

### 7.9 Control Selection

The base-case model evaluates all three controls because no budget cap was supplied and each addresses a different primary risk. Before approval, validate costs, dependencies, operational impacts, and technical effectiveness. 

---

## 8. Phase 3: Executive Dashboard and Reporting

### 8.1 Executive Dashboard

| Metric | Current model | After proposed controls |
|---|---:|---:|
| Total annual loss exposure | $35,000,000 | $8,037,500 |
| Annual modelled risk reduction | — | $26,962,500 |
| Percentage reduction | — | 77.04% |
| Initial control investment | — | $700,000 |
| Annual maintenance | — | $105,000 |
| Three-year lifecycle cost | — | $1,015,000 |
| Three-year gross modelled benefit | — | $80,887,500 |
| Three-year net modelled benefit | — | $79,872,500 |
| Three-year portfolio ROI | — | 7,869.2% |
| Highest financial priority | Database injection | Database injection remains the largest residual ALE |

### 8.2 Current Versus Residual ALE

| Vulnerability | Current ALE | Residual ALE |
|---|---:|---:|
| API authentication bypass | $750,000 | $75,000 |
| Database injection | $31,250,000 | $7,812,500 |
| Session hijacking | $3,000,000 | $150,000 |
| **Total** | **$35,000,000** | **$8,037,500** |

### 8.3 Cumulative Gross Modelled Risk Reduction

| Evaluation year | API Gateway | WAF | MFA | Cumulative portfolio benefit |
|---|---:|---:|---:|---:|
| Year 1 | $675,000 | $23,437,500 | $2,850,000 | $26,962,500 |
| Year 2 | $1,350,000 | $46,875,000 | $5,700,000 | $53,925,000 |
| Year 3 | $2,025,000 | $70,312,500 | $8,550,000 | $80,887,500 |


---

## 9. Risk Treatment Plan and Implementation Timeline

### 9.1 Immediate Actions: Days 0–30

| Action | Risk | Suggested owner | Target | Evidence |
|---|---|---|---|---|
| Validate affected-record count and $250 cost-per-record assumption | Database injection | GRC and Data Protection | Day 10 | Documented assumptions and revised impact estimate |
| Review and remediate unsafe database queries | Database injection | Application Development | Day 30 | Code review and testing evidence |
| Apply least-privilege database permissions | Database injection | Database Administrator | Day 30 | Permission review and approved access matrix |
| Review API authentication and authorisation paths | API bypass | API Engineering and Security | Day 15 | Test results and remediation record |
| Review session lifecycle and token handling | Session hijacking | Application Security | Day 30 | Session review and test cases |
| Establish monitoring and escalation criteria | All scenarios | Security Operations | Day 30 | Alert rules and escalation procedure |

**Expected outcome:** Reduce immediate exposure through direct remediation, temporary safeguards, and improved visibility.

### 9.2 Short-Term Actions: Days 31–90

| Action | Risk | Suggested owner | Target | Evidence |
|---|---|---|---|---|
| Deploy and configure WAF | Web attacks / injection attempts | Infrastructure Security | Day 60 | Configuration review and test results |
| Implement API Security Gateway | API authentication bypass | API Engineering | Day 75 | Authentication, authorisation, and rate-limit tests |
| Deploy MFA enhancements | Account takeover | IAM Team | Day 75 | Authentication test results and adoption metrics |
| Integrate security logs with monitoring | All scenarios | Security Operations | Day 90 | Verified alerting and escalation |
| Retest all three vulnerabilities | All scenarios | Independent Security Tester | Day 90 | Retest report |
| Recalculate residual risk | All scenarios | GRC Analyst | Day 90 | Updated risk register |

**Expected outcome:** Controls are implemented and tested, findings are retested, and residual risk is updated using evidence.

### 9.3 Long-Term Actions: Days 91–365

| Action | Suggested owner | Target / frequency | Success measure |
|---|---|---|---|
| Recurring vulnerability assessments | Vulnerability Management | Quarterly | Findings tracked through closure |
| Periodic penetration testing | Independent Security Tester | At least annually | Retest and remediation evidence |
| Review control effectiveness | GRC and Security Engineering | Quarterly | Documented effectiveness review |
| Incident-response exercises | Security Operations | Within 6 months | Exercise report and tracked actions |
| Review access and privileged accounts | IAM and System Owners | Quarterly | Access reviews completed |
| Refresh quantitative risk estimates | GRC and Finance | Quarterly or after significant events | Updated ALE and assumptions |
| Report risk trends to management | GRC Analyst | Quarterly | Dashboard submitted to CISO and CFO |

### 9.4 Illustrative Timeline

| Activity | Days 0–30 | Days 31–60 | Days 61–90 | Months 4–6 | Months 7–12 |
|---|---|---|---|---|---|
| Validate financial assumptions | Validate | Review | Review | — | — |
| Remediate database injection | Remediate | Continue | Retest | Monitor | Retest |
| Review API authentication | Review | Remediate | Retest | Monitor | Retest |
| Review session management | Review | Remediate | Retest | Monitor | Retest |
| Deploy WAF | Plan | Deploy | Tune and test | Monitor | Review |
| Deploy API Security Gateway | Plan | Deploy | Test and tune | Monitor | Review |
| Deploy MFA enhancement | Plan | Deploy | Test and tune | Monitor | Review |
| Recalculate residual risk | Baseline | — | Update | Update | Update |
| Report to CISO and CFO | Initial | Progress | Review | Quarterly | Annual review |

---

## 10. Monitoring, Measurement and Assurance

### 10.1 Key Risk Indicators

| Metric | Purpose | Frequency |
|---|---|---|
| Confirmed API authentication bypass findings | Track recurrence | Monthly and after major releases |
| Unresolved database injection findings | Track remediation | Monthly |
| Confirmed session hijacking incidents | Monitor account/session compromise | Monthly |
| Critical findings resolved within SLA | Measure remediation timeliness | Monthly |
| WAF rule effectiveness and false-positive rate | Check defensive value and service impact | Monthly |
| API gateway authentication/authorisation test results | Verify transaction endpoint protection | After changes and quarterly |
| MFA coverage for in-scope users | Measure deployment and adoption | Monthly |
| Compromised sessions revoked within target | Measure response effectiveness | Monthly |
| Actual financial losses from relevant incidents | Improve loss estimates | Quarterly |
| Residual ALE and treatment status | Support management oversight | Quarterly |


### 10.2 Management Reporting

Quarterly reporting to the CISO and CFO should include current and residual ALE, high-priority vulnerability status, control implementation and maintenance costs, actual test results, incidents and losses, overdue treatment actions, changed assumptions, and decisions required.

---

## 11. Limitations and Key Assumptions

### 11.1 Probability and ARO

Input probabilities do not specify a time period. Their use as annual ARO proxies is an explicit exercise assumption. A real assessment must establish the relevant time horizon and derive occurrence estimates from evidence.

### 11.2 Financial Impact

- Database-injection SLE assumes all 500,000 records are affected at $250 per record.
- Session-hijacking SLE assumes all 5,000 accounts/sessions incur the stated average loss.
- API SLE uses the supplied maximum single-incident loss of $5,000,000.
- Actual losses may differ due to affected population, recovery, reimbursement, response costs, and incident circumstances.

### 11.3 Control Effectiveness

Effectiveness values are supplied inputs and have not been verified. Actual protection depends on deployment, configuration, architecture, and attack path. WAF does not replace secure query construction; an API gateway does not replace server-side authorisation; MFA does not necessarily prevent reuse of a hijacked active session. Overlapping benefits must be assessed to avoid double-counting.

### 11.4 ROI and Payback

ROI is based on expected loss avoidance, not guaranteed savings. The model assumes constant annual risk reduction and excludes discounting, inflation, and changes in exposure. Payback assumes benefits accrue evenly through the year. The WAF's very short modelled payback is particularly assumption-sensitive.

### 11.5 Budget and Implementation

No formal budget, procurement timeline, staffing allocation, or implementation dependency data was supplied. A real decision should include project costs, operational impact, integration effort, testing, training, vendor terms, and support requirements.

---

## 12. Conclusion and Management Recommendations

### 12.1 Conclusion

This assessment demonstrates how technical vulnerabilities can be translated into financial estimates to support security investment decisions. Under the stated assumptions, combined annual loss exposure is $35,000,000. Database injection is the highest financial priority at $31,250,000 ALE; session hijacking is $3,000,000 ALE; and API authentication bypass is $750,000 ALE.

The proposed controls require $700,000 initial investment and $105,000 annual maintenance. Their combined three-year lifecycle cost is $1,015,000. If stated effectiveness is achieved against assigned scenarios, modelled annual risk reduction is $26,962,500 and residual annual exposure is $8,037,500.

The 7,869.2% portfolio ROI is a scenario-based expected-loss calculation, not a guaranteed return. It is especially sensitive to the database-injection loss assumption and WAF mapping.

### 12.2 Recommendations to the CISO

- Prioritise direct database-injection remediation using parameterised queries, safe input handling, least-privilege access, and retesting.
- Review API authentication and authorisation, especially fund-transfer and sensitive transaction controls.
- Strengthen session management alongside MFA, including secure token handling, timeouts, revocation, and suspicious-activity detection.
- Validate control effectiveness through technical testing.
- Require evidence of remediation before accepting residual-risk estimates.
- Assign accountable owners and monitor treatment through a risk register and quarterly reporting.

### 12.3 Recommendations to the CFO

- Review the proposed $700,000 initial investment and $105,000 annual maintenance.
- Treat ROI and payback as model outputs based on expected loss avoidance.
- Validate the $250 per-record cost and assumption that all 500,000 records could be affected.
- Confirm proposed controls address the relevant vulnerabilities.
- Monitor implementation expenditure against the approved budget.
- Review revised estimates when incident data, validated loss assumptions, or control test results become available.

### 12.4 Management Decision Requested

Approve progression into a structured risk-treatment programme, subject to financial validation and technical verification. Prioritise database-injection remediation and supporting WAF deployment, while progressing the API Security Gateway and MFA enhancement in parallel according to dependencies. Do not rely on modelled control reductions until validated through testing. Document residual risks and obtain appropriate risk-owner approval.

---

## 13. References

National Institute of Standards and Technology. (2012). *Guide for conducting risk assessments* (NIST Special Publication 800-30, Revision 1). U.S. Department of Commerce. https://doi.org/10.6028/NIST.SP.800-30r1

OWASP Foundation. (n.d.-a). *SQL injection prevention cheat sheet*. OWASP Cheat Sheet Series. https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html

OWASP Foundation. (n.d.-b). *Session management cheat sheet*. OWASP Cheat Sheet Series. https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html

OWASP Foundation. (n.d.-c). *OWASP API Security Project*. https://owasp.org/projects/api-security-project

*Lab 3b: Advanced Cybersecurity Risk Quantification — SecureBank Financial SecureMobile Banking Platform Assessment*. (n.d.). Laboratory scenario and assessment brief supplied for the exercise.

*Study Guide: Quantitative Risk Calculations for GRC Professionals*. (n.d.). Course learning material supplied for the exercise.

---
## AI Tool Usage

**AI Tool Used:** ChatGPT (OpenAI)

ChatGPT was used to assist with structuring and refining the assessment report, organising quantitative risk calculations, and improving the clarity and presentation of the documentation. The assessment inputs, assumptions, and final conclusions were reviewed by the author.
