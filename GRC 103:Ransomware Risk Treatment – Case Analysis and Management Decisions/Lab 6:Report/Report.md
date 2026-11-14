# Ransomware Risk Treatment — Case Analysis and Management Decisions

**International Cybersecurity and Digital Forensics Academy (ICDFA)**  
**Programme:** GRC103 — Module 3: Risk Treatment Strategies  
**Assessment:** Lab 6 — Lab 6: Ransomware Risk Treatment – Case Analysis and Management Decisions
 
**Case organisation:** Northbridge Community Health (fictional)  
**Student:** Olubunmi Adesanmi
**Registration number:** C11/26/CGRCE/17550 
**Submission date:** 15 November 2026
**Workbook:** https://docs.google.com/spreadsheets/d/1Br_9Pm8VyBlCbJ92P9-c807JITivYE0H1O8nST9nSDg/edit?usp=sharing

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Introduction, Scope and Assumptions](#2-introduction-scope-and-assumptions)
3. [Real-World Case: 2021 HSE Ransomware Incident](#3-real-world-case-2021-hse-ransomware-incident)
4. [Task 1 — Risk Identification and Prioritisation](#4-task-1--risk-identification-and-prioritisation)
5. [Task 2 — Treatment Selection and Initial Budget](#5-task-2--treatment-selection-and-initial-budget)
6. [Task 3 — Insurance and Retained-Loss Calculations](#6-task-3--insurance-and-retained-loss-calculations)
7. [Task 4 — Revised Decisions Following the Scenario Change](#7-task-4--revised-decisions-following-the-scenario-change)
8. [Task 5 — Thirty-Day Treatment Plan and Residual Risk](#8-task-5--thirty-day-treatment-plan-and-residual-risk)
9. [Board Memo](#9-board-memo)
10. [Conclusion](#10-conclusion)
11. [References](#11-references)

---

## 1. Executive Summary

This report advises Northbridge Community Health, a fictional provider operating three clinics, on treating ransomware-related business risks within a first-year budget of **$100,000**. The analysis uses the 2021 ransomware incident affecting Ireland’s Health Service Executive (HSE) as a real-world reference while keeping HSE facts separate from the fictional Northbridge assumptions.

Four risks were assessed: disruption to healthcare services, exposure of sensitive patient information, unnecessary supplier access and delayed incident detection. The initial portfolio selected workflow retirement, multi-factor authentication (MFA), protected backups and recovery testing, staff awareness and an illustrative cyber-insurance option. Its total cost was **$90,000**, leaving **$10,000**.

The scenario then changed: a restoration test failed, paper bookings could support the clinics for only four hours, and the price of MFA increased to $35,000. The revised portfolio retains workflow retirement, MFA, backup and recovery work, and awareness training. It defers insurance, managed detection and network segmentation. Revised expenditure is **$80,000**, leaving **$20,000** unallocated.

The failed restoration test means service recovery is not yet proven. Service disruption and sensitive-data exposure therefore remain critical residual risks requiring board oversight. Delayed detection remains high and may only be accepted temporarily with formal board approval, documented compensating measures and a fixed review date.

## 2. Introduction, Scope and Assumptions

Ransomware can affect the **availability** of systems and information through encryption and may also affect **confidentiality** where information is accessed or copied. For a healthcare provider, these consequences can disrupt appointments, delay care, expose patient information and create regulatory, financial and reputational consequences.

Northbridge’s fictional scenario identifies four conditions: an unused supplier workflow is enabled; backup restoration has not been tested; phishing reports have no clearly assigned escalation owner; and essential bookings must continue during an incident. The assignment provides seven treatment options and their first-year prices.

This is a classroom case analysis, not a live technical assessment. No Northbridge systems were examined, no controls were implemented or tested by the author, and no insurance was purchased. Risk scores and residual ratings are qualitative estimates for the exercise. All Northbridge details, treatment costs, insurance terms, loss amounts and scenario changes are fictional assumptions.

## 3. Real-World Case: 2021 HSE Ransomware Incident

The HSE’s official account states that a phishing email was sent to a user on its network in **March 2021**. When an attachment was opened, malware was downloaded; the ransomware attack was triggered in **May 2021**. The HSE states that the attackers used ransomware to encrypt files and block access, and that information was accessed and copied. The HSE also states that it stopped the attack when it became aware of it and that **no ransom was paid** (Health Service Executive [HSE], 2025).

Two incident facts are particularly relevant to Northbridge:

1. **Phishing preceded the attack:** the initial access route involved a phishing email attachment opened by a network user in March 2021 (HSE, 2025). This supports investment in awareness, reporting and account-protection measures.
2. **The incident affected both availability and confidentiality:** files were encrypted and information was accessed and copied (HSE, 2025). This demonstrates why ransomware planning must address service recovery as well as information protection.

These are facts about the HSE incident. They do not establish that Northbridge has experienced an attack or has the same technical weaknesses.

## 4. Task 1 — Risk Identification and Prioritisation

### 4.1 Scoring Method

Risk score is calculated as **Likelihood × Impact**. Both factors use a 1–5 scale. The classification thresholds are those supplied in the exercise.

| Score | Classification | Exercise treatment rule |
|---:|---|---|
| 1–4 | Low | Manage through routine controls and monitoring |
| 5–9 | Medium | Treat or monitor according to risk appetite |
| 10–16 | High | Escalate to the board |
| 17–25 | Critical | Must not be accepted; further treatment and escalation required |

### 4.2 Initial Risk Register

| ID | Asset / process | Threat and weakness | Potential business impact | Owner | Likelihood | Impact | Score / rating |
|---|---|---|---|---|---:|---:|---|
| R1 | Patient booking systems and clinic operations | Ransomware encrypts systems; backup restoration has not been tested | Booking interruption, delayed appointments and disruption to essential services | Operations Director | 5 | 5 | **25 — Critical** |
| R2 | Patient records and sensitive information | Phishing or compromised accounts enable unauthorised access; access protections require strengthening | Patient privacy harm, regulatory consequences, financial loss and reputational damage | Data Protection Officer | 4 | 5 | **20 — Critical** |
| R3 | Supplier workflow and connected systems | Unauthorised use of an unnecessary supplier workflow that remains enabled | Expanded attack surface and potential access to connected systems or information | IT Manager | 3 | 4 | **12 — High** |
| R4 | Email and incident-reporting process | Phishing is not escalated promptly because no reporting owner is assigned | Delayed investigation, longer attacker dwell time and increased incident severity | Information Security Manager | 4 | 4 | **16 — High** |

### 4.3 Rating Rationale

- **R1 (4 × 5 = 20, Critical):** Ransomware is a credible threat to systems supporting clinic operations. Untested restoration increases uncertainty about recovery. Impact is very high because unavailable bookings can interrupt essential services.
- **R2 (4 × 5 = 20, Critical):** Phishing and compromised accounts can expose sensitive records. The potential privacy, regulatory and reputational consequences justify a very high impact rating.
- **R3 (3 × 4 = 12, High):** The enabled but unused workflow creates avoidable supplier-related exposure. Its likelihood is moderate, while compromise could affect connected systems or information.
- **R4 (4 × 4 = 16, High):** The absence of a named escalation owner may delay investigation of phishing reports. This can allow malicious activity to continue and increase the scale of an incident.

## 5. Task 2 — Treatment Selection and Initial Budget

### 5.1 Treatment Strategy Assessment

| Strategy | Meaning in this case | Application |
|---|---|---|
| Avoidance | Remove the activity or exposure creating the risk | Retire the unused supplier workflow (Option A) |
| Mitigation | Reduce likelihood and/or impact through controls | MFA, protected backups, restoration testing and staff awareness (Options B, C and E) |
| Transfer | Share specified financial consequences with another party | Consider illustrative cyber insurance (Option G), subject to policy terms and exclusions |
| Acceptance | Retain a known residual risk through an authorised decision | Consider only temporary acceptance of residual delayed-detection risk, with board approval and controls |

Insurance does not transfer Northbridge’s accountability for patient safety, privacy obligations, risk oversight or incident management. Outsourcing a service would not remove that accountability either.

### 5.2 Initial Treatment Portfolio

| Option | Treatment | Cost | Primary risks addressed | Decision and rationale |
|---|---|---:|---|---|
| A | Retire unused supplier workflow | $5,000 | R3 | **Select:** removes an unnecessary exposure |
| B | MFA rollout and account access review | $25,000 | R2, R4 | **Select:** strengthens authentication and identifies unnecessary access |
| C | Protected backups, restoration tests and recovery plan | $30,000 | R1, R2 | **Select:** supports recovery and reduces the consequences of data/system unavailability |
| E | Targeted awareness training and reporting process | $10,000 | R2, R4 | **Select:** addresses the human phishing route and creates an escalation process |
| G | Illustrative cyber insurance | $20,000 | Financial consequences of eligible covered claims | **Select initially:** provides limited financial risk transfer, subject to deductible, limit and exclusions |
| D | Managed detection and incident escalation service | $35,000 | R2, R4 | **Defer:** important, but the initial budget prioritises core recovery, access protection and reporting ownership |
| F | Network segmentation and legacy dependency review | $40,000 | R1, R2, R3 | **Defer:** potentially valuable, but cannot be funded alongside the higher-priority initial package within the budget |

**Initial budget calculation**

- Available budget: **$100,000**
- Selected options: A + B + C + E + G = $5,000 + $25,000 + $30,000 + $10,000 + $20,000 = **$90,000**
- Remaining budget: $100,000 − $90,000 = **$10,000**

The initial portfolio is within budget. Deferred options remain open risks and should be reconsidered during subsequent planning.

### 5.3 Initial Acceptance Record

R1 and R2 are **not accepted** because they are Critical. R3 and R4 are High and must be escalated to the board under the exercise rules. For R4, management may propose temporary acceptance only after establishing the Option E reporting process and presenting the residual risk to the Board Risk Committee.

| Acceptance field | Proposed record |
|---|---|
| Risk | R4 — delayed incident detection |
| Risk owner | Information Security Manager |
| Simulated approver | Board Risk Committee |
| Proposed period | 15 November–14 December 2026 |
| Expiry date | 14 December 2026 |
| Compensating measures | Named escalation owner; documented reporting route; daily review of reports; defined escalation and response times |
| Review triggers | Missed escalation; confirmed phishing incident; suspicious account activity; failed reporting exercise; or expiry date |
| Approval status | **Pending** — this is a proposed acceptance, not an approved decision |

If the Board Risk Committee does not approve the temporary acceptance, R4 remains escalated for additional treatment. Acceptance does not remove the obligation to monitor and report the risk.

## 6. Task 3 — Insurance and Retained-Loss Calculations

### 6.1 Illustrative Policy Terms

| Term | Amount |
|---|---:|
| Annual premium | $20,000 |
| Deductible | $25,000 |
| Maximum insurer payment per covered claim | $250,000 |

**Formula**

```text
Insurer payment = MIN(MAX(Loss - Deductible, 0), Policy limit)
Retained loss = Loss - Insurer payment
First-year outlay = Retained loss + Annual premium
```

### 6.2 Covered-Loss Scenarios

**Scenario 1 — Covered loss of $180,000**

1. Loss above deductible = $180,000 − $25,000 = $155,000.
2. Insurer payment = MIN($155,000, $250,000) = **$155,000**.
3. Retained loss = $180,000 − $155,000 = **$25,000**.
4. First-year outlay including premium = $25,000 + $20,000 = **$45,000**.

**Scenario 2 — Covered loss of $400,000**

1. Loss above deductible = $400,000 − $25,000 = $375,000.
2. Insurer payment = MIN($375,000, $250,000) = **$250,000** because the policy limit applies.
3. Retained loss = $400,000 − $250,000 = **$150,000**.
4. First-year outlay including premium = $150,000 + $20,000 = **$170,000**.

### 6.3 Excluded-Claim Scenarios

If a claim is excluded, insurer payment is **$0**. Northbridge bears the entire loss and still pays the assumed annual premium.

| Scenario | Loss | Insurer payment | Retained loss | Premium | First-year outlay |
|---|---:|---:|---:|---:|---:|
| Covered claim | $180,000 | $155,000 | $25,000 | $20,000 | **$45,000** |
| Covered claim | $400,000 | $250,000 | $150,000 | $20,000 | **$170,000** |
| Excluded claim | $180,000 | $0 | $180,000 | $20,000 | **$200,000** |
| Excluded claim | $400,000 | $0 | $400,000 | $20,000 | **$420,000** |

The first-year outlay figures above combine the retained incident loss and annual premium for the exercise. They are not the treatment-portfolio budget totals. Actual insurance response would depend on the wording, conditions, exclusions and claims process of a real policy. The exercise terms are illustrative and do not represent an insurance quote or purchase.

## 7. Task 4 — Revised Decisions Following the Scenario Change

### 7.1 Change and Management Implications

The revised scenario introduces three facts: the restoration test fails; paper bookings can support the clinics for only **four hours**; and Option B increases from **$25,000 to $35,000**. The failed test means that recovery capability cannot be treated as proven. The limited paper-booking period indicates that existing manual continuity arrangements may be inadequate for a prolonged outage.

### 7.2 Revised Treatment Portfolio

| Option | Revised treatment | Revised cost | Decision |
|---|---|---:|---|
| A | Retire unused supplier workflow | $5,000 | Retain |
| B | MFA rollout and account access review | $35,000 | Retain at revised price |
| C | Protected backups, restoration remediation/tests and recovery plan | $30,000 | Retain and prioritise; effectiveness remains unproven until a successful test |
| E | Targeted awareness training and reporting process | $10,000 | Retain |
| G | Illustrative cyber insurance | $20,000 | Defer |
| D | Managed detection and incident escalation service | $35,000 | Defer |
| F | Network segmentation and legacy dependency review | $40,000 | Defer |

**Revised budget calculation**

- Selected options: A + B + C + E = $5,000 + $35,000 + $30,000 + $10,000 = **$80,000**
- Available budget: **$100,000**
- Remaining budget: $100,000 − $80,000 = **$20,000**

The revised portfolio remains within the budget. The $20,000 balance is **unallocated**, not evidence that the recovery problem has been solved. Management should retain it pending a costed remediation proposal and approval rather than assume it is sufficient to correct the failed restoration test.

### 7.3 Initial-to-Revised Decision Log

| Decision area | Initial decision | Revised decision | Reason for change |
|---|---|---|---|
| Supplier exposure | Select A ($5,000) | Retain A ($5,000) | Avoidance remains appropriate |
| Identity security | Select B ($25,000) | Retain B ($35,000) | Option price increased; account protection remains a priority |
| Backup and recovery | Select C ($30,000) | Retain C ($30,000), prioritise remediation and retest | Failed restoration test elevates urgency; recovery is not yet proven |
| Awareness and reporting | Select E ($10,000) | Retain E ($10,000) | Reporting ownership remains necessary |
| Insurance | Select G ($20,000) | Defer G | Prioritise operational recovery and preventive controls under the revised circumstances |
| Managed detection | Defer D | Continue to defer D | Funding is not included in the revised portfolio; delayed-detection exposure remains |
| Segmentation | Defer F | Continue to defer F | Funding is not included in the revised portfolio; review remains necessary |
| Total | $90,000 | $80,000 | Revised portfolio is within the $100,000 ceiling |

### 7.4 Escalation and Ownership

- **R1 — Operations Director:** escalate the failed restoration test and four-hour paper-booking limit to the Board Risk Committee immediately. Require a remediation plan, successful restoration evidence and a review of manual continuity capacity.
- **R2 — Data Protection Officer:** maintain oversight of patient information protection, MFA rollout and access review. Critical status remains until further treatment and evidence justify a lower rating.
- **R3 — IT Manager:** verify workflow retirement and removal of any unnecessary associated access.
- **R4 — Information Security Manager:** maintain the phishing reporting process and report unresolved detection gaps. Managed detection remains deferred and R4 remains subject to board oversight.
- **Insurance decision — executive management / Board Risk Committee:** record that Option G is deferred and that Northbridge bears the financial exposure not otherwise insured.

## 8. Task 5 — Thirty-Day Treatment Plan and Residual Risk

### 8.1 Thirty-Day Implementation Plan

**Implementation period:** 15 November–14 December 2026.

| Target period | Action | Owner | Allocated cost | Effectiveness test / evidence |
|---|---|---|---:|---|
| Days 1–5 (15–19 Nov) | Retire unused supplier workflow and remove associated unnecessary access | IT Manager | $5,000 | Evidence of deactivation; confirm the workflow is no longer available and review access records |
| Days 1–10 (15–24 Nov) | Roll out MFA and review user accounts and privileges | IT Manager | $35,000 | Report MFA coverage; confirm inactive/unnecessary accounts and excessive privileges are addressed |
| Days 1–15 (15–29 Nov) | Investigate the failed restoration test; remediate backup/recovery weaknesses; update recovery procedures and retest | IT Manager and Operations Director | $30,000 | Document a successful restoration test, data-integrity checks, recovery time and unresolved exceptions; until success, control effectiveness is not proven |
| Days 5–20 (19 Nov–4 Dec) | Deliver targeted phishing awareness and establish named reporting and escalation ownership | Information Security Manager | $10,000 | Run a reporting exercise; verify that reports reach the assigned owner within the defined response time |
| Days 21–25 (5–9 Dec) | Review evidence, open actions and residual risks | Information Security Manager | Included in selected options | Evidence register and updated risk log reviewed by control owners |
| Days 26–30 (10–14 Dec) | Present progress, unresolved risks and any acceptance request to management / Board Risk Committee | Operations Director | No additional allocation | Meeting record, decisions, action owners and due dates documented |

**Total allocated cost: $80,000. Unallocated budget: $20,000.** The costs above are the supplied option prices, not independent vendor quotes. Any additional expenditure to resolve the failed test requires a costed proposal and approval within the available budget or a further funding decision.

### 8.2 Proposed Residual Risk Register

Residual scores below are **proposed estimates**, not measured results. A lower score is only justified when the relevant control has been implemented and its effectiveness supported by evidence. Because the restoration test failed, R1 is increased rather than reduced.

| ID | Risk | Proposed residual likelihood | Impact | Score / rating | Basis and status |
|---|---|---:|---:|---|---|
| R1 | Healthcare service disruption | 5 | 5 | **25 — Critical** | Failed restoration and four-hour manual booking limit indicate severe unresolved continuity exposure. Do not accept. |
| R2 | Sensitive patient information exposure | 4 | 5 | **20 — Critical** | MFA and access reviews are planned, not yet proven. Potential impact remains very high. Do not accept. |
| R3 | Unnecessary supplier exposure | 1 | 4 | **4 — Low** | Proposed reduction assumes workflow retirement and removal of related access are completed and verified. Until verified, retain the initial High rating. |
| R4 | Delayed incident detection | 3 | 4 | **12 — High** | Named reporting ownership and awareness may reduce likelihood, but managed detection is deferred. Board escalation remains required. |

### 8.3 Residual Risk Acceptance Controls

A temporary acceptance of R4 may be proposed to the **Board Risk Committee** for the period **15 November–14 December 2026**. The risk owner is the Information Security Manager. Acceptance is not effective until approved and recorded. Compensating measures are a named escalation owner, a documented reporting route, daily review of reports and defined response times. The risk must be reviewed immediately after a missed escalation, confirmed phishing event, suspicious account activity, failed reporting exercise or expiry date. If the committee declines approval, R4 remains escalated for further treatment.

R1 and R2 remain Critical and must not be accepted. R3 should only be recorded as Low after the workflow and associated access have been verified as removed.

## 9. Board Memo

**To:** Board of Directors, Northbridge Community Health  
**From:** Information Security and Risk Management Function  
**Date:** 14 November 2026  
**Subject:** Approval of Revised Ransomware Risk Treatment Portfolio

Management requests approval of a revised first-year treatment allocation of **$80,000** from the available **$100,000**, leaving **$20,000 unallocated** pending a costed remediation proposal. The portfolio funds supplier-workflow retirement, MFA and account review, backup and recovery remediation, and phishing awareness with an assigned reporting process.

The restoration test failure and the four-hour limit on paper bookings make service continuity the immediate priority. The organisation must not treat recovery as effective until a subsequent restoration test succeeds and evidence is reviewed. Protecting patient information and strengthening access controls remain essential.

R1 (service disruption) and R2 (patient information exposure) remain Critical. R4 (delayed detection) remains High because managed detection is deferred. Insurance is also deferred, leaving Northbridge exposed to losses not otherwise covered. The Board is requested to approve the revised portfolio, require immediate reporting on recovery remediation, maintain oversight of all Critical and High risks, and consider—but not automatically approve—the proposed time-limited acceptance of R4. Critical risks are not proposed for acceptance.

## 10. Conclusion

The exercise demonstrates that ransomware risk treatment must balance prevention, detection, recovery, financial exposure and service continuity. The HSE incident illustrates that phishing can precede a ransomware attack and that consequences can include both encrypted files and copied information. Northbridge’s initial $90,000 portfolio was revised to $80,000 after the scenario changed. The revised plan gives priority to recovery remediation and identity protection, while transparently recording deferred treatments and unresolved risks.

Controls must be tested before their effectiveness is claimed. In particular, Northbridge’s failed restoration test prevents management from concluding that service recovery is adequate. Board oversight, named risk ownership, evidence-based reassessment and a documented review of residual risk are therefore essential.

## 11. References

Health Service Executive. (2025, December 1). *Cyber-attack and HSE response*. Government of Ireland. https://www2.hse.ie/services/cyber-attack/what-happened/

International Organization for Standardization. (2018). *ISO 31000:2018: Risk management—Guidelines*. https://www.iso.org/standard/65694.html

International Organization for Standardization. (2022). *ISO/IEC 27001:2022: Information security, cybersecurity and privacy protection—Information security management systems—Requirements*. https://www.iso.org/standard/27001

---

