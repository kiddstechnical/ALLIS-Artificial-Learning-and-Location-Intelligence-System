<div align="center">

# ALLIS — Conversational Admission Source-to-Runtime Correspondence

### Later implementation/runtime evidence supporting the qualified Lean R2 Conversational Admission domain

<br>

![Domain](https://img.shields.io/badge/R2-CONVERSATIONAL_ADMISSION-7c3aed?style=for-the-badge)
![Layer](https://img.shields.io/badge/CORRESPONDENCE-SOURCE_TO_RUNTIME-2563eb?style=for-the-badge)
![Auth](https://img.shields.io/badge/IDENTITY-SERVER_DERIVED-22c55e?style=for-the-badge)
![Scalar ID](https://img.shields.io/badge/USER__ID-NULL_WHERE_UNESTABLISHED-0ea5e9?style=for-the-badge)
![Authority](https://img.shields.io/badge/IDENTITY_OBJECT-NOT_AUTHORITY-f97316?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document records the **later implementation/runtime correspondence** supporting the already-qualified Lean R2 Conversational Admission workstream.
>
> The direction is:
>
> ```text
> R2 formal model
>     ↓
> source correspondence
>     ↓
> later runtime / behavioral correspondence
> ```
>
> It does not make the runtime observation part of the Lean proof.
>
> Preserve:
>
> ```text
> theorem
>     ≠
> source correspondence
>     ≠
> runtime correspondence
> ```

---

# 1. Purpose

The R2 Lean workstream established six bounded conversational-admission claims.

Later implementation and runtime qualification then tested whether the deployed/current conversational path preserved those same semantics.

This document records the source-to-runtime evidence relevant to:

```text
/api/chat authentication ordering

server-derived authenticated_user

user_id remaining null where no canonical scalar ID exists

identity metadata remaining separate from downstream model/reasoning authority
```

---

# 2. R2 formal predecessor

The six qualified R2 checks are:

```text
TCHAT_A_server_derived_authenticated_identity

TCHAT_B_browser_identity_is_nonauthoritative

TCHAT_C_canonical_scalar_user_id_not_invented

TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated

TCHAT_E_ordinary_chat_does_not_create_governance_authority

TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

The later runtime evidence documented here supports the implementation correspondence of those bounded claims.

---

# 3. Current ordinary conversational route

The ordinary conversational front-door route is:

```text
POST /api/chat
```

The route participates in the current path:

```text
authenticated browser/session
    ↓
/api/chat
    ↓
Unified Gateway
    ↓
current reasoning / JCP path
    ↓
ensemble / synthesizer
    ↓
response
```

Do not substitute `/chatlight` as the canonical current ordinary conversational route.

---

# 4. Authentication ordering

The later qualified implementation/runtime path established the ordering:

```text
authenticate request/session
    ↓
derive trusted server-side identity
    ↓
accept ordinary browser JSON message
    ↓
construct Gateway payload
```

The important boundary is that trusted identity is already established before browser-supplied JSON is treated as ordinary conversational content.

---

# 5. Browser JSON is not identity authority

The browser supplies conversational content.

It does not become the trusted identity authority.

Preserve:

```text
browser JSON identity-like value
    ≠
trusted authenticated identity
```

The trusted source is the authenticated server-side session.

This supports:

```text
TCHAT_B_browser_identity_is_nonauthoritative
```

---

# 6. Server-derived `authenticated_user`

The later source/runtime correspondence established that the `/api/chat` path constructs:

```text
authenticated_user
```

from server-side authenticated state.

Therefore:

```text
AUTHENTICATED_USER_SOURCE=SERVER_DERIVED
```

not:

```text
AUTHENTICATED_USER_SOURCE=BROWSER_BODY
```

---

# 7. `authenticated_user` is identity metadata

The identity object is carried as structured metadata.

It is not automatically:

```text
model input

JCP content

governance authority

H_people SECRET disclosure authority
```

This distinction is central to the runtime correspondence.

---

# 8. Canonical scalar `user_id`

Where no separately established canonical scalar user ID exists, the qualified implementation preserves:

```text
user_id: null
```

This matches the R2 rule:

```text
missing canonical scalar identity
    ≠
permission to invent one
```

and supports:

```text
TCHAT_C_canonical_scalar_user_id_not_invented
```

---

# 9. Why `null` matters

The runtime is not required to manufacture a scalar identifier merely because a structured authenticated identity object exists.

Preserve:

```text
authenticated_user present
    +
canonical scalar user_id absent
    =
user_id remains null
```

This is intentional non-invention.

---

# 10. Qualified payload behavior

The bounded qualified route carried a payload with semantics equivalent to:

```text
message = browser conversational content

user_id = null

authenticated_user = server-derived authenticated identity object
```

The exact runtime/source contract is therefore:

```text
content source
    ≠
identity source
```

---

# 11. Unified Gateway acceptance

The later Gateway source correspondence established that the current Gateway request shape accepts:

```text
authenticated_user
```

as part of the request payload.

This proves only that the Gateway can receive the identity metadata.

It does not establish that downstream reasoning uses it.

---

# 12. `process_unified` behavior

The qualified Gateway source established that:

```text
process_unified
    accepts authenticated_user
```

while:

```text
process_unified
    does not read authenticated_user
```

for the bounded qualified path.

This is the critical downstream non-authority correspondence.

---

# 13. Identity object is not forwarded as model content

The qualified source/runtime path established:

```text
authenticated_user
    is not forwarded downstream as model input
```

and:

```text
authenticated_user
    is not included in ensemble/synthesizer input
```

within the bounded tested route.

This prevents:

```text
identity metadata
    →
implicit model context
```

---

# 14. Identity object does not enter JCP

The qualified path also established:

```text
authenticated_user
    does not enter current JCP
```

The current JCP remains governed by its own source contract.

This supports the separation:

```text
identity metadata
    ≠
JCP reasoning content
```

---

# 15. Identity object does not become governance authority

The later implementation/runtime correspondence supports:

```text
authenticated_user
    ≠
governance authority
```

The identity object may identify the conversational caller.

It does not grant:

```text
adoption authority

publication authority

protected-state mutation authority

SECRET disclosure authority
```

This supports:

```text
TCHAT_E_ordinary_chat_does_not_create_governance_authority
```

---

# 16. Identity object does not become H_people SECRET authority

The bounded runtime path did not use `authenticated_user` as authorization to release H_people SECRET state.

Preserve:

```text
authenticated caller
    ≠
H_people SECRET disclosure authority
```

This supports:

```text
TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

---

# 17. Private memory / H_people withholding

The isolated runtime qualification withheld private memory/H_people material from the ordinary conversational model-input path.

Therefore:

```text
ordinary authenticated conversation
    ≠
automatic private-state injection
```

and:

```text
authenticated_user
    ≠
automatic H_people retrieval key for model context
```

within the bounded qualified path.

---

# 18. Ensemble/synthesizer separation

The bounded runtime evidence established that authenticated-user identity was absent from:

```text
ensemble input
```

and:

```text
LM Synthesizer input
```

for the qualified route.

Therefore the conversational reasoning path did not transform identity metadata into model-facing content merely because the server knew the user's identity.

---

# 19. R2-A correspondence

Formal theorem:

```text
TCHAT_A_server_derived_authenticated_identity
```

Source/runtime support:

```text
/api/chat authenticates from server-side session
    ↓
server derives authenticated_user
```

Bounded correspondence:

```text
PASS
```

---

# 20. R2-B correspondence

Formal theorem:

```text
TCHAT_B_browser_identity_is_nonauthoritative
```

Source/runtime support:

```text
trusted identity established before browser JSON content is accepted
```

and:

```text
browser body does not supply trusted authenticated_user
```

Bounded correspondence:

```text
PASS
```

---

# 21. R2-C correspondence

Formal theorem:

```text
TCHAT_C_canonical_scalar_user_id_not_invented
```

Source/runtime support:

```text
user_id: null
```

where no canonical scalar identifier was separately established.

Bounded correspondence:

```text
PASS
```

---

# 22. R2-D correspondence

Formal theorem:

```text
TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
```

Source/runtime support included bounded A/B session-isolation behavior in the qualified route contract.

The implementation required each request to derive identity from its own authenticated server-side session rather than reusing browser-provided scalar identity.

Bounded correspondence:

```text
PASS
```

within the tested isolation scope.

---

# 23. R2-E correspondence

Formal theorem:

```text
TCHAT_E_ordinary_chat_does_not_create_governance_authority
```

Source/runtime support:

```text
authenticated_user
    accepted as identity metadata
```

but:

```text
process_unified does not use it to mint authority
```

and it does not enter downstream model/JCP reasoning as authority-bearing content.

Bounded correspondence:

```text
PASS
```

---

# 24. R2-F correspondence

Formal theorem:

```text
TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

Source/runtime support:

```text
private memory / H_people withheld
```

and:

```text
authenticated_user absent from downstream ensemble/synthesizer model input
```

and no ordinary chat path was established that converted authentication into H_people SECRET disclosure authority.

Bounded correspondence:

```text
PASS
```

---

# 25. Source objects

The implementation correspondence is associated with the current frontend/auth source set including:

```text
app/api/chat/route.js

lib/server-auth.js

app/ask/ConversationClient.jsx

app/ask/layout.js
```

and the current Unified Gateway request path.

These files/functions together form the relevant source-side correspondence surface.

---

# 26. Frontend production identity

The later production frontend cutover used:

```text
/opt/msjarvis-rebuild/allis-frontend-runtime/deploy-9KyheKDYXyNCclA1YrUAX-fullnm-3ace386dedd9
```

with BUILD_ID:

```text
9KyheKDYXyNCclA1YrUAX
```

and service:

```text
allis-frontend.service
```

These identify the qualified deployed frontend generation associated with the later conversational correspondence record.

---

# 27. Frontend source lineage

The live frontend was produced from the qualified candidate source:

```text
r16c4r18a3-correct-registration-notice-placement-20261002T190827Z-2402886/frontend-candidate
```

within the conversational investigation record.

The source identity and deployment identity are separate evidence objects.

---

# 28. Gateway qualified source identity

The qualified Gateway candidate/later production source SHA-256 was:

```text
a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f
```

This is the source identity used by the later production Gateway correspondence.

---

# 29. Gateway production correspondence

Later production cutover evidence established that the qualified Gateway source became the production source.

The bounded production path completed through:

```text
BBB
    ↓
llm20production
    ↓
LM Synthesizer
```

This strengthened runtime correspondence for the current conversational downstream path.

It did not change the R2 theorem statements.

---

# 30. Production Gateway closeout identity

The corrected production Gateway cutover record was:

```text
R16C4R20R4
```

with final SHA-256:

```text
1aaccf30781dc38f2ad10446bce30f3d9f8eb047a560e9b34de2cb94aa0b6f44
```

and manifest SHA-256:

```text
213eeb4ab6511ff78d5c1df9791d46917e0c055342bc65e2ab054e4a75e5bcbc
```

These are supporting runtime correspondence identities.

---

# 31. Durable server closeout

The later durable server/UI-boundary closeout was:

```text
R16C4R20R5R1
```

with final SHA-256:

```text
79c7ceaf7549543e194176881b9b4b77c8766057c8f2d8f281d3f596502ffbb6
```

and manifest SHA-256:

```text
37b1811a20107c08a0d1eb11c9d0e10a69fcec3e8bc7589f203d9c006d3461f6
```

That closeout preserved the server-side authenticated route while separately recording browser-UI limitations.

---

# 32. Fail-closed unauthenticated behavior

The later durable closeout established bounded unauthenticated fail-closed behavior for:

```text
/api/auth/me

/api/chat
```

This supports the current server-side authentication boundary.

It does not prove every future browser flow.

---

# 33. Browser UI limitation remains separate

The later closeout also recorded:

```text
CURRENT_BROWSER_CONVERSATIONAL_UI_READY=NO

CURRENT_BROWSER_CONVERSATIONAL_SEND_SURFACE=NO

AUTHENTICATED_BROWSER_CHAT_E2E=NOT_EXECUTABLE_CURRENT_UI
```

Therefore preserve:

```text
server-side route correspondence
    ≠
complete browser UI qualification
```

---

# 34. Server-side route qualification remains valid independently

The browser UI limitation did not erase the server-side source/runtime correspondence.

The qualified/deployed server-side `/api/chat` route remained the relevant R2 implementation object.

---

# 35. Runtime correspondence is point-in-time

This document records a bounded point-in-time correspondence.

Preserve:

```text
CURRENT_CORRESPONDENCE
    ≠
PERMANENT_CORRESPONDENCE
```

A source or deployment change can invalidate the correspondence even if the Lean theorem remains mathematically valid.

---

# 36. Revalidation triggers

Revalidate this correspondence if claim-bearing changes occur to:

```text
/api/chat

server-auth

session semantics

authenticated_user shape

user_id semantics

Gateway ChatPayload

process_unified

JCP composition

ensemble input

LM Synthesizer input

private-memory / H_people retrieval behavior
```

---

# 37. What this correspondence establishes

The strongest safe current statements are:

```text
/API_CHAT_AUTHENTICATES_BEFORE_BROWSER_IDENTITY_CONTENT=YES

AUTHENTICATED_USER_SERVER_DERIVED=YES

BROWSER_IDENTITY_AUTHORITATIVE=NO

USER_ID_REMAINS_NULL_WHERE_CANONICAL_SCALAR_ID_UNESTABLISHED=YES

AUTHENTICATED_USER_BECOMES_GOVERNANCE_AUTHORITY=NO

AUTHENTICATED_USER_ENTERS_CURRENT_JCP=NO

AUTHENTICATED_USER_BECOMES_MODEL_INPUT=NO

ORDINARY_CHAT_AUTHORIZES_HPEOPLE_SECRET_DISCLOSURE=NO
```

within the qualified current path.

---

# 38. What this correspondence does not establish

This file does not establish:

```text
EVERY_FUTURE_FRONTEND_PRESERVES_R2=YES
```

It does not establish:

```text
EVERY_FUTURE_AUTH_IMPLEMENTATION_PRESERVES_R2=YES
```

It does not establish:

```text
EVERY_GATEWAY_PATH_EXCLUDES_IDENTITY_FROM_MODEL_INPUT=YES
```

unless separately qualified.

It does not establish:

```text
WHOLE_SYSTEM_PRIVACY_PROVEN=YES
```

It does not establish:

```text
SYSTEM_PROVEN=YES
```

---

# 39. R2 formal/source/runtime separation

Preserve the evidence layering:

```text
Lean R2 theorem family
    ↓
formal qualification
```

```text
R2 model-to-source
    ↓
implementation mapping
```

```text
R2 source-to-runtime
    ↓
deployed/runtime behavior
```

None of these layers should be substituted for another.

---

# 40. Normalized correspondence record

```yaml
r2_source_to_runtime:
  formal_domain: LEAN_R2_CONVERSATIONAL_ADMISSION
  correspondence_layer: SOURCE_TO_RUNTIME

  route:
    ordinary_chat: /api/chat

  authentication:
    authenticate_before_browser_json_identity_acceptance: true
    trusted_identity_source: server_authenticated_session
    browser_identity_authoritative: false

  payload:
    authenticated_user:
      source: server_derived
      present: true

    user_id:
      null_when_canonical_scalar_id_unestablished: true

  gateway:
    accepts_authenticated_user: true
    process_unified_reads_authenticated_user: false
    authenticated_user_forwarded_as_model_input: false
    authenticated_user_enters_jcp: false
    authenticated_user_creates_governance_authority: false

  h_people:
    private_memory_withheld_in_bounded_runtime: true
    ordinary_chat_secret_disclosure_authority: false

  downstream:
    authenticated_user_present_in_ensemble_input: false
    authenticated_user_present_in_synthesizer_input: false

  implementation:
    frontend_build_id: 9KyheKDYXyNCclA1YrUAX
    gateway_source_sha256: a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f

  runtime_evidence:
    gateway_cutover:
      record: R16C4R20R4
      final_sha256: 1aaccf30781dc38f2ad10446bce30f3d9f8eb047a560e9b34de2cb94aa0b6f44
      manifest_sha256: 213eeb4ab6511ff78d5c1df9791d46917e0c055342bc65e2ab054e4a75e5bcbc

    durable_server_closeout:
      record: R16C4R20R5R1
      final_sha256: 79c7ceaf7549543e194176881b9b4b77c8766057c8f2d8f281d3f596502ffbb6
      manifest_sha256: 37b1811a20107c08a0d1eb11c9d0e10a69fcec3e8bc7589f203d9c006d3461f6

  ui_boundary:
    current_browser_conversational_ui_ready: false
    current_browser_send_surface: false
    authenticated_browser_chat_e2e: NOT_EXECUTABLE_CURRENT_UI

  nonclaims:
    permanent_correspondence: false
    every_future_frontend_proved: false
    every_future_auth_implementation_proved: false
    whole_system_privacy_proved: false
    system_proven: false
```

---

# 41. Final correspondence statement

```text
R2_SOURCE_TO_RUNTIME_CORRESPONDENCE=PRESENT

ORDINARY_ROUTE=/api/chat

AUTHENTICATE_BEFORE_BROWSER_JSON_IDENTITY_ACCEPTANCE=YES

AUTHENTICATED_USER_SERVER_DERIVED=YES

BROWSER_IDENTITY_AUTHORITATIVE=NO

USER_ID_NULL_WHERE_CANONICAL_SCALAR_ID_UNESTABLISHED=YES

GATEWAY_ACCEPTS_AUTHENTICATED_USER=YES

PROCESS_UNIFIED_READS_AUTHENTICATED_USER=NO

AUTHENTICATED_USER_ENTERS_JCP=NO

AUTHENTICATED_USER_BECOMES_MODEL_INPUT=NO

AUTHENTICATED_USER_CREATES_GOVERNANCE_AUTHORITY=NO

ORDINARY_CHAT_AUTHORIZES_HPEOPLE_SECRET_DISCLOSURE=NO

CORRESPONDENCE_IS_POINT_IN_TIME=YES

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **The server authenticates first; browser JSON does not establish trusted identity.**

> **`authenticated_user` is server-derived.**

> **`user_id` remains `null` where no canonical scalar identifier has been established.**

> **The Gateway may carry identity metadata without converting it into reasoning content or authority.**

> **`process_unified` does not use the bounded `authenticated_user` object as downstream model input.**

> **The identity object does not enter the current JCP under the qualified path.**

> **Ordinary authenticated chat does not become governance authority.**

> **Ordinary authenticated chat does not authorize H_people SECRET disclosure.**

> **Runtime correspondence is separate from the Lean proof and must be re-earned after claim-bearing implementation changes.**

> **SYSTEM_PROVEN remains NO.**
