# Qualified Baseline

This directory contains the acceptance record for the **qualified ALLIS reference implementation**.

Its purpose is to identify the exact committed source object used as the common referent for measurement, mathematical specification, formal verification, and correspondence analysis, while keeping that object distinct from the evidence and claims produced about it.

> **Qualified object ≠ evidence about the object ≠ formal claims about the object.**

The qualified baseline fixes **what is being studied**. The surrounding qualification record establishes **what is known about it, how that knowledge was obtained, and what remains unresolved**.

---

## Current qualified baseline

The current documentation baseline is:

```text
Baseline ID:
ALLIS-PRODUCTION-DOCUMENTATION-BASELINE-20260917T161252Z

Branch:
remediation/bbb-fail-closed-20260830T212059Z

HEAD:
35f1aa5586e1a23e1ab88f4d757c451b44506893

Tree:
36dd9f2425db4b23bacfce1cb258603cace25f1b

Source authority:
COMMITTED_HEAD_TREE_ONLY

Qualification status:
QUALIFIED_FOR_PRODUCTION_DOCUMENTATION_WITH_EXPLICIT_RESIDUALS
```

The committed HEAD and tree identify the reference source object.

Uncommitted worktree state, later development, historical implementations, runtime observations, and external deployment state are not silently incorporated into this baseline.

---

## Read first

Start with:

- [`QUALIFIED_BASELINE_MANIFEST.md`](./QUALIFIED_BASELINE_MANIFEST.md) — identifies the qualified source object, states the qualification boundary, summarizes current measurement and formal results, and records the principal unresolved residuals.

The manifest is the authoritative entry point for this directory.

It is intentionally not a development log. Temporary scripts, failed analyzers, historical gate chronology, and raw execution transcripts belong in the appropriate evidence and provenance records rather than in the public baseline definition.

---

## What belongs here

This directory should contain the compact acceptance-layer documents needed to understand and audit the qualified baseline.

Planned or supporting documents include:

```text
acceptance/qualified-baseline/
├── README.md
├── QUALIFIED_BASELINE_MANIFEST.md
├── QUALIFICATION_METHOD.md
├── MEASUREMENT_REGISTRY.md
├── FORMAL_MODEL_REGISTRY.md
├── THEOREM_REGISTRY.md
├── CORRESPONDENCE_STATUS.md
└── RESIDUALS_AND_NON_PROMOTIONS.md
```

These files should summarize the research state at the acceptance layer while pointing to deeper technical records elsewhere in the repository.

### `QUALIFICATION_METHOD.md`

Explains how a source object is admitted as a qualified baseline, including source identity, authority rules, provenance requirements, worktree separation, and the conditions for replacing or superseding a baseline.

### `MEASUREMENT_REGISTRY.md`

Indexes measurements associated with the baseline and records, for each measurement:

- the source domain;
- the unit of analysis;
- the inclusion and exclusion rules;
- the measurement procedure;
- the resulting value;
- reproducibility references; and
- the interpretation boundary.

### `FORMAL_MODEL_REGISTRY.md`

Indexes mathematical objects derived from the qualified source, including graphs, relations, predicates, state variables, invariants, and other formal structures used by later proofs.

A formal model is not automatically a theorem.

### `THEOREM_REGISTRY.md`

Records formal propositions separately from measurements and model-construction artifacts.

Each theorem entry should identify its:

- formal statement;
- symbol definitions;
- domain;
- assumptions;
- proof method;
- proof status;
- proof artifact;
- source correspondence;
- runtime correspondence, where required; and
- residual obligations.

### `CORRESPONDENCE_STATUS.md`

Records whether formal objects and results have been connected back to the qualified source and, where required, to observed runtime behavior.

### `RESIDUALS_AND_NON_PROMOTIONS.md`

Records unresolved obligations and the stronger claims that therefore remain unavailable.

Residuals remain part of the research record until they are explicitly resolved; they are not inferred away from successful component-level results.

---

## Relationship to the rest of the repository

The acceptance layer identifies the qualified object and summarizes its research status. Detailed technical material remains modular.

```text
acceptance/
    what source object is qualified and
    what acceptance status applies

measurements/
    how empirical quantities were defined,
    collected, and reproduced

mathematics/
    formal definitions, state spaces,
    graphs, relations, and invariants

formal-verification/
    proofs, specifications, model checks,
    and counterexamples

correspondence/
    model-to-source and source-to-runtime
    correspondence

evidence/
    reproducibility bundles, validation
    artifacts, and provenance
```

This separation prevents the baseline definition from becoming confused with the evidence used to evaluate it.

---

## Research sequence

The qualified baseline serves as the common referent for the following sequence:

\[
\text{qualified implementation}
\rightarrow
\text{measurement}
\rightarrow
\text{formalization}
\rightarrow
\text{proof}
\rightarrow
\text{source correspondence}
\rightarrow
\text{runtime correspondence}
\]

Each stage answers a different question.

```text
qualified
≠ measured

measured
≠ formally specified

formally specified
≠ proven

proven
≠ source-correspondence verified

source-correspondence verified
≠ runtime-correspondence verified
```

A result may advance through these stages only when the required evidence exists.

---

## Current claim boundary

The current qualified baseline supports bounded empirical and formal results, but it does not establish whole-system correctness.

At the present baseline state:

```text
CURRENT_GOVERNED_MODIFICATION_PRODUCTION_CORRESPONDENCE
= UNRESOLVED

PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN
= NO

SYSTEM_PROVEN
= NO
```

These are not failures of the baseline. They are explicit research boundaries.

The purpose of the qualified-baseline record is to make those boundaries visible so that successful local results are not promoted into broader claims without the required proof and correspondence.

---

## Documentation rule

Every substantive result associated with this directory should make it possible for a reader to determine:

```text
What object was studied?
What method was used?
What was measured or proved?
Over what domain?
Against which committed source?
What evidence supports the result?
What correspondence has been established?
What remains unresolved?
```

A count without a method is insufficient.

A theorem without a stated domain is insufficient.

A formal result without correspondence status is insufficient for an implementation or runtime claim.

A successful component result is not a whole-system result.

---

## Baseline replacement

A later ALLIS source revision does not silently become the new qualified baseline.

A replacement baseline should receive:

- a new immutable source identity;
- a new qualification decision;
- an explicit relationship to the prior baseline;
- re-evaluation of measurements affected by the change;
- re-evaluation of formal objects and proofs affected by the change; and
- renewed correspondence analysis where required.

Historical baselines should remain preserved as research records rather than overwritten.

---

## Guiding principle

> **The baseline fixes what is being studied. The qualification record establishes what is known about it. Formal verification establishes only the propositions actually proved over the domains actually modeled. Correspondence determines how far those results may be carried back to implementation and runtime.**
