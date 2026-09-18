# ALLIS system boundary

## Purpose

This document defines the architectural boundary of **ALLIS — the Artificial Learning and Location Intelligence System** developed by Kidd's Technical Services.

For the broader description of ALLIS, its research program, validation model, and related repositories, see the repository `README.md`.

This document focuses only on:

- what is inside the ALLIS computational boundary;
- what remains outside that boundary;
- what kinds of state cross the boundary;
- which controls govern those transitions;
- where authority remains external to ALLIS.

---

## 1. Boundary definition

ALLIS is the Kidd's Technical Services computational platform that governs the movement of information among semantic, geographic, temporal, memory, person-linked, provenance, and authority-aware state.

The ALLIS boundary includes the mechanisms that:

- receive or construct computational state;
- preserve provenance and scope;
- evaluate admissibility and authority;
- perform governed computation;
- control promotion, retention, disclosure, or mutation;
- produce evidence about those transitions.

The boundary does not include every organization, person, deployment, or governance body that uses ALLIS.

A central rule applies throughout the architecture:

> **State does not become authority merely because it exists.**

---

## 2. What is inside the ALLIS boundary

The ALLIS boundary includes the computational mechanisms responsible for representing state, evaluating authority, and controlling protected transitions.

### State representation

ALLIS represents and relates several kinds of state, including:

- semantic and informational state;
- geographic and spatial state;
- temporal state;
- governed memory;
- person-linked state;
- provenance state;
- governance and authority state.

These forms of state can interact, but they are not interchangeable.

A geographic relationship does not automatically establish truth.  
A memory item does not automatically become verified evidence.  
A person-linked record does not automatically become available for general reasoning.  
A governance state does not automatically authorize the next transition.

### Governed processing

ALLIS includes mechanisms for:

- retrieval and reasoning;
- state evaluation;
- admissibility checks;
- policy and constitutional checks;
- protected state transitions;
- governed modification;
- evidence and receipt generation.

### Trust controls

The ALLIS boundary also includes controls for:

- identity and caller authentication interfaces;
- authorization;
- disclosure scope;
- recipient scope;
- protected-operation authority;
- fail-closed handling when required authority is absent.

These mechanisms can be implemented across several services. The system boundary is defined by their function and authority relationships, not by one container, process, or deployment topology.

---

## 3. What is outside the ALLIS boundary

Several related systems, programs, people, and institutions interact with ALLIS but remain outside the core computational boundary.

### Ms. Allis

**Ms. Allis** is a governed analytical and advisory intelligence that can operate through ALLIS.

Ms. Allis is not the entire ALLIS platform and does not independently create system authority merely because she can reason about a requested action.

### MountainShares and The Commons

**MountainShares** and **The Commons** are separate community, governance, and economic structures that can use ALLIS capabilities.

Their governance authority does not automatically become ALLIS technical authority, and ALLIS technical authority does not automatically become community governance authority.

### Community Champions

**Community Champions** are human participants in a governed stewardship and local-knowledge process.

Their roles can include:

- observation;
- training;
- demonstrated competency;
- field practice;
- governed contribution.

Community Champion status does not automatically create system-administrator, institutional, or government authority.

### Institutions

Universities, governments, nonprofits, businesses, and other institutions retain their own legal, academic, regulatory, and organizational authority.

ALLIS can support evidence and decision-making without absorbing that authority.

### Deployments

Projects such as the **New River Gorge Safety & Heritage Mesh Pilot** are deployment and research contexts for ALLIS.

A deployment can exercise part of ALLIS, but no single deployment defines the complete ALLIS architecture.

---

## 4. Boundary-crossing rules

Information can cross an ALLIS boundary only under the controls appropriate to the transition.

The architecture distinguishes:

```text
information
    ≠ evidence

evidence
    ≠ claim

claim
    ≠ authority

authority
    ≠ execution
```

### External information → computational state

Incoming information should retain enough provenance and scope to support its intended use.

Being available to the system does not automatically make information verified, authoritative, or reusable for every purpose.

### Computational result → evidence

A result does not become verified evidence solely because ALLIS produced it.

The system must preserve the distinction between generated analysis, observed evidence, and formally supported claims.

### Person-linked state → recipient-specific use

Person-linked or private information requires the applicable identity, disclosure, recipient, scope, and lifecycle authority.

If the required authority is absent, the protected state should remain unavailable.

### Candidate change → committed state

A proposed modification must pass the applicable governance and promotion controls before it can affect protected live state.

The ability to make a change is not the same as authority to make that change.

### Evidence → action

Evidence can support a decision without independently authorizing the decision.

The authority to act remains a separate state.

---

## 5. Authority boundary

ALLIS distinguishes identity from authority.

```text
identity
≠ authentication
≠ authorization
≠ disclosure authority
≠ operation authority
```

**Authentication** answers who or what is making a request.

**Authorization** answers whether that actor may perform a specific action.

**Disclosure authority** answers whether protected information may be released to a particular recipient for a particular purpose.

**Operation authority** answers whether a protected state transition may occur.

These relationships are scoped and transition-specific.

A caller can therefore be authenticated and still lack authority for a protected operation.

A policy condition can be satisfied without granting unrelated authority.

A completed process does not automatically authorize the next process.

Where the required authority is absent or unresolved, the protected transition should remain unavailable rather than being inferred from context.

Authority held by an external institution remains external to ALLIS.

---

## 6. Evidence and validation boundary

The system architecture and the evidence used to validate a particular implementation are separate concerns.

ALLIS distinguishes:

```text
architecture
≠ implementation
≠ observed runtime
≠ formal proof
≠ implementation correspondence
```

An architectural requirement can exist before every implementation path has reached the same level of validation.

An implemented capability can exist without current runtime evidence.

A runtime observation can establish a bounded fact without establishing a universal architectural claim.

A formal proof can establish a property of a defined model without proving that the current implementation or runtime corresponds to that model.

For that reason, ALLIS separates validation into distinct levels such as:

- implemented;
- observed;
- demonstrated;
- formally specified;
- proven;
- machine-checked;
- source-correspondent;
- runtime-correspondent.

These states are not interchangeable.

Detailed claim status, mathematical results, runtime findings, and validation evidence are maintained separately in the repository under:

- `acceptance/`
- `claims/`
- `measurements/`
- `mathematics/`
- `formal-verification/`
- `correspondence/`
- `evidence/`

This separation keeps the system-boundary document stable while the evidence supporting individual claims continues to mature.

---

## 7. Boundary summary

The ALLIS boundary contains the computational mechanisms that:

- represent and relate governed state;
- preserve provenance and scope;
- evaluate identity, policy, and authority;
- perform governed computation;
- control protected state transitions;
- preserve evidence about those transitions.

It does not absorb the authority of the people, communities, institutions, or deployment programs that interact with it.

The boundary can be summarized as:

> **ALLIS may compute over state, but computation alone does not authorize retention, disclosure, promotion, modification, or external action. Those transitions require the evidence and authority appropriate to their scope.**
