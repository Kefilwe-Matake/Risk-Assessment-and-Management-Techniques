# GRC103 – Module 3: Ransomware Risk Treatment Case Lab

## Risk Treatment Decision and Executive Recommendation

![GRC](https://img.shields.io/badge/Domain-Governance%2C%20Risk%20%26%20Compliance-blue)
![Focus](https://img.shields.io/badge/Focus-Ransomware%20Risk%20Management-red)
![Framework](https://img.shields.io/badge/Approach-Risk%20Treatment-green)
![Academy](https://img.shields.io/badge/ICDFA-GRC103-orange)

---

## 1. Project Overview

This project was completed as part of **GRC103 – Risk Assessment and Management Techniques, Module 3: Risk Treatment Strategies**, under the International Cybersecurity and Digital Forensics Academy (ICDFA).

The case study focuses on ransomware risk treatment for **Northbridge Community Health**, a fictional healthcare organisation facing cybersecurity threats that could disrupt essential services, compromise sensitive information and affect operational continuity.

The objective was to evaluate identified risks, assess available treatment options and recommend a cost-effective ransomware risk treatment portfolio within a first-year budget of **$100,000**.

The exercise also introduces a scenario change that requires the initial treatment strategy to be reassessed and revised while maintaining the approved budget.

## 2. Learning Objectives

The practical exercise demonstrates the application of the following GRC and risk management principles:

- Identifying and prioritising ransomware-related risks.
- Evaluating risk treatment options against business objectives.
- Applying risk avoidance, mitigation, acceptance and financial risk transfer.
- Allocating a limited cybersecurity budget based on risk exposure.
- Assessing residual risk after implementing treatment measures.
- Evaluating the impact of changing operational conditions on risk decisions.
- Developing executive recommendations for management and board approval.
- Establishing risk ownership, accountability and treatment timelines.

## 3. Case Study Scenario

**Organisation:** Northbridge Community Health (Fictional)  
**Industry:** Healthcare  
**Risk Scenario:** Ransomware attack and operational disruption  
**First-Year Treatment Budget:** $100,000

The organisation faces four priority risk areas:

| Risk | Initial Score | Rating | Business Impact |
|---|---:|---|---|
| Service disruption | 20 | Critical | Disruption of essential bookings and business continuity |
| Sensitive-data loss | 15 | High | Exposure of sensitive patient and operational information |
| Supplier exposure | 12 | High | Unnecessary third-party attack surface |
| Delayed detection | 16 | High | Increased attacker dwell time and incident impact |

The assessment highlights the importance of protecting critical healthcare operations while strengthening identity management, recovery capabilities, third-party security and incident detection.

## 4. Initial Risk Treatment Decision

The initial recommendation was to implement **Options A, B, C and D**, with a combined investment of $95,000.

| Option | Treatment | Budget |
|---|---|---:|
| A | Retire the unused supplier workflow | $5,000 |
| B | Implement MFA and account access reviews | $25,000 |
| C | Implement protected backups, restoration testing and a recovery plan | $30,000 |
| D | Implement managed detection and incident escalation | $35,000 |
| | **Total** | **$95,000** |

**Remaining budget:** $5,000

### Treatment Strategy

The initial portfolio combined:

- **Risk avoidance:** Removing the unused supplier workflow to eliminate an unnecessary attack path.
- **Risk mitigation:** Strengthening identity controls, backup protection, recovery capabilities and security monitoring.
- **Operational accountability:** Establishing detection ownership and incident escalation procedures.

Options F (network segmentation) and G (cyber insurance) were initially deferred or rejected in favour of direct risk-reduction measures.

## 5. Scenario Change and Revised Decision

A significant scenario change required the initial decision to be reconsidered.

The following developments occurred:

- The restoration test failed.
- Paper-based bookings could sustain operations for only four hours.
- The cost of Option B (MFA and account access review) increased to $35,000.
- The organisation was required to maintain the original $100,000 budget.

The failed restoration test increased the urgency of addressing business continuity and recovery capabilities.

### Revised Risk Treatment Portfolio

The revised recommendation was to implement **Options A, C, D, E and G**, using the entire $100,000 budget.

| Option | Treatment | Budget |
|---|---|---:|
| A | Retire the unused supplier workflow | $5,000 |
| C | Protected backups and tested recovery | $30,000 |
| D | Managed detection and incident escalation | $35,000 |
| E | Security awareness and phishing-reporting process | $10,000 |
| G | Cyber insurance (partial financial risk transfer) | $20,000 |
| | **Total** | **$100,000** |

### Key Management Decision

MFA and account access review (Option B) was deferred following its increased cost.

This was treated as a **time-limited, board-escalated risk acceptance**, rather than permanent acceptance.

The CISO was assigned ownership of the residual identity and access risk until **12 December 2026**, with earlier review triggered by relevant security incidents, access-review exceptions or additional funding opportunities.

Network segmentation (Option F) remained a longer-term improvement.

## 6. Cyber Insurance Assessment

The exercise also considered cyber insurance as a financial risk transfer mechanism.

Two illustrative loss scenarios were evaluated:

| Covered Loss | Insurance Payment | Retained Loss | Total First-Year Outlay |
|---:|---:|---:|---:|
| $180,000 | $155,000 | $25,000 | $45,000 |
| $400,000 | $250,000 | $150,000 | $170,000 |

The calculations include the $20,000 insurance premium.

**Key observation:** Cyber insurance does not eliminate the underlying cybersecurity risk. Deductibles, coverage limits and exclusions may leave the organisation exposed to substantial financial losses.

Insurance should therefore complement, rather than replace, preventive, detective and recovery controls.

## 7. Residual Risk Assessment

Following the revised treatment decision, the following residual-risk considerations were identified:

| Risk | Residual Position | Required Action |
|---|---|---|
| Service disruption | Critical | Complete a successful controlled restoration test before considering the risk adequately treated. |
| Sensitive-data loss | High | Revisit MFA and account access reviews; maintain oversight of identity and access exposure. |
| Supplier exposure | Low, subject to verification | Confirm that the unused workflow, associated credentials and connectivity are disabled. |
| Delayed detection | Medium, subject to testing | Validate alert routing, assigned ownership and end-to-end escalation. |

A key governance principle demonstrated in this exercise is that implementing a control does not automatically mean the associated risk has been adequately reduced.

Control effectiveness must be supported by evidence.

## 8. 30-Day Risk Treatment Priorities

The revised recommendation includes the following immediate implementation priorities:

| Action | Responsible Owner | Budget |
|---|---|---:|
| Retire supplier workflow | Application Owner / Procurement | $5,000 |
| Repair recovery and conduct restoration testing | IT Recovery Lead / COO | $30,000 |
| Activate managed detection | CISO / Security Operations | $35,000 |
| Implement awareness and phishing reporting | CISO / HR | $10,000 |
| Validate cyber insurance arrangements | CFO / Risk | $20,000 |

### Effectiveness Measures

Implementation should be supported by verifiable evidence, including:

- Documented confirmation that the supplier workflow, credentials and connectivity have been disabled.
- Successful controlled restoration testing within the four-hour fallback window or an approved alternative.
- Evidence that security alerts generate cases and reach designated personnel.
- Completed awareness training and successful phishing-reporting tests.
- Validated insurance deductibles, coverage limits, exclusions and claims procedures.

## 9. Governance and Risk Management Considerations

This exercise demonstrates several important principles for effective cybersecurity governance:

1. **Risk treatment must align with business priorities.** Critical business services should influence the order in which cybersecurity investments are made.

2. **Risk decisions must adapt to changing conditions.** Failed recovery testing and increased control costs can materially change the appropriate treatment strategy.

3. **Risk acceptance requires accountability.** Deferred controls should have an assigned risk owner, review date and escalation conditions.

4. **Insurance is not a substitute for security controls.** Financial risk transfer does not remove operational, regulatory or reputational exposure.

5. **Evidence is essential.** Control effectiveness should be validated through testing, documentation and management oversight.

6. **Executive involvement matters.** Significant residual risks, particularly Critical and High risks, require appropriate management and board oversight.

## 10. Deliverables

This submission consists of two complementary deliverables:

| Deliverable | Description |
|---|---|
| Decision Report | Executive summary, treatment recommendations, scenario reassessment, residual-risk position and board memo. |
| Editable Risk Treatment Workbook | Detailed risk register, initial and revised budget decisions, insurance calculations, residual-risk scoring, 30-day action plan and source/assumption register. |

### Supporting Workbook

[Access the Editable Risk Treatment Workbook](https://docs.google.com/spreadsheets/d/15CkVSNh_C4VmsD5dtOUFDVaFaF44PSmL/edit?usp=sharing)

## 11. Reference and Evidence

The exercise uses the Health Service Executive (HSE) ransomware incident as a real-world contextual reference.

**Official source:**

Health Service Executive (HSE) – [Cyber-attack and HSE response](https://www2.hse.ie/services/cyber-attack/what-happened/)

The report distinguishes actual HSE incident facts from the fictional Northbridge Community Health scenario, including its budget, treatment costs and scenario changes.

## 12. Skills Demonstrated

- Governance, Risk and Compliance (GRC)
- Cybersecurity Risk Assessment
- Ransomware Risk Management
- Risk Treatment Strategy Development
- Risk Prioritisation and Residual Risk Assessment
- Cybersecurity Budget Planning
- Third-Party Risk Management
- Business Continuity and Disaster Recovery
- Incident Detection and Response Governance
- Cyber Insurance and Financial Risk Transfer
- Executive Reporting and Board-Level Recommendations
- Risk Ownership and Accountability

## 13. Conclusion

The case study demonstrates that effective ransomware risk management requires more than selecting cybersecurity tools or allocating a security budget.

Organisations must understand their critical business risks, evaluate treatment options, adapt decisions when circumstances change and ensure that residual risks are properly owned and monitored.

The revised Northbridge portfolio prioritises operational recovery, security detection, supplier-risk reduction and financial risk transfer while formally escalating the deferred identity and access risk.

**The ultimate objective is to ensure that cybersecurity investments deliver measurable risk reduction and support organisational resilience.**

---

## Submission Information

**Institution:** International Cybersecurity and Digital Forensics Academy (ICDFA)  
**Programme:** Global Governance, Risk and Compliance  
**Module:** GRC103 – Risk Assessment and Management Techniques  
**Assessment:** Module 3 – Ransomware Risk Treatment Case Lab  
**Student:** Kefilwe Matake  
**Registration Number:** C11_26_CGRCE_17575  
**Role:** GRC Analyst

---

*Disclaimer: Northbridge Community Health is a fictional organisation created for academic purposes. Scenario figures, treatment costs and risk assumptions are illustrative and should not be interpreted as actual organisational data.*
