<div align="center">

# ALLIS — Governed Evolution

### Governed improvement without self-authorizing production change

<br>

![Governed Evolution](https://img.shields.io/badge/GOVERNED_EVOLUTION-BOUNDED_PRODUCTION_PATH-2563eb?style=for-the-badge)
![Step 12](https://img.shields.io/badge/STEP_12-GREEN_CLOSED_WITH_RESIDUALS-f59e0b?style=for-the-badge)
![Lean R1](https://img.shields.io/badge/LEAN_R1-KERNEL_CHECKED-7c3aed?style=for-the-badge)
![Post A8](https://img.shields.io/badge/POST--A8-B%2FC_CORRESPONDENCE_VERIFIED-16a34a?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd’s Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document explains the **bounded governed-evolution and production authorized-adoption architecture**.
>
> The historical Step-12 evidence remains intact. Later Lean R1 proof-assistant qualification and later post-A8 source/runtime + B/C live revalidation are **additive successor evidence**.
>
> They do **not** rewrite the Step-12 final seal or promote the repository to whole-system proof.
>
> ```text
> SYSTEM_PROVEN=NO
> ```

---

# 👀 Result in one view

| Evidence layer | Bounded result |
|---|---|
| Historical Step-12 formal adjudication | `12 total · 11 proven · 1 disproven · 0 unadjudicated` |
| Historical Step-12 source/runtime | NBB `11/11 PASS` · Worker `11/11 PASS` |
| Later Lean R1 | Principal A/B/C results kernel checked; P12C-09 counterexample/disproof kernel checked; theorem-level axioms `NONE` |
| Current post-A8 source/runtime | `CURRENT_POST_A8_DGM_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11` |
| `T12D-A` | `MACHINE_CHECKED` |
| `T12D-B` | `CORRESPONDENCE_VERIFIED` |
| `T12D-C` | `CORRESPONDENCE_VERIFIED` |
| `P12C-09` | `MACHINE_CHECKED_DISPROVEN` |
| Whole system | `SYSTEM_PROVEN=NO` |

```mermaid
flowchart LR
    P["💡 Candidate proposed"]:::proposal
    E["🧪 Candidate evaluated"]:::evidence
    A["🔐 Independent authorization"]:::authority
    V["🛡️ Runtime verification"]:::verify
    G["🔧 Governed application"]:::apply
    R["🧾 Receipt + evidence"]:::receipt

    P --> E
    E -->|"does not create authority"| A
    A --> V
    V -->|"only if all checks pass"| G
    G --> R

    classDef proposal fill:#dbeafe,stroke:#2563eb,color:#172554,stroke-width:2px;
    classDef evidence fill:#fef3c7,stroke:#ca8a04,color:#713f12,stroke-width:2px;
    classDef authority fill:#fecaca,stroke:#dc2626,color:#7f1d1d,stroke-width:3px;
    classDef verify fill:#ddd6fe,stroke:#7c3aed,color:#3b0764,stroke-width:2px;
    classDef apply fill:#bbf7d0,stroke:#16a34a,color:#14532d,stroke-width:2px;
    classDef receipt fill:#ccfbf1,stroke:#0f766e,color:#134e4a,stroke-width:2px;
```

---

# 🧭 Governed improvement without self-authorizing change

ALLIS separates the ability to **propose, evaluate, and reason about a software improvement** from the authority required to adopt that improvement into a production-controlled system.

The central architectural principle is:

> **Capability does not create authority.**

A system may be able to identify a useful change, generate a candidate, evaluate that candidate, compare evidence, and conclude that the change appears beneficial.

None of those facts, by themselves, authorize production mutation.

ALLIS therefore treats governed evolution as a sequence of distinct evidence and authority states:

```text
candidate proposed
        ↓
candidate evaluated
        ↓
evidence produced
        ↓
candidate may be eligible for review
        ↓
independent authorization required
        ↓
target, prestate, replay, and authority checks
        ↓
governed application
        ↓
poststate verification
        ↓
receipt and evidence
```

The key boundary is:

```text
AI proposes
AI evaluates
AI stops

independent authority authorizes an exact bounded change

runtime verifies
runtime applies only if every required condition succeeds
runtime records the result
```

This architecture is designed so that:

```text
can do it
≠
authorized to do it

believes it is better
≠
may deploy it

evaluation passed
≠
production permission exists

evidence exists
≠
authority exists
```

---

# 📋 Current validation status

The governed-evolution architecture is no longer documented only as a future or conceptual design.

A bounded production authorized-adoption pathway has now been:

- implemented in production source;
- formally specified;
- mapped to its sealed production implementation;
- machine-adjudicated;
- checked against the deployed NBB and worker source identities;
- observed at selected fail-closed runtime boundaries; and
- closed under a Step-12 evidence seal with explicit residuals and non-promotions.

The current formal object is:

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

The controlling scope is:

```text
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

This is a bounded result.

It does not mean that all ALLIS behavior has been formally verified.

---

# 🕰️ What Step 12 established — historical final-seal record

This section records what **Step 12 established at its own final-seal epoch**.

Step 12 adjudicated twelve formal propositions over the sealed production authorized-adoption model.

The final proposition state is:

```text
12 total
11 proven
1 disproven
0 unadjudicated
```

The principal results are:

```text
T12D-A = MACHINE_CHECKED
T12D-B = CORRESPONDENCE_VERIFIED
T12D-C = CORRESPONDENCE_VERIFIED
P12C-09 = MACHINE_CHECKED_DISPROVEN
```

The **historical Step-12** live runtime source correspondence at the final seal was:

```text
NBB source correspondence     11/11 PASS
Worker source correspondence  11/11 PASS
```

The **historical Step-12** final runtime evidence also recorded:

```text
Public trust     PASS
Governance view  PASS
NBB health       PASS
Worker health    PASS
Host health      PASS
Authorized spool PASS_EMPTY
```

Step 12 carried fifteen formal obligations.

At closure:

```text
15/15 adjudicated
0 unadjudicated
```

Closure did not require every desired proposition to become true.

It required every scoped question to receive an explicit disposition.

---

# 🧮 Later Lean R1 qualification

After the Step-12 close, a separate Lean 4.34.0 R1 workstream independently formalized and kernel-checked the principal bounded result set.

Qualified successor evidence:

```text
T12D_A_LEAN_KERNEL_CHECKED=YES
T12D_B_LEAN_KERNEL_CHECKED=YES
T12D_C_LEAN_KERNEL_CHECKED=YES

P12C_09_LOGICAL_RESULT=DISPROVEN
P12C_09_COUNTEREXAMPLE_LEAN_KERNEL_CHECKED=YES

THEOREM_LEVEL_AXIOMS=NONE
LEAN_PROOF_HOLES=0
STEP12_LEAN_QUALIFICATION_AXIOM_FREE_R2=SEALED_PASS
```

The later Lean work is **successor proof-assistant evidence**.

It does not retroactively redefine the historical Step-12 `MACHINE_CHECKED` label.

The Lean R1 closeout itself correctly preserved that direct production correspondence had not yet been established by the Lean workstream:

```text
LEAN_TO_PRODUCTION_SOURCE_CORRESPONDENCE=NOT_YET_ESTABLISHED
LEAN_TO_PRODUCTION_RUNTIME_CORRESPONDENCE=NOT_YET_ESTABLISHED
```

That production implementation bridge was established later through separate post-A8 correspondence work.

See:

- [`../../formal-verification/authorized-adoption/lean/workstream-closeout-r1.md`](../../formal-verification/authorized-adoption/lean/workstream-closeout-r1.md)

---

# 🔗 Post-A8 current revalidation

A later post-A8 observation epoch revalidated the same theorem-relevant production source identity against the current observed DGM runtimes.

Current source/runtime result:

```text
IMMUTABLE_SOURCE_IDENTITY=PASS_11_OF_11

NBB_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11

WORKER_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11

CURRENT_POST_A8_DGM_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11
```

The current theorem-specific fail-closed observations then established:

```text
T12D_B_LIVE_OBSERVATION=PASS
T12D_B_POST_A8_CORRESPONDENCE_VERIFIED=YES
T12D_B_POST_A8_VALIDATION_LEVEL=CORRESPONDENCE_VERIFIED

T12D_C_LIVE_OBSERVATION=PASS
T12D_C_POST_A8_CORRESPONDENCE_VERIFIED=YES
T12D_C_POST_A8_VALIDATION_LEVEL=CORRESPONDENCE_VERIFIED
```

The positive authorized-application path for `T12D-A` remained deliberately unexecuted:

```text
T12D_A_POSITIVE_AUTHORIZED_APPLY_EXECUTED=NO
T12D_A_CURRENT_CORRESPONDENCE_VERIFIED=NO
T12D_A_CURRENT_VALIDATION_LEVEL=MACHINE_CHECKED
```

Therefore the current bounded theorem state is:

| Proposition | Current validation |
|---|---|
| `T12D-A` | `MACHINE_CHECKED` |
| `T12D-B` | `CORRESPONDENCE_VERIFIED` |
| `T12D-C` | `CORRESPONDENCE_VERIFIED` |
| `P12C-09` | `MACHINE_CHECKED_DISPROVEN` |

The later post-A8 record is a **successor observation**, not a rewrite of the Step-12 seal.

See:

- [`post-a8-theorem-correspondence-registry-r1.md`](post-a8-theorem-correspondence-registry-r1.md)

---

# 📐 The strongest current production theorem

The central authorized-application theorem is:

```math
\boxed{
M_{auth}
\Rightarrow
V_{auth}
\land
V_{target}
\land
V_{pre}
\land
V_{once}
\land
S_{spent}
\land
R_{receipt}
}
```

In plain language:

> If the bounded authorized-application path returns successfully, then authorization validation, target safety, prestate correspondence, one-use authority, spent-state reservation, and receipt correspondence must all have succeeded.

This theorem is:

```text
MACHINE_CHECKED
```

It is not currently promoted to:

```text
CORRESPONDENCE_VERIFIED
```

because Step 12 deliberately did not perform a real positive production authorization and DGM patch application.

The later post-A8 current revalidation also deliberately did **not** execute that positive authorized-apply production path:

```text
T12D_A_POSITIVE_AUTHORIZED_APPLY_EXECUTED=NO
T12D_A_CURRENT_CORRESPONDENCE_VERIFIED=NO
```

So `T12D-A` correctly remains:

```text
MACHINE_CHECKED
```

That distinction is important:

```text
machine-checked path
≠
live positive path observed
```

---

# 🛡️ Two fail-closed properties are correspondence-verified

## Invalid authorization does not become authorized work

The NBB publication boundary satisfies:

```math
\boxed{
\neg V_{auth}
\Rightarrow
\neg Publish
}
```

Operationally:

```text
invalid external authorization
        ↓
no authorized spool publication
```

This result was correspondence-verified in the bounded Step-12 record and was later re-observed in the post-A8 current runtime:

```text
T12D_B_LIVE_OBSERVATION=PASS
T12D_B_POST_A8_VALIDATION_LEVEL=CORRESPONDENCE_VERIFIED
```

Current result:

```text
CORRESPONDENCE_VERIFIED
```

## Empty spool does not become authorized application

The worker boundary satisfies:

```math
\boxed{
Incoming=\varnothing
\Rightarrow
Claim=\varnothing
\Rightarrow
NoAuthorizedApply
}
```

Operationally:

```text
no incoming authorized record
        ↓
no worker claim
        ↓
no authorized apply
```

This result was likewise correspondence-verified in the bounded Step-12 record and later re-observed in the post-A8 current runtime:

```text
T12D_C_LIVE_OBSERVATION=PASS
T12D_C_POST_A8_VALIDATION_LEVEL=CORRESPONDENCE_VERIFIED
```

Current result:

```text
CORRESPONDENCE_VERIFIED
```

---

# 🔴 A counterexample is part of the result

The formal process did not promote every proposed property.

The proposed terminal-totality property:

```math
Q_3
\Rightarrow
Q_{6C}\lor Q_{6R}
```

was disproven.

A machine-executed bounded counterexample showed that terminalization can fail while leaving a record in the claimed state:

```text
Q3  WORKER_CLAIMED
 │
 └── terminalization fails
            ↓
          Q3
     WORKER_CLAIMED
```

Therefore:

```text
P12C-09=MACHINE_CHECKED_DISPROVEN
```

This is a first-class scientific result.

The architecture is required to conform to the evidence.

The evidence is not rewritten to make the intended architecture look cleaner.

---

# 🧭 What “governed evolution” means

In ALLIS, **governed evolution** does not mean unrestricted, autonomous, or self-authorizing software change.

It means that a system can support bounded improvement work while preserving independent authority over production adoption.

The architecture separates two related but different domains.

## Research and evaluation

Research-stage work can include:

```text
qualified source or prior record
        ↓
bounded candidate generation
        ↓
evaluation and testing
        ↓
evidence production
        ↓
comparison or review
        ↓
retention as a research or qualified record
```

A successful candidate can become better evidence.

It does not become production authority.

## Production authorized adoption

The bounded production path is:

```text
external candidate package
        ↓
NBB validation
        ↓
authorized spool publication
        ↓
worker claim
        ↓
authorized-application gate
        ↓
governed application
        ↓
poststate verification
        ↓
receipt
        ↓
terminal handling
```

A production transition requires an independent authorization object and runtime validation of the exact change being considered.

---

# ⚖️ Research evidence and production authority remain separate

The architecture deliberately separates:

| Research / evaluation | Production authorized adoption |
|---|---|
| Produces candidate evidence | Changes a production-controlled source state |
| May score or compare a proposal | Requires a separately valid authorization |
| Can determine that a candidate appears better | Must validate the exact target and prestate |
| May preserve a candidate for future review | Uses one-time bounded authority |
| Does not create deployment permission | Requires replay protection |
| Does not prove the mutation occurred | Requires poststate checking and receipt evidence |

This distinction prevents a common failure mode:

```text
good result
        ↓
treated as permission
        ↓
unreviewed production mutation
```

ALLIS rejects that shortcut.

---

# 📦 Candidate and authorization are different objects

The production model separates the proposed change from the authority to adopt it.

Conceptually:

```text
CandidateEnvelope
≠
AuthorizationEnvelope
```

The candidate describes the proposed source change and its evidence.

The authorization binds a governed approval to specific identities and conditions.

A valid authorization can include bindings to:

- authorization identity;
- proposal identity;
- approval decision;
- candidate identity;
- candidate-envelope identity where required;
- evaluation identity;
- target;
- expected target prestate;
- approving identity;
- authority class;
- issue time;
- expiration time; and
- detached signature.

This design prevents:

```text
candidate exists
```

from silently becoming:

```text
candidate is authorized
```

---

# 🔐 Verification is not authorization

The production pathway uses a pinned public verification trust anchor.

The public key allows the runtime to verify whether a detached authorization signature corresponds to the expected signing authority.

But:

```text
signature verifies
≠
complete authorization valid
```

Signature verification is one required predicate inside the broader authorization model.

A valid signature does not independently establish:

- approval;
- permitted authority class;
- valid lifetime;
- proposal binding;
- target binding;
- prestate binding;
- candidate binding;
- evaluation binding;
- target safety;
- one-use status; or
- successful application.

The public verifier verifies authority evidence.

It does not create private signing authority.

---

# 🚧 Authority remains external to the bounded runtime model

The current Step-12 model preserves an explicit authority boundary:

```text
NBB and worker
    ↓
verify and consume authorization

NBB and worker
    ↓
do not independently mint private authorization authority
```

This residual is classified as:

```text
EXTERNAL_TO_RUNTIME_MODEL
```

That separation is intentional.

If the same runtime that wanted to mutate production could manufacture the authority required to approve that mutation, the distinction between capability and authority would collapse.

---

# 🎯 Target access is not target authority

A process may be technically able to reach a source path without being authorized to modify it.

The formal target predicate requires both:

```math
V_{target}
=
V_{contain}
\land
V_{allow}
```

In plain language:

```text
target must remain inside the governed root
AND
target must be permitted by the governed mutation policy
```

Therefore:

```text
filesystem access
≠
governed target authority
```

---

# 🔗 Authorization is bound to the current prestate

A production authorization is not treated as permission to mutate any later version of a target.

The current source must still match the state that was authorized.

Conceptually:

```math
V_{pre}(c,s)=1
```

only when the current source hash matches the candidate's expected target-before hash.

Therefore:

```text
authorization valid for source state A
≠
authorization valid for changed source state B
```

This prevents stale authority from silently migrating onto a different source state.

---

# 1️⃣ Authorization is one-use

The bounded production model includes one-use authorization behavior.

A successful authorization identity cannot simply be replayed indefinitely.

Conceptually:

```math
V_{once}(a,L_s)=1
```

only when the authorization identity is not already spent.

Therefore:

```text
authority was valid once
≠
authority remains reusable forever
```

---

# 🧾 Application success requires evidence of the transition

The production path does not treat an attempted mutation as a completed mutation.

A successful authorized application includes:

```text
authorization validation
        ↓
target validation
        ↓
prestate validation
        ↓
one-use reservation
        ↓
governed application
        ↓
poststate verification
        ↓
receipt
```

The receipt binds evidence about the actual transition.

This preserves another important distinction:

```text
attempted
≠
completed

authorized
≠
successfully applied

successfully applied
≠
successfully terminalized
```

The preserved terminalization counterexample demonstrates why these states must remain separate.

---

# 💻 Source identity is part of the proof boundary

The formal model is bound to the exact sealed eleven-file production source set at:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

The **historical Step-12** runtime evidence established byte correspondence for all eleven governed source files in both inspected runtime roles:

```text
NBB     11/11 PASS
Worker  11/11 PASS
```

The later post-A8 current revalidation independently re-established the same bounded source/runtime relationship:

```text
CURRENT_POST_A8_DGM_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11
```

This correspondence is not based on filenames alone.

It is a source-identity relationship.

A later source state does not inherit the Step-12 proof automatically.

```text
descendant source
≠
same sealed source

new deployment
≠
prior correspondence automatically preserved
```

---

# 🕒 Runtime correspondence is point-in-time

The final Step-12 correspondence result is time-indexed.

Conceptually:

```math
C_{SR}^{\tau_{seal}}(S,R)=1
```

was established at the final seal boundary.

Step 12 does not establish:

```math
\forall\tau>\tau_{seal},
C_{SR}^{\tau}(S,R)=1
```

without future revalidation.

This residual is classified as:

```text
POINT_IN_TIME_BINDING
```

A runtime that changes must earn a new correspondence result.

The later post-A8 runtime did exactly that: it earned a separate current `PASS_11_OF_11` correspondence result.

That newer result is also point-in-time and does not become a permanent invariant.

---

# 🔑 Governance view and cryptographic trust are separate evidence objects

The final Step-12 runtime state separately records:

```text
Public trust     PASS
Governance view  PASS
```

These checks answer different questions.

The public trust anchor answers:

> Does the runtime contain the expected public verification identity?

The governance-view check answers:

> Does the live NBB governance view correspond to the sealed governance object?

Neither result independently authorizes a mutation.

They remain separate parts of the broader evidence chain.

---

# 📊 Validation hierarchy

ALLIS uses a strict validation hierarchy.

```text
Implemented
    ↓
Observed
    ↓
Demonstrated
    ↓
Formally Specified
    ↓
Proven
    ↓
Machine-Checked
    ↓
Correspondence-Verified
```

These statuses are not interchangeable.

For example:

```text
T12D-A
=
MACHINE_CHECKED
```

while:

```text
T12D-B
=
CORRESPONDENCE_VERIFIED
```

and:

```text
P12C-09
=
MACHINE_CHECKED_DISPROVEN
```

A single successful seal does not flatten those results into one generic word such as “verified.”

---

# 🧱 Step-12 residuals remain part of the architecture

Step 12 closed with eight explicit residuals.

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

Residual does not mean unadjudicated.

At final seal:

```text
Unadjudicated = 0
Residuals     = 8
```

Both statements are true.

The historical `R12F-01` classification records the Step-12 close.

The later post-A8 current revalidation did not remove that evidence boundary:

```text
T12D_A_POSITIVE_AUTHORIZED_APPLY_EXECUTED=NO
```

So there is still no positive-path correspondence promotion for `T12D-A`.

---

# ⛔ Seven stronger claims were deliberately not promoted

The Step-12 non-promotion set preserves:

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

These are part of the evidence.

They are not missing documentation.

---

# 🚫 What Step 12 did not do

Step 12 did not perform:

```text
REAL_PRODUCTION_AUTHORIZATION_PUBLICATION
REAL_PRODUCTION_AUTHORIZATION_CONSUMPTION
REAL_PRODUCTION_DGM_PATCH_APPLICATION
```

The controlling state remains:

```text
REAL_PRODUCTION_AUTHORIZATION_PUBLICATION=NOT_PERFORMED
REAL_PRODUCTION_AUTHORIZATION_CONSUMPTION=NOT_PERFORMED
REAL_PRODUCTION_DGM_PATCH_APPLICATION=NOT_PERFORMED
```

The formal close itself did not create production authority.

The later post-A8 current revalidation also avoided positive production authority:

```text
REAL_PRODUCTION_AUTHORIZATION_ISSUED=NO
REAL_PRODUCTION_AUTHORIZATION_CONSUMED=NO
REAL_PRODUCTION_DGM_PATCH_APPLICATION=NO
```

The later observation strengthened correspondence evidence without crossing the positive production-authorization boundary.

---

# 🚫 What this architecture is not

The current evidence does **not** establish that ALLIS is:

- an unrestricted self-rewriting system;
- an autonomous production-deployment authority;
- a canonical open-ended Darwin Gödel Machine;
- an artificial general intelligence system;
- a system in which evaluation results self-promote into production;
- a system in which the runtime can mint its own private authorization authority;
- a whole-system formally proven platform; or
- universally safe against every production mutation or failure mode.

The current controlling system-level statements are:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

These are explicit non-promotions.

They are not unresolved placeholders.

---

# ✅ What the current evidence does support

A defensible description of the current architecture is:

> **ALLIS implements a governed self-modification and authorized-adoption architecture in which candidate generation and evaluation remain separate from the independent authority required to adopt an exact change into production.**

The bounded production path has now been formally modeled and partially correspondence-verified.

That result is narrower than whole-system proof, but materially stronger than an architectural intention.

---

# 💡 Why this matters

Many AI-governance discussions focus on whether a model or agent is capable of performing an action.

ALLIS asks a second question:

> **Even if the system can perform the action, what gives it authority to do so?**

That distinction generalizes beyond software mutation:

```text
AI inferred it
≠
may treat it as authoritative fact

AI retrieved it
≠
may disclose it

AI remembers it
≠
may promote it

AI can perform the action
≠
may perform the action

AI believes the improvement is beneficial
≠
may rewrite production
```

Governed evolution is therefore not only a self-modification pattern.

It is an example of a broader ALLIS design principle:

> **Intelligence and sovereignty are separate computational concerns.**

---

# ⚖️ Computational separation of powers

The architecture can be understood as a computational separation of powers.

Different functions remain distinct:

```text
proposal
        ↓
evidence

evaluation
        ↓
evidence

authorization
        ↓
bounded authority

verification
        ↓
admission decision

application
        ↓
state transition

receipt
        ↓
evidence of transition
```

No one stage is allowed to silently absorb the authority of another.

This separation is what prevents:

```text
reasoning
```

from becoming:

```text
sovereignty
```

merely because the system is technically capable.

---

# 🏛️ Relevance to universities, governments, and community partners

For a university, public institution, local government, nonprofit, or community partner, the important question is not whether an AI system can generate an impressive result.

The important questions include:

- What exact system state produced the recommendation?
- What evidence supports the proposed change?
- Who or what has authority to approve it?
- Is the approval bound to one candidate?
- Is it bound to one target?
- Is it bound to the source state that was actually reviewed?
- Can the authority expire?
- Can it be replayed?
- Can a changed candidate reuse an old approval?
- Can the result be independently verified?
- Can the actual production transition be proven afterward?
- What happens when terminalization or another downstream step fails?
- Which claims are proven, which are merely observed, and which remain residual?

The governed-evolution architecture is intended to make those questions explicit and auditable.

---

# 🔒 Public documentation and private operations

This public repository documents the architecture, formal model, theorem status, correspondence structure, non-sensitive evidence identities, counterexamples, residuals, and claim boundaries.

It does not need to publish:

- private signing keys;
- passwords or tokens;
- active authorization artifacts;
- operational secret material;
- private runtime credentials;
- sensitive network details; or
- security-sensitive internal evidence that would weaken the system by being published.

The public documentation should expose enough provenance to audit the claim without exposing secrets.

---

# 📚 How to read the governed-evolution package

Start here for the architecture.

Then follow the evidence chain.

## Formal verification

```text
formal-verification/
    authorized-adoption/
        formal-model.md
        theorem-registry.md
        counterexample-registry.md
        lean/
            workstream-closeout-r1.md
```

Use:

- [`formal-model.md`](../../formal-verification/authorized-adoption/formal-model.md) for the bounded mathematical object;
- [`theorem-registry.md`](../../formal-verification/authorized-adoption/theorem-registry.md) for proposition status and validation level;
- [`counterexample-registry.md`](../../formal-verification/authorized-adoption/counterexample-registry.md) for the preserved terminalization counterexample; and
- [`lean/workstream-closeout-r1.md`](../../formal-verification/authorized-adoption/lean/workstream-closeout-r1.md) for the later Lean R1 proof-assistant qualification.

## Correspondence

```text
correspondence/
    authorized-adoption/
        model-to-source.md
        source-to-runtime.md
```

Use:

- [`model-to-source.md`](../../correspondence/authorized-adoption/model-to-source.md) for the mapping from mathematical objects to sealed production source behavior; and
- [`source-to-runtime.md`](../../correspondence/authorized-adoption/source-to-runtime.md) for the 11/11 NBB and worker byte-correspondence result and its point-in-time boundary.

## Evidence

```text
evidence/
    governed-evolution/
        source-identity.md
        trust-anchor.md
        governance-view.md
        residuals.md
        step12-final-seal.md
        post-a8-theorem-correspondence-registry-r1.md
```

Use:

- [`source-identity.md`](../../evidence/governed-evolution/source-identity.md) for the canonical bounded source identity;
- [`trust-anchor.md`](../../evidence/governed-evolution/trust-anchor.md) for the public verification trust anchor and its role;
- [`governance-view.md`](../../evidence/governed-evolution/governance-view.md) for the sealed governance-view identity and NBB correspondence;
- [`residuals.md`](../../evidence/governed-evolution/residuals.md) for the eight residuals and seven non-promotions;
- [`step12-final-seal.md`](../../evidence/governed-evolution/step12-final-seal.md) for the historical package-level Step-12 evidence state; and
- [`post-a8-theorem-correspondence-registry-r1.md`](../../evidence/governed-evolution/post-a8-theorem-correspondence-registry-r1.md) for the later current source/runtime and B/C live correspondence observation.

---

# 🧷 Final Step-12 seal — historical predecessor

The controlling Step-12 state is:

```text
STEP12_FINAL_THEOREM_AND_FORMAL_CORRESPONDENCE_SEALED_GREEN_WITH_EXPLICIT_RESIDUALS
```

The final Step-12 seal SHA-256 is:

```text
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

The controlling scope is:

```text
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

The seal does not enlarge its own scope.

The later Lean R1 and post-A8 records are successor evidence and do not rewrite this historical Step-12 seal.

It does not authorize a successor production action.

It does not establish:

```text
SYSTEM_PROVEN=YES
```

---

# ✅ Current bounded state

<div align="center">

### 📐 FORMAL OBJECT
**`DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1`**

### 🧮 LATER FORMAL QUALIFICATION
**Lean 4.34.0 R1 · principal result set kernel checked · theorem-level axioms `NONE`**

### 🔗 CURRENT DGM SOURCE/RUNTIME
**`PASS_11_OF_11`**

### 🛡️ CURRENT FAIL-CLOSED RESULTS
**`T12D-B = CORRESPONDENCE_VERIFIED`**

**`T12D-C = CORRESPONDENCE_VERIFIED`**

### 🚧 POSITIVE AUTHORIZED APPLY
**`T12D-A = MACHINE_CHECKED` · positive path not executed**

### 🔴 PRESERVED NEGATIVE RESULT
**`P12C-09 = MACHINE_CHECKED_DISPROVEN`**

<br>

# `SYSTEM_PROVEN=NO`

</div>

---

# 🧠 Core commitment

The governed-evolution architecture can be reduced to one rule:

> **The AI may participate in proposing, evaluating, and understanding a change without acquiring the right to make that change.**

That rule is enforced through separate candidate, evidence, authorization, verification, application, poststate, receipt, correspondence, and governance boundaries.

The larger ALLIS commitment is:

> **Evidence may justify a claim. Capability may enable an action. Neither becomes authority unless the governed system explicitly establishes that authority.**

> **Intelligence, evidence, authorization, execution, correspondence, and publication remain distinct states. Evidence earned in one state does not silently promote another.**
