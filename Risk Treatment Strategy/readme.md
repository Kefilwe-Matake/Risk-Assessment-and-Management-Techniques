# GRC103 Module 3 | Technical Risk Treatment Lab

## Implementing and Validating Controls on a Local Linux Server

![Risk Treatment](https://img.shields.io/badge/GRC103-Module%203-blue)
![Linux](https://img.shields.io/badge/Platform-Ubuntu%20%26%20Kali-green)
![Status](https://img.shields.io/badge/Assessment-Completed-success)
![Risk Management](https://img.shields.io/badge/Domain-Cybersecurity-orange)

## Overview

This project demonstrates the practical implementation and validation of cybersecurity risk treatment strategies within a controlled Linux environment.

The assessment was conducted for the fictional organization **Northbridge Services** as part of the **ICDFA GRC103 - Risk Assessment and Management Techniques** module. The objective was to identify security risks, implement appropriate controls, validate treatment effectiveness, and evaluate residual risk using industry-aligned Governance, Risk, and Compliance (GRC) principles. ICDFA_GRC103_Module3_Technical_Risk_Treatment_Report_Kefilwe_Matake_C11ion

| Item | Details |
|--------|--------|
| Student | Kefilwe Matake |
| Registration Number | C11_26_CGRCE_17575 |
| Course | GRC103 |
| Module | Module 3 – Risk Treatment Strategies |
| Role | GRC Analyst and Technical Control Implementer |
| Organization | Northbridge Services (Fictional) |
| Assessment Type | Technical Risk Treatment Lab |

---

# Project Objectives

The primary objectives of this lab were to:

- Build a secure Linux lab environment.
- Establish baseline security conditions.
- Identify and assess technical risks.
- Apply the four risk treatment strategies:
  - Risk Avoidance
  - Risk Mitigation
  - Risk Transfer
  - Risk Acceptance
- Validate implemented controls.
- Correlate security logs.
- Perform backup and recovery testing.
- Reassess residual risks after treatment.

---

# Lab Architecture

```text
+-------------------+
|   Kali Linux VM   |
| Authorized Client |
| 192.168.56.10     |
+---------+---------+
          |
          |
          |
+---------v---------+
| Ubuntu Server VM  |
| 192.168.56.20     |
| NGINX             |
| UFW Firewall      |
| Backup Storage    |
+-------------------+

Simulated Unauthorized Client:
192.168.56.11
```

---

# Technology Stack

| Component | Purpose |
|------------|------------|
| Ubuntu Server 24.04 LTS | Target Server |
| Kali Linux | Security Testing |
| NGINX | Web Service |
| UFW | Host Firewall |
| Python HTTP Server | Legacy Service Simulation |
| SHA-256 | Integrity Verification |
| Nmap | Port Scanning |
| Curl | Web Testing |

---

# Baseline Risk Assessment

Four primary risks were identified during the baseline assessment. ICDFA_GRC103_Module3_Technical_Risk_Treatment_Report_Kefilwe_Matake_C11_26_CGRCE_17575.docx.pdf 【1-3800c5】

| Risk ID | Risk Description | Initial Score | Rating |
|-----------|-----------------|--------------|---------|
| R1 | Legacy Service Exposure | 16 | High |
| R2 | Public Archive Exposure | 12 | High |
| R3 | Unauthorized Network Access | 16 | High |
| R4 | Loss of Portal Content | 12 | High |

### Risk Scoring Formula

```text
Risk Score = Likelihood × Impact
```

Scale:

| Score | Rating |
|---------|---------|
| 1-4 | Low |
| 5-9 | Medium |
| 10-16 | High |
| 17-25 | Critical |

---

# Baseline Findings

Initial testing confirmed:

✅ Port 80 reachable

✅ Port 8080 reachable

✅ Internal portal accessible

✅ Archive directory accessible

✅ Dummy records downloadable

These findings indicated unnecessary exposure and confirmed the need for treatment activities. ICDFA_GRC103_Module3_Technical_Risk_Treatment_Report_Kefilwe_Matake_C11_26_CGRCE_17575.docx.pdf 【1-3800c5】

---

# Risk Treatment Strategy 1 — Avoidance

## Legacy Service Retirement

A Python HTTP service running on TCP Port 8080 was determined to be unnecessary for business operations.

### Action Taken

```bash
sudo systemctl disable --now grc-legacy
```

### Result

| Test | Outcome |
|---------|---------|
| Port 8080 Before | Open |
| Port 8080 After | Closed |
| Approved Portal | Available |

### Security Benefit

Eliminated an unnecessary attack surface while preserving required services.

---

# Risk Treatment Strategy 2 — Mitigation

## Archive Hardening

The archive directory was removed from the web root and access controls were strengthened.

### Implemented Controls

- Archive moved outside web root.
- Directory listing disabled.
- Explicit deny rules configured.

### Validation Results

| Resource | Result |
|------------|-----------|
| /public/ | HTTP 200 |
| /archive/ | HTTP 403 |
| dummy-records.txt | HTTP 403 |

### Key Lesson

Simply disabling directory listing does not prevent direct file requests when filenames are known.

Moving sensitive content outside the web root provides stronger protection.

---

## Firewall Restriction

UFW was configured to only allow access from the approved Kali Linux host.

### Firewall Rules

```bash
sudo ufw default deny incoming
sudo ufw allow from 192.168.56.10 to any port 80
```

### Validation

| Source IP | Result |
|------------|----------|
| 192.168.56.10 | Allowed |
| 192.168.56.11 | Blocked |

### Security Benefit

Reduced unauthorized network access by implementing source-based filtering.

---

# Detective Control Validation

Security logging was reviewed to validate both allowed and denied events.

### Log Correlation

| Event Type | Expected Log |
|-------------|--------------|
| Allowed Request | NGINX Access Log |
| HTTP 403 Request | NGINX Access Log |
| Blocked Connection | UFW Log |
| Authorized Portal Session | NGINX Log |

### Observation

Firewall-blocked traffic does not reach the NGINX application layer and therefore should not appear in NGINX logs.

---

# Corrective Control Validation

## Backup and Recovery Testing

A protected backup was created for the approved portal
