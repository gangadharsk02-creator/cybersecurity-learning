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
| [Security Incident Triage](skills/triaging-security-incident/README.md) | Learning | Windows authentication analysis |

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

---

## Tools Used

Tools listed here are included only after they have been used during hands-on work.

- Windows Event Viewer
- Windows Security Event Log
- Windows Settings
- Command Prompt
- Git

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