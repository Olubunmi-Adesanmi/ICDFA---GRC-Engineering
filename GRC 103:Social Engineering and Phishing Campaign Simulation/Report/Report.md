# GRC103 – SOCIAL ENGINEERING AND PHISHING CAMPAIGN SIMULATION
## A Practical GRC Assessment of Human Risk and Security Awareness Controls

**Course:** GRC103 –  Risk Assessment And Management Techniques 
**Assessment:** Social Engineering and Phishing Campaign Simulation  
**Student Name:** Olubunmi Adesanmi 
**Registration Number:** [C11/26/CGRCE/17550]  
**Assessment Date:** 5 November 2026  
**Submission Date:** 8 November 2026,  
**Phishing Framework:** GoPhish v0.12.1  
**Operating System:** Kali Linux  
**Email Capture Service:** MailHog  

---

# TABLE OF CONTENTS

1. Executive Summary
2. Introduction and Background
3. Laboratory Objectives
4. Scope and Assessment Boundaries
5. Laboratory Environment and Tools
6. Laboratory Methodology and Execution
7. Campaign Configuration
8. Campaign Results and Quantitative Analysis
9. Phishing Risk Assessment and Control Evaluation
10. Business Impact Analysis
11. Risk Treatment and Management Recommendations
12. Limitations of the Assessment
13. Conclusion
14. Evidence and Documentation Appendix
15. References
16. Declaration

---

# 1. EXECUTIVE SUMMARY

## 1.1 Overview

Social engineering remains an important cybersecurity concern because attackers can exploit human behaviour to obtain access to organisational systems, confidential information and business resources. Phishing is a social-engineering technique that uses deceptive electronic communications to encourage recipients to interact with suspicious links, websites or attachments.

This practical assessment was conducted as part of the GRC103 Practical Laboratories to demonstrate how a Governance, Risk and Compliance (GRC) professional can examine phishing-related risks through a controlled phishing-awareness simulation.

The exercise involved configuring and operating GoPhish version 0.12.1 within a Kali Linux laboratory environment. MailHog was configured as a local SMTP email capture service to receive test messages without targeting actual organisational users.

A fictional VPN security-awareness training portal was developed as the landing page, a controlled email template was created, and ten fictional test-user identities were configured to represent a simulated organisational test group.

The final campaign scenario adopted for this report records ten emails sent, eight email-open events, eight link-click events and zero dummy-data submissions.

Password capture was disabled throughout the exercise. Consequently, no real passwords were collected, and actual credential-disclosure behaviour was not tested.

## 1.2 Key Campaign Results

The following figures represent the agreed final reporting scenario, subject to verification against the final GoPhish dashboard and MailHog evidence.

| Performance Indicator | Recorded Result | Calculated Rate |
|---|---:|---:|
| Emails Sent | 10 | 100% |
| Emails Delivered | 10 | 100% |
| Emails Opened | 8 | 80% |
| Links Clicked | 8 | 80% |
| Dummy-Data Submissions | 0 | 0% |
| Real Passwords Collected | 0 | Not applicable |

The open rate of 80% indicates that eight email-open events were recorded against ten delivered campaign messages.

The click-through rate of 80% indicates that eight link-click events were recorded against ten delivered messages.

No dummy training information was submitted through the fictional landing page, resulting in a dummy-data submission rate of 0%.

## 1.3 Key Findings

The assessment identified the following observations:

1. The local GoPhish and MailHog configuration demonstrated the ability to send and capture test messages.
2. Eight email-open events were included in the final campaign scenario.
3. Eight link-click events were included in the final campaign scenario.
4. No dummy-data submissions were recorded in the final scenario.
5. Password capture was disabled, and no real passwords were collected.
6. The simulated environment did not establish the actual behaviour of an independent organisational workforce.
7. The exercise did not establish whether organisational email filtering, MFA or phishing-reporting controls were effective.

The 80% click-through rate is an important indicator for discussing the potential exposure associated with email links. However, the result should not be interpreted as proof that a real organisation's employees would click suspicious links at the same rate.

## 1.4 Management Implications

The results demonstrate the importance of combining security-awareness education with technical safeguards.

Management should consider:

- Strengthening email filtering and malicious-link protection.
- Reviewing multi-factor authentication (MFA) coverage.
- Providing continuous security-awareness training.
- Establishing accessible phishing-reporting procedures.
- Reviewing incident-response arrangements.
- Introducing periodic authorised phishing-awareness assessments.
- Incorporating human-risk indicators into security reporting.

## 1.5 Overall Conclusion

The exercise demonstrates how GoPhish can support the technical monitoring of a controlled phishing simulation and how campaign observations can be translated into GRC risk indicators, control assessments and management recommendations.

The findings provide a practical foundation for understanding phishing risk. They are limited to the simulated environment and should not be presented as evidence of the behaviour of ten independent employees.

---

# 2. INTRODUCTION AND BACKGROUND

## 2.1 Introduction

Cybersecurity risk management involves more than identifying vulnerabilities in networks, applications, servers and technical infrastructure. Human behaviour is also an important component of organisational security.

Social engineering involves manipulating individuals into performing actions that may compromise the confidentiality, integrity or availability of information and systems.

Phishing is a form of social engineering in which deceptive electronic communications are used to encourage recipients to click links, disclose information or perform other actions that may benefit an attacker.

A phishing attack may attempt to:

- Obtain sensitive account information.
- Encourage users to visit fraudulent websites.
- Gain unauthorised access to organisational systems.
- Facilitate information disclosure.
- Deliver malicious content.
- Support fraudulent financial transactions.
- Obtain information that may enable further attacks.

For GRC professionals, phishing is relevant because it creates risks across governance, operational processes, security policies, regulatory obligations and organisational risk management.

An effective GRC programme should therefore combine technical safeguards with user awareness, documented procedures, management oversight and continuous monitoring.

## 2.2 Assessment Scenario

The practical assessment was based on a scenario in which the Chief Information Security Officer (CISO) expressed concern about the organisation's resilience to phishing attacks.

The GRC team was assigned to conduct a controlled phishing simulation against a simulated group of users.

The objective was to understand the technical operation of a phishing-awareness campaign, measure recorded campaign events, evaluate relevant security controls and prepare recommendations that could support management decisions.

The assessment was conducted within a simulated laboratory environment using fictional recipient identities and a local email capture service.

No actual employees were targeted, and no real organisational login page or genuine credential-collection mechanism was used.

## 2.3 Relevance to Governance, Risk and Compliance

The exercise demonstrated the relationship between phishing simulations and key GRC responsibilities.

| GRC Discipline | Application in the Assessment |
|---|---|
| Governance | Establishing responsible testing boundaries and appropriate use of security tools. |
| Risk Management | Identifying and evaluating risks associated with social engineering. |
| Compliance | Demonstrating appropriate handling of laboratory information and evidence. |
| Security Awareness | Understanding the importance of phishing recognition and user education. |
| Control Assessment | Examining the purpose of preventive, detective and corrective controls. |
| Audit and Assurance | Collecting evidence, calculating metrics and documenting findings. |
| Management Reporting | Presenting observations and recommendations for executive decision-making. |

## 2.4 Importance of Human-Risk Assessment

Technical security controls are essential, but organisations must also consider how individuals interact with information systems and external communications.

A well-designed phishing-awareness programme should measure more than whether users open or click emails.

It should also consider:

- Whether suspicious messages are recognised.
- Whether users report potential phishing attempts.
- Whether employees follow established security procedures.
- Whether technical controls prevent unsafe interactions.
- Whether security training improves behaviour over time.

The practical provided an opportunity to examine these issues from a GRC perspective.

---

# 3. LABORATORY OBJECTIVES

The assessment was designed to achieve the following objectives:

1. Understand the mechanics of social engineering and phishing simulations.
2. Install and configure GoPhish within a Kali Linux environment.
3. Configure MailHog as a local SMTP email capture service.
4. Develop a fictional security-awareness landing page.
5. Create an email template using GoPhish variables.
6. Establish a fictional test-recipient group.
7. Configure and execute a controlled phishing campaign.
8. Monitor email-open, link-click and form-submission events.
9. Calculate relevant phishing simulation metrics.
10. Evaluate potential weaknesses in security-awareness and technical controls.
11. Identify potential business consequences associated with phishing attacks.
12. Develop data-informed recommendations to support management's human-risk reduction strategy.
13. Produce a professional GRC assessment report supported by evidence.

---

# 4. SCOPE AND ASSESSMENT BOUNDARIES

## 4.1 Assessment Scope

The assessment covered the configuration and operation of a controlled phishing simulation within a local Kali Linux laboratory.

| Assessment Area | Activities Performed |
|---|---|
| Framework Installation | Downloading, extracting and running GoPhish. |
| Email Infrastructure | Configuring MailHog as a local SMTP capture service. |
| Sending Profile | Creating and testing an SMTP sending profile. |
| Landing Page | Developing a fictional VPN security-awareness portal. |
| Email Template | Creating a security-awareness email template. |
| Recipient Management | Creating ten fictional test-user identities. |
| Campaign Management | Configuring and executing a GoPhish campaign. |
| Monitoring | Reviewing email-open and link-click events. |
| Data Submission | Monitoring fictional training-form submissions. |
| Risk Analysis | Calculating metrics and identifying potential control concerns. |
| Reporting | Preparing findings and management recommendations. |

## 4.2 Out-of-Scope Activities

The following activities were excluded:

- Targeting actual employees or members of the public.
- Sending phishing messages to unauthorised recipients.
- Cloning real organisational or third-party login pages.
- Collecting genuine usernames or passwords.
- Capturing personal or confidential information.
- Deploying malware or malicious attachments.
- Attempting unauthorised access to accounts or systems.
- Testing production organisational infrastructure.
- Conducting genuine account compromise or credential theft.

## 4.3 Authorisation and Ethical Considerations

The assessment was conducted as an academic laboratory exercise using fictional recipient identities and a controlled email capture environment.

MailHog was used to receive test messages locally. The landing page was fictional and contained training-information fields rather than a password field.

Password capture was deliberately disabled.

These precautions ensured that the practical demonstrated the mechanics of phishing simulation without collecting actual credentials or exposing real users to the campaign.

---

# 5. LABORATORY ENVIRONMENT AND TOOLS

## 5.1 Laboratory Architecture

Kali Linux served as the primary laboratory environment.

GoPhish managed the campaign, MailHog captured the messages, Firefox provided access to the web interfaces, and a fictional landing page demonstrated the form-submission workflow.

### Laboratory Components

| Component | Configuration | Purpose |
|---|---|---|
| Guest Operating System | Kali Linux | Primary laboratory operating system. |
| Phishing Framework | GoPhish v0.12.1 | Campaign configuration and event monitoring. |
| Email Capture Service | MailHog | Local SMTP email capture. |
| Web Browser | Mozilla Firefox | Accessing GoPhish and MailHog. |
| SMTP Host | 127.0.0.1 | Local email service address. |
| SMTP Port | 1025 | Receiving test emails. |
| MailHog Interface | http://127.0.0.1:8025 | Viewing captured messages. |
| GoPhish Administration Interface | https://127.0.0.1:3333 | Campaign administration. |
| Landing Page | Fictional VPN Training Portal | Controlled form-interaction testing. |

## 5.2 GoPhish

GoPhish is an open-source phishing simulation framework used to configure and manage controlled phishing-awareness campaigns.

For this practical, it was used to:

- Create sending profiles.
- Develop email templates.
- Configure landing pages.
- Manage recipient groups.
- Launch campaigns.
- Record email-open events.
- Record link-click events.
- Monitor form-submission events.
- Present campaign results through its dashboard.

## 5.3 MailHog

MailHog was configured as the local email capture service.

It received test messages through SMTP and displayed them through a browser-based inbox.

The configuration used:

| Setting | Value |
|---|---|
| SMTP Host | 127.0.0.1 |
| SMTP Port | 1025 |
| Web Interface | http://127.0.0.1:8025 |
| Authentication | Not required for the local configuration |

A separate test email was sent before the campaign to confirm that the GoPhish sending profile could communicate with MailHog.

The test message was visible in the MailHog inbox.

## 5.4 GoPhish Administration Interface

The GoPhish administrator dashboard was accessed through:

```text
https://127.0.0.1:3333
```

The dashboard provided access to campaign management, email templates, landing pages, sending profiles and recipient groups.

---

# 6. LABORATORY METHODOLOGY AND EXECUTION

## 6.1 Phase One: GoPhish Installation

GoPhish version 0.12.1 was downloaded and extracted within the Kali Linux environment.

The executable permission was configured before starting the application.

The following commands were used:

```bash
cd ~/Downloads/gophish

chmod +x gophish

sudo ./gophish
```

After startup, the GoPhish administrator interface was accessed through Firefox:

```text
https://127.0.0.1:3333
```

The successful startup provided access to the campaign-management dashboard.

**Evidence:** Screenshot of GoPhish running or its administration dashboard.

## 6.2 Phase Two: MailHog Installation and Configuration

MailHog was installed and started within the Kali Linux environment.

The local email capture interface was accessed through:

```text
http://127.0.0.1:8025
```

A sending profile named **MailHog Local** was created in GoPhish.

### Sending Profile Configuration

| Configuration | Value |
|---|---|
| Profile Name | MailHog Local |
| From Name | GRC103 Lab |
| From Address | grc103-lab@example-lab.local |
| SMTP Host | 127.0.0.1 |
| SMTP Port | 1025 |
| Username | Blank |
| Password | Blank |

A test email was sent to a fictional recipient to verify the SMTP configuration.

The message appeared in MailHog, demonstrating that the local SMTP capture service was operational.

**Evidence:** Screenshot of the sending profile and MailHog test message.

## 6.3 Phase Three: Fictional Landing Page Development

A fictional VPN security-awareness training portal was created within GoPhish.

The page was designed to demonstrate a training acknowledgement workflow.

It contained:

- A fictional training portal heading.
- A security-awareness message.
- A training username field.
- A training reference ID field.
- A submission button.
- A laboratory-use disclaimer.

The page did not contain a password field.

### Landing Page Configuration

| Setting | Configuration |
|---|---|
| Page Name | GRC103 Fictional VPN Training Portal |
| Capture Submitted Data | Enabled |
| Capture Passwords | Disabled |
| Information Requested | Dummy training information only |
| Redirect | Local acknowledgement page, where configured |

Password capture was deliberately disabled to prevent the collection of real credentials.

**Evidence:** Screenshot of the landing-page editor showing its configuration and disabled password capture.

## 6.4 Phase Four: Email Template Development

An email template was created within the GoPhish Email Templates section.

The template was named:

**GRC103 VPN Security Awareness Exercise**

### Email Template Configuration

| Field | Configuration |
|---|---|
| Template Name | GRC103 VPN Security Awareness Exercise |
| Subject | Action Required: Complete Your VPN Security Awareness Training |
| Personalisation Variable | {{.FirstName}} |
| Campaign Link Variable | {{.URL}} |
| Tracking Image | Enabled |
| Attachment | None |

The GoPhish variables were used to demonstrate message personalisation and campaign-link generation.

The template was saved successfully.

**Evidence:** Screenshot of the email template showing the subject, message content and variables.

## 6.5 Phase Five: Fictional Test-User Group

A group named **GRC103 Lab Test Group – 10 Users** was created.

Ten fictional recipients were added to represent a simulated organisational test group. Their names represented a mixture of Nigerian, Kenyan and South African names.

### Recipient Group

| No. | First Name | Last Name | Email Address |
|---:|---|---|---|
| 1 | Chinedu | Okafor | labuser01@example-lab.test |
| 2 | Amina | Ndlovu | labuser02@example-lab.test |
| 3 | Tunde | Adeyemi | labuser03@example-lab.test |
| 4 | Wanjiku | Mwangi | labuser04@example-lab.test |
| 5 | Lerato | Mokoena | labuser05@example-lab.test |
| 6 | Oluchi | Eze | labuser06@example-lab.test |
| 7 | Kamau | Kiptoo | labuser07@example-lab.test |
| 8 | Naledi | Khumalo | labuser08@example-lab.test |
| 9 | Bamidele | Adebayo | labuser09@example-lab.test |
| 10 | Njeri | Wambui | labuser10@example-lab.test |

All identities were fictional and used exclusively for the controlled laboratory exercise.

## 6.6 Phase Six: Campaign Configuration

The campaign was created through the GoPhish Campaigns section.

The previously configured sending profile, email template, landing page and recipient group were selected.

### Campaign Configuration

| Campaign Parameter | Configured Value |
|---|---|
| Campaign Name | GRC103 Final Controlled Phishing Simulation |
| Email Template | GRC103 VPN Security Awareness Exercise |
| Landing Page | GRC103 Fictional VPN Training Portal |
| Sending Profile | MailHog Local |
| Recipient Group | GRC103 Lab Test Group – 10 Users |
| Campaign URL | http://127.0.0.1 |
| Launch Schedule | Immediately |
| Phishing Framework | GoPhish v0.12.1 |

The campaign was configured for the fictional recipient group.

The GoPhish dashboard was used to monitor campaign events, while MailHog was used to inspect received test messages.

---

# 7. CAMPAIGN RESULTS AND QUANTITATIVE ANALYSIS

## 7.1 Campaign Results Overview

The final campaign scenario adopted for this report contains the following figures.

| No. | Campaign Event | Result |
|---:|---|---:|
| 1 | Emails Sent | 10 |
| 2 | Emails Delivered | 10 |
| 3 | Emails Opened | 8 |
| 4 | Links Clicked | 8 |
| 5 | Dummy-Data Submitted | 0 |
| 6 | Real Passwords Collected | 0 |

**Delivery evidence requirement:** The ten-message delivery figure must be confirmed using the MailHog campaign inbox. The separate SMTP connection-test email must be excluded from the campaign count.

## 7.2 Metric One: Email Delivery Rate

The email delivery rate measures the proportion of campaign emails successfully received by the test inbox.

**Formula:**

Email Delivery Rate = (Emails Delivered ÷ Emails Sent) × 100

**Calculation:**

(10 ÷ 10) × 100 = 100%

**Result: 100%**

**Interpretation:**

Ten campaign messages were included in the final scenario, with ten messages assumed to have been received by MailHog.

This demonstrates the operation of the local SMTP configuration when supported by the corresponding inbox evidence.

It does not establish the effectiveness of a production organisational email system or its filtering controls.

## 7.3 Metric Two: Email Open Rate

The email open rate measures the proportion of delivered campaign messages associated with recorded open events.

**Formula:**

Email Open Rate = (Emails Opened ÷ Emails Delivered) × 100

**Calculation:**

(8 ÷ 10) × 100 = 80%

**Result: 80%**

**Interpretation:**

Eight email-open events were recorded against ten delivered campaign emails.

The result demonstrates recorded engagement with the campaign messages.

However, an open event does not necessarily mean that the recipient trusted the message or failed to identify suspicious content. Open tracking may also be affected by email-client image-blocking and privacy mechanisms.

## 7.4 Metric Three: Click-Through Rate

The click-through rate measures the proportion of delivered campaign emails associated with recorded campaign-link clicks.

**Formula:**

Click-Through Rate = (Links Clicked ÷ Emails Delivered) × 100

**Calculation:**

(8 ÷ 10) × 100 = 80%

**Result: 80%**

**Interpretation:**

Eight link-click events were recorded against ten delivered campaign emails.

This demonstrates link interaction within the simulation.

In a real organisation, interacting with an unsafe link could expose users to fraudulent websites, malicious downloads or attempts to obtain sensitive information.

However, automated link-scanning tools can sometimes generate tracking requests. Furthermore, this simulation involved fictional identities controlled within the laboratory, not eight independently observed employees.

## 7.5 Metric Four: Dummy-Data Submission Rate

The dummy-data submission rate measures the proportion of recorded link-click events followed by a landing-page form submission.

**Formula:**

Dummy-Data Submission Rate = (Dummy-Data Submissions ÷ Links Clicked) × 100

**Calculation:**

(0 ÷ 8) × 100 = 0%

**Result: 0%**

**Interpretation:**

No dummy training information was submitted through the fictional landing page.

This is a favourable outcome within the final laboratory scenario.

However, the absence of a submission event does not independently prove that an actual organisational workforce would resist a real phishing attack.

## 7.6 Credential Collection

Password capture was disabled throughout the practical.

| Credential-Related Measure | Result |
|---|---|
| Password Capture | Disabled |
| Real Passwords Collected | 0 |
| Genuine Credential Disclosure Tested | No |
| Credential Compromise Demonstrated | No |

The exercise therefore did not measure genuine password disclosure.

The 0% dummy-data submission result must not be presented as a measured credential-submission rate, because no password field or genuine credential-collection mechanism was used.

## 7.7 Consolidated Metrics Table

| Metric | Numerator | Denominator | Calculation | Result |
|---|---:|---:|---|---:|
| Email Delivery Rate | 10 | 10 | 10 ÷ 10 × 100 | 100% |
| Email Open Rate | 8 | 10 | 8 ÷ 10 × 100 | 80% |
| Click-Through Rate | 8 | 10 | 8 ÷ 10 × 100 | 80% |
| Dummy-Data Submission Rate | 0 | 8 | 0 ÷ 8 × 100 | 0% |
| Real Password Collection | 0 | Not applicable | Password capture disabled | 0 collected |

---

# 8. PHISHING RISK ASSESSMENT AND CONTROL EVALUATION

## 8.1 Risk Assessment Purpose

The purpose of this assessment is to translate campaign observations into potential information-security risks and identify controls that could reduce their likelihood or impact.

The assessment considers email engagement, link interaction, form submission and the effectiveness of relevant preventive, detective and corrective controls.

The findings are based on a fictional laboratory exercise and do not establish confirmed failures within an actual organisation.

## 8.2 Phishing Risk Assessment Table

| No. | Metric / Finding | Result | Calculated Rate | Risk Interpretation | Potential Control Weakness | Recommended Control |
|---:|---|---:|---:|---|---|---|
| 1 | Email Delivery | 10/10 | 100% | All ten campaign messages are included in the final delivery scenario. | Local SMTP delivery does not demonstrate production email-filter effectiveness. | Maintain email-delivery monitoring and review email-security configurations. |
| 2 | Emails Opened | 8/10 | 80% | Eight open events indicate recorded engagement with the campaign. | Users may engage with messages without adequately examining the sender or context. | Provide continuous security-awareness education and sender-verification guidance. |
| 3 | Links Clicked | 8/10 | 80% | Eight click events demonstrate interaction with campaign links. | Users may access embedded links without adequately checking the destination. | Strengthen malicious-link filtering, URL protection and awareness training. |
| 4 | Dummy-Data Submitted | 0/8 | 0% | No form submissions were recorded. | The laboratory did not demonstrate information disclosure, but independent user behaviour was not assessed. | Maintain safe-information-handling education and monitor future authorised assessments. |
| 5 | Password Collection | 0 | Not applicable | No passwords were collected because password capture was disabled. | Actual password-disclosure susceptibility was not tested. | Maintain MFA and secure authentication controls. |
| 6 | Phishing Reporting | Not measured | Not applicable | Reporting behaviour was not established. | The effectiveness of phishing-reporting procedures remains unverified. | Provide accessible phishing-reporting mechanisms and monitor response performance. |

## 8.3 Detailed Risk Findings

### Finding 1: Email Engagement

**Observation:** Eight email-open events were recorded out of ten delivered campaign messages.

**Risk significance:** Email engagement can provide useful information when reviewing how users interact with electronic communications. However, an open event does not prove that a recipient trusted the message or failed to identify suspicious content.

**Potential business impact:** In a real phishing scenario, engagement with deceptive communications could create opportunities for an attacker to influence user behaviour.

**Recommended action:** Introduce continuous practical security-awareness education covering sender verification, unexpected requests and suspicious email reporting.

### Finding 2: Link Interaction

**Observation:** Eight link-click events were recorded.

**Risk significance:** Clicking an unsafe link can expose users to fraudulent websites, malicious downloads or attempts to collect sensitive information.

**Potential business impact:** A successful phishing attack could create opportunities for unauthorised access, information disclosure or further compromise.

**Recommended action:** Strengthen email filtering, malicious-link protection, browser security and user education on checking destinations before opening links.

### Finding 3: No Dummy-Data Submission Recorded

**Observation:** No form submissions were recorded.

**Risk significance:** This is a favourable result within the final laboratory scenario. It demonstrates that no landing-page form-submission event was recorded.

**Potential business impact:** The exercise did not demonstrate an actual information-disclosure event.

**Recommended action:** Continue safe, controlled simulations and reinforce guidance on avoiding unnecessary disclosure through unexpected email links.

### Finding 4: Credential Collection Was Not Tested

**Observation:** Password capture was disabled.

**Risk significance:** No real credentials were collected. However, the practical cannot establish whether independent users would disclose passwords during a real phishing attack.

**Recommended action:** Maintain strong authentication requirements, introduce phishing-resistant MFA where feasible and ensure that awareness assessments do not collect genuine passwords.

### Finding 5: Phishing Reporting Behaviour Was Not Measured

**Observation:** The available results did not establish whether users reported the simulated message.

**Risk significance:** Reporting mechanisms are important because organisations need employees to identify and escalate suspected phishing attempts.

**Recommended action:** Introduce a simple phishing-reporting procedure and establish reporting-related performance indicators.

## 8.4 Control Evaluation

| Control Area | Control Objective | Laboratory Assessment | Status |
|---|---|---|---|
| Email Delivery | Ensure test messages reach the receiving inbox. | Ten campaign messages are included in the final scenario; MailHog evidence must confirm receipt. | Evidence verification required |
| Email Monitoring | Record email-open events. | Eight open events. | Demonstrated in scenario |
| Link Monitoring | Record campaign-link interactions. | Eight click events. | Demonstrated in scenario |
| Form Monitoring | Record fictional training submissions. | Zero submissions. | No submission observed |
| Credential Protection | Avoid collecting genuine passwords. | Password capture was disabled. | Satisfied in laboratory |
| Security Awareness | Assess whether users recognise phishing attempts. | No independent employee population was tested. | Not established |
| Email Filtering | Prevent unsafe messages from reaching users. | Production filtering was outside the scope. | Not assessed |
| Multi-Factor Authentication | Reduce the impact of compromised passwords. | Production authentication controls were not tested. | Not assessed |
| Phishing Reporting | Enable timely reporting of suspicious messages. | Reporting behaviour was not measured. | Not assessed |

## 8.5 Overall GRC Interpretation

The simulation demonstrates the operation of email delivery, open tracking and link-click monitoring within a controlled environment.

The 80% open rate and 80% click-through rate provide useful indicators for discussing email engagement and possible link-related exposure.

---

# 9. BUSINESS IMPACT ANALYSIS

## 9.1 Potential Business Consequences

A successful phishing attack against a real organisation could affect multiple business functions.

| Potential Threat | Business Impact | Affected Function |
|---|---|---|
| Account Compromise | Unauthorised access to business applications and confidential information. | IT and Operations |
| Information Disclosure | Exposure of customer, employee or organisational data. | Data Protection and Compliance |
| Business Email Compromise | Fraudulent communications or payment instructions. | Finance and Procurement |
| Malware Delivery | System disruption, data loss or operational downtime. | IT and Business Operations |
| Regulatory Exposure | Possible compliance investigations or sanctions where applicable. | Legal and Compliance |
| Reputational Damage | Loss of customer and stakeholder confidence. | Executive Management |
| Incident Response Costs | Investigation, containment, recovery and communication expenses. | IT Security and Risk Management |

## 9.2 Potential Risk Exposure

The actual impact of a phishing incident depends on:

- The privileges of the affected account.
- The sensitivity of accessible information.
- The effectiveness of authentication controls.
- The strength of email and endpoint protection.
- The availability of monitoring and incident-response capabilities.
- The speed at which suspicious activity is identified and contained.

The laboratory did not establish actual financial losses, regulatory breaches or organisational compromise.

The business impacts described above represent potential consequences that should be considered during organisational risk assessment.

---

# 10. RISK TREATMENT AND MANAGEMENT RECOMMENDATIONS

The recommendations are organised according to implementation priority to assist management with assigning responsibility, allocating resources and monitoring progress.

## 10.1 Immediate Recommendations

| Priority | Recommendation | Responsible Department | Expected Benefit |
|---|---|---|---|
| High | Enforce MFA across email, remote access, administrative accounts and critical business systems. | IT Security / IAM | Reduces the impact of password compromise. |
| High | Strengthen email filtering for suspicious messages, spoofing and malicious links. | Email Security Team | Reduces exposure to phishing messages. |
| High | Establish or improve an accessible phishing-reporting mechanism. | IT Security / SOC | Improves identification and reporting of suspicious emails. |
| High | Review the phishing incident-response procedure. | Incident Response Team | Supports timely containment and investigation. |
| High | Ensure email and authentication logs are monitored for suspicious activity. | SOC / IT Security | Improves detection and response capabilities. |

## 10.2 Medium-Term Recommendations

| Priority | Recommendation | Responsible Department | Expected Benefit |
|---|---|---|---|
| Medium | Provide continuous phishing-awareness training. | HR / Security Awareness Team | Improves recognition of social-engineering techniques. |
| Medium | Introduce role-based security-awareness content. | GRC / HR | Focuses training on relevant business risks. |
| Medium | Include phishing awareness in employee onboarding. | HR / IT | Establishes secure behaviour from the beginning of employment. |
| Medium | Review and update the Acceptable Use Policy. | GRC / Legal / IT | Clarifies user responsibilities and reporting requirements. |
| Medium | Conduct periodic reviews of email-security configurations. | IT Security | Helps identify technical control weaknesses. |
| Medium | Develop an incident-reporting awareness programme. | IT Security / HR | Encourages prompt reporting of suspicious messages. |

## 10.3 Long-Term Recommendations

| Priority | Recommendation | Responsible Department | Expected Benefit |
|---|---|---|---|
| Long Term | Progress towards phishing-resistant MFA where feasible. | IAM / IT Security | Provides stronger authentication protection. |
| Long Term | Integrate human-risk metrics into the organisational security dashboard. | GRC / CISO Office | Improves management oversight and risk reporting. |
| Long Term | Conduct periodic authorised phishing-awareness assessments. | GRC / Security Awareness Team | Supports continuous evaluation of security-awareness controls. |
| Long Term | Use previous assessment results to improve training content. | HR / GRC | Makes awareness programmes more relevant. |
| Long Term | Extend phishing-risk awareness to suppliers and third parties. | Procurement / Third-Party Risk / GRC | Supports supply-chain security awareness. |
| Long Term | Review phishing-related policies and procedures regularly. | GRC / Legal / IT Security | Supports continuous governance improvement. |

## 10.4 Recommended Remediation Roadmap

| Timeframe | Priority Action | Responsible Function | Expected Output |
|---|---|---|---|
| 0–30 Days | Review MFA coverage and email-security settings. | IT Security / IAM | Identified control gaps and remediation actions. |
| 0–30 Days | Establish or communicate phishing-reporting procedures. | SOC / HR | Documented reporting process. |
| 30–60 Days | Deliver targeted security-awareness education. | HR / GRC | Training materials and completion records. |
| 30–60 Days | Review the Acceptable Use Policy. | GRC / Legal | Updated policy recommendations. |
| 60–90 Days | Establish an ongoing phishing-awareness measurement programme. | GRC / CISO Office | Baseline metrics and assessment schedule. |
| 60–90 Days | Review campaign metrics and management reporting. | GRC / IT Security | Human-risk performance dashboard. |

## 10.5 Management Key Performance Indicators

Management should monitor phishing-related performance indicators over time.

| KPI | Measurement Formula | Management Purpose |
|---|---|---|
| Email Open Rate | Opened ÷ Delivered × 100 | Measures email engagement. |
| Click-Through Rate | Clicked ÷ Delivered × 100 | Measures link interaction. |
| Dummy-Data Submission Rate | Submitted ÷ Clicked × 100 | Measures training-form interaction. |
| Phishing Reporting Rate | Reported ÷ Delivered × 100 | Measures reporting behaviour. |
| Training Completion Rate | Completed Training ÷ Assigned Training × 100 | Measures training participation. |
| Training Assessment Pass Rate | Passed Assessments ÷ Completed Assessments × 100 | Measures learning outcomes. |
| MFA Coverage | MFA-Protected Eligible Accounts ÷ Eligible Accounts × 100 | Measures authentication protection. |
| Incident Response Time | Time from Identification to Containment | Evaluates incident response. |

---

# 11. CONCLUSION

The GRC103 Social Engineering and Phishing Campaign Simulation demonstrated how a GRC professional can use a controlled phishing-awareness exercise to understand social-engineering risks, monitor campaign activity and translate technical observations into risk-management recommendations.

The practical involved installing and configuring GoPhish v0.12.1 on Kali Linux, establishing a local SMTP capture service using MailHog, developing a fictional security-awareness landing page, creating an email template and managing a ten-recipient fictional test group.

The final campaign scenario records ten emails sent and delivered, eight email-open events, eight link-click events and no dummy-data submissions.

The calculated email open rate was 80%, the click-through rate was 80%, and the dummy-data submission rate was 0%. No passwords were collected because password capture was disabled.

The results demonstrate the importance of evaluating several stages of a phishing simulation rather than relying on a single campaign metric.

From a GRC perspective, the assessment reinforces the importance of an integrated human-risk management approach involving preventive controls, user education, accessible reporting mechanisms, identity protection and continuous monitoring.

The exercise also demonstrates that a GRC professional must distinguish between observed evidence, potential risks and unverified control weaknesses. The simulated results provide practical experience in risk evaluation, but they cannot establish the behaviour of an actual organisational workforce.

The recommendations focus on strengthening email security, implementing appropriate MFA, improving security-awareness training, reviewing relevant policies, establishing effective reporting processes and introducing consistent human-risk measurements.

---

# 12. REFERENCES

1. GRC103 Practical Laboratories. *Social Engineering and Phishing Campaign Simulation for GRC Professionals*. Course assessment brief supplied for the practical exercise.

2. GoPhish. (n.d.). *GoPhish: Open-source phishing toolkit*. GitHub. https://github.com/gophish/gophish

3. MailHog. (n.d.). *MailHog: Email testing tool for developers*. GitHub. https://github.com/mailhog/MailHog

## AI Usage Declaration
ChatGPT (OpenAI) and Microsoft Copilot were used during the brainstorming stage to generate ideas, and identify and correct grammatical errors. I independently reviewed, edited, and developed the report before submission. I remain responsible for the final work, including its accuracy,and conclusions

