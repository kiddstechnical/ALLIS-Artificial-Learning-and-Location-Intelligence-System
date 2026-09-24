# ALLIS Step-12 Lean Workstream R1 Closeout

## Status

**Workstream:** Step-12 authorized-adoption Lean formalization
**Workstream revision:** R1
**Status:** CLOSED
**Closeout result:** PASS
**Environment:** Local only
**Remote publication:** None

## Formal object

This workstream formalized and qualified the principal results associated with:

`DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1`

The work was performed as a later proof-assistant layer over the existing Step-12 formal record.

It does not rewrite, replace, or retroactively change the historical Step-12 validation classifications.

---

## Controlling identities

### Historical Step-12 parent

`04b933b8db0041716ebe9d74c71248f1a444e9df`

### Qualified Lean proof commit

`71ee78982c918145ca73850170a4c2a8a447170d`

This commit contains the evidence-backed Lean source, toolchain configuration, qualification manifest, correspondence crosswalk, and principal-result qualification report.

All 23 files in this commit were verified byte-for-byte against the sealed qualification evidence.

### Final local metadata head

`beceb3ee44fd5c33eaf689a5abe086e5e9c67911`

This child commit adds only:

* `README.md`
* `.gitignore`

It does not modify proof-bearing source or qualification evidence.

---

## Lean toolchain

Pinned Lean toolchain:

`leanprover/lean4:v4.34.0`

The complete Lean package was rebuilt successfully from a clean state.

Qualified build result:

`LEAN_CLEAN_BUILD=PASS`

Proof-hole check:

`LEAN_PROOF_HOLES=0`

No `sorry` or `admit` proof holes were present in the qualified Lean source.

---

## Principal Step-12 results

### T12D-A — Authorized-application gating

**Lean status:** Kernel checked

The Lean theorem establishes, within the translated formal model, that successful authorized application requires the modeled authorization, target, prestate, one-use/spent-authority, and receipt conditions.

`T12D_A_LEAN_KERNEL_CHECKED=YES`

### T12D-B — Invalid authorization fails closed

**Lean status:** Kernel checked

The Lean theorem establishes, within the translated formal model, that invalid authorization cannot produce successful authorized publication.

`T12D_B_LEAN_KERNEL_CHECKED=YES`

### T12D-C — Empty spool prevents authorized application

**Lean status:** Kernel checked

The Lean theorem establishes, within the translated formal model, that an empty incoming authorized spool produces no claimed work and therefore no authorized application.

`T12D_C_LEAN_KERNEL_CHECKED=YES`

### P12C-09 — Terminal totality

**Lean status:** Disproven

The previously proposed totality claim:

`Q3 ⇒ Q6C ∨ Q6R`

does not hold under the bounded Step-12 model.

The preserved `CE001` counterexample establishes a valid path in which terminalization fails and the record remains in `Q3`.

`P12C_09_LOGICAL_RESULT=DISPROVEN`

`P12C_09_COUNTEREXAMPLE_LEAN_KERNEL_CHECKED=YES`

The refined replacement proposition has not been promoted.

`P12C_09_REFINED_REPLACEMENT_PROMOTED=NO`

---

## Axiom qualification

Lean `#print axioms` reported no theorem-level axiom dependencies for the qualified principal results.

Qualified status:

* T12D-A: `NONE`
* T12D-B: `NONE`
* T12D-C: `NONE`
* P12C-09: `NONE`

This means that Lean reported no theorem-level axiom dependencies for the checked proof terms.

It does **not** mean that every implementation component of the production system has been formally verified.

---

## Formal-statement correspondence

A crosswalk between the controlling Step-12 formal statements and the later Lean encoding has been documented.

`LEAN_TO_STEP12_FORMAL_STATEMENT_CROSSWALK=DOCUMENTED`

This establishes the relationship between the Step-12 propositions and the Lean propositions being proved.

---

## Production correspondence boundary

The following have **not yet** been independently established for the later Lean encoding:

`LEAN_TO_PRODUCTION_SOURCE_CORRESPONDENCE=NOT_YET_ESTABLISHED`

`LEAN_TO_PRODUCTION_RUNTIME_CORRESPONDENCE=NOT_YET_ESTABLISHED`

Accordingly, the current Lean result should be understood as:

> The principal governance propositions have been mathematically adjudicated in the translated Lean model, and the Lean proofs have been independently checked by the Lean kernel.

It should not yet be stated as:

> The Lean proof directly proves every corresponding behavior of the current production implementation.

That stronger statement requires a separate source-correspondence and runtime-correspondence workstream.

---

## Abstract implementation boundary

The present Lean layer intentionally treats some implementation details through abstract interfaces.

These include, among other things:

* SHA-256 implementation;
* canonical JSON implementation;
* detached-signature implementation;
* public-key custody;
* filesystem/path resolution;
* target allowlisting;
* governed mutation implementation; and
* production poststate behavior.

The current proof establishes properties of the formalized governance relationships without claiming independent verification of each underlying production implementation.

---

## Sealed evidence

Final qualification evidence:

`/home/cakidd/allis-lean-evidence/step12-lean-qualification-axiom-free-r2`

Final evidence status:

`STEP12_LEAN_QUALIFICATION_AXIOM_FREE_R2=SEALED_PASS`

The sealed evidence includes:

* repository identity;
* toolchain identity;
* qualified Lean source snapshot;
* controlling Step-12 records;
* qualification manifest;
* correspondence crosswalk;
* principal theorem and axiom report;
* proof-hole check;
* clean-build record;
* prior workstream evidence status;
* SHA-256 manifests; and
* claim-boundary documentation.

The evidence tree passed SHA-256 verification at closeout.

---

## Local Git closeout

Final local branch:

`formal-verification/lean-authorized-adoption-r1`

Commit chain:

`04b933b8db0041716ebe9d74c71248f1a444e9df`

↓

`71ee78982c918145ca73850170a4c2a8a447170d`

↓

`beceb3ee44fd5c33eaf689a5abe086e5e9c67911`

Final worktree status:

`WORKTREE_CLEAN=YES`

Qualified proof commit backed by sealed evidence:

`PROOF_COMMIT_SEALED_EVIDENCE_BACKED=YES`

Proof and metadata commits separated:

`METADATA_SEPARATED_FROM_PROOF_COMMIT=YES`

No remote push or online publication was performed as part of this workstream.

---

## What this workstream establishes

This workstream moves the principal Step-12 governance claims beyond prose-only or test-only representation.

The relevant propositions now exist as precise Lean objects whose proofs or disproof have been checked by the Lean kernel.

This provides an independent formal-logic assurance layer over the Step-12 model.

The workstream also demonstrates that the formal process can preserve a negative result: P12C-09 remains disproven rather than being modified merely to obtain a successful proof.

---

## What this workstream does not establish

This workstream does not establish that the entire ALLIS system is formally proven.

`SYSTEM_PROVEN=NO`

It does not establish direct Lean-to-production source correspondence.

It does not establish direct Lean-to-production runtime correspondence.

It does not independently verify every cryptographic, operating-system, filesystem, build, deployment, key-custody, or runtime mechanism upon which production behavior may depend.

---

## Closeout determination

The Step-12 Lean formalization and qualification workstream R1 is complete.

The principal Step-12 logical results have been adjudicated in Lean, the qualification evidence has been sealed, the qualified proof commit has been verified against that evidence, metadata has been separated from proof-bearing material, and the local worktree is clean.

`LOCAL_LEAN_WORKSTREAM_R1=CLOSED`

Future work should proceed as a new workstream rather than modifying this closed R1 record.

## Next independent workstream

The logical next phase is:

**Lean-to-Production Source Correspondence**

Its purpose is to establish, claim by claim, how the formal objects and predicates used by the Lean proofs correspond to the exact functions, branches, state transitions, data structures, and enforcement points in the qualified production source.

Only after that correspondence is established should the Lean results be promoted as direct evidence about those implementation elements.

Runtime correspondence should remain a distinct subsequent qualification layer.
