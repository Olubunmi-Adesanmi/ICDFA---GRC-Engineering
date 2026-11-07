# GRC103 – Social Engineering & Phishing Campaign Simulation

> **Risk Assessment And Management Technique**

## Lab Overview

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

8/10 x 100=80%

**Click-Through Rate**

8/10x100=80%

**Dummy-Data Submission Rate**

0/8x 100=0%


## Repository Contents

```text
GRC103_GitHub_Package/
│
├── README.md
│
├── GRC103_Phishing_Simulation_Report.md
|
|__Report Pdf
|
|__Screenshots
│
└── evidence/
    └── README.md
```

## Scope and Safety

This repository documents a controlled academic laboratory exercise using fictional identities and a fictional training page.

It does not provide authorisation to target real users or systems.

No real credentials were collected. Password capture was disabled throughout the exercise.

The simulation should only be repeated in environments for which the operator has appropriate permission.

## Author

**Student:** Adesanmi Bunmi 
**Registration Number** C11/26/CGRCE/17550
**Course:** GRC103 – Risk Assessment And Management Techniques
**Assessment:** Social Engineering & Phishing Campaign Simulation

---


