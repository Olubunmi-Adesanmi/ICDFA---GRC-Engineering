# Lab 1: Practical Vulnerability Assessment for GRC Professionals

![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-blue)
![Assessment](https://img.shields.io/badge/Assessment-Vulnerability%20Assessment-orange)
![Focus](https://img.shields.io/badge/Focus-Cybersecurity%20%7C%20GRC-green)
![Status](https://img.shields.io/badge/Status-Completed%20-yellow)

## Lab Overview

This project documents a practical vulnerability assessment conducted in an authorised, isolated lab environment using Kali Linux and a deliberately vulnerable Metasploitable target.

The objective was to identify exposed network services, examine web-server security weaknesses, evaluate potential business risks, and translate technical observations into actionable governance, risk, and compliance (GRC) recommendations.

The assessment demonstrates how vulnerability assessment findings can support risk identification, control improvement, remediation planning, and security reporting. It also highlights the importance of distinguishing confirmed observations from unverified vulnerabilities.
  
> **Environment:** Authorised isolated lab (Kali Linux)  
> **Primary focus:** Vulnerability identification, risk assessment, evidence documentation, and remediation prioritisation  
> **Target:** Deliberately vulnerable Metasploitable test server (Metasploitable 2)

## Objectives

The assessment aimed to:

- Discover active hosts and exposed TCP ports.
- Identify running services and available version information.
- Assess web-server weaknesses using automated scanning.
- Document security observations and their potential business impact.
- Assign provisional risk ratings based on potential impact and exposure.
- Map relevant findings to recognised security and GRC frameworks.
- Recommend remediation actions and identify evidence needed for validation.
- Practise transparent reporting when tools cannot complete successfully.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Kali Linux | Assessment environment |
| Nmap | Host discovery, port scanning, service enumeration, and OS fingerprinting |
| Nikto | Web-server security checks and configuration assessment |
| Nuclei | Intended template-based vulnerability assessment; execution was limited by missing templates |
| xsltproc | Conversion of Nmap XML output into an HTML report |
| Metasploitable | Intentionally vulnerable lab target |


## Methodology

The assessment followed a structured workflow.

### 1. Host Discovery and Connectivity

A connectivity check was performed to confirm that the authorised target was reachable within the lab.

### 2. Network and Service Enumeration

Nmap was used to identify open TCP ports, service banners, software versions, and an operating-system estimate. Results were saved in multiple formats to support review and evidence preservation.

### 3. Web-Server Assessment

Nikto was run against the target's HTTP service to check for potential weaknesses, including directory indexing, information disclosure, legacy software, enabled HTTP methods, and missing security headers.

### 4. Vulnerability Assessment Tool 

 Nuclei is template-based: the engine loads YAML templates and reports matches that satisfy a template's conditions . An earlier run failed because no templates were available; its “No results found” was not a clean scan. The later saved output contains two lines, so the report treats these as target-specific Nuclei results, while still distinguishing a version/EOL template from an exploit-confirmation test.

### 5. Risk Evaluation

Observed issues were documented in a consolidated risk register.

### 6. GRC Mapping and Remediation Planning

Relevant observations were mapped to applicable security framework themes. Recommended actions were prioritised to support risk reduction, accountability, and subsequent verification.

## Key Findings

### Network and Service Enumeration

Nmap identified **30 open TCP ports** on the lab target.

The observed services included:

- Legacy FTP, SSH, and web-server software.
- Telnet, remote shell, and remote login services.
- SMB/Samba and NFS.
- MySQL and PostgreSQL database services.
- Java RMI, distccd, VNC, and Apache AJP.
- UnrealIRCd.
- A service identified by Nmap as a Metasploitable root shell on port `1524`.


### Web-Server Assessment

Nikto reported several issues requiring investigation:

| Observation | Potential Security Impact | Recommended Action |
|---|---|---|
| Outdated PHP and Apache versions | Known weaknesses may exist in unsupported or legacy software | Upgrade to supported versions and validate the deployed build |
| Directory indexing on web paths | Unintended files or directory contents may be exposed | Disable indexing and restrict access to unnecessary directories |
| Publicly accessible `phpinfo()` output | Technical configuration details may be disclosed | Remove diagnostic pages or restrict access |
| HTTP TRACE method enabled | May increase exposure to certain web attack scenarios | Disable TRACE unless there is a documented requirement |
| Missing recommended security headers | May reduce browser-side security protections | Configure suitable headers according to application requirements |
| phpMyAdmin resources accessible | Database administration interfaces may be exposed | Restrict access to authorised users and networks |
| PHP Easter Egg responses | May disclose unnecessary application information | Disable the feature or remove the relevant exposure |
| Apache MultiViews enabled | May make resource discovery easier in some configurations | Review necessity and disable if not required |
| Apache default or documentation files present | May disclose implementation details | Remove unnecessary files or restrict access |

## Nuclei  vulnerability scanning

A web-focused and broader Nuclei scans was conducted  using these commands:
nuclei -u http:// 192.168.**.*** -o nuclei_web_scan.txt
nuclei -target 192.168.**.*** -o nuclei_full_scan.txt
Nuclei v3.11.1 was installed. During the attempt, the tool initially reported that it could not find the expected template path under /home/kali/.local/nuclei-templates which was later resolved.

Assessment Findings summary: CVE-2012-1823 High; CVE-2026-109618 version/EOL branch Critical
High-priority PHP exposure; confirm configuration and CVE applicability

## Risk Assessment Approach

The risk register consolidates key network and web assessment observations into prioritised items for remediation.

| Priority Area | Risk Rationale | Recommended Response |
|---|---|---|
| Critical  | Service identified as a root-shell listener on port `1524` | Verify the service in the isolated lab and remove or restrict it if confirmed unnecessary |
| High | Legacy services, potentially vulnerable software, and exposed remote-access interfaces | Validate exposure, restrict access, patch, or disable affected services |
| Medium  | Information disclosure and unnecessary web-server functionality | Remove information leaks and harden server configuration |
| Low to Medium | Missing security headers and minor configuration weaknesses | Apply appropriate security configuration and verify effectiveness 

## GRC and Security Framework Alignment

The findings can support a control review using the following framework areas:

| Framework | Relevant Areas | Application to This Assessment |
|---|---|---|
| NIST Cybersecurity Framework 2.0 | Govern, Identify, Protect, Detect | Risk governance, asset and exposure identification, protective controls, and monitoring |
| CIS Critical Security Controls | Asset Inventory, Secure Configuration, Vulnerability Management, Access Control | Inventory exposed services, reduce unnecessary exposure, remediate weaknesses, and restrict access |
| ISO/IEC 27001:2022 | Information security risk assessment and treatment, access control, vulnerability management, secure configuration | Assess risks, document treatment decisions, assign responsibilities, and retain verification evidence |
| PCI DSS | Applicable requirements where payment-card data or in-scope systems are involved | Consider cardholder-data scope and applicable technical controls where relevant |

This is a preliminary framework alignment exercise, not a formal compliance audit. The assessment does not establish that a control has failed solely because a scanner reported a finding, nor does it establish compliance or non-compliance with any framework.

## Remediation Recommendations

The following actions are recommended in order of priority:

1. **Validate high-impact services.** Investigate the root-shell service observation and review exposed remote-access services.
2. **Reduce the attack surface.** Disable unnecessary services and restrict administrative interfaces to authorised networks.
3. **Modernise legacy software.** Upgrade unsupported software and confirm versions against reliable vendor and vulnerability information.
4. **Harden the web server.** Disable directory indexing where unnecessary, remove diagnostic pages, review HTTP methods, and implement appropriate security headers.
5. **Protect database services.** Restrict network exposure, enforce strong authentication, and review administrative interfaces.
6. **Confirm remediation.** Re-scan the authorised target after changes and retain before-and-after evidence.
7. **Complete the Nuclei assessment.** Install or restore an appropriate template set, confirm the templates are available, rerun the scan, and review the resulting output.
8. **Maintain a remediation register.** Assign action owners, target dates, risk status, and verification evidence.


## Learning Outcomes

Through this exercise, I practised:

- Performing network and service discovery using Nmap.
- Reviewing web-server findings using Nikto.
- Preserving technical evidence in multiple file formats.
- Separating scanner observations from confirmed vulnerabilities.
- Developing a structured risk register and prioritising remediation.
- Relating technical findings to recognised GRC frameworks.
- Communicating assessment limitations and recommendations clearly.


## Ethical and Safety Considerations

All scanning activities were intended for an authorised, isolated lab environment using a deliberately vulnerable target. No public, production, or third-party systems were intended to be assessed.

## Lab Files


```text
Lab1-Vulnerability-Assessment/
├── README.md
├── reports/
│   ├── Lab1_Practical_Vulnerability_Assessment_Report.pdf
│   └── Lab1_Practical_Vulnerability_Assessment_Report.docx
└── evidence/
    ├── initial_scan.nmap
    ├── initial_scan.xml
    ├── initial_scan.gnmap
    ├── initial_scan_report.html
    ├── nikto_scan.txt
    ├── nuclei_terminal.log
    └── screenshots/
```
---

**Author:** Olubunmi Adesanmi 
**Course:** GRC103: Risk Assessment and Management Techniques
**Module:**  Risk Identification Techniques 

