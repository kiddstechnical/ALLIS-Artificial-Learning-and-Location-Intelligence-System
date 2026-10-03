<div align="center">

# ALLIS — Conversational Admission R2 Qualification Evidence

### Public-safe evidence package for the Lean R2 Conversational Admission workstream

<br>

![Workstream](https://img.shields.io/badge/WORKSTREAM-LEAN_R2_CONVERSATIONAL_ADMISSION-7c3aed?style=for-the-badge)
![Lean](https://img.shields.io/badge/LEAN-4.34.0-2563eb?style=for-the-badge)
![Checks](https://img.shields.io/badge/PRINCIPAL_CHECKS-6_OF_6-22c55e?style=for-the-badge)
![Proof Holes](https://img.shields.io/badge/PROOF_HOLES-0-22c55e?style=for-the-badge)
![Axioms](https://img.shields.io/badge/THEOREM_LEVEL_AXIOMS-0_OF_6-22c55e?style=for-the-badge)
![Status](https://img.shields.io/badge/QUALIFICATION-PASS-22c55e?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document is a **public-safe evidence package** for the qualified Lean R2 Conversational Admission workstream.
>
> It preserves:
>
> - final proof metrics;
> - exact theorem identifiers;
> - parent and R2 Git identities;
> - the initial `propext` dependency failure;
> - the proof repair;
> - theorem-statement/type/semantic preservation;
> - evidence/source manifest identities;
> - final qualification seals;
> - and bounded claim limits.
>
> It does **not** claim whole-system proof, production authority, or permanent implementation correspondence.

---

# 1. Workstream identity

```text
WORKSTREAM=LEAN_CONVERSATIONAL_ADMISSION_R2

STATUS=QUALIFIED

RESULT=PASS

LEAN_VERSION=4.34.0
```

The workstream formalizes the ordinary authenticated conversational-admission boundary.

---

# 2. Formal scope

The R2 domain establishes bounded properties around:

```text
server-derived authenticated identity

browser identity non-authority

non-invention of canonical scalar user ID

session identity isolation

ordinary chat non-creation of governance authority

ordinary chat non-authorization of H_people SECRET disclosure
```

It is not a whole-system theorem.

---

# 3. Principal theorem family

The six exact principal theorem identifiers are:

```text
TCHAT_A_server_derived_authenticated_identity

TCHAT_B_browser_identity_is_nonauthoritative

TCHAT_C_canonical_scalar_user_id_not_invented

TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated

TCHAT_E_ordinary_chat_does_not_create_governance_authority

TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

These identifiers are preserved as the public R2 theorem family.

---

# 4. Final proof metrics

Final qualification metrics:

```text
PRINCIPAL_THEOREMS=6

KERNEL_CHECKED=6_OF_6

PROOF_HOLES=0

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

FINAL_PROPEXT_DEPENDENCIES=0_OF_6

LEAN_BUILD_JOBS=27
```

The final workstream passed qualification.

---

# 5. Initial qualification state

The initial R2 formalization reached:

```text
COMPILED_THEOREMS=6_OF_6

PROOF_HOLES=0
```

but all six principal theorems reported theorem-level dependency on:

```text
propext
```

Therefore the initial state was not accepted as final qualification.

Record:

```text
INITIAL_PROPEXT_DEPENDENCIES=6_OF_6

INITIAL_QUALIFICATION=FAIL
```

---

# 6. Why the initial result failed

A clean compile was not treated as sufficient.

The workstream required inspection of theorem-level axiom dependencies.

The presence of unexpected `propext` dependency meant:

```text
compiled
    ≠
qualified
```

This became an important qualification precedent for later Lean work.

---

# 7. Proof repair

The six proof bodies were repaired directly.

The repair removed the unexpected theorem-level `propext` dependency.

Final state:

```text
FINAL_PROPEXT_DEPENDENCIES=0_OF_6

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6
```

---

# 8. Theorem preservation across the repair

The repair was intentionally bounded.

Preserve:

```text
THEOREM_STATEMENTS_PRESERVED=YES

THEOREM_TYPES_PRESERVED=YES

THEOREM_SEMANTICS_PRESERVED=YES
```

The workstream did not qualify a different architectural claim merely to eliminate `propext`.

---

# 9. Source-model preservation

The following formal source layers were preserved through the repair:

```text
Types.lean

Semantics.lean
```

The qualification change was in the proof construction for the six principal theorems.

This distinction matters:

```text
proof body changed
    ≠
formal claim changed
```

---

# 10. Final proof-state summary

```text
INITIAL:
  6/6 compile
  0 holes
  6/6 propext
  qualification = FAIL

REPAIR:
  theorem statements preserved
  theorem types preserved
  theorem semantics preserved
  proof bodies changed

FINAL:
  6/6 kernel checked
  0 holes
  0/6 propext
  0/6 theorem-level axiom dependencies
  qualification = PASS
```

---

# 11. Parent R1 Git identity

R2 was based on the qualified R1 authorized-adoption workstream.

Parent branch:

```text
formal-verification/lean-authorized-adoption-r1
```

Parent HEAD:

```text
beceb3ee44fd5c33eaf689a5abe086e5e9c67911
```

Parent tree:

```text
a62d4b78db5aae522fd06f61b9563e676eacc0a8
```

---

# 12. R2 Git identity

R2 branch:

```text
formal-verification/lean-conversational-admission-r2
```

R2 HEAD:

```text
c1a18b2e5fbe2e288d8b91dafe18668392bc787d
```

R2 tree:

```text
e325bfdd78cd6903dbfb3a8c15130af26de5cd9f
```

These identities define the qualified R2 source state.

---

# 13. Toolchain identity

Pinned Lean version:

```text
Lean 4.34.0
```

Pinned Lean commit:

```text
293d5d0c0c3f3dded4688b3ccd6a33939ac5102b
```

The qualification should be interpreted against that toolchain identity.

---

# 14. Evidence directory

The final axiom-free R2 evidence directory is:

```text
conversational-admission-r2-axiom-free-r1-20261002T215319Z
```

This is the sealed evidence package for the final qualification state.

---

# 15. Evidence manifest identity

Final evidence manifest SHA-256:

```text
fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229
```

Interpretation:

```text
EVIDENCE_MANIFEST_SHA256=
fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229
```

---

# 16. Status file identity

Final qualification status SHA-256:

```text
38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898
```

Interpretation:

```text
STATUS_SHA256=
38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898
```

---

# 17. Source manifest identity

Final source manifest SHA-256:

```text
21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b
```

Interpretation:

```text
SOURCE_MANIFEST_SHA256=
21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b
```

---

# 18. R19L2R1 final identity

Final R19L2R1 closeout/result SHA-256:

```text
ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30
```

Interpretation:

```text
R19L2R1_FINAL_SHA256=
ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30
```

---

# 19. R19L2R1 manifest identity

R19L2R1 manifest SHA-256:

```text
7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf
```

Interpretation:

```text
R19L2R1_MANIFEST_SHA256=
7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf
```

---

# 20. Final seal summary

The public-safe final seal identities are:

```text
EVIDENCE_MANIFEST_SHA256
fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229

STATUS_SHA256
38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898

SOURCE_MANIFEST_SHA256
21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b

R19L2R1_FINAL_SHA256
ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30

R19L2R1_MANIFEST_SHA256
7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf
```

---

# 21. Formal claim A

```text
TCHAT_A_server_derived_authenticated_identity
```

Bounded meaning:

```text
trusted conversational identity is derived from authenticated server-side state
```

It does not establish all future authentication implementations.

---

# 22. Formal claim B

```text
TCHAT_B_browser_identity_is_nonauthoritative
```

Bounded meaning:

```text
browser-supplied identity-like content does not become trusted identity authority
```

It does not prohibit the browser from supplying ordinary conversational content.

---

# 23. Formal claim C

```text
TCHAT_C_canonical_scalar_user_id_not_invented
```

Bounded meaning:

```text
where no canonical scalar user ID is established,
the system does not invent one
```

The qualified implementation correspondence later preserved:

```text
user_id: null
```

for the bounded route.

---

# 24. Formal claim D

```text
TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
```

Bounded meaning:

```text
distinct authenticated sessions remain identity-isolated
```

This is a conversational identity-separation claim.

It is not a whole-system privacy theorem.

---

# 25. Formal claim E

```text
TCHAT_E_ordinary_chat_does_not_create_governance_authority
```

Bounded meaning:

```text
ordinary authenticated conversation
    ≠
governance authority
```

This is a permanent architecture distinction.

---

# 26. Formal claim F

```text
TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

Bounded meaning:

```text
ordinary authenticated conversation
    ≠
H_people SECRET disclosure authority
```

Authentication does not collapse the H_people SECRET boundary.

---

# 27. Proof holes

Final evidence records:

```text
PROOF_HOLES=0
```

The qualification discipline required no unresolved theorem placeholders in the principal R2 proof family.

---

# 28. Axiom review

The final theorem-level axiom review records:

```text
0_OF_6
```

unexpected theorem-level dependencies.

This is stronger than:

```text
the files compiled
```

and is why the final axiom-free evidence package is the controlling R2 proof state.

---

# 29. Propext history must remain visible

Do not erase the failed intermediate state from the public record.

The correct chronology is:

```text
initial proof family
    ↓
6/6 compiled
    ↓
0 proof holes
    ↓
6/6 propext dependency discovered
    ↓
qualification failed
    ↓
proof repair
    ↓
0/6 propext
    ↓
qualification passed
```

The failure is evidence of the qualification discipline working as intended.

---

# 30. Theorem-statement preservation must remain visible

The public record should also preserve:

```text
the theorem family was repaired
without changing the intended theorem statements/types/semantics
```

This avoids the misleading interpretation:

```text
"the proof was fixed by weakening the claim"
```

That is not the recorded R2 outcome.

---

# 31. Formal evidence vs implementation evidence

The final Lean proof seal establishes the bounded formal domain.

It does not itself prove:

```text
deployed /api/chat source correspondence

Gateway source correspondence

runtime source identity

live request/response behavior
```

Those belong to separate correspondence evidence.

---

# 32. Later source correspondence

Later source qualification established a bounded correspondence to:

```text
app/api/chat/route.js

lib/server-auth.js

app/ask/ConversationClient.jsx

app/ask/layout.js

Unified Gateway ChatPayload

process_unified
```

Those source objects support implementation correspondence.

They are not part of the Lean proof itself.

---

# 33. Later authenticated-user correspondence

Later correspondence established that the deployed conversational path:

```text
authenticates before browser JSON is accepted

constructs authenticated_user server-side

preserves user_id: null
```

for the bounded qualified route.

This supports the R2 model-to-source mapping.

---

# 34. Gateway identity carriage

Later Gateway source correspondence established that:

```text
authenticated_user
```

is accepted in the bounded request payload.

The qualified path did not use that object to create authority.

---

# 35. `process_unified` bounded behavior

The later qualified Gateway source established:

```text
process_unified
    accepts authenticated_user
```

while:

```text
process_unified
    does not read authenticated_user
```

and the object was not forwarded downstream as model content in the qualified path.

---

# 36. JCP boundary

The authenticated-user object did not become current JCP content under the qualified route.

This helps preserve:

```text
identity metadata
    ≠
reasoning context
```

and:

```text
identity metadata
    ≠
authority
```

---

# 37. H_people runtime correspondence

The bounded isolated-runtime qualification withheld private memory/H_people state from the ordinary conversational path and did not place authenticated-user identity into ensemble/synthesizer model inputs.

This supports the R2 SECRET-disclosure nonauthority claim.

It does not prove every possible H_people path.

---

# 38. Correspondence is point-in-time

Preserve:

```text
qualified source correspondence
    =
point-in-time evidence
```

A future route/auth/Gateway implementation must re-earn correspondence.

---

# 39. R2 does not prove every future frontend

R2 does not establish:

```text
EVERY_FUTURE_FRONTEND_IDENTITY_SAFE=YES
```

A future frontend or route change must preserve the same source-side identity semantics.

---

# 40. R2 does not prove every future auth implementation

R2 does not establish:

```text
EVERY_FUTURE_AUTH_IMPLEMENTATION_SAFE=YES
```

Authentication implementation changes require renewed correspondence.

---

# 41. R2 does not prove full-system privacy

R2 is not:

```text
WHOLE_SYSTEM_PRIVACY_THEOREM
```

It is a bounded conversational-admission theorem family.

---

# 42. R2 does not grant production mutation authority

The proof work does not authorize:

```text
production mutation

service restart

deployment

DGM adoption

publication
```

Formal proof is not operational authority.

---

# 43. R2 does not prove browser UI totality

The theorem family does not prove:

```text
every browser conversational UI state
```

or:

```text
authenticated browser chat end-to-end UX totality
```

Those are separate runtime/UI concerns.

---

# 44. R2 does not make H_people ordinary state

Preserve:

```text
H_people SECRET
    ≠
ordinary chat context
```

and:

```text
authentication
    ≠
SECRET disclosure authority
```

---

# 45. R2 / R3 separation

R2 and R3 are separate formal domains.

R2:

```text
identity / conversational admission / governance noncreation / SECRET nondisclosure
```

R3:

```text
current JCP structure / Hilbert nonadmission / H_geo-H_p-H_people separation
```

Do not use R2 as proof of R3 claims.

---

# 46. Public-safe evidence boundaries

This file intentionally publishes only qualification-safe identities and metrics.

It does not need to expose:

- credentials;
- secrets;
- private user data;
- protected runtime values;
- privileged KYC content.

The proof and seal identities are sufficient for public technical traceability.

---

# 47. Evidence object summary

```yaml
r2_qualification_evidence:
  workstream: LEAN_CONVERSATIONAL_ADMISSION_R2
  status: QUALIFIED
  result: PASS

  lean:
    version: "4.34.0"
    commit: 293d5d0c0c3f3dded4688b3ccd6a33939ac5102b
    build_jobs: 27

  principal_theorems:
    count: 6
    kernel_checked: "6/6"
    proof_holes: 0
    final_theorem_level_axiom_dependencies: "0/6"
    initial_propext_dependencies: "6/6"
    final_propext_dependencies: "0/6"

  preservation:
    theorem_statements_preserved: true
    theorem_types_preserved: true
    theorem_semantics_preserved: true
    proof_bodies_changed: true
    Types_lean_preserved: true
    Semantics_lean_preserved: true

  parent_r1:
    branch: formal-verification/lean-authorized-adoption-r1
    head: beceb3ee44fd5c33eaf689a5abe086e5e9c67911
    tree: a62d4b78db5aae522fd06f61b9563e676eacc0a8

  r2:
    branch: formal-verification/lean-conversational-admission-r2
    head: c1a18b2e5fbe2e288d8b91dafe18668392bc787d
    tree: e325bfdd78cd6903dbfb3a8c15130af26de5cd9f

  evidence:
    directory: conversational-admission-r2-axiom-free-r1-20261002T215319Z

    evidence_manifest_sha256:
      fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229

    status_sha256:
      38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898

    source_manifest_sha256:
      21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b

    r19l2r1_final_sha256:
      ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30

    r19l2r1_manifest_sha256:
      7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf

  theorem_family:
    - TCHAT_A_server_derived_authenticated_identity
    - TCHAT_B_browser_identity_is_nonauthoritative
    - TCHAT_C_canonical_scalar_user_id_not_invented
    - TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
    - TCHAT_E_ordinary_chat_does_not_create_governance_authority
    - TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure

  nonclaims:
    source_runtime_correspondence_automatic: false
    production_authority_granted: false
    all_future_frontends_proved: false
    all_future_auth_implementations_proved: false
    whole_system_privacy_proved: false
    system_proven: false
```

---

# 48. Final qualification record

```text
R2_QUALIFICATION=PASS

LEAN_VERSION=4.34.0

PRINCIPAL_CHECKS=6_OF_6

PROOF_HOLES=0

INITIAL_PROPEXT_DEPENDENCIES=6_OF_6

FINAL_PROPEXT_DEPENDENCIES=0_OF_6

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

THEOREM_STATEMENTS_PRESERVED=YES

THEOREM_TYPES_PRESERVED=YES

THEOREM_SEMANTICS_PRESERVED=YES

R2_HEAD=c1a18b2e5fbe2e288d8b91dafe18668392bc787d

R2_TREE=e325bfdd78cd6903dbfb3a8c15130af26de5cd9f

EVIDENCE_MANIFEST_SHA256=fdeca0705e19b0a844ccaba6b933dff6a56d8f1cc198f33781cc006837c5e229

STATUS_SHA256=38cb2f47826d2a407f66757eb01dd5f155322b67a1a2fdd9aad4b789a84ff898

SOURCE_MANIFEST_SHA256=21c33b72f21d1e3fb3e923fc7c761be298b9a5ea7f9dbf9cb4ab08da8d07a34b

R19L2R1_FINAL_SHA256=ab740bdcd95f501791d00966ab650412c9c8f1236f28fa614c532b8c3e1c3d30

R19L2R1_MANIFEST_SHA256=7570c963c00ea40bd27cfd429847c003eac7aab03ee02c871b6b38b62e15e6cf

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **R2 is a qualified formal domain for conversational admission.**

> **All six principal checks are kernel-checked.**

> **The final proof family contains zero proof holes and zero final theorem-level axiom dependencies.**

> **The initial `propext` result is preserved as part of the qualification history rather than erased.**

> **The proof repair preserved theorem statements, types, and intended semantics.**

> **Git identities and evidence seals remain explicit so the qualified source/evidence state can be identified exactly.**

> **Formal proof does not automatically establish implementation/runtime correspondence.**

> **Implementation correspondence was established separately and remains point-in-time.**

> **Ordinary authenticated chat does not create governance authority.**

> **Ordinary authenticated chat does not authorize H_people SECRET disclosure.**

> **R2 does not grant production authority and does not prove the whole system.**

> **SYSTEM_PROVEN remains NO.**
