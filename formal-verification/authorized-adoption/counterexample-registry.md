<div align="center">

# ALLIS — Counterexample Registry

### Preserved falsifying cases from the bounded Step-12 production authorized-adoption formal model

<br>

![Formal Verification](https://img.shields.io/badge/FORMAL_VERIFICATION-COUNTEREXAMPLE_REGISTRY-7c3aed?style=for-the-badge)
![Counterexamples](https://img.shields.io/badge/COUNTEREXAMPLES-1-0ea5e9?style=for-the-badge)
![Proposition](https://img.shields.io/badge/P12C--09-DISPROVEN-dc2626?style=for-the-badge)
![Validation](https://img.shields.io/badge/VALIDATION-MACHINE_CHECKED_DISPROVEN-f97316?style=for-the-badge)
![Step 12](https://img.shields.io/badge/STEP_12-GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS-f59e0b?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd’s Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This registry preserves a **valid negative formal result**.
>
> `P12C-09` was not merely unproven or inconclusive. Within the bounded Step-12 formal domain, a machine-executed counterexample falsified unconditional terminal totality, so the controlling disposition remains `MACHINE_CHECKED_DISPROVEN`.
>
> The counterexample must not be deleted, softened, or silently replaced by a narrower theorem. Any refined proposition requires its own theorem identity, evidence, adjudication, and promotion path.

---

# 👀 Counterexample in one view

```mermaid
flowchart LR
    Q3["🟠 Q3<br/>WORKER_CLAIMED"]:::claimed
    F["⚠️ FinishClaim(r,z,q_s)<br/>fails"]:::failure
    Q3B["🟠 Q3<br/>record remains claimed"]:::claimed
    P["❌ P12C-09<br/>Terminal Totality"]:::prop
    D["🔬 MACHINE_CHECKED_DISPROVEN"]:::disproven

    Q3 --> F --> Q3B
    Q3B -->|"valid bounded counterexample"| P
    P --> D

    classDef claimed fill:#f59e0b,stroke:#92400e,color:#111827,stroke-width:3px;
    classDef failure fill:#ef4444,stroke:#991b1b,color:#ffffff,stroke-width:3px;
    classDef prop fill:#8b5cf6,stroke:#5b21b6,color:#ffffff,stroke-width:2px;
    classDef disproven fill:#dc2626,stroke:#7f1d1d,color:#ffffff,stroke-width:3px;
```

The counterexample establishes one bounded fact:

> **A claimed record is not guaranteed to reach `TERMINAL_COMPLETED` or `TERMINAL_REJECTED` if terminalization fails.**

That negative result is part of the successful Step-12 scientific close.

---

# 🎯 Purpose

This registry preserves falsifying cases discovered during formal analysis of the bounded ALLIS production authorized-adoption model.

The referenced formal object is:

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

A counterexample is treated here as a **first-class scientific result**.

It is not a failed documentation task.  
It is not a theorem that needs better wording.  
It is not removed because the intended property would have been convenient.

The governing rule is:

> **Evidence constrains the claim. The claim does not control the evidence.**

This is the formal-verification expression of the broader ALLIS architecture:

> **State does not become authority merely because it exists.**

A proposed theorem does not become true merely because it was proposed.  
A desired invariant does not become established merely because the architecture was intended to preserve it.  
A bounded counterexample has authority over the claim because it falsifies the universal statement inside the modeled domain.

---

# 📋 Registry status

| Field | Value |
|---|---|
| Document role | Current counterexample registry |
| Formal object | `DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1` |
| Production source commit | `20c8cbe175781c8a1c05d65c03977859ceca884a` |
| Source domain | Sealed 11-file production authorized-adoption source set |
| Registered counterexamples | `1` |
| Preserved proposition | `P12C-09` |
| Result | `MACHINE_CHECKED_DISPROVEN` |
| Residual mapping | `R12F-02` / terminal-totality proposition disproven |
| Final Step-12 status | `GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS` |
| Final seal SHA-256 | `b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b` |

The current registry contains one formal counterexample because Step 12 produced one adjudicated disproven proposition.

The registry must grow if future formal work discovers additional falsifying cases.

---

# 1. Why counterexamples are preserved

A universal proposition has the form:

```math
\forall x,\;P(x)
```

To disprove it, the analysis does not need to show that every execution fails.

It needs one valid case in the modeled domain for which:

```math
\neg P(x)
```

Therefore:

```text
one valid counterexample
        ↓
universal proposition is false
```

The scientific value of the counterexample is that it identifies the exact boundary of a claim.

In ALLIS documentation, this means:

```text
desired property
≠
established property

intended behavior
≠
proven invariant

normal path
≠
all possible modeled paths
```

A negative result narrows the architecture to what the evidence actually supports.

---

# 🔬 Registered counterexample

# 🧪 2. CE-001 — P12C-09 terminal-totality counterexample

## Proposition identifier

```text
P12C-09
```

## Proposition name

```text
Terminal Totality
```

## Proposed statement

The proposed property was:

```math
\boxed{
Q_3
\Rightarrow
Q_{6C}
\lor
Q_{6R}
}
```

where:

- $`Q_3`$ = `WORKER_CLAIMED`;
- $`Q_{6C}`$ = `TERMINAL_COMPLETED`; and
- $`Q_{6R}`$ = `TERMINAL_REJECTED`.

## Intended meaning

The proposition asserted:

> Every claimed record necessarily reaches either the completed terminal state or the rejected terminal state.

In operational form:

```text
record claimed
     ↓
must eventually become
     ↓
completed OR rejected
```

If true, this would make the claimed state terminally total within the modeled pathway.

Step 12 did not establish that property.

It disproved it.

---

# 🧩 Counterexample mechanics

# 3. Counterexample condition

The bounded counterexample begins with a record $`r`$ in the claimed state:

```math
State(r)=Q_3
```

The model then permits terminalization to fail:

```math
FinishClaim(r,z,q_s)\uparrow
```

where:

```math
z\in\{completed,rejected\}
```

and $`\uparrow`$ means the bounded function fails to return successfully.

One valid failure condition identified by the formal record is that terminal-record creation cannot complete.

The resulting state can remain:

```math
State'(r)=Q_3
```

instead of becoming:

```math
Q_{6C}
```

or:

```math
Q_{6R}
```

Therefore:

```math
\exists r:
Q_3(r)
\land
\neg Q_{6C}(r)
\land
\neg Q_{6R}(r)
```

after terminalization failure.

This single valid bounded execution falsifies the universal proposition.

---

# ✅ 4. Machine adjudication

The formal result is:

```math
\boxed{
\mathcal{M}_{DGM}
\not\models
P12C\text{-}09
}
```

The final Step-12 disposition is:

```text
P12C-09 = MACHINE_CHECKED_DISPROVEN
```

The result is not:

```text
NOT_TESTED
```

It is not:

```text
INCONCLUSIVE
```

It is not:

```text
NOT_YET_PROVEN
```

It is:

```text
DISPROVEN
```

within the bounded formal domain.

## Registry classification

| Field | Result |
|---|---|
| Proposition | `P12C-09` |
| Proposed property | Claimed records are terminally total |
| Counterexample state | `Q3 = WORKER_CLAIMED` |
| Failing operation | `FinishClaim(r,z,q_s)` |
| Failure semantics | Function does not successfully complete |
| Post-failure state | Record may remain at `Q3` |
| Universal property | False |
| Highest validation level | `MACHINE_CHECKED_DISPROVEN` |
| Counterexample preserved | `YES` |
| Proposition promoted to proven | `NO` |

---

# 🔄 Transition interpretation

# 5. Transition-level interpretation

The normal terminal path can be represented as:

```text
Q3  WORKER_CLAIMED
 │
 ├── FinishClaim(completed) succeeds
 │          ↓
 │        Q6C
 │   TERMINAL_COMPLETED
 │
 └── FinishClaim(rejected) succeeds
            ↓
          Q6R
     TERMINAL_REJECTED
```

The counterexample adds a third modeled outcome:

```text
Q3  WORKER_CLAIMED
 │
 └── FinishClaim fails
            ↓
          Q3
     WORKER_CLAIMED
```

Formally:

```math
\delta(Q_3,FinishClaim\uparrow)=Q_3
```

is an allowed bounded state transition.

That transition is sufficient to defeat:

```math
Q_3
\Rightarrow
Q_{6C}\lor Q_{6R}
```

---

# 6. What the counterexample means

The counterexample does **not** mean that every claimed record remains stuck.

It means that the current bounded model does not support the universal assertion that every claimed record must terminate.

The distinction is:

```text
normal terminalization exists
≠
terminalization is total

terminalization can succeed
≠
terminalization cannot fail

most records may terminate
≠
all modeled claimed records must terminate
```

A universal theorem must survive every valid state allowed by its domain.

`P12C-09` does not.

---

# 7. Why this result matters architecturally

The counterexample exposes an important governance boundary.

A record can legitimately reach `WORKER_CLAIMED`, yet that predecessor state does not create a guarantee that the next administrative transition will succeed.

In other words:

```text
claimed
≠
completed

claimed
≠
rejected

attempted terminalization
≠
successful terminalization
```

This follows the same architectural discipline used elsewhere in ALLIS:

```text
candidate
≠
authorization

evaluation
≠
authorization

authorization
≠
successful application

execution started
≠
execution completed

claimed state
≠
terminal state
```

The system therefore cannot infer a stronger successor state merely from the existence of a predecessor state.

> **State transition requires evidence of transition. Predecessor state alone does not authorize a stronger conclusion.**

---

# 🧠 8. Scientific significance

Preserving this counterexample strengthens the formal record.

A verification process that records only successful propositions would obscure the boundary of the model.

Step 12 instead records:

```text
12 propositions adjudicated
11 proven
1 disproven
0 unadjudicated
```

The disproven proposition contributes directly to that closed scientific state.

The result demonstrates that:

- propositions were allowed to fail;
- machine evidence could reduce rather than inflate a claim;
- the final seal did not require every candidate proposition to become true;
- formal closure means every scoped question received a disposition, not that every desired property was proven; and
- residual risk remains visible after formal closure.

This distinction is central to the ALLIS evidence model.

```text
closed
≠
perfect

adjudicated
≠
proven

green
≠
no residuals
```

---

# 📐 9. Refined proposition

The discovered counterexample supports a narrower statement:

```math
\boxed{
Q_3
\land
FinishClaim\downarrow
\Rightarrow
Q_{6C}
\lor
Q_{6R}
}
```

This statement says:

> If a record is claimed **and terminalization successfully completes**, then the record reaches either the completed or rejected terminal state.

That refined proposition is consistent with the modeled transition structure.

However, Step 12 did **not** independently promote it to a new sealed theorem.

Its current status is therefore:

```text
SUPPORTED_BY_TRANSITION_STRUCTURE
NOT_INDEPENDENTLY_PROMOTED
NOT_A_SEALED_REPLACEMENT_THEOREM
```

This distinction is deliberate.

The system does not repair a failed theorem by quietly adding a missing premise after the fact.

If the refined proposition is to become a formal theorem, it requires its own explicit theorem definition, evidence, adjudication, and promotion path.

---

# 🚫 10. No silent theorem substitution

The following transformation is prohibited by the current evidence record:

```text
P12C-09 disproven
        ↓
rewrite proposition
        ↓
call rewritten proposition "P12C-09 proven"
```

The correct record is:

```text
P12C-09
    =
MACHINE_CHECKED_DISPROVEN

Refined proposition
    =
separate unpromoted statement
```

This keeps theorem identity stable.

It also preserves the provenance of the scientific result.

---

# 🧱 Residual and non-promotion mapping

# 11. Residual mapping

The counterexample remains represented in the Step-12 residual set.

The relevant residual is:

```text
R12F-02
Terminalization
```

with the controlling result:

```text
P12C-09 disproven;
a record may remain claimed if terminalization fails.
```

Its state is:

```text
DISPROVEN
```

This residual is not an unadjudicated proposition.

The proposition has already been adjudicated.

The residual records the architectural consequence that remains after that adjudication.

```text
unadjudicated
≠
residual

P12C-09 is adjudicated
AND
its discovered limitation remains a residual
```

---

# 12. Non-promotion mapping

Step 12 explicitly preserves:

```text
P12C-09
not mapped to
PROVEN
```

Formally:

```math
P12C\text{-}09
\not\mapsto
PROVEN
```

This is part of the final non-promotion set.

The non-promotion is not temporary wording.

It is part of the formal evidence boundary.

---

# ⚪ Broader claim boundaries

# 13. Relationship to system safety

The terminalization counterexample must not be inflated into a broader conclusion in either direction.

It does **not** establish:

```text
ALLIS is unsafe
```

It also does not permit:

```text
ALLIS is proven safe
```

The counterexample establishes one bounded fact:

> The current production authorized-adoption model does not satisfy unconditional terminal totality for claimed records.

The controlling broader statements remain:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

The counterexample is one bounded result inside that larger explicit proof boundary.

---

# 14. Relationship to governed autonomy

This result is especially important to the larger ALLIS architecture because governed autonomy requires more than blocking unauthorized actions.

It also requires honest representation of the state of authorized workflows.

A system that reports:

```text
claimed
```

as:

```text
completed
```

without evidence would violate the same governing principle as a system that treats:

```text
capable
```

as:

```text
authorized
```

Both would promote one state into a stronger state without sufficient authority or evidence.

The counterexample therefore reinforces the architecture at a deeper level:

```text
capability
≠
authority

attempt
≠
completion

predecessor state
≠
successor state

intended invariant
≠
proven invariant
```

---

# 15. Counterexample record

## CE-001

| Field | Value |
|---|---|
| Registry ID | `CE-001` |
| Formal proposition | `P12C-09` |
| Formal section | `A.44` |
| Name | Terminal Totality |
| Model state | `Q3 = WORKER_CLAIMED` |
| Trigger | `FinishClaim(r,z,q_s)` fails |
| Failure notation | `FinishClaim(r,z,q_s)\uparrow` |
| Resulting state | `State'(r)=Q3` permitted |
| Falsified assertion | `Q3 ⇒ Q6C ∨ Q6R` |
| Formal result | `DISPROVEN` |
| Validation | `MACHINE_CHECKED_DISPROVEN` |
| Residual | `R12F-02` |
| Replacement theorem | None |
| Counterexample status | Preserved |

---

# 🛡️ 16. Evidence boundary

This registry records the formal counterexample and its sealed Step-12 disposition.

It does not claim that a real production record was deliberately stranded in `Q3` as part of Step 12.

The result is a **machine-executed bounded counterexample in the formal/source-model verification work**, not a claim of a naturally occurring production incident.

That distinction matters:

```text
machine-executed bounded counterexample
≠
observed production outage

formal reachability
≠
claim that the failure happened operationally in normal production
```

The scientific result remains valid inside its stated bounded domain.

---

# 🧾 Final bounded result

# 17. Final counterexample statement

The controlling result is:

```math
\boxed{
\exists r:
Q_3(r)
\land
FinishClaim(r,z,q_s)\uparrow
\land
State'(r)=Q_3
}
```

therefore:

```math
\boxed{
\mathcal{M}_{DGM}
\not\models
\left(
Q_3
\Rightarrow
Q_{6C}\lor Q_{6R}
\right)
}
```

and:

```text
P12C-09=MACHINE_CHECKED_DISPROVEN
```

No stronger or weaker disposition replaces this result.

---

# 18. Seal identity

The controlling Step-12 formal seal is:

```text
STEP12_FINAL_THEOREM_AND_FORMAL_CORRESPONDENCE_SEALED_GREEN_WITH_EXPLICIT_RESIDUALS
```

Final result SHA-256:

```text
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

Controlling scope:

```text
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

At final seal:

```text
12 propositions total
11 proven
1 disproven
0 unadjudicated
```

The preserved counterexample is the one disproven formal proposition in that adjudication vector.

---

# 📚 19. Companion records

This registry belongs with:

```text
formal-verification/
    authorized-adoption/
        formal-model.md
        theorem-registry.md
        counterexample-registry.md

correspondence/
    authorized-adoption/
        model-to-source.md
        source-to-runtime.md

evidence/
    governed-evolution/
        step12-final-seal.md
        source-identity.md
        trust-anchor.md
        governance-view.md
        residuals.md
```

Use:

- [`formal-model.md`](./formal-model.md) — state space and transition semantics
- [`theorem-registry.md`](./theorem-registry.md) — full proposition adjudication and validation levels
- [`counterexample-registry.md`](./counterexample-registry.md) — this preserved falsifying-case registry
- [`model-to-source.md`](../../correspondence/authorized-adoption/model-to-source.md) — formal object → sealed source correspondence
- [`source-to-runtime.md`](../../correspondence/authorized-adoption/source-to-runtime.md) — sealed source → inspected runtime correspondence
- [`step12-final-seal.md`](../../evidence/governed-evolution/step12-final-seal.md) — controlling bounded Step-12 final seal
- [`source-identity.md`](../../evidence/governed-evolution/source-identity.md) — canonical sealed source identity
- [`trust-anchor.md`](../../evidence/governed-evolution/trust-anchor.md) — sealed public verification trust identity
- [`governance-view.md`](../../evidence/governed-evolution/governance-view.md) — sealed governance-view evidence
- [`residuals.md`](../../evidence/governed-evolution/residuals.md) — residual and non-promotion ledger preserving `R12F-02`

---

# 🧾 Counterexample summary

<div align="center">

### 🔬 REGISTERED COUNTEREXAMPLE
# **CE-001**

### 📐 PROPOSITION
**`P12C-09` — Terminal Totality**

### 🧱 COUNTEREXAMPLE STATE
**`Q3 = WORKER_CLAIMED`**

### ⚠️ FAILING OPERATION
**`FinishClaim(r,z,q_s)` fails**

### 🔄 PERMITTED RESULT
**record may remain at `Q3`**

<br>

### ❌ FORMAL DISPOSITION
# `MACHINE_CHECKED_DISPROVEN`

### 🧱 RESIDUAL
**`R12F-02`**

### 🚫 REPLACEMENT THEOREM
**NONE**

<br>

# `SYSTEM_PROVEN=NO`

</div>

---

# Governing counterexample principle

> **A counterexample is not something the documentation must explain away. It is evidence that defines the true boundary of the architecture.**

> **Evidence constrains the claim. The claim does not control the evidence.**
