<div align="center">

# ALLIS — Hilbert Projection Interfaces

### Prospective typed projection/view interfaces for governed H_* domains over a shared mathematical carrier without prematurely treating named domains as linear subspaces

<br>

![Architecture](https://img.shields.io/badge/ARCHITECTURE-TYPED_H__STAR_PROJECTIONS-7c3aed?style=for-the-badge)
![Carrier](https://img.shields.io/badge/CARRIER-H384_PROSPECTIVE-2563eb?style=for-the-badge)
![Classification](https://img.shields.io/badge/H__STAR-typed_projection_or_view-0ea5e9?style=for-the-badge)
![Subspace](https://img.shields.io/badge/LINEAR_SUBSPACE-NOT_ASSUMED-f97316?style=for-the-badge)
![JCP](https://img.shields.io/badge/JCP_ADMISSION-SEPARATE-f59e0b?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document defines a **prospective typed interface model** for named H_* objects.
>
> It does not declare that `H_geo`, `H_p`, `H_people`, `H_commons`, `H_App`, or any other named H_* object is a linear subspace.
>
> The safe current classification remains:
>
> ```text
> named H_* object
>     =
> governed typed projection / view / architectural state domain
> ```
>
> until closure and subspace properties are separately defined and proved.
>
> Preserve:
>
> ```text
> shared carrier
>     ≠
> semantic domain
>     ≠
> linear subspace
>     ≠
> JCP admission
> ```

---

# 1. Purpose

The purpose of this architecture is to give named H_* domains a **common typed contract** without forcing them into stronger mathematical categories before the evidence supports those categories.

The interface should make it possible to describe:

- what a projection means;
- where it comes from;
- what mathematical carrier it uses;
- who may produce it;
- who may consume it;
- whether it persists;
- how it is retrieved;
- what privacy class applies;
- what authority governs use;
- whether Gateway sees it;
- whether JCP admits it;
- whether conversation may use it;
- what correspondence evidence exists;
- what residuals remain.

The interface is therefore primarily a **governed semantic contract**.

It is not initially a theorem that each projection is a submodule or linear subspace.

---

# 2. Current architectural starting point

The qualified R3 state establishes:

```text
H_geo current JCP admission = NO

H_p current JCP admission = NO

H_people current JCP admission = NO
```

and:

```text
static H_geo path qualified = YES
```

The planned H384 work will formalize a common carrier such as:

```text
Fin 384 → ℝ
```

but:

```text
H384 carrier qualified
    ≠
all H_* objects are subspaces
```

The projection-interface layer belongs between those two concerns:

```text
shared mathematical carrier
    ↓
typed semantic projection/view
    ↓
projection-specific qualification
    ↓
optional future conversational/JCP admission
```

---

# 3. Why a typed interface is needed

Without a common interface, named H_* objects risk being described inconsistently.

One document may treat an H_* object as:

```text
a vector space
```

another as:

```text
a database collection
```

another as:

```text
a governed view
```

and another as:

```text
a conversational context field
```

Those are different properties.

The interface forces each named object to state which properties actually apply.

---

# 4. Core design rule

Every H_* object should be modeled as a typed record with explicit semantics.

Conceptually:

```text
HilbertProjection
    =
{
  identity,
  semantics,
  carrier,
  source,
  runtime,
  producer,
  consumer,
  privacy,
  authority,
  persistence,
  retrieval,
  gateway_relation,
  jcp_relation,
  conversational_relation,
  accuracy,
  correspondence,
  residuals
}
```

This prevents the name alone from carrying hidden assumptions.

---

# 5. Prospective carrier parameter

The interface should be generic over a carrier.

Conceptually:

```text
HilbertProjection Carrier
```

with a future common carrier:

```text
Carrier = H384
```

where:

```text
H384 := Fin 384 → ℝ
```

This lets the architecture define projection semantics before asserting that the projection is algebraically closed under H384 operations.

---

# 6. Typed-view rather than subspace default

The default type relation should be:

```text
H_x
    =
typed view over Carrier
```

not:

```text
H_x ≤ Carrier
```

in the mathematical subspace sense.

A typed view may still expose:

- vectors;
- identifiers;
- provenance;
- metadata;
- privacy class;
- authority class;
- retrieval state;
- conversational projection.

None of those require linear-subspace closure.

---

# 7. Prospective interface sketch

A language-neutral conceptual interface:

```text
HilbertProjection<Carrier>:
    canonical_name
    semantic_domain
    carrier_type
    source_contract
    runtime_contract
    producer_contract
    consumer_contract
    privacy_class
    authority_contract
    persistence_contract
    retrieval_contract
    gateway_contract
    jcp_contract
    conversational_contract
    accuracy_contract
    correspondence_contract
    residuals
```

A Lean-facing structure may later encode only the mathematically/formally relevant subset.

A runtime schema may encode operational fields separately.

Do not force one representation to carry all concerns.

---

# 8. Projection identity interface

Every H_* object should have a stable identity record.

Recommended fields:

```text
canonical_name:
aliases:
historical_names:
semantic_version:
formal_object:
source_objects:
runtime_objects:
status:
```

This is especially important where terminology has shifted or where thesis-era names do not map one-to-one to present implementation objects.

---

# 9. Semantic-domain interface

Each projection must state:

```text
semantic_domain:
description:
included_state:
excluded_state:
subject_scope:
geographic_scope:
temporal_scope:
```

Examples:

```text
H_geo
    =
geographic / spatial governed projection
```

```text
H_p
    =
separate governed civic-query projection
```

```text
H_people
    =
governed people / private-state domain
```

These semantics must remain independent of mathematical carrier terminology.

---

# 10. Carrier interface

Each projection should declare whether it actually uses H384.

Recommended state:

```text
carrier:
    kind:
    dimension:
    scalar_type:
    embedding_contract:
    normalization_contract:
    metric:
    correspondence_status:
```

Possible `kind` values:

```text
H384

OTHER_VECTOR

NONVECTOR

UNRESOLVED
```

Do not assume every H_* object is vector-valued merely because the name uses H.

---

# 11. Source interface

Each projection should bind to exact source evidence.

Recommended fields:

```text
source:
    current_files:
    functions:
    classes:
    schemas:
    fields:
    source_sha256:
    branch:
    tree:
    historical_sources:
    candidate_sources:
```

The interface must distinguish:

```text
current
historical
candidate
```

source.

---

# 12. Runtime interface

Each projection should state whether it exists at runtime.

Recommended fields:

```text
runtime:
    status:
    service:
    container:
    image:
    module:
    port:
    route:
    runtime_source_identity:
```

Possible statuses:

```text
CURRENT_ACTIVE
CURRENT_STATIC_ONLY
CURRENT_SEPARATE_PATH
CANDIDATE_NOT_LIVE
HISTORICAL_ONLY
NOT_LOCATED
UNRESOLVED
```

---

# 13. Producer interface

Each projection should identify what produces it.

Recommended fields:

```text
producer:
    component:
    source:
    input_type:
    output_type:
    embedding_model:
    normalization:
    authority:
    provenance:
```

If there are multiple producers, define multiple producer records.

---

# 14. Consumer interface

Each projection should identify all consumers.

Recommended fields:

```text
consumers:
    - component:
      purpose:
      read_mode:
      source:
      affects_response:
      affects_authority:
      affects_persistence:
```

A projection may have no current conversational consumer.

That is a valid current state.

---

# 15. Privacy interface

Every projection should declare a privacy classification.

Recommended classes:

```text
PUBLIC
PRIVATE
SECRET
MIXED_REQUIRES_PROJECTION
NOT_APPLICABLE
UNRESOLVED
```

For `H_people`, privacy classification must remain tier-aware:

```text
SECRET
PRIVATE
PUBLIC
```

A numeric vector representation does not erase the sensitivity of the underlying semantics.

---

# 16. Authority interface

The authority interface must be transition-specific.

Recommended structure:

```text
authority:
    create:
    stage:
    evaluate:
    promote:
    persist:
    retrieve:
    contextual_use:
    disclose:
    jcp_admission:
    publish:
    delete:
```

Do not compress all permissions into:

```text
authorized = true
```

Different transitions require different authority.

---

# 17. Persistence interface

Recommended fields:

```text
persistence:
    class:
    backend:
    collection:
    write_path:
    update_path:
    delete_path:
    retention:
    provenance_required:
```

Possible classes:

```text
EPHEMERAL
REQUEST_SCOPED
CACHE
STAGED
DURABLE
APPEND_ONLY
IMMUTABLE_EVIDENCE
NONE
UNRESOLVED
```

---

# 18. Retrieval interface

Recommended fields:

```text
retrieval:
    enabled:
    query_function:
    metric:
    top_k:
    filters:
    subject_scope:
    geographic_scope:
    temporal_scope:
    authority_filter:
    empty_semantics:
    unavailable_semantics:
```

The interface should distinguish:

```text
empty
```

from:

```text
unavailable
```

and from:

```text
withheld
```

---

# 19. Gateway relationship interface

Each projection should explicitly state its current Unified Gateway relationship.

Recommended enumeration:

```text
NONE_CURRENT
METADATA_ONLY
RETRIEVAL_ONLY
REASONING_INPUT
GOVERNED_TOOL_INPUT
CANDIDATE
QUALIFIED_LIVE
```

Recommended fields:

```text
gateway:
    relationship:
    field:
    route:
    function:
    source:
    content_effect:
    authority_effect:
```

No relationship should be inferred from architecture prose.

---

# 20. JCP relationship interface

Every projection should state:

```text
jcp:
    current_admission:
    field_name:
    schema_location:
    authority_owner:
    producer:
    consumer:
    correspondence:
```

Current R3 values:

```text
H_geo.current_admission = false

H_p.current_admission = false

H_people.current_admission = false
```

A projection with:

```text
current_admission = false
```

is:

```text
NONADMITTED
```

not:

```text
implicitly available
```

---

# 21. Conversational-use interface

Recommended fields:

```text
conversation:
    current_use:
    intended_use:
    minimum_necessary_view:
    model_visibility:
    recipient_scope:
    purpose:
    retention:
    fallback:
```

Possible current-use states:

```text
NONE
PRIVATE_CONTEXT
PUBLIC_CONTEXT
BACKGROUND_ONLY
SEPARATE_TOOL_PATH
JCP_CONTEXT
UNRESOLVED
```

---

# 22. Accuracy interface

Each projection requires a domain-specific accuracy contract.

Recommended fields:

```text
accuracy:
    definition:
    metrics:
    test_corpus:
    freshness:
    tolerance:
    failure_semantics:
```

Do not define one universal "Hilbert accuracy" score.

---

# 23. Correspondence interface

Each projection should expose independent correspondence states:

```text
correspondence:
    formal_to_source:
    source_to_runtime:
    runtime_observation:
    current_date:
    evidence_ids:
```

Recommended states:

```text
NOT_STARTED
PARTIAL
PASS
FAIL
UNRESOLVED
NOT_APPLICABLE
```

A formal theorem does not set runtime correspondence to PASS automatically.

---

# 24. Residual interface

Every projection should have:

```text
residuals:
```

as a first-class field.

Examples:

```text
embedding producer unresolved

normalization unresolved

runtime path historical only

JCP admission not installed

accuracy not measured

authority owner unresolved

source/runtime correspondence stale
```

This prevents a qualified bounded object from being mistaken for a fully integrated one.

---

# 25. H_geo interface

Current safe starting interface:

```yaml
H_geo:
  semantic_domain: geographic_spatial_projection

  carrier:
    kind: UNRESOLVED_OR_H384_CANDIDATE

  current_state:
    static_path_qualified: true
    live_jcp_admission: false

  lifecycle:
    - STAGE
    - EVALUATE
    - PROMOTE

  gateway:
    relationship: NONE_CURRENT_OR_STATIC_ONLY

  jcp:
    current_admission: false

  conversation:
    current_use: NONE_AS_LIVE_JCP_FIELD

  subspace:
    proved: false
```

This preserves the qualified R3 static path without overstating live integration.

---

# 26. H_p interface

Current safe starting interface:

```yaml
H_p:
  semantic_domain: governed_civic_query_projection

  carrier:
    kind: UNRESOLVED_OR_H384_CANDIDATE

  runtime:
    status: CURRENT_SEPARATE_PATH

  gateway:
    relationship: SEPARATE_PATH

  jcp:
    current_admission: false

  conversation:
    current_use: SEPARATE_TOOL_PATH_OR_UNRESOLVED

  subspace:
    proved: false
```

Do not merge H_p with H_geo.

---

# 27. H_people interface

Current safe starting interface:

```yaml
H_people:
  semantic_domain: governed_people_private_state

  privacy:
    classes:
      - SECRET
      - PRIVATE
      - PUBLIC

  jcp:
    current_admission: false

  conversation:
    ordinary_chat_secret_disclosure_authority: false

  gateway:
    relationship: NOT_CURRENT_JCP

  subspace:
    proved: false
```

H_people requires stronger privacy/authority fields than most other projections.

---

# 28. H_people SECRET tier

The SECRET tier contains protected identity correspondence, KYC/custody material, and other protected state.

The interface should expose:

```text
secret_use_authority
secret_disclosure_authority
subject_scope
recipient_scope
purpose
minimum_necessary
receipt
immutable_audit
```

Ordinary authenticated conversation does not satisfy this interface automatically.

---

# 29. H_people PRIVATE tier

The PRIVATE tier may support authorized private conversational continuity.

The interface should distinguish:

```text
private contextual use
```

from:

```text
SECRET disclosure
```

A private conversational projection may be permitted without exposing underlying SECRET source state.

---

# 30. H_people PUBLIC tier

The PUBLIC tier contains state intended for public use.

Even public state should retain:

```text
provenance
source identity
scope
freshness
```

where relevant.

Public classification does not mean provenance becomes optional.

---

# 31. Protected-location view

Future protected-location contextual use should be modeled as a derived view, not as raw SECRET KYC location.

Conceptually:

```text
H_people.SECRET.precise_location
    ↓
authorized minimum-necessary projection
    ↓
conversation-safe geographic context
```

Current status:

```text
KYC_LOCATION_CONTEXT_USE_QUALIFIED=NO
```

The interface should therefore remain prospective.

---

# 32. H_commons interface

Current safe starting interface:

```yaml
H_commons:
  semantic_domain: community_commons_governance_projection

  provenance:
    legacy_formal_material_exists: true

  current_correspondence:
    status: REQUALIFICATION_REQUIRED

  jcp:
    current_admission: false_or_unresolved

  subspace:
    proved_currently: false
```

Legacy Commons formal material must not be treated as current controlling semantics without requalification.

---

# 33. H_App interface

Current safe starting interface:

```yaml
H_App:
  semantic_domain: application_projection

  relationship_to_H_geo:
    static_correspondence_exists: true

  carrier:
    current_contract: UNRESOLVED

  jcp:
    current_admission: UNRESOLVED_OR_NO

  subspace:
    proved: false
```

The R3 H_App × H_geo static correspondence does not prove all H_App properties.

---

# 34. H_civic interface

Current safe starting interface:

```yaml
H_civic:
  semantic_domain: civic_projection_candidate

  relationship_to_H_p:
    same_object: UNPROVED

  source:
    status: REVIEW_REQUIRED

  runtime:
    status: REVIEW_REQUIRED

  subspace:
    proved: false
```

Do not collapse H_civic into H_p without explicit semantic/source correspondence.

---

# 35. H_state interface

Current safe starting interface:

```yaml
H_state:
  semantic_domain: UNRESOLVED

  overload_risk: high

  required_before_formalization:
    - define_state_scope
    - define_source
    - define_runtime
    - define_consumer

  subspace:
    proved: false
```

If H_state is overloaded, split it before theorem work.

---

# 36. H_t / H_time interfaces

Do not assume:

```text
H_t = H_time
```

without reconciliation.

Use separate provisional interfaces:

```yaml
H_t:
  semantic_domain: temporal_projection_historical_or_formal
  current_semantics: REVIEW_REQUIRED
  subspace:
    proved: false

H_time:
  semantic_domain: temporal_projection_architectural
  current_semantics: REVIEW_REQUIRED
  subspace:
    proved: false
```

A later naming reconciliation may merge or distinguish them based on evidence.

---

# 37. Projection admission lifecycle

A generic governed projection lifecycle may be modeled as:

```text
source state
    ↓
candidate projection
    ↓
semantic validation
    ↓
provenance validation
    ↓
authority validation
    ↓
qualified projection
    ↓
optional persistence
    ↓
optional retrieval
    ↓
optional conversational view
    ↓
optional JCP admission
```

Each arrow is a separate transition.

---

# 38. Qualification does not imply JCP admission

The interface must encode:

```text
qualified_projection
    ≠
jcp_admitted_projection
```

For example:

```text
H_geo.static_path_qualified = true

H_geo.jcp.current_admission = false
```

This is valid and current.

---

# 39. Qualification does not imply persistence

Likewise:

```text
projection mathematically valid
    ≠
persistence authorized
```

A projection may be:

```text
ephemeral
```

or:

```text
static-only
```

or:

```text
staged
```

without durable persistence.

---

# 40. Qualification does not imply conversational use

A projection may be valid for:

```text
offline analysis
```

while:

```text
conversation.current_use = NONE
```

This should be explicit.

---

# 41. Projection-view transformation

Where conversation should not see raw underlying state, define a view transformation:

```text
Projection
    ↓
authorized view
    ↓
conversation
```

Recommended fields:

```text
view:
    source_projection:
    transform:
    purpose:
    minimum_necessary:
    privacy_effect:
    disclosure_effect:
    retention:
```

This is especially important for H_people and protected location.

---

# 42. View transformation is not necessarily linear

A governed view may:

- redact;
- generalize;
- filter;
- aggregate;
- classify;
- summarize;
- threshold;
- select;
- map categories.

These operations need not be linear.

Therefore do not model every architectural projection as a linear operator.

---

# 43. Prospective formal structure

A future Lean representation may use a structure conceptually like:

```lean
structure GovernedProjection (Carrier : Type) where
  Name : String
  Predicate : Carrier → Prop
  -- plus only mathematically meaningful fields
```

or another more suitable representation.

However, operational fields such as:

```text
privacy
authority
runtime source identity
Gateway route
```

may belong in separate correspondence/documentation structures rather than Lean itself.

The formal design should not be overloaded with operational metadata solely for symmetry.

---

# 44. If a true subspace is later proved

A named projection may later gain a stronger formal object.

For example:

```text
H_geoSubspace : Submodule ℝ H384
```

only after the required closure properties are established.

At that point, the architecture may record:

```text
H_geo projection
    has proved linear-subspace realization
```

rather than rewriting all earlier projection terminology.

---

# 45. Subspace promotion criteria

Before promoting any named H_* object to a subspace claim, require:

```text
carrier correspondence = PASS

semantic definition = PASS

zero membership = PROVED

addition closure = PROVED

scalar closure = PROVED

theorem-level axiom review = PASS

model-to-source correspondence = PASS where implementation claim is made
```

Optional additional properties may include:

```text
closedness
orthogonality
direct-sum relation
projection operator
```

but only if needed and proved.

---

# 46. Direct-sum language boundary

Earlier thesis material may discuss direct-sum decompositions.

Do not promote those architectural/formal research descriptions into present current-state implementation claims unless:

```text
component spaces defined

subspace properties proved

intersection properties proved

sum properties proved

source semantics correspond
```

The typed-interface layer is intentionally weaker and safer.

---

# 47. Tensor language boundary

Similarly, prior tensor language such as:

```text
H_App ⊗ H_geo
```

may remain research/formal architecture.

The current R3 evidence supports a bounded static H_App × H_geo correspondence.

Do not infer a full tensor-product implementation unless separately formalized and corresponded.

---

# 48. Gateway interface example

A projection that is not currently used by Gateway:

```yaml
gateway:
  relationship: NONE_CURRENT
  field: null
  route: null
  content_effect: false
  authority_effect: false
```

A future metadata-only projection:

```yaml
gateway:
  relationship: METADATA_ONLY
  field: some_field
  content_effect: false
  authority_effect: false
```

A future reasoning-input projection:

```yaml
gateway:
  relationship: REASONING_INPUT
  field: qualified_field
  content_effect: true
  authority_effect: false
```

Authority effect must not be inferred from content effect.

---

# 49. JCP interface example

Current H_geo:

```yaml
jcp:
  current_admission: false
  state: NONADMITTED
```

Future successor candidate:

```yaml
jcp:
  current_admission: false
  successor_candidate: true
  authority_required: true
  schema_change_required: true
  correspondence_required: true
```

Only after qualification:

```yaml
jcp:
  current_admission: true
  state: QUALIFIED_LIVE
```

if that future state is actually achieved.

---

# 50. Persistence interface example

A static-only projection:

```yaml
persistence:
  class: STAGED
  durable: false
```

A durable governed projection:

```yaml
persistence:
  class: DURABLE
  provenance_required: true
  admission_authority_required: true
```

Do not infer durability merely because a vector collection exists.

---

# 51. Retrieval interface example

A governed retrieval projection:

```yaml
retrieval:
  enabled: true
  metric: L2
  subject_filter_required: false
  authority_filter_required: true
  empty_semantics: PASS_EMPTY
  unavailable_semantics: UNAVAILABLE
```

The exact values remain projection-specific.

---

# 52. Accuracy interface example

H_geo may use:

```text
spatial accuracy
temporal freshness
coordinate/source precision
geometry validity
```

H_people may use:

```text
subject correspondence
provenance
identity isolation
recipient correctness
```

H_p may use:

```text
civic-query relevance
source provenance
scope correctness
```

The interface should allow different accuracy schemas.

---

# 53. Projection status vocabulary

Recommended statuses:

```text
RESEARCH_ONLY

HISTORICAL_ONLY

FORMALLY_SPECIFIED

STATIC_QUALIFIED

CURRENT_SEPARATE_PATH

RETRIEVAL_QUALIFIED

CONVERSATIONAL_VIEW_QUALIFIED

JCP_CANDIDATE

JCP_LIVE_QUALIFIED

UNRESOLVED
```

This makes "qualified" precise.

---

# 54. Projection correspondence vocabulary

Recommended independent correspondence fields:

```text
formal_to_source
source_to_runtime
runtime_observation
```

Do not use one:

```text
correspondence = true
```

flag for all layers.

---

# 55. Projection privacy/authority vocabulary

Recommended authority booleans should be transition-specific.

For example:

```yaml
authority:
  create: false
  persist: false
  retrieve: true
  contextual_use: true
  disclose: false
  jcp_admission: false
  publish: false
```

This supports least authority.

---

# 56. Future automated research relationship

Future automated research may produce candidate state for one or more projections.

Current status remains:

```text
AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED=NO

RESEARCH_TO_CORPUS_INGESTION_QUALIFIED=NO
```

A prospective projection interface should therefore support:

```text
candidate_source
provenance
admission_status
persistence_status
```

without allowing retrieval to imply qualification.

---

# 57. Research material remains candidate state

For future research-derived content:

```text
retrieved web material
    ↓
candidate evidence
```

not:

```text
retrieved web material
    ↓
qualified H_* state automatically
```

A projection interface should expose:

```text
candidate
qualified
admitted
persistent
```

as distinct states.

---

# 58. Protected location relationship

A future minimum-necessary geographic view derived from H_people should have a dedicated projection identity.

For example:

```text
H_people precise SECRET location
    ↓
authorized geographic-context view
    ↓
ordinary conversation
```

The derived view should not inherit raw SECRET-disclosure semantics.

Nor should it expose the precise source merely because the view is conversationally useful.

---

# 59. Interface anti-circularity

An H_* object may not satisfy its own authority requirements merely because the interface says it is qualified.

Invalid:

```text
projection says it is admissible
    therefore
projection is admitted
```

Valid:

```text
external qualification evidence
    +
authority
    +
correspondence
    →
admission decision
```

---

# 60. Interface versioning

Each projection interface should be versioned.

Recommended fields:

```text
interface_version
projection_semantic_version
source_version
formal_version
runtime_version
```

A source change should not silently retain old correspondence.

---

# 61. Historical compatibility

Historical thesis names should remain traceable.

Recommended fields:

```text
historical_aliases
historical_definition
current_definition
reconciliation_note
```

This preserves chronology without treating historical architecture as current implementation.

---

# 62. Example common interface schema

```yaml
hilbert_projection:
  canonical_name:
  aliases: []

  semantics:
    description:
    included_state:
    excluded_state:

  carrier:
    kind:
    dimension:
    scalar_type:
    formal_object:

  source:
    current_files: []
    functions: []
    fields: []
    sha256: []

  runtime:
    status:
    services: []
    images: []
    containers: []

  producer:
    components: []
    contract:

  consumers: []

  privacy:
    class:

  authority:
    create:
    stage:
    evaluate:
    promote:
    persist:
    retrieve:
    contextual_use:
    disclose:
    jcp_admission:
    publish:

  persistence:
    class:
    backend:
    provenance_required:

  retrieval:
    enabled:
    metric:
    filters: []
    empty_semantics:
    unavailable_semantics:

  gateway:
    relationship:
    fields: []
    functions: []

  jcp:
    current_admission:
    current_field:
    successor_candidate:

  conversation:
    current_use:
    intended_use:
    minimum_necessary_view:
    model_visibility:

  accuracy:
    definition:
    measures: []

  correspondence:
    formal_to_source:
    source_to_runtime:
    runtime_observation:

  residuals: []

  mathematical_structure:
    linear_subspace_proved: false
```

---

# 63. Current projection summary

| Projection | Current safe classification | Current JCP admission | Subspace proved? |
|---|---|---:|---:|
| `H_geo` | governed geographic/spatial projection; static path qualified | NO | NO |
| `H_p` | separate governed civic-query projection | NO | NO |
| `H_people` | governed people/private-state domain | NO | NO |
| `H_commons` | legacy/community-governance projection requiring current requalification | not established/currently not treated as JCP | NO |
| `H_App` | application projection / research object; bounded static H_App × H_geo correspondence exists | not established as live JCP | NO |
| `H_civic` | civic projection candidate | unresolved | NO |
| `H_state` | architectural state-domain candidate | unresolved | NO |
| `H_t` | temporal/formal historical candidate | unresolved | NO |
| `H_time` | temporal architectural candidate | unresolved | NO |

---

# 64. Current formal boundaries

The projection-interface architecture must remain consistent with:

```text
LEAN_R2_CONVERSATIONAL_ADMISSION_QUALIFIED=YES

LEAN_R3_HILBERT_JCP_SEPARATION_QUALIFIED=YES

H384_FORMALIZATION_COMPLETE=NO

LIVE_HILBERT_JCP_INTEGRATION_COMPLETE=NO

SYSTEM_PROVEN=NO
```

It must not silently upgrade future architecture into current proof.

---

# 65. Successor qualification path

For any projection:

```text
interface defined
    ↓
semantic review
    ↓
source review
    ↓
runtime review
    ↓
carrier/dimensional review
    ↓
authority review
    ↓
formal theorem work
    ↓
model-to-source
    ↓
source-to-runtime
    ↓
bounded live observation
    ↓
optional conversational qualification
    ↓
optional JCP admission successor
```

No stage is implied by the one before it.

---

# 66. Final interface statement

```text
HILBERT_PROJECTION_INTERFACE=PROSPECTIVE

DEFAULT_H_STAR_CLASSIFICATION=TYPED_PROJECTION_OR_VIEW

COMMON_H384_CARRIER=PLANNED

H_GEO_LINEAR_SUBSPACE_PROVED=NO

H_P_LINEAR_SUBSPACE_PROVED=NO

H_PEOPLE_LINEAR_SUBSPACE_PROVED=NO

H_COMMONS_LINEAR_SUBSPACE_PROVED=NO

H_APP_LINEAR_SUBSPACE_PROVED=NO

H_GEO_CURRENT_JCP_ADMISSION=NO

H_P_CURRENT_JCP_ADMISSION=NO

H_PEOPLE_CURRENT_JCP_ADMISSION=NO

PROJECTION_QUALIFIED_IMPLIES_JCP_ADMISSION=NO

PROJECTION_QUALIFIED_IMPLIES_PERSISTENCE=NO

PROJECTION_QUALIFIED_IMPLIES_CONVERSATIONAL_USE=NO

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **Named H_* objects are governed semantic projections/views first, not presumed mathematical subspaces.**

> **A shared H384 carrier does not erase domain-specific semantics, privacy, authority, or provenance.**

> **Projection terminology does not imply a linear projection operator.**

> **Subspace terminology requires separate closure/submodule proof.**

> **H_geo, H_p, and H_people remain currently nonadmitted to JCP under R3.**

> **H_people requires tier-aware privacy and disclosure interfaces.**

> **H_commons and other legacy formal objects require current semantic requalification before reuse.**

> **Gateway use, JCP admission, conversational use, persistence, retrieval, and publication are separate transitions.**

> **Every projection retains independent formal/source/runtime correspondence and residuals.**

> **Future successor work may strengthen a projection's mathematical structure without rewriting the historical meaning of the current interface.**

> **SYSTEM_PROVEN remains NO.**
