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

### 3. Windows Process Parent-Child Correlation
- analyzed Windows Security Event ID `4688`
- reconstructed `explorer.exe → cmd.exe → PING.EXE`
- correlated parent and child processes using PIDs
- analyzed executable paths, command lines, and token context
- assessed the controlled activity as benign with high confidence

[View the Windows Process Parent-Child Correlation](labs/process-parent-child-correlation/README.md)

---

## Investigation Tools and Data Sources

Only tools and data sources actually used during the hands-on investigations are listed here.

### Investigation Tools

- **Windows Event Viewer** — located, filtered, and examined Windows Security events.
- **PowerShell** — queried Windows event records and searched structured event data during process correlation.
- **Command Prompt** — generated controlled process activity and executed test commands.
- **`auditpol.exe`** — inspected and enabled Windows process-creation auditing.
- **`reg.exe` / Windows Registry** — inspected and enabled command-line inclusion for Event ID `4688`.

### Data Sources

- **Windows Security event log** — primary source of authentication and process-creation evidence.
- **Event ID `4624`** — successful authentication evidence.
- **Event ID `4625`** — failed authentication evidence.
- **Event ID `4634`** — logoff/session-termination evidence examined during authentication correlation.
- **Event ID `4688`** — process-creation and parent-child process evidence.

Additional investigation tools or data sources will be added only after they are used in hands-on work.

---

## Evidence Produced

Hands-on work completed so far has produced and validated several types of investigation evidence and analyst artifacts:

- sanitized Windows Event Viewer General-view screenshots
- sanitized raw Windows event XML screenshots
- authentication-failure comparison evidence
- failed-to-successful authentication timelines
- Logon Type and Linked Logon ID correlation evidence
- elevated and non-elevated authentication-context comparisons
- documented severity, disposition, confidence, escalation, and closure decisions
- Windows process-creation evidence from Security Event ID `4688`
- parent-child process relationships reconstructed using process IDs
- process command-line evidence
- reconstructed process trees
- documented benign-versus-suspicious process assessments
- investigation limitations and evidence-quality notes

Public evidence is reviewed before publication so that investigation-relevant technical information is preserved while unnecessary identifying or sensitive information is removed.

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
| Process triage | Learning |
| Network triage | Not Started |
| IOC triage | Not Started |
| SIEM-based triage | Not Started |
| Independent incident triage | Not Started |

---

## Completed Hands-On Capabilities

The following capabilities are marked completed only where they have been practiced and supported by hands-on evidence.

| Capability | Status | Evidence |
|---|---|---|
| Security event, alert, and incident differentiation | Completed | Triage fundamentals |
| Investigation-question development | Completed | Security Incident Triage exercises |
| Evidence identification | Completed | Security Incident Triage exercises |
| Windows successful logon analysis | Completed | Event ID `4624` analysis |
| Windows failed logon analysis | Completed | Event ID `4625` analysis |
| Windows authentication failure analysis | Completed | [Authentication Failure Analysis](labs/authentication-failure-analysis/README.md) |
| Raw Windows event XML validation | Completed | Event Viewer General/XML comparison |
| Password vs Windows Hello PIN failure analysis | Completed | [Authentication Failure Analysis](labs/authentication-failure-analysis/README.md) |
| Failed-to-successful authentication correlation | Completed | [Authentication Timeline Correlation](labs/authentication-timeline-correlation/README.md) |
| Authentication timeline construction | Completed | [Authentication Timeline Correlation](labs/authentication-timeline-correlation/README.md) |
| Windows Logon Type analysis | Completed | Logon Types `2`, `5`, `7`, and `11` examined |
| Linked Logon ID analysis | Completed | Type `7` and Type `11` paired-session analysis |
| Elevated vs non-elevated session comparison | Completed | Event ID `4624` analysis |
| Evidence sanitization for public portfolio use | Completed | Sanitized screenshots and documentation |
| Security severity assessment | Completed | Context, scope, impact, and evidence-based severity classification |
| Incident disposition | Completed | `Benign / Test Activity` classification with confidence assessment |
| Escalation and closure decision | Completed | `Do Not Escalate` and `Close — Authorized Test Activity` |
| Windows process-creation event analysis | Completed | Security Event ID `4688` identification and interpretation |
| Process parent-child correlation | Completed | [Windows Process Parent-Child Correlation](labs/process-parent-child-correlation/README.md) |
| Process command-line analysis | Completed | Enabled command-line auditing and interpreted controlled process arguments |
| Basic dual-use process assessment | Completed | Evaluated `cmd.exe` and `ping.exe` using context rather than process name alone |

Additional capabilities will be added only after they have been practiced and supported by evidence.

## Important Lessons So Far

- Event ID alone is not enough to determine what activity means; context is required.
- Alert severity does not automatically determine incident severity.
- A failed authentication event does not automatically indicate an attack.
- Logon Type materially changes the interpretation of a Windows authentication event.
- Subject-account and target-account fields represent different contexts and must not be confused.
- Missing event fields should be documented as missing rather than replaced with assumptions.
- Observed evidence should be separated from analyst assumptions and interpretations.
- Primary log evidence should take precedence over conflicting manual notes or recollection.
- Raw event XML can be used to validate and clarify the human-readable Event Viewer view.
- Timestamps are essential for correlating related actions and constructing investigation timelines.
- Authentication events should be correlated using multiple fields rather than a single username, timestamp, or Event ID.
- Severity should be based on context, scope, demonstrated impact, and available evidence rather than on the presence of a security event alone.
- Disposition describes what the activity represents, while severity describes how serious the activity is.
- Benign or authorized activity is not necessarily a false positive; the underlying event or detection may still have occurred correctly.
- Escalation should be based on unresolved risk, suspected malicious activity, scope, impact, and the need for additional authority or expertise.
- Process names alone are insufficient to determine whether execution is benign or malicious.
- Parent-child process relationships provide important execution context during process triage.
- A process's `NewProcessId` can be correlated with a later event's creator `ProcessId` to reconstruct process lineage.
- Process IDs can be reused, so PID correlation should also consider timestamps, executable paths, command lines, and surrounding events.
- Executable paths provide useful context but do not prove that a process is legitimate.
- Command-line arguments can provide more investigative value than the executable name alone.
- Legitimate Windows utilities such as `cmd.exe` and `ping.exe` are dual-use and may appear in both normal administration and attacker activity.
- Token elevation state is supporting context, not a standalone benign-or-malicious verdict.
- Evidence should be collected and validated before drawing conclusions.
- Public investigation evidence should preserve technical value while removing unnecessary identifying or sensitive information.
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

Continue Windows process triage with activity that is less obviously benign.

The next stage will focus on recognizing suspicious process relationships and command-line patterns, determining what additional evidence is required when process intent is uncertain, and avoiding conclusions based only on executable names.