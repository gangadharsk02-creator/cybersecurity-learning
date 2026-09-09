# Cybersecurity Skills Catalog

This catalog tracks cybersecurity skills that I have actually started practicing through hands-on work.

Detailed capabilities, progress, labs, evidence, and learning notes are maintained inside each individual skill directory rather than duplicated here.

---

## SOC Operations

| Skill | Status | Hands-On Labs | Current Focus |
|---|---|---:|---|
| [Security Incident Triage](triaging-security-incident/README.md) | Learning | 4 | Windows process triage |

---

## Status Definitions

| Status | Meaning |
|---|---|
| Learning | Actively learning the skill and completing guided hands-on work |
| Practicing | Core concepts have been learned, but additional repetition or independent practice is still required |
| Completed | Defined completion criteria have been demonstrated with hands-on evidence |
| Review Needed | Previously practiced material requires review before it can be considered current |

A skill is not marked `Completed` simply because one or more labs have been finished. Completion depends on the criteria documented in that skill's README.

---

## Catalog Organization

Skills are grouped by cybersecurity discipline only after hands-on work in that area begins.

The current navigation model is:

```text
Skills Catalog
    ↓
Cybersecurity Discipline
    ↓
Individual Skill
    ↓
Hands-On Labs
    ↓
Investigation Evidence
```

Detailed capability lists are intentionally kept out of this catalog.

For example, capabilities such as:

- Event ID `4625` analysis
- authentication timeline construction
- severity assessment
- PID correlation
- process command-line analysis

are documented inside the relevant individual skill README rather than repeated here.

This keeps the catalog readable as the portfolio grows.

---

## Current Catalog Rules

- Add a skill only after meaningful learning or hands-on work has begun.
- Keep skill status evidence-based and truthful.
- Do not mark an entire skill completed because a single lab or capability is completed.
- Keep detailed capabilities inside the individual skill README.
- Keep investigation-specific evidence inside the relevant lab README.
- Add new cybersecurity-discipline sections only when actual work exists in those areas.
- Avoid empty placeholder skill directories or sections.

---

## Current Portfolio Scope

At present, the active skill area is:

```text
SOC Operations
└── Security Incident Triage
```

Current hands-on work includes:

- Windows authentication-event analysis
- authentication-event correlation
- authentication timeline construction
- triage severity, disposition, escalation, and closure decisions
- Windows process-creation analysis
- process parent-child correlation
- process command-line analysis
- dual-use PowerShell discovery triage

Process triage remains in progress and has not been marked complete.

---

Additional skills and cybersecurity disciplines will be added only after hands-on work in those areas begins.