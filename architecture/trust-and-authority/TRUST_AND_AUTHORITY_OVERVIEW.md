# ALLIS trust and authority overview

## Purpose

This document defines the high-level trust and authority model of **ALLIS — the Artificial Learning and Location Intelligence System** developed by Kidd's Technical Services.

It describes how ALLIS distinguishes identity, authentication, authorization, disclosure authority, governance authority, and operation authority, and how those distinctions constrain protected state transitions.

This document is evidentiary in the sense that its architectural claims are limited to the qualified ALLIS baseline and the supporting validation record. It does not treat architectural definition as proof that every trust or authority path has reached the same level of implementation, runtime correspondence, or formal verification.

Detailed implementation, measurement, formal-verification, correspondence, and evidence records are maintained elsewhere in the repository.

---

## 1. Document status

**Document role:** Architectural baseline  
**Scope:** Trust, authority, and protected-transition model  
**Evidence basis:** Current qualified ALLIS architecture and supporting validation record  
**Mathematical status:** Architectural definitions only unless separately formalized  
**Runtime status:** Not inferred from architecture alone  

This document uses the following rule:

> **Authority must be established for the transition being performed. It is not inferred merely from identity, system state, prior completion, or technical capability.**

---

## 2. Trust and authority in ALLIS

ALLIS does not treat trust as a single permission granted to a user, service, or piece of information.

Instead, the architecture separates several questions:

```text
Who or what is making the request?
        ↓
What identity has been established?
        ↓
What action is being requested?
        ↓
What state, subject, or resource is affected?
        ↓
What policy and authority apply?
        ↓
Is the requested transition permitted?
```

This separation allows ALLIS to distinguish between knowing **who** is involved and determining **what that actor may do**.

A central architectural relationship is:

```text
identity
≠ authentication
≠ authorization
≠ disclosure authority
≠ governance authority
≠ operation authority
```

These concepts can interact, but they are not interchangeable.

---

## 3. Identity

### Architectural definition

Identity represents the relationship between an actor, subject, service, or other recognized entity and the state or request being evaluated.

Identity can be relevant to questions such as:

- Who is making the request?
- Whom does the information concern?
- Which subject is associated with a memory or record?
- Which service or process is attempting an operation?

### Evidence basis

Identity-aware processing is part of the qualified ALLIS architecture through person-linked state, authentication interfaces, subject relationships, disclosure controls, and protected-operation handling.

### Boundary of claim

Identity alone does not establish permission.

Knowing who an actor is does not determine whether that actor may:

- access protected state;
- disclose person-linked information;
- retain information;
- modify protected state;
- perform an external action.

---

## 4. Authentication

### Architectural definition

Authentication establishes whether a claimed caller or service identity has been sufficiently verified for the relevant interaction.

Authentication answers:

> **Who or what is making this request?**

It does not answer:

> **Is this request permitted?**

### Evidence basis

Authentication is part of the qualified ALLIS trust architecture through caller-identity and protected-access controls.

### Boundary of claim

Successful authentication does not automatically grant:

- disclosure authority;
- modification authority;
- governance authority;
- authority over another subject;
- authority for unrelated operations.

Authentication is therefore a prerequisite for some transitions, not a universal authorization state.

---

## 5. Authorization

### Architectural definition

Authorization determines whether an authenticated or otherwise recognized actor may perform a specific action within a defined scope.

Authorization can depend on:

- actor identity;
- subject or resource;
- requested operation;
- purpose;
- recipient;
- provenance;
- policy;
- temporal validity;
- other governance conditions.

Authorization is transition-specific.

The same actor can be authorized for one operation and not authorized for another.

### Evidence basis

Operation-specific authorization is part of the qualified ALLIS architecture through protected-transition, disclosure, promotion, and modification controls.

### Boundary of claim

Authorization should not be generalized beyond the scope in which it was established.

For example:

```text
authorized to read
    ≠ authorized to disclose

authorized to analyze
    ≠ authorized to retain

authorized to retain
    ≠ authorized to modify

authorized for one subject
    ≠ authorized for another subject
```

---

## 6. Disclosure authority

### Architectural definition

Disclosure authority determines whether protected information may be released to a particular recipient for a particular purpose and scope.

This is especially important for person-linked or otherwise restricted state.

Disclosure authority can depend on:

- subject identity;
- recipient;
- purpose;
- information scope;
- provenance;
- temporal validity;
- applicable consent or governance conditions.

### Evidence basis

Disclosure control is part of the qualified ALLIS architecture through person-linked state, privacy controls, recipient scope, and protected-use boundaries.

### Boundary of claim

Possession of information does not create authority to disclose it.

Likewise:

```text
available to computation
    ≠ available to recipient

authorized to analyze
    ≠ authorized to disclose
```

If disclosure authority is absent or unresolved, protected information should remain unavailable to the proposed recipient.

---

## 7. Governance authority

### Architectural definition

Governance authority determines whether a transition satisfies the applicable governance conditions of the ALLIS architecture.

Governance can apply to actions such as:

- promoting candidate state;
- retaining protected information;
- disclosing restricted information;
- modifying protected state;
- authorizing an external action.

Governance authority is not merely a record that a prior step occurred. It represents the authority applicable to the current transition.

### Evidence basis

Governance authority is part of the qualified ALLIS architecture through policy checks, protected-transition controls, promotion boundaries, and authority-aware state handling.

### Boundary of claim

Completion of one governed process does not automatically authorize another.

A prior state can establish eligibility or evidence without establishing successor authority.

The controlling principle is:

> **A transition requires authority for that transition.**

---

## 8. Operation authority

### Architectural definition

Operation authority determines whether a protected action may be executed.

This is the final distinction between the system being technically capable of performing an action and being permitted to perform it.

Examples of protected actions can include:

- committing state;
- modifying protected data;
- promoting candidate state;
- disclosing restricted information;
- triggering an external action.

### Evidence basis

Operation-specific authority is part of the qualified ALLIS architecture through governed computation and protected-transition controls.

### Boundary of claim

Technical capability is not equivalent to authority.

```text
can execute
    ≠ may execute
```

Likewise, evidence that an operation is possible does not itself authorize the operation.

---

## 9. Authority provenance

ALLIS treats authority as provenance-bearing state.

Authority should be traceable to questions such as:

- Who or what established the authority?
- What action does the authority cover?
- Which actor does it apply to?
- Which subject or resource does it concern?
- What purpose is permitted?
- Which recipient is permitted?
- When does the authority begin?
- When does it expire?
- Can it be revoked?
- What evidence supports its current validity?

This leads to a central architectural principle:

> **Authority itself has provenance.**

Authority should therefore not be inferred solely because a system component, record, request, or prior process exists.

---

## 10. Protected transitions

ALLIS applies trust and authority controls to transitions that can change the status, availability, or effect of governed state.

A simplified model is:

```text
candidate state or requested action
                │
                ▼
          identity context
                │
                ▼
        authentication where required
                │
                ▼
        policy / governance evaluation
                │
                ▼
        transition-specific authority
                │
        ┌───────┴────────┐
        ▼                ▼
   permit transition   withhold / fail closed
```

Protected transitions can include:

```text
temporary context
    → retained memory

candidate claim
    → promoted state

private state
    → authorized disclosure

candidate modification
    → committed state

computed recommendation
    → external action
```

The exact controls can differ by transition.

The architectural requirement is that protected transitions do not occur merely because the preceding computation produced a result.

---

## 11. Fail-closed behavior

### Architectural definition

ALLIS uses a fail-closed principle for protected transitions.

When required identity, authority, policy, provenance, or scope cannot be established, the protected transition should remain unavailable rather than being allowed by assumption.

### Evidence basis

Fail-closed handling is part of the qualified ALLIS architecture through protected-state and authority-boundary design.

### Boundary of claim

Fail closed does not mean that every uncertainty requires the same system response.

It means that missing authority must not be silently converted into permission for a protected transition.

In simplified form:

```text
authority established
    → transition may proceed within scope

authority absent or unresolved
    → protected transition withheld
```

---

## 12. Evidence and authority

ALLIS keeps evidence state separate from authority state.

Evidence can support a claim or decision without granting permission to act.

Likewise, authority can permit an action without making every factual proposition related to that action true.

This distinction can be expressed as:

```text
evidence
    ≠ authority

authority
    ≠ truth

execution
    ≠ proof
```

For example:

- evidence can support a recommendation without authorizing implementation;
- an authorized disclosure can still require accurate recipient and scope handling;
- successful execution does not prove that every broader architectural claim is true.

This separation prevents evidentiary confidence from being silently converted into operational permission.

---

## 13. External authority

ALLIS can interact with people and institutions that hold authority outside the computational system.

External authority can include:

- legal authority;
- regulatory authority;
- institutional authority;
- academic authority;
- organizational authority;
- community governance authority.

ALLIS can receive decisions, permissions, constraints, or evidence from external authorities without absorbing those authorities into the system itself.

Likewise, ALLIS technical authority does not automatically transfer into an external institution's governance domain.

The system can support a decision process without becoming the decision-maker of record.

---

## 14. Intelligence-facing services

An intelligence-facing service can reason about a requested action without possessing independent authority to perform it.

For ALLIS, this means that **Ms. Allis** can support analysis, explanation, and governed decision support while remaining subject to the same trust and authority boundaries as other system interactions.

A conversational instruction does not automatically become authorization for a protected transition.

The architectural distinction is:

```text
request
    ≠ authorization

reasoning
    ≠ governance approval

recommendation
    ≠ external action
```

---

## 15. Trust, authority, and validation

This document defines the architectural trust and authority model.

It does not claim that every trust path has the same implementation or validation status.

The repository separates:

```text
architectural requirement
    ≠ implemented control
    ≠ observed runtime behavior
    ≠ formal property
    ≠ verified correspondence
```

Detailed status belongs in:

- `acceptance/` — qualified system baselines;
- `claims/` — explicit trust and authority claims;
- `measurements/` — empirical protocols and results;
- `mathematics/` — formal definitions and invariants;
- `formal-verification/` — proofs, model checks, and counterexamples;
- `correspondence/` — model-to-source and source-to-runtime validation;
- `evidence/` — supporting provenance and validation artifacts.

This separation allows the architectural trust model to remain stable while evidence about particular implementations continues to mature.

---

## 16. Relationship to the state model

The trust and authority model operates across the state domains defined in `architecture/state-models/STATE_MODEL_OVERVIEW.md`.

For example:

- semantic state can be relevant without being authoritative;
- geographic state can establish context without establishing jurisdiction;
- temporal state can affect whether an authority remains valid;
- person-linked state can require disclosure and recipient controls;
- memory and provenance state can preserve the origin and scope of authority;
- governance and authority state can determine whether a protected transition may proceed.

Trust and authority therefore function as cross-cutting constraints on state use rather than as a separate content domain.

---

## 17. Summary

The ALLIS trust and authority model separates:

- identity;
- authentication;
- authorization;
- disclosure authority;
- governance authority;
- operation authority.

These concepts interact, but they do not collapse into one another.

The model can be summarized as:

> **ALLIS does not ask only whether a system can perform an action. It asks whether the relevant identity, evidence, policy, scope, and authority permit that specific transition.**

Three rules govern the model:

> **State does not become authority merely because it exists.**

> **A transition requires authority for that transition.**

> **Authority itself has provenance.**
