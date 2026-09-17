# ALLIS System Boundary

## Current Architecture, Authority Model, Evidence Scope, and Validation Limits

**System:** ALLIS — Artificial Learning and Location Intelligence System  
**Organization:** Kidd's Technical Services  
**Document role:** Present-state system-boundary description for research, technical review, and university collaboration  
**Audience:** University researchers, technical reviewers, community partners, and collaborators  
**Evidence posture:** Qualified engineering/documentation baseline with explicit residuals  
**Evidence reviewed through:** September 17, 2026  

### Qualified engineering source anchor

- **Branch:** `remediation/bbb-fail-closed-20260830T212059Z`
- **HEAD:** `35f1aa5586e1a23e1ab88f4d757c451b44506893`
- **Tree:** `36dd9f2425db4b23bacfce1cb258603cace25f1b`

> This document describes the present system boundary. It is not a development diary, a production-safety certification, or a claim that every ALLIS subsystem has reached the same level of validation.

---

## Abstract

ALLIS is a governed computational and knowledge architecture developed by Kidd's Technical Services. It combines semantic, geographic, temporal, person-linked, memory, provenance, and governance state while keeping information, evidence, claims, authority, and system action distinct.

The central design principle is simple: **state does not become authority merely because it exists.** Information may be present without being verified. A claim may be well supported without authorizing an action. A user or service may be authenticated without being authorized for a particular transition. A mathematical result may be valid within its formal scope without yet being shown to correspond to the current runtime.

For that reason, ALLIS uses multiple evidence and validation levels rather than a single pass/fail label. The engineering record distinguishes what is implemented, what has been observed or demonstrated, what has been formally specified or proven, and what has been shown to correspond to qualified source or runtime behavior.

This document defines the present ALLIS boundary: what belongs to ALLIS, what remains outside it, how major trust and governance boundaries operate, what current evidence supports, and what remains explicitly unresolved. It also distinguishes ALLIS from Ms. Allis, MountainShares/The Commons, Community Champion roles, and individual deployment projects.

---

## 1. Purpose and Scope

The purpose of this document is to provide a clear, academically rigorous description of ALLIS without requiring the reader to first understand the full engineering history.

It answers five questions:

1. **What is ALLIS?**
2. **What is inside and outside the ALLIS system boundary?**
3. **How does ALLIS separate information, evidence, authority, and action?**
4. **What has been implemented, observed, demonstrated, or formally evaluated?**
5. **What does the current evidence not establish?**

The detailed engineering history, audit scripts, intermediate failures, superseded configurations, and local evidence artifacts are used to determine which present-tense claims are justified. They are not reproduced here as the narrative of the system.

---

## 2. How to Read ALLIS Evidence Labels

ALLIS does not treat all forms of verification as equivalent.

| Evidence level | Meaning |
|---|---|
| **Implemented** | A mechanism exists in the qualified source or system design. |
| **Observed** | A bounded inspection directly found a current configuration or runtime fact. |
| **Demonstrated** | A behavior was exercised under a defined test or operational scope. |
| **Formally Specified** | A property has been expressed precisely enough for formal analysis. |
| **Proven** | A theorem or formal property has been established within stated assumptions and scope. |
| **Machine-Checked** | A formal result has been checked by an appropriate verification tool or formal procedure. |
| **Source-Correspondent** | The formal model or claim has been shown to map to the qualified source. |
| **Runtime-Correspondent** | The claim has been shown to map to the observed runtime within the audited scope. |
| **Not Proven** | The available evidence does not establish the proposition. This does **not** mean the proposition is false. |
| **Disproven** | Evidence establishes that the proposition, as stated, is false within the stated scope. |
| **Outside Audited Scope** | The inquiry did not examine the proposition closely enough to support a conclusion. |

Authority uses a separate vocabulary:

- **Authorized**
- **Not Authorized**
- **Executed**
- **Not Executed**
- **Open**
- **Closed**
- **Unresolved**

These labels answer different questions and should not be collapsed into a generic pass/fail status.

---

## 3. What ALLIS Is

ALLIS is the **Kidd's Technical Services engineering and research platform** for governed computation, knowledge, evidence, location intelligence, and state transition.

At a high level, ALLIS is designed to:

- represent information together with provenance, scope, and governance context;
- combine semantic and geographic reasoning without treating either as self-authorizing;
- distinguish public or common state from person-linked or restricted state;
- preserve evidence about how claims and system states were produced;
- separate identity from authorization;
- separate observation from proof;
- separate proof from implementation correspondence;
- govern high-consequence transitions rather than allowing system state to mutate solely because a computation produced a result.

ALLIS is therefore more than a retrieval system, chatbot, GIS application, or workflow engine. Its defining feature is the relationship among **state, evidence, provenance, authority, and transition**.

---

## 4. What ALLIS Is Not

Several related systems and programs interact with ALLIS but are not identical to it.

### Ms. Allis

**Ms. Allis** is a governed analytical and advisory intelligence that may operate through ALLIS. Ms. Allis is not the entire ALLIS platform.

ALLIS provides the computational, evidence, state, and governance environment. Ms. Allis is one intelligence-facing expression of that environment.

### MountainShares and The Commons

**MountainShares** and **The Commons** are separate governance, community, and economic structures that may use ALLIS services or evidence.

Their community or economic authority does not automatically become ALLIS system authority, and ALLIS technical authority does not automatically become community governance authority.

### Community Champions

**Community Champions** are human participants in a governed stewardship and local-knowledge process. Participation may support observation, training, competency, field practice, and governed contribution.

Community Champion status does not automatically create:

- system-administrator authority;
- institutional authority;
- government authority;
- authority to validate every local claim;
- authority to modify ALLIS.

### Deployment Projects

The **New River Gorge Safety & Heritage Mesh Pilot** and related Mount Hope or future Thurmond work are deployment and research-use contexts for ALLIS.

A deployment may exercise part of ALLIS, but no single deployment defines the complete system.

---

## 5. Core Boundary Principle

ALLIS is organized around a fundamental non-equivalence:

> **State does not become authority merely because it exists.**

In practical terms:

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

A second principle follows:

> **A state transition requires evidence of authority for that transition; evidence that a predecessor state exists or completed does not itself authorize the successor.**

A third principle is equally important:

> **Authority itself has provenance.**

ALLIS therefore treats the origin, scope, and validity of authority as information that must itself be traceable.

A compact formal expression of the boundary is:

```text
Exists(state)  ⇏  Authorized(transition)

Observed(property)  ⇏  Proven(property)

Proven(formal_property)  ⇏  RuntimeCorrespondent(property)
```

These statements are not claims that observation or proof is unimportant. They define which additional evidence is required before one class of statement can be promoted into another.

---

## 6. System Boundary at a Glance

The ALLIS boundary can be understood as a governed flow rather than a single application stack.

```text
External information, research, GIS, community observations, services
                              │
                              ▼
                 Governed intake / provenance
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
                 Claim / authority evaluation
                              │
                ┌─────────────┴─────────────┐
                │                           │
                ▼                           ▼
        Authorized transition       Withhold / fail closed
                │
                ▼
        Governed committed state
        or governed external output
```

The exact implementation of a boundary may involve several services or components. The architectural rule is more important than any one deployment topology: **computation alone does not create authority to commit, disclose, or mutate state.**

---

## 7. Governed State Model

ALLIS works with several related kinds of state.

### 7.1 Semantic and Information State

Semantic state represents meaning, retrieved knowledge, analytical context, and computational interpretation.

Semantic relevance does not by itself establish truth, authority, or permission to act.

### 7.2 Geographic State

Geographic state represents place, spatial relationship, geographic context, and location-linked knowledge.

ALLIS treats place as part of the computational context rather than as a display layer added after reasoning.

Geographic association does not itself prove a fact or grant authority over a place, organization, or community.

### 7.3 Temporal State

Temporal state represents timing, lifecycle, recency, expiration, scheduling, and time-dependent validity.

A declared schedule or decay rule is distinct from evidence that the scheduled process actually executed.

### 7.4 Person-Linked State

ALLIS defines person-linked state as a separately governed class of information.

Person-linked or private state is not treated as ordinary common context. Its use depends on applicable identity, disclosure, provenance, scope, recipient, and lifecycle controls.

The architecture is intentionally designed so that lack of required authority results in withholding rather than silent promotion of private state.

### 7.5 Memory and Provenance State

Memory is not treated as an unqualified pool of reusable information.

The system architecture associates memory and evidence with relevant provenance, scope, identity, temporal, and governance boundaries.

### 7.6 Governance and Authority State

Governance state records whether a transition is eligible, permitted, completed, withheld, unresolved, or outside the authority of the current process.

This state is distinct from the substantive information being governed.

---

## 8. Identity, Privacy, and Person-Linked Information

ALLIS separates several concepts that are often combined in ordinary applications:

```text
identity
≠ authentication
≠ authorization
≠ disclosure authority
≠ governance authority
≠ operation authority
```

An authenticated caller is not automatically authorized for every action.

Likewise, knowing which person a record concerns does not automatically authorize the system to disclose, reuse, or propagate that record.

The person-linked information boundary is designed around several principles:

- private state should remain distinct from common reasoning state;
- identity-bearing information should not be treated as ordinary public context;
- caller-supplied identity claims are not sufficient merely because they were supplied;
- disclosure and recipient scope matter separately from authentication;
- the absence of required authority should result in withholding or fail-closed behavior rather than inferred permission.

This document describes those as architectural boundaries. It does not claim universal runtime correspondence for every person-linked-state path unless such correspondence has been separately established.

---

## 9. Trust and Operational Authority

ALLIS uses multiple trust and governance controls rather than one universal authorization check.

The architecture includes separate concerns for:

- caller identity;
- constitutional or policy admission;
- boundary and policy enforcement;
- Guardian authority;
- operation intent;
- evidence and receipt generation;
- transition-specific authorization.

These controls should not be understood as interchangeable.

For example, a caller may be authenticated but still lack permission to perform a governed operation. A policy condition may pass without granting unrelated mutation authority. A completed audit may establish evidence without authorizing the next audit.

The engineering record also does not justify reducing every governed operation to one universal fixed runtime sequence. Where topology is bounded or unresolved, the documentation preserves that uncertainty rather than forcing the system into an assumed diagram.

---

## 10. Governed Computation and Modification

ALLIS includes a governed modification architecture intended to keep proposed changes separate from committed live state until defined governance conditions are satisfied.

The current evidence records a **69-DGM chain corresponding to 23 connectors across three stages** within the audited modification architecture. The design uses staged or sandboxed processing, governance controls, and rollback boundaries before a candidate modification can affect committed state.

This is an important distinction:

> **A proposed modification is not the same as an authorized production modification.**

The engineering evidence contains bounded proof and runtime evidence for portions of the current DGM architecture. It does **not** establish a universal theorem that every possible production mutation is safe.

Accordingly, this document does not use phrases such as **“mathematically proven safe production mutation”** as a whole-system claim.

---

## 11. Evidence, Claims, and Provenance

ALLIS treats evidence as part of the architecture rather than as documentation added after the fact.

A strong ALLIS claim should be traceable to questions such as:

- What evidence supports this claim?
- What inquiry produced the evidence?
- What source or runtime was examined?
- Was the inquiry completed?
- Was its evidence sealed or otherwise integrity-checked?
- What scope did the inquiry cover?
- What conclusions does that scope allow?
- What remains unresolved?
- What authority permitted the inquiry?
- What successor action, if any, is authorized?

This leads to a central research characteristic of ALLIS:

> **Evidence is not only stored; the authority and scope of the evidence-producing process are themselves part of the record.**

---

## 12. Source, Configuration, Runtime, and Correspondence

ALLIS documentation maintains a strict distinction among several engineering states:

```text
implemented source
≠ verified source
≠ declared configuration
≠ instantiated runtime
≠ observed behavior
≠ operational authority
```

A source file may contain a capability that is not instantiated in the running system.

A configuration may declare a service or authority path that is not currently active.

A runtime observation may establish that a component exists without establishing that every client uses it.

A valid formal theorem may describe a model without establishing that the current runtime corresponds to that model.

This distinction is essential to the accuracy of the ALLIS research record.

---

## 13. Formal Validation and Proof Boundary

ALLIS uses formal analysis where the problem and available evidence support it.

The formal program includes work on:

- protected source roots;
- obligation domains;
- directed control-flow graphs;
- effect candidates and effect sinks;
- governance dominance and cut relationships;
- state-transition properties;
- source correspondence;
- runtime correspondence.

The proof process is intentionally staged.

```text
qualified source domain
        ↓
directed graph
        ↓
effect-sink adjudication
        ↓
governance / cut analysis
        ↓
formal theorem
        ↓
machine checking
        ↓
source correspondence
        ↓
runtime correspondence
```

No stage should be silently promoted into the next.

### Example: bounded graph work

Within the audited mathematical tract, the A5 work is reported as closing four qualified root/component pairs into frozen intraprocedural control-flow graphs with:

- **4 qualified pair bindings**
- **102 graph nodes**
- **107 graph edges**
- **0 unsupported control-flow findings**

The subsequent A5A work reduced **76 broad effect candidates** into:

- **47 source-bound or structural candidates**
- **29 unresolved source symbols**

These are meaningful formal-engineering results. They are not, by themselves, a whole-system theorem.

### Example: BBB bounded result

A later bounded static result established:

```text
BBB_NON_DOMINANCE_BOUNDED_STATIC_PROOF_ESTABLISHED=YES
```

while preserving:

```text
BBB_DOMINATES_COPY2_MUTATION_SINK=NO
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

This is the intended ALLIS use of formal language: the result is stated at the scope actually established.

---

## 14. Current Bounded Runtime Findings

The current architecture record includes several important runtime observations.

### 14.1 BBB

The **BBB static policy architecture is supported**.

Within the audited Docker and systemd metadata surfaces, a dedicated current BBB runtime binding was not established.

That bounded result does **not** establish universal runtime absence. BBB logic may be composed differently, embedded elsewhere, or remain unresolved under the audited topology.

Therefore:

- static architecture: **supported**;
- dedicated runtime binding on audited surfaces: **not established**;
- global absence: **not established**.

### 14.2 Chroma

A running shared `jarvis-chroma` topology was established within the authorized runtime-metadata scope.

Observed characteristics include a persistent data binding and declared dependent services.

The audit did **not** establish:

- global canonical Chroma authority;
- that every active client resolves to that instance.

Therefore the observed shared topology is documented without promoting it to universal canonical authority.

### 14.3 Temporal / GBIM Decay

A current-user scheduled decay cron declaration was established.

The bounded audit did not establish:

- actual decay-tick execution history;
- that decay execution was absent;
- the effective GBIM value path.

A declared schedule therefore remains distinct from demonstrated execution.

### 14.4 Runtime Observation Stage

The authorized PASS09K runtime-observation stage executed eight authorized observation steps with:

- **8 authorized steps**
- **8 executed steps**
- **0 nonzero returns**
- **0 stderr-producing steps**
- **no scope expansion**
- **no prohibited activity**

That establishes clean execution of the authorized observation stage.

It does **not** by itself establish that every architectural proposition tested by those observations was confirmed.

---

## 15. PASS09K and the Audit Authority Boundary

PASS09K was an **audit scope**, not a development, deployment, or production-mutation authorization.

Its runtime-metadata work was bounded to defined architectural questions. After the authorized groups were exhausted, remaining residuals were returned to the parent governance ledger.

The current record therefore supports these statements:

- PASS09K is **closed**;
- its authorized runtime-metadata scope is **exhausted**;
- additional PASS09K observation is not automatically authorized;
- residual questions may remain after a bounded audit closes;
- closure of PASS09K does not establish whole-system proof;
- closure of PASS09K does not establish a universal production-mutation safety theorem.

A bounded post-PASS09K resolver examined the controlling parent-authority chain and found **no explicit authorized successor within that chain**.

That conclusion is limited to the controlling authority chain. It does not establish universal absence across every historical evidence artifact.

A proposed successor record appears in the engineering history, but this system-boundary document does not promote that proposed successor into current authority without separate executed and sealed evidence.

---

## 16. Ms. Allis Boundary

Ms. Allis should be understood as an intelligence-facing layer operating through governed ALLIS capabilities.

She may:

- reason over information made available within the relevant scope;
- explain evidence and claims;
- support research and analysis;
- communicate system status when grounded in governed evidence;
- help users navigate information and services where authority permits.

Ms. Allis does not independently create system authority simply because she can reason about an action.

A conversational request is therefore not equivalent to authorization for a protected state transition.

---

## 17. Human and Institutional Authority

ALLIS is designed to support human and institutional decision-making, not replace it.

Human observations may contribute evidence. Community knowledge may provide important context. Community Champions may support local stewardship and governed feedback.

However:

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

Where a government agency, university, nonprofit, community organization, or other institution holds independent authority, that authority remains its own.

ALLIS may support the evidence process without absorbing that institution's legal or organizational authority.

---

## 18. Deployment and Pilot Boundary

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

Likewise, planning, funding, authorization, installation, testing, and demonstrated outcomes are distinct states.

A project being designed or funded does not establish that it has been installed. Installation does not by itself establish tested performance. Tested performance does not automatically establish long-term community or institutional outcomes.

---

## 19. Public and Research Interface Boundary

A public, university-facing, or community-facing interface should present governed ALLIS evidence without becoming an independent source of authority.

The preferred publication pattern is:

```text
ALLIS live system
        ↓
governed read-only export
        ↓
versioned publication state
        ↓
public / research interface
```

This keeps presentation separate from live-system mutation.

A human-facing interface should fail closed epistemically:

| Condition | Display |
|---|---|
| Data is unavailable | **Unavailable** |
| A proposition is not established | **Not proven** |
| The inquiry did not cover the question | **Outside audited scope** |
| No current successor authority is established | **No authorized successor** |

Missing data should never be automatically converted into **healthy**, **successful**, **proven**, **authorized**, or **canonical**.

This section defines the publication boundary. It does not claim that every proposed public interface or routing component has already been deployed.

---

## 20. Explicit Residuals and Nonclaims

The present evidence supports substantial architectural and formal work, but several broader claims remain intentionally unasserted.

This document does **not** claim that:

- ALLIS is wholly mathematically proven;
- a universal production-mutation safety theorem has been established;
- every protected operation has been proven to traverse one fixed runtime sequence;
- a dedicated BBB runtime service is globally established;
- BBB is globally absent from the runtime;
- `jarvis-chroma` is the universal canonical Chroma authority;
- every active client uses the observed `jarvis-chroma` instance;
- a declared temporal-decay schedule proves actual decay execution;
- every person-linked/private-state path has current runtime correspondence;
- completion of PASS09K creates automatic successor authority;
- a proposed successor authority becomes valid merely because it appears in a script or design record;
- a public GUI, reverse tunnel, Caddy route, Cloudflare route, or publication exporter is deployed unless separately verified;
- a bounded proof may be generalized beyond its stated source, runtime, or theorem scope.

These statements are not disclaimers added after the architecture. They are part of the system boundary itself.

---

## 21. Document Authority and Update Rule

This document is controlled by the strongest qualified evidence available for each claim.

Evidence is not ordered merely by where it appears in a transcript or repository.

Where historical and current records differ, priority should be determined by:

1. evidence timestamp;
2. qualified source identity;
3. bound predecessor/successor relationship;
4. execution status;
5. evidence integrity or seal status;
6. formal acceptance state;
7. later correspondence evidence.

A prepared script is not an executed result.

Expected output is not observed output.

An observed result is not automatically an accepted authority state.

A historical deployment is not automatically the current runtime.

This update rule allows the public documentation to remain present-tense while preserving the engineering discipline that supports it.

---

## 22. Research Significance

ALLIS is being developed not only as software but as a research object concerned with how computational systems represent and govern knowledge, place, identity, time, evidence, and authority.

The research problem is therefore broader than whether an AI system can produce a useful answer.

ALLIS asks questions such as:

- What makes information admissible for a particular use?
- How should provenance travel with computational state?
- How should person-linked state remain separated from common knowledge?
- How can geographic and temporal context affect meaning without automatically creating authority?
- How should systems distinguish observed behavior from formal proof?
- How can formal claims be tied back to qualified source and observed runtime?
- How can community knowledge contribute without being mistaken for institutional authority?
- How can a computational system preserve uncertainty rather than silently converting it into confidence or permission?

These questions make the system boundary part of the research methodology rather than only an engineering diagram.

---

## 23. System Boundary Summary

ALLIS is a governed computational and knowledge architecture that binds information, state transitions, evidence, claims, and operational authority to provenance and scope.

Its present engineering record includes:

- a qualified source anchor;
- governed semantic, geographic, temporal, person-linked, memory, and authority concepts;
- explicit trust and privacy boundaries;
- a staged governed-modification architecture;
- current runtime observations within bounded audit scopes;
- structured evidence and provenance records;
- bounded formal and mathematical results;
- explicit residual and nonclaim handling.

The current evidence does **not** establish a whole-system mathematical proof or a universal production-mutation safety theorem.

Accordingly, ALLIS documentation follows a conservative rule:

> **Claims remain limited to the source, runtime, authority, evidence, and correspondence scopes actually demonstrated.**

This is not a limitation of the documentation method. It is a defining feature of the ALLIS architecture.

---

## 24. Short Form

For readers who need the boundary in one paragraph:

> **ALLIS is a governed computational and knowledge architecture developed by Kidd's Technical Services. It separates information from evidence, evidence from claims, claims from authority, and authority from execution. Semantic, geographic, temporal, person-linked, memory, and governance state may participate in computation, but no state becomes authoritative merely because it exists. ALLIS uses separate validation levels for implementation, observation, demonstration, formal specification, proof, machine checking, and source/runtime correspondence. Its current engineering record supports meaningful bounded architectural, runtime, and formal results while retaining explicit unresolved areas. ALLIS therefore does not claim whole-system mathematical proof or universal production-mutation safety; each claim remains limited to the evidence and authority scope actually established.**
