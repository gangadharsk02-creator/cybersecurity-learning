# Cybersecurity Learning Portfolio

This repository documents my hands-on cybersecurity learning through practical labs, evidence-based analysis, troubleshooting, and progressively more independent exercises.

The purpose of this repository is to demonstrate what I have actually practiced and verified rather than present untested concepts as completed skills.

---

## Learning Approach

My learning process follows:

**Learn → Do → Verify → Troubleshoot → Document → Review**

For investigation-focused work, I use:

**Goal → Question → Action → Evidence → Analysis → Conclusion**

The emphasis is on understanding why an action is performed, validating the result, and documenting evidence that supports the conclusion.

---

## Current Skills

| Skill | Status | Hands-On Work |
|---|---|---|
| [Security Incident Triage](skills/triaging-security-incident/README.md) | Learning | Windows authentication analysis, event correlation, and timeline analysis |

## Completed Hands-On Skills

| Skill / Capability | Status | Evidence |
|---|---|---|
| Security event, alert, and incident differentiation | Completed | Triage fundamentals |
| Investigation-question development | Completed | Security Incident Triage exercises |
| Evidence identification | Completed | Security Incident Triage exercises |
| Windows successful logon analysis | Completed | Event ID `4624` analysis |
| Windows failed logon analysis | Completed | Event ID `4625` analysis |
| Windows authentication failure analysis | Completed | [Authentication Failure Analysis](skills/triaging-security-incident/labs/authentication-failure-analysis/README.md) |
| Raw Windows event XML validation | Completed | Event Viewer General/XML comparison |
| Password vs Windows Hello PIN failure analysis | Completed | Authentication Failure Analysis lab |
| Failed-to-successful authentication correlation | Completed | [Authentication Timeline Correlation](skills/triaging-security-incident/labs/authentication-timeline-correlation/README.md) |
| Authentication timeline construction | Completed | Authentication Timeline Correlation lab |
| Windows Logon Type analysis | Completed | Logon Types `2`, `5`, `7`, and `11` examined |
| Linked Logon ID analysis | Completed | Type `7` and Type `11` paired-session analysis |
| Elevated vs non-elevated session comparison | Completed | Event ID `4624` analysis |
| Evidence sanitization for GitHub | Completed | Sanitized screenshots and documentation |
| Security severity assessment | Completed | Context, scope, impact, and evidence-based severity classification |
| Incident disposition | Completed | Benign / Test Activity classification with confidence assessment |
| Escalation and closure decision | Completed | Do Not Escalate and Close — Authorized Test Activity |
| Git/GitHub portfolio workflow | Practicing | Repository initialization, staging, commits, remotes, push, and troubleshooting |

Additional skills will be added as I actually begin working on them.

---

## Current Hands-On Labs

### Security Incident Triage

#### Windows Authentication Failure Analysis

Practiced analysis of controlled Windows authentication failures using Windows Security Event ID `4625`.

Work performed includes:

- examining failed interactive authentication events
- comparing password and Windows Hello PIN failures
- interpreting relevant authentication fields
- validating Event Viewer data using raw XML
- preserving sanitized screenshots as evidence
- distinguishing observed facts from assumptions

[View the authentication failure analysis lab](skills/triaging-security-incident/labs/authentication-failure-analysis/README.md)

#### Windows Authentication Timeline Correlation

Correlated a controlled failed Windows password authentication with subsequent successful workstation-unlock activity.

Work performed includes:

- correlating Event ID `4625` with subsequent Event ID `4624` activity
- building a failed-to-successful authentication timeline
- analyzing Logon Type `7` workstation unlocks
- examining supporting Logon Type `11` CachedInteractive events
- analyzing Linked Logon IDs
- comparing elevated and non-elevated authentication contexts
- resolving conflicting manual notes using primary log evidence
- preserving sanitized General and XML evidence

[View the authentication timeline correlation lab](skills/triaging-security-incident/labs/authentication-timeline-correlation/README.md)

---

## Tools Used

Tools listed here are included only after they have been used during hands-on work.

- Windows Event Viewer
- Windows Security Event Log
- Windows Settings
- Command Prompt
- Git

---

## Current Focus

Windows process triage, including process execution context, parent-child relationships, command-line analysis, and determining whether process activity is expected or suspicious.

---

## Repository Structure

```text
cybersecurity-learning/
│
├── README.md
│
└── skills/
    └── triaging-security-incident/
        ├── README.md
        └── labs/
            └── authentication-failure-analysis/
                ├── README.md
                └── screenshots/