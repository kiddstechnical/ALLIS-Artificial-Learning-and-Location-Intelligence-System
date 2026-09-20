# ALLIS — Artificial Learning and Location Intelligence System

**A Kidd’s Technical Services research and engineering program for governed artificial intelligence, location intelligence, formal verification, correspondence, and evidence-backed validation.**

ALLIS is the **Artificial Learning and Location Intelligence System** developed through Kidd’s Technical Services (KTS).

This repository is the technical record for the ALLIS platform itself. It documents the system architecture, qualified baseline, formal models, theorem status, correspondence to production source and runtime, evidence identities, counterexamples, residuals, and explicit claim boundaries.

> **A claim may advance only as far as its evidence supports.**

---

## Core principles

ALLIS is built around two related rules:

> **State does not become authority merely because it exists.**

> **Capability does not create authority.**

A system may be able to retrieve information, form a conclusion, generate a candidate change, evaluate it, or technically reach a target without thereby gaining authority to treat that information as final or to perform that action.

```text
available
≠
authorized

inferred
≠
verified

evaluated
≠
approved

technically reachable
≠
permitted target

capable of acting
≠
authorized to act
```

---

## What ALLIS is

ALLIS is a place-aware artificial intelligence and location-intelligence architecture that combines:

- semantic reasoning;
- geographic and spatial state;
- temporal state;
- identity-aware and person-linked state;
- governed memory;
- provenance and source authority;
- authorization and consent;
- trust boundaries;
- privacy-aware disclosure;
- structured state promotion;
- recurrent review and system self-checking; and
- empirical and formal validation.

Not every concept in the broader ALLIS research history has the same validation status. This repository exists to distinguish architectural ideas from implemented, observed, formally specified, proven, machine-checked, and correspondence-verified results.

---

## Validation hierarchy

ALLIS uses this validation hierarchy:

```text
Implemented
    ↓
Observed
    ↓
Demonstrated
    ↓
Formally Specified
    ↓
Proven
    ↓
Machine-Checked
    ↓
Correspondence-Verified
```

These statuses are not interchangeable.

For the current Step-12 work, **Machine-Checked** means machine-executed source-structure checks plus bounded execution evidence. It does not claim proof inside Coq, Lean, Isabelle, TLA+, or another general proof-assistant environment.

---

# Current bounded formal-verification result

The first completed production formal-verification and correspondence package covers the bounded production **authorized-adoption** pathway.

```text
Formal object:
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1

Production source commit:
20c8cbe175781c8a1c05d65c03977859ceca884a

Final Step-12 status:
GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS

Scope:
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

This is a bounded production result.

It is **not** a whole-system ALLIS proof.

### Proposition state

```text
12 formal propositions
11 proven
1 disproven
0 unadjudicated
```

Principal results:

```text
T12D-A = MACHINE_CHECKED
T12D-B = CORRESPONDENCE_VERIFIED
T12D-C = CORRESPONDENCE_VERIFIED
P12C-09 = MACHINE_CHECKED_DISPROVEN
```

### Obligation closure

```text
15/15 formal obligations adjudicated
0 unadjudicated
```

Closure does not mean every desired property became true.

```text
closed
≠
everything proven
```

---

## Governed evolution and authorized adoption

ALLIS separates candidate generation and evaluation from the authority required to change a production-controlled system.

```text
candidate proposed
        ↓
candidate evaluated
        ↓
evidence produced
        ↓
independent authorization required
        ↓
authorization validation
        ↓
target validation
        ↓
prestate validation
        ↓
one-use authority
        ↓
governed application
        ↓
poststate verification
        ↓
receipt
```

The candidate and the authorization are distinct objects:

```text
CandidateEnvelope
≠
AuthorizationEnvelope
```

A useful candidate does not authorize itself.

The runtime can verify external authorization without acquiring the private authority to create that authorization.

### Strongest current authorized-application theorem

```math
\boxed{
M_{auth}
\Rightarrow
V_{auth}
\land
V_{target}
\land
V_{pre}
\land
V_{once}
\land
S_{spent}
\land
R_{receipt}
}
```

In plain language: if the bounded authorized-application path succeeds, authorization validation, target safety, prestate correspondence, one-use authority, spent-state reservation, and receipt correspondence must all have succeeded.

Current level:

```text
MACHINE_CHECKED
```

It is not promoted to `CORRESPONDENCE_VERIFIED` because Step 12 did not perform a real positive production authorization and DGM patch application.

---

# Correspondence

Formal proof about a model does not automatically establish a property of a deployed system.

ALLIS therefore treats correspondence as a first-class validation problem:

```text
FORMAL MODEL
      ↓
model-to-source correspondence
      ↓
SEALED PRODUCTION SOURCE
      ↓
source-to-runtime correspondence
      ↓
LIVE NBB + WORKER
      ↓
theorem-specific live observation
```

Current bounded results:

```text
Formal-to-source correspondence   PASS
NBB source correspondence         11/11 PASS
Worker source correspondence      11/11 PASS
Public trust                      PASS
Governance view                   PASS
```

The theorem-correspondence criterion is:

```math
MC(T,S)
\land
C_{SR}(S,R)
\land
LiveObs(T,R)
```

Matching source is necessary, but theorem-specific live observation remains a separate requirement.

---

## Correspondence is point-in-time

Step 12 establishes:

```math
C_{SR}^{\tau_{seal}}(S,R)=1
```

at the final seal boundary.

It does not establish perpetual future correspondence without revalidation.

```text
R12F-07 = POINT_IN_TIME_BINDING
```

A changed runtime must earn a new correspondence result.

---

# Counterexamples, residuals, and non-promotions

ALLIS preserves negative results as evidence.

The terminal-totality proposition:

```math
Q_3
\Rightarrow
Q_{6C}\lor Q_{6R}
```

was disproven by a bounded machine-executed counterexample.

```text
P12C-09=MACHINE_CHECKED_DISPROVEN
```

Step 12 also preserves eight explicit residuals:

| ID | Residual | Classification |
|---|---|---|
| `R12F-01` | Positive production path | `NOT_OBSERVED` |
| `R12F-02` | Terminalization | `DISPROVEN` |
| `R12F-03` | General production mutation safety | `NOT_PROVEN` |
| `R12F-04` | Whole-system safety | `NOT_PROVEN` |
| `R12F-05` | Historical D1R5 domain | `HISTORICAL_ONLY` |
| `R12F-06` | Bounded formal domain | `BOUNDED_DOMAIN` |
| `R12F-07` | Point-in-time correspondence | `POINT_IN_TIME_BINDING` |
| `R12F-08` | External authority | `EXTERNAL_TO_RUNTIME_MODEL` |

The controlling whole-system boundary remains:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

---

# Repository structure

```text
ALLIS/
│
├── README.md
├── LICENSE
│
├── architecture/
│   ├── deployment-model/
│   ├── state-models/
│   ├── system-boundary/
│   └── trust-and-authority/
│
├── acceptance/
│   └── qualified-baseline/
│
├── formal-verification/
│   └── authorized-adoption/
│       ├── formal-model.md
│       ├── theorem-registry.md
│       └── counterexample-registry.md
│
├── correspondence/
│   ├── README.md
│   └── authorized-adoption/
│       ├── model-to-source.md
│       └── source-to-runtime.md
│
└── evidence/
    ├── README.md
    └── governed-evolution/
        ├── README.md
        ├── source-identity.md
        ├── trust-anchor.md
        ├── governance-view.md
        ├── residuals.md
        └── step12-final-seal.md
```

---

# Where to start

### Architecture

- [System boundary](architecture/system-boundary/ALLIS_SYSTEM_BOUNDARY.md)
- [State model overview](architecture/state-models/STATE_MODEL_OVERVIEW.md)
- [Trust and authority overview](architecture/trust-and-authority/TRUST_AND_AUTHORITY_OVERVIEW.md)
- [Deployment model overview](architecture/deployment-model/DEPLOYMENT_MODEL_OVERVIEW.md)

### Qualified baseline

- [Qualified baseline README](acceptance/qualified-baseline/README.md)
- [Qualified Baseline Manifest](acceptance/qualified-baseline/Qualified%20Baseline%20Manifest.md)

### Formal verification

- [Formal model](formal-verification/authorized-adoption/formal-model.md)
- [Theorem registry](formal-verification/authorized-adoption/theorem-registry.md)
- [Counterexample registry](formal-verification/authorized-adoption/counterexample-registry.md)

### Correspondence

- [Correspondence overview](correspondence/README.md)
- [Model to source](correspondence/authorized-adoption/model-to-source.md)
- [Source to runtime](correspondence/authorized-adoption/source-to-runtime.md)

### Evidence

- [Evidence overview](evidence/README.md)
- [Governed-evolution evidence](evidence/governed-evolution/README.md)
- [Source identity](evidence/governed-evolution/source-identity.md)
- [Trust anchor](evidence/governed-evolution/trust-anchor.md)
- [Governance view](evidence/governed-evolution/governance-view.md)
- [Residuals](evidence/governed-evolution/residuals.md)
- [Step-12 final seal](evidence/governed-evolution/step12-final-seal.md)

---

# What this repository currently supports

A defensible current description is:

> **ALLIS is a governed artificial-intelligence and location-intelligence platform with explicit state, trust, authority, evidence, and correspondence boundaries. Its bounded production authorized-adoption pathway has been formally specified, machine-adjudicated, mapped to sealed production source, and correspondence-verified at selected live fail-closed boundaries.**

For governed evolution specifically:

> **ALLIS implements a governed self-modification and authorized-adoption architecture in which candidate generation and evaluation remain separate from the independent authority required to adopt an exact change into production.**

These are bounded technical claims.

They are not claims of whole-system proof.

---

# What this repository does not claim

This repository does not claim that:

- ALLIS has completed whole-system formal verification;
- every ALLIS subsystem has been mathematically modeled;
- every claimed behavior has been empirically demonstrated;
- every theorem has been correspondence-verified;
- all production mutation is universally safe;
- runtime correspondence can never drift;
- the runtime independently creates its own private authorization authority;
- a passing evaluation automatically authorizes deployment;
- an AI-generated candidate can self-promote into production;
- ALLIS is a canonical open-ended Darwin Gödel Machine;
- ALLIS is artificial general intelligence; or
- a hypothesis becomes knowledge merely because the system generated it.

---

# Public documentation and private operations

This repository is designed to make technical claims reviewable without publishing operational secrets.

Public-safe records may include:

- architecture;
- formal objects;
- theorem status;
- counterexamples;
- source commit identities;
- non-sensitive hashes;
- public trust-anchor hashes;
- governance-object hashes;
- correspondence results;
- residuals;
- non-promotions; and
- final seal identities.

Private signing keys, credentials, tokens, sensitive authorization artifacts, exploit-relevant operational details, and private personal information should remain outside the public repository.

Transparency does not require publishing secrets.

---

# Relationship to deployment programs

ALLIS may be used by separate research, community, nonprofit, institutional, or deployment programs.

Those programs may provide use cases or governance environments, but they do **not** define the technical validation state of ALLIS.

This repository is the KTS technical record for the ALLIS platform itself.

---

# Project stewardship

**Kidd’s Technical Services**  
Mount Hope, West Virginia

ALLIS is an active research and engineering program.

Repository content should be interpreted according to its:

```text
status
evidence
version
source identity
validation level
scope
```
