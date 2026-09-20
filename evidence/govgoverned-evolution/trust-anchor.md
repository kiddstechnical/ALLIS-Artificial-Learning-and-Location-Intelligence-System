# Trust anchor: governed production adoption

## Purpose

This document records the public verification trust anchor used by the bounded ALLIS production authorized-adoption pathway.

The trust anchor exists so the NBB and worker can answer a narrow question:

> **Was this authorization signed by the private authority corresponding to the pinned production public key?**

The trust anchor does not answer:

> **Should this candidate be adopted?**

It also does not answer:

> **May the runtime perform this mutation now?**

Those are separate governed questions.

The governing architecture is:

> **Verification capability does not create authorization authority.**

And the broader ALLIS principle remains:

> **State does not become authority merely because it exists.**

Applied to the trust anchor:

```text
public key exists
≠
authorization exists

signature verifies
≠
full authorization is valid

full authorization is valid
≠
target mutation is permitted

runtime can verify
≠
runtime can sign

trust anchor matches
≠
private authority is present
```

---

## Trust-anchor status

| Field | Value |
|---|---|
| Document role | Public verification trust-anchor evidence record |
| Formal object | `DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1` |
| Production source commit | `20c8cbe175781c8a1c05d65c03977859ceca884a` |
| Trust-anchor type | Pinned production public verification key |
| Sealed public-key SHA-256 | `4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5` |
| NBB trust correspondence | `PASS` at final seal |
| Worker trust correspondence | `PASS` at final seal |
| Formal trust predicate | `C_K=1` at final seal |
| Private signing key in modeled verifier | `NO` |
| Authorization issuance in NBB/worker runtime model | `EXTERNAL_TO_RUNTIME_MODEL` |
| Final Step-12 status | `GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS` |

---

## 1. What a trust anchor is in this architecture

The trust anchor is the public verification key whose exact identity is pinned by SHA-256.

Let:

```math
K_S
```

denote the sealed production public trust anchor.

Let:

```math
K_N
```

denote the NBB runtime copy.

Let:

```math
K_W
```

denote the worker runtime copy.

The sealed public-key SHA-256 is:

```text
4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5
```

The Step-12 trust-correspondence check established that the runtime copies corresponded to that sealed trust anchor at the final seal boundary.

Formally:

```math
\boxed{
C_K=1
}
```

at final seal time.

The public key is therefore an identity-bound verification object.

It is not an authorization object.

---

## 2. Verification role

The formal signature predicate is:

```math
V_{sig}(a,K_{pub})\in\{0,1\}
```

with:

```math
V_{sig}(a,K_{pub})=1
```

if and only if the detached authorization signature verifies against the canonical authorization message under the pinned production public key.

Conceptually:

```math
Verify(
K_{pub},
HashMessage(Payload(a)),
sig(a)
)
```

must succeed.

The public trust anchor therefore supports one bounded function:

```text
verify a detached authorization signature
against the expected production public authority identity
```

It does not perform the authorization decision itself.

---

## 3. Source implementation boundary

The production public-verification implementation is represented by:

```text
services/hilbert/dgm_public_key_authorization_verifier.py
```

The committed-source inspection identified the verifier interface around:

```text
public_key
canonical_payload_bytes
authorization_message_hash
verify_detached_authorization
signature
```

This module belongs to the bounded authorized-adoption verification surface.

The formal model treats this runtime component as a verifier.

It does not treat it as a signer.

---

## 4. The public key is not the private authority

The formal record explicitly states:

```text
The production verifier is modeled only as a verifier.
No private signing key is included in this runtime function.
```

That creates a deliberate authority separation:

```text
public verification material
        ↓
can verify an authorization signature

private signing authority
        ↓
can create a valid signature
```

These are not the same capability.

Possessing the first does not imply possession of the second.

---

## 5. Trust anchor and authorization envelope

The trust anchor verifies the signature associated with an authorization envelope.

The authorization envelope includes bounded fields such as:

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

The signature is therefore attached to a structured authorization object whose payload includes identities and constraints.

However, successful signature verification remains only one part of authorization validation.

---

## 6. Signature verification is one predicate

The composite authorization predicate is:

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

Therefore:

```math
V_{sig}=1
```

does not imply:

```math
V_{auth}=1
```

by itself.

A valid signature can coexist with another invalid authorization condition.

The entire composite predicate must succeed.

---

## 7. What a valid signature establishes

A successful `V_sig` result establishes the bounded cryptographic statement:

```text
the detached signature verifies
against the canonical authorization message
under the pinned public key
```

Within the defined source contract, that provides evidence that the authorization message is attributable to the private key corresponding to the pinned public verifier.

It does not establish that every other field is valid.

---

## 8. What a valid signature does not establish

A valid signature does not independently establish:

```text
authorization ID syntax is valid
```

It does not independently establish:

```text
decision = APPROVE
```

It does not independently establish:

```text
authority class is permitted
```

It does not independently establish:

```text
authorization is within its valid time window
```

It does not independently establish:

```text
proposal ID matches the candidate
```

It does not independently establish:

```text
target matches the authorized target
```

It does not independently establish:

```text
prestate matches the authorized prestate
```

It does not independently establish:

```text
candidate hash matches
```

It does not independently establish:

```text
evaluation hash matches
```

It does not independently establish:

```text
evaluation requirements passed
```

All of those remain separate predicates.

---

## 9. Trust does not override target governance

Even when:

```math
V_{sig}=1
```

and even when:

```math
V_{auth}=1
```

the bounded application path still requires target safety:

```math
V_{target}
=
V_{contain}
\land
V_{allow}
```

Therefore:

```text
authorization signature valid
≠
arbitrary filesystem mutation permitted
```

The target must remain inside the governed root and must be permitted by the governed target policy.

---

## 10. Trust does not override prestate correspondence

The bounded application path also requires:

```math
V_{pre}=1
```

where the current source state must still match the expected authorized prestate.

Therefore:

```text
valid signed authorization
for source state A
≠
authority to mutate changed source state B
```

A signed authorization does not float free of the state it authorized.

---

## 11. Trust does not override one-use authority

The bounded path also requires:

```math
V_{once}=1
```

and successful spent-state reservation:

```math
S_{spent}=1
```

Therefore:

```text
signature was valid once
≠
authorization may be replayed indefinitely
```

The trust anchor verifies signature identity.

It does not nullify the one-use authorization model.

---

## 12. Trust does not guarantee application success

Even complete authorization validation does not guarantee that the governed application succeeds.

The bounded path is:

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

A successful signature is upstream of several additional conditions.

Therefore:

```text
signature verifies
≠
mutation succeeds
```

---

## 13. Trust does not create a receipt

A successful production transition requires durable receipt correspondence.

The receipt records evidence about the actual transition.

The public trust anchor does not create that receipt.

Thus:

```text
valid signature
≠
evidence that the mutation actually occurred
```

and:

```text
valid authorization
≠
evidence of successful application
```

---

## 14. Runtime trust correspondence

At the Step-12 final seal, the NBB and worker runtime copies corresponded to the sealed public trust anchor.

Let:

```math
K_N
```

be the live NBB copy and:

```math
K_W
```

the live worker copy.

The final trust-correspondence result is:

```math
\boxed{
C_K=1
}
```

at the final seal boundary.

In operational terms:

```text
NBB public trust     PASS
Worker public trust  PASS
```

This result establishes that the expected public verification identity was present in both runtime roles at that point in time.

---

## 15. Point-in-time boundary

The trust correspondence result is part of the Step-12 sealed runtime state.

It is not a perpetual assertion.

Conceptually:

```math
C_K^{\tau_{seal}}=1
```

does not automatically imply:

```math
\forall\tau>\tau_{seal},
C_K^{\tau}=1
```

without future revalidation.

A later trust-anchor replacement, deployment change, source change, or runtime change requires a new correspondence determination.

---

## 16. Trust anchor versus source correspondence

These are separate questions:

```text
Does runtime source match sealed source?
```

and:

```text
Does runtime trust material match the sealed public trust anchor?
```

Step 12 checked both.

The 11/11 source correspondence does not make the trust-anchor check redundant.

Likewise, trust-anchor correspondence does not prove that the runtime source matches the source model.

The evidence layers remain distinct.

---

## 17. Trust anchor versus governance view

The trust anchor and governance view also serve different purposes.

The public trust anchor answers:

```text
Does this detached signature verify
under the expected public verification identity?
```

The governance view answers a different class of questions about the applicable governed decision state.

Therefore:

```text
cryptographic trust
≠
governance decision
```

Both can be required without becoming interchangeable.

---

## 18. Trust anchor versus authority class

The formal authorization model accepts only permitted authority classes.

Let:

```math
\mathcal{K}
=
\{
BBB\_GUARDIAN,
CONSTITUTIONAL\_GUARDIAN
\}
```

within the current bounded model.

Then:

```math
V_{class}(a)=1
```

only if the authorization's authority class is permitted.

A cryptographically valid signature does not independently satisfy `V_class`.

The public key proves signature correspondence.

The authorization model separately evaluates whether the claimed authority class is acceptable.

---

## 19. Trust anchor versus approval decision

A valid signature also does not turn any signed decision into approval.

The approval predicate remains:

```math
V_{decision}(a)=
\begin{cases}
1,&d(a)=APPROVE\\
0,&otherwise
\end{cases}
```

Therefore:

```text
signed
≠
approved
```

A correctly signed denial remains a denial.

A cryptographic verifier is not permitted to reinterpret the decision merely because the signature is valid.

---

## 20. Trust anchor versus time

The authorization-time predicate remains independent:

```math
\tau_i(a)\le\tau\le\tau_e(a)
```

with:

```math
\tau_e(a)>\tau_i(a)
```

required.

Therefore:

```text
signature remains mathematically verifiable
≠
authorization remains temporally valid
```

Expiration is a governance condition, not a cryptographic failure.

---

## 21. Trust anchor versus candidate identity

The authorization must bind to the candidate being considered.

A valid signature alone does not establish:

```math
h_c(a)=H_c(c)
```

or, where required:

```math
h_{env}(a)=H_{env}(c)
```

Therefore:

```text
authorization was signed
≠
authorization applies to this candidate
```

The candidate identity must independently correspond.

---

## 22. Trust anchor versus evaluation identity

Likewise, a valid signature does not independently establish:

```math
h_e(a)=H_e(c)
```

or that the evaluation body satisfies the bounded source, compile, and benchmark requirements.

Therefore:

```text
authorization signed
≠
evaluation valid
```

and:

```text
evaluation valid
≠
authorization signed
```

These are separate evidence domains that are joined only by the complete authorization predicate.

---

## 23. External authority boundary

Step 12 preserves the following residual:

```text
R12F-08 — External authority
```

with the controlling meaning:

```text
authorization issuance remains external to runtime model
```

The NBB and worker:

```text
verify external authorization
```

and:

```text
consume external authorization
```

They do not, within this bounded model:

```text
mint private authorization authority
```

or:

```text
sign their own production authorizations
```

This is not an omitted convenience function.

It is an authority boundary.

---

## 24. Why external issuance matters

If the same bounded runtime that wants to perform a mutation could independently manufacture the authority required to approve that mutation, the separation between capability and authority would collapse.

The current model instead preserves:

```text
candidate/evaluation system
        ↓
can produce evidence

external authorization authority
        ↓
can authorize a bounded transition

runtime verifier
        ↓
can verify the supplied authority

runtime application path
        ↓
can act only if all required conditions succeed
```

That separation is the architectural purpose of the public trust anchor.

---

## 25. What the public key authorizes

Strictly speaking:

> **The public key itself authorizes nothing.**

It enables verification of a signature.

Authority is represented by a valid authorization envelope whose required predicates succeed under the governed model.

This distinction should remain explicit in public documentation.

The correct statement is:

```text
the trust anchor verifies an authorization signature
```

not:

```text
the trust anchor authorizes the mutation
```

---

## 26. What possession of the public key does not authorize

Possession of the public verification key does not authorize a holder or runtime to:

```text
sign an authorization
approve a candidate
choose an authority class
extend an expiration time
change an authorization payload
change a target
change a prestate
change a candidate
change an evaluation
replay a spent authorization
bypass the target allowlist
bypass filesystem containment
bypass poststate verification
create a successful receipt without a successful transition
publish unauthorized work
apply an unauthorized production mutation
```

The key is public because verification is not the privileged operation.

Signing remains the privileged operation.

---

## 27. What trust correspondence does not authorize

The final Step-12 status:

```text
PUBLIC_TRUST=PASS
```

does not itself authorize:

```text
production authorization publication
```

It does not authorize:

```text
production authorization consumption
```

It does not authorize:

```text
production DGM patch application
```

At Step-12 close, those actions remained:

```text
REAL_PRODUCTION_AUTHORIZATION_PUBLICATION=NOT_PERFORMED
REAL_PRODUCTION_AUTHORIZATION_CONSUMPTION=NOT_PERFORMED
REAL_PRODUCTION_DGM_PATCH_APPLICATION=NOT_PERFORMED
```

Trust correspondence established identity.

It did not create successor authority.

---

## 28. What the trust anchor does not prove

The trust-anchor evidence does not prove:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=YES
```

It does not prove:

```text
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=YES
```

It does not prove:

```text
SYSTEM_PROVEN=YES
```

The controlling results remain:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

The trust anchor is one bounded component of the authorization architecture.

---

## 29. Failure semantics

If the detached authorization signature cannot be verified under the pinned production public key, then:

```math
V_{sig}=0
```

and therefore the composite authorization predicate cannot satisfy:

```math
V_{auth}=1
```

because:

```math
V_{sig}
```

is a required conjunct.

Thus the verification architecture is fail-closed with respect to the modeled signature requirement:

```text
signature verification fails
        ↓
authorization validation fails
        ↓
successful authorized path is unavailable
```

The verifier does not substitute trust from an unpinned key.

---

## 30. Replacement semantics

A future public-key replacement is a change in the trust anchor.

A new trust anchor does not inherit the current hash identity merely because it is intended as a successor.

If:

```math
K'_S\neq K_S
```

then the current trust-correspondence result does not automatically establish:

```math
C_K(K'_S)=1
```

A replacement requires a new evidence and correspondence boundary.

This mirrors the broader ALLIS rule:

```text
successor state
≠
authorized continuation of predecessor state
```

without evidence of the transition.

---

## 31. Public repository handling

This record intentionally publishes the trust-anchor **hash identity**, not private signing material.

The authoritative public identity is:

```text
SHA-256
4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5
```

A reviewer can use that identity to understand which public verification object the Step-12 trust-correspondence result refers to.

Private signing keys, secret material, or operational signing credentials do not belong in this public evidence document.

---

## 32. Relationship to the formal model

`FORMAL_MODEL.md` defines:

```math
V_{sig}(a,K_{pub})
```

and the composite:

```math
V_{auth}
```

This document provides the evidence identity for the $`K_{pub}`$ trust object.

Therefore:

```text
FORMAL_MODEL.md
        ↓
defines the verification predicate

TRUST_ANCHOR.md
        ↓
identifies the public trust object

SOURCE_TO_RUNTIME.md
        ↓
records that runtime copies matched that object at final seal
```

These roles should remain separate.

---

## 33. Relationship to source-to-runtime correspondence

At final Step-12 sealing:

```text
NBB source correspondence     11/11 PASS
Worker source correspondence  11/11 PASS
Public trust                  PASS
```

The source and trust results support different correspondence claims.

Together they establish that the inspected runtime contained both:

```text
the expected governed source
```

and:

```text
the expected public verification trust identity
```

at the sealed runtime boundary.

---

## 34. Relationship to the final seal

The final Step-12 seal includes trust correspondence as part of the evidence-backed runtime state.

The controlling seal is:

```text
STEP12_FINAL_THEOREM_AND_FORMAL_CORRESPONDENCE_SEALED_GREEN_WITH_EXPLICIT_RESIDUALS
```

with final result SHA-256:

```text
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

and scope:

```text
BOUNDED_PRODUCTION_AUTHORIZED_ADOPTION_FORMAL_MODEL_AND_ESTABLISHED_CORRESPONDENCE_ONLY
```

The trust anchor does not enlarge that scope.

---

## 35. Final trust statement

Let:

```math
K_S
```

be the sealed production public trust anchor with:

```text
SHA-256
4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5
```

Let:

```math
K_N
```

be the NBB runtime copy and:

```math
K_W
```

the worker runtime copy.

At the Step-12 final seal:

```math
\boxed{
C_K=1
}
```

for the bounded inspected runtime state.

This establishes that the expected public verification trust identity was present.

It does not establish that the runtime possessed private signing authority.

It does not authorize a candidate.

It does not authorize a target.

It does not waive prestate, evaluation, replay, application, poststate, or receipt conditions.

It does not authorize a production mutation.

---

## 36. Governing trust statement

The correct architectural reading is:

> **The public trust anchor tells the runtime whose signature it is willing to verify. It does not tell the runtime what it is allowed to do.**

That distinction is the trust-layer expression of the overarching ALLIS architecture:

> **Capability does not create authority.**
