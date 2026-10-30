
# GRC103 – Lab 3B
# Advanced Cybersecurity Risk Quantification

### SecureBank Financial – SecureMobile Banking Platform

**From Cybersecurity Risk to Financial Impact and Business Decisions**

---

## 1. Assessment Information

| Field | Details |
|---|---|
| Institution | International Cybersecurity and Digital Forensics Academy (ICDFA) |
| Programme | GRC103 – Advanced Cybersecurity Risk Quantification |
| Laboratory | Lab 3B |
| Assessment | Advanced Cybersecurity Risk Quantification |
| Organisation | SecureBank Financial (Simulated Scenario) |
| Application | SecureMobile Banking Platform |
| Student | Kefilwe Matake |
| Registration Number | C11_26_CGRCE_17575 |
| Role | Lead GRC Analyst |
| Report Date | 01 October 2026 |
| Intended Audience | Chief Information Security Officer (CISO) and Chief Financial Officer (CFO) |

---

# 2. Executive Summary

## 2.1 Objective

The objective of this assessment was to quantify the financial exposure associated with three critical cybersecurity vulnerabilities affecting SecureBank Financial's SecureMobile banking platform.

The assessment evaluates the potential financial impact of each vulnerability, examines proposed security controls, calculates residual risk and return on investment (ROI), and recommends a financially justified risk treatment strategy.

The analysis demonstrates how cybersecurity risks can be translated into financial terms to support executive decision-making, security investment prioritisation and risk management.

## 2.2 Executive Financial Overview

The assessment produced the following results:

| Executive Measure | Result |
|---|---:|
| Baseline Annualized Loss Expectancy (ALE) | $35,000,000 |
| Residual ALE After Controls | $8,037,500 |
| Modeled Annual Risk Reduction | $26,962,500 |
| Total Risk Reduction | 77.0% |
| First-Year Control Cost | $805,000 |
| Portfolio First-Year ROI | 3,249.4% |
| Largest Modeled Exposure | Database Injection – $31.25M ALE |

## 2.3 Management Recommendation

Approve the proposed three-control package, with the Web Application Firewall (WAF) prioritised because it addresses the largest modeled financial exposure and produces the strongest estimated financial return.

The recommended treatment approach is:

1. **Web Application Firewall (WAF):** Prioritise mitigation of the database injection vulnerability.
2. **Multi-Factor Authentication (MFA):** Implement the enhancement within the 90-day treatment window to reduce session-hijacking and account-takeover exposure.
3. **Advanced API Security Gateway:** Deploy within the first 30 days to address API authentication bypass and unauthorised transaction risk.

All controls should undergo targeted testing after implementation. The risk register should then be updated using measured residual risk rather than relying solely on estimated control effectiveness.

## 2.4 Important Modeling Note

The laboratory scenario provides exploit probabilities rather than historical event frequencies.

For this assessment, each exploit probability is treated as the Annual Rate of Occurrence (ARO) for one modeled annual exposure cycle.

All financial values are scenario-based estimates intended to support decision-making. They are not guaranteed realised losses.

---

# 3. Scenario Overview and Business Context

SecureBank Financial operates the SecureMobile banking application.

The scenario provides the following business information:

| Business Metric | Value |
|---|---:|
| Active Customers | 500,000 |
| Average Transaction Value | $2,500 |
| Daily Transactions | 50,000 |

The assessment identifies three critical vulnerabilities affecting transaction processing, customer data and active user sessions.

### Identified Vulnerabilities

| Vulnerability | Description of Risk | Primary Business Concern |
|---|---|---|
| API Authentication Bypass | Weakness in API authentication controls | Unauthorised fund transfers |
| Database Injection | Injection vulnerability affecting database security | Exposure of customer records and potential data breach |
| Session Hijacking | Compromise of active user sessions | Account takeover and unauthorised access |

The purpose of the quantitative assessment is to determine which risks create the greatest modeled financial exposure and which security investments provide the strongest risk-reduction benefits.

---

# 4. Quantitative Risk Assessment Methodology

The assessment applies quantitative risk analysis to estimate the financial impact of cybersecurity incidents.

The following metrics were used.

## 4.1 Single Loss Expectancy (SLE)

SLE estimates the financial loss associated with one successful security incident.

**Formula:**

`SLE = Impact Quantity × Unit Cost`

Depending on the scenario, SLE may also represent the maximum estimated loss from a single incident.

## 4.2 Annual Rate of Occurrence (ARO)

ARO represents the expected annual occurrence rate of a particular risk.

For this exercise, the exploit probability provided in the scenario was converted into a decimal and used as the ARO.

Example:

`25% = 0.25`

## 4.3 Annualized Loss Expectancy (ALE)

ALE estimates the expected annual financial exposure associated with a risk.

**Formula:**

`ALE = SLE × ARO`

## 4.4 Residual Risk

Residual risk represents the expected exposure remaining after implementing a security control.

**Formula:**

`Residual Risk = Current ALE × (1 − Control Effectiveness)`

## 4.5 Risk Reduction

Risk reduction measures the modeled financial benefit achieved through implementing a security control.

**Formula:**

`Risk Reduction = Current ALE − Residual ALE`

## 4.6 Return on Investment (ROI)

ROI measures the financial return of a proposed security investment relative to its first-year cost.

**Formula:**

`ROI = ((Risk Reduction − First-Year Cost) ÷ First-Year Cost) × 100`

## 4.7 Payback Period

The payback period estimates how long it takes for the annual risk-reduction benefit, after annual maintenance costs, to recover the initial investment.

**Formula:**

`Payback Period = Initial Investment ÷ (Annual Risk Reduction − Annual Maintenance)`

---

# 5. Phase 1 – Risk Exposure Calculation

The first phase establishes the baseline financial exposure associated with each identified vulnerability.

## 5.1 Annualized Loss Expectancy Results

| Vulnerability | Single Loss Expectancy (SLE) | ARO | Annualized Loss Expectancy (ALE) | Priority |
|---|---:|---:|---:|---|
| API Authentication Bypass | $5,000,000 | 15% | $750,000 | Medium |
| Database Injection | $125,000,000 | 25% | $31,250,000 | Critical |
| Session Hijacking | $7,500,000 | 40% | $3,000,000 | High |
| **Total** | | | **$35,000,000** | |

## 5.2 Calculation Breakdown

### A. API Authentication Bypass

The scenario estimates a maximum single-incident loss of $5 million.

- SLE = $5,000,000
- ARO = 15% = 0.15

Calculation:

`ALE = $5,000,000 × 0.15`

**ALE = $750,000**

The modeled annual financial exposure is $750,000.

### B. Database Injection

The potential impact is calculated using the number of customer records at risk and the estimated cost per record.

- Records at risk = 500,000
- Cost per record = $250
- ARO = 25% = 0.25

Calculation:

`SLE = 500,000 × $250`

`SLE = $125,000,000`

Then:

`ALE = $125,000,000 × 0.25`

**ALE = $31,250,000**

This represents the largest modeled financial exposure in the assessment.

### C. Session Hijacking

The scenario estimates that 5,000 sessions could be affected, with an average loss of $1,500 per session.

- Sessions at risk = 5,000
- Average loss per session = $1,500
- ARO = 40% = 0.40

Calculation:

`SLE = 5,000 × $1,500`

`SLE = $7,500,000`

Then:

`ALE = $7,500,000 × 0.40`

**ALE = $3,000,000**

## 5.3 Risk Prioritisation

The database injection vulnerability represents approximately 89.3% of the total modeled annualised risk exposure.

This makes it the dominant financial risk in the SecureMobile scenario.

| Risk | Priority | Financial Exposure | Recommended Treatment |
|---|---|---:|---|
| Database Injection | Critical | $31.25M ALE | Treat first due to significant data-breach exposure |
| Session Hijacking | High | $3.00M ALE | Treat within the same 90-day window |
| API Authentication Bypass | Medium | $750K ALE | Immediate treatment due to direct unauthorised transfer risk |

### Risk Assessment Conclusion

The results demonstrate that technical severity alone should not determine risk prioritisation.

Financial exposure, business impact and the nature of the potential loss should also inform treatment decisions.

---

# 6. Phase 2 – Security Control Evaluation

Following the baseline risk assessment, three security controls were evaluated.

Each control was mapped to the vulnerability it most directly addresses.

## 6.1 Proposed Security Controls

| Vulnerability | Proposed Control | Modeled Effectiveness |
|---|---|---:|
| API Authentication Bypass | Advanced API Security Gateway | 90% |
| Database Injection | Web Application Firewall (WAF) | 75% |
| Session Hijacking | MFA Enhancement | 95% |

## 6.2 Cost-Benefit Analysis

| Security Control | Effectiveness | First-Year Cost | Annual Risk Reduction | Residual ALE | ROI | Payback |
|---|---:|---:|---:|---:|---:|---:|
| Advanced API Security Gateway | 90% | $400,000 | $675,000 | $75,000 | 68.8% | 204.4 days |
| Web Application Firewall (WAF) | 75% | $175,000 | $23,437,500 | $7,812,500 | 13,292.9% | 2.3 days |
| MFA Enhancement | 95% | $230,000 | $2,850,000 | $150,000 | 1,139.1% | 25.9 days |

## 6.3 Control Analysis

### A. Advanced API Security Gateway

**Risk addressed:** API Authentication Bypass

The proposed API Security Gateway is intended to reduce the risk of unauthorised API access and transactions.

| Measure | Result |
|---|---:|
| Baseline ALE | $750,000 |
| Control Effectiveness | 90% |
| First-Year Cost | $400,000 |
| Annual Risk Reduction | $675,000 |
| Residual ALE | $75,000 |
| ROI | 68.8% |
| Payback Period | 204.4 days |

**Financial interpretation:**

The gateway is modeled to reduce annual financial exposure from $750,000 to $75,000.

Although it produces the lowest ROI among the three controls, its estimated annual risk-reduction benefit exceeds its first-year cost.

The control remains justified because API authentication bypass can directly enable unauthorised fund transfers.

### B. Web Application Firewall (WAF)

**Risk addressed:** Database Injection

The WAF is proposed to reduce exposure associated with database injection attacks.

| Measure | Result |
|---|---:|
| Baseline ALE | $31,250,000 |
| Control Effectiveness | 75% |
| First-Year Cost | $175,000 |
| Annual Risk Reduction | $23,437,500 |
| Residual ALE | $7,812,500 |
| ROI | 13,292.9% |
| Payback Period | 2.3 days |

**Financial interpretation:**

The WAF provides the strongest modeled financial return.

A 75% reduction in the database injection exposure removes approximately $23.44 million in annualised risk for a first-year cost of $175,000.

This makes the WAF the highest-priority security investment from a financial risk-reduction perspective.

### C. Multi-Factor Authentication (MFA) Enhancement

**Risk addressed:** Session Hijacking

MFA enhancement is proposed to strengthen user authentication and reduce account-takeover exposure.

| Measure | Result |
|---|---:|
| Baseline ALE | $3,000,000 |
| Control Effectiveness | 95% |
| First-Year Cost | $230,000 |
| Annual Risk Reduction | $2,850,000 |
| Residual ALE | $150,000 |
| ROI | 1,139.1% |
| Payback Period | 25.9 days |

**Financial interpretation:**

MFA provides a strong modeled financial return by reducing the session-hijacking exposure by 95%.

The estimated residual ALE is $150,000.

The enhancement should be implemented within the proposed 90-day treatment window.

---

# 7. Portfolio-Level Financial Justification

The portfolio analysis combines the financial results of all three proposed controls.

## 7.1 Combined Financial Results

| Portfolio Measure | Value |
|---|---:|
| Baseline ALE | $35,000,000 |
| Residual ALE After Controls | $8,037,500 |
| Annual Risk Reduction | $26,962,500 |
| Initial Investment | $700,000 |
| Annual Maintenance | $105,000 |
| First-Year Total Cost | $805,000 |
| First-Year Portfolio ROI | 3,249.4% |

## 7.2 Portfolio ROI Calculation

Using the portfolio's modeled annual risk reduction and total first-year cost:

`ROI = ((Risk Reduction − First-Year Cost) ÷ First-Year Cost) × 100`

`ROI = (($26,962,500 − $805,000) ÷ $805,000) × 100`

**Portfolio ROI = 3,249.4%**

## 7.3 Overall Risk Reduction

`Risk Reduction = Baseline ALE − Residual ALE`

`Risk Reduction = $35,000,000 − $8,037,500`

**Annual Risk Reduction = $26,962,500**

Percentage reduction:

`($26,962,500 ÷ $35,000,000) × 100`

**Total Modeled Risk Reduction = 77.0%**

### Portfolio Interpretation

The proposed controls reduce the modeled annual financial exposure from $35 million to approximately $8.04 million.

The combined first-year investment of $805,000 is substantially lower than the estimated annual risk reduction of approximately $26.96 million.

However, the remaining $8.04 million in residual exposure must not be overlooked. It requires continued monitoring, further treatment where appropriate, or formal risk acceptance by accountable risk owners.

---

# 8. Executive Risk Dashboard

The following indicators summarise the assessment for executive review.

| Executive KPI | Value |
|---|---:|
| Baseline Annual Risk Exposure | $35.00M |
| Residual Annual Risk Exposure | $8.04M |
| Modeled Annual Risk Reduction | $26.96M |
| Risk Reduction Percentage | 77.0% |
| First-Year Investment | $805K |
| Portfolio ROI | 3,249.4% |

### Key Executive Observations

1. Database injection is the dominant financial exposure and should receive the highest treatment priority.
2. The three proposed controls reduce modeled total ALE by 77%.
3. The combined first-year investment is $805,000 against $26.96 million in modeled annual risk reduction.
4. The WAF has the strongest modeled financial return, followed by MFA.
5. The API Security Gateway remains financially justified and addresses direct transaction risk.
6. Residual risk remains material and must be monitored and managed after implementation.

---

# 9. Risk Treatment Roadmap

The implementation strategy is divided into four phases.

| Period | Horizon | Planned Activities | Accountable Functions |
|---|---|---|---|
| 0–30 Days | Immediate | Deploy/pilot API Security Gateway, restrict vulnerable API paths where feasible, begin WAF and MFA design, define control owners and evidence requirements | Application Security / IAM / Security Engineering |
| 31–90 Days | Short Term | Implement WAF and MFA enhancements, validate API gateway effectiveness, perform targeted retesting and update the risk register | Security Engineering / IAM / GRC |
| 3–6 Months | Assurance | Tune detection, monitor control performance, track false positives and exceptions, confirm maintenance ownership and operational KPIs | Security Operations / GRC |
| 6–12 Months | Long Term | Repeat penetration testing, refresh ALE assumptions using actual incident/control data, review risk acceptance and renew the treatment plan | CISO / GRC / Internal Audit |

## 9.1 Immediate Priorities: 0–30 Days

- Deploy or pilot the Advanced API Security Gateway.
- Restrict vulnerable API paths where feasible.
- Begin WAF implementation planning.
- Begin MFA enhancement design.
- Confirm control owners and evidence requirements.

## 9.2 Short-Term Priorities: 31–90 Days

- Implement the WAF.
- Implement MFA enhancement.
- Validate API Security Gateway effectiveness.
- Perform targeted security retesting.
- Update the risk register using measured residual risk.

## 9.3 Assurance: 3–6 Months

- Monitor control performance.
- Tune detection mechanisms.
- Track false positives and exceptions.
- Confirm maintenance ownership.
- Establish and monitor operational KPIs.

## 9.4 Long-Term Assurance: 6–12 Months

- Repeat penetration testing.
- Refresh ALE assumptions using actual incident and control data.
- Review formal risk acceptance.
- Reassess the treatment strategy.

---

# 10. Final Recommendations to the CISO and CFO

Based on the quantitative assessment, the following recommendations are presented for executive consideration.

### Recommendation 1: Approve the Security Control Investment

Approve the full $805,000 first-year control package because the modeled annual risk reduction substantially exceeds the implementation and maintenance cost.

### Recommendation 2: Prioritise the WAF

Prioritise WAF implementation to address the database injection vulnerability, which represents the largest modeled financial exposure.

### Recommendation 3: Implement MFA Enhancement

Implement MFA enhancement within 90 days to reduce the session-hijacking and account-takeover exposure.

### Recommendation 4: Deploy the API Security Gateway

Implement the API Security Gateway within the first 30 days and retest the authentication-bypass scenario before closing the risk.

### Recommendation 5: Continuously Validate Control Effectiveness

Control effectiveness percentages should not be treated as permanent facts.

Actual operating effectiveness must be measured through testing and monitoring.

ALE assumptions should be updated quarterly using available incident and control-performance data.

### Recommendation 6: Monitor Residual Risk

Residual risk must be tracked separately from control implementation status.

A control can be successfully installed while material residual risk remains.

Risk owners should determine whether further treatment is required or whether the remaining exposure should be formally accepted.

---

# 11. Assumptions and Limitations

The assessment is based on the scenario information and modeling assumptions provided in the laboratory exercise.

The following limitations should be considered when interpreting the results:

1. **ARO assumption:** Exploit probability is treated as ARO because the laboratory does not provide separate annual frequency data.

2. **SLE calculation:** API authentication bypass uses the maximum single-incident loss; database injection uses records at risk multiplied by cost per record; session hijacking uses accounts/sessions at risk multiplied by average loss per account/session.

3. **Control mapping:** Each proposed control is mapped to the vulnerability it most directly addresses:
   - API Gateway → API Authentication Bypass
   - WAF → Database Injection
   - MFA → Session Hijacking

4. **First-year cost:** First-year cost includes initial investment plus one year of maintenance.

5. **Payback calculation:** Initial investment is divided by annual risk reduction less annual maintenance.

6. **Treatment timeline:** The implementation timeline is illustrative. The laboratory does not specify exact deployment dates. The assessment assumes API Gateway deployment by Day 30 and WAF/MFA implementation by Day 90 for planning purposes.

7. **Indirect financial losses:** Reputational damage, legal costs, fraud investigation, customer churn and business interruption are not separately included unless already embedded in the laboratory-provided impact values.

Actual financial exposure may therefore be higher than the modeled estimates.

---

# 12. Submission Evidence and Supporting Workbook

The accompanying Excel workbook supports the calculations and executive reporting presented in this document.

The workbook contains formula-driven calculations to allow the analysis to be reviewed and recalculated.

## Workbook Structure

| Worksheet | Purpose |
|---|---|
| Inputs | Scenario data, control costs, effectiveness and modeling assumptions |
| Risk Calculations | SLE, ARO, ALE, risk share and risk priority |
| Risk Heat Map | Probability-impact visualization and risk bands |
| Control Analysis | Residual ALE, risk reduction, ROI and payback |
| Risk Timeline | Modeled risk reduction over time and Gantt-style treatment schedule |
| Executive Dashboard | Management KPIs and executive charts |

The workbook provides supporting calculation evidence for the executive conclusions and recommendations.

---

# 13. Key GRC Competencies Demonstrated

This practical demonstrates the application of quantitative risk analysis within Governance, Risk and Compliance.

### Risk Identification and Assessment
- Identification of cybersecurity vulnerabilities.
- Assessment of potential financial consequences.
- Quantification of risk using SLE, ARO and ALE.
- Risk prioritisation based on financial exposure.

### Financial Risk Analysis
- Residual risk calculations.
- Cost-benefit analysis.
- ROI calculations.
- Payback period analysis.
- Portfolio-level risk reduction assessment.

### Security Governance
- Security control evaluation.
- Risk treatment prioritisation.
- Control ownership and accountability.
- Executive risk reporting.
- Residual risk monitoring and acceptance.

### Risk-Based Decision-Making
- Translating technical vulnerabilities into financial impact.
- Supporting security investment decisions.
- Developing phased treatment roadmaps.
- Communicating risk to CISO and CFO stakeholders.

---

# 14. Conclusion

This assessment demonstrates the value of quantitative cybersecurity risk analysis in supporting business-focused security decisions.

By translating the three identified SecureMobile vulnerabilities into financial exposure, the assessment established a baseline annualised risk exposure of $35 million.

The evaluation of the proposed API Security Gateway, WAF and MFA enhancement demonstrated a modeled reduction of annualised risk exposure by 77%, leaving approximately $8.04 million in residual risk.

The analysis also showed that the WAF provides the strongest modeled financial return due to the significant exposure associated with database injection.

However, the assessment reinforces that financial justification is only one part of effective risk management. Controls must be implemented, tested and monitored to establish actual operating effectiveness.

Management should therefore approve the recommended control package, maintain clear ownership of residual risks, and regularly reassess the financial assumptions as actual operational and security data becomes available.

> **The objective of cybersecurity risk quantification is not simply to calculate the cost of a threat. It is to give decision-makers the financial evidence they need to prioritise investments, reduce exposure and protect business value.**

---

# 15. References

1. International Cybersecurity and Digital Forensics Academy (ICDFA). (2026). *GRC103, Lab 3B: Advanced Cybersecurity Risk Quantification.*
2. Aminu Idris. *Study Guide: Quantitative Risk Calculations for GRC Professionals.*

Formula references applied:

- ALE = SLE × ARO
- ROI = (Benefit − Cost) ÷ Cost × 100
- Residual Risk = Current Risk × (1 − Control Effectiveness)

---

# 16. AI Assistance Declaration

AI assistance was used to support calculation checking, report structuring, spreadsheet construction and language refinement.

Assumptions introduced for analysis are explicitly identified in this report.

The student remains responsible for understanding and validating the submitted calculations and recommendations.

---

**Prepared by:** Kefilwe Matake  
**Role:** Lead GRC Analyst  
**Programme:** ICDFA GRC103 – Advanced Cybersecurity Risk Quantification  
**Registration Number:** C11_26_CGRCE_17575

*End of Report*
