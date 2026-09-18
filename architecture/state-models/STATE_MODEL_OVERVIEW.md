# ALLIS state model overview

## Purpose

This document defines the high-level state model of **ALLIS — the Artificial Learning and Location Intelligence System** developed by Kidd's Technical Services.

It describes the major classes of state represented in the current ALLIS architectural baseline, the relationships among those classes, and the rules that govern movement between them.

This document is evidentiary in the sense that its architectural claims are limited to the qualified ALLIS baseline and the supporting validation record. It does not treat architectural definition as proof of implementation, runtime correspondence, or mathematical completeness.

Detailed implementation, measurement, mathematical, formal-verification, and correspondence records are maintained elsewhere in the repository.

---

## 1. Document status

**Document role:** Architectural baseline  
**Scope:** High-level state model  
**Evidence basis:** Current qualified ALLIS architecture and supporting validation record  
**Mathematical status:** Architectural definitions only unless separately formalized  
**Runtime status:** Not inferred from architecture alone  

This document uses the following rule:

> **A state model can be architecturally defined before every part of that model has reached the same level of implementation, runtime, or formal validation.**

Accordingly, each state class below is treated as an architectural object whose implementation and correspondence status must be established separately.

---

## 2. State in ALLIS

ALLIS treats state as more than stored data.

A state can describe:

- what information means;
- where it applies;
- when it is valid;
- whom it concerns;
- where it came from;
- what authority governs its use.

The current architectural baseline recognizes six major state domains:

1. semantic and informational state;
2. geographic and spatial state;
3. temporal state;
4. person-linked state;
5. memory and provenance state;
6. governance and authority state.

These domains can interact, but they are not interchangeable.

For example:

- semantic relevance does not establish geographic truth;
- geographic proximity does not establish authority;
- a memory item does not automatically become verified evidence;
- person-linked information does not automatically become available for general use;
- a valid computation does not automatically authorize a protected transition.

The state model therefore separates **what the system represents** from **what the system is permitted to retain, disclose, promote, modify, or act on**.

---

## 3. High-level model

At the architectural level, ALLIS state can be represented as:

```text
┌───────────────────────────────────────────────┐
│               ALLIS governed state            │
├───────────────────────────────────────────────┤
│ Semantic / informational state                │
│ Geographic / spatial state                    │
│ Temporal state                                │
│ Person-linked state                           │
│ Memory / provenance state                     │
└───────────────────────────────────────────────┘
                     │
                     ▼
        Governance / authority state
          constrains protected use
```

Governance and authority state is cross-cutting. It does not function as an ordinary content layer. It constrains whether state from the other domains can be retained, disclosed, promoted, modified, or used for external action.

A simplified transition model is:

```text
semantic ───────┐
geographic ─────┤
temporal ───────┤
person-linked ──┼──► governed computation ───► candidate result
memory/prov. ───┘                                 │
                                                  ▼
                                      governance / authority
                                                  │
                              ┌───────────────────┴───────────────────┐
                              ▼                                       ▼
                     permitted transition                     withhold / fail closed
```

This diagram describes the architectural relationship among state classes. It does not imply that each class is implemented as one physical store, one service, or one mathematical object.

---

## 4. Semantic and informational state

### Architectural definition

Semantic and informational state represents meaning, context, retrieved information, analytical relationships, and computational interpretation.

It can include:

- text and document meaning;
- concepts and entities;
- vector or embedding representations;
- retrieved context;
- inferred relationships;
- analytical outputs.

Semantic state supports questions such as:

- What does this information mean?
- Which concepts are related?
- What information is relevant to the current task?
- What interpretation is supported by the available context?

### Evidence basis

Semantic and informational state is part of the qualified ALLIS architecture through the system's reasoning, retrieval, memory, and knowledge-processing design.

### Boundary of claim

Semantic relevance does not by itself establish that a proposition is true, verified, current, authoritative, or permitted for every use.

This document does not assign one universal mathematical representation to semantic state. Formal representations belong in `mathematics/` and `formal-verification/`.

---

## 5. Geographic and spatial state

### Architectural definition

Geographic and spatial state represents place, location, distance, topology, spatial relationships, and location-linked context.

It can include:

- coordinates;
- mapped features;
- spatial relationships;
- route and proximity relationships;
- place identifiers;
- location-linked observations;
- geographic context associated with other information.

Geographic state supports reasoning about **where** information applies and how place changes the meaning or relevance of other state.

### Evidence basis

Geographic and spatial state is part of the qualified ALLIS architecture through its location-intelligence and place-aware design.

### Boundary of claim

A spatial relationship does not by itself establish:

- ownership;
- jurisdiction;
- institutional authority;
- factual correctness;
- permission to act.

This architectural definition does not establish one canonical mathematical model for all geographic state or prove runtime correspondence for every spatial path.

---

## 6. Temporal state

### Architectural definition

Temporal state represents time, sequence, duration, recency, lifecycle, scheduling, expiration, and time-dependent validity.

It can include:

- timestamps;
- effective dates;
- observation periods;
- expiration conditions;
- retention periods;
- scheduled events;
- temporal relationships among state changes.

Temporal state allows ALLIS to distinguish information that:

- was valid at one time;
- remains current;
- has expired;
- is scheduled for future use;
- requires re-evaluation because validity depends on time.

### Evidence basis

Temporal state is part of the qualified ALLIS architecture through lifecycle, scheduling, retention, and time-dependent state handling.

### Boundary of claim

A declared temporal rule or schedule is not evidence that the corresponding process executed.

Runtime execution and temporal correspondence must be established separately.

---

## 7. Person-linked state

### Architectural definition

Person-linked state represents information associated with an identifiable person or subject.

It can include:

- identity relationships;
- subject-specific memory;
- permissions or consent conditions;
- disclosure restrictions;
- recipient scope;
- person-specific provenance.

Person-linked state is not treated as ordinary shared context.

Its permitted use can depend on:

- verified identity;
- authorization;
- disclosure authority;
- purpose;
- recipient;
- provenance;
- lifecycle and temporal validity.

### Evidence basis

Person-linked state is part of the qualified ALLIS architecture through identity-aware, privacy, memory, and disclosure-control design.

### Boundary of claim

Information about a person is not the same as authority to use or disclose that information.

This document defines the architectural class. It does not claim that every person-linked path has current runtime correspondence unless separately demonstrated.

---

## 8. Memory and provenance state

### Architectural definition

Memory and provenance state represents retained information together with the context required to understand where that information came from and how it may be used.

Relevant provenance can include:

- source;
- time of acquisition;
- transformation history;
- scope;
- subject relationship;
- evidence lineage;
- validation status;
- authority context.

ALLIS does not treat memory as an unrestricted pool of reusable information.

A retained item can remain subject to limits on:

- purpose;
- disclosure;
- recipient;
- age;
- confidence;
- source authority;
- governance status.

### Evidence basis

Memory and provenance state is part of the qualified ALLIS architecture through governed memory, evidence lineage, and provenance-aware processing.

### Boundary of claim

Retention does not automatically mean promotion into trusted, verified, or authoritative state.

A remembered item can remain useful while still carrying unresolved provenance, validation, or authority limits.

---

## 9. Governance and authority state

### Architectural definition

Governance and authority state represents whether a protected use or transition is permitted within a defined scope.

It can describe whether a transition is:

- eligible;
- authorized;
- withheld;
- completed;
- unresolved;
- outside the current authority scope.

Authority state can also represent the provenance of authority itself.

Relevant questions include:

- Who or what granted the authority?
- What action does the authority cover?
- Which subject, recipient, or resource does it apply to?
- When is the authority valid?
- Has the authority expired or been revoked?
- Does it permit retention, disclosure, modification, or external action?

### Evidence basis

Governance and authority state is part of the qualified ALLIS architecture through its trust, authorization, disclosure, promotion, and protected-transition model.

### Boundary of claim

Governance and authority state is cross-cutting. It is not simply another content store.

The architectural rule is:

> **Authority is state, but not all state is authority.**

Authority for one operation does not imply authority for another.

---

## 10. Relationships among state domains

ALLIS state domains are designed to interact without losing their individual constraints.

A single computational task can involve several state classes at once.

```text
semantic state
    +
geographic state
    +
temporal state
    +
person-linked state
    +
memory/provenance state
    ↓
governed computation
    ↓
candidate result
    ↓
governance/authority evaluation
    ↓
permitted use, retention, disclosure, modification, or action
```

The presence of several state classes in one computation does not merge their rules.

For example:

- semantic relevance does not override privacy;
- geographic context does not override institutional authority;
- temporal urgency does not create authorization;
- person-linkage does not imply disclosure permission;
- provenance does not automatically make a claim true;
- authority for one transition does not imply authority for another.

---

## 11. State transitions

ALLIS distinguishes state from state transition.

A **state** describes what exists at a given point in the system.

A **transition** describes a change in how that state is classified, retained, disclosed, promoted, modified, or used.

Examples include:

```text
external information
    → computational state

computational state
    → candidate claim

candidate claim
    → verified evidence

temporary context
    → retained memory

private state
    → authorized disclosure

candidate modification
    → committed state
```

Protected transitions are not assumed to be automatic.

A protected transition can depend on:

- provenance;
- identity;
- authorization;
- policy satisfaction;
- recipient scope;
- temporal validity;
- evidence;
- governance approval.

If the required conditions are absent, the transition should remain unavailable, withheld, or unresolved.

---

## 12. State and evidence status

ALLIS keeps state status separate from evidence status.

A state can be:

- represented but not verified;
- observed but not proven;
- retained but not authoritative;
- authoritative for one purpose but not another;
- valid within one scope but not transferable to another.

This distinction supports the repository's validation model.

In simplified form:

```text
represented
    ≠ verified

verified
    ≠ authorized

authorized
    ≠ executed

executed
    ≠ universally valid
```

The state model therefore supports evidence-aware reasoning without treating every represented state as a settled fact.

---

## 13. Mathematical formalization

This document defines architectural state classes.

It does not require each class to use the same mathematical structure.

Depending on the research question, state can later be modeled using:

- vectors;
- graphs;
- temporal structures;
- relational models;
- probabilistic models;
- logical state machines;
- general state spaces;
- Hilbert-space structures where mathematically justified;
- other formal representations.

The mathematical form of a state must be established by the repository's mathematics and formal-verification work.

Architectural naming alone does not prove that a state has a particular mathematical structure.

---

## 14. Relationship to the repository

This document defines the architectural state classes.

Related work is maintained separately:

- `architecture/trust-and-authority/` — how authority governs protected state transitions;
- `architecture/deployment-model/` — how state models are instantiated in deployments;
- `acceptance/` — which system baseline is qualified;
- `claims/` — what is claimed about state behavior;
- `measurements/` — how state behavior is measured;
- `mathematics/state-spaces/` — mathematical representations of state;
- `mathematics/invariants/` — properties expected to hold across transitions;
- `formal-verification/` — proofs, model checks, and counterexamples;
- `correspondence/` — whether architectural and formal state models match source and runtime;
- `evidence/` — provenance and validation artifacts.

This separation keeps the architectural model readable while preserving evidentiary traceability.

---

## 15. Summary

The current ALLIS architectural baseline recognizes six major state domains:

- semantic and informational;
- geographic and spatial;
- temporal;
- person-linked;
- memory and provenance;
- governance and authority.

These domains interact without becoming interchangeable.

The model can be summarized as:

> **ALLIS represents what information means, where it applies, when it is valid, whom it concerns, where it came from, and whether a protected transition involving that state is authorized.**

The governing rule remains:

> **State does not become authority merely because it exists.**
