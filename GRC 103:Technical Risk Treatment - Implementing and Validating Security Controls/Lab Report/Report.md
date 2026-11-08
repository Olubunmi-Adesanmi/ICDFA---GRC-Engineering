# TECHNICAL RISK TREATMENT
## IMPLEMENTING AND VALIDATING SECURITY CONTROLS

** Practical Laboratory Report**

**Organisation:** Northbridge Services (Fictional Case Study)

**Programme:** ICDFA – GRC Engineering Programme  
**Module:** GRC103 – Risk Assessment and Management Techniques  
**Module Component:** Module 3 – Risk Treatment Strategies  
**Laboratory Platform:** Ubuntu Server 24.04 LTS and Kali Linux  
**Prepared by:** Olubunmi Adesanmi 
**Registration Number:** c11/26/CGRCE/17550  
**Submission Date:** 08 November 2026  
** Version:** 1.0  
**Document Classification:** Academic Submission – Controlled Laboratory Environment

---

# TABLE OF CONTENTS

1. Executive Summary
2. Introduction
3. Background and Laboratory Scenario
4. Purpose, Scope and Objectives
5. Laboratory Environment and Technical Architecture
6. Risk Assessment Methodology
7. Baseline Security Assessment
8. Initial Risk Register
9. Risk Treatment Implementation
   - 9.1 Avoidance – Retirement of the Legacy Service
   - 9.2 Mitigation – Archive Protection
   - 9.3 Mitigation – Network Access Control
   - 9.4 Service Continuity Validation
10. Security Monitoring and Log Correlation
11. Corrective Controls – Backup and Recovery
12. Evaluation of Risk Transfer
13. Evaluation of Risk Acceptance
14. Financial Analysis and Cost-Benefit Assessment
15. Residual Risk Assessment
16. Monitoring and Operational Handover
17. Change Management and Rollback
18. Evidence Management and Documentation
19. Management Recommendations
20. Conclusion
21. References
22. Appendices

---

# 1. EXECUTIVE SUMMARY

## 1.1 Overview

This report presents the technical risk treatment practical undertaken within the Northbridge Services case study for GRC103 Module 3 – Risk Treatment Strategies.

The practical focused on implementing and validating security controls on a fictional internal document server operating on Ubuntu Server 24.04 LTS.

The laboratory was designed to demonstrate how a Governance, Risk and Compliance (GRC) professional identifies technical security weaknesses, evaluates associated risks, selects appropriate treatment strategies, implements controls and measures their effectiveness through evidence-based validation.

The assessment was conducted using two virtual machines:

- **Ubuntu Server 24.04 LTS:** Configured as the target document server.
- **Kali Linux:** Used as the security testing workstation.

The laboratory incorporated Nginx as the approved web service, UFW as the host-based firewall, Python 3 as the deliberately unnecessary legacy endpoint, Nmap for network scanning, curl for HTTP validation and Linux backup utilities for recovery testing.

The practical addressed four principal risk areas:

1. Unnecessary exposure of a legacy service.
2. Unauthorised access to a directory containing fictional records.
3. Unrestricted incoming network access to the internal document portal.
4. Loss of approved portal content without a demonstrated recovery capability.

## 1.2 Assessment Approach

A baseline-first assessment approach was adopted.

The initial environment was established before security controls were applied. This enabled the original server configuration, exposed services and accessible content to be assessed and documented.

Following the baseline assessment, the laboratory examined the implementation of preventive, detective and corrective security controls.

The main treatment activities included:

- Retirement of the unnecessary Python-based legacy endpoint.
- Relocation of archive information outside the Nginx document root.
- Application of restrictive Linux directory permissions.
- Disabling automatic directory listings through Nginx.
- Explicit denial of requests to the previous archive URL.
- Configuration of UFW to restrict incoming HTTP connections by source IP address.
- Testing of authorised and unauthorised network access.
- Inspection of Nginx and firewall logs.
- Creation of a protected backup archive.
- Simulation of file deletion and subsequent restoration.
- Verification of restored-file integrity using SHA-256.

The practical also required an evaluation of avoidance, mitigation, transfer and acceptance decisions, together with financial calculations and residual risk reassessment.

## 1.3 Technical Control Assessment

The laboratory established a before-and-after validation process.

| Control area | Technical objective | Primary validation evidence |
|---|---|---|
| Baseline assessment | Identify original service exposure | Nmap, curl and listening-port output |
| Service avoidance | Remove unnecessary legacy service | systemd status and repeat Nmap scan |
| Archive protection | Prevent public access to fictional records | Nginx configuration, file permissions and HTTP responses |
| Firewall mitigation | Restrict access to approved source IP | UFW configuration and connection tests |
| Service continuity | Preserve approved portal availability | Successful HTTP response |
| Security monitoring | Record application and network events | Nginx and UFW log extracts |
| Backup and recovery | Restore deleted portal content | Tar archive, SHA-256 and recovery test |

The individual command outputs and screenshots constitute the technical evidence supporting the reported results.

## 1.4 Financial Assessment

The financial analysis followed the assumptions supplied in the practical brief.

The first-year costs were calculated as follows:

| Investment option | First-year cost |
|---|---:|
| A – Hardening work | $150 |
| B – Managed backup | $360 |
| C – TLS deployment | $100 |
| **Combined investment** | **$610** |

A separate illustrative Annual Loss Expectancy calculation produced:

- Baseline ALE: $1,000.
- Residual ALE: $200.
- Estimated annual benefit: $800.
- First-year managed-backup cost: $360.
- Illustrative first-year net benefit: $440.

These calculations use fictional assumptions and do not represent measured organisational savings.

## 1.5 Overall GRC Assessment

The practical demonstrates that technical risk treatment requires more than the introduction of security configurations.

The effectiveness of a control must be assessed through validation, evidence collection, monitoring and periodic reassessment.

The retirement of an unnecessary service addresses the exposure associated with that service but does not remove all risks associated with the document server.

Similarly, network restrictions, archive protection and recovery controls reduce identified risks but retain limitations that must be addressed through ongoing governance and management oversight.

---

# 2. INTRODUCTION

## 2.1 Background

Cybersecurity risk management involves identifying threats, evaluating weaknesses and implementing appropriate measures to reduce the possibility or impact of security incidents.

Organisations increasingly depend on internal information systems to store and distribute operational documents. Such systems must be appropriately protected to ensure information confidentiality, integrity and availability.

However, unnecessary services, excessive access permissions, insufficient network restrictions and inadequate backup arrangements can create security exposures.

These weaknesses may allow unauthorised access, information disclosure, service disruption or loss of business information.

Effective GRC practice requires that these risks be identified, documented, assigned to accountable owners and treated through appropriate risk management strategies.

The GRC103 Module 3 practical focuses on the technical implementation of risk treatment controls within an isolated Linux environment.

## 2.2 Laboratory Context

The practical places me in the role of a GRC analyst and technical control implementer for Northbridge Services.

The organisation operates an internal document server containing an approved web portal and a directory of fictional training records.

The original environment includes an unnecessary legacy service and an archive directory accessible through the web server.

Management requires the identified risks to be treated without interrupting the approved portal.

The practical therefore examines the relationship between technical security controls, business continuity, risk ownership, evidence collection and management decision-making.


# 3. BACKGROUND AND LABORATORY SCENARIO

## 3.1 Northbridge Services

Northbridge Services is a fictional organisation created for this practical exercise.

The organisation operates an internal document server that provides access to approved business information.

The server contains three principal components:

| Component | Purpose | Original security concern |
|---|---|---|
| Approved web portal | Provides internal document access | Must remain available |
| Archive directory | Contains fictional training records | Initially accessible through the web root |
| Legacy endpoint | Provides an unnecessary training service | Introduces additional network exposure |

The approved portal is intended to remain operational throughout the treatment process.

## 3.2 Identified Security Concerns

The initial scenario identifies four risks.

**Risk R1 – Legacy-service exposure**

An unnecessary Python-based HTTP service listens on TCP port 8080. Its continued operation increases the number of network-accessible services without a justified business requirement.

**Risk R2 – Exposed archive**

The archive directory is initially located within the Nginx document root. Automatic directory listing and direct file retrieval create the possibility of unauthorised information disclosure.

**Risk R3 – Unauthorised network access**

The original network configuration does not implement the required source-based restrictions. Unapproved network clients may be able to reach the approved portal.

**Risk R4 – Portal content loss**

The approved portal requires a demonstrated recovery mechanism to support availability following accidental file deletion.

## 3.3 Business Requirements

The practical establishes the following requirements:

- The approved web portal must remain available.
- The unnecessary legacy service must be retired.
- The archive must no longer be publicly accessible.
- Network access must be restricted to the approved source.
- Permitted and blocked requests must be tested.
- Security events must be investigated through relevant logs.
- Approved portal content must be recoverable.
- Risk treatment decisions must be justified.
- Costs, residual risks, owners and monitoring arrangements must be documented.

---

# 4. PURPOSE, SCOPE AND OBJECTIVES

## 4.1 Purpose

The purpose of the assessment was to demonstrate the implementation and validation of technical security controls in response to identified information-security risks.

The practical also aimed to demonstrate how the GRC professional connects technical findings to risk treatment decisions and management recommendations.

## 4.2 Scope

The assessment was restricted to the designated laboratory environment.

| Scope component | Description |
|---|---|
| Target operating system | Ubuntu Server 24.04 LTS |
| Testing operating system | Kali Linux |
| Web service | Nginx |
| Firewall | UFW |
| Legacy endpoint | Python 3 HTTP server |
| Network assessment | Nmap TCP scanning |
| Application testing | curl |
| Service inspection | systemd and ss |
| Backup utility | tar |
| Integrity verification | SHA-256 |
| Risk assessment | R1–R4 |
| Risk treatment | Avoidance, mitigation, transfer and acceptance |

## 4.3 Exclusions

The practical did not involve testing production systems, third-party infrastructure or publicly accessible targets.

No real customer information or sensitive organisational records were required.

The managed-backup and acceptance exercises were governance evaluations rather than actual service purchases or organisational approvals.

## 4.4 Learning Objectives

The assessment addressed the following learning outcomes:

1. Implement preventive controls to reduce technical exposure.
2. Apply detective controls through logging and monitoring.
3. Implement corrective controls through backup and restoration.
4. Validate permitted and blocked network access.
5. Distinguish exposure removal from residual risk reduction.
6. Evaluate different risk treatment strategies.
7. Calculate fictional first-year control costs.
8. Apply illustrative Annual Loss Expectancy calculations.
9. Document control ownership and monitoring requirements.
10. Prepare evidence suitable for GRC reporting and management review.

---

# 5. LABORATORY ENVIRONMENT AND TECHNICAL ARCHITECTURE

## 5.1 Laboratory Architecture

The practical used a two-VM architecture.

Kali Linux operated as the testing workstation, while Ubuntu Server hosted the target web application and legacy service.

Both VMs were connected through an isolated host-only or internal network.

This configuration was selected to keep the laboratory traffic within the controlled environment.

## 5.2 System Configuration

| Specification | Ubuntu Server | Kali Linux |
|---|---|---|
| Operating system | Ubuntu Server 24.04 LTS | Kali Linux |
| CPU allocation | 2 vCPUs | 2 vCPUs |
| Memory | 2–4 GB | 2–4 GB |
| Storage | 25 GB | 25 GB |
| Network arrangement | Host-only/internal | Host-only/internal |
| Laboratory function | Target server | Testing workstation |

The actual server and client IP addresses were recorded during the laboratory.

**Ubuntu IP address:** Refer to the recorded `ip -br addr` evidence.

**Kali IP address:** Refer to the recorded `ip -br addr` evidence.



## 5.3 Network Security Configuration

The laboratory used an isolated network.

A temporary NAT connection was available for package installation, but the practical required it to be disconnected before creating the intentionally exposed services.

Bridged networking and public service exposure were excluded.

A clean VM checkpoint was created before the practical changes.

## 5.4 Tools and Technologies

| Tool | Purpose |
|---|---|
| Nginx | Hosts the approved internal web portal |
| UFW | Restricts incoming network connections |
| Python 3 | Runs the deliberately unnecessary legacy service |
| systemd | Manages the legacy service |
| Nmap | Identifies exposed TCP ports |
| curl | Tests HTTP requests and responses |
| ss | Inspects listening network sockets |
| tar | Creates and extracts backup archives |
| SHA-256 | Verifies restored-file integrity |
| journalctl | Investigates system and firewall logs |

---

# 6. RISK ASSESSMENT METHODOLOGY

## 6.1 Assessment Approach

This Laboratory practical followed a structured risk treatment lifecycle.

The initial environment was established, risks were identified and assessed, treatment decisions were implemented, and the resulting control configuration was subjected to technical validation.

The process was:

1. Establish the original environment.
2. Identify assets and security weaknesses.
3. Document threats and potential impacts.
4. Assess likelihood and impact.
5. Calculate initial risk scores.
6. Select appropriate risk treatments.
7. Implement the selected controls.
8. Conduct validation tests.
9. Reassess residual risks.
10. Develop monitoring and operational handover requirements.

## 6.2 Risk Identification

Four primary risks were evaluated.

| Risk ID | Risk description | Asset |
|---|---|---|
| R1 | Unnecessary legacy-service exposure | Ubuntu server |
| R2 | Unauthorised access to fictional records | Archive directory |
| R3 | Unauthorised network access | Internal web portal |
| R4 | Loss of approved portal content | Public portal directory |

## 6.3 Risk Scoring

The practical uses a qualitative five-point likelihood and impact scale.

The risk score is calculated as:

**Risk Score = Likelihood × Impact**

Each variable is rated from 1 to 5.

## 6.4 Risk Classification

| Score | Risk classification |
|---:|---|
| 1–4 | Low |
| 5–9 | Medium |
| 10–16 | High |
| 17–25 | Critical |

The scoring system provides a consistent classroom decision-making method.

The scores are ordinal risk ratings. They are not probabilities or monetary loss figures.

## 6.5 Risk Ownership

Each identified risk requires an accountable owner.

The proposed role allocation is:

| Risk | Proposed owner |
|---|---|
| R1 – Legacy service | System Administrator |
| R2 – Archive exposure | System Administrator / Information Asset Owner |
| R3 – Network access | Network or Security Administrator |
| R4 – Portal recovery | Backup Administrator / Service Owner |

These are proposed operational responsibilities for the fictional scenario.

---

# 7. BASELINE SECURITY ASSESSMENT

## 7.1 Purpose of the Baseline

The baseline assessment established the original security condition before the implementation of risk treatment controls.

This was necessary to create a comparison point for the subsequent validation activities.

The baseline examination focused on network exposure, web-server configuration, archive accessibility and service status.

## 7.2 Baseline Server Configuration

The Ubuntu server was prepared with the following laboratory directories:

```text
/var/www/grc-lab/
    public/
    archive/

/srv/grc-legacy/
```

The public directory contained the approved portal content.

The archive directory contained a fictional record.

The separate legacy directory contained the content served through the Python HTTP endpoint.

## 7.3 Baseline Service Exposure

The practical configured Nginx on TCP port 80 and the Python-based legacy service on TCP port 8080.

The baseline scan was designed to examine these ports using:

```bash
nmap -sT -p 80,8080 "$SERVER_IP" \
-oN baseline-ports.txt
```

The scan results were preserved as the original network-service evidence.

**Baseline Nmap evidence:** `baseline-ports.txt`

The actual port states are recorded in the supplied scan output.

## 7.4 Baseline Web Accessibility

The root portal was assessed using:

```bash
curl -i "http://$SERVER_IP/"
```

The archive directory was assessed using:

```bash
curl -i "http://$SERVER_IP/archive/"
```

The individual dummy record was tested through:

```bash
curl -i \
"http://$SERVER_IP/archive/dummy-records.txt"
```

The legacy endpoint was tested using:

```bash
curl -i "http://$SERVER_IP:8080/"
```

These tests were designed to determine whether the original configuration allowed directory enumeration, direct file retrieval and access to the unnecessary service.

## 7.5 Baseline Service Inspection

The server's listening sockets were inspected using:

```bash
sudo ss -lntp
```

The firewall configuration was inspected using:

```bash
sudo ufw status verbose
```

These checks established the server-side context required to interpret the network tests.

## 7.6 Baseline Assessment Findings

The baseline investigation addressed four principal security concerns.

| Finding | Security concern | Risk |
|---|---|---|
| F-01 | Unnecessary service exposed through the legacy endpoint | R1 |
| F-02 | Archive information accessible through the web document root | R2 |
| F-03 | Incoming access not yet restricted by the intended source-based firewall policy | R3 |
| F-04 | Portal recovery capability required validation | R4 |

---

# 8. INITIAL RISK REGISTER

The initial register documented the risks before treatment.

| ID | Risk event | Weakness | Threat consequence | Likelihood | Impact | Score | Classification |
|---|---|---|---|---:|---:|---:|---|
| R1 | Unnecessary service accessed by an unauthorised party | Legacy service running on TCP 8080 | Unnecessary attack surface and potential service misuse | 4 | 3 | 12 | High |
| R2 | Fictional archive records retrieved without authorisation | Archive inside web root, automatic listing enabled | Information disclosure | 4 | 4| 16 | High|
| R3 | Unapproved network client connects to portal | No effective source-specific restriction at baseline | Unauthorised access to the internal portal | 4| 4 | 16 | High |
| R4 | Approved portal content is lost | Recovery capability not yet demonstrated | Service unavailability and content loss | 3 | 4 | 12| High |


# 9. RISK TREATMENT IMPLEMENTATION

The treatment phase addressed the identified risks using avoidance and mitigation controls.

The main requirement was to reduce identified security exposures while maintaining the availability of the approved web portal.

## 9.1 RISK TREATMENT 1: AVOIDANCE – RETIREMENT OF THE LEGACY SERVICE

### 9.1.1 Risk Description

R1 concerned the unnecessary Python HTTP service operating on TCP port 8080.

Because the service was not required for the approved business workflow, retaining it would introduce additional network exposure without a justified operational benefit.

### 9.1.2 Treatment Decision

Avoidance was selected because the most appropriate response was to discontinue the unnecessary service rather than continue maintaining a service that the organisation did not require.

### 9.1.3 Technical Implementation

The legacy service was stopped and disabled through systemd.

The implementation command was:

```bash
sudo systemctl disable --now grc-legacy
```

The service active state was inspected using:

```bash
sudo systemctl is-active grc-legacy
```

Its enablement status was checked using:

```bash
sudo systemctl is-enabled grc-legacy
```

The listening sockets were re-examined using:

```bash
sudo ss -lntp
```

### 9.1.4 Validation Approach

The post-treatment Nmap scan was conducted from Kali:

```bash
nmap -sT -p 80,8080 "$SERVER_IP" \
-oN avoidance-ports.txt
```

The previous legacy endpoint was tested using:

```bash
curl -i --connect-timeout 5 \
"http://$SERVER_IP:8080/"
```

The approved portal was tested using:

```bash
curl -i "http://$SERVER_IP/public/"
```

### 9.1.5 Control Validation

| Test | Expected outcome | 
|---|---|
| systemd active state | Inactive |
| systemd enabled state | Disabled | 
| Port 8080 | No longer listening/open |
| Legacy HTTP request | Connection unavailable |
| Approved portal | HTTP 200 | 

### 9.1.6 Service Continuity

The approved web portal was required to remain operational while the legacy endpoint was retired.

This was an essential part of the treatment because a control that removes an unnecessary service but disrupts the approved business service would introduce an operational availability concern.

The continuity test was therefore included alongside the service retirement validation.

### 9.1.7 Business and GRC Significance

Avoidance reduces exposure by removing the unnecessary activity responsible for the risk.

However, it does not eliminate the security risks associated with the remaining server.

The approved web service continues to require access restrictions, monitoring and appropriate security maintenance.

### 9.1.8 Rollback

The documented rollback command was:

```bash
sudo systemctl enable --now grc-legacy
```

The service must remain inactive and disabled in the final security configuration.

---

## 9.2 RISK TREATMENT 2: MITIGATION – ARCHIVE PROTECTION

### 9.2.1 Risk Description

R2 concerned unauthorised access to the archive directory containing fictional records.

The original archive was located within the Nginx document root.

The initial web-server configuration enabled automatic directory listings, increasing the possibility of information disclosure.

### 9.2.2 Treatment Decision

Mitigation was selected because the archive remained part of the fictional information environment, but it did not need to be published through the web application.

The selected controls were intended to prevent the archive from being served through the approved portal.

### 9.2.3 Archive Relocation

A restricted storage directory was created outside the Nginx document root:

```bash
sudo mkdir -p /srv/grc-private
```

The archive was moved:

```bash
sudo mv /var/www/grc-lab/archive \
/srv/grc-private/
```

The new archive location became:

```text
/srv/grc-private/archive/
```

Moving the directory outside the web root reduced the possibility of accessing it through the original URL.

### 9.2.4 File-System Permission Restrictions

The archive permissions were restricted using:

```bash
sudo chmod -R go-rwx /srv/grc-private
```

Directory permissions were inspected using:

```bash
sudo ls -ld /srv/grc-private
```

The full path was examined using:

```bash
sudo namei -l \
/srv/grc-private/archive/dummy-records.txt
```

This was intended to remove group and other-user access through the applicable permission bits.

### 9.2.5 Nginx Configuration Hardening

The Nginx site configuration was updated to disable directory listings and explicitly deny access to the old archive path.

The intended configuration was:

```nginx
server {
    listen 80;
    server_name _;
    root /var/www/grc-lab;

    access_log /var/log/nginx/grc_access.log combined;
    error_log /var/log/nginx/grc_error.log;

    location / {
        autoindex off;
    }

    location /archive/ {
        deny all;
    }
}
```

The configuration was tested using:

```bash
sudo nginx -t
```

Following successful validation, Nginx was reloaded.

```bash
sudo systemctl reload nginx
```

### 9.2.6 Archive Validation

The approved portal was tested:

```bash
curl -i "http://$SERVER_IP/public/"
```

The old archive directory was tested:

```bash
curl -i "http://$SERVER_IP/archive/"
```

The direct dummy-record path was also tested:

```bash
curl -i \
"http://$SERVER_IP/archive/dummy-records.txt"
```

The root directory was tested:

```bash
curl -i "http://$SERVER_IP/"
```

The intended validation criteria were:

| Test ID | Request | Response |
|---|---|---|
| AR-01 | `/public/` | HTTP 200 |
| AR-02 | `/archive/` | HTTP 403 |
| AR-03 | `/archive/dummy-records.txt` | HTTP 403 |
| AR-04 | `/` | HTTP 403 |

The actual HTTP responses were preserved in the corresponding test outputs.

### 9.2.7 Security Analysis

Disabling automatic directory listing is not sufficient on its own to protect sensitive files.

A user who knows the exact filename may attempt to access the file directly.

Consequently, the implementation combined directory relocation, filesystem restrictions and explicit web-server access denial.

This layered approach reduces reliance on a single control.

### 9.2.8 GRC Significance

The treatment supports the confidentiality objective by reducing the exposure of information that should not be available through the approved web portal.

It also demonstrates the application of least-privilege principles to both filesystem and application configuration.

---

## 9.3 RISK TREATMENT 3: MITIGATION – NETWORK ACCESS CONTROL

### 9.3.1 Risk Description

R3 concerned unauthorised network access to the approved web portal.

The risk was addressed by introducing a source-based UFW firewall rule.

### 9.3.2 Treatment Decision

Mitigation was selected because the organisation still required the HTTP service, but access needed to be restricted to an approved source.

### 9.3.3 Firewall Configuration

The intended default incoming policy was configured as:

```bash
sudo ufw default deny incoming
```

The outgoing policy was:

```bash
sudo ufw default allow outgoing
```

The approved Kali source was permitted on TCP port 80:

```bash
sudo ufw allow from "$KALI_IP" \
to any port 80 proto tcp
```

Logging was enabled:

```bash
sudo ufw logging on
```

The firewall was activated and inspected through:

```bash
sudo ufw enable
```

```bash
sudo ufw status numbered
```

```bash
sudo ufw status verbose
```

Broad conflicting allow rules were required to be checked because they could undermine the intended source restriction.

### 9.3.4 Permitted-Source Validation

The approved source was used to access the public portal through curl.

The expected successful outcome was HTTP 200.

This established whether the permitted source could still access the approved application after the firewall policy was applied.

### 9.3.5 Blocked-Source Validation

A second unused source IP was temporarily assigned to the Kali isolated-network interface, as permitted by the practical brief.

A request was then made using that secondary source address.

The intended security objective was that the unapproved source would not receive the portal.

The secondary address was removed after the test.

### 9.3.6 Firewall Validation Matrix

| Test | Source | Destination | Result |
|---|---|---|---|
| FW-01 | Approved Kali address | TCP 80 | Permitted |
| FW-02 | Second Kali address | TCP 80 | Blocked |
| FW-03 | Approved Kali address | TCP 80 | Permitted after temporary address removal |
| FW-04 | Ubuntu firewall | Incoming connections | Default deny |

### 9.3.7 Security Analysis

The UFW control implements a network-level restriction based on the source address.

This reduces the number of clients that can communicate with the approved HTTP service.

However, IP-based filtering does not provide individual identity verification, application authentication or transport encryption.

The firewall should therefore be regarded as one layer of the overall security architecture.

---

## 9.4 SERVICE CONTINUITY VALIDATION

An important requirement of the treatment process was to protect the availability of the approved portal.

The retirement of the legacy endpoint and the restriction of the archive were not intended to interrupt the legitimate portal workflow.

The continuity requirement was assessed through repeated requests to:

```text
/public/
```

The actual HTTP response evidence is retained in the portal validation outputs.

| Control activity | Continuity objective |
|---|---|
| Legacy retirement | Port 80 remains available |
| Archive relocation | Public portal continues serving approved content |
| Nginx hardening | Legitimate public content remains accessible |
| UFW implementation | Approved source remains permitted |
| Recovery test | Portal becomes available after file restoration |

This supports the principle that risk treatment should consider both information security and operational availability.

---

# 10. SECURITY MONITORING AND LOG CORRELATION

## 10.1 Monitoring Objective

The practical required the examination of application-level and firewall-level events.

The purpose was to determine how requests reaching Nginx could be distinguished from traffic blocked by UFW.

## 10.2 Nginx Access Logging

Nginx was configured to record HTTP requests through:

```nginx
access_log /var/log/nginx/grc_access.log combined;
```

The access log was examined using:

```bash
sudo tail -n 30 \
/var/log/nginx/grc_access.log
```

This log was used to investigate requests to the approved portal and the archive paths.

The HTTP response status codes provide useful evidence of application-level access decisions.

## 10.3 Firewall Logging

UFW logging was enabled during the firewall implementation.

The kernel journal was examined through:

```bash
sudo journalctl -k \
--since '15 minutes ago' | grep 'UFW BLOCK'
```

Where available, the UFW log file was inspected using:

```bash
sudo tail -n 30 /var/log/ufw.log
```

The investigation focused on source addresses, destination addresses, protocol details and destination ports.

## 10.4 Log Correlation

The practical demonstrates two distinct monitoring layers.

**Application layer:** Requests that reach Nginx are available for application access logging, including requests that Nginx denies with HTTP 403.

**Network layer:** Traffic blocked by UFW before reaching Nginx should be investigated using the relevant firewall or kernel logging facility.

A firewall-blocked packet should not be expected to appear as a normal HTTP request in the Nginx access log.

## 10.5 Log Evidence Matrix

| Event |  log source | Information of interest |
|---|---|---|
| Approved portal request | Nginx access log | Client IP, request and HTTP status |
| Archive denial | Nginx access log | Requested URL and HTTP 403 |
| Direct archive-file denial | Nginx access log | Direct request and HTTP 403 |
| Unapproved network request | UFW/kernel log, where collected | Source IP and blocked destination port |

Firewall logging may be subject to rate limiting and logging-service configuration.

Where an event was not available in the expected log location, the correct approach was to investigate the alternative source rather than manufacture an event.

## 10.6 GRC Significance

Log monitoring supports accountability, event investigation and evidence-based assurance.

The combination of application and firewall logging provides a more complete view of the access-control process than examining either source in isolation.

---

# 11. CORRECTIVE CONTROLS – BACKUP AND RECOVERY

## 11.1 Recovery Objective

Risk R4 concerned the possible loss of approved portal content.

The practical required a working backup and recovery exercise to establish whether a deleted laboratory file could be restored.

The recovery activity was designed around the following sequence:

1. Create a protected backup location.
2. Archive the approved portal directory.
3. Generate an original SHA-256 hash.
4. Record the recovery start time.
5. Delete the original portal file.
6. Validate the effect on portal availability.
7. Restore the file from backup.
8. Verify the restored file's integrity.
9. Validate portal availability.
10. Calculate the observed recovery duration.

## 11.2 Backup Location

The backup directory was created at:

```text
/srv/grc-backups
```

Access was restricted using:

```bash
sudo chmod 700 /srv/grc-backups
```

This arrangement reduced access to the backup location.

## 11.3 Backup Creation

The public portal was archived using:

```bash
sudo tar -czpf \
/srv/grc-backups/public-before-test.tgz \
-C /var/www/grc-lab public
```

The contents of the archive were inspected using:

```bash
sudo tar -tzf \
/srv/grc-backups/public-before-test.tgz
```

This provided evidence of the archived portal directory and its contents.

## 11.4 SHA-256 Integrity Reference

The original portal file was hashed using:

```bash
sha256sum \
/var/www/grc-lab/public/index.html \
| tee ~/portal-before.sha256
```

This created the original integrity reference for the recovery exercise.

## 11.5 Simulated File Loss

The original portal file was removed using:

```bash
sudo rm /var/www/grc-lab/public/index.html
```

The file's removal was checked through a directory listing.

The portal was then tested from Kali to assess the effect of the simulated file loss.

## 11.6 Restoration

The backup archive was extracted into the original portal location using:

```bash
sudo tar -xzpf \
/srv/grc-backups/public-before-test.tgz \
-C /var/www/grc-lab
```

The restored file was then inspected.

## 11.7 File-Integrity Verification

SHA-256 verification was performed using:

```bash
sha256sum -c ~/portal-before.sha256
```

The required successful result was:

```text
/var/www/grc-lab/public/index.html: OK
```

This would demonstrate that the restored file matches the original file recorded before deletion.

The actual verification output is retained as the primary integrity evidence.

## 11.8 Portal Availability Validation

Kali was used to test the restored portal.

```bash
curl -i "http://$SERVER_IP/public/"
```

The successful recovery criterion was an HTTP 200 response with the original approved portal content.

## 11.9 Recovery Limitations

The backup was maintained on the same Ubuntu server as the original portal.

This was adequate for demonstrating recovery from controlled file deletion but does not provide full protection against complete host failure, loss of the VM or severe server compromise.

An independent backup location is recommended to improve resilience.

## 11.10 GRC Significance

The exercise demonstrates the corrective-control function of backup and recovery.

It also demonstrates that recovery assurance should involve more than confirming the presence of a backup archive.

The organisation must periodically verify that the backup can be restored and that the recovered information retains its original integrity.

---

# 12. EVALUATION OF RISK TRANSFER

## 12.1 Purpose

The transfer exercise assessed the use of a fictional managed-backup provider as an alternative or supplement to local-only backup.

The objective was to consider the advantages, costs, responsibilities and limitations of outsourcing part of the backup function.

## 12.2 Supplied Commercial Assumptions

The practical brief provides:

| Cost element | Amount |
|---|---:|
| Setup | $120 |
| Monthly service | $20 |
| Annual service period | 12 months |

The first-year cost is:

$120 + ($20 × 12) = **$360**

No actual purchase was required.

## 12.3 Provider Responsibilities

The provider would be expected to perform the agreed backup-storage functions in accordance with a documented service agreement.

Relevant responsibilities should include:

- Agreed backup operations.
- Storage service availability.
- Contractual security obligations.
- Incident notification.
- Agreed service and retention requirements.
- Restoration assistance within the agreed scope.

These responsibilities should be contractually defined rather than assumed.

## 12.4 Customer Responsibilities

Northbridge Services would retain responsibility for:

- Defining the backup scope.
- Selecting information requiring protection.
- Managing authorised access.
- Assessing provider security.
- Reviewing service assurance evidence.
- Conducting restoration tests.
- Maintaining its own recovery procedures.
- Reviewing provider performance.
- Managing third-party risks.

## 12.5 Proposed Contractual Clause

The following is an illustrative clause for academic evaluation.

**Managed Backup Service Clause**

The service provider shall maintain the agreed backup storage service and conduct backup activities in accordance with the documented service scope, security requirements and retention schedule.

The provider shall notify Northbridge Services of relevant service disruptions and security incidents within the agreed contractual notification period.

Northbridge Services shall remain responsible for defining backup scope, managing authorised access, reviewing backup evidence and conducting periodic restoration testing.

The parties shall agree on restoration requirements, evidence retention, service availability and their respective responsibilities before service commencement.

## 12.6 Transfer Limitations

Transferring backup operations to a third party does not eliminate all associated risk.

Provider failure, service disruption, security incidents, contractual limitations and inability to restore information may still affect the organisation.

The customer remains responsible for appropriate provider oversight and recovery assurance.

**GRC decision:** The managed-backup arrangement is a proposed transfer option. It should be supported by contractual requirements, third-party risk assessment and periodic restoration testing.

---

# 13. EVALUATION OF RISK ACCEPTANCE

## 13.1 Risk Under Consideration

The acceptance exercise considered whether the organisation could temporarily retain plain HTTP within the isolated training network.

HTTP does not provide encryption in transit.

Consequently, the risk involves possible exposure of communications to interception or modification by parties able to access the relevant network traffic.

## 13.2 Acceptance Justification

The practical scenario permits consideration of temporary HTTP retention because:

- The laboratory network is isolated.
- Only fictional training data is used.
- Public connectivity is excluded.
- The approval period is limited.
- The arrangement is intended for academic testing.

These limitations reduce the scope of the risk within the laboratory environment.

They do not eliminate the underlying absence of transport encryption.

## 13.3  Risk Acceptance Record

| Field | Record |
|---|---|
| Risk ID | R3 – Unencrypted HTTP |
| Treatment | Temporary acceptance |
| Asset | Internal document portal |
| Risk owner | Designated organisational risk owner |
| Business justification | Controlled laboratory exercise |
| Data classification | Fictional training information |
| Network scope | Isolated network |
| Acceptance period | 14 days |
| Approval | Simulated |
| Start date | Nov 7,2026 |
| Expiry date | [Start date + 14 days] |
| Review date | Nov ,2027 |

## 13.4 Acceptance Conditions

The proposed acceptance remains subject to:

1. Continued network isolation.
2. Use of dummy data only.
3. No external service exposure.
4. No use for actual sensitive information.
5. Review at the expiry date.
6. Immediate reassessment if the scope changes.

## 13.5 Immediate Reassessment Triggers

The acceptance should be reconsidered if real data is introduced, the service becomes externally accessible, the network is expanded or the approval period expires.

If the residual risk falls outside the organisation's risk appetite, further treatment or escalation is required.

**GRC decision:** Acceptance is limited to the stated laboratory conditions and must not be interpreted as a permanent approval for unencrypted operational services.

---

# 14. FINANCIAL ANALYSIS AND COST-BENEFIT ASSESSMENT

## 14.1 Purpose

The financial assessment compared the supplied treatment options to support informed management decisions.

The financial calculations were conducted using the assumptions specified in the practical brief.

## 14.2 Option A – Hardening Work

Supplied information:

- Four labour hours.
- $25 hourly rate.
- $50 annual maintenance.

Labour calculation:

4 × $25 = $100.

First-year cost:

$100 + $50 = **$150**.

## 14.3 Option B – Managed Backup

Supplied information:

- $120 setup.
- $20 monthly service.

Annual recurring cost:

$20 × 12 = $240.

First-year cost:

$120 + $240 = **$360**.

## 14.4 Option C – TLS Deployment

Supplied information:

- Three labour hours.
- $25 hourly rate.
- $25 annual maintenance.

Labour calculation:

3 × $25 = $75.

First-year cost:

$75 + $25 = **$100**.

## 14.5 First-Year Cost Comparison

| Investment | Setup | Labour | Annual recurring | First-year cost |
|---|---:|---:|---:|---:|
| Option A – Hardening | $0 | $100 | $50 | $150 |
| Option B – Managed backup | $120 | $0 | $240 | $360 |
| Option C – TLS | $0 | $75 | $25 | $100 |
| **Combined** | **$120** | **$175** | **$315** | **$610** |

## 14.6 Recommended Investment Combination

The recommended investment combination is A + B + C.

Total first-year cost:

$150 + $360 + $100 = **$610**.

The investment combination supports different security objectives.

| Option | Intended benefit |
|---|---|
| Hardening | Reduces unnecessary technical exposure and improves configuration security |
| Managed backup | Provides a proposed independent backup capability |
| TLS | Protects communications through transport encryption |

The combination provides complementary benefits rather than treating all options as interchangeable.

The TLS investment is particularly relevant before the approved portal is expanded beyond the isolated HTTP training environment.

## 14.7 Excluded Financial Considerations

The supplied calculations do not include additional expenses for hardware, taxes, licensing, training, migration, downtime, incident response or future expansion.

These exclusions should be considered during any real procurement or investment assessment.

## 14.8 Annual Loss Expectancy Analysis

The practical brief supplies a separate illustrative backup-loss scenario.

The assumptions are:

| Variable | Assumption |
|---|---:|
| Annual Rate of Occurrence | 0.2 |
| Baseline Single Loss Expectancy | $5,000 |
| Residual Single Loss Expectancy | $1,000 |

The formula is:

**ALE = ARO × SLE**

### Baseline ALE

0.2 × $5,000 = **$1,000**

### Residual ALE

0.2 × $1,000 = **$200**

### Annual Financial Benefit

$1,000 − $200 = **$800**

### First-Year Net Benefit

$800 − $360 = **$440**

## 14.9 Consolidated Financial Results

| Financial measure | Result |
|---|---:|
| Baseline ALE | $1,000 |
| Residual ALE | $200 |
| Annual benefit | $800 |
| Managed backup first-year cost | $360 |
| First-year illustrative net benefit | **$440** |
| Combined A + B + C investment | **$610** |

## 14.10 Financial Interpretation

Based on the specified assumptions, the managed-backup option produces an illustrative first-year net benefit of $440.

The result supports the educational demonstration of quantitative risk analysis.

However, the assumptions are fictional. They have not been established using actual organisational incident frequencies or financial-loss data.

The recovery exercise does not independently prove the assumed reduction in loss per event.

Consequently, the financial results must be treated as illustrative estimates rather than verified return on investment.

---

# 15. RESIDUAL RISK ASSESSMENT

## 15.1 Purpose

Residual risk is the risk that remains after the implementation of treatment controls.

The practical requires R1–R4 to be reassessed using evidence from the completed tests.

A configured control does not automatically establish that the associated risk has been reduced successfully.

The assessment must consider the observed test outcomes and limitations of the controls.

## 15.2 Residual Risk Register

| ID | Original risk | Treatment | Residual likelihood | Impact | Residual score | Owner |
|---|---|---|---:|---:|---:|---|
| R1 | Legacy service exposure | Avoidance | 1 | 3| 3 | System Administrator |
| R2 | Archive exposure | Mitigation | 2 | 4 | 8 | Information Asset Owner |
| R3 | Unauthorised network access | Mitigation / limited acceptance | 2 | 4 | 8 | Security Administrator |
| R4 | Portal content loss | Mitigation / proposed transfer | 3 | 4 | 12 | Backup Administrator |

## 15.3 Residual Risk Discussion

### R1 – Legacy-Service Exposure

Retiring the unnecessary service addresses the attack surface associated with the legacy endpoint.

The remaining concern is the possibility of configuration drift or future reactivation.

Continued systemd monitoring is therefore recommended.

### R2 – Archive Exposure

Archive relocation, file permissions and explicit Nginx denial reduce the likelihood of public exposure.

However, administrative misuse or an alternative publication path could introduce new risk.

Periodic access and configuration reviews remain necessary.

### R3 – Unauthorised Network Access

Source-based firewall rules restrict incoming access to the approved source address.

However, IP-based access controls do not provide comprehensive identity management or application-level authentication.

The use of plain HTTP also retains a transport-confidentiality concern.

### R4 – Portal Content Loss

The laboratory backup and restoration exercise provides evidence of recovery from simulated file deletion.

However, same-host backup storage remains vulnerable to complete host loss or compromise.

An independent backup arrangement is therefore recommended.

## 15.4 Risk Acceptance and Escalation

Any residual risk that exceeds the approved organisational appetite should be escalated to the appropriate risk owner.

Risk owners should document their decisions, review dates and further treatment requirements.

---

# 16. MONITORING AND OPERATIONAL HANDOVER

## 16.1 Monitoring Objectives

The effectiveness of implemented security controls must be maintained over time.

Northbridge Services should establish measurable monitoring activities to identify control failures and configuration changes.

## 16.2 Monitoring Plan

| Monitoring activity | Owner | Frequency | Measurement | Threshold | Escalation |
|---|---|---|---|---|---|
| Portal availability | System Administrator | Every 5 minutes | HTTP response | HTTP 200 | Escalate after two consecutive failures |
| Unexpected open ports | GRC/Security Analyst | Daily | Approved versus discovered ports | Any unexpected port | Investigate immediately |
| Backup and recovery | Backup Administrator | Monthly | Successful restore and SHA-256 | Successful verification | Escalate failed recovery |
| Legacy-service drift | System Administrator | Weekly | systemd service state | Inactive and disabled | Investigate if active or enabled |

The frequencies and thresholds are proposed operational values. They are not measured laboratory outcomes.

## 16.3 Portal Availability Monitoring

A proposed availability check is:

```bash
curl -sS -o /dev/null \
-w '%{http_code}\n' \
http://SERVER_IP/public/
```

The approved service should return HTTP 200.

## 16.4 Legacy-Service Monitoring

The legacy service should be monitored using:

```bash
sudo systemctl is-active grc-legacy
```

```bash
sudo systemctl is-enabled grc-legacy
```

The intended final states are inactive and disabled.

## 16.5 Port Monitoring

An authorised network scan can be used to compare the observed server ports against the approved service inventory.

Any unexplained service should be investigated.

## 16.6 Recovery Monitoring

Periodic recovery tests should verify:

- Backup availability.
- Successful restoration.
- File-integrity verification.
- Portal availability.
- Achievement of management-approved recovery objectives.

## 16.7 Operational Handover

The System Administrator should maintain the server configuration and access rules.

The Security or GRC Analyst should review service exposure, risk records and control evidence.

The Backup Administrator should maintain backup assurance and recovery testing.

The designated risk owners should review residual risks and approve or escalate outstanding exposures.

---

# 17. CHANGE MANAGEMENT AND ROLLBACK

## 17.1 Change Management Purpose

Change management ensures that technical security modifications are planned, documented, implemented and tested in a controlled manner.

The practical requires each major change to have an identified purpose, expected result, validation procedure and rollback arrangement.

Any approval included within the academic exercise must be labelled simulated.

## 17.2 Change Register

| Change ID | Description | Expected result | Validation |
|---|---|---|---|
| CHG-001 | Retire legacy service | Port 8080 unavailable; port 80 remains available | systemd, Nmap and curl |
| CHG-002 | Protect archive | Archive inaccessible through the former web path | Nginx and curl |
| CHG-003 | Restrict network access | Approved source permitted and unapproved source blocked | UFW and network tests |
| CHG-004 | Backup and restoration exercise | Portal file restored and integrity verified | SHA-256 and HTTP response |

## 17.3 Rollback Arrangements

### Legacy Service

```bash
sudo systemctl enable --now grc-legacy
```

Reapply the treatment:

```bash
sudo systemctl disable --now grc-legacy
```

### Nginx and Archive

The previous Nginx configuration can be restored from its preserved copy, and the archive can be returned to its original location for a controlled rollback on the disposable laboratory VM.

The original configuration should not remain in use because it restores the archive exposure.

### Firewall

The emergency laboratory rollback command is:

```bash
sudo ufw disable
```

This is to be performed only through the Ubuntu VM console in the disposable lab.

The intended UFW policy must be reapplied before the final laboratory state is restored.

### Backup Recovery

```bash
sudo tar -xzpf \
/srv/grc-backups/public-before-test.tgz \
-C /var/www/grc-lab
```

The restored file must subsequently pass integrity verification.

## 17.4 Change Management Assessment

A documented rollback procedure supports service continuity and accountability.

The change register also creates a traceable record of the security modifications and their validation requirements.

Planned rollback arrangements should be distinguished from rollback tests that were actually performed.

---

# 18. EVIDENCE MANAGEMENT AND DOCUMENTATION
All evidences and screenshots attached

---

# 19. MANAGEMENT RECOMMENDATIONS

Based on the risk treatment objectives and the technical design of the laboratory, the following actions are recommended for Northbridge Services.

## 19.1 Maintain Service Minimisation

Unnecessary network services should be retired.

The organisation should maintain an approved service inventory and perform regular checks for unexpected listening ports.

## 19.2 Enforce Least-Privilege Access

Internal records should be stored outside publicly accessible web directories unless publication is explicitly authorised.

File-system permissions and application-level restrictions should be reviewed regularly.

## 19.3 Strengthen Network Access Restrictions

The source-based firewall policy should remain restricted to approved clients.

Any changes to permitted source addresses should follow a documented approval and change-management process.

## 19.4 Implement Transport Encryption

TLS should be introduced before the approved portal is expanded beyond the isolated HTTP laboratory environment.

Temporary acceptance of plain HTTP should expire according to the documented risk decision.

## 19.5 Improve Backup Resilience

The local backup should be supplemented by an independent backup location.

Third-party arrangements should include clearly documented service responsibilities, backup retention, incident notification and recovery testing.

## 19.6 Define Recovery Objectives

Management should define suitable Recovery Time Objectives and Recovery Point Objectives based on operational requirements.

The observed laboratory restoration time should be considered evidence from a controlled exercise, not automatically adopted as an enterprise recovery commitment.

## 19.7 Strengthen Security Monitoring

The organisation should monitor portal availability, unexpected open ports, firewall events, application requests and backup integrity.

Monitoring frequency, thresholds, responsibilities and escalation procedures should be formally documented.

## 19.8 Maintain Risk Ownership

All residual risks should have accountable owners.

Risk owners should periodically review their assigned risks, evaluate changes in exposure and escalate risks that exceed the approved risk appetite.

## 19.9 Strengthen Third-Party Risk Management

Before engaging a managed-backup provider, Northbridge Services should assess provider security, service availability, operational dependencies, contractual responsibilities and recovery assurance.

---

# 20. CONCLUSION

The GRC103 Module 3 Technical Risk Treatment Laboratory demonstrates the practical relationship between cybersecurity controls, risk management decisions and organisational governance.

The Northbridge Services scenario presented four principal risk areas involving unnecessary legacy-service exposure, archive accessibility, network access restrictions and portal content recovery.

The practical applied the required treatment strategies through technical security measures and governance evaluations.

Avoidance addressed the unnecessary legacy endpoint by retiring the service.

Mitigation addressed archive exposure through directory relocation, restrictive file permissions and Nginx configuration hardening. Network exposure was addressed through source-based UFW restrictions.

Detection was examined through application and firewall logging.

Corrective controls were assessed through backup creation, simulated file deletion, restoration and SHA-256 integrity verification.

The transfer exercise considered the financial and operational implications of using a fictional managed-backup service, while the acceptance exercise considered the conditions under which plain HTTP might temporarily remain within an isolated educational environment.

The cost analysis established a combined first-year investment of $610 for the three proposed options and an illustrative first-year net financial benefit of $440 for the separate managed-backup ALE scenario.

These financial outcomes remain based on the assumptions supplied by the practical brief.

An important conclusion from the exercise is that risk treatment does not end when a control is configured.

Controls require validation, monitoring, ownership and periodic reassessment. Their effectiveness must be demonstrated through reliable technical evidence.

The remaining limitations, particularly same-host backup storage, source-address dependence and the absence of HTTP transport encryption, highlight the need for continuous improvement.

Ultimately, the practical reinforces a fundamental GRC engineering principle:

**Effective security requires the combination of appropriate controls, measurable validation, accountable risk ownership and continuous monitoring.**

---

# 21. REFERENCES

The following technical resources are identified in the official practical brief.

1. International Cybersecurity and Digital Forensics Academy (ICDFA). (n.d.). *GRC103 Risk Assessment and Management Techniques – Module 3: Risk Treatment Strategies.* Course learning material and official Technical Risk Treatment Laboratory brief.

2. Canonical. (n.d.). *Ubuntu Server documentation: Firewall.* Ubuntu Server documentation.  
   https://ubuntu.com/server/docs/firewalls/

3. NGINX, Inc. (n.d.). *Module ngx_http_autoindex_module.* NGINX documentation.  
   https://nginx.org/en/docs/http/ngx_http_autoindex_module.html

4. NGINX, Inc. (n.d.). *Module ngx_http_log_module.* NGINX documentation.  
   https://nginx.org/en/docs/http/ngx_http_log_module.html

---

