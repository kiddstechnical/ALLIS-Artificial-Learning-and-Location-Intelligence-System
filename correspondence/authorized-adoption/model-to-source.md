<div align="center">

# ALLIS — Model → Source Correspondence

### Evidence-backed mapping from the bounded Step-12 formal object to the sealed production source

<br>

![Correspondence](https://img.shields.io/badge/CORRESPONDENCE-MODEL_TO_SOURCE-7c3aed?style=for-the-badge)
![Step 12](https://img.shields.io/badge/STEP_12-GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS-f59e0b?style=for-the-badge)
![Mapping](https://img.shields.io/badge/FORMAL_TO_SOURCE-PASS-16a34a?style=for-the-badge)
![Source](https://img.shields.io/badge/SEALED_SOURCE-20c8cbe1-0ea5e9?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd’s Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This record establishes the **model → source correspondence edge** for the bounded Step-12 production authorized-adoption domain.
>
> It does **not** replace `source-to-runtime.md`, establish standing runtime authority, expand the formal model to all ALLIS behavior, or promote the repository to `SYSTEM_PROVEN=YES`.

---

# 👀 Correspondence in one view

```mermaid
flowchart LR
    F["📐 FORMAL MODEL<br/>DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1"]:::formal
    S["💻 SEALED PRODUCTION SOURCE<br/>20c8cbe1… · 11 files"]:::source
    R["🖥️ DEPLOYED RUNTIME<br/>separate correspondence edge"]:::runtime

    F -->|"C_FS(F,S)=1 · PASS"| S
    S -. "source-to-runtime.md" .-> R

    classDef formal fill:#8b5cf6,stroke:#5b21b6,color:#ffffff,stroke-width:2px;
    classDef source fill:#ef4444,stroke:#991b1b,color:#ffffff,stroke-width:3px;
    classDef runtime fill:#f97316,stroke:#9a3412,color:#ffffff,stroke-width:2px;
```

This record establishes the **solid model → source edge**.

The **source → runtime edge remains a separate correspondence record** and does not arise merely because model-to-source correspondence passed.

---

# 🎯 Purpose

This document establishes how the bounded ALLIS production authorized-adoption formal model maps to the sealed production source that implements it.

The formal object is:

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

The production source identity is anchored at:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

The source domain is the sealed 11-file production authorized-adoption source set.

The governing correspondence principle is:

> **A mathematical model does not become implementation truth merely because it describes the intended architecture. It must be bound to the source that actually implements the behavior.**

The broader ALLIS principle remains:

> **Capability does not create authority.**

This correspondence record applies the same discipline to documentation:

```text
formal symbol
≠
source implementation

until

the symbol is explicitly mapped
to the sealed source behavior
that gives it operational meaning
```

---

# 📋 Correspondence status

| Field | Value |
|---|---|
| Document role | Formal-to-source correspondence record |
| Formal object | `DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1` |
| Production source commit | `20c8cbe175781c8a1c05d65c03977859ceca884a` |
| Source domain | Sealed 11-file production authorized-adoption source set |
| Formal-to-source correspondence | `PASS` |
| Formal correspondence predicate | `C_FS(F,S)=1` |
| Correspondence domain | Bounded production authorized-adoption pathway |
| Final Step-12 status | `GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS` |
| Final seal SHA-256 | `b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b` |

Step 12 established:

```math
C_{FS}(F,S)=1
```

where:

- $`F`$ is the bounded formal production model; and
- $`S`$ is the exact sealed production source set.

This correspondence is bounded to the authorized-adoption domain.

It does not establish that the formal model represents every behavior in ALLIS.

---

# 1. What correspondence means here

Formal-to-source correspondence answers:

> **Does each material part of the formal model represent behavior that is actually present in the sealed production source?**

It does not mean:

```text
formal model
=
entire source tree
```

It also does not mean:

```text
source hash equality
=
semantic proof
```

The source identity establishes **which source object is authoritative**.

The mapping in this document establishes **which source behavior gives each formal object its implementation meaning**.

The theorem and machine-check records establish **what propositions were supported over that bounded mapping**.

These are separate evidentiary roles.

---

# 🧭 2. Correspondence chain

The current documentation chain is:

```text
FORMAL MODEL
     │
     │  model-to-source.md
     ▼
SEALED PRODUCTION SOURCE
     │
     │  source-to-runtime.md
     ▼
DEPLOYED RUNTIME
     │
     │  observed theorem behavior
     ▼
CORRESPONDENCE-VERIFIED RESULT
```

This document covers only the first link:

```text
formal model
        ↓
sealed production source
```

It does not replace source-to-runtime correspondence.

---

# ➕ Successor evidence relationship

The Step-12 model → source mapping in this record remains the controlling bounded mapping:

```math
C_{FS}(F,S)=1
```

for:

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

and the sealed production source identity:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

A later Lean 4.34.0 R1 workstream formalized the principal Step-12 proposition layer and documented the formal-statement crosswalk for:

```text
T12D-A
T12D-B
T12D-C
P12C-09
```

That later proof-assistant qualification is a **successor formal-evidence layer**.

It did **not**, by itself, establish production model → source or source → runtime correspondence.

The Lean R1 closeout therefore correctly preserved:

```text
LEAN_TO_PRODUCTION_SOURCE_CORRESPONDENCE=NOT_YET_ESTABLISHED
LEAN_TO_PRODUCTION_RUNTIME_CORRESPONDENCE=NOT_YET_ESTABLISHED
```

The model → source edge remained grounded in the Step-12 correspondence work documented in this file.

Later post-A8 work then consumed the already-qualified production source identity and re-established the current source/runtime bridge:

```text
IMMUTABLE_SOURCE_IDENTITY=PASS_11_OF_11

NBB_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11

WORKER_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11

CURRENT_POST_A8_DGM_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11
```

Against that current runtime bridge, theorem-specific live observations were separately obtained for:

```text
T12D-B = CORRESPONDENCE_VERIFIED
T12D-C = CORRESPONDENCE_VERIFIED
```

with:

```text
T12D_B_LIVE_OBSERVATION=PASS
T12D_C_LIVE_OBSERVATION=PASS
```

`T12D-A` did not receive a positive authorized-apply live observation and therefore remains:

```text
T12D-A = MACHINE_CHECKED
```

The evidence relationship is therefore:

```text
Step-12 model → source mapping
    +
Lean R1 proposition-layer qualification
    +
post-A8 current source → runtime revalidation
    +
theorem-specific B/C live observation
```

These are distinct evidence layers.

Lean proof qualification does not manufacture source correspondence, and source/runtime correspondence does not manufacture theorem-specific live observation.

Successor records:

- [`../../formal-verification/authorized-adoption/lean/workstream-closeout-r1.md`](../../formal-verification/authorized-adoption/lean/workstream-closeout-r1.md)
- [`../../evidence/governed-evolution/post-a8-theorem-correspondence-registry-r1.md`](../../evidence/governed-evolution/post-a8-theorem-correspondence-registry-r1.md)

---

# 3. Source identity boundary

The formal model is bound to the exact 11-file production authorized-adoption source set at:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

The full 11-file identity manifest and per-file hashes belong in:

```text
evidence/governed-evolution/source-identity.md
```

This record intentionally does not create a second competing source manifest.

Instead, it records the source modules and symbols that provide the implementation meaning for the formal model.

The mapping is valid only when those modules are members of the sealed source identity represented by the controlling Step-12 evidence.

---

# 4. Formal symbols are abstractions, not invented Python names

Several names in the mathematical model are formal abstractions.

For example:

```text
NValidate
Publish
Claim
FinishClaim
Reserve_s
GApply
Receipt
```

are names used to reason about bounded behavior.

They do not imply that the production code contains Python functions with those exact names.

This document therefore distinguishes:

- **literal source symbols**, whose names are established by committed-source inspection; and
- **formal abstractions**, which map to a source behavior, call sequence, state transition, or group of source operations.

That distinction prevents the documentation from manufacturing implementation symbols.

---

# 🧩 Core source modules

# 5. `dgm_authorized_adoption.py`

Path:

```text
services/hilbert/dgm_authorized_adoption.py
```

This module is the primary source implementation for the candidate, authorization, validation, replay, application, and receipt side of the formal model.

Committed-source inspection explicitly identified the following source symbols:

```text
CandidateEnvelope
AuthorizationEnvelope
candidate_sha256
evaluation_sha256
authorization_payload
validate_candidate_evaluation
validate_authorization
apply_authorized_candidate
```

## Formal correspondence

| Formal object | Source correspondence |
|---|---|
| $`c \in C`$ | `CandidateEnvelope` |
| $`a \in A`$ | `AuthorizationEnvelope` |
| $`H_c(c)`$ | `candidate_sha256` |
| $`H_e(c)`$ | `evaluation_sha256` |
| $`Payload(a)`$ | `authorization_payload` |
| $`V_{evalbody}`$ | `validate_candidate_evaluation` and its bounded checks |
| $`V_{auth}`$ | `validate_authorization` |
| $`\mathcal{A}(c,a,s)`$ | `apply_authorized_candidate` |
| $`M_{auth}`$ | successful return of `apply_authorized_candidate` |
| $`V_{once}`$ / $`S_{spent}`$ | authorization-ID replay and spent-reservation behavior in the authorized application path |
| $`R_{receipt}`$ | receipt creation required before successful authorized-application return |

## Architectural meaning

This mapping is central because the formal model does not treat a candidate as authority.

The source represents the candidate and authorization as different objects.

```text
CandidateEnvelope
        ≠
AuthorizationEnvelope
```

The formal model preserves that implementation separation as:

```math
c\in C
\qquad
a\in A
```

and does not collapse them into one object.

---

# 6. `dgm_public_key_authorization_verifier.py`

Path:

```text
services/hilbert/dgm_public_key_authorization_verifier.py
```

Committed-source interface inspection identified the public-verification surface around:

```text
canonical_payload_bytes
authorization_message_hash
verify_detached_authorization
public_key
signature
ML_DSA_65
```

## Formal correspondence

| Formal object | Source correspondence |
|---|---|
| $`K_{pub}`$ | externally pinned production public verification key consumed by the verifier |
| $`Payload(a)`$ canonical representation | `canonical_payload_bytes` |
| authorization message digest | `authorization_message_hash` |
| $`V_{sig}(a,K_{pub})`$ | `verify_detached_authorization` |

The formal predicate:

```math
V_{sig}(a,K_{pub})=1
```

therefore represents successful detached authorization verification under the pinned public key.

## Authority boundary

The verifier is modeled as a **verifier**.

It is not modeled as the origin of private signing authority.

```text
can verify authority
≠
can create authority
```

The private authorization-signing function is outside this runtime formal object.

---

# 7. `dgm_nbb_authorized_package.py`

Path:

```text
services/hilbert/dgm_nbb_authorized_package.py
```

The committed-source inspection bound this module to the NBB authorized-package boundary and explicitly inspected candidate, authorization, signature, hash, evaluation, publication, and spool behavior.

The formal appendix defines:

```math
V_{NBB}(x)=1
```

if and only if:

```text
validate_authorized_package
```

returns successfully.

## Formal correspondence

| Formal object | Source correspondence |
|---|---|
| external package $`x`$ | NBB authorized-package input |
| $`NValidate(x)`$ | successful authorized-package validation path |
| $`V_{NBB}(x)`$ | successful return of `validate_authorized_package` |
| candidate construction | construction/validation of `CandidateEnvelope` from the package |
| authorization construction | construction/validation of `AuthorizationEnvelope` from the package |
| authorization admission | required authorization validation before successful package admission |
| target admission | required governed-target allowance before successful package admission |

The formal ordering:

```math
NValidate(x)
\prec
Publish(x,q_s)
```

represents the source requirement that validation precedes successful authorized-spool publication.

## Architectural meaning

Package arrival does not create authorized work.

```text
external package exists
≠
authorized spool record exists
```

The NBB boundary must first establish the required validation conditions.

---

# 8. `dgm_authorized_spool.py`

Path:

```text
services/hilbert/dgm_authorized_spool.py
```

This module participates in the authorized-spool and authorization-reservation boundary.

Committed-source replay inspection included this module together with:

```text
dgm_authorized_adoption.py
dgm_worker_authorized_consumer.py
```

for source primitives involving:

```text
authorization_id
spent
replay
consume
reservation
reserve
```

## Formal correspondence

The formal function:

```math
Publish(x,q_s)
```

abstracts successful publication of a validated record into authorized incoming-spool state.

The spool also participates in authorization-identity reservation behavior.

This record does not rename a specific Python function as `Publish` or `Reserve_s` unless the source uses that exact name.

Instead:

```text
Publish
```

means the bounded source behavior that moves a validated authorization record into the authorized incoming-spool state.

And:

```text
Reserve_s
```

means the bounded exclusive reservation behavior that prevents unauthorized reuse at the modeled reservation boundary.

## Architectural meaning

The spool is not merely a queue.

It is part of the authority boundary.

```text
queued
```

in this model means:

```text
admitted through the authorized publication path
```

not merely:

```text
data was written somewhere
```

---

# 9. `dgm_worker_authorized_consumer.py`

Path:

```text
services/hilbert/dgm_worker_authorized_consumer.py
```

This module participates in the worker-side authorized consumption path.

Source inspection established that the worker:

- validates target behavior against the governed root;
- invokes `apply_authorized_candidate`;
- passes the governed object into the authorized application path; and
- participates in authorization replay/consumption handling.

## Formal correspondence

The following formal functions are worker-side abstractions:

```math
Claim(q_s)
```

```math
FinishClaim(r,z,q_s)
```

and the dispatch transition:

```math
Q_3\rightarrow Q_4
```

`Claim` represents the worker's source behavior that either obtains an incoming authorized record or returns no record.

`FinishClaim` represents the worker's terminalization behavior for:

```text
completed
```

or:

```text
rejected
```

records.

These are formal names for source behavior.

They are not assertions that the worker module contains literal functions named `Claim` and `FinishClaim`.

## Counterexample correspondence

The formal model preserves the fact that terminalization is partial.

Therefore:

```math
FinishClaim(r,z,q_s)\uparrow
```

can leave the record at:

```math
Q_3
```

This source-model behavior is the basis for the machine-executed disproof of `P12C-09`.

---

# 10. `dgm_governed_cycle.py`

Path:

```text
services/hilbert/dgm_governed_cycle.py
```

Committed-source inspection explicitly extracted:

```text
DGMProposal
evaluate
apply_proposal
```

and separately inspected governed mutable-target behavior.

The worker correspondence evidence also established that the authorized consumer resolves target validation against:

```text
governed.ROOT
```

and passes the governed object into `apply_authorized_candidate`.

## Formal correspondence

| Formal object | Source correspondence |
|---|---|
| $`Root(s)`$ | governed root represented by `governed.ROOT` |
| $`V_{contain}`$ | target-resolution containment behavior against the governed root |
| $`V_{allow}`$ | governed mutable-target allowance behavior |
| governed proposal | `DGMProposal` |
| bounded proposal evaluation | `evaluate` where applicable to the governed proposal path |
| $`GApply(c,s)`$ | governed mutation behavior represented by `apply_proposal` |
| resulting state $`s'`$ | governed source state after successful proposal application |
| poststate checking | authorized-adoption post-application verification against expected source identity |

## Architectural meaning

Technical filesystem access does not become target authority.

The formal predicate:

```math
V_{target}
=
V_{contain}
\land
V_{allow}
```

captures the source distinction between:

```text
path is technically reachable
```

and:

```text
path is governed and permitted for this mutation path
```

---

# 11. `dgm_evolution_authorization_bridge.py`

Path:

```text
services/hilbert/dgm_evolution_authorization_bridge.py
```

Committed-source inspection examined this module for:

```text
CandidateEnvelope
AuthorizationEnvelope
proposal_id
candidate_sha256
evaluation_sha256
target_before_sha256
authority
authorization
```

## Formal correspondence

This module participates at the boundary where an evaluated evolution proposal is represented in the candidate/authorization protocol.

It therefore supports the source provenance of formal fields such as:

```math
p(c)
```

```math
H_c(c)
```

```math
H_e(c)
```

and:

```math
h_b(c)
```

as they cross into the authorized-adoption architecture.

## Architectural meaning

The bridge can construct or transmit the information required for an authorization decision.

It does not make evaluation self-authorizing.

```text
evolution result
≠
production authority
```

---

# 📐 Formal-object mapping

# 12. Candidate envelope correspondence

The formal candidate is:

```math
c=
(
p,
t,
h_b,
x_a,
e,
\sigma,
\theta
)
```

The source counterpart is `CandidateEnvelope` in:

```text
services/hilbert/dgm_authorized_adoption.py
```

The formal model uses the source-defined candidate fields to represent:

- proposal identity;
- target path;
- expected prestate hash;
- proposed after-content;
- evaluation;
- scores; and
- expected tests.

The source/evidence work also introduced full candidate-envelope commitment where required by the current sealed source.

The formal object does not invent candidate fields outside the source contract.

---

# 13. Authorization envelope correspondence

The formal authorization is:

```math
a=
(
i,
p,
d,
h_c,
h_{env},
h_e,
t,
h_b,
u,
k,
\tau_i,
\tau_e,
sig
)
```

The source counterpart is `AuthorizationEnvelope` in:

```text
services/hilbert/dgm_authorized_adoption.py
```

Its validation surface includes the source concepts represented formally as:

```text
authorization identity
approval decision
authority class
lifetime
proposal binding
target binding
prestate binding
candidate binding
evaluation binding
signature verification
```

The formal object therefore preserves the production design that authority is a structured, bound object rather than a Boolean attached to a candidate.

---

# 14. Hash correspondence

The formal candidate-content identity is:

```math
H_c(c)=SHA256(x_a)
```

and maps to:

```text
candidate_sha256
```

The formal evaluation identity is:

```math
H_e(c)=SHA256(CanonicalJSON(e))
```

and maps to:

```text
evaluation_sha256
```

The authorization source also contains canonical authorization-payload handling, while the public verifier contains canonical payload and authorization-message hashing for detached verification.

These hashes are identity bindings.

They do not establish semantic equivalence by themselves.

---

# 15. Evaluation correspondence

The formal evaluation body is:

```math
V_{evalbody}
=
V_{source}
\land
V_{compile}
\land
V_{benchmark}
```

The source counterpart is the bounded evaluation-validation behavior in:

```text
validate_candidate_evaluation
```

within:

```text
services/hilbert/dgm_authorized_adoption.py
```

At minimum, the formal model represents the source requirements that the evaluation correspond to the candidate source identity and that required compile/benchmark conditions succeed.

A passing evaluation remains evidence about the candidate.

It does not create authorization.

---

# 16. Composite authorization correspondence

The formal authorization predicate is:

```math
V_{auth}
=
V_{id}
\land
V_{decision}
\land
V_{class}
\land
V_{time}
\land
V_{proposal}
\land
V_{targetbind}
\land
V_{prebind}
\land
V_{candidate}
\land
V_{evaluation}
\land
V_{evalbody}
\land
V_{sig}
```

with full-envelope binding included where required by the sealed source.

The source counterpart is the combined validation behavior centered on:

```text
validate_authorization
```

plus the detached public-key verification interface.

The formal conjunction represents source requirements that must succeed together.

No individual predicate is promoted into complete authorization.

---

# 17. Target correspondence

The formal target-safety condition is:

```math
V_{target}
=
V_{contain}
\land
V_{allow}
```

This maps to the governed target behavior represented across:

```text
dgm_authorized_adoption.py
dgm_worker_authorized_consumer.py
dgm_governed_cycle.py
```

The worker-side evidence establishes target validation against `governed.ROOT`.

The governed source provides the mutable-target policy and proposal-application boundary.

The authorized-application source requires target validation before successful application.

Thus the model represents a source behavior distributed across the bounded adoption path rather than pretending that target authority is implemented by one isolated line of code.

---

# 18. Prestate correspondence

The formal predicate is:

```math
V_{pre}(c,s)=1
```

only when:

```math
H_{current}(s,t(c))=h_b(c)
```

The source counterpart is the pre-mutation comparison in the authorized application path.

Its meaning is:

```text
current governed source
must still match
the source state authorized by the candidate/authorization
```

If the source has changed, the modeled successful path is not available.

This prevents stale authority from silently migrating to a different source state.

---

# 19. One-use authorization correspondence

The formal one-use predicate is:

```math
V_{once}(a,L_s)=1
```

only if:

```math
i(a)\notin L_s
```

The formal reservation operation is:

```math
Reserve_s(a,L_s)
```

The sealed-source replay inspection covered:

```text
dgm_authorized_adoption.py
dgm_authorized_spool.py
dgm_worker_authorized_consumer.py
```

and searched the committed implementation for:

```text
authorization_id
O_EXCL
spent
replay
consume
consumed
reservation
reserve
```

The source-model result establishes that a previously consumed authorization identity cannot successfully traverse the same bounded application path again.

## Architectural meaning

```text
authority was valid once
≠
authority remains valid forever
```

---

# 20. Governed application correspondence

The formal mutation function is:

```math
GApply(c,s)
```

The source mapping is two-layered.

The authorized adoption layer is:

```text
apply_authorized_candidate
```

in:

```text
dgm_authorized_adoption.py
```

The governed mutation layer is represented by:

```text
apply_proposal
```

in:

```text
dgm_governed_cycle.py
```

The formal authorized-application function therefore represents the source composition:

```text
validate authorization
        ↓
validate governed target
        ↓
verify current prestate
        ↓
reserve one-use authorization
        ↓
invoke governed proposal application
        ↓
verify poststate
        ↓
create receipt
```

This is why the model defines a partial function rather than equating source-writing capability with successful authorized adoption.

---

# 21. Receipt correspondence

The formal receipt function is:

```math
Receipt(c,a,s')
```

with successful receipt predicate:

```math
R_{receipt}(c,a,s')=1
```

The receipt source behavior belongs to the successful `apply_authorized_candidate` path.

The formal receipt binds the transition to identities including:

- authorization ID;
- proposal ID;
- candidate hash;
- evaluation hash;
- target;
- authorized prestate;
- resulting state hash;
- signature-verification result; and
- one-use handling.

The receipt records evidence of a successful governed transition.

It does not create retrospective authority for that transition.

---

# 22. NBB validation correspondence

The formal validation function is:

```math
NValidate(x)
```

The source-model success predicate is:

```math
V_{NBB}(x)=1
```

if and only if:

```text
validate_authorized_package
```

returns successfully.

The successful path requires the package to produce candidate and authorization objects whose required authorization and target conditions pass.

Thus:

```text
package arrival
≠
validated package
```

and:

```text
validated package
precedes
authorized spool publication
```

---

# 23. Publication correspondence

The formal publication function is:

```math
Publish(x,q_s)
```

This is a behavioral abstraction over the authorized-spool publication path.

The required ordering is:

```math
NValidate(x)
\prec
Publish(x,q_s)
```

The formal model therefore does not assert that any write to a queue constitutes authorized publication.

It represents only the successful publication path downstream of validation.

---

# 24. Worker claim correspondence

The formal worker claim is:

```math
Claim(q_s)
```

with:

```math
Claim(q_s)=\varnothing
```

when no incoming record exists.

The source counterpart is the worker authorized-consumer behavior that attempts to obtain authorized work and exits the application path when no incoming record is available.

This source behavior supports:

```math
Incoming(q_s)=\varnothing
\Rightarrow
Claim(q_s)=\varnothing
\Rightarrow
NoAuthorizedApply
```

which becomes theorem `T12D-C`.

---

# 25. Terminalization correspondence

The formal terminalization function is:

```math
FinishClaim(r,z,q_s)
```

where:

```math
z\in\{completed,rejected\}
```

This abstracts the worker's successful completion/rejection transition behavior.

The source model also permits terminalization failure.

Therefore:

```math
FinishClaim(r,z,q_s)\uparrow
```

can preserve:

```math
State'(r)=Q_3
```

This is why the model does not force:

```math
Q_3
\Rightarrow
Q_{6C}\lor Q_{6R}
```

and why `P12C-09` is preserved as `MACHINE_CHECKED_DISPROVEN`.

---

# 🔄 State-model correspondence

# 26. Formal states map to execution boundaries

The formal states are:

```math
Q=
\{
Q_0,Q_1,Q_2,Q_3,Q_4,Q_{5A},Q_{6C},Q_{6R}
\}
```

They are **model states**, not a claim that the source declares a Python enum containing these exact labels.

Their source correspondence is behavioral:

| Formal state | Source meaning |
|---|---|
| $`Q_0`$ `EXTERNAL_PACKAGE` | package exists before successful NBB validation |
| $`Q_1`$ `NBB_VALIDATED` | `validate_authorized_package` has successfully returned |
| $`Q_2`$ `INCOMING_SPOOL` | validated record has been published to authorized incoming spool |
| $`Q_3`$ `WORKER_CLAIMED` | worker has successfully claimed the record |
| $`Q_4`$ `AUTHORIZED_APPLY_GATE` | worker dispatch has entered the bounded authorized-application path |
| $`Q_{5A}`$ `AUTHORIZED_APPLIED` | `apply_authorized_candidate` has successfully completed the governed application conditions |
| $`Q_{6C}`$ `TERMINAL_COMPLETED` | successful completion terminalization |
| $`Q_{6R}`$ `TERMINAL_REJECTED` | successful rejection terminalization |

This makes the state model an abstraction of source execution boundaries, not a separate fictional implementation.

---

# 27. Transition relation maps to source ordering

The formal transition relation is:

```math
\delta\subseteq Q\times\Sigma\times Q
```

The principal modeled transitions are derived from source call/return ordering:

```math
\delta(Q_0,V_{NBB}=1)=Q_1
```

```math
\delta(Q_1,Publish\downarrow)=Q_2
```

```math
\delta(Q_2,Claim\downarrow)=Q_3
```

```math
\delta(Q_3,WorkerDispatch)=Q_4
```

```math
\delta(Q_4,M_{auth}=1)=Q_{5A}
```

```math
\delta(Q_{5A},FinishClaim(completed)\downarrow)=Q_{6C}
```

and the bounded rejected/terminalization-failure paths.

The transition system therefore represents **required source ordering**.

It does not assert an independent state machine that is absent from the implementation.

---

# ✅ Theorem correspondence to source

# 28. T12D-A source basis

The principal theorem is:

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

Its source basis is the successful ordering represented by `apply_authorized_candidate` and the governed mutation path.

The theorem is therefore a statement about successful return from the **sealed source path**, not a free-standing architecture aspiration.

Final level:

```text
MACHINE_CHECKED
```

It is not promoted to positive runtime correspondence because no real positive production authorization/application was exercised during Step 12.

Later post-A8 work re-established current source/runtime correspondence for the same bounded source identity, but still did not execute the positive authorized-apply production path:

```text
T12D_A_POSITIVE_AUTHORIZED_APPLY_EXECUTED=NO
T12D_A_CURRENT_CORRESPONDENCE_VERIFIED=NO
```

Therefore the current level remains:

```text
MACHINE_CHECKED
```

---

# 29. T12D-B source basis

The theorem is:

```math
\boxed{
\neg V_{auth}
\Rightarrow
\neg Publish
}
```

Its source basis is the NBB ordering in which authorization/package validation precedes successful authorized-spool publication.

The relevant implementation boundary is:

```text
dgm_nbb_authorized_package.py
        ↓
dgm_authorized_spool.py
```

The source theorem was later combined with source-to-runtime correspondence and live fail-closed observation.

The newest current observation epoch is the post-A8 revalidation:

```text
CURRENT_POST_A8_DGM_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11
T12D_B_LIVE_OBSERVATION=PASS
T12D_B_POST_A8_CORRESPONDENCE_VERIFIED=YES
```

Final/current level:

```text
CORRESPONDENCE_VERIFIED
```

---

# 30. T12D-C source basis

The theorem is:

```math
\boxed{
Incoming(q_s)=\varnothing
\Rightarrow
Claim(q_s)=\varnothing
\Rightarrow
NoAuthorizedApply
}
```

Its source basis is the worker authorized-consumer behavior that exits without entering `apply_authorized_candidate` when no incoming authorized record can be claimed.

Final/current level:

```text
CORRESPONDENCE_VERIFIED
```

after source-to-runtime correspondence and live empty-spool observation were separately established.

The newest current observation epoch is the post-A8 revalidation:

```text
CURRENT_POST_A8_DGM_SOURCE_TO_RUNTIME_CORRESPONDENCE=PASS_11_OF_11
T12D_C_LIVE_OBSERVATION=PASS
T12D_C_POST_A8_CORRESPONDENCE_VERIFIED=YES
```

---

# 31. P12C-09 source basis

The disproven proposition was:

```math
Q_3
\Rightarrow
Q_{6C}\lor Q_{6R}
```

The source model permits terminalization to fail.

Therefore the modeled worker behavior admits:

```math
\delta(Q_3,FinishClaim\uparrow)=Q_3
```

The counterexample is not a discrepancy between the source and the model.

It is a property of the source-derived model itself.

Final disposition:

```text
MACHINE_CHECKED_DISPROVEN
```

---

# 🛡️ Correspondence discipline

# 32. The mapping is directional

The mapping in this record is:

```math
\Phi_{FS}:F\rightarrow\mathcal{B}(S)
```

where $`\mathcal{B}(S)`$ denotes the bounded source behaviors represented by the formal model.

The correspondence means that the formal objects are grounded in sealed source behavior.

It does **not** imply that every source behavior appears in the formal model.

Formally:

```math
C_{FS}(F,S)=1
```

does not imply:

```math
F=S
```

and does not imply:

```math
F
\text{ covers all behavior in }
S
```

The model intentionally covers the authorized-adoption pathway only.

---

# 33. Source identity is necessary but not sufficient

The exact source commit and file hashes establish identity.

They do not, by themselves, establish that the mathematics correctly represents the implementation.

The Step-12 correspondence method therefore combines:

```text
sealed source identity
+
source-symbol inspection
+
source control-flow/order analysis
+
bounded execution evidence
+
formal proposition adjudication
```

The result is stronger than a diagram tied only to filenames.

It is also narrower than a claim that all implementation semantics have been formally verified.

The later Lean R1 workstream strengthens the formal proposition layer, but does not replace this mapping.

Likewise, the later post-A8 source/runtime revalidation strengthens the runtime bridge, but does not rewrite the source-symbol and source-order reasoning recorded here.

Conceptually:

```text
Lean proof qualification
    ≠
model → source correspondence

model → source correspondence
    ≠
source → runtime correspondence

source → runtime correspondence
    ≠
theorem-specific live observation
```

---

# 34. Source changes invalidate unrefreshed correspondence

This correspondence record is tied to:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

A later source revision does not inherit:

```math
C_{FS}(F,S)=1
```

merely because it descends from that commit.

For changed source $`S'`$:

```math
S'\neq S
```

requires a new correspondence determination before the current formal model can be treated as authoritative for the changed behavior.

```text
source descended from sealed source
≠
formal correspondence automatically preserved
```

This is the documentation equivalent of prestate binding in the adoption model.

---

# 35. Authority issuance remains outside the runtime model

The formal model includes authorization verification.

It does not model the runtime verifier as the source of authorization authority.

Therefore:

```text
authorization verification
≠
authorization issuance
```

The private signing authority and its issuance/governance process remain outside the bounded runtime model.

This is an explicit residual boundary, not a missing implicit capability.

---

# 36. What this correspondence establishes

This record establishes that, within the bounded authorized-adoption domain:

- the formal candidate maps to the production `CandidateEnvelope`;
- the formal authorization maps to the production `AuthorizationEnvelope`;
- candidate and evaluation hashes map to committed source hash functions;
- the composite authorization predicate maps to the source authorization-validation path;
- cryptographic verification maps to the detached public-key verifier;
- NBB validation maps to `validate_authorized_package`;
- publication maps to the validated authorized-spool publication behavior;
- claim and terminalization map to worker authorized-consumer behavior;
- target containment and allowance map to the governed root and mutable-target policy;
- governed application maps to `apply_authorized_candidate` plus governed `apply_proposal`;
- replay protection maps to authorization-ID reservation/consumption behavior;
- receipt correspondence maps to required successful receipt generation; and
- the formal transition relation represents the source ordering that connects those boundaries.

Therefore:

```math
\boxed{
C_{FS}(F,S)=1
}
```

for the sealed bounded production authorized-adoption model.

---

# 37. What this correspondence does not establish

This record does not establish:

```text
FORMAL_MODEL_COVERS_ALL_ALLIS_BEHAVIOR=YES
```

It does not establish:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=YES
```

It does not establish:

```text
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=YES
```

It does not establish:

```text
SYSTEM_PROVEN=YES
```

It also does not establish that correspondence remains true after future source changes without revalidation.

The controlling statements remain:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

---

# 38. Architectural meaning

This correspondence layer exists because an architecture description is not allowed to grant itself authority over reality.

The mathematical model says:

```text
this is how the bounded system behaves
```

The correspondence record asks:

```text
does the sealed implementation actually contain
the objects, predicates, ordering, and failure behavior
that make that statement true?
```

Only after that mapping is established is the formal model treated as a model of the sealed production source.

This mirrors the larger ALLIS architecture:

```text
proposal
≠
authority

evidence
≠
authority

model
≠
implementation

documentation claim
≠
established correspondence
```

> **The model earns authority as a description only through correspondence to the source it claims to describe.**

---

# 39. Final correspondence statement

Let:

```math
F=
DGM\_PRODUCTION\_AUTHORIZED\_ADOPTION\_MODEL\_V1
```

and let $`S`$ be the exact sealed 11-file production source set at:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

Then, within the bounded production authorized-adoption domain:

```math
\boxed{
C_{FS}(F,S)=1
}
```

This means the formal model is derived from and bound to the sealed production source behavior represented in this record.

It does not mean:

```math
F
=
\text{whole ALLIS system}
```

and it does not imply:

```math
SYSTEM\_PROVEN=YES
```

---

# 40. Seal identity

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

No stronger correspondence claim is implied by this record.

---

# 📚 41. Companion records

This record belongs at:

```text
correspondence/
    authorized-adoption/
        model-to-source.md
        source-to-runtime.md
```

and should be read with:

```text
formal-verification/
    authorized-adoption/
        formal-model.md
        theorem-registry.md
        counterexample-registry.md
        lean/
            workstream-closeout-r1.md

evidence/
    governed-evolution/
        step12-final-seal.md
        post-a8-theorem-correspondence-registry-r1.md
        source-identity.md
        trust-anchor.md
        governance-view.md
        residuals.md
```

Use:

- [`formal-model.md`](../../formal-verification/authorized-adoption/formal-model.md) — mathematical object
- [`theorem-registry.md`](../../formal-verification/authorized-adoption/theorem-registry.md) — proposition disposition and validation level
- [`counterexample-registry.md`](../../formal-verification/authorized-adoption/counterexample-registry.md) — falsifying cases
- [`lean/workstream-closeout-r1.md`](../../formal-verification/authorized-adoption/lean/workstream-closeout-r1.md) — later Lean R1 proposition-layer qualification and formal-statement crosswalk
- [`model-to-source.md`](model-to-source.md) — formal-to-source correspondence
- [`source-identity.md`](../../evidence/governed-evolution/source-identity.md) — canonical sealed 11-file source manifest and hashes
- [`post-a8-theorem-correspondence-registry-r1.md`](../../evidence/governed-evolution/post-a8-theorem-correspondence-registry-r1.md) — later current source/runtime and B/C live revalidation
- [`source-to-runtime.md`](source-to-runtime.md) — separate source-to-runtime correspondence question


---

# 🧾 Model-to-source correspondence summary

<div align="center">

### 📐 FORMAL MODEL
**`DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1`**

↓

### 🔗 MODEL → SOURCE CORRESPONDENCE
**`C_FS(F,S)=1` · PASS**

↓

### 💻 SEALED PRODUCTION SOURCE
**commit `20c8cbe1…` · 11-file bounded source set**

<br>

### Separate edge
**source → runtime remains independently evidenced**

### ➕ SUCCESSOR EVIDENCE
**Lean R1 qualifies the proposition layer but did not itself establish production source correspondence**

**post-A8 work later re-established current source/runtime 11/11 and separately live-observed B/C**

<br>

# `SYSTEM_PROVEN=NO`

</div>

---

# Governing correspondence principle
> **A formal description is not authoritative merely because it is mathematically coherent. It becomes an evidence-backed description of production only when correspondence to the sealed implementation is established.**

> **Later proof-assistant qualification, source/runtime correspondence, and live observation are distinct successor evidence layers; none silently substitutes for another.**
