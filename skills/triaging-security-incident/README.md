# Security Incident Triage

## Status

**Learning**

This section tracks my hands-on development of security incident triage skills.

The goal is not only to identify alerts, but to investigate evidence, determine what happened, assess the available context, document findings, and make defensible triage decisions.

---

## What Is Security Incident Triage?

Security incident triage is the initial investigation of potentially suspicious activity to determine:

- What happened?
- Which user, host, process, or network source was involved?
- Is the activity expected, suspicious, or malicious?
- What evidence supports the assessment?
- What is the likely scope and impact?
- Does the activity require additional investigation or escalation?

An alert alone does not prove that a security incident occurred.

The investigation must be based on evidence.

---

## Investigation Method

I am practicing the following workflow:

**Goal → Question → Action → Evidence → Analysis → Conclusion**

This helps avoid random log searching and premature conclusions.

---

## Current Skills Practiced

### Triage Fundamentals

- Distinguished security events, alerts, and incidents.
- Practiced converting alerts into specific investigation questions.
- Identified evidence required to answer investigation questions.
- Practiced separating observations from assumptions.

### Windows Authentication Analysis

- Located Windows Security Event ID `4624` successful-logon events.
- Examined different logon contexts, including Logon Type `2` and Logon Type `5`.
- Located and analyzed Event ID `4625` failed-logon events.
- Examined:
  - Failure Reason
  - Status
  - Sub Status
  - Logon Type
  - Logon Process
  - Authentication Package
  - Caller Process
  - Source Network Address
- Used raw XML to verify structured Event Viewer data.
- Compared controlled password and Windows Hello PIN authentication failures.

- Correlated a controlled Event ID `4625` failure with subsequent Event ID `4624` success activity.
- Built a timestamp-based authentication timeline.
- Analyzed Logon Type `7` workstation-unlock events.
- Identified supporting Logon Type `11` CachedInteractive events.
- Used Linked Logon IDs to identify paired elevated and non-elevated authentication contexts.
- Practiced resolving conflicting manual notes using primary log evidence.

### Triage Decision-Making

- Assessed activity severity using context, scope, impact, and available evidence.
- Distinguished an observed security event from demonstrated malicious activity.
- Assigned an `Informational` severity to controlled benign activity.
- Classified activity as `Benign / Test Activity`.
- Expressed investigation confidence as `High`.
- Determined that escalation was not required.
- Recommended closure as `Close — Authorized Test Activity`.
- Practiced distinguishing benign activity from a false-positive classification.

---

## Hands-On Labs

### 1. Windows Authentication Failure Analysis

I performed controlled authentication-failure tests and examined the resulting Windows Security Event ID `4625` records.

The lab includes:

- controlled incorrect-password authentication
- controlled incorrect Windows Hello PIN authentication
- Event Viewer analysis
- raw XML validation
- failure-status comparison
- sanitized evidence screenshots
- documented observations and limitations

[View the authentication failure analysis lab](labs/authentication-failure-analysis/README.md)

### 2. Windows Authentication Timeline Correlation

I correlated a controlled failed password authentication with subsequent successful Windows authentication activity.

The lab includes:

- Event ID `4625` failed-authentication analysis
- Event ID `4624` successful-authentication analysis
- failed-to-successful event correlation
- Logon Type `7` workstation-unlock analysis
- supporting Logon Type `11` CachedInteractive activity
- Linked Logon ID analysis
- elevated and non-elevated session comparison
- authentication timeline construction
- handling conflicting analyst notes
- sanitized General and XML evidence

[View the authentication timeline correlation lab](labs/authentication-timeline-correlation/README.md)

---

## Tools Used So Far

- Windows Event Viewer
- Windows Security Event Log
- Windows Settings
- Git

Additional tools will be added only after I actually use them.

---

## Evidence Produced

Current portfolio evidence includes:

- Event ID `4625` General-tab evidence
- Event ID `4625` XML evidence
- controlled password-failure evidence
- controlled PIN-failure evidence
- documented comparison and analysis

Sensitive machine-identifying information was removed from public screenshots.

---

## Current Learning Progress

| Area | Status |
|---|---|
| Event vs alert vs incident | Completed |
| Investigation-question development | Completed |
| Evidence identification | Completed |
| Windows successful-logon identification | Completed |
| Windows failed-logon identification | Completed |
| Basic authentication-event interpretation | Completed |
| Raw XML validation | Completed |
| Controlled failure correlation | Completed |
| Failed → successful logon correlation | Completed |
| Authentication timeline analysis | Completed |
| Severity assessment | Completed |
| Incident disposition | Completed |
| Escalation decision | Completed |
| Process triage | Not Started |
| Network triage | Not Started |
| IOC triage | Not Started |
| SIEM-based triage | Not Started |
| Independent incident triage | Not Started |

---

## Important Lessons So Far

- Event ID alone is not enough to understand activity.
- Alert severity does not prove incident severity.
- A failed authentication event does not automatically indicate an attack.
- Logon Type changes the meaning of an authentication event.
- Missing fields should be recorded as missing rather than replaced with assumptions.
- Subject and target-account fields must not be confused.
- Timestamps help correlate known actions with log evidence.
- Raw event data can be used to validate human-readable Event Viewer output.
- Evidence should be collected before drawing conclusions.

---

## Skill Completion Criteria

This skill is **not completed yet**.

Before I consider security incident triage completed, I should be able to independently:

- interpret a security alert
- form useful investigation questions
- identify appropriate evidence sources
- correlate multiple related events
- build an incident timeline
- determine affected users and systems
- distinguish benign, suspicious, and malicious activity
- assess severity and impact
- document uncertainty
- decide whether escalation is necessary
- write professional analyst notes
- troubleshoot common investigation problems
- complete an incident-triage exercise with minimal guidance

---

## Next Focus

The next stage is process triage.

This will involve examining Windows process activity, parent-child process relationships, command lines, execution context, and other evidence used to determine whether process behavior is expected or suspicious.