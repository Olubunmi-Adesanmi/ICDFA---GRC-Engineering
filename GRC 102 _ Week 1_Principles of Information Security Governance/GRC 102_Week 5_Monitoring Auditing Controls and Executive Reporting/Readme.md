# GRC102 Practical Lab5 - Security Governance Simulation

**Course:** GRC102 Information Security Governance  
**Assessment:** Practical Lab 5 - Monitoring, Auditing Controls and Executive Reporting  


## Overview

This report  documents a simulated security governance lab covering container setup, vulnerability assessment, governance failure analysis, control status, security metrics, risk oversight and executive reporting. It is organised in the same four-part order required by the assessment brief.

## Important findings

- The supplied vulnerability report identifies one Medium network-segmentation finding, one MySQL default-credential check that did not detect access, and one inconclusive Struts2 check due to hostname resolution failure.
- The governance failure analysis reports three failures: patch-policy implementation, metrics not driving remediation, and insufficient segmentation.
- The tracker data records three open risks: one Critical, one High and one Medium.
- The dashboard marks remediation time (12 days against a 7-day target) and incidents (1 against target 0) as Green. These classifications conflict with their targets and need correction.
- The Struts simulation did not complete; the configured image reference returned `manifest unknown`, the `web_server` hostname did not resolve, and the analysis tool printed `No attack log found`.
- No successful post-remediation retest was provided.

## Contents

| File/folder | Purpose |
|---|---|
| `report.md` | Full evidence-based report, including the required four parts, Equifax comparison, recommendations and references |
| `GRC102_Lab_Security_Governance_Report.docx` | Editable formatted report |
| `GRC102_Lab5_Security_Governance_Report.pdf` | PDF evidence report; screenshot placeholders must be replaced before final submission |
| `board_report.md` | Concise board-level report based on the supplied results |
| `equifax_comparison.md` | Standalone Equifax case-study comparison |
| `governance_controls_report.md` | Control status and verification report; unresolved tests are explicit |
| `governance_metrics_framework.md` | Metric definitions, formula, owner, thresholds, review cadence and response rules |
| `dashboard_user_guide.md` | User guidance for interpreting and validating the governance dashboard |
| `evidence/figures/` | Report-created visualisations reconstructed from supplied JSON values; they are not original Kali screenshots |
| `evidence/screenshots/` | Folder for genuine screenshots captured from the authorised lab |

 
 ## Conclusion

This GRC102 practical laboratory demonstrates how technical security assessments can support information security governance, risk management, control monitoring, and executive decision-making. The lab produced evidence for vulnerability assessment, governance failure analysis, risk tracking, security metrics, and reporting within a simulated, container-based environment.

The findings highlighted three key governance weaknesses: ineffective implementation of the patch management policy, security metrics that were not consistently driving remediation, and insufficient network segmentation. The dashboard also revealed inconsistencies between recorded metric values and their Green status classifications, demonstrating the importance of accurate measurement, validation, and escalation.

However, the lab had technical limitations. The configured Struts2 image could not be resolved, the `web_server` hostname failed to resolve, and no attack log was found. Consequently, the attack simulation was not successfully completed, and the available evidence does not confirm successful post-remediation testing or control effectiveness.

The accompanying reports and documentation provide a foundation for improving governance oversight, prioritising outstanding risks, assigning remediation responsibilities, and strengthening evidence-based reporting. Recommended next steps include resolving the lab configuration issues, correcting metric thresholds, implementing and verifying corrective actions, repeating authorised tests, and documenting the results.

Overall, the lab reinforces an important information security governance principle: **a control should not be considered effective simply because it is recorded as implemented. Its effectiveness must be supported by appropriate evidence, testing, monitoring, and documented follow-up.**

## References

- [ICDFA GRC102 Week 5 Linux Lab Instructions](https://github.com/icdfa/grc-engineering-labs/blob/master/phase1/grc102/week8/LAB_INSTRUCTIONS.md) - official repository instructions supplied with the assessment brief.
- [U.S. GAO report GAO-18-559](https://www.gao.gov/products/gao-18-559) - Equifax breach response and contributing factors.
- [U.S. House Committee report: The Equifax Data Breach](https://oversight.house.gov/wp-content/uploads/2018/12/Equifax-Report.pdf) - patching, monitoring, accountability and other case-study findings.

 ## AI Usage Declaration
Generative AI(ChatGPT) was used to assist with organising the s lab material into a structured report, refining grammar and professional wording, improving table presentation, 
AI was not treated as a source of lab evidence. The reported scanner results, governance counts, risk ratings, metric values, dates, and technical limitations were taken from the supplied lab notes and output summaries.


