# ALLIS deployment model

## Overview

**ALLIS — the Artificial Learning and Location Intelligence System** is a governed computational platform developed by Kidd's Technical Services.

This document defines how ALLIS is instantiated in a specific deployment while preserving the distinction between:

- the qualified ALLIS architecture;
- deployment-specific configuration;
- external infrastructure;
- local data and geographic context;
- human and institutional authority;
- observed runtime behavior;
- deployment evidence.

A deployment applies ALLIS to a bounded environment. It does not redefine the underlying platform.

> **Core rule:** A deployment instantiates ALLIS; it does not redefine ALLIS.

---

## 1. Document status

**Document role:** Architecture specification  
**Scope:** Deployment structure and deployment boundaries  
**Evidence basis:** Current qualified ALLIS architecture and documented deployment contexts  
**Implementation status:** Deployment-specific  
**Runtime status:** Must be established separately for each deployment  
**Formal status:** Not inferred from this architecture document  

This document describes the canonical deployment model. It does not claim that every described component is active in every deployment or that a proposed deployment has been installed, tested, or evaluated.

---

## 2. Deployment definition

An ALLIS deployment is a bounded runtime instance in which the qualified ALLIS architecture is combined with local configuration, infrastructure, data, authority, and interfaces.

At a high level:

```text
qualified ALLIS baseline
        +
deployment configuration
        +
local data and geographic context
        +
runtime infrastructure
        +
external authority and governance
        +
measurement and evidence
        ↓
bounded ALLIS deployment
```

The qualified ALLIS baseline defines the system architecture.

The deployment defines how that architecture is instantiated for a particular place, organization, research environment, or use case.

---

## 3. Canonical deployment architecture

```text
                     EXTERNAL AUTHORITY DOMAIN
        people · institutions · site governance · policy
                              │
                              │ authority, identity,
                              │ permissions, constraints
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                  ALLIS DEPLOYMENT BOUNDARY                  │
│                                                             │
│  1. Interface layer                                         │
│     user, operator, application, research, or API access    │
│                              │                              │
│                              ▼                              │
│  2. Governed ingress                                        │
│     source · provenance · scope · identity context          │
│                              │                              │
│                              ▼                              │
│  3. State layer                                             │
│     semantic · geographic · temporal · person-linked        │
│     memory/provenance · governance/authority                │
│                              │                              │
│                              ▼                              │
│  4. Governed computation                                    │
│     retrieval · reasoning · analysis · state evaluation     │
│                              │                              │
│                              ▼                              │
│  5. Trust and authority evaluation                          │
│     authentication · authorization · disclosure · operation │
│                              │                              │
│                              ▼                              │
│  6. Protected transition control                            │
│     retain · promote · disclose · modify · external action  │
│                              │                              │
│                              ▼                              │
│  7. Evidence and provenance                                 │
│     transition record · result lineage · validation context │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
                    EXTERNAL SYSTEMS / WORLD
```

This diagram is conceptual. A deployment can distribute these functions across multiple services, processes, machines, or network locations.

The boundary is defined by function and authority, not by a single container or host.

---

## 4. Required deployment functions

A deployment must preserve the following architectural functions.

### 4.1 Governed ingress

Incoming information must retain enough context to support its permitted use.

This can include:

- source;
- provenance;
- scope;
- time;
- geographic context;
- identity context;
- applicable authority.

Availability to the system does not automatically make incoming information verified or authoritative.

### 4.2 State representation

The deployment can use the state classes defined in `architecture/state-models/STATE_MODEL_OVERVIEW.md`:

- semantic and informational state;
- geographic and spatial state;
- temporal state;
- person-linked state;
- memory and provenance state;
- governance and authority state.

Not every deployment must use every state class.

### 4.3 Governed computation

The deployment can perform retrieval, analysis, reasoning, comparison, and other computational operations over available state.

Computation does not itself authorize retention, disclosure, modification, or action.

### 4.4 Trust and authority evaluation

Protected transitions remain subject to the trust model defined in `architecture/trust-and-authority/TRUST_AND_AUTHORITY_OVERVIEW.md`.

The deployment must preserve distinctions among:

```text
identity
≠ authentication
≠ authorization
≠ disclosure authority
≠ governance authority
≠ operation authority
```

### 4.5 Protected transition control

The deployment must control transitions that can change the status, availability, or effect of governed state.

Examples include:

```text
temporary context
    → retained memory

candidate result
    → promoted state

private state
    → authorized disclosure

candidate modification
    → committed state

computed result
    → external action
```

### 4.6 Evidence and provenance

Protected transitions should preserve enough evidence to establish what occurred, under what scope, and under what authority.

---

## 5. Deployment-specific components

A deployment can add components that are not part of the universal ALLIS core.

Examples include:

- site-specific data;
- maps and geographic boundaries;
- local knowledge sources;
- external databases;
- devices and sensors;
- network infrastructure;
- public interfaces;
- administrative interfaces;
- local operating procedures;
- site-specific privacy requirements;
- institution-specific policy;
- deployment-specific retention rules.

These components belong to the deployment context.

They do not become universal ALLIS architecture merely because one deployment uses them.

---

## 6. External authority boundary

ALLIS can operate within environments governed by people and institutions that retain their own authority.

Examples can include:

- property owners;
- municipalities;
- universities;
- nonprofits;
- government agencies;
- research institutions;
- community governance bodies.

A deployment can receive authorization, constraints, decisions, or data from these actors.

ALLIS does not absorb their authority.

Likewise, ALLIS technical authority does not automatically grant legal, institutional, regulatory, or community authority.

> **A deployment can connect ALLIS to an authority domain without transferring that authority into ALLIS.**

---

## 7. Interfaces

A deployment can expose ALLIS through one or more interfaces, including:

- operator tools;
- research interfaces;
- APIs;
- browser or application interfaces;
- public information interfaces;
- intelligence-facing services.

An interface provides access to system capabilities. It does not create authority.

For example:

```text
interface access
    ≠ protected-state access

user request
    ≠ authorization

generated recommendation
    ≠ approved external action
```

Where **Ms. Allis** is used as an intelligence-facing service, she operates through these same boundaries and does not create independent governance or operation authority.

---

## 8. Deployment configuration

Deployment configuration is the set of local choices that determine how the qualified ALLIS architecture is instantiated.

Configuration can include:

- enabled services;
- approved data sources;
- local geographic scope;
- interface settings;
- retention policy;
- identity requirements;
- recipient restrictions;
- external integrations;
- measurement settings;
- deployment-specific authority rules.

Configuration is not equivalent to architecture.

A local configuration change should not silently alter the qualified ALLIS baseline.

If a deployment reveals a need for a platform-level change, that change should move through engineering review, qualification, and validation before it becomes part of the accepted baseline.

---

## 9. Runtime correspondence

A deployment is not validated solely because its architecture and configuration are documented.

The expected correspondence chain is:

```text
documented architecture
        ↕
qualified source
        ↕
deployment configuration
        ↕
observed runtime
        ↕
measured results
```

Each link answers a different question:

**Architecture** — What should the system do?  
**Qualified source** — Which implementation is being evaluated?  
**Configuration** — How was that implementation instantiated here?  
**Observed runtime** — What actually ran?  
**Measured results** — What behavior was observed under defined conditions?  

A result at one layer should not be promoted into a broader claim about another layer without supporting evidence.

---

## 10. Deployment status

Deployment status should reflect the strongest state supported by evidence.

The following terms are intentionally distinct:

```text
concept
    ↓
proposed
    ↓
approved
    ↓
authorized
    ↓
installed
    ↓
configured
    ↓
tested
    ↓
observed
    ↓
operational
    ↓
evaluated
    ↓
replication-supported
```

These terms are not interchangeable.

In particular:

```text
proposed
    ≠ approved

approved
    ≠ authorized

authorized
    ≠ installed

installed
    ≠ tested

tested
    ≠ operational

operational
    ≠ evaluated

evaluated
    ≠ universally replicable
```

This vocabulary is part of the evidentiary architecture.

It prevents project status from being overstated.

---

## 11. Failure and degraded operation

A deployment must preserve clear behavior when required dependencies are unavailable.

Examples include:

- missing network access;
- unavailable external services;
- stale information;
- incomplete provenance;
- unavailable identity verification;
- missing authority;
- invalid configuration;
- failed evidence capture.

For protected transitions, unresolved required authority should remain fail closed.

For non-protected functions, bounded degraded behavior can be permitted where it is explicitly supported and does not create a false claim of normal operation.

A degraded deployment should be identified as degraded.

---

## 12. Deployment evidence

Deployment evidence should distinguish physical presence, configuration, runtime observation, and outcome.

Useful categories include:

**Installed**  
A component is physically or logically present.

**Configured**  
The component has been set up for the intended environment.

**Tested**  
A defined test has been executed.

**Observed**  
A behavior has been directly observed in runtime.

**Operational**  
The system is being used within an authorized scope.

**Evaluated**  
Evidence has been analyzed against defined metrics or questions.

**Replication-supported**  
Evidence supports a bounded decision about transfer to another deployment.

No later status should be inferred from an earlier one.

---

## 13. Example deployment context: New River Gorge

The **New River Gorge Safety & Heritage Mesh Pilot** is one documented deployment and research context for ALLIS.

It is not the definition of ALLIS.

The current public project record treats:

- **Mount Hope** as the proposed first implementation phase;
- **Thurmond** as a separate future federal phase.

The project can provide deployment-specific elements such as:

- geographic context;
- public information;
- heritage information;
- local infrastructure;
- community participation;
- site governance;
- field observation;
- evaluation.

The **Community Champion** program is a related human-stewardship and field-participation model. Its existence does not automatically confer technical, institutional, or system-administration authority on participants.

Project budgets, grant status, letters of support, site approvals, and field evidence remain in the project repository or other evidence records that own those artifacts.

The architectural relationship is:

```text
ALLIS
    ↓
qualified technical platform

New River Gorge use case
    ↓
deployment and research context

Mount Hope
    ↓
proposed first implementation phase

Thurmond
    ↓
separate future federal phase
```

A later site must establish its own authority, privacy, infrastructure, configuration, and evidence.

---

## 14. Replication

ALLIS distinguishes technical reproducibility from responsible deployment transfer.

A later deployment can require different:

- authority;
- infrastructure;
- governance;
- privacy rules;
- local data;
- operating capacity;
- maintenance;
- accessibility;
- community participation;
- institutional review.

Therefore:

> **Technology can be reproducible without a deployment being automatically transferable.**

Replication decisions should be based on evidence from the deployment being evaluated and the requirements of the environment receiving it.

---

## 15. Relationship to other architecture documents

This document completes the high-level architecture sequence:

```text
architecture/system-boundary/
    Where does ALLIS begin and end?

architecture/state-models/
    What kinds of state exist inside that boundary?

architecture/trust-and-authority/
    What governs protected use and state transition?

architecture/deployment-model/
    How is the architecture instantiated in a real environment?
```

Related validation material belongs elsewhere:

- `acceptance/` — qualified baselines;
- `claims/` — explicit claims;
- `measurements/` — protocols, metrics, and results;
- `mathematics/` — formal structures;
- `formal-verification/` — proofs and model checks;
- `correspondence/` — architecture/source/runtime correspondence;
- `evidence/` — provenance and reproducibility records.

---

## 16. Summary

An ALLIS deployment is a bounded instantiation of a qualified ALLIS baseline.

It combines the core platform with local configuration, infrastructure, data, authority, interfaces, and evidence while preserving the distinction between the system and the environment in which it operates.

The deployment model is governed by three rules:

> **A deployment instantiates ALLIS; it does not redefine ALLIS.**

> **Installation is not evidence of tested operation, and tested operation is not evidence of demonstrated outcome.**

> **A deployment may connect ALLIS to external authority, but it does not absorb that authority into the system.**
