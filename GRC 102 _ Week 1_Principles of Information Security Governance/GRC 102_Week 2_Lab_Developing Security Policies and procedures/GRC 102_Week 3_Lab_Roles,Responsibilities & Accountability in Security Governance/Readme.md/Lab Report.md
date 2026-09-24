
# GRC102 – Information Security Governance
## Week 3 Laboratory Report
### TechGlobal Security Governance Redesign

Prepared by: [Student Name]  
Registration Number: [Registration Number]  
Programme: GRC Engineering  
Course: GRC102 – Information Security Governance  
Role: Lead Security Governance Consultant  
Submission Date: 25 September 2026  

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Introduction and Laboratory Context](#2-introduction-and-laboratory-context)
3. [Governance Design Principles](#3-governance-design-principles)
4. [Task 1 – Governance Architecture and Stakeholder Map](#4-task-1--governance-architecture-and-stakeholder-map)
5. [Task 2 – Governance Responsibility and Authority Matrix](#5-task-2--governance-responsibility-and-authority-matrix)
6. [Task 3 – Security Governance Committee Ecosystem](#6-task-3--security-governance-committee-ecosystem)
7. [Task 4 – RACI Accountability Matrix](#7-task-4--raci-accountability-matrix)
8. [Task 5 – Cyber-Risk Escalation and Segregation of Duties](#8-task-5--cyber-risk-escalation-and-segregation-of-duties)
9. [Implementation Roadmap](#9-implementation-roadmap)
10. [Expected Governance Outcomes](#10-expected-governance-outcomes)
11. [Conclusion](#11-conclusion)
12. [References and Framework Alignment](#12-references-and-framework-alignment)
13. [Appendices](#13-appendices)

---

## 1. Executive Summary

TechGlobal is a rapidly growing technology organisation with approximately 2,500 employees operating across five global offices. Although the organisation’s revenue and product adoption are increasing, its security governance arrangements have not matured at the same rate. Security decisions are largely concentrated with the IT Director, business units make inconsistent security decisions, formal governance committees are absent, and executive and Board visibility of cyber risk is limited.

This report presents a redesigned security governance model intended to move TechGlobal from an informal, IT-centric approach to a structured, business-aligned and accountable governance model.

The proposed model establishes clear separation between Board oversight, executive accountability, enterprise risk management, security governance, legal and regulatory advice, financial governance, people governance, technology delivery, and business-unit ownership.

The proposed governance structure introduces an Executive Security Council, a Security Governance Steering Committee, and a specialised Cyber Incident and Response Working Group. These forums create defined channels through which operational issues can be reviewed, escalated and resolved.

The report also establishes explicit responsibilities for the Board, CEO, CISO, CRO/Risk, Legal, Finance, HR, IT and Business Unit Leaders. A RACI model is used to clarify responsibility and accountability for fifteen critical governance activities.

A three-level cyber-risk escalation model is proposed: Level 1 – Operational; Level 2 – Executive; and Level 3 – Material/Board.

Finally, the report identifies segregation-of-duties weaknesses created by the current IT-centric model and proposes practical controls such as independent risk acceptance, separation between control implementation and assurance, cross-functional approval, independent legal assessment and Board-level oversight of material risk.

---

## 2. Introduction and Laboratory Context

TechGlobal is experiencing rapid organisational growth, increased revenue and increased product adoption. However, security governance has not developed at the same pace.

The current environment has several characteristics:

- security decisions are concentrated with the IT Director;
- there is no formal governance committee structure;
- business units make local security decisions inconsistently;
- security ownership is unclear;
- risk acceptance authority is not clearly separated from operational responsibility;
- the CEO and Board receive limited cyber-risk visibility; and
- escalation pathways are not formally defined.

The purpose of this report is to provide a complete security governance redesign for TechGlobal covering governance architecture, responsibility and authority, committee governance, RACI accountability, cyber-risk escalation and segregation of duties.

---

## 3. Governance Design Principles

### 3.1 Business Ownership
Cybersecurity should not be treated exclusively as an IT responsibility. Business units that own processes, systems, services and information should also own the business risks associated with those activities.

### 3.2 Clear Accountability
Every material governance decision should have a clearly identified accountable role. Responsibility may be distributed, but accountability should not be ambiguous.

### 3.3 Independent Risk Oversight
The individual or function responsible for implementing a security control should not independently approve the risk created by failure of that control.

### 3.4 Proportionate Governance
Governance should be strong enough to manage TechGlobal’s scale and complexity without creating unnecessary approval layers.

### 3.5 Escalation by Materiality
Not every security event should reach executives or the Board. Escalation should be based on defined criteria such as business impact, customer impact, regulatory exposure, financial exposure, operational disruption, data sensitivity and strategic significance.

### 3.6 Evidence-Based Decisions
Important security decisions should be supported by documented evidence, including risk assessments, recommendations, approvals, decision rationale, action owners and review dates.

### 3.7 Cross-Functional Decision Making
Security decisions with significant business, legal, financial, people or technology implications should involve the appropriate functions rather than being made by one department.

---

## 4. Task 1 – Governance Architecture and Stakeholder Map

### 4.1 Current-State Governance Assessment
TechGlobal’s current model can be described as an informal governance structure centred around the IT function. The IT Director effectively performs several different functions: security owner, risk decision-maker, operational decision-maker, technology authority and escalation point.

### 4.2 Governance Gap Assessment

| No. | Governance Weakness | Business/Risk Consequence | Required Improvement |
| --- | --- | --- | --- |
| 1 | Security authority concentrated in IT | Excessive concentration of decision-making and limited independent challenge | Establish CISO-led security governance with executive and Board oversight |
| 2 | No formal governance committees | Security decisions may be inconsistent and poorly coordinated | Establish Executive Security Council and Security Governance Steering Committee |
| 3 | Unclear risk acceptance authority | Risks may be accepted by people without appropriate authority | Define risk acceptance thresholds and delegated authority |
| 4 | Business units make inconsistent decisions | Different security practices and control maturity across the organisation | Establish common enterprise policies and governance standards |
| 5 | Limited Board visibility | Board may not have sufficient information about material cyber risks | Introduce regular Board cyber-risk reporting |
| 6 | Weak segregation of duties | The same person may implement, approve and assess controls | Separate implementation, risk acceptance and assurance |
| 7 | Informal escalation | Material issues may not reach executives quickly enough | Implement defined cyber-risk escalation thresholds |
| 8 | Limited cross-functional involvement | Legal, Finance, HR and business risks may be overlooked | Establish cross-functional governance committees |
| 9 | Unclear decision trail | Difficult to demonstrate why major security decisions were made | Establish formal decision logs and evidence requirements |
| 10 | Lack of structured governance cadence | Risk management becomes reactive rather than continuous | Introduce monthly, quarterly and annual governance activities |

### 4.3 Stakeholder Map

| Stakeholder | Authority / Influence | Primary Interest | Information Needed | Governance Contribution |
| --- | --- | --- | --- | --- |
| Board of Directors | Very High | Enterprise risk, resilience, reputation and accountability | Material cyber risks, trends, major incidents, risk acceptance, assurance | Provides oversight, challenges management and monitors material risk |
| CEO | Very High | Business performance, strategic risk and growth | Strategic cyber risks, significant incidents, investment needs | Provides executive accountability and resolves major business conflicts |
| CISO | High | Security governance and programme effectiveness | Security risk, controls, incidents, vulnerabilities, compliance | Leads security governance, strategy, policy and reporting |
| CRO / Risk | High | Enterprise risk integration | Cyber-risk exposure, risk treatment and accepted risks | Provides independent risk methodology and aggregation |
| Legal / Compliance | High | Regulatory and contractual exposure | Incidents, data exposure, obligations and evidence | Provides legal/regulatory advice and notification guidance |
| Finance | High | Financial exposure and investment | Cyber losses, security budget, investment priorities | Supports financial decisions, budgeting and loss analysis |
| Human Resources | Medium/High | People risk and workforce controls | Joiner/mover/leaver issues, awareness and conduct | Supports people-related security governance |
| IT / Technology | High | Secure technology delivery and continuity | Architecture, vulnerabilities, incidents and technology risks | Implements and operates technical controls |
| Business Unit Leaders | High | Business performance and operational continuity | Risks affecting their processes, systems and customers | Own business risks and implement required controls |

### 4.4 Proposed Security Governance Organisation Structure

```text
BOARD OF DIRECTORS
      |
      v
CEO
  +-----+-----+
  v           v
CRO/Risk    CISO
  v           v
Executive Security Council
    |
    v
Security Governance Steering Committee
    +-------+-------+
    |               |
    v               v
IT          Legal      Finance/HR
    |
    v
Cyber Incident & Response Working Group
    |
    v
Business and Technology Owners
