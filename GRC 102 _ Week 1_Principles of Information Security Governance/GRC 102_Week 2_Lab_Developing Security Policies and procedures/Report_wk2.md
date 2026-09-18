# 🛡️ GRC102: Information Security Governance in Action

## NexusTech Solutions — Policy Overhaul Simulation

[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](#project-status)
[![Course](https://img.shields.io/badge/Course-GRC102-blue?style=for-the-badge)](#project-overview)
[![Discipline](https://img.shields.io/badge/Discipline-GRC-purple?style=for-the-badge)](#key-learning-outcomes)
[![Focus](https://img.shields.io/badge/Focus-Security%20Governance-orange?style=for-the-badge)](#task-1-governance-blueprint)

> **Full Practical Laboratory Report**
 
> **Prepared by:** Olubunmi Adesanmi
 
> **Course:** GRC102 – Information Security Governance

> **Module**  Module 2 – Developing Security Policies and Procedures
  
> **Assessment:** GRC102, Week 2 Practical Laboratory

> **Scenario role:**  Information Security Manager


---

## 📑 Table of Contents
- [Executive Summary](#executive-summary)
- [Project Overview](#project-overview)
- [Methodology](#methodology)
- [Project Objectives](#project-objectives)
- [Evidence Bundle 1: Security Policy Hierarchy](#evidence-bundle-1-security-policy-hierarchy)
- [Evidence Bundle 2: Acceptable Use Policy](#evidence-bundle-2-acceptable-use-policy)
- [Evidence Bundle 3: User Access Request Procedure](#evidence-bundle-3-user-access-request-procedure)
- [Evidence Bundle 4: Communication and Training Plan](#evidence-bundle-4-communication-and-training-plan)
- [Evidence Bundle 5: Policy Review and Maintenance Memo](#evidence-bundle-5-policy-review-and-maintenance-memo)
- [Key Learning Outcomes](#key-learning-outcomes)
- [Conclusion](#conclusion)
- [Frameworks and References](#frameworks-and-references)
- [Security and Privacy Notice](#security-and-privacy-notice)
- [Disclaimer](#disclaimer)
- [Project Status](#project-status)
- [References](#references)
- [Appendix A: Student Completion Checklist](#appendix-a-student-completion-checklist)

# Executive Summary

NexusTech Solutions has expanded from 50 to 250 employees while continuing to rely on a five-year-old “IT Rules” document that combines strategic intent, detailed configuration instructions and informal recommendations. This creates ambiguity over authority, inconsistent implementation and weak evidence of control operation. As the appointed Information Security Manager, this report establishes a structured, maintainable policy framework designed to improve governance, reduce operational risk and support the organisation’s ISO/IEC 27001 and SOC 2 readiness objectives.

The report contains five integrated evidence bundles. First, it defines the hierarchy of policy, standard, procedure and guideline documents and classifies eight draft statements. Second, it provides a complete Acceptable Use Policy governing company devices, networks, information and cloud services. Third, it translates access-control expectations into an actionable User Access Request Procedure. Fourth, it presents a role-based communication and training plan with acknowledgement, metrics and escalation. Fifth, it provides a policy review memo responding to an AWS migration and a personal-cloud sharing incident.

Together, the artefacts separate management intent from mandatory technical requirements, operational steps and advisory guidance. They also establish ownership, approval, exception, enforcement, evidence retention and review mechanisms. The recommended framework is risk-based, proportionate to a mid-sized software company and written for practical organisational use rather than as a purely theoretical response.

# 1. Evidence Bundle 1: Security Policy Hierarchy

## 1.1 Purpose and Governance Rationale

A clear documentation hierarchy prevents high-level governance requirements from being confused with technical instructions. It enables executive leaders to approve durable policy intent, control owners to set measurable standards, process operators to follow repeatable procedures and personnel to apply recommended guidance where judgement is appropriate. Each document type should have a named owner, approval route, version, effective date, review date and relationship to superior documents.

## 1.2 Hierarchy Definition Table

| **Document Type** | **Definition and Purpose** | **Authority / Approval** | **Nature** | **Typical Detail** |
|----|----|----|----|----|
| Policy | A high-level statement of management intent, principles and mandatory organisational requirements. It explains what must be achieved and why. | Executive management or delegated governance committee; owned by an accountable business or security leader. | Mandatory | Broad, stable and outcome-focused; avoids task-level configuration. |
| Standard | A mandatory, measurable requirement that supports a policy and creates consistent control baselines. | Approved by the policy owner or designated technical/governance authority. | Mandatory | Specific values, approved technologies, control thresholds and minimum requirements. |
| Procedure | A defined sequence of actions used to implement a policy or standard consistently. | Approved by the process owner and relevant control owner. | Mandatory when applicable | Operational, role-based and action-oriented; includes inputs, approvals, evidence and escalation. |
| Guideline | Recommended practices that help personnel make sound decisions when more than one acceptable approach exists. | Issued by a subject-matter expert or control owner. | Recommended unless adopted as mandatory | Advisory examples, preferred practices and context-sensitive advice. |

## 1.3 Categorisation of Existing Statements

| **No.** | **Statement** | **Classification** | **Justification** |
|----|----|----|----|
| 1 | All NexusTech employees must use MFA when accessing the corporate network remotely. | Policy | It states a mandatory, organisation-wide security outcome without prescribing configuration steps. |
| 2 | Download the Authenticator app, scan the QR code in the IT portal and enter the six-digit code. | Procedure | It provides an ordered sequence of actions for configuring MFA. |
| 3 | Developers are recommended to use parameterised queries to reduce SQL injection risk. | Guideline | The wording recommends a secure development practice rather than imposing a compulsory baseline. |
| 4 | NexusTech is committed to protecting the confidentiality, integrity and availability of all client data. | Policy | It expresses high-level management intent and the organisation’s security objective. |
| 5 | All corporate laptops must use BitLocker on Windows or FileVault on macOS for full-disk encryption. | Standard | It specifies a mandatory technical baseline and named approved technologies. |
| 6 | Employees should avoid public, unsecured Wi-Fi when travelling. | Guideline | It offers recommended risk-reduction behaviour rather than an absolute requirement. |
| 7 | For a suspected security breach, employees must immediately contact the IT Helpdesk at extension 5555. | Procedure | It identifies a triggering event and a required operational response channel. |
| 8 | Passwords must contain at least 14 characters including uppercase, lowercase, number and special character. | Standard | It defines measurable, mandatory password configuration criteria. |

## 1.4 Security Documentation Hierarchy Diagram

*The hierarchy below shows authority flowing from management intent to supporting control and operational documents.*

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr>
<th style="text-align: center;"><strong>INFORMATION SECURITY POLICY<br />
Management intent, principles and mandatory outcomes</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: center;"><strong>↓<br />
SECURITY STANDARDS<br />
Mandatory and measurable control requirements</strong></td>
</tr>
<tr>
<td style="text-align: center;"><strong>↓<br />
PROCEDURES<br />
Sequential actions that implement policies and standards</strong></td>
</tr>
<tr>
<td style="text-align: center;"><strong>↘ GUIDELINES<br />
Recommended practices that support informed judgement</strong></td>
</tr>
</tbody>
</table>

## 1.5 Document Governance Rules

- Every policy must identify its owner, approval authority, effective date, review date and associated standards or procedures.

- Standards and procedures must trace to at least one approved policy requirement.

- Mandatory language must use “must” or “shall”; advisory language should use “should” or “may”.

- Exceptions must be documented, risk-assessed, time-bound and approved by authorised roles.

- Superseded versions must be archived, and published versions must be available through a controlled repository.

# 2. Evidence Bundle 2: Acceptable Use Policy

## 2.1 Policy Document Control

| **Title** | Acceptable Use Policy |
|----|----|
| **Policy ID** | NTS-SEC-POL-001 |
| **Version** | 1.0 |
| **Policy Owner** | Information Security Manager |
| **Approval Authority** | Marcus Vance, CEO |
| **Effective Date** | 19 September 2026 |
| **Review Date** | 19 September 2027 |
| **Classification** | Internal |
| **Related Documents** | Information Security Policy; Access Control Standard; Incident Reporting Procedure; User Access Request Procedure |

## 2.2 Purpose

The purpose of this Acceptable Use Policy is to protect NexusTech Solutions, its clients, personnel and information assets by defining acceptable and prohibited use of company-provided devices, networks, systems, applications, cloud services and data. The policy aims to reduce malware, data leakage, legal, regulatory, contractual and operational risks while supporting appropriate business productivity.

## 2.3 Scope

This policy applies to all employees, contractors, consultants, interns, temporary workers, third parties and any other users authorised to access NexusTech information or technology resources. It applies whether access occurs from a corporate location, a home office, a client site or while travelling, and whether the resource is company-owned, personally owned but authorised, or supplied by a third party. It covers endpoints, networks, source-code repositories, messaging, email, collaboration tools, removable media, cloud services, internet access and client information.

## 2.4 Policy Principles

- NexusTech resources must be used primarily for legitimate business purposes and in a manner consistent with law, contracts and approved policies.

- Users must protect the confidentiality, integrity and availability of company and client information.

- Access is granted for authorised purposes and must not be shared, bypassed or used beyond assigned responsibilities.

- Security controls must not be disabled, evaded or altered without documented authorisation.

- Activity conducted through NexusTech resources may be logged, monitored and reviewed in accordance with applicable law and approved organisational processes.

## 2.5 Acceptable Use Requirements

- Users must use company systems only for authorised business activities and approved limited personal use.

- Users must authenticate using individually assigned credentials and approved multi-factor authentication where required.

- Users must lock unattended devices, protect devices from loss or damage and promptly report suspected compromise.

- Users must store, process and transmit company or client information only through approved repositories, applications and communication channels.

- Users must apply the information classification and handling requirements relevant to the data they access.

- Users must use only software, browser extensions, mobile applications and cloud services approved by IT or Security.

- Users must promptly install or permit centrally managed security updates and must not interfere with endpoint protection, encryption, logging or device-management controls.

- Users must report suspected phishing, malware, data exposure, unauthorised access, device loss or other security incidents immediately through the approved Helpdesk or incident-reporting channel.

- Users who access NexusTech resources remotely must use approved secure access methods and take reasonable steps to prevent observation or interception of sensitive information.

## 2.6 Prohibited Activities

- Installing or using unauthorised software, applications, browser extensions, peer-to-peer tools or unapproved cloud services.

- Uploading, synchronising or sharing company or client information through personal email, personal cloud storage, consumer file-sharing accounts or other unapproved services.

- Sharing passwords, authentication tokens, access cards or accounts, or allowing another person to act under the user’s identity.

- Disabling or circumventing security controls, including encryption, anti-malware, web filtering, logging, MFA, device management or access restrictions.

- Accessing, changing, copying, deleting or disclosing information without a legitimate business need and explicit authorisation.

- Using NexusTech resources to conduct unlawful activity, harassment, discrimination, fraud, copyright infringement or activity reasonably likely to damage the organisation or its clients.

- Attempting unauthorised security testing, vulnerability scanning, exploitation, interception or network monitoring. Authorised security testing must have written scope and approval.

- Connecting unapproved devices, storage media, wireless access points or network equipment to corporate systems.

- Sending confidential information to unintended recipients or using insecure methods when an approved secure method is required.

- Using corporate resources for external commercial ventures, political campaigning, excessive entertainment or activities that materially affect performance, capacity or cost.

## 2.7 Reasonable Personal Use

Limited personal use is permitted when it is occasional, lawful, does not interfere with work responsibilities, does not create material cost or security risk, does not consume excessive resources and does not conflict with any NexusTech policy. Users must not expect personal privacy when using company resources, subject to applicable law. Management may restrict or withdraw personal-use permission where operational, security, legal or performance concerns arise.

## 2.8 Data and Cloud Service Use

- Sensitive, confidential, regulated or client information must be processed only in locations and services approved for the applicable classification.

- Personal cloud storage and personal email accounts must not be used to store, transfer or share NexusTech or client information.

- External sharing must use approved collaboration services, authorised recipients, appropriate permissions and the minimum necessary information.

- Users must verify recipients, access settings and data classification before sharing information externally.

- NexusTech cloud resources, including AWS-hosted services, must be accessed and administered only through approved identities, roles, configurations and logging controls.

## 2.9 Roles and Responsibilities

| **Role** | **Responsibilities** |
|----|----|
| All Users | Read and acknowledge the policy; use resources appropriately; protect credentials and devices; complete training; report incidents and policy concerns. |
| Managers | Ensure personnel understand requirements; approve justified access; address non-compliance; support timely training and acknowledgement. |
| IT and Security | Publish approved controls; manage technical safeguards; monitor compliance; investigate alerts; maintain evidence; provide guidance and training. |
| Human Resources | Support onboarding, acknowledgement, disciplinary processes and consistent application of employment-related consequences. |
| Information Owners | Define classification and access requirements; approve access and external sharing where authorised; participate in reviews. |
| Information Security Manager | Own the policy; coordinate exceptions, monitoring, review and updates; report material concerns to governance bodies. |
| CEO / Approval Authority | Approve the policy and material revisions; support organisation-wide enforcement. |

## 2.10 Compliance, Monitoring and Enforcement

Compliance may be assessed through security monitoring, access reviews, configuration reviews, incident investigations, audit activity, training records and manager oversight. Monitoring must be authorised, proportionate and conducted in accordance with applicable law and NexusTech procedures. Suspected violations will be reviewed fairly and documented. Confirmed violations may result in retraining, access restriction, corrective action, disciplinary action, contract action, financial recovery where lawful, or referral to legal or law-enforcement authorities, depending on severity and applicable requirements.

## 2.11 Exceptions

Exceptions are permitted only where a documented business need exists and the risk is understood. Requests must identify the requirement, business justification, affected assets and data, duration, risk, compensating controls and accountable owner. The Information Security Manager and relevant information or system owner must review the request; higher-risk exceptions require executive or steering-committee approval. Every exception must have an expiry date, be recorded in the exception register and be reviewed before renewal. Emergency exceptions must be documented and retrospectively reviewed as soon as practicable.

## 2.12 Breach Reporting and Questions

Users must report suspected violations, accidental disclosures, lost devices and other security concerns immediately through the approved Helpdesk or incident-reporting channel. Questions about interpretation must be directed to the Information Security Manager. Good-faith reporting is encouraged and must be handled consistently with applicable organisational procedures.

## 2.13 Approval and Review

This policy becomes effective upon approval by Marcus Vance, CEO. The Information Security Manager will review it at least annually and earlier following a material security incident, significant technology or cloud change, legal or contractual change, audit finding, sustained non-compliance or a material change in organisational risk. Revised versions must follow stakeholder consultation, risk review, formal approval, controlled publication, communication and acknowledgement.

Approved by: Marcus Vance, CEO \| Signature: \_\_\_\_\_\_\_\_\_\_Marcus\_\_\_\_\vance_\_\_\_\_\_ \| Date: \_\_\_\_\_\_Sept 17 2026\_\_\_\_\_\_\_\_\_\_\_\_\_\_

# 3. Evidence Bundle 3: User Access Request Procedure

## 3.1 Procedure Control

| **Title** | User Access Request Procedure |
|----|----|
| **Procedure ID** | NTS-SEC-PRO-001 |
| **Version** | 1.0 |
| **Owner** | IT Service Manager |
| **Control Owner** | Information Security Manager |
| **Effective Date** | 19 September 2026 |
| **Review Date** | 19 September 2027 |
| **Applies To** | Joiner access, additional/change access, privileged access and approved emergency access |

## 3.2 Purpose

This procedure establishes a consistent, auditable process for requesting, approving, provisioning, verifying and recording user access to NexusTech systems. It reduces the risk of unauthorised or excessive permission by requiring approved workflow, role-based access, segregation of duties and least privilege.

## 3.3 Scope

The procedure applies to workforce identities and access to corporate applications, infrastructure, cloud environments, repositories, databases, collaboration services and client environments managed by NexusTech. It covers new access and changes to existing access. Access removal is governed by the related joiner-mover-leaver process but may be initiated where this procedure identifies obsolete or conflicting access.

## 3.4 Prerequisites and Authorised Roles

- An approved service-management ticket or access workflow is mandatory; informal email or chat alone is not sufficient.

- The requester must provide the user identity, employment or contract status, manager, system, requested role, business justification, required start date and access duration where temporary.

- The line manager must confirm business need. The information owner, data owner or system owner must approve access to restricted resources.

- Privileged or high-risk access requires Security review and any additional approval defined by the applicable access-control standard.

- Only authorised Helpdesk or system-administration personnel may provision access. Requesters and approvers must not provision their own access.

- Required systems include the approved ticketing platform, identity directory, target system, role catalogue, approval record and access log.

## 3.5 Sequential Procedure

| **Step** | **Action** | **Required Control / Evidence** |
|----|----|----|
| 1 | Receive and register the request | Confirm that the request arrived through the approved ticket or workflow. Assign a unique ticket number, date/time and request type. If received through email or chat, instruct the requester to submit the approved form and do not provision access. |
| 2 | Validate request completeness | Verify the user’s full identity, manager, department, employment status, system, requested role, business justification, start date, end date for temporary access and whether privileged access is requested. Return incomplete requests to the requester with the missing fields recorded. |
| 3 | Verify requester and identity status | Confirm that the user has an active and authorised workforce record or approved onboarding record. Confirm that the requester is authorised to request access for the named user. Record the evidence checked. |
| 4 | Confirm manager approval | Verify explicit approval from the user’s current manager within the workflow. The approval must identify the user, system and requested access. Do not accept ambiguous, forwarded or unverifiable approval. |
| 5 | Confirm information or system-owner approval | Where the system, data classification or role requires owner approval, verify that the authorised owner has approved the exact role and scope. Record the approver’s identity and timestamp. |
| 6 | Assess segregation of duties and risk | Check whether the requested access conflicts with the user’s current permissions, business role or prohibited combinations. Escalate conflicts to Security and the relevant owner. Do not provision until an approved resolution or documented exception exists. |
| 7 | Select the approved role | Use the current role catalogue or approved access profile. Choose the least-privileged role that supports the stated duties. Do not create custom or elevated permissions solely for convenience. |
| 8 | Create or update the account | Using an individually assigned administrator identity, create or update the user account in accordance with the applicable standard. Ensure the account is attributable to one user, uses approved authentication controls and has an appropriate status and expiry where temporary. |
| 9 | Assign permissions | Apply only the approved role and resource scope. For privileged access, use the approved privileged-access mechanism and enforce additional controls specified by Security. Record any system-generated identifiers. |
| 10 | Perform quality assurance | A second authorised technician or system owner must verify high-risk or privileged access. For standard access, the technician must compare the final permissions with the ticket before completion. Correct any variance immediately and record the check. |
| 11 | Notify the user and manager | Notify the user and manager that access has been provisioned. Provide the system name, approved role, effective date, support contact and any required training or first-use instructions. Do not transmit passwords or secrets through insecure channels. |
| 12 | Capture evidence | Attach or link the original request, approvals, role selected, segregation-of-duties result, provisioning log, administrator identity, timestamps, verification evidence, notifications, expiry date and exception reference where applicable. |
| 13 | Close the ticket | Confirm that all required fields and evidence are complete. Set the ticket to resolved or closed using the correct closure category. Retain the record according to the retention requirement and ensure temporary access is scheduled for review or expiry. |

## 3.6 Emergency and Exceptional Access

Emergency access may be used only where delay would materially affect safety, availability, incident response or critical business operations. The requester must identify the emergency, system, access required, accountable manager and expected duration. An authorised incident manager, system owner or senior manager must approve the request through the approved emergency workflow. Access must be least privilege, time-bound and monitored. The Helpdesk must record all actions and notify Security. Retrospective owner and Security review must occur promptly, and emergency access must be removed at the stated expiry unless formally extended.

Non-emergency exceptions to normal approval or role requirements must reference an approved policy exception. The technician must not create an exception. If no approved exception exists, pause the request and escalate it to the Information Security Manager.

## 3.7 Records Retention and Audit Trail

Access request records must be retained for the period defined in the NexusTech records-retention schedule and for no less than the period required by applicable legal, contractual and audit obligations. Records must be protected against unauthorised alteration and be searchable by user, system, approver, administrator, date and ticket number. Security and Internal Audit may sample tickets to verify approval, least privilege, segregation of duties, evidence completeness and timely expiry of temporary access.

## 3.8 Procedure Metrics

- Percentage of requests provisioned with complete approvals before access is granted.

- Percentage of sampled tickets with complete evidence and correct role assignment.

- Number of access requests returned because of missing information or invalid approval.

- Number and age of temporary or emergency access assignments past their approved expiry.

- Number of segregation-of-duties conflicts identified before provisioning.

# 4. Evidence Bundle 4: Communication and Training Plan

## 4.1 Objective and Approach

The rollout will make the Acceptable Use Policy visible, understandable, acknowledged and operational. Communication will be role-based and reinforced through training, manager oversight, practical reminders and measurable follow-up. The plan avoids relying on a single email and instead combines executive sponsorship, targeted learning, attestation and compliance reporting.

## 4.2 Audience Communication and Training Matrix

| **Audience** | **Key Message** | **Channel / Method** | **Owner** | **Timing** | **Acknowledgement** | **Success Measure** |
|----|----|----|----|----|----|----|
| All employees and contractors | Use NexusTech resources for authorised purposes; use approved services; protect credentials; report incidents; personal cloud storage is prohibited for company data. | CEO launch email, all-hands briefing, intranet policy page, mandatory LMS module and knowledge check. | Information Security Manager; HR Learning | Announcement Day 0; training Days 1–10; reminder Day 7. | Electronic policy attestation and LMS completion. | ≥95% completion and acknowledgement by Day 10; ≥80% knowledge-check score. |
| IT, Helpdesk and administrators | Enforce approved software, access, logging and exception requirements; use formal tickets; preserve evidence; escalate violations consistently. | Technical workshop, procedure walk-through, scenarios, job aid and team Q&A. | IT Service Manager; Security | Pre-launch Day -3; refresher Day 14. | Workshop attendance and scenario assessment. | 100% assigned staff trained; ≥90% scenario assessment; access tickets meet evidence requirements. |
| Managers and information owners | Model compliance, approve legitimate access and exceptions, monitor team completion and escalate repeated non-compliance. | Management briefing, manager toolkit, dashboard and weekly completion report. | Information Security Manager; HR | Day -2 briefing; weekly reports through Day 21. | Manager sign-off and team completion confirmation. | 100% managers briefed; departments reach target by Day 10. |
| Developers and engineering | Use approved development tools, repositories and cloud services; do not bypass controls; route testing and elevated access through authorised processes. | Engineering town hall, secure-development examples, intranet FAQ and team lead briefing. | Engineering Director; Security | Days 2–7; follow-up Day 21. | Targeted module and acknowledgement. | ≥95% completion; reduction in unapproved-tool findings. |
| HR and onboarding personnel | Embed policy distribution, training, acknowledgement and escalation in onboarding and workforce processes. | Process workshop, onboarding checklist and LMS assignment rule. | HR Director; Security | Before launch; monthly quality check. | Process owner sign-off. | 100% new starters assigned training; complete acknowledgement evidence. |
| Executive leadership | Sponsor policy, reinforce accountability, review risk and approve resources or material exceptions. | Executive briefing and steering dashboard. | Information Security Manager | Day -5 and Day 21. | Recorded approval and meeting action log. | Visible sponsorship; decisions and overdue actions recorded. |

## 4.3 Rollout Timeline

| **Stage** | **Timing** | **Activities** | **Output / Evidence** |
|----|----|----|----|
| Prepare | Day -10 to Day -5 | Publish controlled policy; configure LMS; prepare FAQs, manager toolkit, attestation and metrics dashboard. | Approved materials, LMS test evidence and distribution lists. |
| Leadership Alignment | Day -5 to Day -2 | Brief executives, managers, HR, IT and information owners; confirm escalation and exception routes. | Attendance, sign-offs and agreed responsibilities. |
| Launch | Day 0 | CEO announcement, policy publication and all-hands overview; training assignments issued. | Launch email, intranet record and training assignment report. |
| Train and Acknowledge | Days 1–10 | Complete role-based modules, workshops, knowledge checks and electronic attestation. | Completion, score and acknowledgement records. |
| Remind and Escalate | Days 7–14 | Automated reminders; manager follow-up; targeted support for failed checks or misunderstanding. | Reminder log, support records and overdue list. |
| Evaluate | Day 21 | Review effectiveness metrics, exceptions, incidents, queries and sampled behaviours; report findings. | Rollout dashboard and improvement actions. |
| Sustain | Quarterly and at onboarding | Refresher messages, onboarding assignment, targeted retraining and annual re-attestation. | Ongoing compliance trend and training evidence. |

## 4.4 Acknowledgement and Attestation

Each in-scope user must electronically attest that they have received, read and understood the AUP, agree to comply with it and understand where to ask questions or report concerns. The attestation record must identify the user, policy version, timestamp and completion status. Acknowledgement does not replace training. New starters must complete both within the onboarding period, and users must re-attest after material revisions.

## 4.5 Effectiveness Measures and Reporting

| **Measure** | **Target** | **Data Source** | **Action if Below Target** |
|----|----|----|----|
| Training completion | At least 95% by Day 10; 100% through escalation. | LMS completion report | Reminder, manager follow-up and access or HR escalation where authorised. |
| Policy acknowledgement | At least 95% by Day 10; 100% through escalation. | Attestation register | Direct follow-up and manager accountability. |
| Knowledge assessment | At least 80% pass mark; 90% for IT scenario assessment. | LMS and workshop results | Targeted retraining and reassessment. |
| Helpdesk evidence quality | At least 95% of sampled access tickets complete after stabilisation. | Ticket quality sample | Coaching, procedure clarification and corrective action. |
| Unauthorised software / cloud findings | Downward trend after rollout. | Endpoint, cloud and incident monitoring | Targeted communication, control tuning and investigation. |
| Policy questions and exception requests | Tracked by topic and resolved within assigned service levels. | Helpdesk and exception register | Update FAQs or policy wording where systemic confusion exists. |

## 4.6 Escalation and Remediation

Users who miss the initial deadline receive an automated reminder and are copied to their manager where appropriate. Continued non-completion is escalated to the department manager and HR for action consistent with employment and contractor processes. Failed knowledge checks trigger targeted retraining and reassessment. Repeated misunderstanding is addressed through manager coaching and role-specific guidance. Suspected violations are referred to Security for fair, evidence-based review. Material, deliberate or repeated non-compliance may lead to access restriction or disciplinary action under approved processes. Security will report trends and material issues to the Information Security Steering Committee without publicly naming individuals unless required for authorised case management.

# 5. Evidence Bundle 5: Policy Review and Maintenance Memo

## 5.1 Policy Review Memo

**MEMORANDUM**

| **To** | Information Security Steering Committee |
|----|----|
| **From** | Olubunmi Adesanmi, Information Security Manager |
| **Date** | 17 September 2027 |
| **Subject** | Review of Acceptable Use Policy Following AWS Migration and Personal-Cloud Sharing Incident |

The migration of NexusTech’s primary database to AWS is a material technology and service-delivery change that alters how identities, administrative privileges, data locations, logging and approved cloud services are governed. The incident involving a sensitive document shared through a personal cloud-storage account is also an early-review trigger because it demonstrates that existing acceptable-use expectations may be insufficiently explicit, insufficiently understood or inadequately reinforced. I therefore recommend an immediate, out-of-cycle review of AUP version 1.0 rather than waiting for the routine annual review.

The review should be led by the Information Security Manager with consultation from IT Operations, Cloud Engineering, Legal/Compliance, Human Resources, affected information owners, Internal Audit and representative business managers. The team should examine the AWS migration risk assessment and architecture decisions, access and logging evidence, the incident record and root-cause findings, relevant audit observations, exception records, training results and user feedback. Proposed revisions should be risk-assessed for operational impact, clarity and enforceability. At minimum, the AUP should expressly prohibit use of personal email and personal cloud-storage accounts for company or client information, require approved collaboration services and recipient/permission checks, and define acceptable use of AWS and other cloud services through authorised identities, roles and security controls.

As policy owner, the Information Security Manager should draft the revision and submit it to the Steering Committee for governance review before final approval by Marcus Vance, CEO. After approval, the revised version should be published through document control, communicated to all affected users and supported by targeted retraining and re-attestation. The AUP should be reviewed at least annually, with earlier review following a material security incident, major cloud or technology migration, significant legal or contractual change, audit finding, new high-risk service, sustained non-compliance or material change in organisational risk.

# Conclusion

This report replaces the conceptual weaknesses of NexusTech’s legacy “IT Rules” approach with a coherent governance structure. The documentation hierarchy establishes clarity over authority and detail; the AUP states enforceable expectations; the access procedure converts control intent into repeatable action; the rollout plan builds measurable adoption; and the review memo ensures the framework remains responsive to technology and incident-driven change.

Successful implementation will depend on visible executive sponsorship, controlled publication, role-based training, reliable evidence, proportionate enforcement and timely review. Management should approve the documents, assign responsible owners, implement the rollout plan and use the defined metrics to identify where clarification, control improvement or targeted support is required.

# References

International Cybersecurity and Digital Forensics Academy. (2026). GRC102 Week 2 Practical Laboratory: Developing Security Policies and Procedures. Course laboratory brief.

International Organization for Standardization. (2022). ISO/IEC 27001:2022, Information security, cybersecurity and privacy protection — Information security management systems — Requirements.

International Organization for Standardization. (2022). ISO/IEC 27002:2022, Information security, cybersecurity and privacy protection — Information security controls.

National Institute of Standards and Technology. (2024). The NIST Cybersecurity Framework (CSF) 2.0.

AICPA. Trust Services Criteria for Security, Availability, Processing Integrity, Confidentiality, and Privacy. Referenced conceptually for governance and control readiness.

*Note: Standards are cited at a high level. The report does not reproduce proprietary standards text or claim certification. NexusTech should confirm applicable legal, contractual and regulatory requirements before implementation.*

