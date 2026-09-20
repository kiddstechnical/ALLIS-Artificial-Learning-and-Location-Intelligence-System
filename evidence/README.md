# Evidence

## Evidence that constrains the claim

This directory contains the public, non-sensitive evidence records used to support and bound technical claims made elsewhere in the ALLIS repository.

The evidence layer answers a specific question:

> **What record supports this claim, what exact object does that record refer to, and what does the evidence still not permit us to claim?**

The governing rule is:

> **Evidence may justify a claim. Evidence does not create authority beyond the claim it actually supports.**

In ALLIS, evidence is kept separate from architecture, mathematics, source code, and operational authority.

```text
architecture
    ↓
describes the intended system

formal verification
    ↓
states and adjudicates mathematical claims

correspondence
    ↓
maps model → source → runtime

evidence
    ↓
preserves identities, observations, seals,
residuals, and provenance

authority
    ↓
governs whether an exact action may occur
```

These layers inform one another, but they are not interchangeable.

---

## Why the evidence layer exists

A technical system can become misleading if successful results are preserved while failed claims, counterexamples, residuals, source identities, or scope boundaries are forgotten.

ALLIS therefore treats evidence as a first-class part of the architecture.

The evidence layer is intended to preserve:

- exactly which source object a result applies to;
- which runtime state was observed;
- which trust object was present;
- which governance object was present;
- which formal obligations were closed;
- which propositions were proven;
- which propositions were disproven;
- which stronger claims were deliberately not promoted;
- which residuals remain true after closure; and
- which final seal identifies the completed evidence state.

This allows later reviewers to distinguish:

```text
what was intended
≠
what was implemented

what was implemented
≠
what was observed

what was observed
≠
what was proven

what was proven
≠
what was correspondence-verified

what was verified
≠
what is authorized now
```

---

# Current evidence packages

The evidence directory is organized by technical workstream.

The current governed-evolution evidence package is:

```text
evidence/
├── README.md
└── governed-evolution/
    ├── source-identity.md
    ├── trust-anchor.md
    ├── governance-view.md
    ├── residuals.md
    └── step12-final-seal.md
```

Future ALLIS workstreams may add separate evidence directories rather than mixing unrelated evidence into one package.

---

# Governed-evolution evidence

The current governed-evolution evidence package supports the bounded production authorized-adoption formal object:

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

The controlling production source commit is:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

The final Step-12 status is:

```text
GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS
```

The controlling final seal is:

```text
STEP12_FINAL_THEOREM_AND_FORMAL_CORRESPONDENCE_SEALED_GREEN_WITH_EXPLICIT_RESIDUALS
```

The final Step-12 evidence identity is:

```text
SHA-256
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

The controlling scope is:

```text
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

That scope is part of the evidence.

The seal does not enlarge it.

---

## Current Step-12 evidence state

The current bounded result records:

```text
12 formal propositions
11 proven
1 disproven
0 unadjudicated
```

The principal validation levels are:

```text
T12D-A = MACHINE_CHECKED
T12D-B = CORRESPONDENCE_VERIFIED
T12D-C = CORRESPONDENCE_VERIFIED
P12C-09 = MACHINE_CHECKED_DISPROVEN
```

The runtime source-correspondence result at final seal is:

```text
NBB source correspondence     11/11 PASS
Worker source correspondence  11/11 PASS
```

The final bounded runtime state also records:

```text
Public trust     PASS
Governance view  PASS
NBB health       PASS
Worker health    PASS
Host health      PASS
Authorized spool PASS_EMPTY
```

Step 12 carried fifteen formal obligations.

At final seal:

```text
15/15 adjudicated
0 unadjudicated
```

The package nevertheless preserves:

```text
8 residuals
7 explicit non-promotions
```

This is intentional.

```text
closed
≠
everything proven
```

---

# How to read this directory

## 1. Start with `step12-final-seal.md`

Use:

```text
governed-evolution/step12-final-seal.md
```

for the package-level evidence state.

It ties together:

- the formal object;
- the production source commit;
- proposition adjudication;
- obligation closure;
- source correspondence;
- public trust;
- governance correspondence;
- residuals;
- non-promotions;
- final scope; and
- final evidence identity.

This is the best starting point for a reviewer who wants to understand what Step 12 actually closed.

---

## 2. Use `source-identity.md` for the source object

Use:

```text
governed-evolution/source-identity.md
```

to identify the exact source domain to which the bounded formal result applies.

The controlling source commit is:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

The Step-12 source domain contains:

```text
11 governed production source files
```

The complete per-file source manifest should only contain filenames and hashes transcribed from the sealed source-manifest evidence.

It must not be reconstructed from memory, inferred from referenced modules, or filled with plausible filenames.

The source identity record therefore owns the question:

> **What exact source object did the formal model and correspondence work refer to?**

---

## 3. Use `trust-anchor.md` for verification trust

Use:

```text
governed-evolution/trust-anchor.md
```

for the public verification trust object.

The sealed production public-key SHA-256 is:

```text
4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5
```

The trust record explains:

- the role of the pinned public verification key;
- its final correspondence result;
- the difference between verification and signing;
- why a valid signature is only one predicate inside complete authorization; and
- why possession of the public key does not authorize production mutation.

The governing distinction is:

```text
can verify authority
≠
can create authority
```

---

## 4. Use `governance-view.md` for sealed governance state

Use:

```text
governed-evolution/governance-view.md
```

for the governance-view identity used at the Step-12 NBB boundary.

The sealed governance-view SHA-256 is:

```text
26523c0bad40ff06a75c62a802f20195295534764dce45cfa6acdcdaecc3fcc2
```

The final Step-12 result established:

```text
Governance view = PASS
```

for the live NBB governance view against the sealed governance object.

This result does not independently authorize a candidate or production mutation.

The governing distinction is:

```text
governance state exists
≠
authority to act exists
```

---

## 5. Use `residuals.md` for the surviving limits

Use:

```text
governed-evolution/residuals.md
```

for the eight explicit residuals and seven explicit non-promotions that remain part of the Step-12 record.

The residuals are:

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

The seven non-promotions preserve that:

```text
T12D-A
↛
CORRESPONDENCE_VERIFIED
```

```text
P12C-09
↛
PROVEN
```

```text
historical D1R5
↛
current production proof
```

```text
current bounded proof
⇏
ProductionMutationSafety
```

```text
current bounded proof
⇏
WholeSystemSafety
```

```text
current bounded proof
⇏
SYSTEM_PROVEN
```

```text
MachineCheckedPositivePath
⇏
LivePositivePathObserved
```

These are evidence boundaries.

They are not documentation gaps.

---

# Evidence and formal verification are different

The formal-verification layer contains the mathematical objects and proposition adjudication.

```text
formal-verification/
    authorized-adoption/
        formal-model.md
        theorem-registry.md
        counterexample-registry.md
```

The evidence layer does not replace those documents.

Instead:

```text
formal-model.md
    ↓
What mathematical object is being studied?

theorem-registry.md
    ↓
Which propositions are proven,
disproven, machine-checked,
or correspondence-verified?

counterexample-registry.md
    ↓
Which proposed universal property
was falsified?

evidence/
    ↓
What source, trust, governance,
runtime, residual, and seal identities
support and constrain those results?
```

---

# Evidence and correspondence are different

The correspondence layer answers:

```text
Does the formal model map to the sealed source?
```

and:

```text
Does the sealed source map to the inspected runtime?
```

The relevant records are:

```text
correspondence/
    authorized-adoption/
        model-to-source.md
        source-to-runtime.md
```

The evidence layer preserves the identities and final state against which those correspondence claims are evaluated.

Therefore:

```text
evidence
≠
correspondence

but

correspondence requires evidence
```

---

# Evidence does not create operational authority

This directory documents what is known.

It does not authorize what the system may do next.

At Step-12 close:

```text
REAL_PRODUCTION_AUTHORIZATION_PUBLICATION=NOT_PERFORMED
REAL_PRODUCTION_AUTHORIZATION_CONSUMPTION=NOT_PERFORMED
REAL_PRODUCTION_DGM_PATCH_APPLICATION=NOT_PERFORMED
```

The evidence seal therefore does not mean:

```text
production mutation authorized
```

It means:

```text
the bounded Step-12 evidence state is closed
```

The difference is central to ALLIS.

---

# Residuals are evidence

Residuals are intentionally preserved rather than treated as embarrassing exceptions.

For Step 12:

```text
Unadjudicated = 0
Residuals     = 8
```

Both statements are true.

A result may be fully adjudicated as:

```text
PROVEN
DISPROVEN
NOT_OBSERVED
NOT_PROVEN
HISTORICAL_ONLY
BOUNDED_DOMAIN
POINT_IN_TIME_BINDING
EXTERNAL_TO_RUNTIME_MODEL
```

A limitation that has been explicitly adjudicated is itself evidence.

---

# Counterexamples are evidence

The machine-executed counterexample to:

```text
P12C-09
```

is not hidden because it disproved a desired property.

It is preserved as a first-class scientific result.

The governing rule is:

> **Evidence constrains the architecture. The architecture does not get to rewrite the evidence.**

A public evidence package that preserved only successful results would be incomplete.

---

# Failed or superseded states should remain traceable

When a later repair or stronger result replaces an earlier state, the earlier state should remain recoverable through repository history, evidence identity, or an explicit supersession record.

ALLIS should not create the appearance that:

```text
the corrected state
was always the state
```

when the evidence shows otherwise.

Where appropriate, preserve:

```text
prior claim
        ↓
counterexample / discrepancy
        ↓
repair
        ↓
new evidence
        ↓
new qualification
```

This keeps the scientific record auditable.

---

# Point-in-time evidence

Runtime evidence is temporal.

For source/runtime correspondence, Step 12 establishes:

```math
C_{SR}^{\tau_{seal}}(S,R)=1
```

at the final seal boundary.

It does not establish:

```math
\forall\tau>\tau_{seal},
C_{SR}^{\tau}(S,R)=1
```

without future revalidation.

The same discipline applies to trust, governance, health, deployment, and other runtime evidence.

```text
observed once
≠
guaranteed forever
```

---

# Public and private evidence

This public repository should expose enough evidence to make technical claims auditable without exposing sensitive operational material.

## Appropriate public evidence includes

- source commit identities;
- non-sensitive source-file hashes;
- public-key hashes;
- governance-object hashes;
- formal-object identifiers;
- theorem validation levels;
- proposition counts;
- residuals;
- non-promotions;
- seal identities;
- public-safe correspondence summaries; and
- public-safe provenance descriptions.

## Evidence that should remain private includes

- private signing keys;
- passwords;
- tokens;
- active credentials;
- secret material;
- live authorization artifacts where disclosure would weaken controls;
- unnecessary internal network details;
- sensitive runtime configuration;
- exploit-relevant security details; and
- evidence containing private personal information.

Public transparency does not require publishing secrets.

---

# What belongs in `evidence/`

A record belongs in this directory when its primary purpose is to preserve:

- an evidence identity;
- a cryptographic identity;
- a source identity;
- an observed runtime state;
- a correspondence-supporting artifact;
- an obligation disposition;
- a residual;
- a non-promotion;
- a final seal;
- a public-safe evidence manifest; or
- provenance required to audit a technical claim.

---

# What does not belong in `evidence/`

This directory should not become a catch-all for every project document.

The following belong elsewhere:

```text
architecture/
```

for explanatory system design;

```text
formal-verification/
```

for mathematical models, theorems, proof status, and counterexamples;

```text
correspondence/
```

for formal-to-source and source-to-runtime mappings;

```text
acceptance/
```

for qualified-baseline admission and acceptance status;

```text
measurements/
```

for measurement definitions and reproducible empirical quantities;

and private operational storage for secrets, credentials, raw sensitive runtime bundles, and other non-public evidence.

---

# Naming and identity rules

Evidence records should use stable, descriptive names.

Prefer:

```text
source-identity.md
trust-anchor.md
governance-view.md
residuals.md
step12-final-seal.md
```

over ambiguous names such as:

```text
notes.md
final.md
results2.md
latest.md
```

Where an evidence object has a cryptographic identity, record the exact algorithm and digest.

Where an evidence object is bound to a commit, record the full commit identity.

Where an observation is point-in-time, say so explicitly.

Where a source domain is bounded, state the boundary explicitly.

---

# Claim-preservation rules

An evidence record should never silently convert:

```text
MACHINE_CHECKED
```

into:

```text
CORRESPONDENCE_VERIFIED
```

It should never convert:

```text
NOT_OBSERVED
```

into:

```text
OBSERVED
```

It should never convert:

```text
NOT_PROVEN
```

into:

```text
PROVEN
```

And it should never convert:

```text
SYSTEM_PROVEN=NO
```

into:

```text
SYSTEM_PROVEN=YES
```

without a new evidence basis that explicitly earns that promotion.

---

# Current whole-system boundary

The Step-12 governed-evolution package does not establish a whole-system ALLIS proof.

The controlling statements remain:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

These are explicit non-promotions.

They are not unresolved placeholders.

The bounded Step-12 result remains scientifically meaningful without being expanded into a whole-system claim.

---

# Evidence chain

The current governed-evolution evidence chain can be read as:

```text
sealed source identity
        ↓
formal object derived from source
        ↓
formal propositions adjudicated
        ↓
counterexample preserved
        ↓
model-to-source correspondence
        ↓
source-to-runtime correspondence
        ↓
trust and governance identities checked
        ↓
residuals and non-promotions preserved
        ↓
final Step-12 seal
```

The final seal binds the package together.

It does not erase the different evidentiary roles of the records inside it.

---

# Core commitment

The evidence layer exists to enforce a simple rule:

> **A claim may advance only as far as its evidence supports.**

For ALLIS, that means:

```text
evidence exists
≠
authority exists

evidence supports a bounded claim
≠
evidence supports every stronger claim

seal exists
≠
future state automatically inherits the seal

proof exists
≠
production action is authorized
```

The purpose of `evidence/` is to make those distinctions durable, reviewable, and difficult to accidentally erase.
