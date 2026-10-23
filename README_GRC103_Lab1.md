# GRC103 Lab 1: Practical Vulnerability Assessment

**Technical Evidence · Risk Assessment · Compliance Mapping · Management Reporting**

## Assessment Details

| Field | Details |
|---|---|
| Student | Kefilwe Matake |
| Registration Number | `C11_26_CGRCE_17575` |
| Course | GRC103 |
| Role | Internal GRC Auditor / Assessor |
| Target System | Metasploitable2 |
| Target IP | `192.168.56.103` |
| Assessment Dates | 22–23 October 2026 |
| Environment | Authorised internal training / test lab |
| Overall Risk Rating | **HIGH** |

## 1. Executive Summary

A vulnerability assessment was performed against the authorised Metasploitable2 test server at `192.168.56.103`. The assessment combined host discovery, full TCP port and service enumeration, Nmap scripting, manual web review, and focused Nuclei scanning.

The assessment identified a **high-risk security posture**. Nmap reported **30 open TCP ports** and multiple legacy or insecure services, including anonymous/plaintext FTP, Telnet, obsolete SSLv2 support, SMB1 with message signing disabled, an exposed root bind shell, legacy database services, and an outdated web/application stack.

Nuclei results also included critical and high-severity detections affecting services such as vsFTPd, PostgreSQL, Apache AJP, PHP, Samba, VNC, and FTP. Scanner records are not equivalent to unique business risks; repeated credential combinations and informational detections should not be counted as separate vulnerabilities without review.

**Overall conclusion:** The server should remain isolated from business and public networks until critical and high-risk findings are remediated and verified.

## 2. Objectives and Scope

The objectives were to:

- Confirm target reachability and identify exposed services.
- Identify vulnerabilities and insecure configurations from available scan evidence.
- Assess inherent risk and explain potential business impact.
- Map findings to the compliance references specified in the lab.
- Prioritise remediation actions for management.
- Document evidence and recommend post-remediation verification.

### Methodology and Tools

- Ping for reachability testing.
- Nmap for TCP port discovery, service/version detection, scripts, and OS fingerprinting.
- Nuclei for focused vulnerability and configuration checks.
- Browser/manual review of exposed web applications.
- Nmap HTML/XML/text outputs and Nuclei text outputs for evidence review.

**Compliance context:** CIS Controls, NIST Cybersecurity Framework references, OWASP Top 10, and PCI DSS Requirement 6, as referenced in the lab instructions. These are control-alignment references, not a formal certification or compliance opinion.

## 3. Key Technical Findings

### 3.1 Network Discovery and Enumeration

The target responded to four ICMP echo requests with **0% packet loss**, confirming that `192.168.56.103` was reachable from the assessment environment.

Nmap scanned all 65,535 TCP ports and identified 30 open ports. The reported operating-system fingerprint was Linux 2.6.9–2.6.33.

| Port | Service | Evidence / Concern |
|---|---|---|
| 21/tcp | FTP | vsFTPd 2.3.4; anonymous access and plaintext communication reported |
| 22/tcp | SSH | OpenSSH 4.7p1; legacy version and weak-algorithm/password-authentication concerns |
| 23/tcp | Telnet | Plaintext remote administration |
| 25/tcp | SMTP | SSLv2 support and expired certificate reported |
| 53/tcp | DNS | ISC BIND 9.4.2; legacy software/version disclosure |
| 80/tcp | HTTP | Apache 2.2.8, WebDAV, and exposed web applications |
| 139/445 | SMB | Samba 3.0.20, SMB1, message signing disabled |
| 1524/tcp | Bind shell | Metasploitable root shell exposed |
| 2049/tcp | NFS | Network file service exposed |
| 3306/tcp | MySQL | MySQL 5.0.51a; legacy database service |
| 3632/tcp | distccd | Legacy remote compilation service |
| 5432/tcp | PostgreSQL | Legacy database service and expired SSL certificate reported |
| 5900/tcp | VNC | Remote desktop service; weak/default credentials detected by Nuclei |
| 8009/tcp | AJP | Apache JServ/AJP service exposed |
| 8180/tcp | HTTP/Tomcat | Apache Tomcat 5.5; legacy application server |

### 3.2 Web Application Exposure

Manual review of the HTTP service identified a Metasploitable2 landing page with links to TWiki, phpMyAdmin, Mutillidae, DVWA, and WebDAV. Nuclei separately detected a phpMyAdmin panel, `phpinfo.php`, Apache 2.2.8, PHP 5.2.4, and missing HTTP security headers.

Exposed administrative tools, diagnostic pages, outdated components, and intentionally vulnerable applications increase the attack surface and provide information that may assist an attacker.

### 3.3 Nuclei Scan Summary

The supplied scan outputs contained the following raw detection records:

| Scan output | Critical | High | Medium | Low | Informational | Total |
|---|---:|---:|---:|---:|---:|---:|
| `nuclei_full_scan.txt` | 5 | 18 | 3 | 6 | 39 | 71 |
| `nuclei_web_scan.txt` | 5 | 18 | 3 | 6 | 41 | 73 |

These totals represent **raw detections**, not confirmed unique vulnerabilities. Findings should be validated and deduplicated before reporting unique vulnerability counts.

Notable detections included:

| Detection / Finding | Severity in supplied report | Service | Risk implication |
|---|---|---|---|
| CVE-2011-2523 / vsFTPd backdoor detection | Critical | FTP 21 | Potential remote compromise |
| Empty PostgreSQL password | Critical | PostgreSQL 5432 | Potential unauthorised database access |
| CVE-2020-1938 detection | Critical | AJP 8009 | Potential application-server exposure |
| CVE-2012-1823 detection | High | PHP/HTTP | Potential PHP CGI argument-injection risk |
| Default PostgreSQL login | High | PostgreSQL 5432 | Unauthorised database access |
| Default/weak VNC login | High | VNC 5900 | Unauthorised remote desktop access |
| Weak FTP credentials | High | FTP 21 | Unauthorised access |
| CVE-2004-2687 detection | High | distccd 3632 | Legacy service vulnerability exposure |
| Weak SSH algorithms supported | Medium | SSH 22 | Reduced cryptographic security |
| Anonymous FTP login | Medium | FTP 21 | Unrestricted or unauthorised file access risk |

Scanner detections should be independently validated before being treated as confirmed exploitable vulnerabilities.

## 4. Risk Assessment and Compliance Mapping

The following register consolidates the major findings into business-focused risks. Compliance references follow those provided in the lab and should be treated as indicative control-alignment references.

| Finding | Inherent Risk | Compliance Reference | Potential Business Impact | Recommended Action |
|---|---|---|---|---|
| Exposed root bind shell on TCP/1524 | High | CIS Control 9; NIST PR.IP-1 | Direct privileged access and possible full server compromise | Isolate immediately, remove the bind shell, and check for equivalent backdoors |
| vsFTPd backdoor detection and obsolete FTP | High | CIS Control 7.1 | Potential remote compromise and persistence | Disable or replace FTP; patch/upgrade and rescan |
| Empty/default database credentials | High | CIS Control 5.2; NIST PR.AC-1 | Unauthorised database access and data theft | Remove default/empty passwords, set strong unique credentials, and restrict source networks |
| Plaintext FTP and Telnet | High | NIST PR.DS-2 | Credential or session interception | Disable Telnet; replace FTP with a protected transfer method; enforce encryption |
| Legacy SMB1 and signing disabled | High | CIS Control 9; NIST PR.IP-1 | Exploitation, man-in-the-middle exposure, and lateral movement | Disable SMB1, upgrade Samba, require signing where supported, and restrict SMB access |
| AJP vulnerability detection | High | CIS Control 7.1; PCI DSS Requirement 6 | Potential application compromise or sensitive-file exposure | Patch the application server; disable AJP if unnecessary or restrict it to trusted interfaces |
| PHP CGI detection and obsolete web stack | High | CIS Control 7.1; PCI DSS Requirement 6 | Potential web compromise or code execution | Upgrade supported web/PHP components and validate application security |
| Weak/default VNC credentials | High | CIS Control 5.2; NIST PR.AC-1 | Unauthorised remote desktop access | Disable VNC if unnecessary; enforce strong authentication and network restrictions |
| SSLv2 and expired certificates | Medium | NIST PR.DS-2 | Weak encryption and interception risk | Disable obsolete protocols and replace expired certificates with valid certificates using current TLS |
| Information disclosure and exposed administration/diagnostic tools | Medium | OWASP Top 10; PCI DSS Requirement 6 | Reconnaissance and increased web attack surface | Remove diagnostic pages, restrict administrative tools, and reduce unnecessary version disclosure |

## 5. Remediation Priorities

### Immediate — Containment

- Keep the server restricted to the authorised lab network.
- Block access from business and public networks.
- Remove or disable the exposed root bind shell.
- Confirm that no equivalent unauthorised privileged access mechanism remains.

### Within 24–72 Hours — Critical and High-Risk Findings

- Validate and remediate critical/high Nuclei detections.
- Remove empty and default credentials; rotate affected credentials.
- Disable unnecessary Telnet, anonymous FTP, SMB1, AJP, r-services, and other legacy services.
- Restrict database and remote administration services to authorised network paths.

### Within 7 Days — Hardening and Modernisation

- Replace unsupported operating system, web, database, and application components with supported versions where feasible.
- Enforce secure encrypted protocols and replace obsolete certificates.
- Review exposed services against documented business requirements.
- Apply secure configuration baselines and document any accepted exceptions with risk owners and approval.

### After Remediation — Verification

- Repeat Nmap and Nuclei scans against the same authorised target.
- Compare before-and-after results.
- Validate that critical/high findings are closed or formally risk-accepted.
- Update the risk register and retain evidence of remediation and verification.

## 6. Management Summary

The assessment identified multiple weaknesses that could enable unauthorised access, credential interception, access to exposed services, or potential server compromise. The most significant issues include the exposed root bind shell, vulnerable or obsolete FTP, weak/default database and remote-access credentials, legacy SMB configuration, vulnerable web/application components, and a broad set of exposed services.

Management should maintain isolation, assign remediation owners and deadlines, prioritise critical/high risks, and require evidence-based verification before considering broader use of the system.

### Recommended Management Decisions

1. Approve continued isolation of the server.
2. Assign accountable owners for each high-risk finding.
3. Prioritise removal of direct privileged exposure and remediation of critical/high findings.
4. Require a documented remediation plan and tracked target dates.
5. Require a follow-up scan and evidence review before closure.

## 7. Limitations and Evidence Integrity

- This assessment was conducted in an authorised training/test environment against Metasploitable2.
- Nuclei output totals are raw detection records and may include repeated or informational detections.
- The supplied lab material states that a Nuclei command against `150.168.56.103` returned no results; that output was not used as vulnerability evidence. The supplied scan text files for `192.168.56.103` were treated as the relevant evidence.
- Nikto scan output was **not supplied** and is not represented as completed.
- Vulnerability scanner detections should be validated; the findings in this report are based on the available lab evidence and are not a guarantee of exploitability.
- Compliance references are limited to the lab's stated context and do not constitute a formal certification opinion.

## 8. Evidence Index

Place the evidence files in an `evidence/` folder in this repository, if permitted by your course and lab rules.

| Evidence file | Date in report | Purpose |
|---|---|---|
| `initial_scan.nmap` | 22 Oct 2026 | Human-readable Nmap output, open ports, service versions, scripts, and OS fingerprint |
| `initial_scan.xml` | 22 Oct 2026 | Structured Nmap output |
| `initial_scan.gnmap` | 22 Oct 2026 | Grepable Nmap output |
| `initial_scan_report.html` | 22 Oct 2026 | Formatted Nmap report |
| `nuclei_web_scan.txt` | 23 Oct 2026 | Web-focused Nuclei detections |
| `nuclei_full_scan.txt` | 23 Oct 2026 | Full Nuclei scan detections |
| `installation-report.txt` | 10 May 2025 | Installation/banner artifact; not used to substantiate vulnerabilities |

**Evidence handling:** Remove secrets, credentials, tokens, and unrelated personal data before publishing. Keep vulnerable-lab evidence clearly labelled and do not expose the target to public networks.

## 9. Conclusion

This lab demonstrates how technical findings can be translated into risk decisions, compliance considerations, and management actions. Nmap established the server's broad attack surface and insecure service configuration, while Nuclei provided additional detections relating to known vulnerabilities, weak/default credentials, and obsolete technologies.

Effective GRC practice does not end with scanning. It requires accountable risk ownership, prioritised remediation, documented exceptions where necessary, and independent verification that corrective actions have reduced risk.

---

**Prepared by:** Kefilwe Matake  
**Course:** GRC103 — Practical Vulnerability Assessment  
**Registration Number:** `C11_26_CGRCE_17575`  
**Assessment Date:** 23 October 2026
