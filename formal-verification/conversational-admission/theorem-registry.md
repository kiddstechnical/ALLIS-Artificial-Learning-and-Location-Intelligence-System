<div align="center">

# ALLIS — Lean R2 Conversational Admission Theorem Registry

### Exact theorem statements, semantic readings, trust-boundary meanings, and bounded claim limits for the six principal R2 conversational-admission theorems

<br>

![Registry](https://img.shields.io/badge/REGISTRY-LEAN_R2_THEOREMS-2563eb?style=for-the-badge)
![Lean](https://img.shields.io/badge/LEAN-4.34.0-7c3aed?style=for-the-badge)
![Theorems](https://img.shields.io/badge/PRINCIPAL_THEOREMS-6-22c55e?style=for-the-badge)
![Kernel](https://img.shields.io/badge/KERNEL_CHECKED-6_OF_6-22c55e?style=for-the-badge)
![Proof Holes](https://img.shields.io/badge/PROOF_HOLES-0-22c55e?style=for-the-badge)
![Axioms](https://img.shields.io/badge/THEOREM_LEVEL_AXIOMS-0_OF_6-22c55e?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This registry records the six principal Lean R2 theorem statements and their bounded semantic meanings.
>
> The theorem statements are preserved as the controlling formal propositions for the R2 Conversational Admission domain.
>
> Their semantic descriptions explain what the propositions mean architecturally; they do not broaden the theorem domains.
>
> ```text
> theorem proved
>     ≠
> every implementation corresponded
>     ≠
> every future frontend secure
>     ≠
> whole-system proof
> ```

---

# 1. Registry status

```text
FORMAL_DOMAIN=LEAN_R2_CONVERSATIONAL_ADMISSION

LEAN_VERSION=4.34.0

PRINCIPAL_THEOREMS=6

KERNEL_CHECKED_PRINCIPAL_THEOREMS=6_OF_6

PROOF_HOLES=0

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

PROPEXT_DEPENDENCY_REMOVED=PASS

SYSTEM_PROVEN=NO
```

The six principal theorem IDs are:

```text
TCHAT-A
TCHAT-B
TCHAT-C
TCHAT-D
TCHAT-E
TCHAT-F
```

Their exact Lean theorem identifiers are:

```text
TCHAT_A_server_derived_authenticated_identity

TCHAT_B_browser_identity_is_nonauthoritative

TCHAT_C_canonical_scalar_user_id_not_invented

TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated

TCHAT_E_ordinary_chat_does_not_create_governance_authority

TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

---

# 2. Domain purpose

R2 formalizes the trust boundary for **ordinary authenticated conversation**.

The six theorems cover six distinct properties:

```text
A. authenticated identity is server-derived

B. browser identity-like content is non-authoritative

C. a missing canonical scalar user ID is not invented

D. distinct authenticated sessions remain identity-isolated

E. ordinary chat does not create governance authority

F. ordinary chat does not authorize H_people SECRET disclosure
```

These properties are related, but they are not interchangeable.

The registry therefore preserves them as six separate theorem objects.

---

# 3. TCHAT-A — server-derived authenticated identity

## 3.1 Exact theorem identifier

```lean
TCHAT_A_server_derived_authenticated_identity
```

## 3.2 Exact theorem statement

```lean
TCHAT_A_server_derived_authenticated_identity
(session) (body) (hAuthenticated : session.authenticated = true) :
Option.map (fun chat => chat.authenticatedUser)
  (admitOrdinaryChat session body) = some session.identity
```

## 3.3 Formal effect

For an authenticated session:

```text
admitted chat.authenticatedUser
    =
session.identity
```

## 3.4 Semantic meaning

The trusted conversational identity originates from the authenticated server-side session.

It is not selected from the browser-controlled request body.

The theorem therefore formalizes:

```text
server-side authenticated session
    →
trusted conversational identity
```

not:

```text
browser-controlled content
    →
trusted conversational identity
```

## 3.5 Security meaning

```text
authenticated session identity
    =
identity authority for ordinary-chat admission
```

while:

```text
browser body
    ≠
identity authority
```

## 3.6 Bounded claim limit

TCHAT-A does not prove:

- that every future authentication implementation is correct;
- that every browser route uses the same admission function;
- that every identity-related subsystem is formally verified;
- that authenticated identity implies governance authority;
- that authenticated identity implies H_people disclosure authority.

---

# 4. TCHAT-B — browser identity is non-authoritative

## 4.1 Exact theorem identifier

```lean
TCHAT_B_browser_identity_is_nonauthoritative
```

## 4.2 Exact theorem statement

```lean
TCHAT_B_browser_identity_is_nonauthoritative
(session) (bodyA bodyB) (hAuthenticated : session.authenticated = true) :
Option.map (fun chat => chat.authenticatedUser)
  (admitOrdinaryChat session bodyA) =
Option.map (fun chat => chat.authenticatedUser)
  (admitOrdinaryChat session bodyB)
```

## 4.3 Formal effect

For the same authenticated session:

```text
changing bodyA → bodyB
    does not change
admitted authenticatedUser
```

## 4.4 Semantic meaning

Browser-controlled message content cannot choose, substitute, or overwrite the trusted conversational identity.

The theorem formalizes:

```text
same authenticated session
    +
different browser body
    =
same admitted authenticated user
```

## 4.5 Security meaning

```text
browser identity-like field
    ≠
trusted identity authority
```

A caller cannot become another authenticated user merely by changing request-body identity content.

## 4.6 Bounded claim limit

TCHAT-B does not prove that browser content can never affect any application field.

It proves only the bounded R2 identity property:

```text
browser-controlled body variation
    does not control
admitted authenticatedUser
```

---

# 5. TCHAT-C — canonical scalar user ID is not invented

## 5.1 Exact theorem identifier

```lean
TCHAT_C_canonical_scalar_user_id_not_invented
```

## 5.2 Exact theorem statement

```lean
TCHAT_C_canonical_scalar_user_id_not_invented
(session) (body) (hAuthenticated : session.authenticated = true)
(hNoCanonical : session.canonicalUserId = none) :
Option.map (fun chat => chat.canonicalUserId)
  (admitOrdinaryChat session body) = some none
```

## 5.3 Formal effect

If:

```text
session.canonicalUserId = none
```

then:

```text
admitted chat.canonicalUserId = none
```

## 5.4 Semantic meaning

Ordinary-chat admission does not manufacture a canonical scalar user ID when the authenticated session does not establish one.

The theorem formalizes:

```text
missing canonical identity
    remains
missing canonical identity
```

rather than:

```text
missing canonical identity
    →
invented identifier
```

## 5.5 Security meaning

Identity absence is preserved.

The system is not permitted to fill an identity gap merely because a downstream shape would be easier to satisfy with a scalar user ID.

## 5.6 Bounded claim limit

TCHAT-C does not prohibit a separately qualified identity service from establishing a canonical user ID through another authorized process.

It establishes only:

```text
ordinary-chat admission
    does not invent one
when the authenticated session has none
```

---

# 6. TCHAT-D — distinct authenticated sessions remain identity-isolated

## 6.1 Exact theorem identifier

```lean
TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
```

## 6.2 Exact theorem statement

```lean
TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
(sessionA sessionB) (bodyA bodyB)
(hAuthenticatedA : sessionA.authenticated = true)
(hAuthenticatedB : sessionB.authenticated = true)
(hDistinct : sessionA.identity ≠ sessionB.identity) :
Option.map (fun chat => chat.authenticatedUser)
  (admitOrdinaryChat sessionA bodyA) ≠
Option.map (fun chat => chat.authenticatedUser)
  (admitOrdinaryChat sessionB bodyB)
```

## 6.3 Formal effect

Given:

```text
sessionA.identity ≠ sessionB.identity
```

the corresponding admitted authenticated-user values remain distinct.

## 6.4 Semantic meaning

Distinct authenticated sessions do not collapse into one conversational identity.

The theorem formalizes:

```text
session A
    →
identity A
```

and:

```text
session B
    →
identity B
```

with:

```text
identity A ≠ identity B
```

preserved through admission.

## 6.5 Security meaning

The bounded admission model preserves session identity isolation.

```text
session A
    ≠
session B
```

does not become:

```text
same trusted conversational identity
```

## 6.6 Bounded claim limit

TCHAT-D does not prove whole-system multi-user isolation across every datastore, service, cache, or future runtime.

It proves the stated identity-isolation property inside the R2 admission model.

---

# 7. TCHAT-E — ordinary chat does not create governance authority

## 7.1 Exact theorem identifier

```lean
TCHAT_E_ordinary_chat_does_not_create_governance_authority
```

## 7.2 Exact theorem statement

```lean
TCHAT_E_ordinary_chat_does_not_create_governance_authority
(session) (body) (hAuthenticated : session.authenticated = true) :
Option.map (fun chat => chat.authority)
  (admitOrdinaryChat session body) = some noAuthority
```

## 7.3 Formal effect

For authenticated ordinary-chat admission:

```text
chat.authority
    =
noAuthority
```

## 7.4 Semantic meaning

Authentication is not governance authorization.

The theorem establishes that ordinary conversational admission does not manufacture authority to perform a protected governance transition.

## 7.5 Security meaning

```text
authenticated
    ≠
governance-authorized
```

and:

```text
ordinary chat admitted
    ≠
operation authority granted
```

This is a formal instance of the broader ALLIS rule:

> **State does not become authority merely because it exists.**

## 7.6 Bounded claim limit

TCHAT-E does not prove every governance mechanism in ALLIS.

It proves only that the R2 ordinary-chat admission object itself carries:

```text
noAuthority
```

rather than creating governance authority.

---

# 8. TCHAT-F — ordinary chat does not authorize H_people SECRET disclosure

## 8.1 Exact theorem identifier

```lean
TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

## 8.2 Exact theorem statement

```lean
TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
(session) (body) (hAuthenticated : session.authenticated = true) :
Option.map (fun chat => chat.authority.secretDisclosureAuthorized)
  (admitOrdinaryChat session body) = some false
```

## 8.3 Formal effect

For authenticated ordinary-chat admission:

```text
chat.authority.secretDisclosureAuthorized
    =
false
```

## 8.4 Semantic meaning

Ordinary authenticated conversation does not authorize disclosure of H_people SECRET state.

Authentication may permit ordinary conversation.

It does not establish the separate authority required for protected SECRET disclosure.

## 8.5 Security meaning

```text
ordinary authenticated chat
    ≠
H_people SECRET disclosure authority
```

and:

```text
identity established
    ≠
SECRET disclosure authorized
```

## 8.6 Bounded claim limit

TCHAT-F does not prove the full H_people subsystem.

It does not define every possible lawful/authorized disclosure process.

It proves the narrower R2 proposition that ordinary authenticated chat itself does **not** authorize H_people SECRET disclosure.

---

# 9. Six-theorem semantic matrix

| ID | Exact theorem | Bounded semantic meaning |
|---|---|---|
| TCHAT-A | `TCHAT_A_server_derived_authenticated_identity` | Trusted conversational identity comes from the authenticated server-side session |
| TCHAT-B | `TCHAT_B_browser_identity_is_nonauthoritative` | Browser-controlled body content cannot choose or overwrite trusted identity |
| TCHAT-C | `TCHAT_C_canonical_scalar_user_id_not_invented` | No canonical scalar user ID is invented when the authenticated session has none |
| TCHAT-D | `TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated` | Distinct authenticated session identities remain distinct through admission |
| TCHAT-E | `TCHAT_E_ordinary_chat_does_not_create_governance_authority` | Ordinary authenticated chat carries no governance authority |
| TCHAT-F | `TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure` | Ordinary authenticated chat does not authorize H_people SECRET disclosure |

---

# 10. Qualification status

The final R2 theorem family closed with:

```text
LEAN_VERSION=4.34.0

PRINCIPAL_THEOREMS=6
KERNEL_CHECKED_PRINCIPAL_THEOREMS=6_OF_6

PROOF_HOLES=0

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

PROPEXT_DEPENDENCY_REMOVED=PASS
```

The qualification process treated theorem-level axiom dependency as independently important from compilation.

The initial proof form compiled all six theorems but reported:

```text
propext dependency = 6 / 6
```

That state was rejected for final qualification.

The repaired direct-proof form preserved the six theorem statements while removing the unexpected theorem-level `propext` dependency.

Final result:

```text
propext dependency = 0 / 6
```

---

# 11. Statement preservation and proof repair

The R2 repair preserved:

```text
theorem identifiers
theorem statements
theorem types
theorem semantics
Types.lean
Semantics.lean
```

The repair changed the proof bodies.

That distinction matters:

```text
claim
    ≠
proof construction
```

A proof-body repair can remove an unwanted dependency without changing the proposition being proved.

For R2, that is exactly what occurred.

---

# 12. Registry interpretation rule

Each theorem should be cited by its exact ID when making a current claim.

Use:

```text
TCHAT-A
```

for:

```text
server-derived authenticated identity
```

Use:

```text
TCHAT-B
```

for:

```text
browser identity non-authority
```

Use:

```text
TCHAT-C
```

for:

```text
no invented canonical scalar user ID
```

Use:

```text
TCHAT-D
```

for:

```text
authenticated-session identity isolation
```

Use:

```text
TCHAT-E
```

for:

```text
ordinary chat does not create governance authority
```

Use:

```text
TCHAT-F
```

for:

```text
ordinary chat does not authorize H_people SECRET disclosure
```

Do not collapse all six propositions into a generic statement such as:

```text
Lean proves chat security
```

That would erase the bounded theorem structure.

---

# 13. Theorem proof vs implementation correspondence

This registry is a formal theorem registry.

It does not itself establish implementation correspondence.

Preserve:

```text
theorem statement
    ↓
kernel proof
```

separately from:

```text
formal model
    ↓
source correspondence
    ↓
runtime correspondence
    ↓
relevant live observation
```

Later frontend/Gateway evidence can support implementation correspondence for the R2 semantics.

That later evidence does not change the theorem statements recorded here.

---

# 14. Later correspondence context

Later bounded source/runtime qualification supported the R2 interpretation by showing that:

- `/api/chat` authenticates before browser JSON is accepted as application content;
- `authenticated_user` is constructed server-side;
- `user_id` remains `null` in the qualified bounded path where no canonical scalar ID is established;
- the Gateway accepts the authenticated-user object;
- `process_unified` does not read it;
- it is not forwarded downstream;
- it does not enter JCP;
- it does not become model input;
- it does not create governance authority;
- it does not create SECRET-disclosure authority;
- private-memory/H_people material remains withheld from the bounded ordinary downstream path.

Those later facts belong to correspondence records.

They should not be substituted for the theorem statements themselves.

---

# 15. Claim limits

The R2 theorem family does **not** establish:

```text
EVERY_FUTURE_FRONTEND_SECURE=YES
```

```text
EVERY_AUTHENTICATION_IMPLEMENTATION_CORRECT=YES
```

```text
WHOLE_SYSTEM_IDENTITY_SAFE=YES
```

```text
HPEOPLE_FULL_DOMAIN_PROVEN=YES
```

```text
MODEL_FACTUAL_CORRECTNESS_PROVEN=YES
```

```text
WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=YES
```

```text
SYSTEM_PROVEN=YES
```

It also does not create:

```text
deployment authority
```

```text
governance authority
```

```text
SECRET disclosure authority
```

```text
publication authority
```

```text
protected write authority
```

---

# 16. Normalized theorem registry

```yaml
lean_r2_conversational_admission:
  lean_version: "4.34.0"

  principal_theorems:
    TCHAT-A:
      theorem: TCHAT_A_server_derived_authenticated_identity
      semantic_meaning: server-derived authenticated conversational identity
      result: PASS
      proof_holes: 0
      theorem_level_axiom_dependencies: 0

    TCHAT-B:
      theorem: TCHAT_B_browser_identity_is_nonauthoritative
      semantic_meaning: browser identity content is non-authoritative
      result: PASS
      proof_holes: 0
      theorem_level_axiom_dependencies: 0

    TCHAT-C:
      theorem: TCHAT_C_canonical_scalar_user_id_not_invented
      semantic_meaning: missing canonical scalar user ID is not invented
      result: PASS
      proof_holes: 0
      theorem_level_axiom_dependencies: 0

    TCHAT-D:
      theorem: TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
      semantic_meaning: distinct authenticated sessions remain identity-isolated
      result: PASS
      proof_holes: 0
      theorem_level_axiom_dependencies: 0

    TCHAT-E:
      theorem: TCHAT_E_ordinary_chat_does_not_create_governance_authority
      semantic_meaning: ordinary authenticated chat does not create governance authority
      result: PASS
      proof_holes: 0
      theorem_level_axiom_dependencies: 0

    TCHAT-F:
      theorem: TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
      semantic_meaning: ordinary authenticated chat does not authorize H_people SECRET disclosure
      result: PASS
      proof_holes: 0
      theorem_level_axiom_dependencies: 0

  aggregate:
    principal_theorems: 6
    kernel_checked: "6/6"
    proof_holes: 0
    final_theorem_level_axiom_dependencies: "0/6"
    initial_propext_dependencies: "6/6"
    final_propext_dependencies: "0/6"

  claim_limits:
    every_future_frontend_secure: false
    every_authentication_implementation_correct: false
    whole_system_identity_safe: false
    hpeople_full_domain_proven: false
    whole_system_safety_proven: false
    system_proven: false

  authority:
    authenticated_identity_is_governance_authority: false
    browser_identity_is_trusted_identity_authority: false
    ordinary_chat_authorizes_hpeople_secret_disclosure: false
```

---

# 17. Final registry statement

```text
R2_THEOREM_REGISTRY=CURRENT

TCHAT_A=KERNEL_CHECKED_PASS
TCHAT_B=KERNEL_CHECKED_PASS
TCHAT_C=KERNEL_CHECKED_PASS
TCHAT_D=KERNEL_CHECKED_PASS
TCHAT_E=KERNEL_CHECKED_PASS
TCHAT_F=KERNEL_CHECKED_PASS

PRINCIPAL_THEOREMS=6_OF_6

PROOF_HOLES=0

FINAL_THEOREM_LEVEL_AXIOM_DEPENDENCIES=0_OF_6

SYSTEM_PROVEN=NO
```

---

# Governing interpretation

> **TCHAT-A proves the bounded server-derived identity property.**

> **TCHAT-B proves the bounded browser identity non-authority property.**

> **TCHAT-C proves that ordinary-chat admission does not invent a missing canonical scalar user ID.**

> **TCHAT-D proves bounded authenticated-session identity isolation.**

> **TCHAT-E proves that ordinary authenticated chat does not create governance authority.**

> **TCHAT-F proves that ordinary authenticated chat does not authorize H_people SECRET disclosure.**

> **Together, the six theorems form the R2 Conversational Admission proof domain. They do not become a whole-system proof by aggregation.**
