# Correspondence

## Connecting formal claims to implemented and observed system state

This directory contains ALLIS correspondence records.

The correspondence layer exists to answer a simple but important question:

> **Does the system described by the formal model correspond to the source and runtime that actually exist?**

ALLIS keeps three things separate:

```text
formal model
    ↓
what the system is mathematically claimed to do

source implementation
    ↓
what the sealed production code actually implements

runtime state
    ↓
what source and behavior are actually present in the deployed system
```

Correspondence connects those layers with evidence.

It does not assume they are equivalent.

---

## Why correspondence matters

A formal model can be correct as mathematics while still failing to describe the deployed implementation.

Likewise, source code can implement a modeled property while the live runtime is running different bytes, a different configuration, or a different trust state.

ALLIS therefore does not treat:

```text
model written
```

as equivalent to:

```text
source implements model
```

and does not treat:

```text
source implements model
```

as equivalent to:

```text
runtime is running that source
```

The correspondence layer makes those transitions explicit.

---

## Correspondence chain

The current ALLIS correspondence model is:

```text
FORMAL MODEL
     ↓
model-to-source correspondence
     ↓
SEALED PRODUCTION SOURCE
     ↓
source-to-runtime correspondence
     ↓
LIVE RUNTIME
     ↓
theorem-specific live observation
```

In compact form:

```math
F
\overset{C_{FS}}{\longrightarrow}
S
\overset{C_{SR}}{\longrightarrow}
R
```

where:

- `F` is a bounded formal model;
- `S` is the sealed source object to which that model is bound; and
- `R` is the inspected runtime state.

For theorem-level correspondence, runtime behavior may also need to be observed.

---

## Current correspondence packages

The current directory structure is:

```text
correspondence/
├── README.md
└── authorized-adoption/
    ├── model-to-source.md
    └── source-to-runtime.md
```

The current production correspondence package is:

```text
authorized-adoption/
```

It documents correspondence for the bounded production authorized-adoption model:

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

at production source commit:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

---

## Model-to-source correspondence

The first correspondence boundary asks:

> **Does the formal model map to behavior actually implemented in the sealed production source?**

The current authorized-adoption package establishes:

```math
C_{FS}(F,S)=1
```

for the bounded production authorized-adoption domain.

The corresponding record is:

```text
authorized-adoption/model-to-source.md
```

That document maps formal objects such as:

```text
candidate
authorization
signature verification
NBB validation
authorized publication
worker claim
target validation
prestate validation
one-use authorization
governed application
receipt
terminalization
```

to the sealed production implementation that gives them operational meaning.

---

## Source-to-runtime correspondence

The second boundary asks:

> **Was the sealed source actually present in the inspected live runtime?**

The current authorized-adoption package establishes, at the final Step-12 seal:

```text
NBB source correspondence     11/11 PASS
Worker source correspondence  11/11 PASS
```

The corresponding record is:

```text
authorized-adoption/source-to-runtime.md
```

The runtime comparison is based on the sealed source identities, not merely matching filenames or module names.

---

## Correspondence is not just source identity

Source identity is necessary, but it is not the entire correspondence problem.

The current Step-12 runtime state also separately records:

```text
Public trust     PASS
Governance view  PASS
NBB health       PASS
Worker health    PASS
Host health      PASS
Authorized spool PASS_EMPTY
```

These are different evidence objects.

For example:

```text
source matches
≠
trust anchor matches
```

and:

```text
trust anchor matches
≠
governance state matches
```

ALLIS preserves those distinctions rather than collapsing them into one generic statement that the system "matched."

---

## Correspondence and theorem validation

A theorem does not become correspondence-verified merely because the runtime contains matching source.

The Step-12 theorem-correspondence criterion is:

```math
MC(T,S)
\land
C_{SR}(S,R)
\land
LiveObs(T,R)
```

where:

- `MC(T,S)` means the theorem was machine-checked against the sealed source;
- `C_SR(S,R)` means that source corresponded to the runtime; and
- `LiveObs(T,R)` means the relevant behavior was actually observed live.

This distinction explains why the current validation levels differ:

```text
T12D-A = MACHINE_CHECKED
T12D-B = CORRESPONDENCE_VERIFIED
T12D-C = CORRESPONDENCE_VERIFIED
```

For `T12D-A`, the positive live production path was not exercised.

Therefore:

```text
runtime source matched theorem source
≠
positive theorem behavior observed
```

---

## Correspondence is point-in-time

Runtime correspondence is temporal.

A successful correspondence result means:

> **The inspected runtime matched the sealed source and related evidence objects at the time of the correspondence check.**

It does not mean:

> The runtime can never change.

Conceptually:

```math
C_{SR}^{\tau_{seal}}(S,R)=1
```

does not imply:

```math
\forall \tau>\tau_{seal},
C_{SR}^{\tau}(S,R)=1
```

without future revalidation.

The current Step-12 residual preserves this as:

```text
R12F-07 = POINT_IN_TIME_BINDING
```

A changed runtime must earn a new correspondence result.

---

## Correspondence does not create authority

Correspondence establishes identity and relationship.

It does not authorize an operation.

```text
formal model corresponds to source
≠
production mutation authorized
```

```text
runtime source corresponds to sealed source
≠
production mutation authorized
```

```text
public trust matches
≠
runtime possesses private signing authority
```

```text
governance view matches
≠
runtime may invent an approval decision
```

The correspondence layer answers:

> **Is this the system we think it is?**

The authority layer answers:

> **May this exact action occur now?**

Those are separate questions.

---

## Correspondence does not imply whole-system proof

The current correspondence package is bounded.

It does not establish:

```text
all ALLIS source is formally modeled
```

It does not establish:

```text
every runtime behavior has been observed
```

It does not establish:

```text
all production mutation is safe
```

It does not establish:

```text
whole-system safety
```

The controlling Step-12 boundaries remain:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

---

## Relationship to formal verification

The correspondence layer should be read with:

```text
formal-verification/
```

Formal verification answers:

> **What mathematical object is being studied, and what propositions were established or disproven?**

Correspondence answers:

> **Does that formal object map to the implementation and runtime being discussed?**

In the current authorized-adoption package:

```text
formal-verification/authorized-adoption/
        ↓
defines and adjudicates the formal object

correspondence/authorized-adoption/
        ↓
binds that formal object to source and runtime
```

---

## Relationship to evidence

The correspondence layer should also be read with:

```text
evidence/
```

Evidence preserves:

- source identity;
- trust identity;
- governance identity;
- residuals;
- non-promotions; and
- final seal state.

The relationship is:

```text
evidence
    ↓
defines and preserves authoritative identities

correspondence
    ↓
compares those identities across model, source, and runtime
```

Correspondence depends on evidence but is not the same thing as evidence.

---

## Current authorized-adoption result

The current bounded correspondence package supports:

```text
Formal-to-source correspondence   PASS
NBB source correspondence         11/11 PASS
Worker source correspondence      11/11 PASS
Public trust                      PASS
Governance view                   PASS
```

under the Step-12 final state:

```text
GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS
```

The controlling final seal is:

```text
STEP12_FINAL_THEOREM_AND_FORMAL_CORRESPONDENCE_SEALED_GREEN_WITH_EXPLICIT_RESIDUALS
```

The final evidence SHA-256 is:

```text
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

The controlling scope is:

```text
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

---

## What belongs in `correspondence/`

A record belongs in this directory when its primary purpose is to establish or explain a mapping between evidence domains.

Examples include:

```text
formal model
→
source implementation
```

```text
sealed source
→
runtime source
```

```text
sealed trust object
→
runtime trust object
```

```text
sealed governance object
→
runtime governance view
```

or another explicitly defined correspondence boundary.

---

## What does not belong in `correspondence/`

This directory should not become a duplicate of other repository layers.

Use:

```text
formal-verification/
```

for models, theorems, proposition status, and counterexamples.

Use:

```text
evidence/
```

for canonical identities, hashes, seals, residuals, and non-promotions.

Use:

```text
architecture/
```

for explanatory system design.

Use:

```text
acceptance/
```

for qualified-baseline admission and acceptance records.

Correspondence should remain focused on the evidence-backed relationship between defined objects.

---

## Core commitment

The correspondence layer exists to enforce one rule:

> **A claim about one system state cannot be silently promoted into a claim about another system state.**

For ALLIS:

```text
model describes it
≠
source implements it

source implements it
≠
runtime is running it

runtime is running it
≠
theorem behavior was observed

theorem behavior was observed once
≠
future runtime correspondence is guaranteed
```

Correspondence is the evidence bridge between those states.

It is not a shortcut to authority, and it is not a whole-system proof.
