# ALLIS system boundary

## Purpose

This document defines the current system boundary of **ALLIS — the Artificial Learning and Location Intelligence System** developed by Kidd's Technical Services.

It explains:

- what ALLIS is;
- what belongs inside the ALLIS architecture;
- what remains outside the ALLIS architecture;
- how ALLIS separates information, evidence, authority, and action;
- how privacy, identity, provenance, and governance constrain system behavior;
- how formal validation relates to the implemented system;
- how ALLIS relates to Ms. Allis, MountainShares, The Commons, Community Champions, and deployment projects.

This document describes the architecture in present tense. It does not reproduce the engineering history, audit chronology, or individual validation runs that support the current documentation.

Detailed acceptance, claim, measurement, formal-verification, correspondence, and evidence records are maintained separately in the repository.

---

## 1. What ALLIS is

ALLIS is a governed computational and knowledge architecture for artificial learning, location intelligence, evidence-aware reasoning, and controlled state transition.

It combines several forms of state, including:

- semantic and informational state;
- geographic and spatial state;
- temporal state;
- person-linked state;
- memory and provenance state;
- governance and authority state.

ALLIS is designed around a central principle:

> **State does not become authority merely because it exists.**

Information can be available to a computational process without becoming verified evidence, durable knowledge, authorized memory, public disclosure, or an approved system action.

For this reason, ALLIS separates reasoning from authority and separates authority from execution.

---

## 2. What ALLIS is not

ALLIS is not synonymous with every system, program, organization, or deployment that uses it.

### Ms. Allis

**Ms. Allis** is a governed analytical and advisory intelligence that can operate through ALLIS.

ALLIS is the underlying engineering and research platform. Ms. Allis is one intelligence-facing expression of that platform.

Ms. Allis does not independently create system authority merely because she can reason about a requested action.

### MountainShares and The Commons

**MountainShares** and **The Commons** are separate community, governance, and economic structures that can use ALLIS capabilities.

Community governance does not automatically become ALLIS technical authority, and ALLIS technical authority does not automatically become community governance authority.

### Community Champions

**Community Champions** are human participants in a governed stewardship and local-knowledge process.

Their roles can include:

- observation;
- training;
- demonstrated competency;
- field practice;
- governed contribution.

Community Champion status does not automatically create:

- system-administrator authority;
- institutional authority;
- government authority;
- authority to validate every local claim;
- authority to modify ALLIS.

### Deployment projects

Projects such as the **New River Gorge Safety & Heritage Mesh Pilot** are deployment and research contexts for ALLIS.

A deployment can exercise part of ALLIS, but no single deployment defines the complete ALLIS architecture.

---

## 3. Core boundary principles

ALLIS separates concepts that many software systems combine.

```text
information
    ≠ evidence

evidence
    ≠ claim

claim
    ≠ authority

authority
    ≠ execution

execution
    ≠ demonstrated correspondence
```

Three rules follow from this separation.

### State does not become authority merely because it exists

A record, memory, model output, configuration, or service does not gain authority simply because it is present.

### A transition requires authority for that transition

Evidence that one state exists or has completed does not automatically authorize the next state.

### Authority itself has provenance

ALLIS treats the origin, scope, and validity of authority as traceable state.

A compact representation is:

```text
Exists(state)  ⇏  Authorized(transition)

Observed(property)  ⇏  Proven(property)

Proven(formal_property)  ⇏  RuntimeCorrespondent(property)
```

These distinctions are foundational to the system boundary.

---

## 4. System boundary at a glance

ALLIS is best understood as a governed flow rather than as a single application stack.

```text
External information, research, GIS, community observations, and services
                              │
                              ▼
                 Governed intake and provenance
                              │
                              ▼
          Semantic, geographic, temporal, memory,
          person-linked, and governance state
                              │
                              ▼
                   Governed computation
                              │
                              ▼
                  Evidence-bearing results
                              │
                              ▼
                 Claim and authority evaluation
                              │
                ┌─────────────┴─────────────┐
                │                           │
                ▼                           ▼
        Authorized transition       Withhold or fail closed
                │
                ▼
        Governed committed state
        or governed external output
```

The exact implementation can use several services or components.

The architectural rule remains constant:

> **Computation alone does not create authority to commit, disclose, or mutate state.**

---

## 5. Governed state model

ALLIS works with several related forms of state.

### 5.1 Semantic and informational state

Semantic state represents meaning, retrieved knowledge, analytical context, and computational interpretation.

Semantic relevance does not automatically establish:

- truth;
- provenance;
- authority;
- permission to retain;
- permission to disclose;
- permission to act.

### 5.2 Geographic state

Geographic state represents place, spatial relationships, geographic context, and location-linked knowledge.

ALLIS treats place as part of the computational context rather than as a display layer added after reasoning.

A geographic relationship does not by itself prove a fact or grant authority over a place, organization, property, institution, or community.

### 5.3 Temporal state

Temporal state represents timing, lifecycle, recency, expiration, scheduling, and time-dependent validity.

A declared schedule or temporal rule is separate from evidence that the scheduled process executed.

### 5.4 Person-linked state

ALLIS treats person-linked or private information as a separately governed class of state.

Its use can depend on:

- verified identity;
- disclosure authority;
- provenance;
- scope;
- recipient;
- consent where applicable;
- lifecycle and temporal validity.

Protected state should remain unavailable when the required authority is absent.

### 5.5 Memory and provenance state

ALLIS does not treat memory as an unrestricted pool of reusable information.

The architecture associates memory and evidence with relevant provenance, scope, identity, temporal, and governance boundaries.

### 5.6 Governance and authority state

Governance state records whether a transition is:

- eligible;
- authorized;
- withheld;
- completed;
- unresolved;
- outside the current authority scope.

Governance state is separate from the substantive information that the system governs.

---

## 6. Identity, privacy, and person-linked information

ALLIS separates concepts that many applications combine.

```text
identity
≠ authentication
≠ authorization
≠ disclosure authority
≠ governance authority
≠ operation authority
```

An authenticated caller is not automatically authorized for every action.

Likewise, identifying the person associated with a record does not automatically authorize the system to disclose, reuse, or propagate that record.

The person-linked information boundary follows these principles:

- private state remains separate from common reasoning state;
- identity-bearing information is not ordinary public context;
- caller-supplied identity claims are not sufficient authority by themselves;
- disclosure scope and recipient scope remain separate from authentication;
- missing authority results in withholding or fail-closed behavior instead of inferred permission.

This boundary allows ALLIS to reason about people without treating identity as unrestricted computational context.

---

## 7. Trust and operational authority

ALLIS uses several trust and governance controls rather than one universal authorization check.

The architecture separates concerns such as:

- caller identity;
- constitutional or policy admission;
- boundary and policy enforcement;
- Guardian authority;
- operation intent;
- evidence and receipt generation;
- transition-specific authorization.

These controls are related, but they are not interchangeable.

For example:

- a caller can be authenticated and still lack authority for a governed operation;
- a policy condition can pass without granting unrelated mutation authority;
- successful execution does not automatically establish completion of a broader governance process;
- completion of one governed process does not automatically authorize the next process.

ALLIS therefore treats authority as scoped and transition-specific.

---

## 8. Governed computation

ALLIS distinguishes ordinary computation from governed computation.

A computational result can be:

- relevant;
- internally consistent;
- generated by a trusted service;
- supported by retrieved context;

and still lack authority to:

- become durable memory;
- become verified evidence;
- become public disclosure;
- modify protected state;
- trigger an external action.

Governed computation evaluates whether a proposed transition satisfies the relevant evidence, provenance, privacy, policy, and authority requirements before the result can cross into a protected state.

---

## 9. Governed modification

ALLIS includes a governed modification architecture that keeps proposed system changes separate from committed live state until defined governance conditions are satisfied.

The design uses concepts such as:

- staged evaluation;
- sandboxed processing;
- protected promotion boundaries;
- governance controls;
- rollback boundaries;
- transition-specific authorization.

A proposed modification is not the same as an authorized production modification.

The architectural requirement is:

```text
candidate change
      ↓
bounded evaluation
      ↓
governance review
      ↓
authorized promotion
      ↓
committed state
```

If the required authority is absent, the candidate should not be promoted merely because the technical process can perform the change.

Detailed validation of particular modification paths belongs in the repository's mathematics, formal-verification, correspondence, and evidence records rather than in this architectural definition.

---

## 10. Evidence, claims, and provenance

ALLIS treats evidence as part of the architecture rather than as documentation added after the fact.

A strong ALLIS claim should make it possible to determine:

- what evidence supports the claim;
- what source or runtime was examined;
- what scope the evidence covers;
- whether the evidence completed its required integrity process;
- what conclusions the evidence supports;
- what remains unresolved;
- what authority permitted the evidence-producing process.

This creates an important distinction:

> **Evidence can support a claim without authorizing an action.**

Likewise, an authorized process can execute without proving every proposition that the process was designed to examine.

The architecture therefore keeps evidence state and authority state separate.

---

## 11. Implementation, runtime, and correspondence

ALLIS documentation separates several engineering states.

```text
implemented source
≠ verified source
≠ declared configuration
≠ instantiated runtime
≠ observed behavior
≠ operational authority
```

A source file can contain a capability that is not active in the runtime.

A configuration can declare a service or authority path that is not currently instantiated.

A runtime observation can establish that a component exists without establishing that every dependent path uses that component.

A formal theorem can describe a valid model without establishing that the current implementation or runtime corresponds to that model.

This separation prevents architectural descriptions from being silently promoted into stronger implementation or runtime claims.

---

## 12. Validation boundary

ALLIS separates the architecture from the evidence used to validate a particular implementation of that architecture.

The architecture can define a required boundary before every part of that boundary has reached the same level of empirical or formal validation.

ALLIS therefore distinguishes among:

- **Implemented** — the mechanism exists in qualified source or defined architecture;
- **Observed** — a bounded inspection found a current configuration or runtime fact;
- **Demonstrated** — a behavior was exercised under a defined scope;
- **Formally specified** — a property has been expressed precisely enough for formal analysis;
- **Proven** — a theorem or formal property has been established within stated assumptions and scope;
- **Machine-checked** — a formal result has been checked by an appropriate verification method;
- **Source-correspondent** — the formal model or claim has been shown to map to qualified source;
- **Runtime-correspondent** — the claim has been shown to map to observed runtime within the audited scope;
- **Not proven** — available evidence does not establish the proposition;
- **Disproven** — evidence establishes that the proposition is false within the stated scope;
- **Outside audited scope** — the inquiry did not examine the proposition closely enough to support a conclusion.

These states are not interchangeable.

For example:

```text
implementation
    ≠ runtime observation

runtime observation
    ≠ formal proof

formal proof
    ≠ source correspondence

source correspondence
    ≠ runtime correspondence
```

A result applies only within the scope that its evidence supports.

Detailed validation status is maintained separately in the repository's acceptance, claims, measurements, mathematics, formal-verification, correspondence, and evidence records.

This separation allows the system-boundary document to remain a stable description of ALLIS while supporting evidence continues to mature.

---

## 13. Formal validation boundary

ALLIS uses formal analysis where the problem and available evidence support it.

Formal work can include:

- state-transition models;
- invariants;
- reachability analysis;
- authorization logic;
- provenance-chain properties;
- temporal-governance properties;
- graph and topology analysis;
- model checking;
- theorem proving;
- state-space mathematics where the structure is justified.

Formal proof establishes properties of a formal model under stated assumptions.

It does not, by itself, establish that the current implementation or runtime satisfies those assumptions.

For that reason, ALLIS treats proof-to-implementation correspondence as a separate research problem.

```text
formal model
    ↕
qualified source
    ↕
observed runtime
```

The strongest claim requires evidence that these layers correspond.

---

## 14. Ms. Allis boundary

Ms. Allis is an intelligence-facing layer that operates through governed ALLIS capabilities.

Ms. Allis can:

- reason over information available within the relevant scope;
- explain evidence and claims;
- support research and analysis;
- communicate system status when grounded in governed evidence;
- help people navigate information and services when authority permits.

Ms. Allis does not create system authority simply by reasoning about an action.

A conversational request is therefore not equivalent to authorization for a protected state transition.

---

## 15. Human and institutional authority

ALLIS supports human and institutional decision-making. It does not replace it.

Human observations can contribute evidence. Community knowledge can provide important context. Community Champions can support local stewardship and governed feedback.

The architecture preserves these distinctions:

```text
observation
≠ verified fact

local knowledge
≠ institutional authority

participation
≠ competency

competency
≠ unrestricted system authority

system evidence
≠ government or institutional decision authority
```

When a government agency, university, nonprofit organization, community organization, or other institution holds independent authority, that authority remains its own.

ALLIS can support the evidence process without absorbing that institution's legal, academic, regulatory, or organizational authority.

---

## 16. Deployment boundary

ALLIS can support multiple deployments without becoming defined by any one deployment.

A deployment can include:

- community information;
- geographic context;
- heritage interpretation;
- connectivity;
- research;
- evaluation;
- governed participation;
- local knowledge.

Planning, funding, authorization, installation, testing, and demonstrated outcomes remain separate states.

```text
planned
    ≠ funded

funded
    ≠ authorized

authorized
    ≠ installed

installed
    ≠ tested

tested
    ≠ demonstrated long-term outcome
```

This distinction allows ALLIS to support research and field deployment without overstating the maturity of a specific project.

---

## 17. New River Gorge pilot boundary

The **New River Gorge Safety & Heritage Mesh Pilot** is a practical deployment and research context for ALLIS.

The pilot can exercise elements of:

- place-based information;
- geographic state;
- heritage interpretation;
- community participation;
- governed feedback;
- connectivity;
- evaluation.

The pilot remains outside the definition of the core ALLIS platform.

Likewise, Mount Hope and any future Thurmond work remain deployment phases or use cases rather than definitions of ALLIS itself.

---

## 18. Public and research interface boundary

A public, university-facing, or community-facing interface should present governed ALLIS information without becoming an independent source of authority.

A suitable publication pattern is:

```text
ALLIS
   ↓
governed read-only publication boundary
   ↓
versioned publication state
   ↓
public or research interface
```

The interface should preserve uncertainty.

| Condition | Recommended display |
|---|---|
| Data is unavailable | **Unavailable** |
| A proposition is not established | **Not proven** |
| The inquiry did not cover the question | **Outside audited scope** |
| No current authority exists for an action | **Not authorized** |

Missing data should not automatically become:

- healthy;
- successful;
- proven;
- authorized;
- canonical.

The user interface is subordinate to the evidence and authority model. It does not manufacture authority because a user can select an action.

---

## 19. Relationship to the thesis

The ALLIS thesis and the KTS ALLIS technical documentation serve different purposes.

### The thesis

The thesis preserves the research lineage, theoretical development, mathematical ideas, and broader intellectual framework.

### The KTS ALLIS repository

The KTS repository describes the current engineering and research system.

### This document

This system-boundary document defines the present architectural boundary among:

- state;
- computation;
- evidence;
- authority;
- implementation;
- runtime;
- formal proof;
- correspondence;
- external systems and deployments.

When later qualified engineering evidence supersedes an older implementation description, the older thesis language remains research lineage rather than current system authority.

---

## 20. Research significance

ALLIS is both an engineering system and a research object.

The research questions extend beyond whether an artificial-intelligence system can generate a useful answer.

ALLIS asks questions such as:

- What makes information admissible for a specific use?
- How should provenance travel with computational state?
- How should person-linked state remain separate from common knowledge?
- How should geographic and temporal context affect meaning without automatically creating authority?
- How should a system distinguish observed behavior from formal proof?
- How can a formal claim be tied back to qualified source and observed runtime?
- How can community knowledge contribute without being mistaken for institutional authority?
- How can a computational system preserve uncertainty instead of converting uncertainty into confidence or permission?
- How can a system represent the provenance of authority itself?

These questions make the system boundary part of the research method rather than only an engineering diagram.

---

## 21. Related technical records

Detailed validation material is maintained separately from this architectural description.

The repository organizes those records into:

- **Acceptance** — qualified baselines and closeout records;
- **Claims** — claim definitions, status, and explicit nonclaims;
- **Measurements** — empirical protocols, metrics, and results;
- **Mathematics** — mathematical foundations, state spaces, invariants, and theorems;
- **Formal verification** — specifications, proofs, model checks, and counterexamples;
- **Correspondence** — model-to-source and source-to-runtime validation;
- **Evidence** — reproducibility records, validation bundles, and provenance;
- **Research** — research questions and future work.

This separation keeps the architecture stable while validation evidence and claim status continue to evolve.

---

## 22. Conclusion

ALLIS is a governed computational and knowledge architecture that separates information, evidence, claims, authority, and execution.

Its system boundary is defined by several commitments:

- semantic, geographic, temporal, person-linked, memory, and governance state remain distinct but interoperable;
- identity does not automatically create authorization;
- evidence does not automatically create authority;
- computation does not automatically create permission to commit, disclose, or mutate state;
- authority is scoped, transition-specific, and provenance-bound;
- formal proof is distinct from implementation and runtime correspondence;
- human and institutional authority remain external where those authorities properly belong;
- deployments use ALLIS but do not define the underlying platform.

The architecture follows one final rule:

> **Claims remain limited to the source, runtime, authority, evidence, and correspondence scopes that the supporting record actually establishes.**

That rule is not separate from ALLIS.

It is part of the system boundary itself.
