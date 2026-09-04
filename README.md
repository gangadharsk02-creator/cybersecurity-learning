# Cybersecurity Learning Portfolio

This repository documents my hands-on cybersecurity learning through practical labs, evidence-based analysis, troubleshooting, and progressively more independent investigation work.

The portfolio is intended to demonstrate what I have actually practiced and verified rather than present untested concepts as completed skills.

---

## Portfolio Navigation

### Skills

Browse the complete skills catalog:

**[Cybersecurity Skills Catalog](skills/README.md)**

Each skill has its own README containing:

- current status
- demonstrated hands-on capabilities
- hands-on labs
- investigation tools and data sources
- evidence produced
- learning progress
- important lessons
- completion criteria
- next learning focus

### Hands-On Evidence

Detailed investigation evidence is stored inside the relevant skill and lab directories rather than duplicated on this landing page.

Navigation follows:

```text
Portfolio
    ↓
Skills Catalog
    ↓
Individual Skill
    ↓
Hands-On Lab
    ↓
Investigation Evidence
```

---

## Featured Skill

### Security Incident Triage

**Status: Learning**

[View Security Incident Triage](skills/triaging-security-incident/README.md)

Current hands-on work has included:

- Windows authentication-event investigation
- failed-to-successful authentication correlation
- authentication timeline construction
- severity, disposition, escalation, and closure decisions
- Windows process-creation analysis
- parent-child process correlation
- command-line analysis

The broader process-triage capability remains in progress and is not yet marked complete.

---

## Current Focus

Continue Windows process triage with less obviously benign activity.

The next work will focus on:

- suspicious or unusual parent-child process relationships
- unusual command-line patterns
- determining what additional evidence is required when process intent is uncertain
- avoiding conclusions based only on executable names

---

## Learning Approach

My general learning workflow is:

**Learn → Do → Verify → Troubleshoot → Document → Review**

For investigation-focused work, I use:

**Goal → Question → Action → Evidence → Analysis → Conclusion**

The emphasis is on understanding why an action is performed, validating the result, separating observations from assumptions, and documenting evidence that supports the conclusion.

---

## Portfolio Principles

This repository follows several documentation principles:

- Skills are added only after meaningful learning or hands-on work begins.
- Completed capabilities must be supported by work that was actually performed.
- A complete lab does not automatically mean the broader skill is complete.
- Evidence is reviewed before publication.
- Sensitive or unnecessary identifying information is removed from public evidence.
- Technical evidence required to support an investigation is preserved where practical.
- Conflicting notes are resolved using primary evidence rather than assumptions.
- Investigation limitations are documented rather than hidden.
- Repository structure is expanded only when real work requires it.

---

## Portfolio Workflow

The repository itself is also being used to practice a repeatable technical-documentation workflow.

Current portfolio workflow status:

**Git/GitHub workflow: Practicing**

Work performed so far includes:

- Git repository initialization
- staging and reviewing changes
- creating descriptive commits
- configuring repository remotes
- pushing work to GitHub
- troubleshooting GitHub authentication
- configuring repository-specific Git identity
- verifying published commits
- reviewing evidence before publication
- maintaining sanitized screenshots and Markdown documentation

Git and GitHub are treated as portfolio and version-control tools rather than as Security Incident Triage investigation tools.

---

## Repository Organization

The repository uses a layered structure so that the landing page remains manageable as additional cybersecurity skills are added.

```text
cybersecurity-learning/
│
├── README.md
│   └── portfolio landing page
│
├── skills/
│   ├── README.md
│   │   └── cybersecurity skills catalog
│   │
│   └── triaging-security-incident/
│       ├── README.md
│       │   └── detailed skill progress and capabilities
│       │
│       └── labs/
│           └── individual evidence-driven labs
│
└── projects/
    └── reserved for future multi-skill projects when required
```

Existing skill and lab paths are kept stable unless there is a strong reason to reorganize them.

Additional discipline layers can be introduced later if the number of skills grows enough to require them.

---

## Architecture

The portfolio currently follows:

```text
Root Portfolio
    ↓
Skills Catalog
    ↓
Individual Skill
    ↓
Hands-On Labs
    ↓
Evidence and Analysis
```

If the portfolio becomes substantially larger, the skills catalog can later introduce cybersecurity-discipline pages without requiring the root README to become a large index.

---

## Current Portfolio Scope

Active skill area:

```text
SOC Operations
└── Security Incident Triage
```

Detailed capability status and lab evidence are maintained in the relevant skill README and are intentionally not duplicated here.

---

This portfolio will grow as additional skills are actually practiced, verified, documented, and supported by hands-on evidence.
