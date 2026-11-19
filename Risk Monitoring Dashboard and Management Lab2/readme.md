# GRC103 – Risk Monitoring and Reporting
## Module 4 | Lab 2: Risk Monitoring Dashboard and Management Report

![GRC](https://img.shields.io/badge/Domain-Governance%2C%20Risk%20%26%20Compliance-17365D)
![Focus](https://img.shields.io/badge/Focus-Risk%20Monitoring-blue)
![Status](https://img.shields.io/badge/Assessment-Completed-success)

## 📌 Project Overview

This practical assessment demonstrates the application of Governance, Risk and Compliance (GRC) principles in monitoring organisational risks, evaluating control performance, reporting risk exposure, and tracking remediation activities.

The exercise uses **Northbridge Services (Fictional)** as the case study organisation. The objective was to develop a risk monitoring dashboard and management report that translates operational control performance into actionable management decisions.

The assessment focuses on identifying control weaknesses, evaluating residual risk exposure, assigning accountability, and establishing measurable remediation targets.

## 🎯 Objectives

- Monitor the effectiveness of existing security and operational controls.
- Evaluate key risk indicators and identify areas requiring management attention.
- Maintain a structured risk register supported by measurable evidence.
- Apply a likelihood and impact scoring methodology.
- Develop an action and assurance plan with accountable owners and deadlines.
- Define measurable closure criteria to validate remediation effectiveness.
- Communicate risk exposure through management reporting.

## 🏢 Case Study: Northbridge Services

The assessment evaluates four key risk areas using March monitoring results.

### 1. Management Monitoring Dashboard

The dashboard highlights five critical performance indicators.

| Key Risk Indicator | March Result | Status |
|---|---:|---|
| Monitoring Coverage | 90.0% | 🔴 Red |
| Timely Critical-Alert Review | 70.0% | 🔴 Red |
| Restore-Test Success | 80.0% | 🔴 Red |
| Overdue High-Risk Actions | 40.0% | 🔴 Red |
| Confirmed Unauthorised Changes | 5 | 🔴 Red |

### 2. Key Monitoring Findings

**Endpoint Monitoring**
- 108 out of 120 eligible endpoints were monitored.
- Monitoring coverage stood at 90%.
- 12 endpoints remained outside active monitoring.

**Critical Alert Management**
- 28 out of 40 critical alerts were reviewed within 24 hours.
- 12 alerts were reviewed late.
- Timely review performance was 70%.

**Backup and Recovery Assurance**
- 8 out of 10 restore tests were successful.
- 2 restoration tests failed.
- Remediation and verified retesting were required.

**Risk Remediation**
- 6 out of 15 high-risk actions were overdue.
- The overdue action rate was 40%.
- Management escalation and recovery dates were required.

**Unauthorised Changes**
- Five confirmed unauthorised changes were recorded.
- These incidents required investigation and management attention.

## 📊 3. Risk Register

Four priority risks were documented and assessed using a 5 × 5 likelihood and impact methodology.

Risk Score = Likelihood × Impact

| Risk ID | Risk Area | Likelihood | Impact | Score | Rating |
|---|---|---:|---:|---:|---|
| M4-R01 | Endpoint Monitoring | 4 | 4 | 16 | High |
| M4-R02 | Critical Alert Handling | 4 | 4 | 16 | High |
| M4-R03 | Backup / Restoration | 3 | 5 | 15 | High |
| M4-R04 | Risk Remediation | 4 | 4 | 16 | High |

### Risk Treatment Priorities

| Risk ID | Recommended Treatment |
|---|---|
| M4-R01 | Onboard 12 uncovered endpoints and automate monitoring reconciliation. |
| M4-R02 | Clear the alert backlog, assign escalation owners and improve SLA workflows. |
| M4-R03 | Investigate failed restore tests, remediate issues and perform verified retesting. |
| M4-R04 | Escalate overdue actions, resolve blockers and establish approved recovery dates. |

**Escalation requirement:** All four risks were rated High and require management escalation. Each Red indicator must be escalated to the responsible manager within one working day.

## 🛠️ 4. Action and Assurance Plan

A structured remediation plan was developed to ensure that identified risks are addressed through accountable actions and measurable outcomes.

| Risk ID | Target Date | Closure Criteria |
|---|---|---|
| M4-R01 | 26 November 2026 | Monitoring coverage reaches at least 98%, with no unexplained gap. |
| M4-R02 | 25 November 2026 | At least 95% of critical alerts reviewed within 24 hours. |
| M4-R03 | 30 November 2026 | 100% successful verified restoration for previously failed systems. |
| M4-R04 | 03 December 2026 | Overdue high-risk action rate reduced to 10% or less. |

Each remediation activity includes:
- Identified risk.
- Corrective action.
- Responsible owner.
- Target completion date.
- Containment or improvement measures.
- Closure evidence and outcome testing.
- Implementation status.

All actions were recorded as **Proposed** in the assessment. Completion must only be confirmed when supporting evidence demonstrates that the required outcome has been achieved.

## 📋 5. Management Decisions and Recommendations

The following decisions were identified as necessary to improve the organisation's risk posture:

1. Approve immediate management escalation for all five Red indicators and the four High risks.
2. Allocate resources to close the 12-endpoint monitoring gap.
3. Restore compliance with the 24-hour critical-alert review SLA.
4. Prioritise remediation and retesting of the two failed recovery tests.
5. Require owners of overdue high-risk actions to provide documented blockers, recovery dates and closure evidence.
6. Maintain regular monitoring of remediation progress.

**Next formal management review:** 3 December 2026.

## 📚 6. GRC Concepts Demonstrated

This assessment demonstrates practical application of the following GRC concepts:

- Risk Monitoring and Reporting
- Key Risk Indicators (KRIs)
- Key Control Performance Indicators
- Risk Register Development and Maintenance
- Likelihood and Impact Assessment
- Risk Scoring and Prioritisation
- Control Effectiveness Monitoring
- Risk Treatment and Remediation
- Management Escalation
- Action Tracking and Accountability
- Evidence-Based Assurance
- Management Reporting and Decision Support

## 📂 7. Repository Structure

```text
GRC103-Module4-Lab2/
│
├── README.md
│
└── GRC103_Module4_Lab2_Kefilwe_Matake.pdf
```

## 💡 8. Key Learning Outcomes

Through this exercise, I strengthened my understanding of how GRC professionals use monitoring data to support organisational decision-making.

Key takeaways include:

- Risk monitoring must be supported by measurable evidence.
- Increased monitoring activity does not necessarily mean improved monitoring coverage.
- Control failures must be translated into actionable remediation plans.
- Risk ownership and accountability are essential for effective treatment.
- Management reporting should communicate exposure, impact and required decisions.
- Remediation should not be considered complete without documented closure evidence and successful outcome testing.

An important observation from this assessment was that monitored endpoints increased from 95 to 108, but eligible endpoints also increased from 100 to 120. Consequently, monitoring coverage deteriorated despite the increase in monitored endpoints.

This reinforces the importance of analysing performance indicators in context rather than relying on isolated figures.

## 👩‍💻 Author

**Kefilwe Matake**

GRC Practitioner | IT & Cybersecurity Professional

- Programme: GRC103 – Risk Assessment and Management Techniques
- Institution: International Cybersecurity and Digital Forensics Academy (ICDFA)
- Cohort: 11
- Registration Number: C11_26_CGRCE_17575
- Role in Assessment: GRC Analyst

## ⚠️ Disclaimer

This assessment was developed for educational and practical learning purposes. Northbridge Services is a fictional organisation, and the monitoring results, risk scenarios and management recommendations are simulated.

---

**Building practical GRC capabilities through risk identification, monitoring, reporting and assurance.**
