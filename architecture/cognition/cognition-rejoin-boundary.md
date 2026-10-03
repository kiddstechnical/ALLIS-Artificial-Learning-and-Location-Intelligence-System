<div align="center">

# ALLIS — Cognition Rejoin Boundary

### Current composition path to be formalized by the next cognition Lean family

<br>

![Boundary](https://img.shields.io/badge/BOUNDARY-COGNITION_REJOIN-7c3aed?style=for-the-badge)
![Composition](https://img.shields.io/badge/COMPOSITION-PREFRONTAL_%2B_ICONTAINERS_%2B_PSYCHOLOGY-2563eb?style=for-the-badge)
![Lifecycle](https://img.shields.io/badge/COGNITION-STAGE_%E2%86%92_EVALUATE_%E2%86%92_EMIT-0ea5e9?style=for-the-badge)
![Packet](https://img.shields.io/badge/OUTPUT-LLM__PACKET-14b8a6?style=for-the-badge)
![Formal](https://img.shields.io/badge/LEAN_FAMILY-NOT_YET_COMPLETE-f59e0b?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document records the **actual cognition composition and rejoin boundary** that the next Lean theorem family should formalize.
>
> The target is not a new cognition architecture.
>
> The target is the already-established composition pattern:
>
> ```text
> prefrontal result
>     +
> iContainers result
>     +
> psychology result
>     ↓
> cognition stage
>     ↓
> cognition evaluate
>     ↓
> cognition emit
>     ↓
> llm_packet
>     ↓
> Gateway / JCP
>     ↓
> ensemble
>     ↓
> synthesizer
> ```
>
> The current work is therefore **wiring/correspondence formalization**, not invention of a parallel component or sandbox.

---

# 1. Boundary status

```text
COGNITION_REJOIN_BOUNDARY=DOCUMENTED

COGNITION_THEOREM_FAMILY_COMPLETE=NO

ARCHITECTURE_CONSTRAINT=WIRING_REWIRING_ONLY

NEW_COMPONENT_BUILD_REQUIRED=NO

NEW_SANDBOX_RUNTIME_REQUIRED=NO

SYSTEM_PROVEN=NO
```

The current evidence supports the composition topology.

It does not yet support a completed Lean theorem family over the whole cognition rejoin.

---

# 2. Current composition path

The intended current path is:

```text
prefrontal result
    +
iContainers result
    +
psychology result
    ↓
cognition stage
    ↓
cognition evaluate
    ↓
cognition emit
    ↓
llm_packet
    ↓
Gateway / JCP
    ↓
ensemble
    ↓
LM Synthesizer
    ↓
response
```

In compact form:

```text
prefrontal_result
+ icontainers_result
+ psychology_result
-> cognition stage/evaluate/emit
-> llm_packet
-> Gateway/JCP
-> ensemble
-> synthesizer
```

This is the next cognition theorem-family target.

---

# 3. Current producer-side source names

The current front-door source already computes the three input families under current variable names:

```text
prefrontalinfo
icontainersinfo
psychinfo
```

with producer calls:

```text
prefrontalinfo = await call_nbb_prefrontal(...)

icontainersinfo = await call_icontainers(...)

psychinfo = await call_psychology_assessment(...)
```

The historical cognition helper consumed normalized result objects corresponding to:

```text
prefrontal_result
icontainers_result
psychology_result
```

The source reconciliation therefore identified a mapping:

```text
call_nbb_prefrontal(...)
    ↓
prefrontalinfo
    ↓
prefrontal_result
```

```text
call_icontainers(...)
    ↓
icontainersinfo
    ↓
icontainers_result
```

```text
call_psychology_assessment(...)
    ↓
psychinfo
    ↓
psychology_result
```

---

# 4. Discovery match is not semantic proof

The name/value mapping above is an important source clue.

It is not, by itself, complete semantic correspondence.

Preserve:

```text
DISCOVERY_MATCH_IS_NOT_SEMANTIC_PROOF=YES

SEMANTIC_EQUIVALENCE_ESTABLISHED_BY_NAME_ALONE=NO
```

The next formal/correspondence work must establish that the current values supplied from:

```text
prefrontalinfo
icontainersinfo
psychinfo
```

actually satisfy the semantics expected by the cognition-stage model.

---

# 5. Historical cognition helper

The earlier cognition integration path used a helper equivalent to:

```text
build_and_emit_cognition_packet(...)
```

with inputs including:

```text
prefrontal_result

icontainers_result

psychology_result
```

together with additional request/context fields.

That helper then executed:

```text
/cognition/stage
    ↓
/cognition/evaluate
    ↓
/cognition/emit
```

and returned:

```text
emitted["llm_packet"]
```

This establishes a concrete historical dataflow lineage for the present rejoin work.

---

# 6. Cognition request structure

The historical cognition stage contract used a nine-field request shape:

```text
request_context

intent_assessment

cognitive_stages

retrieval_evidence

spatial_temporal_context

routing_decisions

risk_and_policy

identity_mode

metadata
```

The three cognition-stage source families were represented inside the cognitive-stage composition as:

```text
prefrontal

i_containers

psychology_assessment
```

The next theorem family should formalize the semantics of those stage contributions rather than merely the field names.

---

# 7. Producer composition boundary

The cognition rejoin starts only after the three producer families have produced their results.

Conceptually:

```text
call_nbb_prefrontal
    ↓
prefrontal result
```

```text
call_icontainers
    ↓
iContainers result
```

```text
call_psychology_assessment
    ↓
psychology result
```

Then:

```text
(prefrontal, iContainers, psychology)
    ↓
cognition composition
```

The theorem family should preserve that the three inputs are distinct contributors.

Do not collapse them into a single undifferentiated blob.

---

# 8. Prefrontal contribution

The prefrontal source contribution originates from:

```text
call_nbb_prefrontal(...)
```

and current source variable:

```text
prefrontalinfo
```

The normalized cognition-facing semantic label is:

```text
prefrontal_result
```

The next formal work should determine:

- exact result shape;
- exact fields admitted into cognition;
- which fields are summaries versus raw payload;
- failure semantics;
- whether confidence/status affects cognition;
- whether any authority semantics are present;
- whether any values reach JCP or only cognition summaries.

Do not infer those properties solely from the name `prefrontal`.

---

# 9. iContainers contribution

The iContainers source contribution originates from:

```text
call_icontainers(...)
```

and current source variable:

```text
icontainersinfo
```

The normalized cognition-facing semantic label is:

```text
icontainers_result
```

The current source also derives values such as:

```text
icstatus

icstate
```

and identity-layer-related material from `icontainersinfo`.

That means the iContainers input family is semantically richer than one scalar result.

The next formal family must define which portion is admitted into cognition and which remains outside the cognition packet.

---

# 10. Psychology contribution

The psychology source contribution originates from:

```text
call_psychology_assessment(...)
```

and current source variable:

```text
psychinfo
```

The normalized cognition-facing semantic label is:

```text
psychology_result
```

The next formal work should define:

- exact admitted fields;
- summary semantics;
- failure behavior;
- whether raw assessment state is withheld;
- relationship to later reasoning context.

Again:

```text
name match
    ≠
semantic proof
```

---

# 11. Cognition lifecycle

The qualified/historical cognition lifecycle is:

```text
stage
    ↓
evaluate
    ↓
emit
```

This lifecycle should remain explicit in the next Lean family.

Do not collapse it into one function called:

```text
cognition
```

without preserving the internal state transitions.

The theorem family should be able to distinguish:

```text
staged
```

from:

```text
evaluated
```

from:

```text
emitted
```

because those are different states.

---

# 12. Stage boundary

The stage phase takes the cognition request and constructs the staged cognition representation.

The next formal model should answer:

```text
What inputs are admitted to stage?

What stage names are allowed?

What source values are summarized?

What metadata is carried?

What source fields are excluded?

What happens when one producer is unavailable?
```

The stage theorem family should be bounded to exact source semantics.

---

# 13. Evaluate boundary

The evaluate phase operates on the staged cognition representation.

The next formal model should answer:

```text
What constitutes a valid staged packet?

What evaluation state is produced?

What failures block emit?

What failures degrade rather than block?

What status/confidence semantics are retained?

What authority effect does evaluation have?
```

Evaluation is reasoning state.

It is not governance authority.

---

# 14. Emit boundary

The emit phase produces the structured output:

```text
llm_packet
```

The next formal family should establish:

```text
valid evaluated cognition
    →
bounded emitted llm_packet
```

and should separately define failure behavior.

The emitted packet must not be treated as unrestricted authority.

---

# 15. `llm_packet` is the cognition rejoin object

The key rejoin object is:

```text
llm_packet
```

The current architectural intent is:

```text
cognition stage/evaluate/emit
    ↓
llm_packet
    ↓
existing Gateway/JCP reasoning path
```

The cognition effort is therefore not about inventing a second final-response system.

It is about rejoining cognition into the already-qualified reasoning/synthesis path.

---

# 16. Historical nonconsumption correction

Historically, cognition could produce an output packet without that packet being consumed by the downstream reasoning path.

Therefore preserve:

```text
cognition packet produced
    ≠
cognition packet consumed downstream
```

The present rejoin work exists precisely because:

```text
producer path existed
```

and:

```text
downstream 20LLM/synthesis path existed
```

but the exact current bridge had to be re-established and qualified.

---

# 17. Wiring-only classification

The engineering classification for this work is:

```text
WIRING_REWIRING_ONLY
```

That means:

```text
NEW_COMPONENT_BUILD_REQUIRED=NO

NEW_SANDBOX_RUNTIME_REQUIRED=NO
```

The intended repair is:

```text
existing producers
    ↓
existing cognition lifecycle
    ↓
existing llm_packet
    ↓
existing Gateway/JCP
    ↓
existing ensemble
    ↓
existing synthesizer
```

not a parallel stack.

---

# 18. Gateway/JCP rejoin

The cognition output rejoin occurs at the existing Gateway/JCP boundary.

The target conceptual flow is:

```text
llm_packet
    ↓
Gateway
    ↓
JCP / request-context composition
```

Earlier source analysis identified the current JCP builder:

```text
build_judge_context_v2
```

The exact cognition-to-JCP adapter remains a correspondence object that must be formally specified rather than inferred.

---

# 19. Current JCP constraint

The current JCP remains the R3-qualified four-field object:

```text
schema_version
request_context
approved_evidence
wv_deliberative_context
```

Therefore cognition rejoin must not silently add new top-level fields without a successor JCP qualification.

Any cognition contribution must either:

- project into an existing qualified field;
- or be introduced through a separately qualified successor schema.

---

# 20. Known cognition-to-JCP projection concept

Prior qualification work identified a bounded projection concept in which cognition stage summaries contribute to existing reasoning context rather than creating a new unrestricted packet namespace.

The relevant design idea is:

```text
cognitive stage summaries
    ↓
existing JCP reasoning/request context
```

with only bounded summary content admitted.

The next Lean family should formalize the projection semantics explicitly.

---

# 21. Summary-only boundary

The cognition rejoin should preserve the distinction between:

```text
stage summary
```

and:

```text
raw stage payload
```

Earlier qualification work identified a bounded projection pattern that used stage name + summary while excluding broader raw state.

The next formal model should explicitly decide which of the following are admitted:

```text
stage name

summary

status

confidence

raw payload

routing metadata
```

No field should be assumed admitted merely because it exists in the source result.

---

# 22. Ensemble boundary

After Gateway/JCP composition, the current ordinary reasoning path proceeds into the ensemble service.

The current ensemble service name is:

```text
llm20production
```

Preserve:

```text
llm20production
    =
service naming convention
```

not:

```text
formal theorem that runtime cardinality = 20
```

The ensemble stage remains downstream of the cognition/JCP composition boundary.

---

# 23. Existing 20LLM reasoning path

The current reasoning stack already contains the 20LLM-style sequence:

```text
build_prompt
    ↓
process_all
    ↓
synthesize
```

or equivalent current functions in the qualified source.

The cognition rejoin should feed the already-existing reasoning context rather than replacing that path.

---

# 24. External LM Synthesizer boundary

After ensemble reasoning, the Gateway path reaches the external LM Synthesizer.

The end-to-end intended cognition rejoin is therefore:

```text
producer results
    ↓
cognition
    ↓
llm_packet
    ↓
Gateway/JCP
    ↓
ensemble
    ↓
LM Synthesizer
    ↓
response
```

The synthesizer remains the final response-composition stage.

---

# 25. Current production support

Later Gateway production qualification established a real `/chat` path through:

```text
BBB
    ↓
llm20production
    ↓
LM Synthesizer
```

This supports the downstream rejoin side.

It does not, by itself, prove the full cognition input/rejoin theorem family.

---

# 26. Cognition is not authority

The cognition path may:

```text
stage

evaluate

emit

summarize

contribute reasoning context
```

It does not thereby gain authority to:

```text
adopt

persist protected state

publish

disclose H_people SECRET

alter JCP schema

authorize its own admission
```

Preserve:

```text
cognitive result
    ≠
governance authority
```

---

# 27. Cognition output is not DGM adoption

The `llm_packet` is a conversational reasoning object.

It is not:

```text
DGM authorized-adoption package
```

unless a separate governed path explicitly creates such an object.

Preserve:

```text
llm_packet
    ≠
authorized adoption package
```

---

# 28. Cognition output is not governed publication

Likewise:

```text
llm_packet
    ≠
public publication object
```

and:

```text
synthesized response
    ≠
governed publication
```

unless a separate publication transition occurs.

---

# 29. Cognition does not automatically admit H_* state

The cognition path must remain consistent with R3.

Current JCP admission remains:

```text
H_geo = NO

H_p = NO

H_people = NO
```

Therefore cognition may not treat those domains as live JCP context merely because source material or projection objects exist elsewhere.

---

# 30. Prefrontal/iContainers/psychology do not automatically become JCP fields

The next formal family should distinguish:

```text
producer result participates in cognition
```

from:

```text
producer result becomes JCP field
```

The likely rejoin pattern is a bounded cognition projection into existing reasoning context.

That must be proved explicitly.

---

# 31. Identity boundary

Current conversational identity is governed by the R2 server-derived identity boundary.

The cognition path must not reinterpret:

```text
authenticated_user
```

as model content or authority merely because cognition has access to request context.

Preserve:

```text
authenticated identity metadata
    ≠
cognition authority
```

and:

```text
authenticated identity metadata
    ≠
automatic stage payload
```

---

# 32. H_people boundary

Cognition must preserve the R2/H_people rule:

```text
ordinary authenticated chat
    ≠
H_people SECRET disclosure authority
```

If future cognition uses a derived H_people PRIVATE projection, that use requires its own minimum-necessary and authority qualification.

Raw SECRET identity correspondence must not be inferred into the cognition packet.

---

# 33. Spatial/H_geo boundary

Cognition may receive spatial-temporal context fields in the historical request structure.

That does not establish:

```text
H_geo live JCP admission
```

The next theorem family must distinguish:

```text
spatial_temporal_context
```

from:

```text
qualified H_geo JCP projection
```

Those are not automatically the same object.

---

# 34. Retrieval-evidence boundary

The cognition stage request historically included:

```text
retrieval_evidence
```

This does not mean every retrieval source is automatically qualified cognition state.

The formal family should require that admitted retrieval evidence already satisfies the relevant provenance/admission contract.

---

# 35. Routing-decisions boundary

The cognition request historically included:

```text
routing_decisions
```

The next theorem family must distinguish:

```text
routing description
```

from:

```text
routing authority
```

A recorded route decision is not automatically permission to cross a protected boundary.

---

# 36. Risk-and-policy boundary

The cognition request historically included:

```text
risk_and_policy
```

The next formal family should define whether this is:

- advisory state;
- evaluated policy context;
- hard admission state;
- metadata.

Do not infer governance authority from the field name.

---

# 37. Identity-mode boundary

The cognition request historically included:

```text
identity_mode
```

The next theorem family should define its semantics exactly.

It must not be allowed to override the R2 source of trusted authenticated identity.

Preserve:

```text
identity_mode
    ≠
identity authority
```

unless a separate theorem establishes a more specific relation.

---

# 38. Metadata boundary

The historical stage request also included:

```text
metadata
```

The formal model should treat metadata as typed data with explicit semantics, not as an unrestricted escape hatch.

Do not permit:

```text
arbitrary metadata
    →
implicit authority
```

or:

```text
arbitrary metadata
    →
unbounded model context
```

---

# 39. Failure semantics

The next theorem family should explicitly define cognition behavior when any producer fails.

Candidate states to formalize may include:

```text
producer unavailable

producer empty

producer degraded

stage failure

evaluation failure

emit failure
```

The exact allowed fallback behavior should come from qualified source semantics.

Do not assume:

```text
missing producer
    =
successful complete cognition
```

---

# 40. Fail-open vs fail-closed must be theorem-specific

Earlier cognition/source work included fail-open behavior in some bounded composition cases.

That behavior should not be generalized.

The next formal family must specify:

```text
which missing inputs may degrade

which failures must block

which failures may emit partial summaries

which failures must prevent llm_packet emission
```

Do not use one universal fail-open rule.

---

# 41. Stage-state formal target

A useful formal decomposition is:

```text
CognitionInput
    ↓
StagedCognition
    ↓
EvaluatedCognition
    ↓
EmittedCognition
```

with:

```text
EmittedCognition.llm_packet
```

as the bounded rejoin object.

This gives Lean explicit state transitions to reason about.

---

# 42. Producer-result formal types

The next Lean family should define separate types for:

```text
PrefrontalResult

IContainersResult

PsychologyResult
```

or equivalent typed structures.

Do not model all three as untyped JSON if the theorem family needs semantic guarantees.

---

# 43. Stage-summary formal type

If only stage name + summary is admitted into JCP/reasoning context, define that explicitly.

For example, conceptually:

```text
CognitiveStageSummary:
    stage_name
    summary
```

Then prove that excluded raw fields do not enter the projected context.

---

# 44. Candidate theorem family

The next Lean family may include bounded results such as:

```text
COG-A
prefrontal contribution is typed and preserved through stage

COG-B
iContainers contribution is typed and preserved through stage

COG-C
psychology contribution is typed and preserved through stage

COG-D
stage preserves allowed stage summaries

COG-E
evaluate consumes only valid staged cognition

COG-F
emit produces a bounded llm_packet from valid evaluated cognition

COG-G
raw excluded stage payload does not enter projected JCP context

COG-H
cognition does not create governance authority

COG-I
cognition llm_packet rejoin preserves current JCP admission boundary

COG-J
cognition output is consumed by the existing ensemble/synthesis path
```

These are candidate theorem areas.

Exact theorem names should be chosen only after the formal model is written.

---

# 45. Model/source correspondence targets

The cognition formal family should crosswalk to exact source elements including:

```text
call_nbb_prefrontal

prefrontalinfo

call_icontainers

icontainersinfo

call_psychology_assessment

psychinfo

build_and_emit_cognition_packet

/cognition/stage

/cognition/evaluate

/cognition/emit

llm_packet

build_judge_context_v2

Gateway /chat path

ensemble call

LM Synthesizer call
```

Where current function names differ from historical names, preserve the distinction.

---

# 46. Source/runtime correspondence targets

After model-to-source is established, qualify:

```text
cognition source identity

cognition runtime service

cognition port / route

Gateway source identity

Gateway runtime identity

ensemble service identity

synthesizer service identity
```

The historical cognition service port was:

```text
8012
```

where applicable to the recovered architecture.

Do not treat the historical port alone as current runtime authority.

---

# 47. MainBrain separation

MainBrain remains a separate component/runtime concern.

The cognition rejoin document does not equate:

```text
MainBrain
```

with:

```text
cognition service
```

or with:

```text
Gateway
```

Preserve component boundaries.

---

# 48. Current front-door relationship

The ordinary current front door is:

```text
authenticated browser/session
    ↓
/api/chat
    ↓
Unified Gateway
```

The cognition rejoin lives downstream of conversational admission.

It should not alter the R2 identity source.

---

# 49. Current JCP relationship

The current JCP remains governed by R3.

Any cognition projection into JCP must preserve:

```text
current field set
```

unless a successor JCP schema is separately qualified.

Therefore the next cognition formal family should first target:

```text
projection into existing qualified context
```

rather than silently expanding the schema.

---

# 50. Ensemble relationship

The current ensemble path remains an existing consumer boundary.

The cognition formal model should define whether:

```text
llm_packet
```

becomes:

- prompt context;
- JCP request context;
- approved evidence;
- a separate adapter input;
- another bounded existing field.

Do not infer which one from architecture prose alone.

The exact source adapter must control the claim.

---

# 51. Synthesizer relationship

The cognition rejoin must terminate in the existing synthesis path.

The next theorem family should establish, at minimum:

```text
valid cognition rejoin
    does not bypass
existing ensemble/synthesizer flow
```

if that is what the source implements.

It should not create an independent final-answer path.

---

# 52. Rejoin anti-duplication rule

The architecture must avoid:

```text
old cognition path
    +
new parallel cognition path
```

unless a deliberate successor architecture explicitly requires both.

The current classification is:

```text
restore / qualify one rejoin
```

not:

```text
add second reasoning stack
```

---

# 53. Rejoin anti-authority rule

No cognition stage may self-promote:

```text
stage result
    →
authority
```

No evaluate result may self-promote:

```text
evaluation result
    →
authority
```

No emitted packet may self-promote:

```text
llm_packet
    →
authority
```

Authority remains external to cognition.

---

# 54. Rejoin anti-persistence rule

The cognition theorem family should not silently treat emitted reasoning state as durable knowledge.

Preserve:

```text
llm_packet emitted
    ≠
persistent corpus state
```

and:

```text
response synthesized
    ≠
research-to-corpus ingestion
```

---

# 55. Research/learning boundary

Future automated-learning/web-research work remains separate.

Current status:

```text
AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED=NO

RESEARCH_TO_CORPUS_INGESTION_QUALIFIED=NO
```

Cognition composition does not change those flags.

---

# 56. H384 boundary

Cognition may eventually consume typed H_* projections over H384.

Current status remains:

```text
H384_FORMALIZATION_COMPLETE=NO
```

Therefore the cognition theorem family should not assume all H_* domains are already mathematically qualified subspaces.

---

# 57. Cognition maturity status

Current safe status:

```text
COGNITION_SOURCE_TOPOLOGY=ESTABLISHED

COGNITION_REJOIN_ARCHITECTURE=ESTABLISHED

COGNITION_FORMAL_THEOREM_FAMILY=NOT_COMPLETE

COGNITION_FULL_RUNTIME_CORRESPONDENCE=NOT_CLAIMED_BY_THIS_DOCUMENT
```

This document is an architecture/formalization boundary.

It is not the cognition closeout.

---

# 58. Revalidation triggers

Re-evaluate this boundary if any claim-bearing changes occur to:

```text
call_nbb_prefrontal

call_icontainers

call_psychology_assessment

producer result schemas

cognition stage request schema

/cognition/stage

/cognition/evaluate

/cognition/emit

llm_packet schema

Gateway/JCP adapter

build_judge_context_v2

ensemble input

LM Synthesizer input
```

A source change may invalidate correspondence without invalidating the abstract theorem.

---

# 59. Normalized architecture record

```yaml
cognition_rejoin_boundary:
  status: CURRENT_ARCHITECTURE_TARGET

  formalization:
    lean_family_complete: false

  producers:
    prefrontal:
      call: call_nbb_prefrontal
      current_value: prefrontalinfo
      normalized_semantic: prefrontal_result

    icontainers:
      call: call_icontainers
      current_value: icontainersinfo
      normalized_semantic: icontainers_result

    psychology:
      call: call_psychology_assessment
      current_value: psychinfo
      normalized_semantic: psychology_result

  cognition:
    lifecycle:
      - stage
      - evaluate
      - emit

    historical_routes:
      - /cognition/stage
      - /cognition/evaluate
      - /cognition/emit

    output:
      field: llm_packet

  rejoin:
    destination:
      - Unified_Gateway
      - JCP
      - ensemble
      - LM_Synthesizer

  current_jcp:
    builder: build_judge_context_v2
    successor_schema_change_implied: false

  authority:
    cognition_creates_governance_authority: false
    cognition_creates_adoption_authority: false
    cognition_creates_publication_authority: false
    cognition_authorizes_hpeople_secret_disclosure: false

  persistence:
    emitted_llm_packet_is_persistent_knowledge: false

  architecture:
    wiring_rewiring_only: true
    new_component_required: false
    new_sandbox_runtime_required: false

  boundaries:
    discovery_match_is_semantic_proof: false
    historical_packet_produced_equals_downstream_consumed: false
    cognition_result_equals_jcp_field: false
    system_proven: false
```

---

# 60. Final boundary statement

```text
COGNITION_REJOIN_BOUNDARY=CURRENT

PATH:
prefrontal_result
+ icontainers_result
+ psychology_result
-> cognition_stage
-> cognition_evaluate
-> cognition_emit
-> llm_packet
-> Unified_Gateway
-> JCP
-> ensemble
-> LM_Synthesizer
-> response

CURRENT_PRODUCER_NAMES:
prefrontalinfo
icontainersinfo
psychinfo

HISTORICAL_NORMALIZED_RESULT_NAMES:
prefrontal_result
icontainers_result
psychology_result

COGNITION_LIFECYCLE=STAGE_EVALUATE_EMIT

COGNITION_OUTPUT=llm_packet

ARCHITECTURE_CONSTRAINT=WIRING_REWIRING_ONLY

NEW_COMPONENT_BUILD_REQUIRED=NO

NEW_SANDBOX_RUNTIME_REQUIRED=NO

COGNITION_CREATES_GOVERNANCE_AUTHORITY=NO

COGNITION_OUTPUT_EQUALS_DGM_ADOPTION=NO

COGNITION_OUTPUT_EQUALS_GOVERNED_PUBLICATION=NO

COGNITION_THEOREM_FAMILY_COMPLETE=NO

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **The next cognition work formalizes an existing composition path; it does not invent a parallel reasoning architecture.**

> **Prefrontal, iContainers, and psychology remain distinct typed contributors.**

> **Name correspondence is not semantic proof.**

> **Cognition preserves explicit stage → evaluate → emit states.**

> **`llm_packet` is the cognition rejoin object, not governance authority.**

> **Historical packet production does not prove historical downstream consumption.**

> **The rejoin must target the existing Gateway/JCP → ensemble → synthesizer path.**

> **Current R2 identity and R3 JCP boundaries remain controlling.**

> **Cognition does not self-authorize persistence, disclosure, publication, adoption, or JCP expansion.**

> **SYSTEM_PROVEN remains NO.**
