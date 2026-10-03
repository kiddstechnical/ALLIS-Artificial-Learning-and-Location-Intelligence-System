<div align="center">

# ALLIS — Lean R2 Conversational Admission Closeout

### Public technical closeout for authenticated ordinary-conversation admission, identity isolation, authority non-escalation, and H_people SECRET-disclosure boundaries

<br>

![Workstream](https://img.shields.io/badge/WORKSTREAM-LEAN_R2_CONVERSATIONAL_ADMISSION-2563eb?style=for-the-badge)
![Lean](https://img.shields.io/badge/LEAN-4.34.0-7c3aed?style=for-the-badge)
![Kernel](https://img.shields.io/badge/PRINCIPAL_THEOREMS-6_OF_6-22c55e?style=for-the-badge)
![Proof Holes](https://img.shields.io/badge/PROOF_HOLES-0-22c55e?style=for-the-badge)
![Axioms](https://img.shields.io/badge/THEOREM_LEVEL_AXIOMS-0_OF_6-22c55e?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This closeout records a **bounded Lean proof workstream** for ordinary authenticated conversational admission.
>
> It does **not** claim that Lean proves the whole ALLIS system, that every future authentication implementation is correct, that every frontend is secure, that all private-state behavior is proven, or that production/runtime correspondence follows automatically from theorem proof.
>
> The controlling distinction remains:
>
> ```text
> formal theorem
>     ≠
> model-to-source correspondence
>     ≠
> source-to-runtime correspondence
>     ≠
> live observation
>     ≠
> operational authority
> ```

---

# 1. Closeout status

```text
WORKSTREAM=LEAN_CONVERSATIONAL_ADMISSION_R2
STATUS=CLOSED
RESULT=PASS

LEAN_VERSION=4.34.0

PRINCIPAL_THEOREMS=6
KERNEL_CHECKED_PRINCIPAL_THEOREMS=6_OF_6

PROOF_HOLES=0

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

PROPEXT_DEPENDENCY_REMOVED=PASS

SYSTEM_PROVEN=NO
PRODUCTION_AUTHORITY_CREATED_BY_THIS_WORKSTREAM=NO
```

The R2 workstream closed as a separate successor formal domain after the already-closed Lean R1 authorized-adoption workstream.

R1 was preserved as its parent rather than rewritten.

---

# 2. Purpose

R2 formalizes the admission boundary for **ordinary authenticated conversation**.

Its purpose is not to prove model intelligence, prose quality, or whole-system safety.

Its purpose is to establish six narrower properties:

```text
authenticated identity
    comes from
server-side authenticated session

browser-controlled body
    does not become
identity authority

missing canonical scalar user ID
    does not become
invented canonical user ID

distinct authenticated sessions
    remain
identity-isolated

ordinary authenticated conversation
    does not create
governance authority

ordinary authenticated conversation
    does not authorize
H_people SECRET disclosure
```

This is a separate formal domain from DGM authorized adoption.

---

# 3. R2 domain boundary

The bounded R2 model covers:

- authenticated server-side session state;
- browser-controlled ordinary-chat request body;
- server-derived conversational identity;
- optional canonical scalar user identity;
- ordinary-chat authority state;
- H_people SECRET-disclosure authority.

The initial R2 scope explicitly excluded:

- language-model factual correctness;
- quality of generated prose;
- whole-system safety;
- arbitrary code-execution safety;
- cryptographic primitive correctness;
- governance-instrument authenticity;
- legal-process authenticity;
- browser UX;
- production source correspondence;
- production runtime correspondence.

Those exclusions remain important to interpreting the result.

---

# 4. R2 theorem family

R2 contains six principal theorems.

They are preserved individually because each protects a different trust boundary.

## 4.1 TCHAT-A — server-derived authenticated identity

```text
TCHAT_A_server_derived_authenticated_identity
```

Semantic reading:

> For an authenticated session, ordinary-chat admission derives the admitted `authenticatedUser` from the authenticated server-side session identity.

Formally, the admitted trusted identity does not originate from browser-controlled message content.

Security meaning:

```text
authenticated session identity
    =
trusted conversational identity source
```

and:

```text
browser body identity-like content
    ≠
trusted identity source
```

---

## 4.2 TCHAT-B — browser identity is non-authoritative

```text
TCHAT_B_browser_identity_is_nonauthoritative
```

Semantic reading:

> For one authenticated session, changing browser-controlled body content does not change the admitted authenticated user.

Security meaning:

```text
browser body changes
    ≠
authenticated identity changes
```

The browser cannot choose or overwrite the trusted conversational identity merely by supplying identity-like request content.

---

## 4.3 TCHAT-C — canonical scalar user ID is not invented

```text
TCHAT_C_canonical_scalar_user_id_not_invented
```

Semantic reading:

> If the authenticated session has no canonical scalar user ID, ordinary-chat admission preserves that absence.

Security meaning:

```text
session.canonicalUserId = none
    ⇒
admitted canonicalUserId = none
```

R2 therefore forbids inventing a scalar identity merely to satisfy an expected shape.

---

## 4.4 TCHAT-D — authenticated sessions remain identity-isolated

```text
TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
```

Semantic reading:

> Distinct authenticated session identities yield distinct admitted authenticated-user values.

Security meaning:

```text
session A identity
    ≠
session B identity

therefore

admitted identity A
    ≠
admitted identity B
```

This theorem formalizes the bounded identity-isolation property for the R2 admission model.

---

## 4.5 TCHAT-E — ordinary chat does not create governance authority

```text
TCHAT_E_ordinary_chat_does_not_create_governance_authority
```

Semantic reading:

> Authenticated ordinary-chat admission carries `noAuthority`.

Security meaning:

```text
authenticated conversation
    ≠
governance authorization
```

Authentication permits ordinary conversational admission within scope.

It does not mint protected transition authority.

---

## 4.6 TCHAT-F — ordinary chat does not authorize H_people SECRET disclosure

```text
TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

Semantic reading:

> Authenticated ordinary-chat admission does not set H_people SECRET-disclosure authority.

Security meaning:

```text
ordinary authenticated chat
    ≠
H_people SECRET disclosure authority
```

Protected person-linked SECRET disclosure remains a separately governed transition.

---

# 5. Principal theorem disposition

| ID | Lean theorem | Final result | Proof holes | Final theorem-level axiom dependency |
|---|---|---|---:|---:|
| TCHAT-A | `TCHAT_A_server_derived_authenticated_identity` | PASS | 0 | none |
| TCHAT-B | `TCHAT_B_browser_identity_is_nonauthoritative` | PASS | 0 | none |
| TCHAT-C | `TCHAT_C_canonical_scalar_user_id_not_invented` | PASS | 0 | none |
| TCHAT-D | `TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated` | PASS | 0 | none |
| TCHAT-E | `TCHAT_E_ordinary_chat_does_not_create_governance_authority` | PASS | 0 | none |
| TCHAT-F | `TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure` | PASS | 0 | none |

Final aggregate:

```text
KERNEL_CHECKED_PRINCIPAL_THEOREMS=6_OF_6
PROOF_HOLES=0
THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6
```

---

# 6. Lean toolchain

The qualified workstream used:

```text
leanprover/lean4:v4.34.0
```

The workstream completed a clean Lean project build with:

```text
LEAN_CLEAN_BUILD=PASS
BUILD_JOBS=27
```

The R1 and R2 modules were built together during the qualified R2 project build.

---

# 7. Proof-hole discipline

R2 closed with:

```text
sorry = 0
admit = 0
proof holes = 0
```

The workstream did not treat a successful compile as sufficient qualification.

The qualification process separately checked:

```text
build
proof holes
principal theorem kernel acceptance
#print axioms
source identity
evidence sealing
```

---

# 8. The propext qualification failure

The first complete R2 proof form compiled successfully.

That was **not** enough to qualify it.

Initial R2 state:

```text
BUILD=PASS
PROOF_HOLES=0
PRINCIPAL_THEOREMS_COMPILED=6_OF_6
THEOREMS_WITH_PROPEXT_DEPENDENCY=6_OF_6
QUALIFICATION=FAIL
```

All six principal theorems reported a theorem-level dependency on:

```text
propext
```

The project treated that dependency as a real qualification failure rather than ignoring it because the code compiled.

This distinction is central:

```text
Lean elaboration succeeds
    ≠
project axiom qualification passes
```

---

# 9. Direct-proof repair

The repair did not weaken the R2 claims.

For R2, the theorem statements were preserved while the proof construction changed.

The repair:

- preserved all six theorem statements;
- preserved theorem types;
- preserved theorem semantics;
- preserved `Types.lean`;
- preserved `Semantics.lean`;
- changed the six proof bodies;
- replaced the proof construction that induced `propext`;
- used more direct unfolding, rewriting, and equality reasoning;
- reran build, hole, and axiom checks.

Final repaired state:

```text
BUILD=PASS
PROOF_HOLES=0
PRINCIPAL_THEOREMS=6_OF_6
THEOREMS_WITH_PROPEXT_DEPENDENCY=0_OF_6
FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6
QUALIFICATION=PASS
```

The R2 repair therefore demonstrates why the project distinguishes:

```text
theorem statement
    ≠
proof body
    ≠
axiom dependency
```

---

# 10. R2 Git lineage

R2 was created as a successor workstream from the closed R1 lineage.

The parent R1 workstream was not mutated.

## Parent R1

```text
branch = formal-verification/lean-authorized-adoption-r1

HEAD =
beceb3ee44fd5c33eaf689a5abe086e5e9c67911

tree =
a62d4b78db5aae522fd06f61b9563e676eacc0a8
```

## Closed R2

```text
branch =
formal-verification/lean-conversational-admission-r2

HEAD =
c1a18b2e5fbe2e288d8b91dafe18668392bc787d

tree =
e325bfdd78cd6903dbfb3a8c15130af26de5cd9f
```

Relationship:

```text
closed R1
    ↓
new R2 worktree / branch
    ↓
R2 formal domain
    ↓
R2 qualification
    ↓
closed R2
```

This preserves historical evidence lineage instead of rewriting the predecessor workstream.

---

# 11. R2 source/evidence package

The qualified R2 evidence directory was:

```text
conversational-admission-r2-axiom-free-r1-20261002T215319Z
```

The final retained identities are:

## Evidence manifest

```text
fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229
```

## Status record

```text
38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898
```

## Lean source manifest

```text
21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b
```

## R19L2R1 final result

```text
ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30
```

## R19L2R1 manifest

```text
7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf
```

These identities bind the public closeout to the retained qualification record without requiring the public repository to reproduce private/local raw evidence.

---

# 12. Evidence-method boundary

The R2 formal closeout intentionally separated proof qualification from implementation correspondence.

At the initial axiom-free R2 seal:

```text
LEAN_TO_CURRENT_SOURCE_CORRESPONDENCE
    =
NOT_YET_ESTABLISHED

LEAN_TO_CURRENT_RUNTIME_CORRESPONDENCE
    =
NOT_YET_ESTABLISHED
```

That was correct.

The theorem layer answered:

```text
Does the formal R2 model prove the six stated admission properties?
```

It did not answer:

```text
Does every current or future frontend/runtime exactly implement that model?
```

That second question belongs to correspondence.

---

# 13. Later correspondence relevant to R2 semantics

Subsequent frontend/Gateway qualification strengthened the implementation interpretation of R2 without changing the theorem layer.

Later bounded evidence established that the deployed `/api/chat` path:

- authenticates before accepting browser JSON as application content;
- constructs `authenticated_user` server-side;
- carries `user_id: null` in the bounded qualified path;
- passes the authenticated-user object into the qualified Gateway candidate;
- does not cause `process_unified` to read that identity object;
- does not forward that identity object downstream;
- does not insert it into JCP;
- does not make it model input;
- does not create governance authority;
- does not create H_people SECRET-disclosure authority.

Isolated runtime qualification also withheld private-memory/H_people material and confirmed that authenticated-user identity material was absent from ensemble and synthesizer inputs in the bounded observation.

Those are **correspondence/implementation facts**, not additional R2 theorems.

---

# 14. What R2 establishes

The strongest safe R2 statements are:

```text
LEAN_R2_CONVERSATIONAL_ADMISSION_QUALIFIED=YES

TCHAT_A=PASS
TCHAT_B=PASS
TCHAT_C=PASS
TCHAT_D=PASS
TCHAT_E=PASS
TCHAT_F=PASS

LEAN_VERSION=4.34.0
KERNEL_CHECKED_PRINCIPAL_THEOREMS=6_OF_6
PROOF_HOLES=0
FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

SERVER_DERIVED_AUTHENTICATED_IDENTITY=PROVEN_IN_R2_MODEL
BROWSER_IDENTITY_NONAUTHORITY=PROVEN_IN_R2_MODEL
CANONICAL_SCALAR_USER_ID_NOT_INVENTED=PROVEN_IN_R2_MODEL
SESSION_IDENTITY_ISOLATION=PROVEN_IN_R2_MODEL
ORDINARY_CHAT_CREATES_GOVERNANCE_AUTHORITY=NO
ORDINARY_CHAT_AUTHORIZES_HPEOPLE_SECRET_DISCLOSURE=NO
```

---

# 15. What R2 does not establish

R2 does **not** prove:

```text
EVERY_FUTURE_FRONTEND_SECURE=YES
```

It does not prove:

```text
EVERY_AUTHENTICATION_IMPLEMENTATION_CORRECT=YES
```

It does not prove:

```text
WHOLE_SYSTEM_IDENTITY_SAFE=YES
```

It does not prove:

```text
HPEOPLE_WHOLE_DOMAIN_PROVEN=YES
```

It does not prove:

```text
MODEL_FACTUAL_CORRECTNESS=YES
```

It does not prove:

```text
MODEL_PROSE_QUALITY=YES
```

It does not prove:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=YES
```

It does not prove:

```text
SYSTEM_PROVEN=YES
```

It does not establish operational authority.

It does not authorize deployment.

It does not authorize a protected disclosure.

It does not authorize a governed write.

It does not authorize a future source change to inherit old correspondence.

---

# 16. Correspondence must be re-earned

R2 proof validity is stable with respect to the exact qualified formal object.

Implementation correspondence is not perpetual.

For a changed frontend, changed server-auth implementation, changed Gateway contract, changed conversational schema, or changed private-state path:

```text
prior R2 theorem validity
    remains theorem validity
```

but:

```text
prior implementation correspondence
    ≠
automatic new implementation correspondence
```

Therefore:

> **Correspondence must be re-earned for the implementation/runtime under review.**

---

# 17. Authority boundary

R2 does not collapse identity into authority.

The governing relations are:

```text
authenticated identity
    ≠
governance authority
```

```text
ordinary chat
    ≠
protected disclosure authority
```

```text
formal proof
    ≠
production authority
```

```text
proof workstream closed
    ≠
successor production change authorized
```

This preserves the same architectural discipline used elsewhere in ALLIS:

> **State does not become authority merely because it exists.**

---

# 18. Relationship to H_people

R2 addresses one narrow H_people boundary:

```text
ordinary authenticated chat
    does not authorize
H_people SECRET disclosure
```

R2 does not redefine the full H_people architecture.

It does not convert H_people SECRET state into ordinary chat state.

It does not establish general H_people runtime correspondence.

It does not supersede the separate H_people privacy, disclosure, retention, and legal-process boundaries.

The R2 theorem therefore means:

```text
authentication alone
    ≠
SECRET disclosure authority
```

not:

```text
H_people is fully formalized by R2
```

---

# 19. Relationship to later R3

R2 and R3 are separate formal workstreams.

```text
R2
    =
Conversational Admission
```

```text
R3
    =
Hilbert / JCP Separation
```

R2 proves ordinary-chat identity and authority boundaries.

R3 later proves the current JCP/Hilbert separation and current nonadmission state.

Neither should be silently folded into the other.

---

# 20. Public claim boundary

The public repository may safely state:

> **Lean R2 Conversational Admission is a closed, qualified Lean 4.34.0 workstream containing six principal kernel-checked theorems, zero proof holes, and zero final theorem-level axiom dependencies. It formalizes server-derived conversational identity, browser identity non-authority, non-invention of a missing canonical scalar user ID, authenticated-session identity isolation, absence of governance authority in ordinary chat, and absence of H_people SECRET-disclosure authority in ordinary chat.**

The public repository should also state immediately:

> **R2 is bounded. It does not prove whole-system safety, every authentication implementation, every future frontend, complete H_people behavior, or automatic source/runtime correspondence.**

---

# 21. Compact closeout matrix

| Dimension | Final R2 state |
|---|---|
| Workstream | Lean R2 Conversational Admission |
| Lean version | 4.34.0 |
| Principal theorems | 6 |
| Principal kernel checks | 6 / 6 PASS |
| Proof holes | 0 |
| Final theorem-level axiom dependencies | 0 / 6 |
| Initial `propext` dependencies | 6 / 6 |
| Final `propext` dependencies | 0 / 6 |
| Clean build | PASS |
| Build jobs | 27 |
| Parent | Closed Lean R1 |
| Parent mutated | NO |
| R2 HEAD | `c1a18b2e5fbe2e288d8b91dafe18668392bc787d` |
| R2 tree | `e325bfdd78cd6903dbfb3a8c15130af26de5cd9f` |
| Production authority created | NO |
| Whole-system proof | NO |
| System proven | NO |

---

# 22. Normalized closeout record

```yaml
lean_r2_conversational_admission:
  status: CLOSED
  result: PASS

  domain:
    name: AUTHENTICATED_ORDINARY_CONVERSATION_ADMISSION
    whole_system: false

  toolchain:
    lean: "4.34.0"
    toolchain: "leanprover/lean4:v4.34.0"

  parent:
    workstream: LEAN_AUTHORIZED_ADOPTION_R1
    branch: formal-verification/lean-authorized-adoption-r1
    head: beceb3ee44fd5c33eaf689a5abe086e5e9c67911
    tree: a62d4b78db5aae522fd06f61b9563e676eacc0a8
    mutated_by_r2: false

  git:
    branch: formal-verification/lean-conversational-admission-r2
    head: c1a18b2e5fbe2e288d8b91dafe18668392bc787d
    tree: e325bfdd78cd6903dbfb3a8c15130af26de5cd9f

  principal_theorems:
    TCHAT_A:
      theorem: TCHAT_A_server_derived_authenticated_identity
      result: PASS
    TCHAT_B:
      theorem: TCHAT_B_browser_identity_is_nonauthoritative
      result: PASS
    TCHAT_C:
      theorem: TCHAT_C_canonical_scalar_user_id_not_invented
      result: PASS
    TCHAT_D:
      theorem: TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
      result: PASS
    TCHAT_E:
      theorem: TCHAT_E_ordinary_chat_does_not_create_governance_authority
      result: PASS
    TCHAT_F:
      theorem: TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
      result: PASS

  qualification:
    lean_clean_build: PASS
    build_jobs: 27
    kernel_checked_principal_theorems: "6/6"
    proof_holes: 0
    initial_propext_dependent_theorems: "6/6"
    final_propext_dependent_theorems: "0/6"
    final_theorem_level_axiom_dependencies: "0/6"

  evidence:
    directory: conversational-admission-r2-axiom-free-r1-20261002T215319Z
    manifest_sha256: fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229
    status_sha256: 38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898
    source_manifest_sha256: 21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b
    r19l2r1_final_sha256: ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30
    r19l2r1_manifest_sha256: 7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf

  claim_limits:
    every_future_frontend_secure: false
    every_authentication_implementation_correct: false
    whole_system_identity_safe: false
    hpeople_whole_domain_proven: false
    model_factual_correctness_proven: false
    model_prose_quality_proven: false
    whole_system_safety_proven: false
    production_authority_created: false
    system_proven: false

  correspondence:
    proof_layer_separate_from_model_to_source: true
    model_to_source_separate_from_source_to_runtime: true
    source_to_runtime_separate_from_live_observation: true
    correspondence_must_be_reearned_after_claim_bearing_change: true

  authority:
    authenticated_identity_is_governance_authority: false
    ordinary_chat_authorizes_hpeople_secret_disclosure: false
    formal_proof_is_production_authority: false
```

---

# 23. Final closeout statement

```text
LEAN_R2_CONVERSATIONAL_ADMISSION_QUALIFIED=YES

TCHAT_A_THROUGH_TCHAT_F=KERNEL_CHECKED_PASS

LEAN_VERSION=4.34.0

LEAN_CLEAN_BUILD=PASS

PROOF_HOLES=0

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

PROPEXT_DEPENDENCY_REMOVED=PASS

R1_PARENT_PRESERVED=YES

R2_GIT_IDENTITY=SEALED

R2_EVIDENCE_IDENTITY=SEALED

FORMAL_PROOF_EQUALS_PRODUCTION_AUTHORITY=NO

LEAN_TO_RUNTIME_CORRESPONDENCE_AUTOMATIC=NO

SYSTEM_PROVEN=NO

WORKSTREAM_R2=CLOSED_PASS
```

---

# Governing principles

> **Authenticated identity is not governance authority.**

> **Browser-controlled identity content is not trusted identity authority.**

> **A missing canonical scalar user ID is not permission to invent one.**

> **Distinct authenticated sessions must remain identity-isolated.**

> **Ordinary authenticated conversation does not authorize H_people SECRET disclosure.**

> **A clean build is not enough when theorem-level axiom dependencies remain.**

> **Formal proof does not create production authority.**

> **Correspondence must be established separately and re-earned when claim-bearing implementation state changes.**

> **SYSTEM_PROVEN remains NO.**
