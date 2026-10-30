
# Advanced Cybersecurity Risk Quantification
### GRC103 – Lab 3B | SecureBank Financial – SecureMobile Banking Platform

![GRC](https://img.shields.io/badge/Domain-GRC-blue)
![Risk Management](https://img.shields.io/badge/Focus-Cyber_Risk_Quantification-purple)
![Framework](https://img.shields.io/badge/Approach-Quantitative_Risk_Analysis-green)
![Status](https://img.shields.io/badge/Project-Completed-success)

## Project Overview

This project demonstrates how cybersecurity risks can be translated into measurable financial exposure to support informed business and security decisions.

The assessment was completed as part of the **International Cybersecurity and Digital Forensics Academy (ICDFA), GRC103 – Advanced Cybersecurity Risk Quantification, Lab 3B**.

Using a simulated financial institution, SecureBank Financial, the assessment evaluates three critical vulnerabilities affecting its SecureMobile banking platform. It quantifies the potential financial impact, evaluates proposed security controls, calculates return on investment (ROI), and develops a risk treatment plan.

The objective is to demonstrate how GRC professionals can communicate cybersecurity risks in financial terms that support executive decision-making.

## Scenario: SecureBank Financial

SecureBank Financial operates the SecureMobile banking application with the following business profile:

| Business Metric | Value |
|---|---:|
| Active customers | 500,000 |
| Average transaction value | $2,500 |
| Daily transactions | 50,000 |

Three critical vulnerabilities were identified for assessment:

1. API Authentication Bypass
2. Database Injection
3. Session Hijacking

## Key Financial Results

The assessment quantified the baseline exposure and evaluated the financial benefits of implementing three security controls.

| Executive Measure | Result |
|---|---:|
| Baseline Annualized Loss Expectancy (ALE) | $35,000,000 |
| Residual ALE after controls | $8,037,500 |
| Annualized risk reduction | $26,962,500 |
| Risk reduction | 77.0% |
| First-year control cost | $805,000 |
| Portfolio first-year ROI | 3,249.4% |

### Executive Risk Dashboard

| Measure | Value |
|---|---:|
| Baseline Risk | $35.00M |
| Residual Risk | $8.04M |
| Risk Reduction | 77.0% |
| First-Year Investment | $805K |

**Key finding:** Database injection represents the largest modeled financial exposure, with an ALE of $31.25 million. The Web Application Firewall (WAF) therefore provides the strongest modeled financial return.

## Risk Quantification

The following quantitative risk formulas were applied:

| Metric | Formula | Purpose |
|---|---|---|
| Single Loss Expectancy (SLE) | Impact × Cost | Estimates the financial loss from one successful incident |
| Annual Rate of Occurrence (ARO) | Exploit probability as a decimal | Represents the modeled annual occurrence rate |
| Annualized Loss Expectancy (ALE) | SLE × ARO | Estimates annual financial exposure |
| Residual Risk | Current ALE × (1 − Control Effectiveness) | Estimates risk remaining after a control |
| Risk Reduction | Current ALE − Residual ALE | Measures modeled annual risk benefit |
| ROI | (Risk Reduction − First-Year Cost) ÷ First-Year Cost × 100 | Measures first-year return |

## Vulnerability Assessment Results

| Vulnerability | SLE | ARO | ALE | Priority |
|---|---:|---:|---:|---|
| API Authentication Bypass | $5,000,000 | 15% | $750,000 | Medium |
| Database Injection | $125,000,000 | 25% | $31,250,000 | Critical |
| Session Hijacking | $7,500,000 | 40% | $3,000,000 | High |

Database injection accounts for approximately **89.3% of the total modeled ALE**, making it the dominant financial risk in this scenario.

## Security Control Evaluation

Three security controls were evaluated against the identified vulnerabilities.

| Proposed Control | Effectiveness | First-Year Cost | Risk Reduction | ROI |
|---|---:|---:|---:|---:|
| Advanced API Security Gateway | 90% | $400,000 | $675,000 | 68.8% |
| Web Application Firewall (WAF) | 75% | $175,000 | $23,437,500 | 13,292.9% |
| Multi-Factor Authentication (MFA) Enhancement | 95% | $230,000 | $2,850,000 | 1,139.1% |

### Control-to-Risk Mapping

- **API Security Gateway:** Addresses API authentication bypass and unauthorized transaction risk.
- **Web Application Firewall:** Addresses database injection exposure.
- **MFA Enhancement:** Reduces session hijacking and account-takeover exposure.

All three controls have a positive modeled financial case and address distinct security risks.

## Risk Treatment Roadmap

The recommended implementation approach follows four phases:

| Timeline | Key Activities |
|---|---|
| 0–30 Days | Deploy/pilot API Security Gateway, restrict vulnerable API paths, begin WAF and MFA design |
| 31–90 Days | Implement WAF and MFA enhancements, validate API gateway effectiveness, perform targeted retesting |
| 3–6 Months | Monitor control performance, tune detection, track exceptions and confirm maintenance ownership |
| 6–12 Months | Repeat penetration testing, refresh ALE assumptions and review risk acceptance |

## Repository Deliverables

The project includes:

| Deliverable | Description |
|---|---|
| `README.md` | Project overview, key findings and navigation |
| `GRC103_Lab3B_Risk_Quantification_Report.md` | Detailed executive and technical risk quantification report |
| `GRC103_Lab3B_Risk_Quantification_Report.pdf` | Original submitted assessment report |
| `Risk_Quantification_Workbook.xlsx` | Supporting calculation model and executive dashboard, where included |

### Workbook Structure

The accompanying calculation workbook contains the following sheets:

- **Inputs:** Scenario data, control costs, effectiveness and assumptions.
- **Risk Calculations:** SLE, ARO, ALE, risk share and priority.
- **Risk Heat Map:** Probability-impact visualization and risk bands.
- **Control Analysis:** Residual ALE, risk reduction, ROI and payback.
- **Risk Timeline:** Modeled risk reduction and treatment schedule.
- **Executive Dashboard:** Management KPIs and executive charts.

## Important Modeling Assumptions

- Exploit probabilities were treated as ARO because the scenario did not provide separate historical annual frequency data.
- Financial figures are modeled estimates for decision support, not guaranteed losses.
- Each proposed control was mapped to the vulnerability it most directly addresses.
- First-year cost includes initial investment and one year of maintenance.
- The implementation timeline is illustrative and based on the planning assumptions documented in the report.
- Indirect costs such as reputational damage, legal expenses, customer churn and business interruption were not separately quantified unless already embedded in the scenario values.

## Executive Recommendation

Approve the proposed first-year control package of **$805,000**, subject to implementation governance and validation.

Prioritise:

1. **WAF:** Address the largest modeled exposure, database injection.
2. **MFA:** Reduce account-takeover and session-hijacking exposure.
3. **API Security Gateway:** Address API authentication bypass and direct unauthorized transfer risk.

The organization should monitor residual risk, independently test implemented controls, and update ALE assumptions using actual incident and control-performance data.

## Key GRC Learning Outcomes

This practical demonstrates the ability to:

- Identify and quantify cybersecurity risk in financial terms.
- Calculate SLE, ARO and ALE.
- Prioritise vulnerabilities based on financial exposure.
- Evaluate security controls using cost-benefit analysis.
- Calculate residual risk, ROI and payback periods.
- Develop a risk-based treatment roadmap.
- Translate technical vulnerabilities into executive-level recommendations.
- Support risk acceptance and investment decisions with measurable evidence.

## References

1. ICDFA – GRC103, Lab 3B: Advanced Cybersecurity Risk Quantification.
2. Aminu Idris – *Study Guide: Quantitative Risk Calculations for GRC Professionals*.

## Author

**Kefilwe Matake**  
Lead GRC Analyst  
ICDFA – GRC103  
Registration: C11_26_CGRCE_17575

---

*This project forms part of a practical Governance, Risk and Compliance portfolio demonstrating the application of quantitative cybersecurity risk analysis to business decision-making.*

**Disclaimer:** SecureBank Financial and SecureMobile are simulated assessment scenarios. All financial figures are scenario-based estimates.
