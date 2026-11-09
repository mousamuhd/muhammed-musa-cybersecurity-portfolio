# Project 02 – Vulnerability Scanning with Nessus

**Status:** Practical exposure reported; detailed scan evidence to be added  
**Tool:** Nessus  
**Environment:** Training / controlled lab environment

## 1. Objective

Develop familiarity with running vulnerability scans, reviewing scanner output and understanding how scan findings can guide remediation priorities.

## 2. Scope and authorization

Nessus scanning should be limited to systems owned by the learner or explicitly authorized for assessment. The specific target address, scan policy and date for this exercise have not been retained in the available project notes, so they are intentionally not invented here.

## 3. Activities performed

The learner reports carrying out vulnerability scanning using Nessus during cybersecurity internship/practical training.

The available notes also show prior work with Nessus plugin updates and plugin-update logs. This demonstrates exposure to the scanner's maintenance and update process, but does not establish a particular vulnerability finding or scan result.

## 4. Suggested workflow for documenting a repeatable scan

1. Confirm written authorization and identify the approved target.
2. Record the target, date, scan policy and scanner/plugin update status.
3. Select an appropriate scan template for the authorized environment.
4. Run the scan without disrupting the target.
5. Review findings by severity and inspect the supporting evidence.
6. Validate important findings before reporting them.
7. Recommend remediation and, where authorized, rescan to confirm changes.

## 5. Findings

No specific Nessus vulnerability names, severity counts, CVEs, affected hosts or remediation outcomes are included because those details are not available in the current notes. Add them only after checking the original Nessus report.

| Item to record | Value |
|---|---|
| Scan date | [Add date] |
| Authorized target | [Add target or sanitized identifier] |
| Scan policy | [Add policy] |
| Critical / High / Medium / Low counts | [Copy from actual report] |
| Key validated finding | [Add finding and evidence] |
| Remediation recommendation | [Add recommendation] |
| Rescan result | [Add if completed] |

## 6. Reporting and remediation principles

- Prioritize findings using severity, exploitability, exposure and business impact.
- Verify scanner findings; automated results can include false positives.
- Do not claim a vulnerability is exploitable solely because a scanner reported it.
- Recommend patching, secure configuration, service restriction or compensating controls as appropriate.
- Record whether remediation was completed and verified.

## 7. Evidence to add

Add sanitized screenshots or exports from an authorized scan:

- `evidence/nessus-scan-overview.png`
- `evidence/nessus-findings-summary.png`
- `evidence/nessus-remediation-notes.md`

Remove hostnames, public IPs, credentials, internal business names and other sensitive information before publishing.

## 8. Learning outcome

This work provided practical exposure to vulnerability scanning with Nessus and the importance of reviewing scan results as part of a structured security assessment.

## 9. Limitations

The available record confirms Nessus scanning practice but does not contain the original report. This project therefore documents the workflow and learning, not unverified scan findings.
