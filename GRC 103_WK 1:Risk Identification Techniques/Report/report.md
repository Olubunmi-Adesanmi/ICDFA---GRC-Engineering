# Lab 1: Practical Vulnerability Assessment for GRC Professionals

![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-blue)
![Focus](https://img.shields.io/badge/Focus-Cybersecurity%20%7C%20GRC-green)
![Tools](https://img.shields.io/badge/Tools-Nmap%20%7C%20Nikto%20%7C%20Nuclei-orange)


## Table of Contents

- [1. Introduction](#1-introduction)
- [2. Scenario and Objectives](#2-scenario-and-objectives)
- [3. Lab Environment and Tools](#3-lab-environment-and-tools)
- [4. Assessment Methodology](#4-assessment-methodology)
  - [Phase 1: Discovery and Enumeration](#phase-1-discovery-and-enumeration)
  - [Phase 2: Vulnerability Identification](#phase-2-vulnerability-identification)
- [5. Risk Assessment and Triage](#5-risk-assessment-and-triage)
- [6. Executive Summary](#6-executive-summary)
- [7. GRC and Compliance Framework Mapping](#7-grc-and-compliance-framework-mapping)
- [8. Remediation and Follow-Up Plan](#8-remediation-and-follow-up-plan)
- [9. Evidence and Deliverables](#9-evidence-and-deliverables)
- [10. Limitations](#10-limitations)
- [11. Conclusion and Learning Outcomes](#11-conclusion-and-learning-outcomes)
- [12. Suggested Repository Structure](#12-suggested-repository-structure)
- [Ethical and Safety Statement](#ethical-and-safety-statement)
- [References](#references)


## 1. Introduction

This project documents a practical vulnerability assessment performed as part of my development in Governance, Risk and Compliance (GRC) engineering.

The assessment simulates the work of an internal auditor evaluating a newly discovered development server. It combines network discovery, service enumeration, web-server security checks, risk assessment, and compliance-oriented recommendations.

The main objective is to translate technical observations into business risks and prioritised remediation actions that can support management decision-making.

**Project type:** Practical vulnerability assessment  
**Assessment environment:** Authorised, isolated lab  
**Target:** Metasploitable intentionally vulnerable test server  
**Operating environment:** Kali Linux  
**Primary focus:** Vulnerability identification, risk assessment, GRC mapping, evidence collection, and management reporting

## 2. Scenario and Objectives

The scenario involved assessing a deliberately vulnerable Metasploitable server identified within a simulated development environment.

The assessment objectives were to:

- Discover the target and identify exposed TCP ports.
- Enumerate services, software versions, and operating-system information.
- Identify potential weaknesses using Nmap and Nikto.
- Attempt focused vulnerability scanning with Nuclei.
- Assess findings according to inherent risk criteria.
- Map relevant observations to NIST, CIS Controls, and PCI DSS where applicable.
- Prepare a structured risk assessment and an executive summary for management.
- Preserve scan results and visual evidence to support the assessment.

## 3. Lab Environment and Tools

| Component | Purpose |
|---|---|
| Kali Linux | Assessment workstation |
| Metasploitable | Intentionally vulnerable target |
| Nmap | Host discovery, port scanning, service/version enumeration, and OS detection |
| Nikto | Web-server configuration and vulnerability checks |
| Nuclei | Template-based vulnerability scanning; assessment incomplete |
| xsltproc | Conversion of Nmap XML output to an HTML report |
| Firefox | Reviewing the target web server and HTML scan report |

All testing was intended for the authorised isolated lab. The target address is not published in this README.

## 4. Assessment Methodology

The assessment followed the phases specified in the lab instructions.

### Phase 1: Discovery and Enumeration

#### Step 1 — Network Discovery

The target's reachability was checked using ICMP ping.

```bash
ping -c 4 <TARGET_IP>
```

**Result:** The connectivity check succeeded, according to the recorded lab results.

**GRC relevance:** Asset discovery provides a foundation for asset inventory and risk management. Unknown or unmanaged assets can create blind spots in security monitoring and control coverage.

#### Step 2 — Nmap Port and Service Enumeration

A comprehensive scan was run against the authorised target:

```bash
nmap -sV -sC -O -p- -oA initial_scan <TARGET_IP>
```

The command was used to identify open ports, probe services and versions, run default Nmap scripts, and estimate the operating system.

The XML output was converted into an HTML report:

```bash
xsltproc -o initial_scan_report.html \
/usr/share/nmap/nmap.xsl initial_scan.xml
```

**Recorded result:** Nmap identified 31 open TCP ports and estimated a Linux 2.6-series operating system.

The following files were generated:

- `initial_scan.nmap`
- `initial_scan.gnmap`
- `initial_scan.xml`
- `initial_scan_report.html`

Knowing which services are exposed helps an organisation identify unnecessary network access, reduce its attack surface, and define appropriate security controls.

### Phase 2: Vulnerability Identification

#### Step 3 — Nmap Results Analysis

The Nmap output and HTML report were reviewed to identify service names, version information, and services requiring further investigation.

#### Observed Services and Versions

| Port | Service | Detected Version or Details |
|---:|---|---|
| 21/tcp | FTP | vsftpd 2.3.4 |
| 22/tcp | SSH | OpenSSH 4.7p1 Debian 8ubuntu1 |
| 23/tcp | Telnet | Linux telnetd |
| 25/tcp | SMTP | Postfix smtpd |
| 53/tcp | DNS | ISC BIND 9.4.2 |
| 80/tcp | HTTP | Apache httpd 2.2.8, Ubuntu |
| 111/tcp | RPC | rpcbind 2 |
| 139/tcp | NetBIOS/SMB | Samba 3.X–4.X |
| 445/tcp | SMB | Samba 3.0.20-Debian |
| 512/tcp | Remote execution | netkit-rsh rexecd |
| 513/tcp | Remote login | rlogind |
| 514/tcp | Remote shell | Netkit rshd |
| 1099/tcp | Java RMI | GNU Classpath grmiregistry |
| 1524/tcp | Bindshell | Identified by Nmap as a Metasploitable root shell |
| 2049/tcp | NFS | Versions 2–4 |
| 2121/tcp | FTP | ProFTPD 1.3.1 |
| 3306/tcp | MySQL | 5.0.51a-3ubuntu5 |
| 3632/tcp | distccd | Version 1, GNU 4.2.4 |
| 5432/tcp | PostgreSQL | 8.3.0–8.3.7 |
| 5900/tcp | VNC | Protocol 3.3 |
| 6000/tcp | X11 | Access denied |
| 6667/tcp | IRC | UnrealIRCd; version not established in the supplied results |
| 6697/tcp | IRC | UnrealIRCd; version not established in the supplied results |
| 8009/tcp | AJP | Apache JServ Protocol v1.3 |
| 8180/tcp | HTTP | Apache Tomcat/Coyote JSP engine 1.1 |
| 8787/tcp | Ruby DRb | Ruby 1.8 |
| 45552/tcp | RPC mountd | Versions 1–3 |
| 48741/tcp | RPC lock manager | Versions 1–4 |
| 50703/tcp | Java RMI | GNU Classpath grmiregistry |
| 55353/tcp | RPC status | Version 1 |

The detected operating-system estimate was Linux 2.6.x, with the supplied Nmap output indicating a possible kernel range of 2.6.9–2.6.33.

**Key observation:** The target exposes a broad range of legacy network, remote-access, database, file-sharing, and application services. The presence of a service does not, on its own, prove that it is exploitable; it does identify an area requiring security review.

#### Step 4 — Nikto Web-Server Assessment

Nikto was used to check the target's HTTP service:

```bash
nikto -h http://<TARGET_IP> -o nikto_scan.txt
```

The saved output contained the following observations:

| Finding | Potential Impact | Recommended Action |
|---|---|---|
| Legacy PHP 5.2.4 and Apache 2.2.8 | Exposure to weaknesses affecting old software versions | Upgrade to supported versions and validate the deployed build |
| Directory indexing on `/icons/`, `/doc/`, and `/test/` | Unintended file or directory disclosure | Disable indexing where unnecessary and restrict sensitive paths |
| `phpinfo.php` accessible | Disclosure of technical configuration details | Remove the diagnostic page or restrict access |
| HTTP TRACE enabled | Additional web attack surface | Disable TRACE unless specifically required |
| Recommended security headers missing | Reduced browser-side security protections | Configure suitable headers for the application |
| phpMyAdmin resources accessible | Potential exposure of database administration resources | Restrict access to authorised users and networks |
| Apache MultiViews enabled | May make alternative resource names easier to discover | Review the configuration and disable if unnecessary |
| PHP Easter Egg responses | Unnecessary application information disclosure | Disable the feature or remove the relevant exposure |
| Apache default README present | Disclosure of default server files and implementation details | Remove or restrict unnecessary default files |
| ETag metadata reported by Nikto | Potential disclosure of file metadata | Verify the finding and adjust the configuration if appropriate |

Nikto also reported an uncommon header and a possible PHP information disclosure issue. These observations should be validated in context before final remediation decisions are made.

CVE references appearing in automated tool output are treated as leads for verification, not as proof that the exact vulnerability is exploitable on the target.

#### Step 5 — Nuclei Focused Vulnerability Scanning

The intended Nuclei commands were:

```bash
nuclei -u http://<TARGET_IP> -o nuclei_web_scan.txt
```

```bash
nuclei -target <TARGET_IP> -o nuclei_full_scan.txt
```

Nuclei v3.11.1 was installed, and scan execution was attempted. However, the expected template directory was unavailable. The recorded output files `nuclei_scan.txt` and `nuclei_web_scan.txt` were empty when checked.

**Status: Incomplete.** The evidence does not demonstrate a valid completed Nuclei scan. No conclusion that the target has zero Nuclei-detectable vulnerabilities can be drawn from these empty output files.

The scan should be repeated after an appropriate template set is installed and its availability is confirmed.

## 5. Risk Assessment and Triage

The purpose of risk assessment is to translate technical observations into potential business consequences and prioritise remediation.

The lab's inherent-risk criteria are:

- **High (H):** Potentially easy to exploit and capable of causing major compromise.
- **Medium (M):** May require additional skill or conditions and could result in data leakage or unauthorised access.
- **Low (L):** Primarily limited information disclosure or lower-impact security weaknesses.


| ID | Finding | Affected Service | CVE / Reference | Inherent Risk | Potential Control Mapping | Potential Business Impact |
|---|---|---|---|---|---|---|
| RA-01 | Service identified as a root-shell listener | TCP/1524 | Nmap service identification; validate manually | High — potentially critical | CIS secure configuration and access control; NIST Protect outcomes | Potential unauthorised privileged access and system compromise |
| RA-02 | Legacy vsftpd 2.3.4 version | FTP/21 | CVE-2011-2523 is associated with a backdoored vsftpd 2.3.4 release; verify the exact build | High, provisional | CIS vulnerability management and secure configuration | Potential remote compromise if the affected build is present and vulnerable |
| RA-03 | Unencrypted remote-access services | Telnet/23, rlogin/513, rsh/512 and 514 | Service and protocol observations; no separate CVE assigned | High, provisional | NIST data protection and access-control outcomes; CIS secure configuration | Potential credential interception, unauthorised access, and exposure of session data |
| RA-04 | Legacy Apache and PHP versions | HTTP/80 | Detected version banners; specific vulnerabilities require validation | High, provisional | CIS vulnerability management; applicable web-security requirements | Potential exploitation of unpatched software and compromise of the web service |
| RA-05 | Exposed database services | MySQL/3306 and PostgreSQL/5432 | Nmap service/version observations | High, provisional | CIS access control and secure configuration | Potential unauthorised database access or data exposure |
| RA-06 | Legacy SMB/Samba service | SMB/139 and 445 | Detected Samba version; validate applicable vulnerabilities | High, provisional | CIS vulnerability management and access control | Potential unauthorised file access or service compromise |
| RA-07 | Other remotely accessible services | Java RMI, distccd, VNC, AJP, Ruby DRb, NFS and RPC services | Service exposure; exploitability not established | High, provisional | CIS attack-surface reduction and secure configuration | Potential remote attack paths or unintended access to internal resources |
| RA-08 | Directory indexing enabled | HTTP/80 | Nikto; CWE-548 reference | Medium, provisional | Applicable CIS secure-configuration practices; OWASP guidance | Exposure of filenames, documentation, or unintended resources |
| RA-09 | PHP diagnostic page exposed | HTTP/80 | Nikto; information-disclosure observation | Medium, provisional | Applicable information-protection and secure-configuration controls | Disclosure of system or application configuration information |
| RA-10 | phpMyAdmin resources accessible | HTTP/80 | Nikto observation | Medium, provisional | Access control and administrative-interface protection | Increased exposure of database-management functions |
| RA-11 | HTTP TRACE enabled | HTTP/80 | Nikto observation | Medium, provisional | Web-server hardening and applicable OWASP guidance | Additional HTTP attack surface; practical exploitability depends on the application and client configuration |
| RA-12 | Recommended security headers missing | HTTP/80 | Nikto observations | Low–Medium, provisional | Applicable secure-configuration controls | Reduced defence-in-depth for browser-based security |
| RA-13 | Apache MultiViews enabled | HTTP/80 | Nikto observation; X-Force reference reported by scanner | Low, provisional | Secure configuration and minimisation of unnecessary functionality | Easier discovery of alternative resources in some configurations |
| RA-14 | ETag metadata and default documentation exposure | HTTP/80 | Nikto observations; CVE reference requires verification | Low, provisional | Information disclosure and secure configuration | Unnecessary file metadata or platform information may be disclosed |
| RA-15 | Nuclei assessment not completed | Nuclei scan process | Missing templates and empty output files | Not a vulnerability rating | Assessment completeness and evidence management | The assessment may lack additional vulnerability coverage until the scan is completed |


## 6. Executive Summary

**To:** IT Management  
**From:** GRC Audit Team  
**Date:** 21 October 2026  
**Subject:** Vulnerability Assessment Findings — Development Test Server

### Overview

A vulnerability assessment was conducted against the authorised Metasploitable test server in an isolated lab environment. Nmap identified 31 open TCP ports, while Nikto reported several web-server configuration and information-disclosure concerns.

The combined results indicate a broad attack surface, including legacy software, remote-access services, exposed database ports, a service identified as a root-shell listener, and web-server weaknesses. These observations warrant prioritised investigation and remediation within the simulated environment.


### Key Risks

**High priority — Potential privileged access and remote compromise**

The service on port 1524 was identified by Nmap as a Metasploitable root shell. The legacy vsftpd 2.3.4 version also requires immediate verification because an affected release is associated with CVE-2011-2523. Neither observation should be presented as a confirmed successful exploit without additional validation.

**High priority — Unnecessary and insecure service exposure**

Telnet, remote shell/login services, legacy file-sharing services, database services, and other remotely accessible applications increase the target's attack surface. Services that are not required should be disabled or restricted.

**Medium priority — Web-server information disclosure and configuration weaknesses**

Nikto reported directory indexing, an accessible PHP diagnostic page, accessible phpMyAdmin resources, and other configuration concerns. These may disclose useful technical information or expose administrative functionality.

### Recommended Actions

1. **Contain and prioritise:** Keep the deliberately vulnerable target isolated from production and untrusted networks. Prioritise investigation of the root-shell service and legacy FTP version.
2. **Reduce exposure:** Disable unnecessary services and restrict access to required remote-management, database, file-sharing, and application services.
3. **Harden and update:** Replace unsupported software, remove diagnostic and default files, disable unnecessary directory indexing and HTTP methods, and apply suitable security configurations.
4. **Validate remediation:** Repeat the authorised scans after changes and retain before-and-after evidence.
5. **Complete the assessment:** Restore the appropriate Nuclei templates, confirm the scan runs, and document the actual findings.
6. **Improve governance:** Assign remediation owners, target dates, risk acceptance decisions where appropriate, and evidence requirements for closure.

### Management Conclusion

The assessment highlights why technical scanning should be supported by risk analysis, control mapping, and evidence-based reporting. Remediation should be prioritised according to potential business impact, confirmed exposure, and the importance of the affected service.

These results relate to the lab target and are not a formal compliance audit of a production organisation.

## 7. GRC and Compliance Framework Mapping

The findings can inform a review against applicable security framework areas.

| Framework | Relevant Areas | Application |
|---|---|---|
| NIST Cybersecurity Framework | Asset management, risk assessment, access control, data protection, and protective technology | Maintain an accurate asset inventory, evaluate exposure, and apply appropriate controls |
| CIS Critical Security Controls | Asset inventory, secure configuration, account/access management, and continuous vulnerability management | Identify exposed services, remove unnecessary functionality, review access, and remediate weaknesses |
| OWASP guidance and Top 10 | Web-application security and server hardening | Investigate information disclosure and reduce unnecessary web-server exposure |
| PCI DSS | Requirement 6 and other requirements applicable to the system's actual scope | Apply relevant security practices if payment-card data or in-scope systems are involved |
| ISO/IEC 27001:2022 | Risk assessment and treatment, access control, vulnerability management, and secure configuration | Document risks, treatment decisions, responsibilities, and verification evidence |

No PCI DSS applicability or compliance breach can be established from these lab results alone.

## 8. Remediation and Follow-Up Plan

| Priority | Action | Suggested Responsible Role | Verification Evidence |
|---|---|---|---|
| Immediate | Investigate the port 1524 root-shell service and isolate or disable it if confirmed unnecessary | Lab/System Administrator | Service review, configuration evidence, and repeat scan |
| Immediate | Validate the vsftpd 2.3.4 build and remediate if affected | System Administrator | Installed version, patch evidence, and scan results |
| High | Review Telnet, rsh, rlogin, SMB, RMI, distccd, database, and other exposed services | System Administrator | Approved service inventory and firewall/service configuration |
| High | Upgrade or replace unsupported Apache, PHP, database, and supporting components as appropriate | Application/System Owner | Version evidence and validated remediation results |
| Medium | Remove public diagnostic pages and restrict phpMyAdmin access | Web/Application Administrator | Access-control test and updated Nikto output |
| Medium | Disable unnecessary directory indexing, review MultiViews, and configure suitable headers | Web/Application Administrator | Configuration review and repeat web scan |
| Medium | Complete the Nuclei scan after restoring the template set | Assessment Operator | Successful command output, template availability, and saved results |
| Ongoing | Maintain the risk register and document closure decisions | GRC/Risk Owner | Updated risk register, assigned owners, due dates, and closure evidence |

## 9. Evidence and Deliverables

The evidence directory used during the lab was:

```text
/home/kali/Lab1_Vulnerability_Assessment/evidence/
```

The following files were present when the directory was reviewed:

| File | Status | Purpose |
|---|---|---|
| `initial_scan.nmap` | Generated | Human-readable Nmap output |
| `initial_scan.xml` | Generated | Structured Nmap output |
| `initial_scan.gnmap` | Generated | Grepable Nmap output |
| `initial_scan_report.html` | Generated | HTML presentation of the Nmap results |
| `nikto_scan.txt` | Generated | Nikto web-server findings |
| `nuclei_terminal.log` | Generated | Records the Nuclei execution issue |
| `nuclei_scan.txt` | Empty at review | Nuclei output file; no results recorded |
| `nuclei_web_scan.txt` | Empty at review | Web Nuclei output file; no results recorded |


## 10. Limitations

- The assessment was performed against an intentionally vulnerable lab target.
- Service detection and banners do not establish exploitability on their own.
- Risk ratings are provisional and should be revisited after validation.
- Default credentials were not confirmed by the evidence reviewed.
- Nikto CVE references require validation against the precise product build and finding.
- Nuclei output files were empty, so the Nuclei assessment cannot be considered complete.
- Framework mapping identifies relevant control areas; it does not amount to a formal compliance determination.
- The assessment does not constitute a complete penetration test or a certification audit.

## 11. Conclusion and Learning Outcomes

This lab provided practical experience in moving from technical discovery to risk-based security reporting. The work demonstrates how open ports, service versions, and web-server observations can be assessed in terms of attack surface, information exposure, potential business impact, and remediation priorities.

The main learning outcome was that a GRC professional must do more than run scanning tools. Findings should be supported by evidence, assigned appropriate risk ratings, mapped carefully to applicable controls, and translated into actions that management can prioritise and verify.

This project forms part of my ongoing development in **GRC engineering**, with a focus on connecting technical evidence to governance, risk assessment, and control improvement.


## Ethical and Safety Statement

All assessment activities were intended for the authorised, isolated lab environment and deliberately vulnerable target. The commands and workflow should only be used on systems for which explicit permission has been granted.

---

## References

Center for Internet Security. (n.d.). *CIS Critical Security Controls v8.1*. https://www.cisecurity.org/controls/v8-1

International Organization for Standardization. (2022). *ISO/IEC 27001:2022—Information security, cybersecurity and privacy protection—Information security management systems—Requirements*. https://www.iso.org/standard/27001

MITRE. (n.d.). *CWE-548: Exposure of information through directory listing*. https://cwe.mitre.org/data/definitions/548.html

National Institute of Standards and Technology. (n.d.). *National Vulnerability Database: CVE-2011-2523*. https://nvd.nist.gov/vuln/detail/CVE-2011-2523

Nmap Project. (n.d.). *Nmap reference guide*. https://nmap.org/book/man.html

OWASP Foundation. (2025). *OWASP Top 10:2025*. https://top10.owasp.org/2025/

OWASP Foundation. (n.d.). *Web Security Testing Guide*. https://owasp.org/projects/web-security-testing-guide

Pascoe, C., Quinn, S., & Scarfone, K. (2024). *The NIST Cybersecurity Framework (CSF) 2.0* (NIST Cybersecurity White Paper 29). National Institute of Standards and Technology. https://doi.org/10.6028/NIST.CSWP.29

PCI Security Standards Council. (n.d.). *Document library: PCI DSS v4.0.1*. https://www.pcisecuritystandards.org/document_library/

ProjectDiscovery. (n.d.-a). *Nuclei documentation: Supported input formats*. https://docs.projectdiscovery.io/tools/nuclei/input-formats

ProjectDiscovery. (n.d.-b). *Nuclei templates* [GitHub repository]. https://github.com/projectdiscovery/nuclei-templates

Sullo. (n.d.). *Nikto documentation*. GitHub. https://github.com/sullo/nikto/wiki/

### Reference and validation note

These sources provide guidance for the assessment tools and frameworks. Their inclusion does not mean that every observed issue is a confirmed vulnerability or compliance breach. In particular, CVE-2011-2523 applies to affected vsftpd 2.3.4 distributions downloaded during a specific period in 2011, so the exact target build must be validated before the finding is treated as confirmed. [NVD](https://nvd.nist.gov/vuln/detail/CVE-2011-2523)

**Author:** Olubunmi Adesanmi  
**Course:** GRC 103:Risk Assessment and Management Techniques
**Module:** Risk Identification Techniques 
Lab 1 — Practical Vulnerability Assessment for GRC Professionals  


