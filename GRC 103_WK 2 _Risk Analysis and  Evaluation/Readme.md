# SecureBank Financial — Quantitative Cybersecurity Risk Assessment

## Project Overview

This project presents a quantitative cybersecurity risk assessment of SecureBank Financial’s SecureMobile Banking Platform. It evaluates three identified security vulnerabilities, estimates their financial exposure, and assesses proposed security controls to support risk-based decision-making.

The assessment translates technical findings into financial estimates using Single Loss Expectancy (SLE), Annualised Loss Expectancy (ALE), control effectiveness, residual risk, Return on Investment (ROI), and payback period.

## Business Context

SecureMobile supports **500,000 active customers** and processes approximately **50,000 transactions daily**, with an average transaction value of **$2,500**.

| Platform Metric | Value |
|---|---:|
| Active customers | 500,000 |
| Daily transactions | 50,000 |
| Average transaction value | $2,500 |
| Indicative daily transaction throughput | $125,000,000 |

*Daily transaction throughput represents the value processed, not the amount necessarily lost in a security incident.*

## Assessment Scope

The assessment covers:

- API security: authentication bypass and unauthorised transactions
- Database security: injection and potential customer-data exposure
- Session security: session hijacking and account takeover
- Financial risk exposure and prioritisation
- Proposed control effectiveness and residual risk
- Three-year investment analysis and executive reporting

## Key Risk Findings

| Vulnerability | Single Loss Expectancy (SLE) | ARO Proxy | Annualised Loss Expectancy (ALE) | Priority |
|---|---:|---:|---:|---|
| API authentication bypass | $5,000,000 | 0.15 | $750,000 | High |
| Database injection | $125,000,000 | 0.25 | $31,250,000 | Critical |
| Session hijacking | $7,500,000 | 0.40 | $3,000,000 | High |
| **Total** | — | — | **$35,000,000** | — |

The supplied probabilities are treated as annual occurrence-rate proxies for this exercise. They are assumptions, not verified incident frequencies.

## Proposed Security Controls

| Control | Initial Investment | Annual Maintenance | Assumed Effectiveness |
|---|---:|---:|---:|
| Advanced API Security Gateway | $350,000 | $50,000 | 90% |
| Web Application Firewall (WAF) | $150,000 | $25,000 | 75% |
| MFA enhancement | $200,000 | $30,000 | 95% |
| **Total** | **$700,000** | **$105,000** | — |

## Modelled Financial Outcomes

| Metric | Result |
|---|---:|
| Current annual loss exposure | $35,000,000 |
| Residual annual loss exposure | $8,037,500 |
| Annual modelled risk reduction | $26,962,500 |
| Modelled reduction in annual exposure | 77.04% |
| Initial control investment | $700,000 |
| Three-year lifecycle cost | $1,015,000 |
| Three-year gross modelled benefit | $80,887,500 |
| Three-year net modelled benefit | $79,872,500 |
| Three-year portfolio ROI | 7,869.2% |

These are expected-loss model outputs, not guaranteed cash savings. Results depend on the supplied loss assumptions and the effectiveness of controls against the assigned scenarios.

## Recommended Risk Treatment

1. **Database injection:** Prioritise direct remediation using parameterised queries, secure input handling, and least-privilege database access. Deploy and test the WAF as a supplementary control.
2. **API authentication bypass:** Strengthen authentication and server-side authorisation, supported by the API Security Gateway.
3. **Session hijacking:** Enhance MFA and session management, including secure token handling, session revocation, and monitoring.
4. **Assurance:** Retest vulnerabilities, validate control effectiveness, and update residual-risk estimates.
5. **Governance:** Assign risk owners, track remediation, and report risk metrics to management.

## Repository Contents

```text
.
├── README.md
└── quantitative-cybersecurity-risk-assessment.md
```

## Methodology

The report applies the following formulas:

- **SLE:** estimated financial loss from one successful incident
- **ALE:** `SLE × ARO`
- **Residual ALE:** `Current ALE × (1 − Control Effectiveness)`
- **Risk Reduction:** `Current ALE − Residual ALE`
- **ROI:** `(Three-year Gross Benefit − Three-year Lifecycle Cost) ÷ Three-year Lifecycle Cost × 100`
- **Payback Period:** `Initial Investment ÷ (Annual Risk Reduction − Annual Maintenance) × 12`

## Important Assumptions and Limitations

- Supplied probabilities lack a stated time period and are used as annual ARO proxies.
- Database-injection SLE assumes all 500,000 records are affected at $250 per record.
- Control effectiveness figures are supplied assumptions and require technical validation.
- WAF protection does not replace secure query construction and database controls.
- MFA does not necessarily prevent reuse of a hijacked active session.
- ROI and payback estimates exclude discounting, inflation, and changes in exposure.

## References

- National Institute of Standards and Technology. (2012). *Guide for conducting risk assessments* (NIST SP 800-30 Rev. 1). https://doi.org/10.6028/NIST.SP.800-30r1
- OWASP Foundation. *SQL Injection Prevention Cheat Sheet*. https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- OWASP Foundation. *Session Management Cheat Sheet*. https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html
- OWASP Foundation. *OWASP API Security Project*. https://owasp.org/projects/api-security-project

---

## AI Tool Usage

**AI Tool Used:** ChatGPT (OpenAI)

ChatGPT was used to assist with structuring and refining the assessment report, and improving the clarity and presentation of the documentation. The assessment inputs, assumptions, and final conclusions were reviewed by the author.
