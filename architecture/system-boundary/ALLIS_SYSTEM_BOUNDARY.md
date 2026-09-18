# ALLIS system boundary

## Purpose

This document defines the architectural boundary of **ALLIS — the Artificial Learning and Location Intelligence System** developed by Kidd's Technical Services.

The repository `README.md` provides the broader description of ALLIS, its research program, validation model, and relationships to other programs. This document has a narrower purpose: it defines where the ALLIS computational boundary begins and ends.

It addresses four questions:

- What is inside the ALLIS boundary?
- What remains outside the ALLIS boundary?
- What can cross the boundary?
- What authority is required when state crosses that boundary?

---

## 1. Boundary definition

ALLIS is a governed computational platform for artificial learning, location intelligence, evidence-aware reasoning, and controlled state transition.

Its boundary includes the mechanisms that:

- receive, construct, and relate computational state;
- preserve provenance and scope;
- evaluate admissibility, policy, and authority;
- perform governed computation;
- control retention, promotion, disclosure, modification, and external action;
- preserve evidence about protected transitions.

The boundary is functional rather than organizational. A component is inside the ALLIS boundary because of the role it performs in governed computation, not because it belongs to a particular deployment, organization, container, or user interface.

A central rule applies throughout the architecture:

> **State does not become authority merely because it exists.**

---

## 2. What is inside the ALLIS boundary

The ALLIS boundary contains the computational mechanisms that represent state, evaluate its permitted use, and control protected transitions.

### State

ALLIS can represent and relate several forms of state, including:

- semantic and informational state;
- geographic and spatial state;
- temporal state;
- governed memory;
- person-linked state;
- provenance state;
- governance and authority state.

These forms of state can interact, but they are not interchangeable.

For example:

- a geographic relationship does not automatically establish truth;
- a memory item does not automatically become verified evidence;
- a person-linked record does not automatically become available for general reasoning;
- an existing governance state does not automatically authorize the next transition.

### Governed processing

The boundary includes processing used to:

- retrieve and reason over information;
- evaluate state and context;
- apply admissibility and policy checks;
- enforce protected transition rules;
- support governed modification;
- generate or preserve evidence and receipts.

### Trust and safety controls

The boundary also includes controls used to determine whether protected state may be used or changed, including:

- identity and caller-authentication interfaces;
- authorization;
- disclosure and recipient scope;
- provenance requirements;
- operation-specific authority;
- privacy and safety review where applicable;
- fail-closed handling when required authority is absent.

These mechanisms can span multiple services. The system boundary is defined by their function and authority relationships, not by a single runtime topology.

---

## 3. What is outside the ALLIS boundary

ALLIS interacts with people, organizations, governance systems, and deployment environments that remain outside the core computational boundary.

These can include:

- human users and contributors;
- community governance structures;
- universities and research partners;
- government agencies;
- nonprofit and commercial organizations;
- field deployments and pilot programs.

External actors can provide information, exercise their own authority, receive outputs, or use ALLIS capabilities without becoming part of the ALLIS computational architecture.

Their legal, institutional, academic, regulatory, community, or organizational authority remains external to ALLIS.

Likewise, ALLIS technical authority does not automatically transfer into those external governance domains.

**Ms. Allis** is an intelligence-facing service that operates through ALLIS. She does not independently create system authority and should not be treated as synonymous with the full ALLIS platform.

---

## 4. Boundary-crossing rules

Information and actions can cross an ALLIS boundary only under the controls appropriate to the transition.

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

Incoming information must retain enough provenance and scope to support its intended use.

Availability to the system does not automatically make information verified, authoritative, or reusable for every purpose.

### Computational result → evidence

A result does not become verified evidence solely because ALLIS produced it.

Generated analysis, observed evidence, and formally supported claims remain distinct.

### Person-linked state → permitted use

Person-linked or private information is subject to the applicable identity, disclosure, recipient, scope, and lifecycle controls.

If required authority is absent, the protected state should remain unavailable.

### Candidate change → committed state

A proposed modification must pass the applicable governance and promotion controls before it can affect protected live state.

The technical ability to make a change is not the same as authority to make that change.

### Evidence → action

Evidence can support a decision without independently authorizing the decision.

Authority to act remains a separate state.

---

## 5. Authority boundary

ALLIS separates identity from authority.

```text
identity
≠ authentication
≠ authorization
≠ disclosure authority
≠ operation authority
```

**Authentication** establishes who or what is making a request.

**Authorization** establishes whether that actor may perform a specific action.

**Disclosure authority** establishes whether protected information may be released to a particular recipient for a particular purpose.

**Operation authority** establishes whether a protected state transition may occur.

These relationships are scoped and transition-specific.

As a result:

- an authenticated caller can still lack authority for a protected operation;
- a satisfied policy condition does not grant unrelated authority;
- completion of one governed process does not automatically authorize another;
- authority held by an external institution remains external to ALLIS.

Where required authority is absent or unresolved, the protected transition should remain unavailable rather than being inferred from context.

---

## 6. Architecture and validation boundary

The ALLIS architecture and the evidence used to validate a particular implementation are related but separate.

ALLIS distinguishes:

```text
architecture
≠ implementation
≠ observed runtime
≠ formal proof
≠ implementation correspondence
```

An architectural requirement can exist before every implementation path has reached the same level of validation.

Likewise:

- an implemented capability can exist without current runtime evidence;
- a runtime observation can establish a bounded fact without establishing a universal architectural claim;
- a formal proof can establish a property of a defined model without proving that the current source or runtime corresponds to that model.

Detailed validation status is maintained elsewhere in the repository, including:

- `acceptance/`
- `claims/`
- `measurements/`
- `mathematics/`
- `formal-verification/`
- `correspondence/`
- `evidence/`

Keeping these records separate allows this document to remain a stable description of the ALLIS architecture while implementation evidence, formal results, and correspondence findings continue to mature.

---

## 7. Boundary summary

The ALLIS boundary contains the computational mechanisms that:

- represent and relate governed state;
- preserve provenance and scope;
- evaluate identity, policy, and authority;
- perform governed computation;
- control protected state transitions;
- preserve evidence about those transitions.

It does not absorb the authority of the people, institutions, communities, or deployment environments that interact with it.

The boundary can be summarized as:

> **ALLIS may compute over state, but computation alone does not authorize retention, disclosure, promotion, modification, or external action. Those transitions require the evidence and authority appropriate to their scope.**
