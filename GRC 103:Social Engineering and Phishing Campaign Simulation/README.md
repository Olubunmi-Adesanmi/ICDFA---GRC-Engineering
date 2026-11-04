# GRC103 – Social Engineering & Phishing Campaign Simulation

> **Practical laboratory project | Governance, Risk and Compliance (GRC)**

## Project Overview

This project documents a controlled phishing-awareness simulation performed as part of the GRC103 Practical Laboratories.

The exercise demonstrates how a GRC professional can configure a phishing-simulation platform, monitor campaign events, calculate human-risk indicators, assess relevant security controls, and communicate practical recommendations to management.

The laboratory used **GoPhish v0.12.1** on **Kali Linux** and **MailHog** as a local SMTP email-capture service. A fictional VPN security-awareness landing page and fictional test identities were used. The landing page was configured without a password field, and password capture remained disabled.

## Objectives

- Understand the lifecycle of a controlled phishing-awareness simulation.
- Configure GoPhish and a local SMTP capture service.
- Create a fictional landing page and email template.
- Manage a fictional test-recipient group.
- Review email-open, link-click, and form-submission events.
- Calculate campaign metrics using clearly stated denominators.
- Evaluate potential preventive, detective, and corrective security controls.
- Produce evidence-based GRC findings and management recommendations.

## Laboratory Tools

| Component | Purpose |
|---|---|
| Kali Linux | Laboratory operating environment |
| GoPhish v0.12.1 | Campaign configuration and event monitoring |
| MailHog | Local SMTP email capture and inbox review |
| Mozilla Firefox | Access to GoPhish and MailHog interfaces |
| Fictional training landing page | Safe demonstration of form interaction |

## Campaign Metrics

The following figures represent the agreed final scenario for this report.

| Metric | Count | Rate |
|---|---:|---:|
| Campaign emails sent | 10 | 100% |
| Campaign emails delivered | 10* | 100% |
| Email-open events | 8 | 80% |
| Link-click events | 8 | 80% |
| Dummy-data submissions | 0 | 0% |
| Real passwords collected | 0 | Not applicable |

*The delivery count must be verified against the final MailHog campaign inbox, excluding the separate SMTP test email.*

### Metric Calculations

**Email Open Rate**

\[
\frac{8}{10}\times100=80\%
\]

**Click-Through Rate**

\[
\frac{8}{10}\times100=80\%
\]

**Dummy-Data Submission Rate**

\[
\frac{0}{8}\times100=0\%
\]

### Evidence Qualification

These are the agreed final-scenario figures for the report draft. Before treating them as verified observations, confirm that the final GoPhish campaign dashboard shows:

- 10 emails sent.
- 8 email-open events.
- 8 link-click events.
- 0 data submissions.

Also confirm that MailHog shows ten campaign messages, excluding the separate SMTP test email.

Earlier in the working session, a dashboard result of 11 sent, 9 opened, 9 clicked and 1 submitted was also reported. The two result sets must not be combined or substituted for each other.

If the final dashboard shows different counts, update the report and calculations to match the actual evidence. Do not alter screenshots to match the proposed figures.

## Key GRC Considerations

- Open events indicate tracking activity, not necessarily that a person carefully read or trusted a message.
- Click events indicate tracked link interaction; automated link scanning may affect results.
- The ten recipient identities were fictional and operated in a laboratory. They do not represent ten independently observed employees.
- The exercise did not test actual credential disclosure.
- Password capture was disabled, and no real passwords were collected.
- The results must not be used to claim that an organisation's security-awareness programme failed or succeeded without an appropriately authorised and representative assessment.

## Repository Contents

```text
GRC103_GitHub_Package/
│
├── README.md
│
├── GRC103_Phishing_Simulation_Report.md
│
└── evidence/
    └── README.md
```

## Evidence to Add

Place genuine, readable screenshots in the `evidence/` directory.

| Filename | Evidence Description |
|---|---|
| `01-gophish-dashboard.png` | GoPhish administration dashboard or startup |
| `02-sending-profile.png` | MailHog sending-profile configuration; hide secrets |
| `03-mailhog-test-email.png` | Separate SMTP test email in MailHog |
| `04-landing-page.png` | Fictional landing-page configuration showing password capture disabled |
| `05-email-template.png` | Email template and GoPhish variables |
| `06-test-user-group.png` | Ten fictional recipients |
| `07-campaign-configuration.png` | Campaign configuration |
| `08-mailhog-campaign-inbox.png` | Campaign messages received in MailHog |
| `09-campaign-results.png` | Final GoPhish campaign results |
| `10-landing-page-display.png` | Fictional training page, if captured |
| `11-acknowledgement-page.png` | Local acknowledgement page, if used |

Add screenshots only after capturing them. Do not create mock screenshots or edit evidence counts.

Remove or obscure SMTP credentials, tokens, passwords, personal information and other secrets before committing evidence.

## How to Use This Repository

1. Read this README for the project overview and evidence requirements.
2. Read [`GRC103_Phishing_Simulation_Report.md`](GRC103_Phishing_Simulation_Report.md) for the detailed methodology, campaign metrics, risk assessment and management recommendations.
3. Add genuine screenshots to the `evidence/` directory.
4. Link the relevant screenshots from the detailed report.
5. Reconcile all campaign counts against the final GoPhish dashboard and MailHog inbox.
6. Replace any bracketed placeholders with verified information before submission.

## Scope and Safety

This repository documents a controlled academic laboratory exercise using fictional identities and a fictional training page.

It does not provide authorisation to target real users or systems.

No real credentials were collected. Password capture was disabled throughout the exercise.

The simulation should only be repeated in environments for which the operator has appropriate permission.

## Author

**Student:** Adesanmi Bunmi  
**Course:** GRC103 – Practical Laboratories  
**Assessment:** Social Engineering & Phishing Campaign Simulation

---

*This project demonstrates practical exposure to phishing simulation, campaign monitoring, quantitative risk analysis, security-control evaluation and professional GRC reporting.*
