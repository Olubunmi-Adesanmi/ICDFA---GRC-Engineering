# Lab 1: Practical Vulnerability Assessment for GRC Professionals

![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-blue)
![Focus](https://img.shields.io/badge/Focus-Cybersecurity%20%7C%20GRC-green)
![Tools](https://img.shields.io/badge/Tools-Nmap%20%7C%20Nikto%20%7C%20Nuclei-orange)


**Prepared by:** Olubunmi Adesanmi 

**Course:**  GRC103 — Risk Assessment and Management Techniques 

**Module:** Risk Identification Techniques 

**Assessment role:** Internal GRC Auditor 

**Target:** Metasploitable 2 

**Environment:** Kali Linux 


## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Introduction and Assessment Objectives](#2-introduction-and-assessment-objectives)
3. [Scenario, Scope, and Limitations](#3-scenario-scope-and-limitations)
4. [Lab Environment, Tools, and Methodology](#4-lab-environment-tools-and-methodology)
5. [Phase 1: Discovery and Enumeration](#5-phase-1-discovery-and-enumeration)
6. [Phase 2: Vulnerability Identification](#6-phase-2-vulnerability-identification)
7. [Phase 3: Risk Assessment and Triage](#7-phase-3-risk-assessment-and-triage)
   - [Likelihood, Impact, and Inherent Risk Scoring](#73-likelihood-impact-and-inherent-risk-scoring)
8. [GRC and Compliance Framework Mapping](#8-grc-and-compliance-framework-mapping)
9. [Remediation and Follow-Up Plan](#9-remediation-and-follow-up-plan)
10. [Evidence Inventory and Submission Checklist](#10-evidence-inventory-and-submission-checklist)
11. [Conclusion and Learning Outcomes](#11-conclusion-and-learning-outcomes)
12. [Ethical and Safety Statement](#12-ethical-and-safety-statement)
13. [References](#13-references)
14. [Appendix A: Commands Used](#appendix-a-commands-used)
15. [Appendix B: Evidence and Interpretation Notes](#appendix-b-evidence-and-interpretation-notes)

---

## Document Control

| Item | Details |
|---|---|
| Report title | Lab 1: Practical Vulnerability Assessment for GRC Professionals |
| Assessment purpose | Identify exposed services and potential security weaknesses, assess risk, map relevant control themes, and recommend remediation |
| Assessment target | Metasploitable lab server; target IP intentionally omitted from this report |
| Assessment workstation | Kali Linux |
| Evidence reviewed | Nmap and Nikto outputs and evidence-directory listing supplied for the lab; file timestamps indicate 19 October 2026 |
| Intended audience | IT Management, system owners, security and GRC reviewers, and course assessors |
| Handling | Training report based on an authorised isolated lab. Do not interpret as a production-system penetration test or compliance certification. |

---

## 1. Executive Summary

**To:** IT Management  
**From:** GRC Audit Team  
**Date:** 23 October 2026  
**Subject:** Vulnerability Assessment and Risk Prioritisation — Metasploitable Development Test Server

### 1.1 Purpose and scope

A vulnerability assessment was conducted against a deliberately vulnerable Metasploitable server in an authorised, isolated lab environment. The objective was to identify exposed network services and potential security weaknesses, assess their possible business consequences, and propose remediation actions from a Governance, Risk and Compliance (GRC) perspective. The assessment used Nmap for host discovery, port and service enumeration, and operating-system detection; Nikto for web-server checks; and an attempted Nuclei scan for template-based vulnerability identification.

### 1.2 Overall results

Nmap identified **30 open TCP ports** and estimated that the target was running a Linux 2.6-series operating system. The exposed services included FTP, SSH, Telnet, remote shell/login services, SMB/Samba, NFS, MySQL, PostgreSQL, Java RMI, VNC, Apache HTTP, Tomcat, AJP, distccd, UnrealIRCd, and other network services. The breadth of exposed services represents a substantial attack surface within the lab and warrants review of service necessity, network reachability, authentication, and configuration.

Nikto reported multiple web-server concerns, including legacy PHP and Apache version banners, directory indexing, an accessible PHP diagnostic page, accessible phpMyAdmin resources, an enabled HTTP TRACE method, and missing recommended security headers. These observations indicate potential weaknesses in software maintenance, information disclosure, and secure configuration.

Nuclei v3.11.1 was installed and an execution was made.The lab instructions called for web-focused and broader Nuclei scans using commands:
nuclei -u http://192.168.**.*** -o nuclei_web_scan.txt
nuclei -target 192.168.**.*** -o nuclei_full_scan.txt

Assessment Findings: CVE-2012-1823 High; CVE-2026-109618 version/EOL branch Critical
High-priority PHP exposure; confirm configuration and CVE applicability

### 1.3 . Business Impact by Technical Finding

No.	Finding / Security Weakness	Potential Business Impact	Preliminary Priority
1	Outdated Apache and PHP software	Exploitation of applicable vulnerabilities could compromise the web server, expose information or disrupt services.	High
2	PHP CGI vulnerability — CVE-2012-1823	If the vulnerable CGI configuration is present, an attacker may execute commands remotely and compromise application data or server resources.	High; verify CGI configuration
3	PHP end-of-life version detection	Unsupported software increases exposure to known vulnerabilities and ongoing maintenance risk. The specific newer CVE requires version-specific validation.	High software lifecycle concern; specific CVE unconfirmed
4	Anonymous FTP access and legacy FTP service	Unauthorised users may retrieve exposed files, potentially disclosing confidential information.	High
5	Telnet and legacy remote-shell services	Unencrypted communications may expose credentials and session data, increasing the risk of account compromise.	High
6	Root-shell-labelled service on port 1524	If unauthorised root-level access is available, an attacker could gain extensive system control, access data or alter configurations.	Critical potential impact; validate access
7	Exposed MySQL and PostgreSQL services	Weak authentication or access controls could permit unauthorised access, disclosure, alteration or deletion of business records.	High; configuration-dependent
8	Exposed SMB and NFS services	Inadequately restricted file-sharing services could expose confidential files and shared resources.	High; validate permissions
9	Exposed phpMyAdmin and diagnostic files	Accessible administration resources and diagnostic pages may reveal database, software and configuration information.	Medium–High

### 1.4 Highest-priority risks

1. **Potential privileged access:** Nmap identified TCP port 1524 as a service associated with a Metasploitable root shell. If the service offers the access indicated by the scan and is reachable by an unauthorised party, the potential impact could include full host compromise. The service identity and exposure should be validated.
2. **Legacy FTP service:** Nmap identified `vsftpd 2.3.4`. CVE-2011-2523 affects a specific backdoored vsftpd 2.3.4 distribution downloaded during a defined period in 2011. The version banner makes this a priority for verification but does not, alone, prove that the affected build is present.
3. **Excessive and potentially insecure service exposure:** Telnet, traditional remote shell/login services, file-sharing services, database ports, and other remotely accessible applications increase the number of possible entry points. Unnecessary services should be disabled and required services restricted.
4. **Web-server information disclosure and configuration issues:** Directory indexing, an accessible `phpinfo.php` page, accessible phpMyAdmin resources, and other Nikto observations should be reviewed and remediated where confirmed.
5. **Incomplete vulnerability coverage:** Nuclei needs a functioning template set and a repeat scan before its findings can contribute to the final risk assessment.

### 1.4 Management recommendations

Management should keep the intentionally vulnerable target isolated, prioritise validation of the port 1524 service and the FTP build, reduce unnecessary network exposure, replace unsupported software, harden the web server, and ensure that database and administrative interfaces are only available to authorised users and systems. Each remediation should have an accountable owner, target date, and verification evidence. A follow-up assessment should confirm that the changes have reduced the documented risks.

The findings can inform a review against the NIST Cybersecurity Framework, CIS Critical Security Controls, and relevant web-security guidance. PCI DSS should be considered only if the system is in the scope of a payment-card environment. **This report does not establish formal compliance violations or successful exploitation.** All risk ratings are provisional where exploitation, configuration, or exact software builds have not been independently confirmed.

---

## 2. Introduction and Assessment Objectives

### 2.1 Introduction

Technical vulnerability assessment is a supporting activity within cybersecurity governance and risk management. For GRC professionals, the value of scanning is not limited to listing ports or scanner alerts; it also involves determining what the evidence means, how a weakness could affect an organisation, which controls may be relevant, and what action is needed to reduce risk. This report translates the lab's technical results into structured observations and management-focused recommendations.

The assessment was performed on Metasploitable, an intentionally vulnerable test server, using the lab's prescribed tools. The results should be understood within that training context and not generalised to another host without independent testing.

### 2.2 Objectives

The assessment aimed to:

- Confirm that the authorised lab target was reachable.
- Identify open TCP ports, services, service versions, and an operating-system estimate.
- Review Nmap output and preserve results in readable, structured, and HTML formats.
- Assess the target's HTTP service using Nikto and document its reported observations.
- Attempt focused vulnerability scanning with Nuclei.
- Classify significant observations using the lab's inherent-risk criteria.
- Connect relevant observations to recognised security-control and compliance themes.
- Recommend practical remediation and follow-up validation steps.
- Maintain a clear distinction between scanner observations, verified vulnerabilities, and limitations in assessment coverage.

### 2.3 Deliverables

The lab brief requires Nmap output files, a screenshot of the Nmap HTML report, Nikto and Nuclei output, a completed risk assessment table, and an executive summary. The evidence inventory in Section 10 records which files were present when the supplied evidence directory was reviewed and identifies remaining evidence gaps.

---

## 3. Scenario, Scope, and Limitations

### 3.1 Scenario

The assessment simulates an internal audit of a newly discovered Metasploitable server within a development environment. The task is to identify potential vulnerabilities and explain their implications for security risk and control effectiveness.

### 3.2 In scope

- Connectivity verification to the designated Metasploitable target.
- Nmap TCP port scanning, service/version detection, default scripts, and operating-system detection.
- Review of Nmap `.nmap`, `.gnmap`, `.xml`, and generated HTML output.
- Nikto assessment of the target's HTTP service.
- Attempted Nuclei scanning, limited to the evidence available.
- Provisional risk assessment and high-level mapping to GRC frameworks.
- Recommendations for remediation and validation.

### 3.3 Out of scope

- Scanning any public, production, organisational, or third-party system.
- Exploitation beyond the authorised lab tasks documented in the evidence.
- Confirmation of credentials or password strength where no test evidence was supplied.
- A formal PCI DSS assessment, ISO/IEC 27001 certification audit, or complete penetration test.
- A conclusive vulnerability determination for every legacy service based solely on a version banner.

### 3.4 Limitations

- Service/version detection and scanner output can be incomplete or inaccurate and may require manual verification.
- Nmap's operating-system identification is an estimate, not definitive proof of the exact kernel build.
- Some Nikto observations are informational or configuration-related and do not necessarily represent exploitable vulnerabilities.
- References to CVEs in scanner output have not all been independently confirmed against the exact target build.
- The exact vsftpd build associated with CVE-2011-2523 has not been independently established from the supplied output.
- The Nuclei template directory could not be found, and its output files were empty; the Nuclei assessment remains incomplete.
- The evidence directory listing did not show a screenshot of the Nmap HTML report. A Nikto screenshot was reported as captured, but its filename was not visible in that listing.


---

## 4. Lab Environment, Tools, and Methodology

### 4.1 Environment

| Component | Description |
|---|---|
| Assessment workstation | Kali Linux |
| Target | Metasploitable intentionally vulnerable test server |
| Network context | Authorised isolated lab network |
| Nmap | Used for discovery, port/service enumeration, version detection, and OS estimation; precise version not recorded in the supplied notes |
| Nikto | Version 2.6.1, according to the supplied lab notes/output context |
| Nuclei | Version 3.11.1 |
| xsltproc | Used to create an HTML view of Nmap XML output |
| Browser | Firefox, for reviewing web resources and HTML report |

### 4.2 Methodology

The assessment followed the three phases specified in the assignment:

**Phase 1 — Discovery and enumeration:** Verify target reachability, scan all TCP ports, enumerate services and versions, and generate output files and an HTML report.

**Phase 2 — Vulnerability identification:** Review Nmap findings, run Nikto against the HTTP service, and attempt focused Nuclei scans.

**Phase 3 — Analysis and reporting:** Triage observations, assign provisional inherent-risk ratings, map relevant control themes, produce management recommendations, and document evidence and limitations.

### 4.3 Risk-rating approach

These lab's inherent-risk criteria are used:

- **High (H):** Potentially easy to exploit and capable of resulting in full system compromise or similarly significant impact.
- **Medium (M):** May require additional skill or conditions and could result in data leakage or unauthorised access.
- **Low (L):** Primarily information disclosure or lower-impact security weaknesses.

Ratings in this report are **provisional inherent-risk judgments** based on the evidence and plausible impact. They are not verified exploitability scores and do not account for controls that may exist outside the evidence supplied. A final organisational risk decision should also consider asset criticality, reachability, likelihood, compensating controls, and business impact.

---

## 5. Phase 1: Discovery and Enumeration

### 5.1 Step 1 — Network discovery

A four-packet ping check was performed against the target using the lab command:

```bash
ping -c 4 192.168.**.***
```

**Result:** The connectivity check succeeded according to the recorded lab results.

**GRC interpretation:** Asset discovery is a foundation for asset inventory and risk management. Systems that are unknown or not represented in an asset inventory can be missed by vulnerability management, monitoring, and access-control processes. Discovery alone does not establish ownership or authorisation; discovered assets should be matched to an approved inventory.

### 5.2 Step 2 — Nmap port and service enumeration

The all-TCP-port scan used the following command pattern, with the authorised target address substituted locally:

```bash
nmap -sV -sC -O -p- -oA initial_scan 192.168.**.***
```

The options request service/version detection (`-sV`), default scripts (`-sC`), operating-system detection (`-O`), all TCP ports (`-p-`), and output in three formats (`-oA`). The XML file was converted to HTML with:

```bash
xsltproc -o initial_scan_report.html \
  /usr/share/nmap/nmap.xsl initial_scan.xml
```

**Recorded result:** Nmap identified 31 open TCP ports. Its operating-system output indicated a Linux 2.6-series system, with a possible kernel range of 2.6.9–2.6.33.

### 5.3 Open-port and service inventory

The following table transcribes the 31 open TCP entries in the supplied Nmap output. Version banners and service identifications should be validated before they are used as the basis for a definitive vulnerability claim.

| Port | State | Service | Detected version / Nmap detail |
|---:|---|---|---|
| 21/tcp | Open | FTP | vsftpd 2.3.4 |
| 22/tcp | Open | SSH | OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0) |
| 23/tcp | Open | Telnet | Linux telnetd |
| 25/tcp | Open | SMTP | Postfix smtpd |
| 53/tcp | Open | DNS | ISC BIND 9.4.2 |
| 80/tcp | Open | HTTP | Apache httpd 2.2.8 ((Ubuntu) DAV/2) |
| 111/tcp | Open | RPC | rpcbind 2 (RPC #100000) |
| 139/tcp | Open | NetBIOS/SMB | Samba smbd 3.X–4.X; workgroup WORKGROUP |
| 445/tcp | Open | SMB | Samba smbd 3.0.20-Debian; workgroup WORKGROUP |
| 512/tcp | Open | Remote execution | netkit-rsh rexecd |
| 513/tcp | Open | Remote login | OpenBSD or Solaris rlogind (Nmap fingerprint) |
| 514/tcp | Open | Remote shell | Netkit rshd |
| 1099/tcp | Open | Java RMI | GNU Classpath grmiregistry |
| 1524/tcp | Open | Bindshell | Identified by Nmap as “Metasploitable root shell” |
| 2049/tcp | Open | NFS | Versions 2–4 |
| 2121/tcp | Open | FTP | ProFTPD 1.3.1 |
| 3306/tcp | Open | MySQL | 5.0.51a-3ubuntu5 |
| 3632/tcp | Open | distccd | distccd v1, GNU 4.2.4 (Ubuntu 4.2.4-1ubuntu4) |
| 5432/tcp | Open | PostgreSQL | PostgreSQL DB 8.3.0–8.3.7 |
| 5900/tcp | Open | VNC | VNC protocol 3.3 |
| 6000/tcp | Open | X11 | Access denied |
| 6667/tcp | Open | IRC | UnrealIRCd; version not established in supplied table |
| 6697/tcp | Open | IRC | UnrealIRCd; version not established in supplied table |
| 8009/tcp | Open | AJP | Apache JServ Protocol v1.3 |
| 8180/tcp | Open | HTTP | Apache Tomcat/Coyote JSP engine 1.1 |
| 8787/tcp | Open | Ruby DRb | Ruby DRb RMI (Ruby 1.8; path `/usr/lib/ruby/1.8/drb`) |
| 45552/tcp | Open | RPC mountd | Versions 1–3 (RPC #100005) |
| 48741/tcp | Open | RPC lock manager | Versions 1–4 (RPC #100021) |
| 50703/tcp | Open | Java RMI | GNU Classpath grmiregistry |
| 55353/tcp | Open | RPC status | Version 1 (RPC #100024) |

### 5.4  GRC interpretation

The service inventory indicates several risk areas for review:

- **Attack-surface management:** 31 open TCP ports create a need to confirm the business requirement for every service and close unnecessary exposure.
- **Remote administration:** Telnet, rsh, and rlogin are legacy protocols and should not normally be exposed when secure alternatives are available.
- **Data-store exposure:** MySQL and PostgreSQL were detected as listening services. The scan does not prove that these services are reachable from outside the lab network or that authentication can be bypassed; their reachability and access controls require review.
- **Legacy components:** Several detected software versions are old and warrant support-status and patch-level verification.
- **Potentially high-impact service:** The service identified on port 1524 requires priority verification because the Nmap label associates it with a root shell.
- **Further validation required:** Java RMI, distccd, VNC, AJP, Ruby DRb, NFS, RPC, SMB, and IRC services should be investigated for necessity, access restrictions, and applicable vulnerabilities rather than assumed exploitable solely because they are open.

Open ports are not automatically compliance breaches. The compliance concern arises when an exposed service is unnecessary, inadequately controlled, inconsistent with the system's approved baseline, or violates a requirement that applies to the environment.

---

## 6. Phase 2: Vulnerability Identification

### 6.1 Step 3 — Nmap result analysis

The Nmap output and generated HTML report were reviewed for detected service names, version strings, and unusual service exposure. These results formed the basis for the inventory in Section 5.3 and for prioritising further review. No separate evidence of successful exploitation was supplied.

### 6.2 Step 4 — Nikto web-server assessment

Nikto was run against the target's HTTP service using the following command pattern:

```bash
nikto -h http://192.168.**.*** -o nikto_scan.txt
```

The supplied Nikto output included the observations below. The risk comments indicate plausible impact and required validation, rather than a claim that exploitation has been demonstrated.

| ID | Nikto observation | Potential impact / interpretation | Recommended treatment |
|---|---|---|---|
| WEB-01 | `X-Powered-By` disclosed PHP 5.2.4-2ubuntu5.10; Nikto described PHP 5.2.4 as outdated | Technology disclosure and potential exposure to weaknesses affecting unsupported software | Verify installed package/build and upgrade to a supported version where feasible |
| WEB-02 | Apache httpd 2.2.8 reported as outdated | Legacy web-server software may contain unpatched weaknesses | Confirm the actual package and support state; upgrade or replace |
| WEB-03 | Directory indexing reported on `/icons/`, `/doc/`, and `/test/` | Directory contents or filenames may be disclosed; sensitivity depends on contents and access | Disable indexing where not needed and remove or restrict unnecessary content |
| WEB-04 | `/phpinfo.php` returned output from PHP `phpinfo()`; Nikto referenced CWE-552 | Detailed configuration output can support attacker reconnaissance | Remove the diagnostic page or restrict it to authorised administrators |
| WEB-05 | `/phpMyAdmin/changelog.php`, `/phpMyAdmin/ChangeLog`, `/phpMyAdmin/Documentation.html`, and `/phpMyAdmin/README` were accessible | Database administration resources and documentation may be exposed; this does not itself prove administrative login is possible | Restrict phpMyAdmin to authorised users and networks; remove unused resources |
| WEB-06 | HTTP TRACE was enabled and responded | May increase exposure to certain cross-site tracing scenarios, depending on the application and client environment | Disable TRACE if there is no documented requirement and verify after remediation |
| WEB-07 | Nikto reported missing `X-Content-Type-Options`, `Referrer-Policy`, `Permissions-Policy`, `Strict-Transport-Security`, and `Content-Security-Policy` headers | Missing headers may reduce browser-side, defence-in-depth protections; HSTS applicability depends on HTTPS use | Review the application and deployment model; configure suitable headers and test for functional impact |
| WEB-08 | Apache MultiViews was enabled and `index.php` was identified as an alternative for `/index` | May make alternate resource names easier to discover in some configurations | Review whether content negotiation is required; disable if unnecessary |
| WEB-09 | PHP Easter Egg query responses were reported | May disclose unnecessary PHP or implementation details | Disable the feature where applicable and verify the responses no longer reveal extra information |
| WEB-10 | `/icons/README` was identified as an Apache default file | Default content may disclose implementation details | Remove unnecessary defaults or restrict access |
| WEB-11 | An uncommon `TCN` header with value `list` was reported | May reveal server negotiation behaviour; relevance depends on context | Review the header and configuration; retain only if required |
| WEB-12 | A response to a non-standard method string (`RDEEKDPP`, as displayed in the supplied output) was reported | May indicate unusual handling of HTTP methods or a scanner false positive | Validate manually and review accepted methods and server logs |
| WEB-13 | Nikto reported ETag metadata for `/phpMyAdmin/ChangeLog`, including an inode, size, and modification time; it cited CVE-2003-1418 | May disclose file metadata; applicability of the cited CVE is not established by the scan alone | Verify the server behaviour and reference applicability; minimise unnecessary metadata where appropriate |
| WEB-14 | Nikto associated browseable `/doc/` with CWE-548 and referenced CVE-1999-0678 | Potential directory disclosure; the scanner reference requires context-specific validation | Confirm whether sensitive content is exposed and remove/restrict unnecessary documentation |
| WEB-15 | Nikto raised a note about `X-Frame-Options` and modern `Content-Security-Policy` framing controls | Framing protection should be reviewed for the actual application; the scanner's wording is not itself proof of exploitation | Configure a suitable `frame-ancestors` directive and/or compatible header according to application needs |

The Nikto output also noted that server responses to unusual methods may cause false positives. Therefore, findings should be confirmed manually where practicable. A scanner reference to a CVE is not a verified finding unless the affected product/version and conditions match.

#### Web assessment conclusion

Nikto identified several plausible configuration and information-disclosure issues requiring remediation review. The highest-value actions are to remove the diagnostic page, restrict database administration resources, disable unneeded directory indexing and HTTP methods, and replace unsupported web-server components. Header recommendations should be tailored to the application's actual HTTPS and browser-security requirements; the absence of a header is not automatically a severe vulnerability in every deployment.

### 6.3 Step 5 — Nuclei focused vulnerability scanning

The lab instructions called for web-focused and broader Nuclei scans using commands similar to:

```bash
nuclei -u http://192.168.**.*** -o nuclei_web_scan.txt
nuclei -target 192.168.**.*** -o nuclei_full_scan.txt
```

Nuclei v3.11.1 was installed. The lab instructions called for web-focused and broader Nuclei scans using commands:
nuclei -u http://192.168.**.*** -o nuclei_web_scan.txt
nuclei -target 192.168.**.*** -o nuclei_full_scan.txt.

During the attempt,it initially stated that  the tool could not find the expected template path under /home/kali/.local/nuclei-templates. But new templates was downloaded and it was resolved.

Assessment Findings summary: CVE-2012-1823 High; CVE-2026-109618 version/EOL branch Critical
High-priority PHP exposure; confirm configuration and CVE applicability

---

## 7. Phase 3: Risk Assessment and Triage

### 7.1 Assessment approach

The risk register below prioritises material observations by plausible impact and exposure. It includes the CVE/reference where a reference was provided or is relevant for verification. A rating of High is provisional where the finding could result in substantial compromise if confirmed. Medium and Low ratings similarly require validation against actual configuration and business context.

The “control relevance” column identifies potential framework/control themes. It does **not** assert that a formal compliance breach has been established. The assessor should document the applicable framework version, scope, requirement, and evidence before making a compliance determination.

### 7.2 Consolidated risk assessment register

| ID | Finding / affected service | CVE or reference | Inherent risk | Potential control relevance | Business impact and recommended response |
|---|---|---|---|---|---|
| RA-01 | Service identified as a Metasploitable root shell on TCP/1524 | Nmap service identification; manual validation required | High, provisional | Secure configuration, least privilege, access control; CIS Controls 4 and 6 themes | If confirmed reachable and privileged, unauthorised host control, data exposure, modification, or disruption. Investigate immediately; keep isolated; disable or restrict if unnecessary; retain verification evidence. |
| RA-02 | FTP on TCP/21, vsftpd 2.3.4 | CVE-2011-2523 applies to a specific backdoored distribution downloaded 2011-06-30 to 2011-07-03 | High, provisional | Vulnerability management and secure configuration; CIS Controls 2, 4, and 7 themes | Potential remote compromise if the affected build is present and exploitable. Verify package/build; patch, replace, or disable as appropriate; retest. |
| RA-03 | Telnet and traditional rsh/rlogin services on TCP/23, 512–514 | Protocol/service observations; no separate CVE assigned | High, provisional | Access control and protection of data in transit; CIS Controls 4 and 6 themes | Potential credential/session exposure and unauthorised access, depending on reachability and configuration. Disable if unnecessary; use secure administration; restrict management access. |
| RA-04 | Legacy Apache 2.2.8 and PHP 5.2.4 version banners | Version banners; specific vulnerability mapping not confirmed | High, provisional | Software inventory, vulnerability management, secure configuration; CIS Controls 2 and 7 themes | Potential exposure to known weaknesses if affected software is present and unpatched. Validate installed versions/support status, update or replace, and repeat scan. |
| RA-05 | Database listeners: MySQL TCP/3306 and PostgreSQL TCP/5432 | Nmap version observations | High, provisional; exposure/authentication not validated | Access control, network segmentation, secure configuration | Potential unauthorised data access or service compromise if reachable and inadequately protected. Restrict to required clients, review authentication, patch, and check network rules. |
| RA-06 | SMB/Samba services on TCP/139 and 445 | Detected Samba banners; applicable vulnerability not verified | High, provisional | Asset/software inventory, vulnerability management, least privilege | Potential file-share exposure or exploitation if the build/configuration is vulnerable. Validate build and share permissions; patch; restrict network access. |
| RA-07 | Java RMI, distccd, VNC, AJP/Tomcat, Ruby DRb, NFS and RPC services | Exposed services as enumerated by Nmap; no specific exploit confirmed | High, provisional for exposure review | Attack-surface reduction, secure configuration, access management | Potential additional attack paths or access to internal resources. Confirm business need, restrict to trusted hosts, disable unused services, and verify versions/configuration. |
| RA-08 | UnrealIRCd on TCP/6667 and 6697 | Version not established in supplied output | Medium, provisional | Software inventory and vulnerability management | Potential service compromise if a vulnerable build/configuration is present. Identify exact build/configuration; patch or disable if unnecessary. |
| RA-09 | Directory indexing on `/icons/`, `/doc/`, `/test/` | Nikto; CWE-548 reference; CVE-1999-0678 cited by scanner and requires verification | Medium, provisional | Secure configuration and information protection | Unnecessary discovery of files, paths, or documentation. Disable indexing; review content and restrict sensitive paths. |
| RA-10 | Publicly accessible `phpinfo.php` | Nikto; CWE-552 reference from scanner | Medium, provisional | Secure configuration and information-disclosure controls | Disclosure of PHP/system configuration useful for reconnaissance. Remove the page or restrict access; retest. |
| RA-11 | phpMyAdmin changelog/documentation/readme resources accessible | Nikto observations | Medium, provisional | Access control and administrative-interface protection | Increased visibility of database administration resources and software details. Restrict phpMyAdmin access and remove unused files. |
| RA-12 | HTTP TRACE responds | Nikto observation; XST concern cited by scanner | Medium, provisional | Web hardening and access/data-protection practices | Additional HTTP attack surface; impact depends on application/client environment. Disable if unnecessary and validate allowed methods. |
| RA-13 | Missing recommended web security headers | Nikto observations for X-Content-Type-Options, Referrer-Policy, Permissions-Policy, HSTS, and CSP | Low–Medium, provisional | Secure configuration and defence in depth | Reduced browser-side protections depending on deployment. Define suitable headers and test; apply HSTS only with appropriate HTTPS deployment. |
| RA-14 | Apache MultiViews enabled; TCN header observed | Nikto observation; scanner cited an X-Force reference for MultiViews | Low–Medium, provisional | Secure configuration | May ease resource discovery or reveal negotiation behaviour. Validate relevance and disable unnecessary content negotiation. |
| RA-15 | ETag metadata and default Apache README exposed | Nikto observations; CVE-2003-1418 cited by scanner but not independently confirmed | Low–Medium, provisional | Information disclosure and secure configuration | Exposure of file metadata or default implementation details. Validate behaviour; remove default content and minimise unnecessary metadata. |
| RA-16 | Nuclei output files empty because template directory was unavailable | Nuclei terminal log and zero-byte output files | Not a vulnerability rating; assurance gap | Assessment completeness, evidence quality, vulnerability-management process | Assessment may lack additional findings until template-based scanning is completed. Configure templates, rerun the authorised scan, review results, and append verified findings. |

### 7.3 Likelihood, impact, and inherent risk scoring

Likelihood and impact are assessed separately before assigning an inherent risk rating. These are qualitative, evidence-based judgments rather than statistically calculated probabilities. The scores are provisional because exploitability, full configuration, and compensating controls were not independently validated.

- **Likelihood — High:** Strong evidence indicates the condition is exposed and likely to be exploitable under the relevant conditions. **Medium:** A service or issue was observed, but exploitability, exact build, authentication, or deployment conditions still require validation. **Low:** The evidence is indirect, weak, or not reproduced.
- **Impact — High:** Potential for major system compromise, privileged access, serious data exposure, or substantial service disruption. **Medium:** Meaningful information disclosure, administrative-interface exposure, or additional attack surface with harm dependent on context. **Low:** Limited information disclosure or a defence-in-depth weakness with no material impact established.
- **Inherent risk:** The estimated risk before crediting unverified mitigating controls. It is not residual risk.

The qualitative scoring logic used here is: High likelihood + High impact = High; Medium likelihood + High impact = High; Medium + Medium = Medium; Medium + Low = Low–Medium; and Low + Low = Low. A high-impact finding may remain High even where likelihood is only Medium, when the potential consequence is substantial and the issue requires timely validation.

| ID | Likelihood | Impact | Inherent risk |
|---|---|---|---|
| RA-01 | Medium | High | High, provisional |
| RA-02 | Medium | High | High, provisional |
| RA-03 | Medium | High | High, provisional |
| RA-04 | Medium | High | High, provisional |
| RA-05 | Medium | High | High, provisional |
| RA-06 | Medium | High | High, provisional |
| RA-07 | Medium | High | High, provisional |
| RA-08 | Medium | Medium | Medium, provisional |
| RA-09 | Medium | Medium | Medium, provisional |
| RA-10 | Medium | Medium | Medium, provisional |
| RA-11 | Medium | Medium | Medium, provisional |
| RA-12 | Medium | Medium | Medium, provisional |
| RA-13 | Medium | Low | Low–Medium, provisional |
| RA-14 | Medium | Low | Low–Medium, provisional |
| RA-15 | Medium | Low | Low–Medium, provisional |
| RA-16 | N/A | N/A | Not scored: assessment-completeness gap, not a vulnerability |

These scores correspond to the finding IDs in the consolidated risk register above. The ratings should be revisited after manual validation, review of the target's actual configuration, and verification of remediation.

### 7.4 Important triage notes

- **Weak/default credentials:** The lab brief gives weak default credentials as an example, but the evidence reviewed for this report does not show that credentials were tested or discovered. This is therefore not recorded as a confirmed finding.
- **CVE-2011-2523:** The CVE is associated with a particular backdoored vsftpd 2.3.4 distribution. The Nmap banner warrants validation but is not sufficient, on its own, to confirm that exact build.
- **CVE-1999-0678 and CVE-2003-1418:** These references appeared in Nikto's output. Their applicability to the exact target and observed behaviour has not been independently confirmed.
- **Compliance violations:** The control mapping is preliminary. A formal violation should be declared only after comparing verified evidence with the exact requirement and confirming scope and applicability.
  

---

## 8. GRC and Compliance Framework Mapping

The following mapping identifies control themes that could be relevant to the recorded observations. It is an initial cross-reference to guide remediation—not a compliance audit or certification assessment.

| Observation / risk theme | NIST CSF 2.0 outcome area | CIS Critical Security Controls v8.1 theme | Other relevant guidance / consideration |
|---|---|---|---|
| Unknown or insufficiently tracked target assets | Identify — Asset Management | Control 1: Inventory and Control of Enterprise Assets | Maintain an authorised asset inventory and define asset ownership |
| Old or unknown software versions | Identify — asset and risk assessment; Protect — Platform Security | Control 2: Inventory and Control of Software Assets; Control 7: Continuous Vulnerability Management | Verify packages, versions, support status, and applicable advisories |
| Unnecessary exposed ports and services | Protect — Platform Security; Govern/Identify risk decisions | Control 4: Secure Configuration of Enterprise Assets and Software; Control 12: Network Infrastructure Management | Define an approved secure baseline and restrict access by network and role |
| Legacy remote-access protocols and privileged listeners | Protect — Identity/Access and Platform Security outcomes | Control 5: Account Management; Control 6: Access Control Management; Control 4: Secure Configuration | Use secure administration methods, least privilege, and restricted management paths |
| Database service exposure | Protect — access-control and platform-security outcomes | Controls 4, 6, and 7 | Confirm system boundaries, network ACLs, authentication, and data sensitivity |
| Directory indexing, diagnostic pages, exposed phpMyAdmin resources, and headers | Protect — Platform Security | Controls 4 and 7 | OWASP Top 10:2025, particularly Security Misconfiguration; OWASP Web Security Testing Guide |
| Vulnerability assessment incomplete | Identify — risk assessment; Govern — roles and oversight | Control 7: Continuous Vulnerability Management; documentation and process ownership | Record tool limitations, complete testing, and preserve reproducible evidence |
| Potential cardholder-data scope | Applicable NIST and organisational risk outcomes | Relevant CIS safeguards as supporting practices | PCI DSS is applicable only when the system is within the cardholder data environment or can affect its security; review the current PCI DSS version and exact requirement |
| ISMS risk treatment and continual improvement | NIST CSF 2.0 cross-cutting risk management | CIS Controls governance and safeguard implementation | ISO/IEC 27001:2022 risk assessment and treatment, access control, and vulnerability-management processes, as applicable |

### 8.1 Compliance interpretation

The open ports and Nikto observations may indicate areas where security controls should be reviewed, but they do not automatically establish non-compliance. For example, the PCI DSS requirements apply to relevant in-scope payment-card environments; their inclusion here does not mean that this training target handles cardholder data. Similarly, a missing HTTP header should be evaluated against the application's architecture and approved secure configuration rather than treated as a universal compliance breach.

---

## 9. Remediation and Follow-Up Plan

The actions below are prioritised for the lab scenario. Timeframes are suggested planning targets, not confirmed service-level commitments. If applied in a real production setting, containment and changes must follow approved incident, change-management, and business-continuity procedures.

| Priority / suggested timing | Action | Suggested owner | Evidence required for closure |
|---|---|---|---|
| Immediate | Maintain isolation of the intentionally vulnerable Metasploitable target and investigate the service identified on port 1524 | Lab administrator / system owner | Service identity and exposure review; configuration before and after change; follow-up scan |
| Immediate | Verify exact vsftpd package/build and determine whether the CVE-2011-2523 affected distribution is present | System administrator | Package/version evidence, trusted advisory comparison, and remediation/retest result |
| High | Review all 31 open ports and document business purpose, exposure, and control owner for each service | System/network administrator | Approved service inventory and documented disposition for each service |
| High | Disable Telnet/rsh/rlogin and other unnecessary services; restrict required management access | System/network administrator | Service status, firewall/routing rules, and validation output |
| High | Verify versions and support status for Apache, PHP, databases, Samba, FTP, IRC, Tomcat/AJP, RMI, distccd, VNC, and other detected services | System/application owners | Version inventory, applicable vulnerability review, patch/upgrade records |
| High | Restrict MySQL/PostgreSQL and SMB/NFS to authorised hosts and appropriate accounts | Database and system administrators | Network access rules, account/permission review, and authorised connectivity tests |
| Medium | Remove or restrict `phpinfo.php`, phpMyAdmin resources, default documentation, and unnecessary directory content | Web/application administrator | Updated web root/configuration and authorised retest |
| Medium | Disable directory indexing and TRACE when not required; review MultiViews and other HTTP method handling | Web/application administrator | Configuration review and repeat Nikto/manual checks |
| Medium | Define and test a suitable header policy for CSP, X-Content-Type-Options, Referrer-Policy, Permissions-Policy, and HSTS where appropriate | Web/application administrator | Header validation and application functionality test |
| Follow-up | Restore the Nuclei template set and rerun the web-focused and broader scans against the authorised target | Assessment operator | Non-empty scan output, template availability evidence, and review of each result |
| Ongoing | Maintain a risk register, assign owners and target dates, record risk acceptance, and retain closure evidence | GRC/risk owner | Updated register, management decisions, and verification records |

---

## 10. Evidence Inventory and Submission Checklist

### 10.1 Evidence directory

The evidence folder reviewed for this report was:

```text
/home/kali/Lab1_Vulnerability_Assessment/evidence/
```

The following files appeared in the directory listing supplied for review. File sizes are recorded as shown in that listing and may change if scans are repeated.

| Evidence file | Recorded size | Purpose / status |
|---|---:|---|
| `initial_scan.nmap` | 5.6 KB | Human-readable Nmap output with the port/service inventory |
| `initial_scan.gnmap` | 1.9 KB | Grepable Nmap output |
| `initial_scan.xml` | 24 KB | Structured Nmap results and input for HTML conversion |
| `initial_scan_report.html` | 19 KB | HTML presentation of Nmap results; file was present |
| `nikto_scan.txt` | 4.4 KB | Nikto web-server assessment output |
| `nuclei_scan.txt` | 0 bytes | Empty at the time of review; not evidence of a clean scan |
| `nuclei_terminal.log` | 888 bytes | Terminal log recording the Nuclei issue |
| `nuclei_web_scan.txt` | 0 bytes | Empty at the time of review; not evidence of a clean scan |


---

## 11. Conclusion and Learning Outcomes

The assessment progressed from target discovery to service enumeration, web-server checking, risk triage, framework mapping, and remediation planning. Nmap identified 31 open TCP ports and multiple legacy or administrative services. Nikto reported web-server configuration and information-disclosure concerns. The assessment also identified a material evidence limitation: Nuclei could not be verified as having completed a valid scan because its template directory was unavailable and its output files were empty.

The main risk-management priority is to validate potentially high-impact exposures, particularly the service identified on port 1524 and the exact vsftpd 2.3.4 build, then reduce unnecessary service exposure and remediate confirmed software and web-configuration weaknesses. Remediation should be tracked to closure with named owners and verification evidence.

This lab reinforces that GRC work requires evidence-based interpretation rather than simply running security tools. A defensible report distinguishes confirmed results from hypotheses, assigns proportionate provisional risk ratings, connects observations to applicable control themes, and gives management clear actions. The report does not claim successful exploitation, confirmed weak credentials, zero vulnerabilities from Nuclei, or formal compliance breaches where the supplied evidence does not support those conclusions.

### Learning outcomes demonstrated

- Network discovery and service enumeration using Nmap.
- Interpretation and documentation of legacy services and application versions.
- Web-server assessment and output preservation using Nikto.
- Recognition of a failed/incomplete scanner setup and accurate disclosure of the limitation.
- Development of a risk register using inherent-risk criteria.
- Translation of technical findings into business impact and remediation actions.
- Preliminary mapping of findings to NIST, CIS, OWASP, and conditionally applicable PCI DSS control themes.
- Evidence management, validation planning, and professional reporting.

---

## 12. Ethical and Safety Statement

All activity documented in this report was intended for the authorised, isolated lab environment using a deliberately vulnerable Metasploitable target. The assessment should not be repeated against public, production, organisational, or third-party systems without explicit authorisation and an approved scope.

---

## 13. References

Center for Internet Security. (2024). *CIS Critical Security Controls v8.1*. https://www.cisecurity.org/controls/v8-1

International Organization for Standardization. (2022). *ISO/IEC 27001:2022—Information security, cybersecurity and privacy protection—Information security management systems—Requirements*. https://www.iso.org/standard/27001

MITRE. (n.d.). *CWE-548: Exposure of information through directory listing*. https://cwe.mitre.org/data/definitions/548.html

National Institute of Standards and Technology. (n.d.). *CVE-2011-2523 detail*. National Vulnerability Database. https://nvd.nist.gov/vuln/detail/CVE-2011-2523

National Institute of Standards and Technology. (2024). *The NIST Cybersecurity Framework (CSF) 2.0* (NIST Cybersecurity White Paper 29). https://doi.org/10.6028/NIST.CSWP.29

Nmap Project. (n.d.). *Nmap reference guide*. https://nmap.org/book/man.html

OWASP Foundation. (2025). *OWASP Top 10:2025*. https://top10.owasp.org/2025/

OWASP Foundation. (n.d.). *Web Security Testing Guide, version 4.2*. https://owasp.org/www-project-web-security-testing-guide/

PCI Security Standards Council. (n.d.). *PCI Data Security Standard (PCI DSS) and document library*. https://www.pcisecuritystandards.org/standards/pci-dss/

ProjectDiscovery. (n.d.). *Nuclei vulnerability scanner*. https://projectdiscovery.io/nuclei

ProjectDiscovery. (n.d.). *Nuclei templates* [GitHub repository]. https://github.com/projectdiscovery/nuclei-templates

Sullo. (n.d.). *Nikto documentation*. GitHub. https://github.com/sullo/nikto/wiki/

---
   
## AI Usage Declaration

Generative AI(ChatGPT) was used to assist with organising the s lab material into a structured report, refining grammar and professional wording, improving table presentation, AI was not treated as a source of lab evidence.




