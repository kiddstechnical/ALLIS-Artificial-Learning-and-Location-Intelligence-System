# ALLIS Qualified Baseline Manifest

This manifest identifies the **qualified ALLIS reference implementation** used as the common source object for empirical measurement, mathematical specification, formal verification, source correspondence, and runtime correspondence.

The qualified baseline is the uniquely identified committed source object admitted as the reference implementation for subsequent research and validation.

Its qualification record preserves the provenance, methods, measurements, bounded formal results, acceptance decisions, correspondence state, and unresolved residuals that establish what may—and may not—be claimed about that object.

> **Qualified object ≠ evidence about the object ≠ formal claims about the object.**

Qualification does not imply whole-system correctness. Each empirical or formal result applies only to the source domain, assumptions, measurement procedure, proof boundary, and correspondence scope stated for that result.

---

## 1. Qualified source object

The current qualified documentation baseline is:

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

The committed Git HEAD and tree identify the qualified source object.

The qualification boundary is therefore:

$$
S_q =
(\text{branch},\text{HEAD},\text{tree})
$$

with:

$$
\text{authority}(S_q)
=
\text{COMMITTED\_HEAD\_TREE\_ONLY}.
$$

Uncommitted worktree state is not part of the qualified object.

Later development does not silently modify this baseline.

Historical implementations, candidate source trees, temporary analyzers, deployment experiments, and unrelated runtime observations are not incorporated into the baseline merely because they exist.

---

## 2. Purpose of qualification

Qualification fixes the reference implementation against which empirical and formal claims are evaluated.

The baseline answers:

> **What exact implementation is being studied?**

It does not, by itself, answer:

> **What has been measured, proved, demonstrated, or correspondence-verified about that implementation?**

Those questions belong to the qualification record attached to the baseline.

The distinction can be expressed as:

$$
S_q
\neq
E(S_q)
\neq
P(S_q),
$$

where:

- $S_q$ is the qualified source object;
- $E(S_q)$ is the evidence obtained about that object; and
- $P(S_q)$ is the set of propositions formally established about that object.

This separation prevents successful observations or local proofs from being promoted into broader claims without the required evidence.

---

## 3. Qualification methodology

A source revision is admitted as a qualified baseline only when its identity, authority boundary, and supporting evidence are sufficiently fixed for subsequent work to refer to the same object reproducibly.

Qualification requires the source object to be bound to an immutable committed identity.

For the current baseline:

$$
S_q =
(H,T)
$$

where:

- $H$ is the qualified Git commit; and
- $T$ is the committed tree referenced by that commit.

The qualified source authority does not extend to uncommitted worktree state.

Accordingly:

$$
\text{worktree state}
\not\subseteq
S_q.
$$

Qualification also preserves explicit residuals. An unresolved obligation is not removed from the research record merely because another component-level result succeeds.

---

## 4. Validation sequence

The qualified source serves as the common referent for the ALLIS validation sequence:

$$
S_q
\rightarrow
M
\rightarrow
\mathcal{F}
\rightarrow
P
\rightarrow
C_s
\rightarrow
C_r,
$$

where:

- $S_q$ = qualified implementation;
- $M$ = empirical measurement;
- $\mathcal{F}$ = mathematical or formal representation;
- $P$ = proved proposition;
- $C_s$ = source correspondence; and
- $C_r$ = runtime correspondence.

These stages are distinct.

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

bounded runtime correspondence
≠ whole-system proof
```

A result advances only as far as its evidence supports.

---

## 5. Measurement methodology

Measurements associated with this baseline are defined by explicit:

- source domains;
- units of analysis;
- inclusion rules;
- exclusion rules;
- procedures;
- evidence artifacts;
- source identities; and
- interpretation boundaries.

A numerical value without those definitions is not treated as a scientifically interpretable ALLIS metric.

For a measurement $m$, the minimum record is:

$$
m =
(D,U,I,X,P,V,E,B),
$$

where:

- $D$ = measurement domain;
- $U$ = unit of analysis;
- $I$ = inclusion rule;
- $X$ = exclusion rule;
- $P$ = measurement procedure;
- $V$ = resulting value;
- $E$ = reproducibility evidence; and
- $B$ = interpretation boundary.

Detailed measurement definitions belong in `MEASUREMENT_REGISTRY.md` and the corresponding `measurements/` records.

The manifest preserves only measurements that materially define the present qualification state.

---

## 6. Frozen protected-source domain

The mathematical wiring program establishes a frozen static protected-root domain containing:

$$
|P_{\text{source}}| = 85.
$$

Here, $P_{\text{source}}$ denotes the source-established protected-root set used by the bounded wiring analysis.

This is a frozen measurement domain.

It is not a claim that every possible protected operation in the complete system universe has been enumerated.

The qualified lower-bound obligation relation contains four frozen root/component pairs:

$$
|R_{\text{qualified}}| = 4.
$$

The qualification record explicitly preserves:

$$
R_{\text{qualified}}
\neq
R_{\text{complete}}.
$$

No complete global relation $R(p)$ is claimed from this result.

---

## 7. Frozen control-flow formalization

For the four qualified root/component pairs, the source analysis constructs frozen intraprocedural directed control-flow graphs.

Let:

$$
G_q = (V_q,E_q)
$$

denote the combined qualified-pair source graph.

The frozen graph contains:

$$
|V_q| = 102
$$

nodes and:

$$
|E_q| = 107
$$

directed edges.

The control-flow construction reports:

$$
U_{\text{unsupported}} = 0,
$$

where $U_{\text{unsupported}}$ is the number of unsupported control-flow structures encountered within the four modeled roots.

Each of the four qualified governance components binds exactly once into its corresponding source CFG.

These values describe the frozen four-pair intraprocedural model only.

They do not establish a global directed wiring graph for ALLIS.

---

## 8. Effect-candidate reduction

The frozen graph initially yields:

$$
N_{\text{candidate}} = 76
$$

broad effect candidates.

Subsequent semantic reduction separates those candidates into:

$$
N_{\text{source-bound/structural}} = 47
$$

and:

$$
N_{\text{unresolved-symbol}} = 29.
$$

The candidate inventory deliberately does not treat every source-level call as a protected effect sink.

Therefore:

$$
\text{effect candidate}
\neq
\text{effect sink}.
$$

The effect inventory is a formalization artifact used by later proof work. It is not itself a theorem.

---

## 9. Governed-modification architecture

The qualified documentation record identifies the governed-modification architecture as a structured multi-stage system containing 23 connector positions across three governed stages.

The corresponding governed-modification inventory contains 69 stage-level units:

$$
69 = 23 \times 3.
$$

These values are architecture counts, not generalized performance measurements.

The detailed definitions of:

- a governed-modification unit;
- a connector;
- stage membership;
- source inclusion;
- exclusion criteria; and
- measurement procedure

belong in the measurement registry and reproducibility evidence.

The manifest does not infer runtime execution from static architecture counts.

Accordingly:

$$
\text{configured architecture}
\neq
\text{runtime execution}.
$$

---

## 10. Bounded governed-modification theorem family

A bounded formal result establishes the implication:

$$
MFS \Rightarrow (D_{23} \land G),
$$

where the symbols are defined within the controlling formal model for that theorem.

The corresponding bounded fail-closed result is:

$$
(\neg D_{23} \lor \neg G)
\Rightarrow
\neg MFS.
$$

These propositions apply only to the formal domain in which $MFS$, $D_{23}$, and $G$ are defined.

They do not establish a whole-system production-safety theorem.

The theorem registry must therefore preserve, for each proposition:

- the formal statement;
- symbol definitions;
- assumptions;
- modeled domain;
- proof method;
- proof status;
- proof artifact;
- source correspondence;
- runtime correspondence; and
- unresolved obligations.

A theorem label without this context is insufficient.

---

## 11. Bounded BBB dominance result

A separate bounded static proof tract establishes:

```text
BBB_NON_DOMINANCE_BOUNDED_STATIC_PROOF_ESTABLISHED
= YES
```

and:

```text
BBB_DOMINATES_COPY2_MUTATION_SINK
= NO
```

This result is deliberately bounded.

It does **not** establish the broader statements:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN
= YES
```

or:

```text
SYSTEM_PROVEN
= YES
```

The stronger theorem states remain unavailable.

Formally, a negative dominance result within a bounded graph $G_b$ means only that the tested node does not dominate the specified sink under the graph and assumptions used for that proof.

It does not independently establish a global architectural failure.

Thus:

$$
\neg\operatorname{Dom}_{G_b}(BBB,s)
$$

does not imply:

$$
\neg\operatorname{Safe}(\text{ALLIS}).
$$

The domain of the dominance proposition must remain attached to the result.

---

## 12. Runtime observation record

The qualification evidence also contains a bounded authorized runtime-observation procedure.

That procedure authorized eight observation steps and executed all eight:

$$
N_{\text{authorized}} = 8
$$

and:

$$
N_{\text{executed}} = 8.
$$

Within that bounded procedure:

$$
N_{\text{nonzero return}} = 0,
$$

$$
N_{\text{stderr step}} = 0,
$$

with no recorded scope expansion and no prohibited activity.

These values characterize the authorized observation procedure.

They do not establish generalized runtime correctness.

Accordingly:

$$
8/8\ \text{authorized observation steps completed}
\not\Rightarrow
\text{system correctness}.
$$

Successful observation execution is evidence that the procedure ran as authorized, not that every proposition under investigation is true.

---

## 13. Formal objects are not automatically theorems

The qualified baseline distinguishes formalization artifacts from theorem results.

A frozen graph, relation, state space, predicate set, or canonical hash establishes the mathematical object on which reasoning may operate.

It does not by itself establish a theorem over that object.

For example:

$$
G=(V,E)
$$

may be fully constructed and frozen while:

$$
\operatorname{Theorem}(G)
$$

remains unproved.

Therefore:

```text
formal object constructed
≠ theorem proved

theorem proved
≠ source correspondence established

source correspondence established
≠ runtime correspondence established
```

This distinction applies throughout the baseline record.

---

## 14. Correspondence model

ALLIS treats correspondence as an independent validation problem.

The required chain is:

$$
\mathcal{F}
\longleftrightarrow
S_q
\longleftrightarrow
R_o,
$$

where:

- $\mathcal{F}$ is the formal model;
- $S_q$ is the qualified source; and
- $R_o$ is observed runtime behavior.

A mathematically correct proposition does not become an implementation claim unless the relevant formal objects correspond to the qualified source.

Likewise, a source-correspondent result does not become a runtime claim unless the required runtime correspondence is established.

The current principal governed-modification correspondence state is:

```text
CURRENT_GOVERNED_MODIFICATION_PRODUCTION_CORRESPONDENCE
= UNRESOLVED
```

Therefore, no stronger production correspondence claim is inferred.

---

## 15. Current claim boundary

The qualified baseline supports bounded empirical, structural, and formal results.

It does not establish whole-system correctness.

The current controlling boundaries include:

```text
CURRENT_GOVERNED_MODIFICATION_PRODUCTION_CORRESPONDENCE
= UNRESOLVED

PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN
= NO

SYSTEM_PROVEN
= NO
```

These statements are not defects in the baseline definition.

They are explicit limits on what the current qualification record supports.

The baseline remains useful precisely because those limits are preserved rather than hidden.

---

## 16. Residuals and non-promotions

Successful local results do not erase unresolved obligations.

The following inference pattern is prohibited:

$$
\text{local success}
\Rightarrow
\text{global success}.
$$

Likewise:

$$
\text{implemented}
\not\Rightarrow
\text{observed},
$$

$$
\text{observed}
\not\Rightarrow
\text{demonstrated},
$$

$$
\text{demonstrated}
\not\Rightarrow
\text{proven},
$$

and:

$$
\text{proven}
\not\Rightarrow
\text{system-proven}.
$$

An unresolved residual remains part of the research record until it is explicitly resolved by the evidence appropriate to that residual.

No result is promoted merely because a neighboring proof, test, or observation succeeds.

---

## 17. Evidence and provenance rule

The public baseline documentation exposes the academically meaningful result rather than reproducing the engineering chronology used to obtain it.

The public record should preserve:

```text
method
formal object
result
scope
source identity
provenance
correspondence state
residual
```

It should not require a reader to reconstruct the research state from temporary script names, failed analyzer versions, intermediate work directories, transient gate identifiers, or superseded debugging procedures.

Those artifacts remain valuable reproducibility and provenance evidence, but they belong in the corresponding evidence records.

A failed analysis tool is not automatically a failed target-system result.

A partial capture is not automatically sealed evidence.

A historical success is not automatically current authority.

A prepared script is not automatically an executed result.

---

## 18. Documentation relationship

This manifest is the acceptance-layer entry point for the qualified source.

Detailed records remain modular:

```text
acceptance/qualified-baseline/
    qualified object and acceptance boundary

measurements/
    measurement definitions, procedures, and results

mathematics/
    mathematical objects, graphs, relations,
    state spaces, predicates, and invariants

formal-verification/
    theorem statements, proofs, model checks,
    specifications, and counterexamples

correspondence/
    formal-model-to-source and
    source-to-runtime correspondence

evidence/
    reproducibility artifacts,
    validation bundles, and provenance
```

The baseline manifest therefore summarizes research status without becoming a duplicate of the deeper technical records.

---

## 19. Baseline replacement

A later ALLIS source revision does not silently replace this qualified baseline.

For a later source object:

$$
S_{q2} \neq S_{q1},
$$

a new qualification decision is required.

A replacement baseline must establish a new immutable source identity and identify its relationship to the previous qualified object.

Measurements affected by the change must be re-evaluated.

Formal models affected by the change must be re-evaluated.

Proofs whose assumptions, graph structure, predicates, operators, or source bindings change must be reconsidered.

Correspondence must be renewed where required.

Historical qualified baselines remain research records and are not overwritten.

---

## 20. Minimum result record

Every substantive result associated with the qualified baseline must allow a reader to determine:

```text
What exact object was studied?

Which committed source identity does the result apply to?

What domain was examined?

What unit of analysis was used?

What method was used?

What was measured, constructed, observed, or proved?

What assumptions apply?

What evidence supports the result?

Has source correspondence been established?

Has runtime correspondence been established?

What stronger claim is not supported?

What remains unresolved?
```

A count without a method is insufficient.

A theorem without a formal domain is insufficient.

A graph without a source binding is insufficient for an implementation claim.

A formal proof without correspondence status is insufficient for a runtime claim.

A successful component result is not a whole-system result.

---

## 21. Current qualification statement

The current ALLIS qualified baseline is therefore the immutable committed source object identified by:

```text
HEAD:
35f1aa5586e1a23e1ab88f4d757c451b44506893

Tree:
36dd9f2425db4b23bacfce1cb258603cace25f1b
```

under the authority rule:

```text
COMMITTED_HEAD_TREE_ONLY
```

with qualification status:

```text
QUALIFIED_FOR_PRODUCTION_DOCUMENTATION_WITH_EXPLICIT_RESIDUALS
```

The baseline provides a stable common referent for measurement, mathematical specification, theorem development, formal verification, and correspondence analysis.

Its qualification record contains meaningful bounded results, including frozen source domains, formal graph objects, measured structural quantities, bounded theorem results, and authorized runtime observations.

Those results remain limited to their documented domains.

The current record does not establish the production mutation safety theorem and does not establish whole-system proof.

---

## Guiding principle

> **The baseline fixes what is being studied. The qualification record establishes what is known about it. Measurement establishes only what the defined procedure measures. Formal verification establishes only the propositions actually proved over the domains actually modeled. Correspondence determines how far those results may be carried back to implementation and runtime. Unresolved obligations remain visible until they are explicitly resolved.**
