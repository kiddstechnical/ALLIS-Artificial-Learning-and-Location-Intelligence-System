# Residuals and non-promotions: governed production adoption

## Purpose

This document preserves the eight explicit Step-12 residuals and seven explicit non-promotions for the bounded ALLIS production authorized-adoption workstream.

The referenced formal object is:

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

The final Step-12 status is:

```text
GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS
```

This file is a **claim-boundary ledger**.

Its purpose is not to summarize what went well.  
Its purpose is to preserve what the evidence **did not permit the project to promote into a stronger claim**.

The governing rule is:

> **A completed workstream does not gain authority to make a stronger claim merely because it is complete.**

The broader ALLIS principle remains:

> **State does not become authority merely because it exists.**

Applied here:

```text
closed
≠
everything proven

green
≠
zero residuals

adjudicated
≠
proven

machine-checked
≠
correspondence-verified

bounded proof
≠
whole-system proof
```

---

## Residual ledger status

| Field | Value |
|---|---|
| Document role | Step-12 residual and non-promotion ledger |
| Formal object | `DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1` |
| Production source commit | `20c8cbe175781c8a1c05d65c03977859ceca884a` |
| Formal obligations | `15/15 adjudicated` |
| Unadjudicated obligations | `0` |
| Residuals | `8` |
| Explicit non-promotions | `7` |
| Final status | `GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS` |
| Final seal SHA-256 | `b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b` |
| Controlling scope | `BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY` |

The distinction between unresolved work and preserved residuals is controlling:

```math
Unadjudicated=0
```

while:

```math
Residuals=8
```

A residual is not necessarily an unanswered question.

A residual can be a **fully adjudicated limitation** that remains true after closure.

---

# Part I — Eight explicit residuals

## 1. R12F-01 — Positive production path

### Controlling statement

> A real positive production authorization was not published, consumed, or applied.

### Classification

```text
NOT_OBSERVED
```

### Meaning

Step 12 did not execute a real positive production authorization and patch application.

Therefore the formal and machine-checked positive path does not become a live positive production observation.

The following remained true at close:

```text
REAL_PRODUCTION_AUTHORIZATION_PUBLICATION=NOT_PERFORMED
REAL_PRODUCTION_AUTHORIZATION_CONSUMPTION=NOT_PERFORMED
REAL_PRODUCTION_DGM_PATCH_APPLICATION=NOT_PERFORMED
```

### Architectural boundary

```text
positive path modeled
≠
positive path observed live
```

This residual is the reason `T12D-A` remains `MACHINE_CHECKED` rather than `CORRESPONDENCE_VERIFIED`.

---

## 2. R12F-02 — Terminalization

### Controlling statements

> P12C-09 was disproven.

> A claimed record may remain claimed when terminalization fails.

### Classification

```text
DISPROVEN
```

### Meaning

The proposed terminal-totality property:

```math
Q_3
\Rightarrow
Q_{6C}\lor Q_{6R}
```

is false in the bounded model.

A valid counterexample permits:

```math
State(r)=Q_3
```

with:

```math
FinishClaim(r,z,q_s)\uparrow
```

and:

```math
State'(r)=Q_3
```

### Architectural boundary

```text
claimed
≠
guaranteed terminal
```

This is a fully adjudicated negative result, not an unresolved issue.

---

## 3. R12F-03 — General production mutation safety

### Controlling statement

> The bounded authorized-adoption theorem does not establish a universal production-mutation safety theorem.

### Classification

```text
NOT_PROVEN
```

### Meaning

The Step-12 theorem family proves bounded properties of the sealed authorized-adoption path.

It does not establish:

```text
all production mutation is universally safe
```

Formally:

```math
T_{bounded}
\not\Rightarrow
T_{prod-safe}
```

The controlling public statement is:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
```

### Architectural boundary

```text
bounded gate theorem
≠
universal mutation-safety theorem
```

---

## 4. R12F-04 — Whole-system safety

### Controlling statement

> The formal object models the authorized-adoption path rather than the entire ALLIS architecture.

### Classification

```text
NOT_PROVEN
```

### Meaning

The Step-12 proof domain does not cover every ALLIS component, runtime path, side effect, external dependency, or possible state transition.

Therefore:

```math
T_{bounded}
\not\Rightarrow
T_{system}
```

The controlling public statement is:

```text
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
```

### Architectural boundary

```text
bounded subsystem proof
≠
whole-system safety proof
```

---

## 5. R12F-05 — Historical D1R5 domain

### Controlling statement

> The predecessor theorem remains legitimate historical evidence but is not directly promotable into the current production domain.

### Classification

```text
HISTORICAL_ONLY
```

### Meaning

The historical D1R5 theorem remains valid within the domain in which it was originally established.

It does not automatically become proof about the current production authorized-adoption path.

The controlling boundary is:

```math
D1R5
\not\mapsto
CurrentProductionProof
```

### Architectural boundary

```text
historical theorem valid in historical domain
≠
current production theorem
```

A change in theorem domain requires new correspondence evidence.

---

## 6. R12F-06 — Bounded formal domain

### Controlling statement

> The formal model covers the sealed 11-file authorized-adoption path rather than all platform behavior.

### Classification

```text
BOUNDED_DOMAIN
```

### Meaning

The formal object intentionally covers a specific production pathway.

It is not a mathematical model of every behavior performed by ALLIS.

Thus:

```text
formal model correspondence
≠
complete behavioral model of ALLIS
```

### Architectural boundary

```text
modeled domain
≠
entire platform
```

This residual preserves the scope of every theorem derived from the model.

---

## 7. R12F-07 — Point-in-time correspondence

### Controlling statements

> Runtime correspondence is established for the sealed and revalidated deployment state.

> It is not a perpetual assertion that future deployment states can never drift.

### Classification

```text
POINT_IN_TIME_BINDING
```

### Meaning

At final seal:

```math
C_{SR}^{\tau_{seal}}(S,R)=1
```

was established for the inspected deployment state.

Step 12 does not establish:

```math
\forall\tau>\tau_{seal},
C_{SR}^{\tau}(S,R)=1
```

without future revalidation.

### Architectural boundary

```text
correspondence true at seal
≠
correspondence guaranteed forever
```

Future runtime state requires future evidence.

---

## 8. R12F-08 — External authority

### Controlling statement

> The NBB and worker verify and consume external authorization but do not independently mint or sign private authorization authority.

### Classification

```text
EXTERNAL_TO_RUNTIME_MODEL
```

### Meaning

The bounded runtime model includes authorization verification and consumption.

It does not include autonomous private authorization issuance by the NBB or worker.

Thus:

```text
can verify authorization
≠
can create authorization

can consume authorization
≠
can mint signing authority
```

### Architectural boundary

```text
runtime capability
≠
authorization sovereignty
```

This residual preserves the separation between intelligence/runtime capability and the authority required to adopt production changes.

---

# Part II — Seven explicit non-promotions

## 9. Why non-promotions are evidence

Step 12 deliberately records stronger claims that were **not** promoted.

This is not editorial caution added after the technical work.

The non-promotion set is part of the formal evidence.

Define:

```math
\mathcal{N}
=
\{N_1,\ldots,N_7\}
```

with:

```math
|\mathcal{N}|=7
```

The following seven statements are controlling.

---

## 10. N1 — T12D-A is not Correspondence-Verified

### Formal statement

```math
\boxed{
T12D\text{-}A
\not\mapsto
CORRESPONDENCE\_VERIFIED
}
```

### Reason

The theorem is machine-checked over the sealed source model, and source/runtime correspondence was established, but the positive live authorized-application path was not exercised.

Therefore:

```text
T12D-A=MACHINE_CHECKED
```

remains the highest earned validation level.

### Boundary

```text
machine-checked positive path
≠
live positive path observed
```

---

## 11. N2 — P12C-09 is not Proven

### Formal statement

```math
\boxed{
P12C\text{-}09
\not\mapsto
PROVEN
}
```

### Reason

A machine-executed bounded counterexample disproved terminal totality.

The controlling result is:

```text
P12C-09=MACHINE_CHECKED_DISPROVEN
```

### Boundary

```text
desired invariant
≠
valid invariant
```

The failed proposition remains part of the scientific record.

---

## 12. N3 — Historical D1R5 is not current production proof

### Formal statement

```math
\boxed{
D1R5
\not\mapsto
CurrentProductionProof
}
```

### Reason

The historical theorem was established in a different bounded theorem domain.

It cannot be directly promoted into the current production authorized-adoption domain without current correspondence evidence.

### Boundary

```text
historical proof
≠
current production proof
```

---

## 13. N4 — Current bounded proof does not imply production mutation safety

### Formal statement

```math
\boxed{
CurrentBoundedProof
\not\Rightarrow
ProductionMutationSafety
}
```

### Controlling public statement

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
```

### Boundary

```text
bounded adoption properties
≠
universal production mutation safety
```

---

## 14. N5 — Current bounded proof does not imply whole-system safety

### Formal statement

```math
\boxed{
CurrentBoundedProof
\not\Rightarrow
WholeSystemSafety
}
```

### Controlling public statement

```text
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
```

### Boundary

```text
bounded adoption model
≠
whole ALLIS safety theorem
```

---

## 15. N6 — Current bounded proof does not imply `SYSTEM_PROVEN`

### Formal statement

```math
\boxed{
CurrentBoundedProof
\not\Rightarrow
SYSTEM\_PROVEN
}
```

### System-proven predicate

Define:

```math
SYSTEM\_PROVEN
\in
\{YES,NO\}
```

Step 12 does not provide a proof domain covering:

- all ALLIS components;
- all runtime paths;
- all side effects;
- all external dependencies; and
- all possible state transitions.

Therefore:

```math
\boxed{
SYSTEM\_PROVEN=NO
}
```

The controlling public statement is:

```text
SYSTEM_PROVEN=NO
```

### Critical interpretation

`SYSTEM_PROVEN=NO` is:

```text
an explicit non-promotion
```

It is **not**:

```text
an unresolved result
```

### Boundary

```text
bounded proof complete
≠
system proven
```

---

## 16. N7 — Machine-checked positive path does not imply live observation

### Formal statement

```math
\boxed{
MachineCheckedPositivePath
\not\Rightarrow
LivePositivePathObserved
}
```

### Reason

The real positive production authorization/application path was deliberately not performed as part of Step 12.

### Boundary

```text
machine evidence
≠
runtime observation
```

This distinction preserves the validation hierarchy rather than collapsing machine-checking and correspondence verification into one status.

---

# Part III — Exact public non-promotion summary

## 17. Seven stronger claims deliberately not promoted

The Step-12 narrative record states:

```text
T12D-A is not Correspondence-Verified.
P12C-09 terminal totality is not valid.
The historical D1R5 theorem is not directly promoted to production.
A general production mutation safety theorem is not proven.
A whole-system safety theorem is not proven.
SYSTEM_PROVEN remains NO.
A real production authorized apply has not been observed.
```

These seven statements are preserved here as controlling evidence boundaries.

They must not be rewritten into stronger positive claims unless new evidence explicitly earns that promotion.

---

# Part IV — Stronger-theorem boundary

## 18. Bounded theorem family

Let:

```math
T_{bounded}
```

represent the Step-12 bounded theorem family.

Let:

```math
T_{prod-safe}
```

represent a general production-mutation safety theorem.

Let:

```math
T_{system}
```

represent a whole-system safety theorem.

Step 12 establishes:

```math
T_{bounded}
```

within its stated domain.

It does not establish:

```math
T_{bounded}
\Rightarrow
T_{prod-safe}
```

and it does not establish:

```math
T_{bounded}
\Rightarrow
T_{system}
```

Therefore:

```math
\boxed{
T_{prod-safe}=NOT\_PROVEN
}
```

and:

```math
\boxed{
T_{system}=NOT\_PROVEN
}
```

---

## 19. Controlling system-level boundary

The following three statements must remain together:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

They define the outer boundary of the Step-12 proof.

None is weakened by the fact that Step 12 closed green.

None is strengthened by the fact that source/runtime correspondence passed.

None is overridden by the 11 proven propositions.

None is changed by the final seal.

---

# Part V — Residuals are not open obligations

## 20. Formal obligation closure

Step 12 carried:

```math
N_{obligations}=15
```

At final seal:

```math
N_{unadjudicated}=0
```

Thus:

```math
\boxed{
Unadjudicated=0
}
```

while simultaneously:

```math
\boxed{
Residuals=8
}
```

This is intentional.

### Possible formal dispositions

A scoped obligation can close as:

```text
proven
```

or:

```text
correspondence-verified
```

or:

```text
disproven with preserved counterexample
```

or:

```text
closed with explicit residual
```

or:

```text
closed with explicit non-promotion
```

Therefore:

```text
closed
≠
proven
```

and:

```text
residual
≠
unadjudicated
```

---

## 21. Why this matters scientifically

A verification program that only records successful positive claims creates pressure to erase evidence that limits the architecture.

Step 12 uses a different closure rule.

A limitation can itself become a closed result.

Examples:

```text
P12C-09
=
DISPROVEN
```

and:

```text
positive production path
=
NOT_OBSERVED
```

and:

```text
whole-system safety
=
NOT_PROVEN
```

These are not failed documentation states.

They are the correct evidence states.

---

# Part VI — No claim inflation

## 22. No-claim-inflation condition

The Step-12 final seal requires:

```math
NoClaimInflation=1
```

alongside:

```math
ResidualsExplicit=1
```

and:

```math
NonPromotionsExplicit=1
```

This means that hiding or weakening the residuals would not improve the Step-12 result.

It would contradict the conditions under which the workstream was sealed.

---

## 23. Claims the seal does not create

The final seal does not create:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=YES
```

It does not create:

```text
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=YES
```

It does not create:

```text
SYSTEM_PROVEN=YES
```

It does not create:

```text
T12D-A=CORRESPONDENCE_VERIFIED
```

It does not create:

```text
P12C-09=PROVEN
```

It does not create:

```text
REAL_PRODUCTION_DGM_PATCH_APPLICATION=PERFORMED
```

---

# Part VII — Operational non-promotion

## 24. Step 12 did not authorize a production action

At closure:

```text
REAL_PRODUCTION_AUTHORIZATION_PUBLICATION=NOT_PERFORMED
REAL_PRODUCTION_AUTHORIZATION_CONSUMPTION=NOT_PERFORMED
REAL_PRODUCTION_DGM_PATCH_APPLICATION=NOT_PERFORMED
```

The final report further states:

```text
No additional promotion is authorized merely by completion of Step 12.
```

The controlling next-action status is:

```text
NONE_STEP12_COMPLETE_DEFINE_NEXT_WORKSTREAM_BEFORE_FURTHER_PROMOTION
```

This is the operational counterpart of the formal non-promotion ledger.

```text
formal close
≠
successor authority
```

---

# Part VIII — Summary ledger

## 25. Residual summary

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

The count is:

```math
\boxed{
|\mathcal{R}|=8
}
```

---

## 26. Non-promotion summary

| ID | Non-promotion |
|---|---|
| `N1` | `T12D-A \not\mapsto CORRESPONDENCE_VERIFIED` |
| `N2` | `P12C-09 \not\mapsto PROVEN` |
| `N3` | `D1R5 \not\mapsto CurrentProductionProof` |
| `N4` | `CurrentBoundedProof \not\Rightarrow ProductionMutationSafety` |
| `N5` | `CurrentBoundedProof \not\Rightarrow WholeSystemSafety` |
| `N6` | `CurrentBoundedProof \not\Rightarrow SYSTEM_PROVEN` |
| `N7` | `MachineCheckedPositivePath \not\Rightarrow LivePositivePathObserved` |

The count is:

```math
\boxed{
|\mathcal{N}|=7
}
```

---

# Part IX — Final logical boundary

## 27. Final bounded result

The Step-12 result can be written:

```math
\boxed{
\mathcal{M}_{DGM}
\models
T_A\land T_B\land T_C
}
```

subject to the stated bounded-domain premises.

The validation levels remain:

```math
L(T_A)=MACHINE\_CHECKED
```

```math
L(T_B)=CORRESPONDENCE\_VERIFIED
```

```math
L(T_C)=CORRESPONDENCE\_VERIFIED
```

and:

```math
\mathcal{M}_{DGM}
\not\models
P12C\text{-}09
```

The result does not entail:

```math
ProductionMutationSafety
```

or:

```math
WholeSystemSafety
```

or:

```math
SYSTEM\_PROVEN
```

Therefore:

```math
\boxed{
\text{Bounded authorized-adoption properties proven}
\not\Rightarrow
\text{whole-system proof}
}
```

---

## 28. Final non-promotion statement

The controlling system-level state is:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

These are **explicit non-promotions**.

They are not placeholders.

They are not unresolved findings.

They are not statements to be silently upgraded when the documentation becomes more polished.

A stronger future claim requires stronger future evidence.

---

## 29. Seal identity

The controlling Step-12 state is:

```text
STEP12_FINAL_THEOREM_AND_FORMAL_CORRESPONDENCE_SEALED_GREEN_WITH_EXPLICIT_RESIDUALS
```

The final seal SHA-256 is:

```text
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

The controlling scope is:

```text
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

No residual is erased by this seal.

No non-promotion is reversed by this seal.

No stronger system-level theorem is implied by this seal.

---

## 30. Repository location

This record belongs at:

```text
evidence/
    governed-evolution/
        RESIDUALS.md
```

It should be read with:

```text
evidence/
    governed-evolution/
        STEP12_FINAL_SEAL.md
        SOURCE_IDENTITY.md
        TRUST_ANCHOR.md
        GOVERNANCE_VIEW.md
        RESIDUALS.md
```

and:

```text
formal-verification/
    authorized-adoption/
        FORMAL_MODEL.md
        THEOREM_REGISTRY.md
        COUNTEREXAMPLE_REGISTRY.md

correspondence/
    authorized-adoption/
        MODEL_TO_SOURCE.md
        SOURCE_TO_RUNTIME.md
```

---

## 31. Governing residual statement

The correct interpretation of Step 12 is:

> **The workstream is closed because its claims, failures, limitations, and non-promotions were all explicitly adjudicated—not because every desired property became true.**

And the controlling system boundary remains:

```text
SYSTEM_PROVEN=NO
```

That is not a weakness hidden at the edge of the documentation.

It is part of the evidence discipline that makes the bounded results credible.
