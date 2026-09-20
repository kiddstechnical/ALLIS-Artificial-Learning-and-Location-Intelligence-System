# Formal model: governed production adoption

## Purpose

This document defines the current formal model for the bounded ALLIS production authorized-adoption pathway.

The formal object is:

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

The model describes how a proposed software change can move from candidate state to production state without allowing technical capability, successful evaluation, or runtime access to become authority by themselves.

The governing architecture is:

> **Capability does not create authority.**

A candidate can exist without being authorized.  
A candidate can evaluate successfully without being authorized.  
A candidate can compile and pass a benchmark without being authorized.  
A runtime can be technically capable of applying a change without being authorized to apply it.

ALLIS therefore models **proposal, evaluation, authorization, adoption, and evidence as separate states and responsibilities**.

```text
PROPOSE
  │
  │  A candidate exists.
  ▼
EVALUATE
  │
  │  Evidence can support the candidate.
  │  Evidence does not authorize the candidate.
  ▼
AUTHORIZE
  │
  │  Independent authority must bind to the exact candidate,
  │  target, expected prestate, evaluation, time window,
  │  and one-use authorization identity.
  ▼
ADOPT
  │
  │  The runtime independently rechecks the authorization,
  │  target, current source state, and replay state.
  ▼
RECORD
     A successful transition produces durable evidence.
```

The central distinction is:

```text
can do
≠
may do
```

That distinction is the architectural theme of this formal model.

---

## Document status

| Field | Value |
|---|---|
| Document role | Current formal specification record |
| Formal object | `DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1` |
| Production source commit | `20c8cbe175781c8a1c05d65c03977859ceca884a` |
| Source domain | Sealed 11-file production authorized-adoption source set |
| Formal close status | `GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS` |
| Final Step-12 seal SHA-256 | `b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b` |
| Controlling scope | `BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY` |

This document describes the current bounded production model.

It does not use an earlier mutation model as current authority unless a separate current correspondence record explicitly carries that result forward.

---

## 1. What this model establishes

This model formalizes a production path in which intelligence and operational authority remain separate.

It establishes a bounded architecture with these properties:

- a candidate is represented independently from its authorization;
- an evaluation is bound to the candidate it evaluates;
- an authorization is bound to an exact proposal, target, candidate content, evaluation, expected prestate, authority class, and time window;
- the runtime verifies authority rather than creating its own authority;
- the runtime checks that the target remains permitted;
- the runtime checks that the source still matches the state that was authorized;
- an authorization is one-use;
- successful application produces durable evidence; and
- failed or disproven properties remain visible rather than being silently promoted.

The model does **not** establish:

- whole-system safety;
- general production-mutation safety;
- unrestricted autonomous self-modification;
- universal correctness of candidate evaluation;
- perpetual source-to-runtime correspondence; or
- authority issuance by the NBB or worker runtime.

The model is intentionally narrower than those claims.

---

## 2. Model boundary

The modeled production pathway is:

```text
External package
      │
      ▼
NBB validation
      │
      │  Validation succeeds only if the package carries
      │  acceptable authorization and an allowed target.
      ▼
Authorized spool
      │
      ▼
Worker claim
      │
      ▼
Authorized-apply gate
      │
      │  Runtime rechecks authority, target, prestate,
      │  one-use status, and application conditions.
      ▼
Governed application
      │
      ▼
Terminal state + evidence
```

Let the bounded model be:

```math
\mathcal{M}_{DGM}
=
(Q,\Sigma,\delta,\mathcal{P},\mathcal{F})
```

where:

- $`Q`$ is the set of modeled states;
- $`\Sigma`$ is the set of relevant inputs and artifacts;
- $`\delta`$ is the transition relation;
- $`\mathcal{P}`$ is the set of modeled predicates; and
- $`\mathcal{F}`$ is the set of modeled functions.

The model includes only the sealed production authorized-adoption path.

---

## 3. Architectural separations

The model depends on several explicit separations.

| Concept | Not equivalent to |
|---|---|
| Candidate existence | Authorization |
| Candidate evaluation | Authorization |
| Benchmark success | Authorization |
| Runtime capability | Permission to execute |
| Source presence | Authority |
| Claimed work | Completed work |
| Machine-checked theorem | Positive live observation |
| Runtime correspondence | Perpetual invariance |
| Bounded proof | Whole-system proof |

These separations prevent one state from being promoted into a stronger state without the evidence and authority required for that promotion.

> **Architecture rule:** State does not become authority merely because it exists.

---

## 4. Notation

| Symbol | Meaning |
|---|---|
| $`c \in C`$ | Candidate envelope |
| $`a \in A`$ | Authorization envelope |
| $`s \in S`$ | Governed runtime state |
| $`q_s`$ | Authorized-spool state |
| $`K_{pub}`$ | Pinned public verification key |
| $`\tau`$ | Current epoch time |
| $`\downarrow`$ | Bounded function returns successfully |
| $`\uparrow`$ | Bounded function rejects, raises, or otherwise fails to return successfully |
| $`H(x)`$ | SHA-256 identity function over the defined representation of $`x`$ |

The authorized-application function is:

```math
\mathcal{A}:
C \times A \times S
\rightharpoonup
S' \times R
```

where:

- $`C`$ is the candidate-envelope domain;
- $`A`$ is the authorization-envelope domain;
- $`S`$ is the governed-state domain;
- $`S'`$ is the resulting governed-state domain; and
- $`R`$ is the application-receipt domain.

The symbol $`q_s`$ denotes authorized-spool state and is distinct from the formal state set $`Q`$.

---

## 5. State space

Define:

```math
Q=
\{
Q_0,Q_1,Q_2,Q_3,Q_4,Q_{5A},Q_{6C},Q_{6R}
\}
```

with:

```math
Q_0=\text{EXTERNAL\_PACKAGE}
```

```math
Q_1=\text{NBB\_VALIDATED}
```

```math
Q_2=\text{INCOMING\_SPOOL}
```

```math
Q_3=\text{WORKER\_CLAIMED}
```

```math
Q_4=\text{AUTHORIZED\_APPLY\_GATE}
```

```math
Q_{5A}=\text{AUTHORIZED\_APPLIED}
```

```math
Q_{6C}=\text{TERMINAL\_COMPLETED}
```

```math
Q_{6R}=\text{TERMINAL\_REJECTED}
```

The normal successful path is:

```math
Q_0
\rightarrow
Q_1
\rightarrow
Q_2
\rightarrow
Q_3
\rightarrow
Q_4
\rightarrow
Q_{5A}
\rightarrow
Q_{6C}
```

A rejected record can terminate at $`Q_{6R}`$, subject to successful terminalization.

The model also admits a nonterminal claimed state when terminalization itself fails.

### Authority across the state path

The state sequence does not represent a gradual accumulation of self-created authority.

```text
Q0  External package          Candidate and authorization arrive as data.
Q1  NBB validated             Runtime has verified required conditions.
Q2  Incoming spool            Work is eligible to be claimed.
Q3  Worker claimed            Work is claimed, not yet authorized-applied.
Q4  Authorized-apply gate     Runtime independently rechecks adoption conditions.
Q5A Authorized applied        The governed transition has succeeded.
Q6C Completed                 Terminal evidence records completion.
Q6R Rejected                  Terminal evidence records rejection.
```

No earlier state is treated as sufficient authority for a later state merely because it was reached.

---

## 6. Candidate envelope

Define a candidate envelope as:

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

where:

- $`p`$ = proposal identifier;
- $`t`$ = target path;
- $`h_b`$ = expected target-before hash;
- $`x_a`$ = proposed after-content;
- $`e`$ = evaluation object;
- $`\sigma`$ = candidate scores; and
- $`\theta`$ = expected tests.

The source-content identity is:

```math
H_c(c)=SHA256(x_a)
```

The evaluation identity is:

```math
H_e(c)=SHA256(CanonicalJSON(e))
```

Where the sealed source uses full candidate-envelope binding, define:

```math
H_{env}(c)=SHA256(CanonicalJSON(c))
```

A candidate therefore represents a proposed transition and its supporting evaluation context.

It does **not** represent permission to perform the transition.

> **Architecture rule:** A candidate is a proposal object, not an authority object.

---

## 7. Authorization envelope

Define an authorization envelope as:

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

where:

- $`i`$ = authorization identifier;
- $`p`$ = proposal identifier;
- $`d`$ = decision;
- $`h_c`$ = candidate-content hash;
- $`h_{env}`$ = candidate-envelope hash where present;
- $`h_e`$ = evaluation hash;
- $`t`$ = authorized target;
- $`h_b`$ = authorized prestate hash;
- $`u`$ = approving identity;
- $`k`$ = authority class;
- $`\tau_i`$ = issuance time;
- $`\tau_e`$ = expiration time; and
- $`sig`$ = detached signature.

Define the unsigned authorization payload as:

```math
Payload(a)=a\setminus\{sig\}
```

The authorization does not merely say "a change is allowed."

It binds permission to a specific change context.

```text
authorization
    ├── proposal identity
    ├── candidate identity
    ├── evaluation identity
    ├── target
    ├── expected prestate
    ├── authority class
    ├── approving identity
    ├── issue time
    ├── expiration time
    └── detached signature
```

The runtime verifier verifies this authority.

The runtime verifier is not modeled as the source that mints its own authorization.

> **Architecture rule:** The component capable of applying the change does not acquire authority merely from that capability.

---

## 8. Cryptographic identity

For byte-oriented objects, define:

```math
H(x)=SHA256(x)
```

For canonical JSON structures, define:

```math
H_J(x)=SHA256(CanonicalJSON(x))
```

These hashes bind exact object identities.

They are not semantic-equivalence functions.

Therefore:

```math
H(x)=H(y)
```

is evidence that the compared sealed representations have the same byte identity under the defined hashing procedure.

It is not a claim that arbitrary semantic systems are mathematically equivalent.

---

## 9. Signature verification

Define:

```math
V_{sig}:A\times K\rightarrow\{0,1\}
```

such that:

```math
V_{sig}(a,K_{pub})=1
```

if and only if the detached authorization signature verifies against the canonical authorization message under the pinned public key.

Conceptually:

```math
Verify(
K_{pub},
HashMessage(Payload(a)),
sig(a)
)
```

must succeed.

The modeled production verifier verifies authority.

It does not mint the private signing authority that it verifies.

---

## 10. Authorization predicates

Authorization is composite.

No single successful check is sufficient.

### 10.1 Authorization identifier

```math
V_{id}(a)\in\{0,1\}
```

$`V_{id}(a)=1`$ only if the authorization identifier satisfies the permitted production syntax.

### 10.2 Approval decision

```math
V_{decision}(a)=
\begin{cases}
1,&d(a)=APPROVE\\
0,&otherwise
\end{cases}
```

### 10.3 Authority class

Let:

```math
\mathcal{K}
=
\{
BBB\_GUARDIAN,
CONSTITUTIONAL\_GUARDIAN
\}
```

Then:

```math
V_{class}(a)=
\begin{cases}
1,&k(a)\in\mathcal{K}\\
0,&otherwise
\end{cases}
```

### 10.4 Authorization time

Define:

```math
V_{time}(a,\tau)=1
```

only when:

```math
\tau_e(a)>\tau_i(a)
```

and:

```math
\tau_i(a)\le\tau\le\tau_e(a)
```

Otherwise:

```math
V_{time}(a,\tau)=0
```

### 10.5 Proposal binding

```math
V_{proposal}(c,a)=
\begin{cases}
1,&p(c)=p(a)\\
0,&otherwise
\end{cases}
```

### 10.6 Target binding

```math
V_{targetbind}(c,a)=
\begin{cases}
1,&t(c)=t(a)\\
0,&otherwise
\end{cases}
```

### 10.7 Prestate binding

```math
V_{prebind}(c,a)=
\begin{cases}
1,&h_b(c)=h_b(a)\\
0,&otherwise
\end{cases}
```

### 10.8 Candidate binding

```math
V_{candidate}(c,a)=
\begin{cases}
1,&h_c(a)=H_c(c)\\
0,&otherwise
\end{cases}
```

Where the sealed source uses full candidate-envelope binding:

```math
V_{envelope}(c,a)=
\begin{cases}
1,&h_{env}(a)=H_{env}(c)\\
0,&otherwise
\end{cases}
```

### 10.9 Evaluation binding

```math
V_{evaluation}(c,a)=
\begin{cases}
1,&h_e(a)=H_e(c)\\
0,&otherwise
\end{cases}
```

The evaluation body must also satisfy the bounded production requirements.

At minimum:

```math
V_{source}=1
\iff
e.source\_sha256=H_c(c)
```

```math
V_{compile}=1
\iff
e.compile\_ok=True
```

```math
V_{benchmark}=1
\iff
e.benchmark.passed=True
```

Define:

```math
V_{evalbody}
=
V_{source}
\land
V_{compile}
\land
V_{benchmark}
```

A passing evaluation contributes evidence about the candidate.

It still does not create adoption authority.

---

## 11. Composite authorization

Define:

```math
V_{auth}(c,a,\tau)
```

as:

```math
\begin{aligned}
V_{auth}
={}&
V_{id}
\land
V_{decision}
\land
V_{class}
\land
V_{time}
\land
V_{proposal}
\\
&\land
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
\end{aligned}
```

Where full-envelope binding is required by the sealed source, $`V_{envelope}`$ is also required.

Therefore:

```math
V_{auth}(c,a,\tau)=1
```

if and only if every required predicate succeeds.

This design prevents partial validity from being treated as full authority.

```text
valid signature only                     → not enough
valid candidate hash only                → not enough
passing benchmark only                   → not enough
valid target only                        → not enough
valid time window only                   → not enough
all required predicates together         → valid authorization
```

> **Architecture rule:** Authority is not inferred from evidence. Authority is independently represented and verified.

---

## 12. Target safety

Let $`Root(s)`$ be the governed filesystem root.

Define:

```math
Resolve(R,t)
```

as target resolution within root $`R`$.

The containment predicate is:

```math
V_{contain}(s,t)=
\begin{cases}
1,&Resolve(Root(s),t)\subseteq Root(s)\\
0,&otherwise
\end{cases}
```

Define:

```math
V_{allow}(t)\in\{0,1\}
```

where:

```math
V_{allow}(t)=1
```

only if the governed target policy permits mutation of target $`t`$.

The composite target predicate is:

```math
V_{target}(s,t)
=
V_{contain}(s,t)
\land
V_{allow}(t)
```

Technical access to a path does not imply authority to mutate that path.

---

## 13. Current-state and prestate correspondence

Define:

```math
CurrentText(s,t)
```

as the currently stored text of target $`t`$ in governed state $`s`$.

Define:

```math
H_{current}(s,t)
=
SHA256(CurrentText(s,t))
```

The prestate predicate is:

```math
V_{pre}(c,s)=
\begin{cases}
1,&H_{current}(s,t(c))=h_b(c)\\
0,&otherwise
\end{cases}
```

A candidate authorized against stale source therefore fails the current-prestate condition.

This separates:

```text
authority for this exact source state
```

from:

```text
authority for whatever source happens to exist later
```

The model accepts the first interpretation and rejects the second.

> **Architecture rule:** Authorization has provenance and context. It does not float free of the state it authorized.

---

## 14. One-use authority

Let $`L_s`$ be the set of authorization identifiers represented by successful exclusive spent reservations.

Define:

```math
V_{once}(a,L_s)=
\begin{cases}
1,&i(a)\notin L_s\\
0,&i(a)\in L_s
\end{cases}
```

Define the partial reservation function:

```math
Reserve_s(a,L_s)
```

such that:

```math
Reserve_s(a,L_s)\downarrow
```

if and only if:

```math
i(a)\notin L_s
```

A successful reservation produces:

```math
L_s'=L_s\cup\{i(a)\}
```

If:

```math
i(a)\in L_s
```

then:

```math
Reserve_s(a,L_s)\uparrow
```

and the authorization is rejected as a replay.

A valid prior authorization therefore does not become standing authority for repeated future changes.

---

## 15. Governed application

Define:

```math
GApply(c,s)
```

as the governed mutation function acting on candidate $`c`$ and governed state $`s`$.

A successful application produces:

- a verdict $`v`$ with `v.applied=True`; and
- a resulting governed state $`s'`$.

The candidate source-content hash $`H_c(c)`$ is the expected identity of the proposed after-content.

The sealed implementation performs a poststate check before the authorized application can return successfully.

The model therefore treats successful mutation as a governed transition, not as the simple consequence of possessing code-writing capability.

---

## 16. Receipt function

Define:

```math
Receipt(c,a,s')
```

as the production application receipt.

A successful receipt binds, among other fields:

- $`i(a)`$, the authorization identifier;
- $`p(c)`$, the proposal identifier;
- $`H_c(c)`$, the candidate-content hash;
- $`H_e(c)`$, the evaluation hash;
- $`t(c)`$, the target;
- $`h_b(c)`$, the authorized prestate hash;
- $`H_{current}(s',t(c))`$, the resulting target-state hash;
- successful signature verification; and
- successful one-use authorization handling.

Define:

```math
R_{receipt}(c,a,s')=1
```

if and only if the expected application receipt is durably created for the successful application.

This receipt does not create retrospective authority.

It records evidence that an authorized transition completed under the modeled conditions.

---

## 17. Authorized-application function

Define:

```math
\mathcal{A}:
C\times A\times S
\rightharpoonup
S'\times R
```

with:

```math
\mathcal{A}(c,a,s)\downarrow
```

only through the ordered sequence:

```math
V_{auth}
\rightarrow
V_{target}
\rightarrow
V_{pre}
\rightarrow
Reserve_s
\rightarrow
GApply
\rightarrow
PoststateCheck
\rightarrow
Receipt
```

Define:

```math
M_{auth}(c,a,s)=1
\iff
\mathcal{A}(c,a,s)\downarrow
```

The sequence is intentionally ordered.

```text
authorization
      ↓
target permission
      ↓
current-state correspondence
      ↓
one-use reservation
      ↓
mutation
      ↓
poststate verification
      ↓
receipt
```

A later successful operation cannot repair a failed earlier requirement.

> **Architecture rule:** The system does not ask, "Can this change be executed?" It asks, "Has every condition required to authorize this exact transition been satisfied?"

---

## 18. NBB validation

Let $`x`$ be an external package.

Define:

```math
NValidate(x)
```

as the NBB validation function.

Successful validation requires construction of $`c`$ and $`a`$, followed by:

```math
V_{auth}(c,a,\tau)=1
```

and:

```math
V_{allow}(t(c))=1
```

Define:

```math
V_{NBB}(x)=1
```

if and only if the bounded authorized-package validation returns successfully.

The NBB therefore acts as an admission boundary.

It does not treat package arrival as permission to publish work.

---

## 19. Authorized spool publication

Define:

```math
Publish(x,q_s)
```

as the partial function that publishes a validated authorization record into authorized incoming-spool state.

The successful-path ordering is:

```math
NValidate(x)
\prec
Publish(x,q_s)
```

where $`\prec`$ means required execution precedence.

Therefore:

```text
external package exists
≠
authorized work exists
```

Validation must occur before publication into the authorized work path.

---

## 20. Worker claim

Define:

```math
Claim(q_s)=
\begin{cases}
r,&\exists r\in Incoming(q_s)\\
\varnothing,&Incoming(q_s)=\varnothing
\end{cases}
```

When a record is successfully claimed:

```math
Q_2\rightarrow Q_3
```

When no record exists:

```math
Claim(q_s)=\varnothing
```

and the worker iteration ends without invoking the authorized-apply path.

Claiming work does not itself authorize application.

---

## 21. Terminalization

Define:

```math
FinishClaim(r,z,q_s)
```

where:

```math
z\in\{completed,rejected\}
```

Successful terminalization produces:

```math
Q_3\rightarrow Q_{6C}
```

or:

```math
Q_3\rightarrow Q_{6R}
```

depending on $`z`$.

`FinishClaim` is a partial function.

It can fail.

That failure remains part of the current model because the formal work discovered a valid counterexample to unconditional terminal totality.

---

## 22. Transition relation

Define:

```math
\delta\subseteq Q\times\Sigma\times Q
```

The principal transitions are:

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

For rejected processing:

```math
\delta(Q_3,RejectedProcessing)=Q_{6R}
```

subject to successful terminalization.

If terminalization fails:

```math
\delta(Q_3,FinishClaim\uparrow)=Q_3
```

is an allowed bounded state.

---

## 23. Formal premises

The theorem family is conditional on six premises.

### P1 — Source identity

The modeled source is the exact sealed 11-file production authorized-adoption source set at:

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

### P2 — Formal domain

The theorem domain is restricted to the sealed production authorized-adoption pathway.

It does not include arbitrary ALLIS behavior.

### P3 — Governed functions follow the sealed source

The modeled definitions of:

- target containment;
- allowlisting;
- state hashing;
- proposal application;
- rollback;
- spent reservation; and
- receipt creation

are the definitions represented by the sealed source model.

### P4 — Cryptographic verification interface

The authorization verifier is modeled according to the sealed verification implementation and its externally pinned public-key contract.

### P5 — Successful-return semantics

For a bounded function $`f`$:

```math
f(x)\downarrow
```

means the function completes successfully according to the bounded implementation.

It does not mean execution merely began.

### P6 — Meaning of `MACHINE_CHECKED`

Within this Step-12 model, `MACHINE_CHECKED` means machine-executed source-structure checks plus bounded execution evidence.

It does **not** mean the theorem was proved in Coq, Lean, Isabelle, TLA+, or another general proof-assistant or model-checking environment.

---

## 24. Principal formal results

Detailed theorem accounting belongs in `THEOREM_REGISTRY.md`.

The principal results are included here because they define the behavior of the model.

### T12D-A — Authorized-application gating theorem

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

Interpretation:

If the bounded authorized-adoption operation returns successfully, then the model requires:

- valid authorization;
- an allowed and contained target;
- prestate correspondence;
- fresh one-use authority;
- successful spent-state reservation; and
- successful receipt creation.

**Source-model status:** `PROVEN_WITHIN_SEALED_SOURCE_MODEL`  
**Validation level:** `MACHINE_CHECKED`

This theorem expresses the central architectural claim of the model:

```text
successful production change
does not stand by itself

successful production change
implies the required authorization and state predicates held
within the sealed bounded model
```

The theorem is not correspondence-verified for the positive production path because Step 12 did not execute a real positive production authorization and production DGM patch application.

### T12D-B — Invalid-authorization fail-closed theorem

```math
\boxed{
\neg V_{auth}
\Rightarrow
\neg Publish
}
```

Equivalent operational statement:

```text
InvalidExternalAuthorization
    ⇒
NoAuthorizedSpoolPublication
```

**Source status:** `PROVEN`  
**Validation level:** `CORRESPONDENCE_VERIFIED`

This is the clearest fail-closed expression of the capability-authority separation:

```text
invalid authority
does not become authorized work
```

### T12D-C — Empty-spool non-application theorem

```math
\boxed{
Incoming(q_s)=\varnothing
\Rightarrow
Claim(q_s)=\varnothing
\Rightarrow
NoAuthorizedApply
}
```

State form:

```math
Q_2=\varnothing
\Rightarrow
Q_3\text{ not reached}
\Rightarrow
Q_4\text{ not reached}
```

**Source status:** `PROVEN`  
**Validation level:** `CORRESPONDENCE_VERIFIED`

The runtime does not invent authorized work when no authorized record exists.

---

## 25. Preserved counterexample

The proposed terminal-totality property was:

```math
\boxed{
Q_3
\Rightarrow
Q_{6C}
\lor
Q_{6R}
}
```

This proposition is false for the current model.

A bounded counterexample exists when a record is in $`Q_3`$ and terminalization fails:

```math
State(r)=Q_3
```

```math
FinishClaim(r,z,q_s)\uparrow
```

which permits:

```math
State'(r)=Q_3
```

rather than forcing either terminal state.

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

The final status is:

```text
P12C-09 = MACHINE_CHECKED_DISPROVEN
```

A narrower proposition:

```math
Q_3
\land
FinishClaim\downarrow
\Rightarrow
Q_{6C}
\lor
Q_{6R}
```

is consistent with the transition structure.

Step 12 did not silently replace the disproven proposition with the narrower statement or promote it as a new sealed theorem.

That preservation is intentional.

> **Architecture rule:** Evidence can constrain a claim. A desired claim does not acquire authority merely because the architecture would be easier to describe if it were true.

---

## 26. Formal-model validation boundary

The formal model is correspondence-verified only for the deployed identity and observed boundaries established by the Step-12 evidence package.

This does not mean every possible modeled behavior has been observed in production.

In particular:

```math
LiveObs^{+}(T12D\text{-}A)=0
```

because no real positive production authorization/application was executed as part of Step 12.

The model therefore keeps these categories distinct:

```text
formal theorem
      ≠
source correspondence
      ≠
runtime correspondence
      ≠
positive runtime observation
```

The companion correspondence records document those relationships.

---

## 27. Explicit non-implications

The bounded theorem family does not imply a general production-mutation safety theorem:

```math
T_{bounded}
\not\Rightarrow
T_{prod-safe}
```

It also does not imply a whole-system safety theorem:

```math
T_{bounded}
\not\Rightarrow
T_{system}
```

Therefore:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

`SYSTEM_PROVEN=NO` is an explicit non-promotion.

It is not an unadjudicated question inside the completed Step-12 scope.

This distinction is part of the architecture's claim discipline:

```text
bounded evidence
≠
unbounded conclusion
```

---

## 28. What the formal model means

The current model does not ask a future user or reviewer to trust the intelligence because it is intelligent.

It does not assume that a good evaluation makes a candidate safe to deploy.

It does not assume that technical access makes an operation legitimate.

It does not assume that a component capable of executing a change should also control the authority required to execute it.

Instead, the architecture separates:

```text
reasoning
from
authority

evaluation
from
authorization

capability
from
permission

state
from
provenance

mutation
from
adoption

successful execution
from
evidence that the execution was authorized
```

The formal model is therefore a model of **governed autonomy**.

It allows an intelligent system to participate in proposing, evaluating, and executing bounded changes while keeping production authority as an independently represented, independently verified constraint.

That is the architectural meaning of:

> **State does not become authority merely because it exists.**

---

## 29. Final model statement

The strongest compact formal statement supported by the current model is:

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

over the sealed current-production authorized-adoption source model.

Additionally:

```math
\boxed{
\neg V_{auth}
\Rightarrow
\neg Publish
}
```

is correspondence-verified against the observed live fail-closed production boundary.

And:

```math
\boxed{
Incoming=\varnothing
\Rightarrow
Claim=\varnothing
\Rightarrow
NoAuthorizedApply
}
```

is correspondence-verified against the observed live empty-spool boundary.

The formal model satisfies the three principal bounded results under their stated premises:

```math
\mathcal{M}_{DGM}
\models
T_A\land T_B\land T_C
```

while:

```math
\mathcal{M}_{DGM}
\not\models
P12C\text{-}09
```

The result does not entail:

```math
ProductionMutationSafety
```

```math
WholeSystemSafety
```

or:

```math
SYSTEM\_PROVEN
```

The controlling logical boundary is:

```math
\boxed{
\text{Bounded authorized-adoption properties proven}
\not\Rightarrow
\text{whole-system proof}
}
```

---

## 30. Seal identity

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

No stronger theorem is implied by this seal.

---

## 31. Companion records

This formal model is intended to be read with the following support records:

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

evidence/
    governed-evolution/
        STEP12_FINAL_SEAL.md
        SOURCE_IDENTITY.md
        TRUST_ANCHOR.md
        GOVERNANCE_VIEW.md
        RESIDUALS.md
```

`FORMAL_MODEL.md` defines the bounded mathematical object and the architecture that object represents.

It does not replace the theorem registry, counterexample registry, source manifest, runtime correspondence record, trust evidence, governance evidence, or residual register.

Together, those records support a documentation model in which:

```text
a claim
must remain distinguishable from
the evidence supporting it,

and evidence
must remain distinguishable from
the authority required to act on it.
```
