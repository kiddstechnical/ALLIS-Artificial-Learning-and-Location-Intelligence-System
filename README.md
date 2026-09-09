# ALLIS — Artificial Learning and Location Intelligence System

**A Kidd’s Technical Services research and engineering program for governed artificial intelligence, location intelligence, empirical system validation, and formal verification.**

ALLIS is the **Artificial Learning and Location Intelligence System** developed through Kidd’s Technical Services (KTS).

This repository is the KTS-centered research and validation home for ALLIS as an engineered computational system. Its purpose is to document what the system is, what it is claimed to do, how those claims are measured, which properties can be formally specified or proven, and whether the formal model corresponds to the qualified implementation and observed runtime.

This repository is intentionally distinct from the **MountainShares**, **The Commons**, **New River Gorge Safety & Heritage Mesh Pilot**, and **msjarvis-public-docs** repositories. Those bodies of work remain important deployment, governance, community, thesis, and research contexts for ALLIS, but they are not the authoritative KTS validation repository for the underlying system.

---

## What ALLIS Is

ALLIS is a place-aware artificial intelligence and location-intelligence architecture that combines semantic reasoning, geographic information, temporal state, governed memory, provenance, identity and authorization controls, and structured promotion boundaries.

The system has been developed around a core principle:

> **State does not become authority merely because it exists.**

Information may be available to a computational process without thereby becoming authorized memory, verified evidence, durable belief, public disclosure, or external action. ALLIS therefore treats reasoning, retention, promotion, projection, disclosure, and action as distinct state transitions subject to explicit constraints.

The system architecture includes research and engineering work involving:

- semantic and vector state;
- geographic and spatial state;
- temporal state and lifecycle;
- person-linked and identity-aware state;
- governed memory;
- provenance and source authority;
- authorization and consent;
- privacy-preserving disclosure;
- psychological and relational safety controls;
- candidate-to-authoritative state promotion;
- recurrent review and system self-checking;
- formal trust boundaries;
- reproducibility and evidence capture;
- empirical measurement and experimental validation.

Not every architectural term in the broader research corpus is assumed here to be a completed mathematical object. One purpose of this repository is to determine precisely which descriptions are literal mathematical structures, which are computational representations, and which remain architectural abstractions requiring further formalization.

---

## ALLIS, MountainShares, and the `MS.` Designation

ALLIS is **not synonymous with MountainShares**.

ALLIS is the underlying KTS technology and research system. MountainShares is a separate community economic, governance, and commons program developed through Harmony for Hope, Inc. and its associated Commons structure.

Within the MountainShares deployment model, node names may use the form:

```text
MS.<partner-or-node>.ALLIS
```

The `MS.` prefix identifies the deployment as part of the **MountainShares** program or sponsorship relationship. The middle identifier names the relevant community, partner, corridor, or node, while `ALLIS` identifies the underlying KTS technology platform.

Examples documented in the broader project corpus include forms such as:

```text
MS.MHHWT.ALLIS
MS.THURMOND.ALLIS
MS.NPS.ALLIS
```

The MountainShares designation does **not** transfer ownership of ALLIS.

The project contracts and licensing documents distinguish among:

- **Kidd’s Technical Services** — technical and commercial system development, retained ALLIS/GBIM intellectual property, and related proprietary architecture;
- **Harmony for Hope, Inc.** — charitable and programmatic sponsor for applicable MountainShares and community initiatives;
- **MountainShares Commons / DUNA** — community governance, participation, mutual-credit, treasury, and related community-account structures;
- **ALLIS** — the underlying KTS artificial learning and location-intelligence system used or licensed within applicable deployments.

This separation is intentional. Community governance of a MountainShares deployment does not imply ownership of the underlying ALLIS platform, and KTS ownership of ALLIS does not confer control over community governance, participant accounts, or Commons decision-making.

---

## Ms. Allis

Within the MountainShares and Commons documentation, **Ms. Allis** is the governed analytical and advisory intelligence associated with that ecosystem.

She is described as supporting analysis, system-health awareness, community information, and governed decision support while remaining subject to explicit human governance, privacy, economic-safety, and authority boundaries.

Ms. Allis is not described here as the owner of MountainShares, the Commons, community accounts, participant value, or governance authority.

The `MS.` naming convention used in MountainShares ALLIS deployments refers to **MountainShares**.

Legacy project materials may still contain earlier names, including **Ms. Jarvis** or related historical identifiers. Those references are retained where necessary for provenance and research continuity but should not be treated as the preferred current naming standard for new ALLIS documentation.

---

## Relationship to Other Repositories and Programs

### `msjarvis-public-docs`

The public-docs repository preserves the broader thesis, conceptual development, architecture documentation, discipline, evaluations, hypothesis work, MountainShares materials, Commons documentation, contracts, and research history that contributed to ALLIS.

It is a major source of provenance and research lineage.

It is **not** this repository’s substitute for a KTS system-validation record.

### MountainShares and The Commons

MountainShares and The Commons are governed community and economic structures that may use ALLIS capabilities under defined agreements, licenses, and deployment boundaries.

They are not the owner or definition of ALLIS itself.

### New River Gorge Safety & Heritage Mesh Pilot

The New River Gorge Safety & Heritage Mesh Pilot is a community-centered deployment, planning, and research use case.

It provides one important environment in which ALLIS capabilities may be applied, studied, and evaluated, but the pilot is not the parent architecture for ALLIS.

### Kidd’s Technical Services

This repository belongs to the KTS research and engineering side of the work.

It is intended to provide a clean system-level record independent of any single nonprofit program, community deployment, grant, pilot, or thesis chapter.

---

## Why This Repository Exists

The broader ALLIS documentation has accumulated across architecture chapters, evaluations, service inventories, MountainShares governance materials, Commons documentation, contracts, research hypotheses, pilot materials, and production-closeout evidence.

That history is valuable, but formal validation requires a more disciplined separation between:

1. **what is implemented;**
2. **what has been empirically observed;**
3. **what has been experimentally demonstrated;**
4. **what is formally specified;**
5. **what has been mathematically proven;**
6. **what has been machine-checked;**
7. **what corresponds to the qualified implementation;**
8. **what remains a hypothesis, conjecture, or future research direction.**

This repository exists to maintain those distinctions.

---

## Validation Model

ALLIS validation is organized around three complementary forms of evidence.

### 1. Empirical Measurement

Empirical measurement asks:

> **Does the qualified running system actually exhibit the claimed behavior?**

Examples may include measurements of:

- state continuity;
- authorization success and rejection;
- promotion and retention behavior;
- provenance continuity;
- memory isolation;
- disclosure boundaries;
- fail-closed behavior;
- system-state stability;
- retrieval and grounding performance;
- semantic and geographic disambiguation;
- temporal validity;
- error and fabrication rates;
- recovery after controlled degradation.

A claim is not considered validated merely because the architecture was designed to support it.

### 2. Mathematical and Formal Verification

Formal analysis asks:

> **Given a defined model and stated assumptions, what properties must hold?**

This phase may include:

- state-transition models;
- invariants;
- reachability analysis;
- authorization logic;
- provenance-chain properties;
- temporal-governance properties;
- graph and topology analysis;
- formal specification;
- model checking;
- SMT-based verification;
- theorem proving where appropriate;
- Hilbert-space and other state-space mathematics where the structure is actually justified.

Mathematical proof establishes properties of a formal model under stated assumptions. It does not, by itself, prove that a running implementation matches that model.

### 3. Proof-to-Implementation Correspondence

The strongest validation requires correspondence among:

```text
formal model
    ↕
qualified source
    ↕
observed runtime
```

A formally proven invariant is useful only if the implementation actually instantiates the assumptions, state variables, transitions, boundaries, and operators used by the proof.

This correspondence layer is therefore treated as a first-class research problem.

---

## Discrepancy Preservation and Remediation

Formal verification is expected to find discrepancies.

That is not treated as a failure of the research program.

If a proof attempt, model check, runtime measurement, or correspondence review identifies a mismatch, the discrepancy should be preserved as evidence:

```text
claim
  ↓
formalization
  ↓
proof attempt / measurement
  ↓
counterexample or discrepancy
  ↓
root-cause analysis
  ↓
repair
  ↓
re-test
  ↓
re-proof
```

The original failed state should remain traceable.

A repaired implementation should not silently erase:

- the failed invariant;
- the counterexample;
- the affected source or runtime path;
- the repair;
- the regression checks;
- the subsequent proof or validation result.

The purpose of formal verification is not to protect the implementation from criticism. The purpose is to make the architecture, mathematics, qualified source, and observed behavior correspond as accurately as possible.

---

## Current Development Boundary

ALLIS is currently completing a staged production-acceptance and administrative-closeout process.

That work is intentionally finite and separate from the mathematical-verification program.

The formal research sequence is:

```text
production acceptance and closeout
        ↓
qualified baseline freeze
        ↓
formal claim inventory
        ↓
operational definitions and measurements
        ↓
mathematical specification
        ↓
invariants and theorem development
        ↓
machine-checkable verification where appropriate
        ↓
proof-to-implementation correspondence
        ↓
discrepancy remediation and re-verification
```

The post-acceptance proof phase is not an extension of the production acceptance checklist. It is a distinct research and validation phase performed against a frozen, qualified system baseline.

---

## Research Program

The ALLIS research program includes several related but separately testable lines of inquiry.

### Governed State

A foundational proposition is that computational state and authoritative state are not identical.

Conceptually:

\[
x \in \mathcal{S}
\]

does not imply that \(x\) is automatically admissible as:

- retained memory;
- verified evidence;
- promoted knowledge;
- public disclosure;
- external action.

Each transition may require its own conditions of identity, authority, provenance, consent, scope, time, purpose, and safety.

### Relational and Geographic Meaning

ALLIS has been developed around the importance of structured relationships among semantic content, place, time, identity, provenance, and authority.

The related **Does Meaning Require Geometry?** research program tests whether removing specified relational grounding produces measurable degradation in semantic behavior and whether restoring those relations produces recovery.

The current research does **not** assume that representational geometry is physically identical to quantum or spacetime geometry.

### Cognitive-State Architecture

The broader architecture includes separate experiential/meaning-oriented and analytical/evidentiary processing structures, recurrent state, memory, introspection, psychological-safety review, and governed promotion.

A post-acceptance research goal is to determine which of these properties can be:

- operationally defined;
- empirically measured;
- mathematically modeled;
- formally verified;
- mapped accurately to the implemented system.

Terms such as **governed cognitive state** or any future integrated personal-state formalism should be treated as research constructs until their mathematical definitions and implementation correspondence are established.

### Formal State-Space Mathematics

ALLIS uses state-space and Hilbert-inspired language in parts of its research lineage.

The formal-verification program will distinguish among:

- genuine Hilbert-space structures;
- non-Hilbert objects represented within Hilbert or vector spaces;
- graph, temporal, probabilistic, relational, or other mathematical structures;
- architectural metaphors that require reformulation before they can support mathematical claims.

Using Hilbert-space mathematics does not imply that ALLIS is a physical quantum system.

### Physics and Domain-External Conjectures

Some research documents explore whether relational, contextual, geometric, or admissibility principles discovered through ALLIS could provide useful mathematical lenses in other domains, including foundational physics.

Those ideas remain **outside the current confirmatory claims of ALLIS** unless and until they are separately formalized, compared against existing theory, shown to produce nontrivial consequences, and subjected to appropriate physical experiment.

The existence of a mathematical analogy is not evidence of physical equivalence.

---

## Research Integrity

This repository is intended to preserve a strict claim hierarchy.

### Implemented

A component, path, or behavior exists in the qualified implementation.

### Observed

The behavior has been directly observed under documented runtime conditions.

### Demonstrated

A controlled test or experiment has produced evidence supporting the claim.

### Formally Specified

The claim has been expressed in an explicit mathematical or logical model.

### Proven

The claim follows from the formal model under stated assumptions.

### Machine-Checked

A suitable formal method or verification system has independently checked the derivation or invariant.

### Correspondence-Verified

Evidence supports that the formal object actually maps to the qualified source and observed runtime.

These statuses are not interchangeable.

A documented idea is not automatically implemented.  
An implemented capability is not automatically demonstrated.  
A demonstration is not automatically a mathematical proof.  
A mathematical proof is not automatically proof of implementation correspondence.  
A computational property is not automatically a claim about phenomenal consciousness or physical reality.

---

## Intellectual Property and Licensing Boundary

The broader contract and licensing record identifies ALLIS, GBIM, related proprietary models, technical frameworks, commercial system elements, and pre-existing technical materials as retained KTS/Contractor intellectual property except where a separate signed agreement expressly provides otherwise.

Use of ALLIS by nonprofit, Commons, MountainShares, corridor, institutional, or community partners may occur under project-use rights, licensing, hosting, maintenance, support, or other written agreements.

Publication of research documentation in this repository should not be interpreted as an implied transfer of ownership of the underlying proprietary system.

Specific source-code licensing, research-data licensing, documentation licensing, trademarks, deployment rights, and commercial-use rights should be governed by the applicable repository license and written agreements.

---

## What This Repository Does Not Claim

This repository does not claim, merely by documenting the system, that:

- ALLIS has completed formal verification;
- every architectural object is a mathematically proven Hilbert structure;
- every claimed system behavior has already been empirically validated;
- every mathematical model already corresponds to production source and runtime;
- Ms. Allis possesses independent governance or ownership authority;
- MountainShares owns ALLIS;
- KTS owns MountainShares community governance or participant accounts;
- computational subjectivity establishes phenomenal consciousness;
- semantic or computational geometry is physically identical to quantum or spacetime geometry;
- current physics conjectures have been experimentally established;
- a hypothesis becomes knowledge because the system generated or retained it.

Claims should be promoted only when the appropriate evidence supports that promotion.

---

## Planned Repository Organization

The repository is expected to develop along the following structure:

```text
ALLIS/
│
├── README.md
│
├── architecture/
│   ├── system-boundary/
│   ├── state-models/
│   ├── trust-and-authority/
│   └── deployment-model/
│
├── acceptance/
│   ├── qualified-baseline/
│   └── closeout/
│
├── claims/
│   ├── claim-inventory/
│   ├── definitions/
│   └── nonclaims/
│
├── measurements/
│   ├── protocols/
│   ├── metrics/
│   └── results/
│
├── mathematics/
│   ├── foundations/
│   ├── state-spaces/
│   ├── invariants/
│   └── theorems/
│
├── formal-verification/
│   ├── specifications/
│   ├── proofs/
│   ├── model-checks/
│   └── counterexamples/
│
├── correspondence/
│   ├── model-to-source/
│   ├── source-to-runtime/
│   └── discrepancy-register/
│
├── evidence/
│   ├── reproducibility/
│   ├── validation-bundles/
│   └── provenance/
│
├── research/
│   ├── meaning-requires-geometry/
│   ├── governed-state/
│   ├── cognitive-state/
│   └── future-work/
│
└── publications/
    ├── manuscripts/
    ├── preprints/
    └── presentations/
```

The directory structure may evolve as the qualified system and formal research program mature. Changes to organization should not silently alter claim status, evidence lineage, or the relationship between research documents and the implementation they describe.

---

## Relationship Between Engineering and Research

ALLIS is both an engineering system and a research instrument.

Engineering asks:

> **Does the system work accurately, safely, reproducibly, and according to its defined boundaries?**

Research asks:

> **What can be measured, modeled, falsified, derived, or proven about the system and the principles instantiated within it?**

Those questions inform each other but should not be collapsed into one.

The engineering system provides the qualified object.

The measurement program provides empirical evidence.

The mathematical program provides formal structure.

The correspondence program determines whether those layers actually describe the same system.

---

## Guiding Principle

> **State does not become authority merely because it exists.**

That principle applies not only to ALLIS runtime state, but also to the research program itself.

A conjecture is not knowledge because it is interesting.  
A model is not physical reality because it is mathematically elegant.  
A proof is not implementation evidence unless correspondence is established.  
An observation is not a universal claim without appropriate replication and scope.

ALLIS is being developed to preserve those distinctions.

---

## Project Stewardship

**Kidd’s Technical Services**  
Mount Hope, West Virginia

ALLIS is an active research and engineering program. Repository content should be interpreted according to the status, evidence, version, and scope attached to each claim or artifact.
