<div align="center">

# ALLIS — H384 Formalization Plan

### Next mathematical target for the common 384-dimensional carrier, metric geometry, normalization, and later typed H_* projection work

<br>

![Plan](https://img.shields.io/badge/PLAN-H384_FORMALIZATION-7c3aed?style=for-the-badge)
![Carrier](https://img.shields.io/badge/CARRIER-Fin_384_%E2%86%92_%E2%84%9D-2563eb?style=for-the-badge)
![Geometry](https://img.shields.io/badge/GEOMETRY-INNER_PRODUCT_%C2%B7_NORM_%C2%B7_L2-0ea5e9?style=for-the-badge)
![Completeness](https://img.shields.io/badge/FINITE_DIMENSIONAL_COMPLETENESS-PLANNED-f59e0b?style=for-the-badge)
![Subspaces](https://img.shields.io/badge/NAMED_H__STAR_SUBSPACES-NOT_YET_PROVED-f97316?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document defines the next shared mathematical/formal target for the ALLIS Hilbert work.
>
> The immediate goal is to formalize the common 384-dimensional real-vector carrier and its standard geometry.
>
> It does **not** declare that named architectural objects such as `H_geo`, `H_p`, `H_people`, `H_commons`, `H_App`, or other `H_*` objects are linear subspaces.
>
> Preserve:
>
> ```text
> common carrier
>     ≠
> named projection
>     ≠
> proved linear subspace
> ```

---

# 1. Current status

The current formal record supports:

```text
LEAN_R3_HILBERT_JCP_SEPARATION_QUALIFIED=YES
```

and:

```text
H_GEO_CURRENT_JCP_ADMISSION=NO
H_P_CURRENT_JCP_ADMISSION=NO
H_PEOPLE_CURRENT_JCP_ADMISSION=NO
```

The next mathematical phase is not yet complete:

```text
H384_FORMALIZATION_COMPLETE=NO
```

The current safe mathematical posture is:

```text
named H_* objects
    =
governed typed projections / views / architectural state domains
```

until stronger closure/subspace properties are separately established.

---

# 2. Why H384 comes next

The current source/runtime inventory contains multiple live 384-dimensional retrieval collections.

The observed geometry provides a concrete basis for a common mathematical carrier.

The candidate shared carrier is:

```text
Fin 384 → ℝ
```

This gives a stable finite-dimensional real vector type on which the project can define:

- vector-space operations;
- standard inner product;
- induced norm;
- Euclidean/L2 distance;
- finite-dimensional completeness;
- normalization predicates;
- later typed projection interfaces.

The purpose is to formalize the **shared geometry first**, before assigning stronger algebraic structure to named semantic domains.

---

# 3. Core target

The first H384 formal object should be a type equivalent to:

```lean
Fin 384 → Real
```

Conceptually:

```text
H384 := Fin 384 → ℝ
```

This object is the proposed common carrier for 384-dimensional vector state.

The intended initial theorem family concerns the carrier itself.

It does not yet concern any named H_* domain.

---

# 4. Carrier semantics

The H384 carrier should represent exactly:

```text
384 coordinates
over the real numbers
with standard pointwise vector operations
```

The formal record should make explicit:

```text
dimension = 384
scalar field = ℝ
coordinate index = Fin 384
```

This avoids vague statements such as:

```text
"an embedding vector"
```

without an exact mathematical type.

---

# 5. Standard vector-space structure

The first mathematical layer should establish that:

```text
Fin 384 → ℝ
```

inherits the standard real-vector-space structure.

At minimum:

```text
zero vector

vector addition

additive inverse

scalar multiplication
```

with the ordinary real-vector-space laws.

The project should rely on Lean/mathlib's standard finite function/vector-space instances where appropriate rather than reimplementing elementary algebra.

---

# 6. Standard inner product

The next target is the standard Euclidean inner product.

Conceptually:

```text
⟪x, y⟫
    =
Σ i, x i * y i
```

for:

```text
x y : Fin 384 → ℝ
```

The formalization should identify the exact inner-product instance used.

The intended semantics are:

```text
standard coordinate-wise real inner product
```

not a custom learned similarity function.

---

# 7. Norm

From the standard inner product, formalize or use the induced norm:

```text
‖x‖
```

with the expected Euclidean meaning:

```text
‖x‖²
    =
Σ i, (x i)²
```

subject to the exact mathlib theorem/instance used.

The public documentation should distinguish:

```text
vector norm
```

from:

```text
application-specific score
```

and from:

```text
retrieval distance
```

even where those are mathematically related.

---

# 8. L2 metric

The common geometry should explicitly connect the norm to L2/Euclidean distance.

Conceptually:

```text
dist x y
    =
‖x - y‖
```

This is the formal object relevant to current L2-oriented vector retrieval geometry.

The formal target should establish the exact relationship between:

```text
standard metric on H384
```

and:

```text
L2 distance
```

rather than relying on terminology alone.

---

# 9. Retrieval metric caution

The mathematical fact:

```text
H384 has an L2 metric
```

does not by itself prove:

```text
every live collection is semantically comparable
```

or:

```text
every current embedding producer uses identical normalization
```

or:

```text
cross-collection distance is meaningful
```

The formal H384 geometry is a shared mathematical substrate.

Producer and collection semantics remain separate correspondence questions.

---

# 10. Finite-dimensional completeness

The next formal target should establish the completeness expected of a finite-dimensional real inner-product space.

Conceptually:

```text
H384
    =
finite-dimensional real inner-product space
    ⇒
complete metric space
```

and therefore supports the mathematical carrier-level Hilbert-space structure.

The preferred proof route should use standard library results for finite-dimensional real normed spaces where possible.

Do not introduce unnecessary axioms or custom completeness assumptions.

---

# 11. Hilbert-carrier claim

Once the required standard instances and completeness facts are established, the safe mathematical claim may become:

```text
H384 is a finite-dimensional real Hilbert carrier
```

That claim applies to:

```text
Fin 384 → ℝ
```

It does **not** automatically apply to every named H_* architecture object.

Preserve:

```text
H384 is Hilbert
    ≠
H_geo is proved Hilbert subspace
```

and likewise for every other named H_* object.

---

# 12. Normalization predicate

The next core formal object should be an explicit normalization predicate.

A candidate definition is:

```text
Normalized(x)
    ↔
‖x‖ = 1
```

or the exact numerically/formally appropriate equivalent chosen during implementation.

The project must make the predicate explicit rather than relying on prose such as:

```text
"normalized embedding"
```

without a formal condition.

---

# 13. Zero-vector edge case

Normalization must address:

```text
x = 0
```

explicitly.

The project should not define a normalization operation that silently divides by zero.

A candidate formal split is:

```text
x = 0
```

versus:

```text
x ≠ 0
```

For nonzero vectors:

```text
normalize(x)
    =
(1 / ‖x‖) • x
```

or the exact library equivalent.

Then prove the appropriate normalized result.

---

# 14. Candidate normalization theorem family

The normalization phase should consider bounded theorems such as:

```text
norm_nonnegative
```

```text
normalized_implies_norm_one
```

```text
normalize_nonzero_has_norm_one
```

```text
normalize_zero_behavior_explicit
```

```text
normalize_idempotent_on_normalized_vectors
```

where those claims match the chosen definitions.

Do not invent stronger numerical guarantees than the formal representation supports.

---

# 15. Exact-vs-floating-point boundary

The Lean carrier:

```text
Fin 384 → Real
```

is exact mathematical state.

Runtime embeddings are finite-precision numeric data.

Therefore preserve:

```text
Lean Real model
    ≠
runtime floating-point semantics
```

The H384 formalization should eventually include a correspondence note explaining what runtime numeric representation corresponds to the real-vector model.

That correspondence belongs outside the pure carrier theorem.

---

# 16. Embedding producer contract remains separate

The H384 formal carrier does not prove an embedding producer contract.

For each producer, later work must establish:

```text
model identity

model version

output dimension

preprocessing

normalization

numeric representation

determinism / nondeterminism where relevant
```

The common carrier theorem only says what a 384-dimensional mathematical vector is.

---

# 17. Dimension equality is not semantic equality

Preserve:

```text
384 dimensions
    ≠
same embedding semantics
```

Two producers may both return:

```text
ℝ^384
```

while encoding incompatible semantic spaces.

Therefore H384 should not be used to justify cross-producer combination unless producer correspondence is separately established.

---

# 18. H_* projection interface comes after H384

Once H384 is qualified, define typed interfaces for named H_* objects.

A safe first design is something like:

```text
Projection H_x over H384
```

or another typed view that preserves domain semantics.

The interface should be capable of expressing:

```text
source domain
privacy class
authority class
producer
consumer
persistence
retrieval
conversational admissibility
JCP admissibility
```

without requiring the object to be a linear subspace.

---

# 19. Do not call H_* objects subspaces yet

The current formal record does not support:

```text
H_geo is a linear subspace of H384

H_p is a linear subspace of H384

H_people is a linear subspace of H384

H_commons is a linear subspace of H384
```

unless those properties are separately proved.

The repository should therefore avoid phrases such as:

```text
the H_people subspace
```

as a formal mathematical claim unless a theorem registry establishes it.

Use:

```text
H_people projection
```

or:

```text
H_people governed state domain
```

instead.

---

# 20. What must be proved before "linear subspace"

For a named set/domain `H_x` to be called a linear subspace of H384, establish at minimum:

```text
0 ∈ H_x
```

```text
x ∈ H_x
y ∈ H_x
    ⇒
x + y ∈ H_x
```

```text
x ∈ H_x
a ∈ ℝ
    ⇒
a • x ∈ H_x
```

or use the exact Lean `Submodule` structure that carries these obligations.

Without those properties:

```text
H_x
```

may still be a valid:

- projection;
- subset;
- typed view;
- manifold-like restricted domain;
- retrieval corpus;
- governed state family;
- semantic label.

It is simply not yet a proved linear subspace.

---

# 21. "Projection" does not imply linear projection

The word:

```text
projection
```

is used architecturally in ALLIS to mean a governed view/state mapping.

That does not automatically mean:

```text
linear idempotent operator
```

in the strict functional-analysis sense.

The formalization should distinguish:

```text
architectural projection
```

from:

```text
linear projection operator
```

unless linearity and idempotence are separately proved.

---

# 22. Candidate H384 definition layer

A public Lean module may eventually contain a carrier definition equivalent to:

```lean
abbrev H384 := Fin 384 → ℝ
```

or the exact preferred mathlib-compatible spelling.

The module should then expose or derive:

```text
AddCommGroup H384
Module ℝ H384
InnerProductSpace ℝ H384
NormedAddCommGroup H384
MetricSpace H384
CompleteSpace H384
FiniteDimensional ℝ H384
```

using standard instances where available.

The exact implementation should be chosen from Lean/mathlib rather than inferred from this plan.

---

# 23. Candidate H384 theorem groups

The workstream should organize theorem work into bounded groups.

## Group A — carrier identity

```text
dimension = 384

scalar field = ℝ
```

## Group B — inner-product geometry

```text
standard inner product

norm correspondence
```

## Group C — L2 metric

```text
dist x y = ‖x - y‖
```

plus any exact theorem needed to connect implementation terminology to the mathematical metric.

## Group D — completeness

```text
finite-dimensional completeness
```

## Group E — normalization

```text
explicit Normalized predicate

nonzero normalization behavior
```

No H_* subspace theorem belongs in the initial carrier group.

---

# 24. Candidate file layout

Recommended formal-verification layout:

```text
formal-verification/h384/
    README.md
    H384.lean
    Geometry.lean
    Normalization.lean
    theorem-registry.md
    model-to-source.md
    source-to-runtime.md
    residuals.md
    workstream-closeout.md
```

If the project prefers to keep the H384 work under the existing Hilbert formalization tree, the exact location may differ.

The important separation is:

```text
carrier mathematics
```

from:

```text
named projection semantics
```

---

# 25. Initial theorem registry should stay small

Do not begin by formalizing every architectural H_* object.

First qualify a minimal H384 theorem set.

A suitable initial target is:

```text
H384-C1
carrier is Fin 384 → ℝ

H384-C2
standard real inner product is available

H384-C3
induced norm is the standard Euclidean norm

H384-C4
metric is induced L2 / Euclidean distance

H384-C5
carrier is finite-dimensional

H384-C6
carrier is complete

H384-C7
explicit Normalized predicate is defined

H384-C8
normalization of nonzero vectors satisfies Normalized
```

Exact theorem names should be chosen after the Lean source is written.

This plan intentionally does not fabricate Lean declarations.

---

# 26. Axiom discipline

Use the same qualification discipline established in R1–R3.

Require:

```text
clean build
```

```text
sorry = 0
```

```text
admit = 0
```

```text
principal #print axioms reviewed
```

```text
unexpected theorem-level axioms = qualification failure
```

Do not treat successful compilation alone as sufficient.

The R2/R3 `propext` history is the precedent.

---

# 27. Mathematical source correspondence

After the pure H384 carrier theorem family is qualified, create:

```text
model-to-source.md
```

to answer:

- which runtime collections are dimension 384?
- which producers emit 384-D vectors?
- which current paths use L2?
- which branches normalize embeddings?
- which collections share producer identity?
- which historical collections have unresolved producer provenance?

The formal theorem should not be used as evidence for these implementation claims.

---

# 28. Source/runtime correspondence

The H384 work must then distinguish:

```text
source says 384
```

from:

```text
runtime actually uses 384
```

For each relevant current runtime collection/service record:

```text
collection
producer
runtime dimension
metric
normalization
source identity
runtime identity
```

The earlier observed count of 27 live dimension-384 collections is a useful starting inventory.

It is not the final H384 correspondence proof.

---

# 29. Normalization correspondence

A particularly important follow-on is to determine which current runtime producers actually satisfy the chosen normalization predicate.

Possible outcomes:

```text
PRODUCER_A_NORMALIZED=YES

PRODUCER_B_NORMALIZED=NO

PRODUCER_C_NORMALIZATION_UNRESOLVED
```

Do not make a global theorem-to-runtime claim until producer branches are reconciled.

---

# 30. L2 and cosine relationship

If later documentation discusses cosine similarity and normalized L2 geometry, the project should prove the exact mathematical relation it intends to use rather than relying on folklore.

For normalized vectors, useful relations may exist between:

```text
dot product

cosine similarity

squared L2 distance
```

But these should become a separate theorem family only if they are needed by the actual source/runtime contract.

Do not include them merely because they are mathematically familiar.

---

# 31. Current R3 boundary remains controlling during H384 work

While H384 is being formalized:

```text
H_geo current JCP admission = NO

H_p current JCP admission = NO

H_people current JCP admission = NO
```

remain unchanged.

A stronger mathematical description of the carrier does not modify the current JCP.

Preserve:

```text
better mathematics
    ≠
new runtime admission
```

---

# 32. H384 does not create authority

Even if H384 is fully machine-checked:

```text
H384 theorem qualified
```

does not imply:

```text
may persist vectors
```

or:

```text
may promote vectors
```

or:

```text
may admit H_geo to JCP
```

or:

```text
may disclose H_people
```

or:

```text
may publish state
```

Formal geometry is not authority.

---

# 33. H384 does not establish accuracy

Mathematical correctness of the carrier does not prove that an embedding is semantically accurate.

Preserve:

```text
vector has valid dimension
    ≠
vector faithfully represents source semantics
```

and:

```text
L2 distance mathematically defined
    ≠
nearest neighbor semantically correct
```

Accuracy remains projection- and producer-specific.

---

# 34. H384 does not establish provenance

A mathematically valid vector may have insufficient provenance.

Therefore:

```text
H384-valid vector
    ≠
qualified persistent state
```

Persistence/admission still requires:

```text
source identity

producer identity

schema

time

scope

authority

provenance
```

where applicable.

---

# 35. H384 and automated learning

Future automated research/learning may eventually create candidate vectors.

Current status remains:

```text
AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED=NO

RESEARCH_TO_CORPUS_INGESTION_QUALIFIED=NO
```

The H384 formalization does not change that.

Preserve:

```text
vectorizable
    ≠
admissible
```

and:

```text
embedding generated
    ≠
qualified corpus state
```

---

# 36. H384 and H_people

The shared carrier does not weaken privacy boundaries.

If H_people uses 384-dimensional vector state:

```text
numeric representation
    ≠
non-sensitive state
```

The privacy/SECRET classification depends on semantics and provenance, not the fact that the information is represented as a vector.

---

# 37. H384 and protected location

Likewise:

```text
location-derived embedding
```

does not become public or ordinary conversational state merely because it is encoded as:

```text
ℝ^384
```

The KYC/protected-location authority boundary remains separate.

Current status:

```text
KYC_LOCATION_CONTEXT_USE_QUALIFIED=NO
```

---

# 38. H384 and H_geo

For H_geo, later work should distinguish:

```text
raw geographic geometry

derived embedding

static H_geo value state

conversational projection

JCP-admitted projection
```

These are potentially different objects.

Do not identify all of them with H384 automatically.

---

# 39. H384 and H_p

For H_p, later work must determine whether the current civic-query projection:

- actually uses the same H384 carrier;
- uses the same embedding producer;
- uses normalized embeddings;
- uses L2;
- has an independent retrieval geometry.

Until then:

```text
H_p uses Hilbert-related architecture
    ≠
H_p formally corresponds to H384
```

---

# 40. H384 and H_commons

Legacy Commons formal material must be requalified against the current H384 semantics before reuse.

Preserve:

```text
legacy theorem
    ≠
current H384 correspondence
```

Even a mathematically valid older proof may model a different carrier, abstraction, or governance meaning.

---

# 41. H384 and H_t / H_time

Temporal Hilbert names should not be attached to H384 merely because 384-D vectors are available.

First establish:

```text
H_t semantics

H_time semantics

current source identity

vector representation if any
```

Then determine whether H384 is relevant.

---

# 42. Formal proof order

Recommended order:

```text
1. exact carrier type

2. vector-space instances

3. standard inner product

4. induced norm

5. induced metric / L2 relation

6. finite-dimensional property

7. completeness

8. normalization predicate

9. normalization operation / theorems

10. model-to-source correspondence

11. source-to-runtime correspondence

12. typed projection interfaces

13. projection-specific theorem families
```

Do not start with projection-specific subspace claims.

---

# 43. Evidence package

Recommended evidence package:

```text
00-scope.md

01-toolchain.txt

02-source-manifest.txt

03-build.txt

04-proof-hole-scan.txt

05-print-axioms.txt

06-principal-theorem-results.json

07-carrier-correspondence.md

08-runtime-dimension-inventory.json

09-normalization-inventory.json

10-residuals.md

11-final.txt

SHA256SUMS
```

The exact filenames may change.

The qualification layers should remain separate.

---

# 44. Required residuals

The H384 closeout should explicitly report unresolved items such as:

```text
producer normalization unresolved

historical collection producer unknown

cross-collection semantic compatibility unproved

floating-point correspondence unproved

projection-specific subspace closure unproved

JCP admission not addressed

conversational use not addressed
```

A carrier-level workstream can close successfully with these residuals.

---

# 45. Success criteria

The initial H384 workstream may close when it can truthfully state:

```text
H384_CARRIER_FORMALIZED=YES

H384_INNER_PRODUCT_FORMALIZED=YES

H384_NORM_FORMALIZED=YES

H384_L2_METRIC_FORMALIZED=YES

H384_FINITE_DIMENSIONAL=YES

H384_COMPLETE=YES

H384_NORMALIZATION_PREDICATE_DEFINED=YES

PRINCIPAL_PROOF_HOLES=0

UNEXPECTED_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0
```

without requiring:

```text
ALL_H_STAR_SUBSPACES_PROVED=YES
```

---

# 46. Explicit non-success criteria

Do not block the carrier workstream merely because:

```text
H_geo subspace theorem not done

H_p subspace theorem not done

H_people subspace theorem not done

JCP admission not done

automated learning not done

cognition theorem family not done
```

Those are successor domains.

The point of H384 is to establish the common mathematical substrate.

---

# 47. Naming rule

Recommended terminology after H384 qualification:

Use:

```text
H384 carrier
```

for the shared mathematical space.

Use:

```text
H_geo projection
H_p projection
H_people projection
```

for named governed domains unless stronger structure has been separately proved.

Use:

```text
H_geo subspace
```

only after a corresponding closure/submodule theorem exists.

---

# 48. Theorem-registration rule

Every future statement that promotes a named H_* object to a mathematical subspace should receive:

```text
theorem identifier

exact statement

proof result

#print axioms result

model-to-source correspondence

claim limits
```

Do not promote the terminology in prose before the theorem registry exists.

---

# 49. Candidate normalized plan

```yaml
h384_formalization_plan:
  status: PLANNED
  complete: false

  carrier:
    type: "Fin 384 -> Real"
    scalar_field: Real
    dimension: 384

  target_structure:
    vector_space: true
    standard_inner_product: planned
    induced_norm: planned
    l2_metric: planned
    finite_dimensional: planned
    complete_space: planned
    hilbert_carrier: planned

  normalization:
    explicit_predicate: planned
    candidate_meaning: "norm x = 1"
    zero_vector_behavior_must_be_explicit: true
    nonzero_normalization_theorem: planned

  formal_discipline:
    proof_holes_allowed: false
    unexpected_theorem_level_axioms_allowed: false
    clean_build_required: true
    print_axioms_review_required: true

  implementation_correspondence:
    observed_live_dimension_384_collections: 27
    producer_identity_review_required: true
    normalization_review_required: true
    metric_review_required: true
    cross_collection_semantic_compatibility_proved: false

  named_H_objects:
    automatically_subspaces: false
    default_classification: governed_typed_projection_or_view
    subspace_claim_requires:
      - zero_membership
      - addition_closure
      - scalar_closure
      - theorem_registration
      - correspondence

  current_jcp:
    H_geo_admitted: false
    H_p_admitted: false
    H_people_admitted: false

  successor_work:
    - typed_projection_interfaces
    - H_geo_specific_formalization
    - H_p_specific_formalization
    - H_people_specific_formalization
    - remaining_H_star_reviews

  system_proven: false
```

---

# 50. Final plan statement

```text
NEXT_MATHEMATICAL_TARGET=H384

H384_CARRIER=Fin_384_TO_Real

STANDARD_INNER_PRODUCT_TARGET=YES

INDUCED_NORM_TARGET=YES

L2_METRIC_TARGET=YES

FINITE_DIMENSIONAL_COMPLETENESS_TARGET=YES

NORMALIZATION_PREDICATE_TARGET=YES

H384_FORMALIZATION_COMPLETE=NO

NAMED_H_STAR_OBJECTS_AUTOMATICALLY_LINEAR_SUBSPACES=NO

SUBSPACE_TERMINOLOGY_REQUIRES_CLOSURE_PROOF=YES

H_GEO_CURRENT_JCP_ADMISSION=NO

H_P_CURRENT_JCP_ADMISSION=NO

H_PEOPLE_CURRENT_JCP_ADMISSION=NO

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **Formalize the shared 384-dimensional carrier before making stronger claims about named projections.**

> **Use `Fin 384 → ℝ` as the candidate common mathematical carrier.**

> **Establish the standard inner product, norm, L2 metric, and finite-dimensional completeness explicitly.**

> **Define normalization as a formal predicate rather than an informal assumption.**

> **Treat zero-vector normalization as an explicit edge case.**

> **A common carrier does not prove common semantics.**

> **A 384-dimensional vector is not automatically a qualified persistent state.**

> **Named H_* objects remain governed typed projections/views until closure and subspace properties are separately proved.**

> **Do not call an H_* object a linear subspace merely because it lives over H384.**

> **Better mathematics does not create JCP admission or governance authority.**

> **SYSTEM_PROVEN remains NO.**
