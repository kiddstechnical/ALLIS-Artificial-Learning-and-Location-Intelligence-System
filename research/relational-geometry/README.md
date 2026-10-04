<div align="center">

# ALLIS — Referential Geometry Experimental Plan

### Prospective design for testing whether warranted referential inference depends on preservation of task-relevant relational bindings

<br>

![Research](https://img.shields.io/badge/RESEARCH-PROSPECTIVE-7c3aed?style=for-the-badge)
![Protocol](https://img.shields.io/badge/PROTOCOL-PLAN_ONLY-2563eb?style=for-the-badge)
![Geometry](https://img.shields.io/badge/GEOMETRY-REFERENTIAL-0ea5e9?style=for-the-badge)
![Dataset](https://img.shields.io/badge/DATASET-NOT_YET_FROZEN-f59e0b?style=for-the-badge)
![Execution](https://img.shields.io/badge/EXECUTION-NOT_AUTHORIZED-ef4444?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document is an **experimental plan**.
>
> It defines how a referential-geometry experiment should be designed before a final dataset, executable protocol, or result exists.
>
> It does not authorize execution.
>
> It does not establish an experimental effect.
>
> It does not convert the broader relational-geometry research hypothesis into a current ALLIS system claim.

Preserve:

```text
research question
    ≠
experimental plan
    ≠
frozen protocol
    ≠
execution
    ≠
result
    ≠
validated claim
```

---

# 1. Relationship to the parent research program

This plan implements one bounded experimental family proposed in:

- [`../README.md`](../README.md)

The parent research program asks:

$$
\boxed{\text{Does reliable intelligence require preservation of task-relevant relational distinctions?}}
$$

This plan narrows that question to **referential geometry**.

The specific experimental question is:

$$
\boxed{\text{Does warranted referential inference depend on preservation of task-relevant relational bindings?}}
$$

More operationally:

> If the informational objects available to ALLIS remain substantially the same, but the relations connecting those objects are changed, does the corresponding warranted inference change in a predictable and relation-specific way?

This plan tests one component of the broader theory.

It does not attempt to test consciousness, subjective experience, non-computability, or physical spacetime geometry.

---

# 2. Plan status

```text
DOCUMENT_CLASS=PROSPECTIVE_EXPERIMENTAL_PLAN

REFERENTIAL_GEOMETRY_HYPOTHESIS=NOT_ESTABLISHED

DATA_DOMAIN_CANDIDATES=IDENTIFIED

DATASET_SELECTED=NO

DATASET_SOURCE_VERIFIED=NO

DATASET_ADMITTED=NO

DATASET_FROZEN=NO

TRANSFORMATION_SET_FROZEN=NO

SCORING_PLAN_FROZEN=NO

EXECUTABLE_PROTOCOL_FROZEN=NO

EXECUTION_AUTHORIZED=NO

RESULTS_AVAILABLE=NO

SYSTEM_PROVEN=NO
```

The governing rule is:

> **This document specifies what must be established before the experiment can legitimately run.**

---

# 3. Research objective

The purpose of the experiment is to distinguish:

```text
information availability
```

from:

```text
relational organization
```

The preferred design therefore does **not** compare:

$$
\text{more information}
\quad\text{versus}\quad
\text{less information}.
$$

Instead, it attempts to preserve the informational objects while selectively altering the relationships among them.

Let the valid referential representation be:

$$
G=(V,E,\tau),
$$

where:

- $V$ = informational objects;
- $E$ = relations among those objects;
- $\tau$ = types assigned to nodes and edges.

Construct an experimental representation:

$$
G'=(V,E',\tau),
$$

such that:

$$
V_G=V_{G'}
$$

while:

$$
E_G\neq E_{G'}.
$$

Where feasible, node identity, lexical content, quantity, relation count, relation type, and approximate prompt budget should remain unchanged.

The experimental variable is the **referential binding structure**.

---

# 4. Referential geometry

For this experiment, referential geometry concerns the relations that determine **what a claim is about**.

Candidate relation types include:

```text
ENTITY ──located_at──────► PLACE

ENTITY ──within──────────► REGION

ENTITY ──associated_with─► FEATURE

OBSERVATION ──about──────► ENTITY

OBSERVATION ──observed_at► TIME

RECORD ──sourced_from────► SOURCE

RECORD ──source_epoch────► SOURCE_TIME

CLAIM ──supported_by─────► EVIDENCE

FEATURE ──connected_to───► FEATURE
```

The exact relation set will depend on the admitted dataset.

Not every candidate relation must appear in the first experiment.

---

# 5. Central hypothesis

The primary hypothesis is:

$$
H_1:
\quad
\text{task-relevant relational perturbation produces selective degradation in warranted referential performance.}
$$

In plain language:

> **When a task depends on a specific referential relation, altering that relation while preserving the underlying informational objects will selectively reduce or change warranted task performance.**

A stronger comparative prediction is:

$$
\Delta_{\mathrm{relevant}}
>
\Delta_{\mathrm{irrelevant}},
$$

where $\Delta$ represents degradation relative to the correctly related control condition.

The experiment therefore predicts not merely performance loss, but **relation-specific performance loss**.

---

# 6. Null and competing explanations

## 6.1 Null hypothesis

The null hypothesis is:

$$
H_0:
\quad
\Delta_{\mathrm{relevant}}
\approx
\Delta_{\mathrm{irrelevant}}.
$$

Operationally:

> Altering a task-relevant referential relation produces no reliable degradation beyond task-irrelevant perturbation or ordinary response variability.

---

## 6.2 Information-content explanation

A possible competing explanation is:

> Performance changes because the experimental representation contains less usable information, not because referential geometry changed.

The experiment should therefore preserve the same underlying nodes and values wherever technically possible.

---

## 6.3 Lexical-cue explanation

A model may infer the intended relation from names, co-occurrence patterns, or world knowledge despite altered bindings.

The experiment must distinguish:

```text
relation supported by supplied evidence
```

from:

```text
relation reconstructed from parametric or external knowledge
```

These are not equivalent.

---

## 6.4 Generic disruption explanation

If every perturbation degrades every task equally, the result may indicate generic representation disruption rather than relation-specific dependence.

The design therefore requires **task-irrelevant perturbation controls**.

---

# 7. Experimental units

An experimental unit should contain enough independently verifiable structure to support at least one controlled referential manipulation.

A candidate normalized record may take the form:

$$
r_i=
(e_i,t_i,p_i,c_i,q_i,s_i,v_i,a_i),
$$

where, depending on the domain:

- $e_i$ = entity;
- $t_i$ = entity or record type;
- $p_i$ = place;
- $c_i$ = coordinate or geometry;
- $q_i$ = temporal state;
- $s_i$ = source;
- $v_i$ = source version or epoch;
- $a_i$ = associated physical or semantic feature.

Not every dataset must contain every field.

The executable protocol must state exactly which fields are required.

---

# 8. Dataset-selection requirements

The first experimental dataset should satisfy the following requirements.

## 8.1 Referential multiplicity

Records should contain multiple independently meaningful relations.

Preferred:

```text
entity
    ├── located_at → place
    ├── coordinate → geometry
    ├── associated_with → feature
    ├── source → source authority
    └── source_epoch → time
```

Less preferred:

```text
entity
    └── located_at → coordinate
```

Multiple relations permit stronger tests of selective degradation.

---

## 8.2 Independent verifiability

The ground-truth relation must be verifiable independently of ALLIS output.

The final dataset should preferably derive from:

- authoritative public records;
- qualified local data;
- stable governmental datasets;
- validated institutional records;
- deterministic spatial relationships;
- other sources with explicit provenance.

---

## 8.3 Adequate cardinality

The dataset must contain enough records to permit:

- matched control and experimental conditions;
- relation permutations without trivial duplication;
- task-relevant and task-irrelevant controls;
- meaningful uncertainty estimates;
- held-out or replication subsets where feasible.

The final minimum sample size must be chosen before execution.

---

## 8.4 Relation separability

The dataset must allow one relationship to be altered without necessarily changing all others.

For example:

```text
entity → place
```

should ideally be manipulable without simultaneously deleting:

```text
entity → source
```

or:

```text
entity → type
```

---

## 8.5 Avoidance of trivial leakage

The dataset should minimize cases where the answer is directly encoded in an unmanipulated label.

For example:

```text
Charleston Area Medical Center
```

contains a geographic cue in the entity name itself.

A location task using that record may therefore remain partially solvable after the explicit location relation has been altered.

Such cases may still be retained, but they must be identified as leakage-prone.

---

# 9. Candidate data domains

Candidate domains have been identified but are **not yet selected**.

Potential first domains include:

```text
geographic names

hospitals and public facilities

bridges and transportation infrastructure

stream gauges

rivers and waterways

hazard records

public-safety infrastructure

historic or civic places

other spatially verified public records
```

A hydrologic or infrastructure dataset may be especially useful if it contains several simultaneously testable relationships.

Example:

```text
Gauge_A
    ├── located_at → Point_A
    ├── within → County_A
    ├── measures → River_A
    ├── source → USGS
    └── observed_at → Time_A
```

The plan does not yet select a final source.

---

# 10. Dataset admission process

Candidate data must not become experimental evidence merely because it is available.

The intended admission sequence is:

```text
candidate source
    ↓
source identity verification
    ↓
licensing / permitted-use check
    ↓
record extraction
    ↓
schema normalization
    ↓
referential validation
    ↓
duplicate / conflict review
    ↓
ground-truth relation construction
    ↓
dataset manifest
    ↓
checksum freeze
    ↓
experimental admission
```

The dataset must have a preserved manifest before protocol freeze.

---

# 11. Required dataset manifest

The eventual dataset manifest should record at least:

```text
dataset_name

dataset_version

source_organization

source_url_or_origin

retrieval_date

license_or_use_status

source_files

source_checksums

normalization_code_identity

record_count

included_relation_types

excluded_relation_types

known_limitations

known_ambiguities

ground_truth_method

admission_status

frozen_dataset_sha256
```

The manifest belongs with the eventual experimental package.

---

# 12. Condition design

The minimum design should contain three condition classes.

## 12.1 Correct-relation control

The control representation preserves the verified referential structure:

$$
G_C=(V,E_C).
$$

All task-relevant bindings are correct.

Example:

```text
Gauge_A ──measures────► New_River

Gauge_A ──located_at──► Point_A

Gauge_A ──source──────► USGS
```

---

## 12.2 Task-irrelevant perturbation control

A relation that is not required for the target task is altered.

$$
G_I=(V,E_I).
$$

For a waterbody-identification task, the critical relation might remain:

```text
Gauge_A ──measures──► New_River
```

while an independently represented noncritical relation is changed.

This condition tests whether arbitrary relational manipulation itself causes degradation.

---

## 12.3 Task-relevant perturbation

The relation required for the task is altered:

$$
G_R=(V,E_R).
$$

Example:

```text
correct:

Gauge_A ──measures──► New_River
```

```text
perturbed:

Gauge_A ──measures──► Gauley_River
```

The same nodes remain present.

Only the relevant binding changes.

---

# 13. Preferred matched design

Where possible, every experimental unit should appear across matched conditions:

$$
r_i^C,\qquad r_i^I,\qquad r_i^R,
$$

where:

- $C$ = correct relation;
- $I$ = task-irrelevant perturbation;
- $R$ = task-relevant perturbation.

Define:

$$
\Delta_i^R
=
Y_i^C-Y_i^R
$$

and:

$$
\Delta_i^I
=
Y_i^C-Y_i^I.
$$

The key prediction is:

$$
\mathbb{E}[\Delta^R]
>
\mathbb{E}[\Delta^I].
$$

---

# 14. Relation transformations

## 14.1 Edge permutation

Relations of one type are permuted among records.

```text
A → X
B → Y
C → Z
```

becomes:

```text
A → Y
B → Z
C → X
```

All original nodes remain available.

---

## 14.2 Pairwise swap

Two bindings exchange targets.

```text
A → X
B → Y
```

becomes:

```text
A → Y
B → X
```

Node count, relation count, and target distribution remain unchanged.

---

## 14.3 Edge deletion

A required relationship is removed while both endpoint nodes remain present.

Correct:

```text
A → X
```

Perturbed:

```text
A     X
```

This tests missing relational structure rather than missing informational objects.

---

## 14.4 Ambiguous rebinding

An entity is given multiple possible referential targets without sufficient evidence to distinguish among them.

The appropriate response may become:

```text
INSUFFICIENT_INFORMATION
```

or an explicitly bounded ambiguity statement.

---

## 14.5 Type-preserving replacement

A target is replaced only with another valid target of the same type.

```text
PLACE → PLACE
```

rather than:

```text
PLACE → SOURCE
```

This helps isolate referential identity from obvious type corruption.

---

# 15. Transformations excluded from the primary test

The first referential-geometry experiment should avoid transformations that introduce unnecessary confounds.

Examples include:

```text
removing entire records

changing semantic labels and relations simultaneously

changing model settings between conditions

changing prompt instructions between paired units

using different model versions across conditions

changing relation type and node type simultaneously

adding explanatory context to only one condition
```

Such manipulations may be useful in later experiments.

They should not define the primary causal contrast.

---

# 16. Task families

## 16.1 Entity-to-place attribution

Question:

> Where is entity $E$ located?

Required relation:

```text
ENTITY ──located_at──► PLACE
```

---

## 16.2 Entity-to-feature attribution

Question:

> Which river, road, facility, district, or other feature is entity $E$ associated with?

Required relation:

```text
ENTITY ──associated_with──► FEATURE
```

---

## 16.3 Observation attribution

Question:

> What entity or event does observation $O$ concern?

Required relation:

```text
OBSERVATION ──about──► ENTITY
```

---

## 16.4 Temporal attribution

Question:

> When does record or observation $R$ apply?

Required relation:

```text
RECORD ──observed_at──► TIME
```

---

## 16.5 Source attribution

Question:

> Which source supports record $R$?

Required relation:

```text
RECORD ──sourced_from──► SOURCE
```

Source attribution approaches provenance geometry and may later become its own experimental protocol.

---

# 17. Target behavior

The experiment should not simply reward answering.

Correct behavior may include:

```text
specific supported answer

explicit ambiguity

explicit uncertainty

INSUFFICIENT_INFORMATION

rejection of unsupported specificity
```

The system should not be penalized for abstaining when the supplied relational state is genuinely underdetermined.

---

# 18. Primary outcomes

The primary outcome should be **warranted referential accuracy**.

A response is correct only when its specificity does not exceed the relations supplied by the condition.

Possible scoring states:

```text
SUPPORTED_CORRECT

SUPPORTED_BUT_INCOMPLETE

APPROPRIATE_UNCERTAINTY

AMBIGUITY_PRESERVED

UNSUPPORTED_SPECIFICITY

RELATION_SUBSTITUTION

CONTRADICTED_RELATION

NONRESPONSIVE
```

The exact scoring rubric must be frozen before execution.

---

# 19. Relation-specific error measures

## 19.1 Referential Accuracy

$$
\mathrm{RA}
=
\frac{
\text{correct supported referential answers}
}{
\text{eligible tasks}
}.
$$

---

## 19.2 Unsupported Specificity Rate

$$
\mathrm{USR}
=
\frac{
\text{unsupported specific referential claims}
}{
\text{eligible responses}
}.
$$

---

## 19.3 Appropriate Uncertainty Rate

$$
\mathrm{AUR}
=
\frac{
\text{correct uncertainty or ambiguity responses}
}{
\text{underdetermined trials}
}.
$$

---

## 19.4 Relation-Following Rate

For deliberately rebound conditions:

$$
\mathrm{RFR}
=
\frac{
\text{responses consistent with the supplied relation}
}{
\text{perturbed-relation trials}
}.
$$

Interpretation requires care.

A model that follows a deliberately false experimental binding may be behaving correctly relative to the supplied experimental representation while being wrong relative to external reality.

The protocol must therefore distinguish:

```text
condition-relative correctness
```

from:

```text
world-relative truth
```

---

# 20. Two truth layers

The experiment requires explicit separation of two truth layers.

## 20.1 World truth

Let the verified external relation be:

$$
E_{\mathrm{world}}.
$$

## 20.2 Supplied experimental relation

Let the relation presented to the system be:

$$
E_{\mathrm{supplied}}.
$$

In the correct condition:

$$
E_{\mathrm{supplied}}
=
E_{\mathrm{world}}.
$$

In a deliberate perturbation:

$$
E_{\mathrm{supplied}}
\neq
E_{\mathrm{world}}.
$$

This creates two distinct questions:

> Did ALLIS follow the relational structure actually supplied?

and:

> Did ALLIS recover, resist, or contradict external ground truth?

Both may be scientifically useful.

They must not be collapsed.

---

# 21. Parametric reconstruction

A model may know or infer the world relation independently of the supplied experimental representation.

Example:

```text
supplied relation:
Facility_A → Place_B

model prior:
Facility_A is actually associated with Place_A
```

Possible behaviors include:

```text
follow supplied relation

follow prior knowledge

identify conflict

express uncertainty

attempt reconciliation
```

These responses should be separately classified.

They may reveal an important boundary between:

```text
supplied relational evidence
```

and:

```text
parametric semantic knowledge
```

Prior-knowledge resistance should not automatically be classified as failure.

---

# 22. Information-budget control

Where practical, paired conditions should preserve:

```text
same nodes

same labels

same relation count

same relation types

same approximate token count

same prompt template

same response schema

same model

same inference settings
```

The principal difference should be:

```text
which node is connected to which node
```

This is the strongest available test of relational organization rather than information quantity.

---

# 23. Task-irrelevant controls

Every selected task should identify at least one relation that should not materially affect the answer.

Example:

```text
task:
identify waterbody measured by Gauge_A

critical relation:
Gauge_A ──measures──► River_A

possible noncritical relation:
Gauge_A ──source_epoch──► Epoch_1
```

If source epoch is not required for the bounded task, altering it should have substantially less effect than altering the waterbody binding.

The predicted pattern is:

$$
\Delta_{\mathrm{critical}}
>
\Delta_{\mathrm{noncritical}}.
$$

---

# 24. Restoration test

A strong experimental subset should use a three-stage manipulation:

$$
G
\rightarrow
G'
\rightarrow
G.
$$

Conceptually:

```text
correct relation
    ↓
perturbed relation
    ↓
restored relation
```

The predicted task behavior is:

```text
correct
    ↓
selectively degraded or changed
    ↓
restored
```

while unrelated capabilities remain comparatively stable.

This tests reversibility.

A reversible, relation-specific effect would provide stronger evidence than one-time degradation alone.

---

# 25. Minimal sufficient relation set

A later extension may attempt to identify the smallest relation set required for a task.

For task $T$, define:

$$
E_T^{*}\subseteq E,
$$

where $E_T^{*}$ is sufficient for warranted performance on $T$ and removal of a required member materially reduces performance.

This would move the research from:

> Do relations matter?

toward:

> **Which relations are minimally sufficient for this task?**

This is not required for the first experiment.

---

# 26. Prompt construction

The executable protocol should use a frozen prompt schema.

The prompt should:

- define the bounded task;
- present the same informational object inventory across matched conditions;
- avoid telling the model which relation has been manipulated;
- specify the permitted evidence boundary;
- preserve the same output format across conditions;
- avoid evaluative language that reveals the expected answer.

Prompt wording must be frozen before execution.

---

# 27. Output schema

A structured response format is preferred.

A candidate schema may include:

```text
task_id

record_id

answer

answer_status

referent_used

relation_type_used

evidence_basis

uncertainty_status

conflict_status

unsupported_completion_detected
```

The exact schema should be finalized only after the task family is selected.

---

# 28. Blinding

Where human scoring is required, raters should be blinded to:

```text
condition identity

paired-record identity

transformation class

expected hypothesis direction
```

Where support scoring requires access to condition-specific evidence, a semi-blind procedure may be used.

The final scoring method must state exactly what a rater is permitted to see.

---

# 29. Automated scoring

Automated scoring may be appropriate when:

- the expected referent is deterministic;
- output fields are structured;
- relation identity is machine-readable;
- uncertainty states are explicit.

Human review may still be required for:

- free-text explanations;
- ambiguous responses;
- conflict detection;
- unsupported but linguistically hedged claims.

Automated and human scoring must remain distinguishable.

---

# 30. Model and runtime controls

The final execution must pin the exact inference environment.

The frozen protocol should record at least:

```text
ALLIS source identity

runtime identity

model identity

model version

model checksum where available

prompt identity

temperature

seed where supported

sampling settings

context limits

retrieval configuration

enabled H_* inputs

Gateway path

JCP state

synthesis path

execution timestamp

correspondence evidence
```

A changed model or runtime is a different experimental object unless separately adjudicated.

---

# 31. Qualified baseline gate

Execution must not proceed merely because the experimental dataset is ready.

The relevant ALLIS path must also be sufficiently qualified for the claims the experiment intends to make.

The pre-execution question is:

> **Can we establish what source, runtime, model path, relational inputs, and response path actually produced these outputs?**

If not:

```text
EXECUTION_AUTHORIZED=NO
```

The executable protocol must identify the exact qualification gate.

---

# 32. Protocol-freeze gate

Before execution, freeze:

```text
research question

hypotheses

dataset

dataset manifest

record inclusion criteria

record exclusion criteria

relation types

transformation code

randomization method

prompt template

model/runtime identity

response schema

primary outcomes

secondary outcomes

scoring rubric

statistical analysis

stopping criteria
```

After this point, changes require an explicit protocol amendment.

---

# 33. Randomization

Where relation targets are permuted, the transformation must be deterministic and reproducible.

Preferred:

```text
frozen pseudorandom seed
+
versioned transformation code
+
manifested input dataset
```

The same input and seed should reproduce the same transformed graph.

The transformation process should emit its own manifest.

---

# 34. Transformation validity checks

Every generated perturbation must pass mechanical validation.

Checks may include:

```text
node set unchanged

expected relation count preserved

target relation type preserved

no accidental self-link where prohibited

no duplicate edge where prohibited

critical edge actually changed

noncritical edges preserved where required

control record unchanged

paired record identity preserved

output manifest complete
```

A transformation failing these checks should not enter the experimental corpus.

---

# 35. Statistical analysis plan

The final statistical model should be selected after the task and dataset are finalized but before execution.

The design should favor paired analysis because experimental units are matched across conditions.

Potential methods include:

```text
paired proportion comparison

McNemar-type analysis

conditional logistic models

mixed-effects logistic models

paired ordinal models

bootstrap confidence intervals

permutation tests
```

Choice depends on the final scoring scale and dependency structure.

The first protocol should avoid unnecessary statistical complexity.

Effect sizes and uncertainty should be reported alongside significance testing.

---

# 36. Primary comparison

The principal comparison is:

$$
G_C
\quad\text{versus}\quad
G_R.
$$

That is:

$$
\text{correct relation}
\quad\text{versus}\quad
\text{task-relevant perturbation}.
$$

The stronger confirmatory comparison is:

$$
\Delta_{\mathrm{relevant}}
>
\Delta_{\mathrm{irrelevant}}.
$$

Evidence supporting the hypothesis should therefore require more than:

```text
the perturbed condition performed worse
```

It should preferably show:

```text
task-relevant relational disruption
    ↓
greater task-specific degradation
than
task-irrelevant relational disruption
```

---

# 37. Relation-specificity analysis

Suppose the experiment contains spatial and temporal tasks.

A strong result would look like:

```text
spatial-edge perturbation
    ↓
spatial task degrades strongly
temporal task remains comparatively stable
```

and:

```text
temporal-edge perturbation
    ↓
temporal task degrades strongly
spatial task remains comparatively stable
```

Define an effect matrix:

$$
M_{ij}
=
\text{effect of perturbing relation } i
\text{ on task } j.
$$

A diagonal or near-diagonal effect pattern would provide stronger evidence for typed relational dependence than generalized disruption.

Conceptually:

$$
|M_{ii}|
>
|M_{ij}|
\qquad
\text{for relevant } i\neq j.
$$

This is a prospective prediction, not an established result.

---

# 38. Falsification conditions

The hypothesis would be weakened if one or more of the following occurs:

- task-relevant relation perturbation has no reproducible effect;
- task-irrelevant perturbations have equal or greater effects;
- all relation perturbations cause undifferentiated global degradation;
- results are explained entirely by token count or lexical changes;
- the model reliably reconstructs required referents without the tested relations;
- relation restoration does not restore the affected capability;
- the apparent effect disappears under replication;
- results depend only on one fragile prompt formulation.

Negative and mixed results must be preserved.

---

# 39. Positive-result boundary

A positive experiment would support a bounded statement such as:

> **Under the tested ALLIS configuration, dataset, task, and transformation, preservation of the specified referential relation contributed measurably to warranted referential performance.**

It would **not** establish:

```text
MEANING_REQUIRES_GEOMETRY=PROVEN

UNDERSTANDING_REQUIRES_GEOMETRY=PROVEN

ALL_INTELLIGENCE_REQUIRES_THIS_GEOMETRY=PROVEN

CONSCIOUSNESS_REQUIRES_GEOMETRY=PROVEN

PHYSICAL_SPACETIME_GEOMETRY_EQUIVALENCE=PROVEN

PENROSE_VALIDATED=YES
```

---

# 40. Negative-result boundary

A null result may mean:

- the tested relation was not actually required;
- other retained information reconstructed it;
- the task did not isolate the intended dependency;
- the transformation was too weak;
- the model was insensitive to the representation;
- the hypothesis is wrong for the tested relation/task;
- the selected geometry is not the relevant geometry.

A null result must not be rewritten as success.

---

# 41. Replication

At least one independent replication should precede broader claims.

Replication may vary:

```text
dataset

relation family

task family

model

runtime configuration
```

but should preserve the same formal hypothesis where comparison is intended.

A result confined to one dataset and one prompt family should remain correspondingly bounded.

---

# 42. Cross-domain comparison

This experiment is designed first as an ALLIS study.

Any later comparison with physics-aware cyber-physical systems must establish an actual formal correspondence.

Similarity of terms such as:

```text
topology

constraint

geometry

state

relation
```

is insufficient.

A valid cross-domain comparison would require identifying a common structure such as:

```text
task-relevant state distinction

relation required to preserve that distinction

controlled perturbation of that relation

selective performance consequence
```

Only then should a broader invariant be proposed.

---

# 43. Evidence progression

The referential-geometry work should advance through explicit states:

```text
HYPOTHESIZED
    ↓
PLAN_DEFINED
    ↓
DATASET_SELECTED
    ↓
DATASET_VERIFIED
    ↓
DATASET_FROZEN
    ↓
PROTOCOL_FROZEN
    ↓
EXECUTION_QUALIFIED
    ↓
OBSERVED
    ↓
ANALYZED
    ↓
REPLICATED
    ↓
FORMALIZED_WHERE_SUPPORTED
    ↓
CORRESPONDENCE_VERIFIED_WHERE_APPLICABLE
```

No stage implies the next.

---

# 44. Planned artifacts

This plan anticipates later artifacts such as:

```text
research/relational-geometry/
│
├── README.md
│
├── protocols/
│   ├── referential-geometry-plan.md
│   └── referential-geometry-protocol.md
│
├── datasets/
│   ├── referential-geometry-dataset-manifest.md
│   └── ...
│
└── results/
    └── ...
```

These are future artifacts.

Their appearance in this plan does not mean they already exist.

---

# 45. Immediate next gate

The next task after adoption of this plan is **not experimental execution**.

It is:

> **Select and qualify the candidate dataset.**

That work should answer:

```text
Which source?

Which records?

Which relations?

Which source versions?

Which ground truth?

Which ambiguities?

Which exclusions?

Which task families?

Can the same node inventory support clean relation-only perturbation?
```

Only after those questions are answered should the executable protocol be frozen.

---

# 46. Decision criteria for dataset selection

A candidate dataset should be favored if it provides:

```text
high provenance quality

multiple typed relations

independent ground truth

adequate record count

low lexical leakage

low ambiguity

clean pairwise or permutation transformations

stable source identity

reproducible extraction

clear licensing / permitted use

relation-specific task construction
```

A dataset should be rejected if its limitations make it impossible to distinguish:

```text
relational effect
```

from:

```text
ordinary information loss
```

---

# 47. Working experimental prediction

The core planned prediction is:

> **If a task-relevant relation is changed while the underlying informational objects remain available, the inference depending on that relation should change or become appropriately uncertain, while unrelated inferences should remain comparatively stable.**

In compact form:

$$
\boxed{
\Delta_{\mathrm{relevant}}
>
\Delta_{\mathrm{irrelevant}}
}
$$

with the additional expectation that restoration of the original relation should restore the corresponding task behavior:

$$
G
\rightarrow
G'
\rightarrow
G
$$

and, where the hypothesis holds:

$$
Y
\rightarrow
Y'
\rightarrow
Y.
$$

---

# 48. Research boundary

This plan belongs to the research layer.

It does not supersede:

- [`../../../CURRENT.md`](../../../CURRENT.md)
- [`../../../acceptance/current-system-manifest.md`](../../../acceptance/current-system-manifest.md)
- [`../../../claims/claim-registry.md`](../../../claims/claim-registry.md)
- [`../../../claims/nonclaims-and-residuals.md`](../../../claims/nonclaims-and-residuals.md)

It also does not convert prospective architecture into current runtime fact.

Preserve:

```text
experiment planned
    ≠
experiment executable
```

```text
experiment executable
    ≠
experiment run
```

```text
experiment run
    ≠
result replicated
```

```text
result replicated
    ≠
universal theory established
```

---

# 49. Plan completion condition

This planning document may be considered complete when it sufficiently defines:

```text
the research question

the causal contrast

the required relation structure

dataset admission requirements

control conditions

relation transformations

target tasks

planned measurements

falsification conditions

qualification gates

protocol-freeze requirements
```

It should then remain a planning record.

The later executable protocol should reference this plan rather than silently rewriting its original research logic.

---

<div align="center">

## Kidd's Technical Services

**ALLIS — Referential Geometry Research**

<br>

### **Same informational objects. Different relational bindings. Measurable consequences.**

<br>

The purpose of the experiment is not to prove that geometry matters.

The purpose is to determine whether a task fails **specifically when the relation required to solve that task is no longer preserved**.

<br>

`DATASET_FROZEN=NO`

`PROTOCOL_FROZEN=NO`

`EXECUTION_AUTHORIZED=NO`

`RESULTS_AVAILABLE=NO`

</div>
