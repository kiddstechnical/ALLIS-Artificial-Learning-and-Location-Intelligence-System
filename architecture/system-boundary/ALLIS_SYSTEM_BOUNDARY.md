# ALLIS system boundary

## Current architecture, authority model, evidence scope, and validation limits

**System:** ALLIS — Artificial Learning and Location Intelligence System  
**Organization:** Kidd's Technical Services  
**Document type:** Present-state technical and research boundary  
**Evidence reviewed through:** September 17, 2026  

### Qualified engineering source anchor

- **Branch:** `remediation/bbb-fail-closed-20260830T212059Z`
- **HEAD:** `35f1aa5586e1a23e1ab88f4d757c451b44506893`
- **Tree:** `36dd9f2425db4b23bacfce1cb258603cace25f1b`

> This document describes the current ALLIS system boundary. It is not a development history, a deployment certificate, or a claim that every subsystem has reached the same level of validation.

---

## Abstract

ALLIS is a governed computational and knowledge architecture developed by Kidd's Technical Services. It combines semantic, geographic, temporal, person-linked, memory, provenance, and governance state while keeping information, evidence, claims, authority, and system action separate.

The core design principle is simple:

> **State does not become authority merely because it exists.**

Information can exist without being verified. A claim can be well supported without authorizing an action. A caller can be authenticated without being authorized for a specific transition. A mathematical result can be valid within its formal scope without yet corresponding to the current runtime.

ALLIS therefore uses several evidence and validation levels instead of one pass/fail label. The engineering record distinguishes what is implemented, what has been observed or demonstrated, what has been formally specified or proven, and what has been shown to correspond to qualified source or runtime behavior.

This document defines the present ALLIS boundary. It explains what belongs to ALLIS, what remains outside it, how major trust and governance boundaries work, what current evidence supports, and what remains unresolved.

---

## 1. Document status and evidence basis

This document presents the current system boundary in present tense.

The engineering history is used as evidence. 

The current documentation rule is:

```text
development evidence
        ↓
supports present claims
        ↓
present-state documentation
```

The document does not promote a claim because it appears later in a transcript or because a script contains an expected result.

A current claim must be supported by the strongest applicable evidence, including:

1. qualified source identity;
2. execution status;
3. evidence integrity or seal status;
4. predecessor and successor relationships;
5. runtime observation when required;
6. formal acceptance state;
7. later correspondence evidence.

A prepared procedure is not an executed result.  
An executed result is not automatically an accepted authority state.  
A historical deployment is not automatically the current runtime.

---

## 2. How to read this document

ALLIS uses several evidence labels. Each label answers a different question.

| Evidence level | Meaning |
|---|---|
| **Implemented** | The mechanism exists in qualified source or in the defined architecture. |
| **Observed** | A bounded inspection found a current configuration or runtime fact. |
| **Demonstrated** | A behavior was exercised under a defined scope. |
| **Formally specified** | A property has been expressed precisely enough for formal analysis. |
| **Proven** | A theorem or formal property has been established within stated assumptions and scope. |
| **Machine-checked** | A formal result has been checked by an appropriate formal method or verification procedure. |
| **Source-correspondent** | The formal model or claim has been shown to map to qualified source. |
| **Runtime-correspondent** | The claim has been shown to map to observed runtime within the audited scope. |
| **Not proven** | The available evidence does not establish the proposition. This does not mean the proposition is false. |
| **Disproven** | Evidence establishes that the proposition is false within the stated scope. |
| **Outside audited scope** | The inquiry did not examine the proposition closely enough to support a conclusion. |

Authority uses a separate vocabulary:

- **Authorized**
- **Not authorized**
- **Executed**
- **Not executed**
- **Open**
- **Closed**
- **Unresolved**

These labels should not be reduced to a generic pass/fail status.

---

## 3. Key terms

### Qualified source

The **qualified source** is the source state that the current evidence record treats as the engineering anchor for a claim.

### Provenance

**Provenance** records where information, evidence, authority, or a state transition came from.

### Authority

**Authority** defines what a person, service, or governed process may do within a specific scope.

### Correspondence

**Correspondence** shows that a formal or architectural claim maps to the implementation or runtime that the claim describes.

### Bounded result

A **bounded result** applies only to the source, runtime surface, theorem scope, or inquiry that was examined.

### Fail closed

A process **fails closed** when missing or unresolved authority prevents a protected transition instead of allowing the transition by default.

---

## 4. What ALLIS is

ALLIS is the Kidd's Technical Services engineering and research platform for governed computation, knowledge, evidence, location intelligence, and state transition.

ALLIS is designed to:

- represent information together with provenance, scope, and governance context;
- combine semantic and geographic reasoning without treating either as self-authorizing;
- distinguish public or common state from person-linked or restricted state;
- preserve evidence about how claims and system states were produced;
- separate identity from authorization;
- separate observation from proof;
- separate proof from implementation correspondence;
- govern high-consequence transitions before they affect committed state.

ALLIS is therefore more than a retrieval system, chatbot, GIS application, or workflow engine. Its defining feature is the relationship among **state, evidence, provenance, authority, and transition**.

---

## 5. What ALLIS is not

Several related systems and programs interact with ALLIS but remain outside the core ALLIS definition.

### Ms. Allis

**Ms. Allis** is a governed analytical and advisory intelligence that can operate through ALLIS.

Ms. Allis is not the entire ALLIS platform.

ALLIS provides the computational, evidence, state, and governance environment. Ms. Allis is one intelligence-facing expression of that environment.

### MountainShares and The Commons

**MountainShares** and **The Commons** are separate governance, community, and economic structures that can use ALLIS services or evidence.

Their community or economic authority does not automatically become ALLIS system authority. ALLIS technical authority does not automatically become community governance authority.

### Community Champions

**Community Champions** are human participants in a governed stewardship and local-knowledge process.

The model can support:

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

The **New River Gorge Safety & Heritage Mesh Pilot** and related Mount Hope or future Thurmond work are deployment and research contexts for ALLIS.

A deployment can exercise part of ALLIS, but no single deployment defines the complete system.

---

## 6. Core boundary principles

ALLIS separates several concepts that many systems combine.

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

Three principles govern this boundary.

### State does not become authority merely because it exists

A record, model output, memory item, service, or configuration does not gain authority only because it is present.

### A state transition requires authority for that transition

Evidence that a prior state exists or completed does not automatically authorize the next state.

### Authority itself has provenance

ALLIS treats the origin, scope, and validity of authority as traceable state.

A compact form of the boundary is:

```text
Exists(state)  ⇏  Authorized(transition)

Observed(property)  ⇏  Proven(property)

Proven(formal_property)  ⇏  RuntimeCorrespondent(property)
```

---

## 7. System boundary at a glance

ALLIS is better understood as a governed flow than as one application stack.

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

The exact implementation can use several services or components. The architectural rule remains the same:

> **Computation alone does not create authority to commit, disclose, or mutate state.**

---

## 8. Governed state model

ALLIS works with several related kinds of state.

### 8.1 Semantic and information state

Semantic state represents meaning, retrieved knowledge, analytical context, and computational interpretation.

Semantic relevance does not establish truth, authority, or permission to act.

### 8.2 Geographic state

Geographic state represents place, spatial relationships, geographic context, and location-linked knowledge.

ALLIS treats place as part of the computational context rather than as a display layer added after reasoning.

A geographic association does not by itself prove a fact or grant authority over a place, organization, or community.

### 8.3 Temporal state

Temporal state represents timing, lifecycle, recency, expiration, scheduling, and time-dependent validity.

A declared schedule or decay rule is distinct from evidence that the scheduled process executed.

### 8.4 Person-linked state

ALLIS defines person-linked state as a separately governed class of information.

Person-linked or private state is not ordinary common context. Its use depends on applicable identity, disclosure, provenance, scope, recipient, and lifecycle controls.

If the required authority is absent, the architecture is designed to withhold protected state instead of silently promoting it.

### 8.5 Memory and provenance state

ALLIS does not treat memory as an unrestricted pool of reusable information.

The architecture associates memory and evidence with the relevant provenance, scope, identity, temporal, and governance boundaries.

### 8.6 Governance and authority state

Governance state records whether a transition is eligible, permitted, completed, withheld, unresolved, or outside the authority of the current process.

This state is separate from the substantive information that the system governs.

---

## 9. Identity, privacy, and person-linked information

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

Likewise, identifying the person connected to a record does not automatically authorize the system to disclose, reuse, or propagate that record.

The person-linked information boundary follows these principles:

- private state remains separate from common reasoning state;
- identity-bearing information is not ordinary public context;
- caller-supplied identity claims are not sufficient authority by themselves;
- disclosure scope and recipient scope remain separate from authentication;
- missing authority results in withholding or fail-closed behavior instead of inferred permission.

This section describes the architectural boundary. It does not claim universal runtime correspondence for every person-linked state path unless later evidence establishes that correspondence.

---

## 10. Trust and operational authority

ALLIS uses several trust and governance controls rather than one universal authorization check.

The architecture separates:

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
- a completed audit can establish evidence without authorizing the next audit.

The engineering record also does not support one universal fixed runtime sequence for every governed operation. Where topology remains bounded or unresolved, the documentation preserves that uncertainty.

---

## 11. Governed computation and modification

ALLIS includes a governed modification architecture that keeps proposed changes separate from committed live state until defined governance conditions are satisfied.

Within the qualified governed-modification tract, the engineering record establishes a **69-evaluation architecture produced by 23 connector evaluations across three successive stages**.

The design uses:

- staged evaluation;
- sandboxed processing;
- governance controls;
- rollback boundaries;
- protected transition rules.

A proposed modification is not the same as an authorized production modification.

The engineering evidence contains bounded source and runtime results for portions of the current DGM architecture. The existing evidence does not establish a universal theorem that every possible production mutation is safe.

This document therefore does not describe ALLIS as having a whole-system, mathematically proven production-mutation path.

---

## 12. Evidence, claims, and provenance

ALLIS treats evidence as part of the architecture rather than as documentation added after a system action.

A strong ALLIS claim should answer these questions:

- What evidence supports the claim?
- What inquiry produced the evidence?
- What source or runtime did the inquiry examine?
- Did the inquiry complete?
- Did the evidence pass its integrity checks?
- What scope did the inquiry cover?
- What conclusions does that scope support?
- What remains unresolved?
- What authority permitted the inquiry?
- What successor action, if any, is authorized?

This leads to a central research characteristic of ALLIS:

> **The system records not only evidence, but also the scope and authority of the process that produced that evidence.**

---

## 13. Source, configuration, runtime, and correspondence

ALLIS documentation keeps several engineering states separate.

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

A runtime observation can establish that a component exists without establishing that every client uses it.

A formal theorem can describe a model without establishing that the current runtime corresponds to that model.

This distinction is essential to the accuracy of the ALLIS research record.

---

## 14. Formal validation and proof boundary

ALLIS uses formal analysis when the problem and available evidence support it.

The formal program includes work on:

- protected source roots;
- obligation domains;
- directed control-flow graphs;
- effect candidates and effect sinks;
- governance dominance and cut relationships;
- state-transition properties;
- source correspondence;
- runtime correspondence.

The proof process is staged.

```text
qualified source domain
        ↓
directed graph
        ↓
effect-sink adjudication
        ↓
governance or cut analysis
        ↓
formal theorem
        ↓
machine checking
        ↓
source correspondence
        ↓
runtime correspondence
```

Each stage supports a different class of claim.

### 14.1 Example: bounded graph analysis

Within the audited mathematical tract, the A5 work is reported as closing four qualified root/component pairs into frozen intraprocedural control-flow graphs with:

- **4 qualified pair bindings**
- **102 graph nodes**
- **107 graph edges**
- **0 unsupported control-flow findings**

The subsequent A5A work reduced **76 broad effect candidates** into:

- **47 source-bound or structural candidates**
- **29 unresolved source symbols**

These are meaningful formal-engineering results. They are not a whole-system theorem.

### 14.2 Example: bounded BBB result

A later bounded static result established:

```text
BBB_NON_DOMINANCE_BOUNDED_STATIC_PROOF_ESTABLISHED=YES
```

The same result preserved:

```text
BBB_DOMINATES_COPY2_MUTATION_SINK=NO
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

This is the intended ALLIS use of formal language: the claim stays within the scope that the evidence establishes.

---

## 15. Current correspondence findings

The current architecture record includes several important bounded runtime findings.

### 15.1 BBB

**Architectural role:**  
The BBB acts as a policy boundary in the governed architecture.

**Current evidence:**  
Static policy architecture is supported.

A bounded audit did not establish a dedicated current BBB runtime binding on the Docker and systemd metadata surfaces that it examined.

**Boundary of claim:**  
The audit did not prove that BBB logic is globally absent from the runtime.

Current documentation therefore records:

- static architecture: **supported**;
- dedicated runtime binding on audited surfaces: **not established**;
- global absence: **not established**.

### 15.2 Chroma

**Architectural role:**  
Chroma participates in the system's memory and retrieval architecture.

**Current evidence:**  
A running shared `jarvis-chroma` topology was established within the authorized runtime-metadata scope.

The observed topology includes persistent data binding and declared dependent services.

**Boundary of claim:**  
The audit did not establish:

- global canonical Chroma authority;
- universal resolution of every active client to that instance.

The documentation therefore treats the observed shared topology as bounded runtime evidence, not as universal canonical authority.

### 15.3 Temporal and GBIM decay

**Architectural role:**  
Temporal state governs lifecycle and time-dependent behavior.

**Current evidence:**  
A current-user scheduled decay cron declaration was established.

**Boundary of claim:**  
The bounded audit did not establish:

- actual decay-tick execution history;
- absence of actual decay execution;
- the effective GBIM value path.

A declared schedule remains distinct from demonstrated execution.

### 15.4 Runtime observation stage

The authorized PASS09K runtime-observation stage executed eight authorized observation steps with:

- **8 authorized steps**
- **8 executed steps**
- **0 nonzero returns**
- **0 stderr-producing steps**
- **no scope expansion**
- **no prohibited activity**

This establishes clean execution of the authorized observation stage.

It does not establish that every architectural proposition tested by those observations was confirmed.

---

## 16. PASS09K and audit authority

PASS09K was an audit scope. It was not a development, deployment, or production-mutation authorization.

Its runtime-metadata work was limited to defined architectural questions. After the authorized groups were exhausted, remaining residuals returned to the parent governance ledger.

The current evidence supports these statements:

- PASS09K is **closed**;
- its authorized runtime-metadata scope is **exhausted**;
- additional PASS09K observation is not automatically authorized;
- residual questions can remain after a bounded audit closes;
- closure of PASS09K does not establish whole-system proof;
- closure of PASS09K does not establish a universal production-mutation safety theorem.

A bounded post-PASS09K resolver examined the controlling parent-authority chain and found **no explicit authorized successor within that chain**.

That conclusion applies only to the controlling authority chain. It does not establish universal absence across every historical evidence artifact.

A proposed successor record appears in the engineering history. This document does not promote that proposed record into current authority without separate executed and sealed evidence.

---

## 17. Ms. Allis boundary

Ms. Allis is an intelligence-facing layer that operates through governed ALLIS capabilities.

Ms. Allis can:

- reason over information made available within the relevant scope;
- explain evidence and claims;
- support research and analysis;
- communicate system status when grounded in governed evidence;
- help people navigate information and services when authority permits.

Ms. Allis does not create system authority by reasoning about an action.

A conversational request is not equivalent to authorization for a protected state transition.

---

## 18. Human and institutional authority

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

When a government agency, university, nonprofit, community organization, or other institution holds independent authority, that authority remains its own.

ALLIS can support the evidence process without absorbing that institution's legal or organizational authority.

---

## 19. Deployment and pilot boundary

The New River Gorge Safety & Heritage Mesh Pilot is a practical research and deployment context for ALLIS.

The pilot can exercise elements of:

- place-based information;
- geographic state;
- heritage interpretation;
- community participation;
- governed feedback;
- connectivity;
- research evaluation.

The pilot does not redefine the underlying ALLIS architecture.

Planning, funding, authorization, installation, testing, and demonstrated outcomes remain separate states.

A project being designed or funded does not establish that it has been installed. Installation does not establish tested performance. Tested performance does not automatically establish long-term community or institutional outcomes.

---

## 20. Public and research interface boundary

A public, university-facing, or community-facing interface should present governed ALLIS evidence without becoming an independent source of authority.

The preferred publication pattern is:

```text
ALLIS live system
        ↓
governed read-only export
        ↓
versioned publication state
        ↓
public or research interface
```

This pattern keeps presentation separate from live-system mutation.

A human-facing interface should preserve uncertainty.

| Condition | Display |
|---|---|
| Data is unavailable | **Unavailable** |
| A proposition is not established | **Not proven** |
| The inquiry did not cover the question | **Outside audited scope** |
| No current successor authority is established | **No authorized successor** |

Missing data should not be converted into **healthy**, **successful**, **proven**, **authorized**, or **canonical**.

This section defines the publication boundary. It does not claim that every proposed public interface, reverse tunnel, Caddy route, Cloudflare route, or publication exporter is already deployed.

---

## 21. Current validation boundaries

The current evidence supports substantial architectural, runtime, and formal work. It does not support several broader claims.

This document does not claim that:

- ALLIS is wholly mathematically proven;
- a universal production-mutation safety theorem has been established;
- every protected operation has been proven to traverse one fixed runtime sequence;
- a dedicated BBB runtime service is globally established;
- BBB is globally absent from the runtime;
- `jarvis-chroma` is the universal canonical Chroma authority;
- every active client uses the observed `jarvis-chroma` instance;
- a declared temporal-decay schedule proves actual decay execution;
- every person-linked or private-state path has current runtime correspondence;
- completion of PASS09K creates automatic successor authority;
- a proposed successor authority becomes valid because it appears in a script or design record;
- a public GUI or publication path is deployed unless separate evidence verifies it;
- a bounded proof can be generalized beyond its stated source, runtime, or theorem scope.

These boundaries are part of the architecture record. They are not post hoc disclaimers.

---

## 22. Relationship to the thesis and university portfolio

The ALLIS thesis and the KTS ALLIS technical documentation serve different roles.

### Thesis

The thesis explains the research lineage, theoretical development, and broader intellectual framework.

### KTS ALLIS technical documentation

The KTS ALLIS repository describes the current engineering and research system.

### This system-boundary document

This document defines the present boundary between:

- architecture;
- implementation;
- runtime;
- evidence;
- authority;
- formal proof;
- correspondence;
- external systems and deployments.

The university portfolio can therefore use this document as a current technical reference while using the thesis as the broader research narrative.

The thesis does not determine the present system state when later qualified engineering evidence supersedes an older implementation description.

---

## 23. Research significance

ALLIS is both software and a research object.

Its research questions extend beyond whether an AI system can generate a useful answer.

ALLIS asks questions such as:

- What makes information admissible for a specific use?
- How should provenance travel with computational state?
- How should person-linked state remain separate from common knowledge?
- How should geographic and temporal context affect meaning without automatically creating authority?
- How should a system distinguish observed behavior from formal proof?
- How can a formal claim be tied back to qualified source and observed runtime?
- How can community knowledge contribute without being mistaken for institutional authority?
- How can a computational system preserve uncertainty instead of converting uncertainty into confidence or permission?

These questions make the system boundary part of the research method rather than only an engineering diagram.

---

## 24. Evidence families referenced by this document

This document summarizes results from several evidence families.

| Evidence family | Role in the current boundary |
|---|---|
| **Qualified source baseline** | Defines the engineering source anchor used for present-state claims. |
| **MATHAUDIT A4F1 / A5 / A5A** | Supports the bounded source-domain, graph, and effect-candidate analysis. |
| **D1R5F** | Supports the bounded BBB non-dominance result while preserving the larger production-mutation theorem as unproven. |
| **PASS09J** | Supports architecture, governance, DGM, trust, and documentation-baseline work. |
| **PASS09K** | Supports bounded runtime-metadata observation and adjudication. |
| **PASS09K R8** | Supports the completed authorized runtime-observation stage. |
| **PASS09K R10** | Supports formal closeout and return of residuals to the parent governance ledger. |
| **Post-PASS09K resolver** | Supports the bounded conclusion that the controlling parent-authority chain contained no explicit successor at the time of that inquiry. |

Detailed evidence artifacts remain part of the engineering evidence record. This document uses them to support current claims without reproducing the full audit history.

---

## 25. Conclusion

ALLIS is a governed computational and knowledge architecture that binds information, evidence, claims, state transitions, and operational authority to provenance and scope.

Its present engineering record includes:

- a qualified source anchor;
- governed semantic, geographic, temporal, person-linked, memory, and authority concepts;
- explicit trust and privacy boundaries;
- a staged governed-modification architecture;
- current runtime observations within bounded audit scopes;
- structured evidence and provenance records;
- bounded formal and mathematical results;
- explicit handling of unresolved claims.

The current evidence does not establish a whole-system mathematical proof or a universal production-mutation safety theorem.

The documentation therefore follows one final rule:

> **Claims remain limited to the source, runtime, authority, evidence, and correspondence scopes that the record actually supports.**

That rule is not separate from ALLIS. It is part of the architecture itself.
