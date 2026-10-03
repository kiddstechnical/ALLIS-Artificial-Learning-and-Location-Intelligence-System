# ALLIS — Hilbert/JCP Separation R3 Qualification Evidence

## Public-safe evidence package for the Lean R3 Hilbert/JCP Separation workstream

> [!IMPORTANT]
> This document is a public-safe evidence package for the qualified Lean R3 Hilbert/JCP Separation workstream.
>
> It preserves the fourteen final R3 checks, final proof metrics, current/candidate JCP AST identity, the exact current four-field JCP structure, qualified static H_geo status, current H_geo/H_p/H_people nonadmission, the 11/14 -> 0/14 propext repair history, Git identities, and bounded nonclaims.
>
> It does not claim that future live H_geo admission is proved or that all named H_* objects are linear subspaces.

---

## 1. Workstream identity

```text
WORKSTREAM=LEAN_R3_HILBERT_JCP_SEPARATION
STATUS=QUALIFIED
RESULT=PASS
LEAN_VERSION=4.34.0
```

R3 formalizes the present separation between the current Judge Context Packet and the named Hilbert/projection domains under review.

---

## 2. Final qualification metrics

```text
FINAL_CHECKS=14_OF_14
PROOF_HOLES=0
FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_14
FINAL_PROPEXT_DEPENDENCIES=0_OF_14
```

The final R3 theorem/check family passed qualification.

---

## 3. Fourteen exact R3 checks

```text
1. spatial_sandbox_to_hgeo_static_value_plane
2. happ_x_hgeo_static_admission_correspondence
3. current_jcp_has_exactly_four_top_level_fields
4. current_jcp_has_no_hilbert_tensor_or_spatial_field_names
5. current_jcp_no_hilbert_admission
6. current_hgeo_not_admitted_to_jcp
7. current_hp_not_admitted_to_jcp
8. current_hpeople_not_admitted_to_jcp
9. hp_is_not_hgeo
10. hpeople_is_not_hgeo
11. r10_static_hgeo_candidate_is_not_live_jcp_admission
12. static_hgeo_qualification_does_not_self_authorize
13. absent_current_field_blocks_live_admission
14. source_history_or_static_candidate_cannot_override_current_nonadmission
```

---

## 4. Current JCP builder

The current JCP builder is:

```text
build_judge_context_v2
```

This is the source object against which the present R3 JCP structure was corresponded.

---

## 5. Exact current JCP field set

The current JCP has exactly four top-level fields:

```text
schema_version
request_context
approved_evidence
wv_deliberative_context
```

Therefore:

```text
CURRENT_JCP_TOP_LEVEL_FIELD_COUNT=4
```

---

## 6. No current Hilbert/tensor/spatial JCP field

The current four-field structure contains no top-level field for:

```text
Hilbert
tensor
spatial
H_geo
H_p
H_people
```

Therefore:

```text
CURRENT_JCP_HILBERT_TENSOR_SPATIAL_FIELD_COUNT=0
```

---

## 7. Current/candidate JCP AST identity

The current/candidate JCP builder AST identity is:

```text
7c9cc765677848685066884c47d7ef8c2adf49a5ee4c6ec32da0492f7ef0b422
```

Interpretation:

```text
CURRENT_JCP_AST_SHA256
=
CANDIDATE_JCP_AST_SHA256
```

for the qualified current/candidate comparison.

This supports source correspondence. It is not itself a Lean theorem.

---

## 8. Static H_geo status

The R3 evidence preserves:

```text
STATIC_H_GEO_PATH_QUALIFIED=YES
```

The qualified static path is associated with:

```text
SpatialSandbox
-> stage / evaluate / promote
-> static H_geo value plane
```

and with the bounded static:

```text
H_App x H_geo
```

correspondence.

---

## 9. Static H_geo is not live JCP admission

Preserve:

```text
STATIC_H_GEO_PATH_QUALIFIED=YES
H_GEO_CURRENT_JCP_ADMISSION=NO
```

These are not contradictory. They are the core R3 distinction.

---

## 10. Current nonadmission boundaries

```text
H_GEO_CURRENT_JCP_ADMISSION=NO
H_P_CURRENT_JCP_ADMISSION=NO
H_PEOPLE_CURRENT_JCP_ADMISSION=NO
```

H_p remains a separate governed civic-query projection path.

H_people remains a separate governed people/private-state domain.

---

## 11. H_p / H_people distinction from H_geo

The qualified R3 domain preserves:

```text
H_p != H_geo
H_people != H_geo
```

This prevents H_geo qualification from being substituted for H_p or H_people qualification.

---

## 12. Static candidate does not equal live admission

R3 establishes:

```text
static H_geo candidate
!=
live JCP admission
```

via:

```text
r10_static_hgeo_candidate_is_not_live_jcp_admission
```

---

## 13. Static qualification does not self-authorize

R3 establishes:

```text
static H_geo qualification
!=
authority to modify live JCP
```

via:

```text
static_hgeo_qualification_does_not_self_authorize
```

The broader architecture rule remains:

```text
qualified
!=
authorized
```

---

## 14. Absent field blocks live admission

R3 preserves:

```text
field absent
=>
current live admission blocked
```

via:

```text
absent_current_field_blocks_live_admission
```

The fail-closed interpretation is:

```text
NONADMITTED
```

not:

```text
implicitly available
```

---

## 15. Historical/static evidence cannot override current nonadmission

R3 also establishes:

```text
historical source reference
!=
current live admission
```

and:

```text
static candidate
!=
authority to override current nonadmission
```

via:

```text
source_history_or_static_candidate_cannot_override_current_nonadmission
```

---

## 16. Initial proof state

The initial R3 formalization reached:

```text
COMPILED_CHECKS=14_OF_14
PROOF_HOLES=0
INITIAL_PROPEXT_DEPENDENCIES=11_OF_14
```

That state was not accepted as final qualification.

---

## 17. R3 proof repair

R3 was repaired by re-expressing the predicates in a more computational / Bool-oriented form.

Final state:

```text
FINAL_PROPEXT_DEPENDENCIES=0_OF_14
FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_14
```

The architectural claims were preserved, but the final formulation should not be described as byte-identical to the initial statements.

```text
ARCHITECTURAL_CLAIMS_PRESERVED=YES
FORMAL_EXPRESSION_REWORKED=YES
```

---

## 18. Parent and R3 Git identities

Parent R2 HEAD:

```text
c1a18b2e5fbe2e288d8b91dafe18668392bc787d
```

R3 branch:

```text
formal-verification/hilbert-jcp-separation-r3
```

R3 HEAD:

```text
6f4a7de303e2d80c3d94a28a8d82e696387bf4b2
```

R3 tree:

```text
f5ffcb3fd693cbed60c1bd9dc966f868472707d4
```

Primary formal source:

```text
HilbertJcpSeparationR3.lean
```

---

## 19. R16AR2 seal identities

Final R16AR2 closeout/result SHA-256:

```text
2c1752a49d4a503023439df166621bdfaa08d60cf6344f32adcf4e81b281462f
```

R16AR2 manifest SHA-256:

```text
3827f6fad0923c18f6896f381e5a1ab26335adf4def81765765aae06e87280cd
```

---

## 20. Public-safe qualification seal

```text
R3_HEAD
6f4a7de303e2d80c3d94a28a8d82e696387bf4b2

R3_TREE
f5ffcb3fd693cbed60c1bd9dc966f868472707d4

JCP_AST_SHA256
7c9cc765677848685066884c47d7ef8c2adf49a5ee4c6ec32da0492f7ef0b422

R16AR2_FINAL_SHA256
2c1752a49d4a503023439df166621bdfaa08d60cf6344f32adcf4e81b281462f

R16AR2_MANIFEST_SHA256
3827f6fad0923c18f6896f381e5a1ab26335adf4def81765765aae06e87280cd
```

---

## 21. Model/source correspondence summary

The R3 model/source crosswalk binds the formal domain to:

```text
build_judge_context_v2
exact four-field JCP structure
current absence of Hilbert/tensor/spatial field names
static H_geo path
separate H_p boundary
separate H_people boundary
```

This correspondence remains distinct from pure Lean proof and from runtime identity.

---

## 22. Future live H_geo admission is not proved

Preserve exactly:

```text
FUTURE_LIVE_H_GEO_ADMISSION_PROVED=NO
LIVE_HILBERT_JCP_INTEGRATION_COMPLETE=NO
```

R3 proves present nonadmission. It does not prohibit a separately qualified successor implementation.

---

## 23. H384 remains future work

R3 does not prove the planned shared carrier theorem family.

```text
H384_FORMALIZATION_COMPLETE=NO
```

---

## 24. Named H_* objects are not automatically subspaces

R3 does not establish:

```text
ALL_NAMED_H_OBJECTS_ARE_LINEAR_SUBSPACES=YES
```

The safe current classification remains:

```text
governed typed projection / view / architectural state domain
```

until closure/subspace properties are separately proved.

---

## 25. R3 does not grant JCP mutation authority

Formal qualification does not authorize:

```text
changing build_judge_context_v2
adding H_geo fields
adding H_people fields
deploying a successor JCP schema
```

Operational authority remains separate.

---

## 26. R3 does not prove whole-system safety

Preserve:

```text
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO
SYSTEM_PROVEN=NO
```

R3 is a bounded current-state separation domain.

---

## 27. Evidence summary table

| Evidence item | Value |
|---|---|
| Lean version | `4.34.0` |
| Final R3 checks | `14/14` |
| Proof holes | `0` |
| Initial `propext` dependencies | `11/14` |
| Final `propext` dependencies | `0/14` |
| Final theorem-level axiom dependencies | `0/14` |
| Current JCP builder | `build_judge_context_v2` |
| Current JCP field count | `4` |
| Current/candidate JCP AST SHA-256 | `7c9cc765677848685066884c47d7ef8c2adf49a5ee4c6ec32da0492f7ef0b422` |
| R3 HEAD | `6f4a7de303e2d80c3d94a28a8d82e696387bf4b2` |
| R3 tree | `f5ffcb3fd693cbed60c1bd9dc966f868472707d4` |
| R16AR2 final SHA-256 | `2c1752a49d4a503023439df166621bdfaa08d60cf6344f32adcf4e81b281462f` |
| R16AR2 manifest SHA-256 | `3827f6fad0923c18f6896f381e5a1ab26335adf4def81765765aae06e87280cd` |

---

## 28. Normalized evidence record

```yaml
r3_qualification_evidence:
  workstream: LEAN_R3_HILBERT_JCP_SEPARATION
  status: QUALIFIED
  result: PASS
  lean_version: "4.34.0"

  qualification:
    final_checks: 14
    proof_holes: 0
    initial_propext_dependencies: "11/14"
    final_propext_dependencies: "0/14"
    final_theorem_level_axiom_dependencies: "0/14"

  git:
    parent_r2_head: c1a18b2e5fbe2e288d8b91dafe18668392bc787d
    branch: formal-verification/hilbert-jcp-separation-r3
    head: 6f4a7de303e2d80c3d94a28a8d82e696387bf4b2
    tree: f5ffcb3fd693cbed60c1bd9dc966f868472707d4

  source:
    principal_lean_file: HilbertJcpSeparationR3.lean

  jcp:
    builder: build_judge_context_v2
    top_level_field_count: 4
    fields:
      - schema_version
      - request_context
      - approved_evidence
      - wv_deliberative_context
    hilbert_tensor_spatial_field_count: 0
    current_candidate_ast_sha256: 7c9cc765677848685066884c47d7ef8c2adf49a5ee4c6ec32da0492f7ef0b422

  static_h_geo:
    qualified: true
    live_jcp_admission: false
    self_authorizes: false

  current_admission:
    H_geo: false
    H_p: false
    H_people: false

  seals:
    r16ar2_final_sha256: 2c1752a49d4a503023439df166621bdfaa08d60cf6344f32adcf4e81b281462f
    r16ar2_manifest_sha256: 3827f6fad0923c18f6896f381e5a1ab26335adf4def81765765aae06e87280cd

  nonclaims:
    future_live_H_geo_admission_proved: false
    live_hilbert_jcp_integration_complete: false
    h384_formalization_complete: false
    named_H_objects_automatically_linear_subspaces: false
    system_proven: false
```

---

## 29. Final qualification record

```text
R3_QUALIFICATION=PASS
LEAN_VERSION=4.34.0
FINAL_CHECKS=14_OF_14
PROOF_HOLES=0
INITIAL_PROPEXT_DEPENDENCIES=11_OF_14
FINAL_PROPEXT_DEPENDENCIES=0_OF_14
FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_14

CURRENT_JCP_BUILDER=build_judge_context_v2
CURRENT_JCP_TOP_LEVEL_FIELD_COUNT=4

CURRENT_JCP_FIELDS:
schema_version
request_context
approved_evidence
wv_deliberative_context

CURRENT_JCP_HILBERT_TENSOR_SPATIAL_FIELD_COUNT=0

JCP_AST_SHA256=7c9cc765677848685066884c47d7ef8c2adf49a5ee4c6ec32da0492f7ef0b422

STATIC_H_GEO_PATH_QUALIFIED=YES
H_GEO_CURRENT_JCP_ADMISSION=NO
H_P_CURRENT_JCP_ADMISSION=NO
H_PEOPLE_CURRENT_JCP_ADMISSION=NO

R3_HEAD=6f4a7de303e2d80c3d94a28a8d82e696387bf4b2
R3_TREE=f5ffcb3fd693cbed60c1bd9dc966f868472707d4

R16AR2_FINAL_SHA256=2c1752a49d4a503023439df166621bdfaa08d60cf6344f32adcf4e81b281462f
R16AR2_MANIFEST_SHA256=3827f6fad0923c18f6896f381e5a1ab26335adf4def81765765aae06e87280cd

FUTURE_LIVE_H_GEO_ADMISSION_PROVED=NO
LIVE_HILBERT_JCP_INTEGRATION_COMPLETE=NO
H384_FORMALIZATION_COMPLETE=NO
SYSTEM_PROVEN=NO
```

---

## Governing principles

> **R3 is a qualified formal domain with fourteen final checks.**
>
> **The final workstream contains zero proof holes and zero final theorem-level axiom dependencies.**
>
> **The current JCP has exactly four top-level fields.**
>
> **The current JCP contains no Hilbert/tensor/spatial top-level field.**
>
> **The current/candidate JCP builder AST identity is explicit and preserved.**
>
> **Static H_geo qualification is real evidence, but static qualification is not live JCP admission.**
>
> **H_geo, H_p, and H_people remain currently nonadmitted to JCP.**
>
> **Static H_geo qualification does not self-authorize a schema or runtime transition.**
>
> **Historical source and static candidate evidence cannot override current nonadmission.**
>
> **Future live H_geo admission is not proved by R3.**
>
> **Named H_* objects are not automatically proved linear subspaces.**
>
> **SYSTEM_PROVEN remains NO.**
