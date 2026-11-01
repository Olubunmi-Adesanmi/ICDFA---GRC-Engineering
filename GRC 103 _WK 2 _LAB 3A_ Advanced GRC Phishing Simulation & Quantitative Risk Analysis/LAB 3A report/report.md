# Lab 3: Advanced GRC Phishing Simulation & Quantitative Risk Analysis

**Organisation:** GlobalTech Inc.  
**Prepared for:** Board of Directors, Chief Information Security Officer (CISO), and Chief Financial Officer (CFO)  
**Prepared by:** GRC Risk Analysis Team  
**Report date:** 31 October 2026  
**Classification:** Internal   
**Currency:** United States dollars (USD)

---
## Table of Contents

## Table of Contents

- [Executive Summary](#executive-summary)
- [1. Introduction and Assessment Objectives](#1-introduction-and-assessment-objectives)
- [2. Scope, Source Data and Methodology](#2-scope-source-data-and-methodology)
- [3. Phase 1 – Basic Phishing Metrics](#3-phase-1---basic-phishing-metrics)
- [4. Phase 2 – Advanced Risk Quantification](#4-phase-2---advanced-risk-quantification)
- [5. Phase 3 – Comprehensive Risk Assessment](#5-phase-3---comprehensive-risk-assessment)
- [6. Phase 4 – Executive Briefing and Control Economics](#6-phase-4---executive-briefing-and-control-economics)
- [7. Strategic Recommendations](#7-strategic-recommendations-and-implementation-roadmap)
- [8. Limitations and Assumptions](#8-limitations-assumptions-and-corrections-to-the-supplied-brief)
- [9. Conclusion](#9-conclusion)
- [Appendices and References](#appendix-a---formula-reference)
- [AI Usage Declaration](#ai-usage-declaration)
- 
## Executive summary

GlobalTech Inc. conducted three phishing simulations during the previous quarter involving 430 email sends across general employee and executive/assistant target groups. Across the three campaigns, 354 messages were opened, 257 links were clicked, 105 credential submissions were recorded, and 38 participants entered additional personal information. The weighted credential-submission rate was **24.42%** (105/430). Campaign B, **IT System Password Reset**, had the highest credential-submission rate at **30%**, followed by Campaign A at **18%** and Campaign C at **15%**.

When Campaign B's credential rate is projected across 2,000 employees, the lab's prescribed model estimates 600 employees could submit credentials. Applying the scenario's 25% conditional breach probability produces 150 **expected breach-equivalent outcomes**. At the assumed $4.35 million loss per breach, the resulting modelled exposure is **$652.5 million**. This is a scenario-based estimate, not a verified annual loss forecast: it assumes each account-level outcome creates a separate breach costing $4.35 million, and it treats the projected count as an annual occurrence frequency. Those assumptions require validation before the figure is used as a real budget forecast.

The control calculations indicate potentially material economic value under the lab assumptions. Enterprise MFA costs $90,000 and, at the assumed 99.9% effectiveness, reduces modelled exposure by $651.8475 million; the corresponding ROI is 724,175%. Targeted security training costs $100,000 and, if it reduces Campaign B's click-through rate by 60% while the post-click credential conversion remains unchanged, reduces the modelled exposure by $391.5 million; the corresponding ROI is 391,400%. Email filtering is modelled with an assumed 20% ALE reduction because no direct filtering effectiveness value was supplied; its calculated ROI is 260,900%.

These very high ROI values are mathematically consistent with the lab's large projected loss baseline, but they should not be interpreted as reliable real-world returns until the loss model, annual frequency, control effectiveness, implementation costs, and overlap between controls are validated. The recommended decision is to prioritise phishing-resistant MFA, targeted training, email protection, and repeat measurement, while establishing a defensible loss-event model before presenting the $652.5 million figure as an annual forecast.

### Key quantitative findings

| Risk metric | Calculated value | Comparator supplied in the brief | Severity in the brief |
|---|---:|---:|---|
| Overall credential-submission rate | **24.42%** | 15.3% | High |
| Maximum campaign credential rate | **30%** | 18.7% | Critical |
| Campaign B modelled ALE | **$652.5M** | $285M | Severe |
| MFA stand-alone ROI | **724,175%** | 350% | Excellent |

The comparator figures above are reproduced from the lab brief only. They have no accompanying source, date, sector, or metric definition and are not independently verified; they should be treated as illustrative training inputs.

### Executive decision points

1. **Prioritise Campaign B risk:** approve an enterprise MFA rollout, beginning with privileged, finance, HR, and high-risk users, with a funded path to organisation-wide coverage.
2. **Reduce human susceptibility:** deliver role-based training and repeat simulations, with particular attention to the password-reset lure and executive-targeted scenarios.
3. **Improve email-layer prevention:** assess and tune the secure email gateway, URL protection, attachment sandboxing, and reporting controls.
4. **Validate the financial model:** distinguish compromised accounts from distinct breach incidents, and replace the assumed 150 annual events with a defensible annual frequency estimate.
5. **Measure outcomes:** report credential submissions, reporting rates, repeat susceptibility, MFA coverage, and verified incidents quarterly.

---

## 1. Introduction and assessment objectives

Phishing is a human-centred attack technique that attempts to persuade users to open messages, visit malicious links, disclose credentials, or provide other sensitive information. For a GRC function, simulation results are useful evidence for identifying human-related vulnerabilities, evaluating control performance, prioritising treatment, and communicating business exposure.

This assessment converts the three supplied simulations into measurable rates, projects the results to the stated workforce, applies the lab's financial assumptions, assesses statistical uncertainty, and evaluates the proposed security investments.

### Objectives

- Calculate fundamental phishing rates and attack-stage conversion metrics.
- Project the observed credential-submission rates across the 2,000-person workforce.
- Estimate scenario-based loss exposure using the supplied $4.35 million breach cost and 25% conditional probability.
- Assess campaign priority and the uncertainty of the sample estimates.
- Calculate stand-alone control benefits, net benefits, ROI, and portfolio break-even.
- Provide executive recommendations and explain assumptions that need validation.

## 2. Scope, source data, and methodology

### 2.1 Scope

The assessment covers Campaigns A, B, and C, the supplied employee population and salary information, the assumed breach cost, and the proposed MFA, training, and email-filtering controls. No actual security incident, confirmed compromise, or financial loss is reported in the dataset. The analysis is therefore a simulation-based risk projection.

### 2.2 Supplied campaign data

| Campaign | Target group | Emails sent | Opened | Clicked | Credentials submitted | Additional data entries |
|---|---|---:|---:|---:|---:|---:|
| A - HR Bonus Notification | 100 employees | 100 | 82 | 47 | 18 | 5 |
| B - IT System Password Reset | 250 employees | 250 | 200 | 150 | 75 | 25 |
| C - CEO Urgent Document Review | 80 executives and assistants | 80 | 72 | 60 | 12 | 8 |
| **Total** | **430 target places** | **430** | **354** | **257** | **105** | **38** |

### 2.3 Organisational and financial assumptions

| Input | Supplied value | Use in this assessment |
|---|---:|---|
| Total employees | 2,000 | Workforce projection |
| Average annual employee salary | $85,000 | Context only; not added to breach loss |
| Implied annual payroll | $170,000,000 | Context only (2,000 x $85,000) |
| Cost per data breach (SLE) | $4,350,000 | Assumed loss per breach-equivalent outcome |
| Probability of major breach if credentials are stolen | 25% | Applied to projected credential submissions |
| MFA implementation cost | $45 per user / $90,000 total | Control investment |
| MFA effectiveness | 99.9% | Scenario assumption for reduction in credential-theft impact |
| Training cost | $50 per user / $100,000 total | Control investment |
| Training effectiveness | 60% reduction in click-through rate | Applied to Campaign B click-through rate |
| Email filtering cost | $50,000 | Control investment; 20% risk reduction is an explicit planning assumption inferred from the brief's table |

### 2.4 Calculation method and terminology

Basic rates use the number of emails sent as the denominator. Conversion metrics use the preceding attack stage as the denominator. Workforce projections use the observed credential-submission rate multiplied by 2,000 employees. The lab's simplified financial model then multiplies projected credential submissions by 25% and by the $4.35 million assumed breach cost.

For clarity, this report calls the result of applying 25% to projected credential submissions **expected breach-equivalent outcomes**. It is not a verified count of distinct incidents. The term **modelled ALE** is used for the lab's calculation, subject to the limitations in Section 9.

---

## 3. Phase 1 - Basic phishing metrics

Workbook Link:https://docs.google.com/spreadsheets/d/14y7oqt00_K3Uhgt4TW5B2jEp_fjhfOvZmJXRmacaoWY/edit?usp=sharing

### 3.1 Fundamental rates

**Formula:** Rate = (Number of events / Number of emails sent) x 100

| Campaign | Email open rate | Click-through rate | Credential-submission rate | Additional data-entry rate |
|---|---:|---:|---:|---:|
| A | 82/100 = **82.00%** | 47/100 = **47.00%** | 18/100 = **18.00%** | 5/100 = **5.00%** |
| B | 200/250 = **80.00%** | 150/250 = **60.00%** | 75/250 = **30.00%** | 25/250 = **10.00%** |
| C | 72/80 = **90.00%** | 60/80 = **75.00%** | 12/80 = **15.00%** | 8/80 = **10.00%** |

**Worked examples:**

- Campaign B open rate = (200 / 250) x 100 = **80%**.
- Campaign B click-through rate = (150 / 250) x 100 = **60%**.
- Campaign B credential-submission rate = (75 / 250) x 100 = **30%**.
- Campaign B additional data-entry rate = (25 / 250) x 100 = **10%**.

### 3.2 Attack-stage conversion metrics

**Open-to-click conversion** = (Clicked / Opened) x 100.  
**Post-click credential submission** = (Credentials submitted / Clicked) x 100.

| Campaign | Open-to-click conversion | Post-click credential-submission conversion |
|---|---:|---:|
| A | 47/82 = **57.32%** | 18/47 = **38.30%** |
| B | 150/200 = **75.00%** | 75/150 = **50.00%** |
| C | 60/72 = **83.33%** | 12/60 = **20.00%** |

Campaign C had the highest open-to-click conversion, meaning that a high proportion of people who opened the message clicked its link. However, its post-click credential-submission conversion was the lowest. Campaign B converted half of all clickers into credential submitters, which helps explain why it produced the highest credential-submission rate.

### 3.3 Combined results across all campaign sends

| Metric | Calculation | Combined rate |
|---|---|---:|
| Open rate | 354 / 430 x 100 | **82.33%** |
| Click-through rate | 257 / 430 x 100 | **59.77%** |
| Credential-submission rate | 105 / 430 x 100 | **24.42%** |
| Additional data-entry rate | 38 / 430 x 100 | **8.84%** |

The combined rates are weighted by email volume. The combined credential-submission rate is 24.42%, not 22.1%. These are campaign-send-level statistics; they should not be described as a unique-employee rate unless the organisation confirms that the three target groups do not overlap.

---

## 4. Phase 2 - Advanced risk quantification

### 4.1 Workforce projection

**Formula:** Projected credential submissions = Total employees x Campaign credential-submission rate.

Campaign B is the highest credential-submission scenario:

- Campaign B credential rate = 75 / 250 = **0.30 (30%)**.
- Projected credential submissions = 2,000 x 0.30 = **600 employees**.
- Expected breach-equivalent outcomes = 600 x 0.25 = **150**.

The same method applied to each campaign produces the following scenario results:

| Campaign | Credential rate | Projected credential submissions (2,000 x rate) | Expected breach-equivalent outcomes (x 25%) |
|---|---:|---:|---:|
| A | 18% | **360** | **90** |
| B | 30% | **600** | **150** |
| C | 15% | **300** | **75** |

These are alternative projections using each campaign's observed rate. They must not be added together because the campaigns are different scenarios applied to the same workforce, not independent new populations.

### 4.2 Financial impact and modelled ALE

**Formula:** ALE = Single Loss Expectancy (SLE) x Annual Rate of Occurrence (ARO).

For the lab's Campaign B scenario:

- SLE = **$4,350,000**.
- ARO used by the lab = **150 expected breach-equivalent outcomes**.
- Modelled ALE = $4,350,000 x 150 = **$652,500,000**.

| Campaign scenario | Expected breach-equivalent outcomes | Assumed loss per outcome | Modelled financial exposure |
|---|---:|---:|---:|
| A | 90 | $4,350,000 | **$391,500,000** |
| B | 150 | $4,350,000 | **$652,500,000** |
| C | 75 | $4,350,000 | **$326,250,000** |

Campaign B is the highest-exposure scenario. Campaign A's corrected modelled exposure is $391.5 million, and Campaign C's is $326.25 million. The $156.6 million and $104.4 million values in the supplied matrix do not follow from the formula and inputs shown in the brief.

### 4.3 Employee and payroll context

The scenario's implied annual payroll is 2,000 x $85,000 = **$170 million**. The Campaign B modelled exposure divided by 2,000 employees is **$326,250 per employee**. This is an allocation of the modelled organisational exposure, not an expected loss attributable to each individual employee. Salary and payroll have not been added to the breach cost because the brief provides no separate downtime or productivity-loss assumptions and doing so could double-count costs already included in the breach estimate.

---

## 5. Phase 3 - Comprehensive risk assessment

### 5.1 Risk assessment matrix

The ratings below are provisional qualitative judgements based on credential-submission rate, projected financial exposure, additional data entry, and the role profile of the target group. The brief does not provide formal rating thresholds.

| Campaign | Credential rate | Additional data-entry rate | Modelled exposure | Provisional risk | Priority | Recommended treatment |
|---|---:|---:|---:|---|---:|---|
| A - HR Bonus Notification | 18% | 5% | **$391.50M** | Medium-High | 2 | Targeted HR awareness training; reinforce verification of payroll/bonus requests; MFA |
| B - IT System Password Reset | 30% | 10% | **$652.50M** | Critical | 1 | Immediate MFA priority; password-reset process hardening; email/URL protection; targeted training |
| C - CEO Urgent Document Review | 15% | 10% | **$326.25M** | High | 3 | Executive and assistant-focused training; verified document-sharing procedures; stronger account protections |

### 5.2 Risk interpretation

- **Campaign B - Critical:** it has the highest credential-submission rate and the highest modelled exposure. The password-reset theme is a strong candidate for targeted control testing and identity-process hardening.
- **Campaign A - Medium-High:** 18% of recipients submitted credentials. HR and payroll-related lures may exploit employee interest in compensation or benefits. Verification procedures and role-based training are recommended.
- **Campaign C - High:** its credential-submission rate is lower than A and B, but the target population consists of executives and assistants, and the additional data-entry rate is 10%. The organisation should assess account privileges and business-process access before determining whether a higher impact rating is warranted.

### 5.3 Statistical confidence intervals (95%)

**Formula:** p +/- 1.96 x sqrt[p(1-p)/n], where p is the observed credential rate and n is the number of emails sent.

**Campaign A worked calculation:**

- p = 18/100 = 0.18; n = 100.
- Standard error = sqrt[0.18 x (1 - 0.18) / 100] = sqrt(0.001476) = **0.03842**.
- Margin of error = 1.96 x 0.03842 = **0.07530**, or **7.53 percentage points**.
- 95% confidence interval = 0.18 +/- 0.07530 = **10.47% to 25.53%**.

| Campaign | Observed credential rate | Sample size (n) | Margin of error | Approximate 95% confidence interval |
|---|---:|---:|---:|---:|
| A | 18.00% | 100 | +/- 7.53 pp | **10.47% - 25.53%** |
| B | 30.00% | 250 | +/- 5.68 pp | **24.32% - 35.68%** |
| C | 15.00% | 80 | +/- 7.82 pp | **7.18% - 22.82%** |

The intervals show uncertainty around each observed sample rate. Campaign A and Campaign C have relatively wide intervals because their sample sizes are smaller. These are approximate normal (Wald) intervals, as specified in the study guide. Their interpretation depends on representative, sufficiently independent sampling. The target groups may differ by role and risk exposure, so these intervals do not automatically establish organisation-wide employee susceptibility. A larger, stratified, repeated simulation programme would provide stronger evidence.

---

## 6. Phase 4 - Executive briefing and control economics

### 6.1 Board-level briefing

**To:** Board of Directors, CISO, CFO  
**From:** GRC Risk Analysis Team  
**Date:** 31 October 2026  
**Subject:** Quantitative Phishing Risk Assessment and Campaign B Exposure

Three phishing simulations generated a combined credential-submission rate of 24.42%. Campaign B recorded the highest rate at 30%. Applying that result to the 2,000-person workforce produces 600 projected credential submissions. Under the lab's simplified 25% conditional probability and $4.35 million loss assumptions, this results in 150 expected breach-equivalent outcomes and a modelled exposure of $652.5 million.

This figure is suitable as a scenario-based risk indicator for the exercise, but it is not yet a validated annual loss forecast. ARO must represent a defensible annual event frequency, and compromised accounts must not be treated as separate $4.35 million breach incidents without evidence that each would create an independent loss event.

The immediate control priority is to strengthen identity protection with MFA, reduce susceptibility through role-based training, and strengthen email-layer controls. The proposed investment should be approved in stages, tied to measurable control outcomes, and reassessed using repeat simulations and incident data.

### 6.2 Stand-alone control cost-benefit analysis

**ROI formula:** ROI = [(Risk-reduction benefit - Control cost) / Control cost] x 100.

| Control | Cost | Assumed effect | Modelled risk reduction (benefit) | Net benefit after cost | ROI | Modelled residual ALE |
|---|---:|---|---:|---:|---:|---:|
| MFA implementation (Priority 1) | $90,000 | 99.9% reduction in credential-theft impact | **$651,847,500** | **$651,757,500** | **724,175%** | $652,500 |
| Security training (Priority 2) | $100,000 | 60% reduction in Campaign B CTR; post-click conversion held at 50% | **$391,500,000** | **$391,400,000** | **391,400%** | $261,000,000 |
| Email filtering (Priority 3) | $50,000 | 20% ALE reduction assumed for modelling | **$130,500,000** | **$130,450,000** | **260,900%** | $522,000,000 |

#### MFA calculation

- Cost = 2,000 x $45 = **$90,000**.
- Risk reduction = $652,500,000 x 0.999 = **$651,847,500**.
- Residual ALE = $652,500,000 x 0.001 = **$652,500**.
- Net benefit = $651,847,500 - $90,000 = **$651,757,500**.
- ROI = ($651,757,500 / $90,000) x 100 = **724,175%**.

#### Training calculation

Campaign B's observed click-through rate is 60%. A 60% reduction results in a new click-through rate of 60% x (1 - 0.60) = **24%**. If the post-click credential conversion remains 50%, the new credential-submission rate is 24% x 50% = **12%** of emails sent.

- Projected credential submissions = 2,000 x 0.12 = **240**.
- Expected breach-equivalent outcomes = 240 x 0.25 = **60**.
- New modelled ALE = 60 x $4,350,000 = **$261,000,000**.
- Risk reduction = $652,500,000 - $261,000,000 = **$391,500,000**.
- ROI = [($391,500,000 - $100,000) / $100,000] x 100 = **391,400%**.

This resolves a wording error in the brief: 12% is the new credential-submission rate, not the new click-through rate. The new click-through rate is 24%.

#### Email-filtering calculation

The brief's control table implies a 20% reduction in the $652.5 million baseline. No direct email-filtering risk-reduction value is otherwise given, so this is treated as a planning assumption rather than a measured result.

- Risk reduction = $652,500,000 x 0.20 = **$130,500,000**.
- Residual ALE = $652,500,000 - $130,500,000 = **$522,000,000**.
- Net benefit = $130,500,000 - $50,000 = **$130,450,000**.
- ROI = ($130,450,000 / $50,000) x 100 = **260,900%**.

**Important:** The three stand-alone benefits are measured against the same baseline. They must not be added together as if each control independently removes a separate portion of risk. Control effects can overlap, depend on implementation quality, and vary by attack path.

### 6.3 Proposed security investment portfolio

The brief's full proposed portfolio totals $490,000:

| Initiative | Proposed cost |
|---|---:|
| Enterprise MFA | $90,000 |
| Targeted phishing simulation programme | $25,000 |
| Emergency security awareness training | $100,000 |
| Advanced email security gateway | $50,000 |
| Continuous security monitoring | $150,000 |
| Security behaviour analytics | $75,000 |
| **Total** | **$490,000** |

The brief states a 90% portfolio risk-reduction target but does not provide individual effectiveness values for simulations, monitoring, or behaviour analytics, nor a method for combining the control effects. If management uses 90% as an explicit planning target, the arithmetic is:

- Target risk reduction = $652,500,000 x 90% = **$587,250,000**.
- Residual modelled ALE = $652,500,000 - $587,250,000 = **$65,250,000**.
- Net financial benefit = $587,250,000 - $490,000 = **$586,760,000**.
- Indicative portfolio ROI = ($586,760,000 / $490,000) x 100 = **119,746.94%**.

This is a target-based scenario, not an evidenced forecast. The 90% reduction should be validated through control testing and repeated simulation results. Monitoring and behaviour analytics should not be assigned financial benefits until their effect on likelihood, detection, containment, or loss magnitude is defined.

### 6.4 Expected risk posture after controls

The brief proposes a 90% risk-reduction target. Applied consistently to the corrected combined credential baseline and the Campaign B modelled ALE, the illustrative posture is:

| Metric | Current state | With 90% reduction target | Reduction |
|---|---:|---:|---:|
| Combined credential-submission rate | 24.42% | 2.44% | 90% |
| Campaign B credential-submission rate | 30.00% | 3.00% | 90% |
| Campaign B modelled ALE | $652.50M | $65.25M | 90% |
| Organisation-wide probability of at least one major breach | Not established | Not established | Not calculable from supplied data |

The 90% outcomes are planning targets, not measured post-control results. The brief's 93.75% current breach probability and 25% post-control probability are not supported by the calculation inputs and should not be used as executive metrics.

### 6.5 Break-even analysis

**Formula:** Break-even breach-equivalents = Total investment / Cost per breach.

$490,000 / $4,350,000 = **0.1126 breach-equivalents**.

On an expected-loss basis, the portfolio breaks even if it avoids at least 0.1126 of the modelled breach-equivalent loss. If only whole breach events are counted, preventing **one full breach** would exceed the $490,000 investment, assuming the $4.35 million loss estimate applies to that event and the loss is genuinely avoidable by the controls.

The portfolio needs to reduce the $652.5 million modelled baseline by only about **0.0751%** to equal its $490,000 cost. This low mathematical threshold is driven by the very large baseline and should not be mistaken for proof that the baseline is realistic.

---

## 7. Strategic recommendations and implementation roadmap

### Immediate actions - first 90 days

1. **Deploy MFA:** prioritise privileged and high-impact accounts, then extend to all users. Prefer phishing-resistant methods where practical; document exceptions and recovery processes.
2. **Harden password-reset workflows:** require strong identity verification, prevent help-desk reset abuse, notify users of resets, and monitor unusual authentication events.
3. **Run targeted training:** focus on password-reset lures, HR/benefit requests, executive document-review requests, sender verification, and safe reporting.
4. **Tune email protections:** evaluate sender authentication, URL rewriting/time-of-click checks, attachment sandboxing, impersonation protection, and external-sender warnings.
5. **Establish a reporting path:** make it simple for users to report suspicious messages and ensure the security team triages them consistently.

### Strategic actions - next 6 to 12 months

- Run quarterly simulations using a consistent metric definition and stratified groups.
- Track repeat susceptibility and report rates, not only opens and clicks.
- Introduce identity and email control coverage dashboards for management.
- Use continuous monitoring and behaviour analytics to detect anomalous sign-ins, mailbox rules, suspicious OAuth consent, and unusual data access.
- Validate breach cost and annual frequency using the organisation's incident history, insurance data, regulatory exposure, recovery costs, and business impact analysis.
- Recalculate ALE and control ROI after each measurement cycle.

### Suggested quarterly KPIs

| KPI | Baseline from supplied simulations | Suggested management objective |
|---|---:|---|
| Credential-submission rate | 24.42% combined; 30% Campaign B | Reduce quarter-on-quarter; set a formal target after baseline validation |
| Click-through rate | 59.77% combined; 60% Campaign B | Reduce through layered controls and targeted coaching |
| Additional data-entry rate | 8.84% combined | Reduce to zero; investigate every submission event |
| MFA coverage | Not supplied | 100% of workforce accounts, with tracked exceptions |
| Phishing report rate | Not supplied | Establish baseline, then improve reporting and response speed |
| Repeat-susceptibility rate | Not supplied | Track by cohort and target repeat users with coaching |
| Mean time to triage reported phishing | Not supplied | Establish baseline and improve quarterly |

---

## 8. Limitations, assumptions, and corrections to the supplied brief

1. **Breach-event assumption:** 600 projected credential submissions multiplied by 25% gives 150 expected outcomes. It does not establish 150 distinct organisational breach incidents. Applying a full $4.35 million loss to every account-level outcome may materially overstate loss.
2. **ARO interpretation:** ALE requires an annual occurrence frequency. The simulations took place last quarter, but the dataset does not establish that 150 breach-equivalent outcomes recur every year. The $652.5 million figure is therefore a lab-modelled ALE proxy, not a verified annual forecast.
3. **Probability statement:** 150 expected outcomes is a count/expectation, not a 93.75% probability. The supplied 93.75% figure has no derivation from the provided inputs and should not be reported as the organisation's breach probability.
4. **Campaign matrix arithmetic:** Campaign A calculates to $391.5 million, not $156.6 million. Campaign C calculates to $326.25 million, not $104.4 million, using the stated formula and inputs.
5. **Training wording:** reducing Campaign B's 60% click-through rate by 60% gives 24%, not 12%. The 12% figure is the resulting credential-submission rate if the 50% post-click conversion remains unchanged.
6. **Email-filtering effectiveness:** the 20% ALE reduction is implied by the proposed benefit in the supplied table; it is not established by campaign data or a stated control test.
7. **Portfolio reduction:** a 90% aggregate reduction is a target assumption only. The brief does not provide enough data to combine control effects or calculate the actual reduction from monitoring, simulation, and behaviour analytics.
8. **ROI scale:** the very high returns result from dividing large modelled benefits by comparatively small control costs. They are not credible investment forecasts until the loss baseline and effectiveness assumptions are validated.
9. **Sample representativeness:** the campaigns target different groups and may not be a random, independent sample of all employees. Confidence intervals are approximate and do not eliminate sampling or selection bias.
10. **Benchmark quality:** the industry comparisons in the brief and study guide are not accompanied by sources, dates, sectors, or matching metric definitions. They are not treated as verified industry benchmarks in this report.
11. **Salary input:** the $85,000 average salary is used only to calculate contextual payroll. No salary-based loss is added to breach costs because the brief provides no productivity-loss assumptions.
12. **Additional data entries:** the 38 additional data-entry events may overlap with credential submissions. They are reported separately and are not added to credential submissions as if they were distinct victims.

### Corrections to headline values

| Item | Supplied brief value | Correct treatment in this report |
|---|---:|---:|
| Combined credential-submission rate | 22.1% | **24.42%** (105/430 weighted rate) |
| Campaign A modelled exposure | $156.6M | **$391.5M** |
| Campaign C modelled exposure | $104.4M | **$326.25M** |
| New Campaign B click-through rate after 60% reduction | 12% | **24%**; 12% is the derived credential-submission rate |
| Email filtering ROI | 260,800% | **260,900%** under 20% benefit assumption |
| 90% portfolio risk reduction | $587.5M | **$587.25M** when applied to $652.5M |
| Net portfolio benefit | $587.01M | **$586.76M** after subtracting $490,000 |
| Probability of major breach | 93.75% | **Not supported** by the supplied data; 150 is an expected count under the simplified model |

---

## 9. Conclusion

The simulations identify a material human-risk issue that warrants immediate treatment. Campaign B is the highest-priority scenario because it produced a 30% credential-submission rate and the highest projected financial exposure under the lab's model. Campaign A and Campaign C also demonstrate meaningful susceptibility and require tailored interventions.

The calculations show how phishing metrics can be translated into financial terms for executive decision-making. However, quantitative GRC reporting must separate observed results, mathematical projections, and assumptions. The $652.5 million estimate is useful for completing the exercise and illustrating the financial consequences of the supplied model, but it should not be represented as a validated annual loss forecast until the organisation validates how credential compromise translates into distinct breach events and annual frequency.

GlobalTech should prioritise MFA, targeted training, email-layer protection, and recurring measurement. Management should approve the proposed investment in stages, track control outcomes, and refresh the risk model with validated incident and loss data.

---

## Appendix A - Formula reference

| Metric | Formula |
|---|---|
| Open rate | (Opened / Sent) x 100 |
| Click-through rate | (Clicked / Sent) x 100 |
| Credential-submission rate | (Credentials submitted / Sent) x 100 |
| Additional data-entry rate | (Additional data entries / Sent) x 100 |
| Open-to-click conversion | (Clicked / Opened) x 100 |
| Post-click credential conversion | (Credentials submitted / Clicked) x 100 |
| Projected credential submissions | Total employees x credential-submission rate |
| Expected breach-equivalent outcomes | Projected credential submissions x conditional probability |
| Annualized Loss Expectancy | SLE x ARO |
| Risk reduction | Current ALE x control effectiveness |
| New risk | Current ALE x (1 - control effectiveness) |
| ROI | [(Benefit - Cost) / Cost] x 100 |
| 95% confidence interval | p +/- 1.96 x sqrt[p(1-p)/n] |
| Break-even breach-equivalents | Investment cost / cost per breach |

##  References
1.Cybersecurity and Infrastructure Security Agency. (2022, October). Implementing phishing-resistant MFA.
https://www.cisa.gov/sites/default/files/2023-01/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf

2.Cybersecurity and Infrastructure Security Agency, National Security Agency, Federal Bureau of Investigation, & Multi-State Information Sharing and Analysis Center. (2023, October). Phishing guidance: Stopping the attack cycle at phase one.
https://www.cisa.gov/sites/default/files/2025-03/Phishing%20Guidance%20-%20Stopping%20the%20Attack%20Cycle%20at%20Phase%20One%20508.pdf

3.GlobalTech Inc. (n.d.). Lab 3: Advanced GRC phishing simulation & quantitative risk analysis.Supplied lab scenario, campaign dataset, control assumptions and deliverables.

4.National Institute of Standards and Technology. (2012). Guide for conducting risk assessments (NIST Special Publication 800-30 Rev. 1). U.S. Department of Commerce.
https://doi.org/10.6028/NIST.SP.800-30r1

5. GlobalTech Inc. (n.d.). *Lab 3: Advanced GRC Phishing Simulation & Quantitative Risk Analysis*. Supplied training brief.
6. *Study Guide: Quantitative Risk Calculations for GRC Professionals*. Supplied training material.
   

LAB 3A workbook Link: https://docs.google.com/spreadsheets/d/14y7oqt00_K3Uhgt4TW5B2jEp_fjhfOvZmJXRmacaoWY/edit?usp=sharing


## AI Usage Declaration
ChatGPT (OpenAI) and Microsoft Copilot were used  for brainstorming, report structuring and  editing. AI-assisted outputs were reviewed, I  remain  responsible for the accuracy and final content of this report.
