# Practical Risk Monitoring with Wazuh
## Implementing and Verifying File Integrity Monitoring (FIM) as a Detective Control

![Wazuh](https://img.shields.io/badge/SIEM-Wazuh-blue)
![Domain](https://img.shields.io/badge/Domain-GRC%20%7C%20Cybersecurity-17365D)
![Control](https://img.shields.io/badge/Control-File%20Integrity%20Monitoring-success)
![Assessment](https://img.shields.io/badge/Status-Completed-brightgreen)

## 1. Project Overview

This project demonstrates the practical implementation and verification of **File Integrity Monitoring (FIM)** using Wazuh as part of the GRC103 Risk Assessment and Management Techniques programme at the International Cybersecurity and Digital Forensics Academy (ICDFA).

The exercise focused on implementing a detective security control to identify unauthorised creation, modification and deletion of sensitive financial documents.

Using an Ubuntu virtual machine as the Wazuh Manager and a Windows workstation as the monitored endpoint, I configured endpoint monitoring, registered the Wazuh agent, established agent-manager communication and tested file integrity monitoring through a simulated risk scenario.

The project demonstrates how technical security controls can generate centralised evidence to support risk monitoring, compliance activities and audit assurance.

## 2. Project Objectives

The primary objectives were to:

- Deploy and configure the Wazuh Manager and Dashboard.
- Install and register a Windows endpoint agent.
- Establish communication between the Wazuh Manager and endpoint.
- Configure File Integrity Monitoring for a designated sensitive folder.
- Simulate unauthorised file activity through creation, modification and deletion.
- Verify that Wazuh detects and generates alerts for file activity.
- Evaluate the effectiveness of FIM as a detective control.
- Identify the governance, risk and compliance implications of monitoring sensitive information.

## 3. Lab Environment and Architecture

The practical exercise used a two-system environment.

| Component | Configuration |
|---|---|
| SIEM Platform | Wazuh |
| Wazuh Version | 4.12.0 |
| Manager Operating System | Ubuntu Server |
| Monitored Endpoint | Windows 11 |
| Endpoint Hostname | DESKTOP-OIO4LNO |
| Agent ID | 004 |
| Endpoint IP | 192.168.1.241 |
| Monitoring Technology | File Integrity Monitoring (FIM) |
| Monitored Directory | SensitiveFiles |

### Architecture Overview

```text
              WAZUH MONITORING ENVIRONMENT

        +------------------------------+
        |       Ubuntu Server          |
        |                              |
        |       Wazuh Manager          |
        |       Wazuh Dashboard        |
        +---------------+--------------+
                        |
                        | Agent Communication
                        |
        +---------------v--------------+
        |       Windows 11             |
        |       Endpoint               |
        |                              |
        |       Wazuh Agent 004        |
        |                              |
        |       SensitiveFiles         |
        +------------------------------+
                        |
                        v
              File Activity Detection
                        |
                        v
              Centralised FIM Alerts
                        |
                        v
              Security and GRC Review
```

## 4. Implementation Process

### 4.1 Wazuh Manager Deployment

The Wazuh Manager and Dashboard were deployed on the Ubuntu Server virtual machine.

The dashboard provided a central location for monitoring registered agents, reviewing security events and examining endpoint activity.

### 4.2 Windows Agent Installation and Registration

The Wazuh agent was installed and registered on the Windows workstation.

- Endpoint: DESKTOP-OIO4LNO
- Agent ID: 004
- Wazuh Version: 4.12.0

An initial agent-manager communication issue was encountered during implementation. This was resolved, and the final dashboard confirmed that the Windows agent was Active.

This demonstrated successful communication between the monitored endpoint and the central Wazuh Manager.

### 4.3 File Integrity Monitoring Configuration

The required `SensitiveFiles` directory was configured for File Integrity Monitoring.

The purpose was to detect changes affecting sensitive financial documents and provide a centralised record of file activity.

The monitoring exercise covered:

- File creation.
- File modification.
- File deletion.

### 4.4 Risk Simulation and Control Testing

A simulated financial document risk scenario was performed.

The following activities were conducted:

1. Created the monitored `SensitiveFiles` folder.
2. Created a test document inside the monitored directory.
3. Modified the contents of the document.
4. Deleted the test document.
5. Reviewed the resulting FIM/security alerts in the Wazuh Dashboard.

**Observed result:** Wazuh generated centralised alerts corresponding to the simulated file modification and deletion activities.

This provided practical evidence that the configured detective control was functioning within the lab environment.

## 5. Technical Evidence and Results

The final dashboard confirmed:

| Verification Item | Observed Result |
|---|---|
| Wazuh Manager | Deployed |
| Windows Agent | Successfully registered |
| Agent ID | 004 |
| Agent Status | Active |
| Agent Communication | Successfully established |
| FIM Configuration | Configured |
| File Creation | Tested |
| File Modification | Tested |
| File Deletion | Tested |
| Security Alerts | Generated and visible |

The screenshots included in the assessment document provide evidence of:

- Wazuh agent running on the Windows endpoint.
- Agent registration and Active status in the Wazuh Dashboard.
- Endpoint security monitoring information.
- Centralised monitoring interface.

## 6. Risk Identification and Analysis

### Identified Risk Scenario

Unauthorised modification or deletion of sensitive financial forecast documents could compromise the integrity and reliability of organisational financial information.

### Potential Business Impacts

| Risk Category | Potential Impact |
|---|---|
| Financial | Incorrect budgets, cash-flow decisions and funding allocations. |
| Operational | Poor business decisions based on inaccurate financial information. |
| Reputational | Reduced confidence among management, auditors and business partners. |
| Compliance and Audit | Audit exceptions and concerns regarding information integrity. |
| Fraud and Decision-Making | Concealment of losses, manipulation of performance and unauthorised approvals. |

### How FIM Supports Risk Monitoring

Wazuh FIM generates time-stamped records of file activity, including additions, modifications and deletions.

These records can help GRC and security teams:

- Identify changes to sensitive files.
- Investigate unexpected file activity.
- Identify repeated or suspicious changes.
- Track activity by endpoint, file or event type.
- Analyse trends over time.
- Maintain evidence for security investigations and audits.

The lab demonstrated observable alerts but did not establish a complete numerical event-frequency rate because a full event-count export was not retained.

## 7. Control Evaluation and Treatment

### Detective Control: File Integrity Monitoring

Wazuh FIM was implemented as a detective control to identify changes to files within the designated monitoring directory.

Its effectiveness was demonstrated through the successful generation of alerts following the simulated file activity.

### Complementary Preventive Controls

FIM should be supported by additional preventive controls, including:

- Least-privilege access.
- Role-Based Access Control (RBAC).
- NTFS folder permissions.
- Restricted write, modify and delete permissions.
- Strong authentication.
- Controlled administrative access.

These measures help reduce the likelihood of unauthorised changes occurring.

### Corrective Controls

Unexpected or unauthorised FIM alerts should initiate an investigation and appropriate corrective action.

Recommended response activities include:

1. Validate the user and business justification for the change.
2. Preserve relevant evidence.
3. Restrict the affected account or endpoint if malicious activity is suspected.
4. Restore the trusted file version where necessary.
5. Investigate the root cause.
6. Initiate the incident response process where required.

## 8. Risk Monitoring and Management Reporting

Three key management metrics were identified to measure the operational effectiveness of the FIM control.

| Metric | Purpose |
|---|---|
| Monitoring Coverage and Agent Health | Measures the percentage of in-scope endpoints with an Active Wazuh agent and the required FIM configuration. |
| FIM Event Volume and Change Type | Tracks additions, modifications and deletions affecting sensitive locations. |
| Alert Review Effectiveness | Measures the percentage of high-priority FIM alerts reviewed within the agreed SLA. |

### Governance Value of Centralised Monitoring

Centralised monitoring provides a consistent, time-stamped evidence source instead of relying on manual reviews of individual workstation logs.

It enables security and GRC teams to:

- Apply consistent monitoring rules.
- Compare security trends.
- Assign accountability.
- Track exceptions.
- Retain audit evidence.
- Identify inactive agents and monitoring gaps.
- Support management reporting and compliance assurance.

## 9. Compliance Mapping and Audit Evidence

Wazuh FIM can support compliance and audit activities by recording relevant information such as:

- Monitored endpoint.
- File path.
- Event type and action.
- Timestamp.
- File-integrity information, including checksums where available.

These records can demonstrate that a detective control was operating and that detected file changes were available for review.

For stronger audit assurance, technical evidence should be linked to:

- Defined control ownership.
- Alert-review procedures.
- Evidence-retention requirements.
- Escalation procedures.
- Remediation records.
- Periodic control testing.

### Demonstrating File Integrity Over a Defined Period

To demonstrate that a sensitive file was not altered during a specified period:

1. Confirm that the Wazuh agent remained Active throughout the period.
2. Verify that FIM continuously covered the relevant file path.
3. Query Wazuh for the specific file path and relevant FIM events.
4. Review the required date range.
5. Retain the monitoring configuration, query results and baseline/current integrity evidence.

An absence of file-change alerts is meaningful only when continuous monitoring coverage and agent health can also be demonstrated.

## 10. GRC Control-Assurance Conclusion

This practical exercise demonstrated the difference between simply deploying a security control and verifying that it operates effectively.

The final Wazuh dashboard confirmed that agent 004 was Active, while the file-integrity simulation generated centralised alerts when the monitored document was modified and deleted.

This provided practical evidence that the FIM detective control operated end-to-end within the authorised training environment.

From a GRC perspective, the exercise demonstrated how technical monitoring supports risk identification, control verification, evidence collection and audit readiness.

It also reinforced that technical evidence must be supported by clear ownership, defined review SLAs, evidence retention, escalation and corrective action to achieve sustained control assurance.

## 11. Skills and Competencies Demonstrated

- Security Information and Event Management (SIEM).
- Wazuh deployment and configuration.
- Endpoint monitoring and agent management.
- File Integrity Monitoring (FIM).
- Security event monitoring and alert analysis.
- Risk identification and assessment.
- Detective and preventive controls.
- Control effectiveness testing.
- GRC risk monitoring and reporting.
- Compliance evidence and audit assurance.
- Security governance and incident response.

## 12. Repository Structure

```text
GRC103-Wazuh-Risk-Monitoring/
│
├── README.md
│
└── GRC103_Wazuh_Risk_Monitoring_Kefilwe_Matake_C11_26_CGRCE_17575.pdf
```

## 13. References

- International Cybersecurity and Digital Forensics Academy (ICDFA) – GRC103: Risk Assessment and Management Techniques.
- Wazuh Official Documentation: https://documentation.wazuh.com/
- Wazuh File Integrity Monitoring: https://documentation.wazuh.com/current/user-manual/capabilities/file-integrity/

## 14. Author

**Kefilwe Matake**

GRC Practitioner | IT & Cybersecurity Professional

- Institution: International Cybersecurity and Digital Forensics Academy
- Programme: GRC103 – Risk Assessment and Management Techniques
- Cohort: 11
- Registration Number: C11_26_CGRCE_17575
- Assessment: Practical Risk Monitoring with Wazuh
- Role: GRC Analyst and Technical Control Implementer

---

*Building practical GRC capabilities through cybersecurity monitoring, risk assessment, technical control implementation and evidence-based assurance.*
