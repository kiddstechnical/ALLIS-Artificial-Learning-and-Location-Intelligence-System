<div align="center">

# ALLIS — Baseline Object Registry

### Composite registry of qualified object identities, successor qualifications, correspondence objects, and sealed evidence states

<br>

![Registry](https://img.shields.io/badge/REGISTRY-BASELINE_OBJECTS-2563eb?style=for-the-badge)
![R1](https://img.shields.io/badge/LEAN_R1-CLOSED_PASS-9333ea?style=for-the-badge)
![R2](https://img.shields.io/badge/LEAN_R2-CLOSED_PASS-7c3aed?style=for-the-badge)
![R3](https://img.shields.io/badge/LEAN_R3-CLOSED_PASS-6d28d9?style=for-the-badge)
![Rule](https://img.shields.io/badge/PREDECESSOR_IDENTITIES-PRESERVED-f59e0b?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This registry adds the new qualified R2/R3 objects and their correspondence identities to the composite baseline **without rewriting predecessor identities**.
>
> Preserve:
>
> ```text
> successor object added
>     ≠
> predecessor identity replaced
> ```
>
> and:
>
> ```text
> new correspondence
>     ≠
> historical seal rewritten
> ```

---

# 1. Purpose

This file is the compact baseline object registry for the current composite ALLIS technical record.

It records:

- predecessor qualified sources;
- proof/source anchors;
- DGM Step-12 production and seal objects;
- Lean R1;
- Lean R2;
- Lean R3;
- R2/R3 correspondence objects;
- post-A8 DGM correspondence;
- trust/governance objects;
- publication objects;
- current frontend/Gateway production evidence where appropriate.

The registry is additive.

---

# 2. Registry rule

The central registry rule is:

```text
object identity belongs to a role and scope
```

Therefore:

```text
later qualification
    ≠
earlier identity replacement
```

No object inherits another object's authority merely by appearing later in time.

---

# 3. Object classes

| Class | Meaning |
|---|---|
| `QUALIFIED_SOURCE` | Qualified source identity for a bounded workstream |
| `PROOF_SOURCE_ANCHOR` | Source identity anchoring a bounded formal analysis |
| `PRODUCTION_SOURCE` | Production source identity used by a bounded formal/correspondence package |
| `PROOF_ASSISTANT_QUALIFICATION` | Lean-qualified proof object over a bounded proposition/check family |
| `CORRESPONDENCE_REFERENCE_SET` | Source/runtime/live-observation correspondence object |
| `TRUST_OBJECT` | Sealed verification trust state |
| `GOVERNANCE_OBJECT` | Sealed governance-state identity |
| `EVIDENCE_SEAL` | Final bounded evidence-state identity |
| `PUBLICATION_OBJECT` | Governed immutable public projection |
| `FRONTEND_BUILD` | Frontend build identity |
| `PRODUCTION_RUNTIME` | Qualified production runtime identity |

---

# 4. Predecessor identities — preserved unchanged

The following predecessor identities remain unchanged.

## `OBJ-F01` — Workstream-F qualified source

```text
class = QUALIFIED_SOURCE

branch =
remediation/active-source-baseline-20260902

HEAD =
65b9f7dbd594ec9d225152aabd705eefc9216dbb

tag =
stage10-auth-identity-65b9f7dbd594
```

State:

```text
CLOSED
```

---

## `OBJ-A501` — A5 proof/source anchor

```text
class = PROOF_SOURCE_ANCHOR

HEAD =
35f1aa5586e1a23e1ab88f4d757c451b44506893

tree =
36dd9f2425db4b23bacfce1cb258603cace25f1b
```

State:

```text
QUALIFIED_ANCHOR
```

---

## `OBJ-D1201` — Step-12 production DGM source

```text
class = PRODUCTION_SOURCE

identity =
20c8cbe175781c8a1c05d65c03977859ceca884a

formal_object =
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

State:

```text
GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS
```

---

## `OBJ-LR101` — Lean R1 proof-assistant qualification

```text
class = PROOF_ASSISTANT_QUALIFICATION

qualified_proof_commit =
71ee78982c918145ca73850170a4c2a8a447170d

metadata_head =
beceb3ee44fd5c33eaf689a5abe086e5e9c67911

tree =
a62d4b78db5aae522fd06f61b9563e676eacc0a8

lean_toolchain =
leanprover/lean4:v4.34.0
```

State:

```text
CLOSED_PASS
```

This identity remains R1.

It is not replaced by R2 or R3.

---

## `OBJ-D12R01` — Post-A8 DGM theorem correspondence

```text
class = CORRESPONDENCE_REFERENCE_SET

identity =
POST_A8_DGM_THEOREM_CORRESPONDENCE_REGISTRY_R1

production_source =
20c8cbe175781c8a1c05d65c03977859ceca884a

source_tree =
8d0840f076e84b4033ff398f602fb81a6d6e29f2
```

State:

```text
PASS
```

Current bounded correspondence:

```text
NBB = PASS_11_OF_11
WORKER = PASS_11_OF_11
T12D-B = CORRESPONDENCE_VERIFIED
T12D-C = CORRESPONDENCE_VERIFIED
```

---

## `OBJ-D1202` — Step-12 public trust object

```text
class = TRUST_OBJECT

sha256 =
4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5
```

State:

```text
PASS_AT_FINAL_SEAL
```

---

## `OBJ-D1203` — Step-12 governance view

```text
class = GOVERNANCE_OBJECT

sha256 =
26523c0bad40ff06a75c62a802f20195295534764dce45cfa6acdcdaecc3fcc2
```

State:

```text
PASS_AT_FINAL_SEAL
```

---

## `OBJ-D1204` — Step-12 final evidence seal

```text
class = EVIDENCE_SEAL

sha256 =
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

State:

```text
GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS
```

---

## `OBJ-P1701` — Step-17 publication object

```text
class = PUBLICATION_OBJECT

identity =
allis-publication-step6-retention-v2
```

State:

```text
GREEN_COMPLETE
```

---

## `OBJ-P1702` — Step-17 publication body

```text
class = PUBLICATION_OBJECT

sha256 =
d6ab63522f9080fae440578ebbb6ed42140595155c9a30253f5b8eeeef8009b7
```

State:

```text
DIRECT_PUBLIC_BODY_PASS
```

---

## `OBJ-P1703` — Step-17 frontend build

```text
class = FRONTEND_BUILD

identity =
5By6R3CWTM7NDXc-4lmSi
```

Observation boundary:

```text
FINAL_STEP17_SEAL
```

This historical frontend object remains unchanged.

---

# 5. New first-class R2 object

## `OBJ-LR201` — Lean R2 Conversational Admission qualification

```text
class = PROOF_ASSISTANT_QUALIFICATION

branch =
formal-verification/lean-conversational-admission-r2

HEAD =
c1a18b2e5fbe2e288d8b91dafe18668392bc787d

tree =
e325bfdd78cd6903dbfb3a8c15130af26de5cd9f

lean_version =
4.34.0
```

State:

```text
CLOSED_PASS
```

Final proof metrics:

```text
principal_checks = 6
kernel_checked = 6/6
proof_holes = 0
final_theorem_level_axiom_dependencies = 0/6
final_propext_dependencies = 0/6
```

---

# 6. R2 proof evidence identities

Public-safe R2 evidence identities:

```text
evidence_manifest_sha256 =
fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229

status_sha256 =
38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898

source_manifest_sha256 =
21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b

final_sha256 =
ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30

final_manifest_sha256 =
7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf
```

---

# 7. New R2 correspondence object

## `OBJ-R2C01` — Conversational Admission source/runtime correspondence

```text
class = CORRESPONDENCE_REFERENCE_SET

role =
conversational_admission_r2_source_runtime
```

State:

```text
PASS
```

Bounded correspondence:

```text
ordinary_route = /api/chat

authenticated_user_source = SERVER_DERIVED

browser_identity_authoritative = NO

user_id_when_canonical_scalar_unestablished = null

Gateway_accepts_authenticated_user = YES

process_unified_reads_authenticated_user = NO

authenticated_user_enters_current_JCP = NO

authenticated_user_becomes_model_input = NO

authenticated_user_creates_governance_authority = NO

ordinary_chat_authorizes_H_people_SECRET_disclosure = NO
```

This object does not replace `OBJ-LR201`.

It represents a different evidence layer.

---

# 8. New first-class R3 object

## `OBJ-LR301` — Lean R3 Hilbert/JCP Separation qualification

```text
class = PROOF_ASSISTANT_QUALIFICATION

branch =
formal-verification/hilbert-jcp-separation-r3

HEAD =
6f4a7de303e2d80c3d94a28a8d82e696387bf4b2

tree =
f5ffcb3fd693cbed60c1bd9dc966f868472707d4

principal_source =
HilbertJcpSeparationR3.lean
```

State:

```text
CLOSED_PASS
```

Final proof metrics:

```text
principal_checks = 14
kernel_checked = 14/14
proof_holes = 0
final_theorem_level_axiom_dependencies = 0/14
final_propext_dependencies = 0/14
```

---

# 9. New R3 correspondence object

## `OBJ-R3C01` — Hilbert/JCP source/runtime correspondence

```text
class = CORRESPONDENCE_REFERENCE_SET

role =
hilbert_jcp_separation_r3_source_runtime
```

State:

```text
PASS
```

Current JCP builder:

```text
build_judge_context_v2
```

Current/candidate AST SHA-256:

```text
7c9cc765677848685066884c47d7ef8c2adf49a5ee4c6ec32da0492f7ef0b422
```

Exact current top-level field set:

```text
schema_version
request_context
approved_evidence
wv_deliberative_context
```

Admission state:

```text
H_geo = NO
H_p = NO
H_people = NO
```

Static qualification state:

```text
STATIC_H_GEO_PATH_QUALIFIED=YES
```

---

# 10. R3 final seal identities

Public-safe R3 final identities:

```text
R16AR2_FINAL_SHA256 =
2c1752a49d4a503023439df166621bdfaa08d60cf6344f32adcf4e81b281462f

R16AR2_MANIFEST_SHA256 =
3827f6fad0923c18f6896f381e5a1ab26335adf4def81765765aae06e87280cd
```

These belong to the R3 qualification record.

They do not replace any Step-12 or R1 seal.

---

# 11. Current frontend production object

## `OBJ-FE201` — Current conversational frontend production deployment

```text
class = FRONTEND_BUILD

build_id =
9KyheKDYXyNCclA1YrUAX

live_path =
/opt/msjarvis-rebuild/allis-frontend-runtime/deploy-9KyheKDYXyNCclA1YrUAX-fullnm-3ace386dedd9

service =
allis-frontend.service
```

Cutover final SHA-256:

```text
48156cf5595ea93093439c9d199d91e60d1236603b971d4b4938fc0cbb3a2cb6
```

Cutover manifest SHA-256:

```text
40f79d6ce944ce7be096fe4d3ccc286457ed3d0de72f65203bfb9b1fb747c95d
```

State:

```text
PRODUCTION_CUTOVER_PASS
```

This is a later current conversational frontend object.

It does not overwrite historical `OBJ-P1703`.

---

# 12. Current Unified Gateway production object

## `OBJ-GW201` — Qualified production Unified Gateway

```text
class = PRODUCTION_RUNTIME

source_sha256 =
a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f

container =
6056e7c7848af2e676bbc53c6c909e3844bdec2f1c5a5832b7599e237bce3481

image =
sha256:f2ee4e106373a321f65ab2eef00cf7d3b09cf1bdcf61bfb44ed79ec977f6444b
```

Production cutover:

```text
record =
R16C4R20R4

final_sha256 =
1aaccf30781dc38f2ad10446bce30f3d9f8eb047a560e9b34de2cb94aa0b6f44

manifest_sha256 =
213eeb4ab6511ff78d5c1df9791d46917e0c055342bc65e2ab054e4a75e5bcbc
```

State:

```text
PRODUCTION_CUTOVER_PASS
```

Observed path:

```text
Unified Gateway
-> BBB
-> llm20production
-> LM Synthesizer
-> response
```

---

# 13. Current durable server closeout object

## `OBJ-CS201` — Durable server/UI-boundary closeout

```text
class = EVIDENCE_SEAL

record =
R16C4R20R5R1

final_sha256 =
79c7ceaf7549543e194176881b9b4b77c8766057c8f2d8f281d3f596502ffbb6

manifest_sha256 =
37b1811a20107c08a0d1eb11c9d0e10a69fcec3e8bc7589f203d9c006d3461f6
```

State:

```text
SERVER_SIDE_ROUTE_QUALIFIED
```

Explicit browser boundary:

```text
CURRENT_BROWSER_CONVERSATIONAL_UI_READY=NO
CURRENT_BROWSER_CONVERSATIONAL_SEND_SURFACE=NO
AUTHENTICATED_BROWSER_CHAT_E2E=NOT_EXECUTABLE_CURRENT_UI
```

---

# 14. Auth/Guardian current qualified object

## `OBJ-AUTH201` — Versioned auth/Guardian installation

```text
class = QUALIFIED_SOURCE

installed_path =
/opt/msjarvis-rebuild/ms-allis-auth-runtime/deploy-r16c4r15r1-3db1a68d6bcc

rollback_path =
/opt/msjarvis-rebuild/ms-allis-auth-runtime/deploy-r16c4r6r4r1-a288b4613774

service =
ms-allis-auth8095.service
```

Auth runtime candidate inventory SHA-256:

```text
3db1a68d6bccca0ef04c52bb40b6b54fb00d0ab9851a9dd0c8b7b3de37d4e7f8
```

Guardian-client candidate SHA-256:

```text
066a5959007824b57d2cd62f6357d0af1ffaa1db200d9ad52a6e4acaea6339c6
```

State at install closeout:

```text
INSTALL_ONLY
ACTIVE_RUNTIME_MUTATION=NO
PRODUCTION_NONACTIVATION=PASS
```

This object records qualified installation, not hidden activation.

---

# 15. Guardian candidate object

## `OBJ-GUARD201` — Guardian registration-review candidate

```text
class = QUALIFIED_SOURCE

tag =
allis-guardian-registration-review-r16c4r15:5860bf8ab543

image_id =
sha256:5e270aa93911602c15f5f052eab2e5283b39f023e5b495475d2c52daf0d55105

source_sha256 =
5860bf8ab543253f32f52de74da6fb9be8263e3ff35ca4fb078e8c6a1af3fe25
```

State:

```text
QUALIFIED_CANDIDATE
```

---

# 16. Guardian rollback object

## `OBJ-GUARDRB201` — Guardian rollback identity

```text
class = PRODUCTION_RUNTIME

rollback_image =
sha256:c0600d72c450c6ce8849ead27e5289fd780f01469f35a158f0ac760a651d8d0b

rollback_tag =
allis-guardian-protected-remediation-step11c5g4d9o:20260919T151555Z
```

State:

```text
ROLLBACK_PRESERVED
```

---

# 17. Gateway rollback object

## `OBJ-GWRB201` — Gateway rollback runtime

```text
class = PRODUCTION_RUNTIME

name =
jarvis-unified-gateway.rollback-r20r4-20261003T011108Z-2966359

image =
sha256:d52c4a716d491158c66240251c7e158752c2c9afa0a03afaffd9ed747bf2107b
```

State:

```text
STOPPED_RETAINED
```

Retirement:

```text
AUTHORIZED=NO
```

---

# 18. Composite registry table

| ID | Object | Class | State |
|---|---|---|---|
| `OBJ-F01` | Workstream-F qualified baseline | `QUALIFIED_SOURCE` | CLOSED |
| `OBJ-A501` | A5 proof/source anchor | `PROOF_SOURCE_ANCHOR` | Qualified |
| `OBJ-D1201` | Step-12 DGM production source | `PRODUCTION_SOURCE` | Closed bounded source |
| `OBJ-LR101` | Lean R1 authorized-adoption qualification | `PROOF_ASSISTANT_QUALIFICATION` | CLOSED / PASS |
| `OBJ-LR201` | Lean R2 Conversational Admission | `PROOF_ASSISTANT_QUALIFICATION` | CLOSED / PASS |
| `OBJ-R2C01` | R2 source/runtime correspondence | `CORRESPONDENCE_REFERENCE_SET` | PASS |
| `OBJ-LR301` | Lean R3 Hilbert/JCP Separation | `PROOF_ASSISTANT_QUALIFICATION` | CLOSED / PASS |
| `OBJ-R3C01` | R3 source/runtime correspondence | `CORRESPONDENCE_REFERENCE_SET` | PASS |
| `OBJ-D12R01` | Post-A8 DGM correspondence | `CORRESPONDENCE_REFERENCE_SET` | PASS |
| `OBJ-D1202` | Step-12 public trust object | `TRUST_OBJECT` | PASS at final seal |
| `OBJ-D1203` | Step-12 governance view | `GOVERNANCE_OBJECT` | PASS at final seal |
| `OBJ-D1204` | Step-12 final seal | `EVIDENCE_SEAL` | GREEN closed with residuals |
| `OBJ-P1701` | Step-17 publication | `PUBLICATION_OBJECT` | GREEN complete |
| `OBJ-P1702` | Step-17 publication body | `PUBLICATION_OBJECT` | Correspondence PASS |
| `OBJ-P1703` | Historical Step-17 frontend build | `FRONTEND_BUILD` | Final Step-17 observation |
| `OBJ-AUTH201` | Current versioned auth/Guardian install | `QUALIFIED_SOURCE` | INSTALL_ONLY qualified |
| `OBJ-GUARD201` | Guardian registration-review candidate | `QUALIFIED_SOURCE` | Qualified candidate |
| `OBJ-GUARDRB201` | Guardian rollback object | `PRODUCTION_RUNTIME` | Preserved |
| `OBJ-FE201` | Current conversational frontend production build | `FRONTEND_BUILD` | Production cutover PASS |
| `OBJ-GW201` | Current Unified Gateway production runtime | `PRODUCTION_RUNTIME` | Production cutover PASS |
| `OBJ-GWRB201` | Gateway rollback runtime | `PRODUCTION_RUNTIME` | STOPPED_RETAINED |
| `OBJ-CS201` | Durable server/UI-boundary closeout | `EVIDENCE_SEAL` | Server-side qualified |

---

# 19. Explicit proof-assistant registry

The current first-class Lean objects are:

```text
OBJ-LR101 = R1 Authorized Production Adoption

OBJ-LR201 = R2 Conversational Admission

OBJ-LR301 = R3 Hilbert/JCP Separation
```

They are separate objects with separate scopes.

---

# 20. Proof totals

Current named principal-check count:

```text
R1 = 4

R2 = 6

R3 = 14

TOTAL = 24
```

Preserve:

```text
24 named principal checks
    ≠
whole-system theorem
```

---

# 21. R2/R3 successor relationship

The formal branch lineage is:

```text
R1
    ↓
R2
    ↓
R3
```

This lineage does not mean:

```text
R3 replaces R2
```

or:

```text
R2 replaces R1
```

Each remains independently meaningful within its bounded scope.

---

# 22. Correspondence objects remain separate

Preserve:

```text
OBJ-LR201
    ≠
OBJ-R2C01
```

and:

```text
OBJ-LR301
    ≠
OBJ-R3C01
```

Proof objects and correspondence objects answer different questions.

---

# 23. Historical frontend object remains historical

`OBJ-P1703` remains the historical Step-17 frontend build:

```text
5By6R3CWTM7NDXc-4lmSi
```

The current conversational frontend object is separately registered as:

```text
OBJ-FE201
```

with BUILD_ID:

```text
9KyheKDYXyNCclA1YrUAX
```

This prevents current frontend work from overwriting publication history.

---

# 24. Historical DGM identities remain controlling for their scopes

The following remain unchanged:

```text
OBJ-D1201
OBJ-D1202
OBJ-D1203
OBJ-D1204
OBJ-LR101
OBJ-D12R01
```

R2/R3 publication into the repository does not alter their identities.

---

# 25. Current nonadmission registry state

The current R3 correspondence preserves:

```text
H_GEO_CURRENT_JCP_ADMISSION=NO

H_P_CURRENT_JCP_ADMISSION=NO

H_PEOPLE_CURRENT_JCP_ADMISSION=NO
```

Static H_geo remains:

```text
STATIC_H_GEO_PATH_QUALIFIED=YES
```

---

# 26. Current browser boundary

The registry must not promote:

```text
server-side route qualified
```

into:

```text
browser E2E qualified
```

Current state:

```text
BROWSER_E2E_DEMONSTRATED=NO
```

---

# 27. Current future-work boundaries

Do not add qualified-object identities yet for workstreams that remain unqualified.

Current flags:

```text
H384_FORMALIZATION_COMPLETE=NO

COGNITION_THEOREM_FAMILY_COMPLETE=NO

AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED=NO

RESEARCH_TO_CORPUS_INGESTION_QUALIFIED=NO

KYC_LOCATION_CONTEXT_USE_QUALIFIED=NO

FULL_DGM_COMPLETION_CLAIMED=NO
```

These do not yet belong in the registry as closed qualified objects.

---

# 28. Object-admission rule

A future object should enter this registry only after it has an evidence-backed identity and bounded role.

Minimum rule:

```text
named object
+
qualified identity
+
bounded role
+
state
+
evidence reference
```

Architecture prose alone is insufficient.

---

# 29. Predecessor preservation rule

Never mutate an old identity merely because a newer object exists.

Use:

```text
OLD_OBJECT
    remains historical/current for its qualified scope

NEW_OBJECT
    added with new identity and role
```

Do not use:

```text
OLD_OBJECT identity silently changed to NEW_OBJECT
```

---

# 30. Normalized registry

```yaml
allis_baseline_object_registry:
  status: COMPOSITE

  proof_assistant_objects:
    - id: OBJ-LR101
      workstream: R1_AUTHORIZED_PRODUCTION_ADOPTION
      class: PROOF_ASSISTANT_QUALIFICATION
      qualified_proof_commit: 71ee78982c918145ca73850170a4c2a8a447170d
      metadata_head: beceb3ee44fd5c33eaf689a5abe086e5e9c67911
      tree: a62d4b78db5aae522fd06f61b9563e676eacc0a8
      state: CLOSED_PASS

    - id: OBJ-LR201
      workstream: R2_CONVERSATIONAL_ADMISSION
      class: PROOF_ASSISTANT_QUALIFICATION
      head: c1a18b2e5fbe2e288d8b91dafe18668392bc787d
      tree: e325bfdd78cd6903dbfb3a8c15130af26de5cd9f
      state: CLOSED_PASS
      principal_checks: 6
      proof_holes: 0
      final_theorem_level_axiom_dependencies: 0

    - id: OBJ-LR301
      workstream: R3_HILBERT_JCP_SEPARATION
      class: PROOF_ASSISTANT_QUALIFICATION
      head: 6f4a7de303e2d80c3d94a28a8d82e696387bf4b2
      tree: f5ffcb3fd693cbed60c1bd9dc966f868472707d4
      state: CLOSED_PASS
      principal_checks: 14
      proof_holes: 0
      final_theorem_level_axiom_dependencies: 0

  correspondence_objects:
    - id: OBJ-R2C01
      class: CORRESPONDENCE_REFERENCE_SET
      role: conversational_admission_r2_source_runtime
      state: PASS

    - id: OBJ-R3C01
      class: CORRESPONDENCE_REFERENCE_SET
      role: hilbert_jcp_separation_r3_source_runtime
      state: PASS
      jcp_ast_sha256: 7c9cc765677848685066884c47d7ef8c2adf49a5ee4c6ec32da0492f7ef0b422

    - id: OBJ-D12R01
      class: CORRESPONDENCE_REFERENCE_SET
      identity: POST_A8_DGM_THEOREM_CORRESPONDENCE_REGISTRY_R1
      state: PASS

  current_runtime_objects:
    - id: OBJ-AUTH201
      role: versioned_auth_guardian_install
      state: INSTALL_ONLY_QUALIFIED

    - id: OBJ-GUARD201
      role: guardian_registration_review_candidate
      state: QUALIFIED_CANDIDATE

    - id: OBJ-GUARDRB201
      role: guardian_rollback
      state: PRESERVED

    - id: OBJ-FE201
      role: current_conversational_frontend
      build_id: 9KyheKDYXyNCclA1YrUAX
      state: PRODUCTION_CUTOVER_PASS

    - id: OBJ-GW201
      role: current_unified_gateway
      source_sha256: a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f
      state: PRODUCTION_CUTOVER_PASS

    - id: OBJ-GWRB201
      role: gateway_rollback
      state: STOPPED_RETAINED

    - id: OBJ-CS201
      role: durable_server_ui_boundary_closeout
      state: SERVER_SIDE_QUALIFIED

  current_boundaries:
    browser_e2e_demonstrated: false
    H_geo_current_jcp_admission: false
    H_p_current_jcp_admission: false
    H_people_current_jcp_admission: false
    H384_formalization_complete: false
    cognition_theorem_family_complete: false
    automated_learning_web_research_qualified: false
    research_to_corpus_ingestion_qualified: false
    kyc_location_context_use_qualified: false
    full_dgm_completion_claimed: false
    system_proven: false
```

---

# 31. Final registry statement

```text
BASELINE_OBJECT_REGISTRY=UPDATED

PREDECESSOR_IDENTITIES_REWRITTEN=NO

LEAN_R1_FIRST_CLASS_OBJECT=YES

LEAN_R2_FIRST_CLASS_OBJECT=YES

LEAN_R3_FIRST_CLASS_OBJECT=YES

R2_SOURCE_RUNTIME_CORRESPONDENCE_OBJECT=YES

R3_SOURCE_RUNTIME_CORRESPONDENCE_OBJECT=YES

CURRENT_FRONTEND_OBJECT_ADDED=YES

CURRENT_GATEWAY_OBJECT_ADDED=YES

AUTH_GUARDIAN_OBJECTS_ADDED=YES

ROLLBACK_OBJECTS_PRESERVED=YES

BROWSER_E2E_DEMONSTRATED=NO

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **The baseline registry is additive.**

> **R2 and R3 are new first-class qualified objects; they do not rewrite R1.**

> **Correspondence objects are separate from proof objects.**

> **Historical Step-12, publication, trust, governance, and frontend identities remain unchanged.**

> **The current conversational frontend is a new object rather than a rewrite of the historical Step-17 frontend.**

> **Current Gateway and rollback identities are registered independently.**

> **Objects enter the registry only after they have an evidence-backed identity and bounded role.**

> **Future unqualified workstreams remain roadmap items rather than qualified registry objects.**

> **SYSTEM_PROVEN remains NO.**
