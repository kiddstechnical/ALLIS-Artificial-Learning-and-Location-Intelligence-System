<div align="center">

# ALLIS — Lean R2 Model-to-Source Correspondence

### Public crosswalk from the R2 Conversational Admission formal semantics to the exact current conversational source boundary

<br>

![Domain](https://img.shields.io/badge/R2-CONVERSATIONAL_ADMISSION-2563eb?style=for-the-badge)
![Layer](https://img.shields.io/badge/CORRESPONDENCE-MODEL_TO_SOURCE-7c3aed?style=for-the-badge)
![Frontend](https://img.shields.io/badge/FRONTEND-%2Fapi%2Fchat-0ea5e9?style=for-the-badge)
![Gateway](https://img.shields.io/badge/GATEWAY-AUTHENTICATED_USER_BOUNDARY-14b8a6?style=for-the-badge)
![Authority](https://img.shields.io/badge/THEOREM_PROOF-%E2%89%A0_SOURCE_CORRESPONDENCE-f97316?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document is the **model-to-source crosswalk** for Lean R2 Conversational Admission.
>
> It is intentionally separate from:
>
> - the R2 theorem registry;
> - the R2 workstream closeout;
> - source-to-runtime correspondence;
> - live runtime observation.
>
> The governing rule is:
>
> ```text
> theorem proof
>     ≠
> implementation correspondence
> ```
>
> A theorem may be valid while a deployed or candidate program implements different semantics. This file therefore binds the R2 formal claims to the exact source objects, source fields, and source functions that carry the corresponding conversational behavior.

---

# 1. Correspondence status

```text
FORMAL_DOMAIN=LEAN_R2_CONVERSATIONAL_ADMISSION

CORRESPONDENCE_LAYER=MODEL_TO_SOURCE

R2_THEOREM_QUALIFICATION=PASS

MODEL_TO_SOURCE_CROSSWALK=PRESENT

SOURCE_TO_RUNTIME_CORRESPONDENCE=SEPARATE

LIVE_OBSERVATION=SEPARATE

OPERATIONAL_AUTHORITY=SEPARATE

SYSTEM_PROVEN=NO
```

The R2 formal workstream initially closed without claiming source/runtime correspondence.

That was correct.

Later frontend/Gateway qualification supplied the source-side evidence needed to build this crosswalk.

---

# 2. Correspondence ladder

The ALLIS evidence model distinguishes:

```text
formal statement
    ↓
kernel proof
    ↓
model-to-source correspondence
    ↓
source-to-runtime identity
    ↓
relevant live observation
    ↓
operational authority
```

Each layer answers a different question.

| Layer | Question |
|---|---|
| Formal statement | What bounded property is being claimed? |
| Kernel proof | Does the proposition follow in the formal R2 model? |
| Model-to-source | Which exact source objects implement the same semantics? |
| Source-to-runtime | Is the running code the qualified source? |
| Live observation | Did the relevant running path exhibit the bounded behavior? |
| Operational authority | May a protected transition occur? |

This document covers only the third row.

---

# 3. Source set used for R2 correspondence

The frontend source snapshot used during the R2 preflight and later conversational qualification was the source that produced the qualified/live frontend cutover.

## 3.1 Frontend source root

```text
/home/cakidd/allis-conversational-investigation-20260925T204513Z/
r16c4r18a3-correct-registration-notice-placement-20261002T190827Z-2402886/
frontend-candidate
```

The R2 preflight identified these exact source objects:

```text
app/api/chat/route.js

app/ask/ConversationClient.jsx

app/ask/layout.js

lib/server-auth.js
```

Their roles are different:

| Source object | R2 correspondence role |
|---|---|
| `app/api/chat/route.js` | server-side ordinary-chat admission bridge |
| `lib/server-auth.js` | authenticated server-side identity source |
| `app/ask/ConversationClient.jsx` | browser-side ordinary-chat caller; message transport only, not identity authority |
| `app/ask/layout.js` | frontend composition point for the conversation client |

The R2 preflight captured source SHA-256 identities for those objects as part of the qualification record.

This public crosswalk does not invent SHA values that are not reproduced in the retained public evidence.

---

# 4. Current frontend deployment identity associated with the source snapshot

The controlling frontend cutover referenced during R2 preflight was:

```text
r16c4r18a4-frontend-production-cutover-20261002T191856Z-2417338
```

with:

```text
FINAL_SHA256 =
48156cf5595ea93093439c9d199d91e60d1236603b971d4b4938fc0cbb3a2cb6

MANIFEST_SHA256 =
40f79d6ce944ce7be096fe4d3ccc286457ed3d0de72f65203bfb9b1fb747c95d
```

The expected live frontend release was:

```text
/opt/msjarvis-rebuild/allis-frontend-runtime/
deploy-9KyheKDYXyNCclA1YrUAX-fullnm-3ace386dedd9
```

with:

```text
BUILD_ID=9KyheKDYXyNCclA1YrUAX
```

Those identities belong to the deployment/source evidence layer.

They are not theorem identities.

---

# 5. `/api/chat` is the source-side R2 admission boundary

The principal frontend source correspondence object is:

```text
app/api/chat/route.js
```

The R2 source record established that the deployed `/api/chat` path:

1. performs authentication before accepting browser JSON as ordinary application content;
2. obtains the trusted identity from the server-side authenticated context;
3. constructs:

```text
authenticated_user
```

server-side;

4. carries:

```text
user_id: null
```

where no separately adjudicated canonical scalar user ID exists;

5. forwards the ordinary message together with the server-derived authenticated-user object to the Gateway `/chat` path.

The important source-ordering rule is:

```text
authenticate
    ↓
derive trusted identity
    ↓
accept ordinary browser message content
    ↓
construct Gateway chat payload
```

not:

```text
read browser identity claim
    ↓
treat browser claim as trusted identity
```

---

# 6. `lib/server-auth.js` is the trusted frontend identity source

The exact frontend authentication source object bound into the R2 preflight is:

```text
lib/server-auth.js
```

The correspondence claim is deliberately source-semantic rather than name-based:

```text
server-auth source
    →
authenticated server-side session / identity
```

The R2 formal identity object:

```text
session.identity
```

maps to the trusted server-derived identity used by `/api/chat`.

The crosswalk does **not** assert that a particular JavaScript function name is controlling unless that function identifier is separately present in the source evidence.

This is intentional.

The correspondence is to the verified server-auth source semantics, not to an invented function label.

---

# 7. Browser request body is not the identity source

The browser-side source object is:

```text
app/ask/ConversationClient.jsx
```

Its R2 role is to send ordinary conversational content to:

```text
/api/chat
```

The browser may supply the conversational message.

The browser does not supply the trusted `authenticated_user` authority object.

The source correspondence is therefore:

```text
browser:
    message content

server:
    trusted authenticated identity
```

and not:

```text
browser:
    message
    +
    trusted identity claim
```

This is the source-side counterpart of TCHAT-B.

---

# 8. `app/ask/layout.js` is a composition object, not identity authority

The R2 source snapshot also included:

```text
app/ask/layout.js
```

Its relevant role is frontend composition around the conversation client.

It is not treated by R2 as an identity authority source.

The presence of a component in the browser rendering tree does not give that component authority to establish trusted user identity.

---

# 9. Gateway source boundary

The qualified Gateway candidate accepted the frontend server-derived identity object through its chat input contract.

The source-side fields/functions established by the retained correspondence record are:

```text
ChatPayload.authenticated_user

/chat

payload.authenticated_user

process_unified(..., authenticated_user=...)
```

The exact semantics established by static and isolated qualification are:

```text
/chat
    receives ChatPayload

/chat
    passes payload.authenticated_user

process_unified
    accepts authenticated_user
```

but:

```text
process_unified
    does not read authenticated_user
```

and:

```text
authenticated_user
    is not forwarded downstream
```

and:

```text
authenticated_user
    does not enter JCP
```

and:

```text
authenticated_user
    does not become model input
```

and:

```text
authority effect = NO
content effect = NO
```

This inert carriage is critical to R2 correspondence.

The implementation may carry authenticated identity metadata without thereby converting it into conversational content or governance authority.

---

# 10. Qualified Gateway source identity

The qualified Gateway candidate later associated with production correspondence had source identity:

```text
a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f
```

Later production runtime correspondence recorded:

```text
Gateway image =
sha256:f2ee4e106373a321f65ab2eef00cf7d3b09cf1bdcf61bfb44ed79ec977f6444b
```

and production container:

```text
6056e7c7848af2e676bbc53c6c909e3844bdec2f1c5a5832b7599e237bce3481
```

Those later identities belong to source/runtime correspondence.

They are included here only to identify the later source object to which the R2 source semantics were bound.

---

# 11. R2 formal-to-source crosswalk — overview

| R2 theorem | Formal semantic | Source-side correspondence |
|---|---|---|
| TCHAT-A | server-derived authenticated identity | `/api/chat` derives `authenticated_user` from server-side authenticated context before browser JSON becomes trusted application content |
| TCHAT-B | browser identity is non-authoritative | browser `ConversationClient` supplies message content; trusted identity is constructed server-side rather than taken from browser identity-like content |
| TCHAT-C | canonical scalar user ID is not invented | `/api/chat` carries `user_id: null` where no canonical scalar user ID has been separately established |
| TCHAT-D | distinct authenticated sessions remain identity-isolated | bounded behavior contract requires session A → identity A and session B → identity B, with no crossing |
| TCHAT-E | ordinary chat creates no governance authority | Gateway accepts `authenticated_user` but `process_unified` does not use it to create authority; authority effect remains NO |
| TCHAT-F | ordinary chat does not authorize H_people SECRET disclosure | H_people/private-memory retrieval remains outside the bounded ordinary path; authenticated-user identity is not used as SECRET disclosure authority |

---

# 12. TCHAT-A model-to-source correspondence

## 12.1 Formal object

```text
TCHAT_A_server_derived_authenticated_identity
```

Formal semantic:

```text
admitOrdinaryChat(session, body).authenticatedUser
    =
session.identity
```

for an authenticated session.

## 12.2 Source objects

```text
lib/server-auth.js
app/api/chat/route.js
```

## 12.3 Source fields

```text
authenticated_user
```

and the server-side authenticated session/identity object from the authentication source.

## 12.4 Correspondence relation

```text
R2 session.identity
    ↔
server-derived authenticated identity

R2 admittedChat.authenticatedUser
    ↔
/api/chat authenticated_user
```

## 12.5 Source evidence

The qualified `/api/chat` semantics establish:

```text
authentication occurs before browser JSON is accepted
```

and:

```text
authenticated_user is constructed server-side
```

This is the source-side realization of the TCHAT-A trust boundary.

## 12.6 Nonclaim

This crosswalk does not prove every future auth implementation.

It binds TCHAT-A only to the qualified source semantics under review.

---

# 13. TCHAT-B model-to-source correspondence

## 13.1 Formal object

```text
TCHAT_B_browser_identity_is_nonauthoritative
```

Formal semantic:

```text
changing browser body
    does not change
trusted admitted identity
```

## 13.2 Source objects

```text
app/ask/ConversationClient.jsx
app/api/chat/route.js
lib/server-auth.js
```

## 13.3 Source relation

```text
ConversationClient message
    →
/api/chat ordinary content
```

while:

```text
server-auth authenticated context
    →
authenticated_user
```

The browser message body does not become the source of trusted `authenticated_user`.

## 13.4 Bounded behavior contract

The conversational qualification contract required:

```text
json.authenticated_user
    =
server-derived /api/auth/me identity object
```

not a caller-fabricated identity object.

The intended behavioral proof also required two real, distinct nonproduction sessions rather than fake `authenticated_user` JSON.

That distinction protects the theorem/source mapping from circular testing.

---

# 14. TCHAT-C model-to-source correspondence

## 14.1 Formal object

```text
TCHAT_C_canonical_scalar_user_id_not_invented
```

Formal semantic:

```text
session.canonicalUserId = none
    ⇒
admitted canonicalUserId = none
```

## 14.2 Source field

```text
user_id
```

## 14.3 Source-side qualified value

The bounded qualified ordinary-chat request carries:

```text
user_id: null
```

unless a canonical scalar user ID is separately adjudicated.

## 14.4 Correspondence relation

```text
R2 canonicalUserId = none
    ↔
source user_id = null
```

The source does not fabricate a scalar identifier solely to populate the payload.

## 14.5 Nonclaim

This does not prohibit a separately qualified identity subsystem from establishing a canonical scalar ID through another governed process.

---

# 15. TCHAT-D model-to-source correspondence

## 15.1 Formal object

```text
TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
```

Formal semantic:

```text
session A identity ≠ session B identity
    ⇒
admitted identity A ≠ admitted identity B
```

## 15.2 Source objects

```text
lib/server-auth.js
app/api/chat/route.js
Gateway ChatPayload.authenticated_user
```

## 15.3 Required implementation behavior

The bounded behavior contract was explicitly defined as:

```text
real session A
    →
trusted identity A
    →
request A

real session B
    →
trusted identity B
    →
request B
```

with:

```text
no crossing
```

The associated behavior contract required:

- A request forwards only A's server-derived identity;
- B request forwards only B's server-derived identity;
- A marker never appears in B's captured request;
- B marker never appears in A's captured request;
- `user_id` remains null for both unless separately adjudicated.

## 15.4 Correspondence boundary

This source mapping is narrower than a whole-system multi-user isolation theorem.

It binds the R2 identity-isolation property to the ordinary-chat admission path.

---

# 16. TCHAT-E model-to-source correspondence

## 16.1 Formal object

```text
TCHAT_E_ordinary_chat_does_not_create_governance_authority
```

Formal semantic:

```text
admitted ordinary chat authority
    =
noAuthority
```

## 16.2 Gateway source functions/fields

```text
ChatPayload.authenticated_user

/chat

payload.authenticated_user

process_unified
```

## 16.3 Source semantics

The qualified Gateway source establishes:

```text
process_unified accepts authenticated_user
```

but:

```text
process_unified does not read authenticated_user
```

and:

```text
authenticated_user is not forwarded downstream
```

and:

```text
authority effect = NO
```

Thus server-derived identity metadata is transported at the Gateway boundary without being interpreted as governance authority.

## 16.4 Correspondence relation

```text
R2 noAuthority
    ↔
source path has no authority-producing use of authenticated_user
```

## 16.5 Nonclaim

This does not prove all governance behavior in ALLIS.

It proves the bounded relationship between ordinary chat identity carriage and absence of governance-authority creation in the qualified source path.

---

# 17. TCHAT-F model-to-source correspondence

## 17.1 Formal object

```text
TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
```

Formal semantic:

```text
secretDisclosureAuthorized
    =
false
```

for ordinary authenticated-chat admission.

## 17.2 Source/runtime boundary relevant to the crosswalk

The qualified conversational path preserved:

```text
H_people remains outside the ordinary path
```

The bounded behavior contract required:

```text
no /gateway/hp/query request
no H_people retrieval
```

Later isolated qualification also withheld:

```text
private memory / H_people
```

and confirmed authenticated-user identity material was absent from ensemble and synthesizer inputs.

## 17.3 Source correspondence

The source path does not map:

```text
authenticated_user
```

into:

```text
H_people SECRET disclosure authority
```

or ordinary downstream model context.

## 17.4 Nonclaim

This does not define every authorized H_people disclosure path.

It establishes that ordinary authenticated conversation is not itself such a path.

---

# 18. JCP boundary relevant to R2

The current ordinary-chat JCP is a separate source boundary.

R2 source correspondence establishes that:

```text
authenticated_user
    does not enter JCP
```

This matters because:

```text
trusted conversational identity metadata
    ≠
ordinary model context
```

The later R3 formal work separately qualifies the current JCP field set.

R2 does not absorb R3.

The only R2-relevant statement here is:

> The qualified Gateway source does not turn `authenticated_user` into JCP content.

---

# 19. Downstream model-input boundary

The retained correspondence evidence establishes:

```text
authenticated_user
    is not forwarded downstream
```

and:

```text
authenticated_user
    does not become model input
```

Later isolated qualification additionally confirmed that authenticated-user identity material was absent from:

```text
ensemble inputs

LM synthesizer inputs
```

Therefore the source correspondence does not merely say:

```text
identity has no authority
```

It also preserves:

```text
identity metadata
    ≠
ordinary synthesized-content input
```

within the bounded qualified path.

---

# 20. Ordinary message flow remains distinct from identity flow

The ordinary conversational request has at least two conceptually distinct channels:

```text
CONTENT FLOW
browser message
    ↓
/api/chat
    ↓
Gateway
    ↓
reasoning / synthesis
```

and:

```text
IDENTITY FLOW
server-authenticated context
    ↓
/api/chat
    ↓
authenticated_user metadata
    ↓
Gateway boundary
    ↓
not consumed as content or authority
```

R2 depends on preserving this distinction.

If identity and message content were collapsed into one caller-controlled body, TCHAT-A/B correspondence would fail.

---

# 21. Source fields that carry the R2 boundary

The retained source record supports these exact field names:

```text
authenticated_user
user_id
message
```

Gateway correspondence additionally establishes:

```text
payload.authenticated_user
```

The public record should not invent additional R2 field names unless they are separately captured from source.

---

# 22. Source functions/routes that carry the R2 boundary

The retained source record supports these exact implementation functions/routes:

```text
POST /api/chat

POST /chat

process_unified
```

and the source object:

```text
lib/server-auth.js
```

The exact internal `server-auth.js` function identifier is not promoted here because the retained public evidence used for this crosswalk establishes the source object and semantics, not a controlling function name.

That is a deliberate evidence boundary.

---

# 23. Related frontend source objects

The R2 source snapshot also includes:

```text
app/ask/ConversationClient.jsx
app/ask/layout.js
```

Their roles are supporting:

```text
ConversationClient.jsx
    →
browser message submission to /api/chat
```

```text
layout.js
    →
frontend composition
```

Neither file is an identity authority merely because it participates in the conversational UI tree.

---

# 24. Model/source correspondence matrix

| Formal object | Formal field/property | Exact source object/function/field | Correspondence result |
|---|---|---|---|
| TCHAT-A | `session.identity` | `lib/server-auth.js` + `/api/chat` server-derived `authenticated_user` | mapped |
| TCHAT-A | `chat.authenticatedUser` | `authenticated_user` | mapped |
| TCHAT-B | browser body is non-authoritative | `ConversationClient.jsx` message body vs server-derived `/api/chat` identity | mapped |
| TCHAT-C | `canonicalUserId = none` | `user_id: null` | mapped |
| TCHAT-D | session identity isolation | server-auth session A/B → separate `/api/chat` request identities | mapped to bounded behavior contract |
| TCHAT-E | `authority = noAuthority` | `process_unified` accepts but does not consume `authenticated_user`; authority effect NO | mapped |
| TCHAT-F | `secretDisclosureAuthorized = false` | no H_people retrieval / no `/gateway/hp/query` in bounded ordinary path | mapped |
| Supporting | ordinary message | `message` field | mapped |
| Supporting | Gateway identity carriage | `ChatPayload.authenticated_user`, `payload.authenticated_user` | mapped |
| Supporting | model-context exclusion | authenticated-user object does not enter JCP or downstream model input | mapped |

---

# 25. What this crosswalk does not claim

This document does **not** claim:

```text
R2 theorem proof
    =
automatic production correspondence
```

It does not claim:

```text
one source snapshot
    =
perpetual source correspondence
```

It does not claim:

```text
server-auth source object identified
    =
all auth implementations universally proven
```

It does not claim:

```text
authenticated_user inert in this path
    =
all private-state paths proven
```

It does not claim:

```text
Gateway carries identity
    =
Gateway may disclose identity
```

It does not claim:

```text
model-to-source correspondence
    =
source-to-runtime identity
```

It does not claim:

```text
source-to-runtime identity
    =
live theorem-specific behavior
```

It does not claim:

```text
SYSTEM_PROVEN=YES
```

---

# 26. Revalidation rule

Any claim-bearing change to the following requires renewed correspondence analysis:

```text
app/api/chat/route.js

lib/server-auth.js

app/ask/ConversationClient.jsx

Gateway ChatPayload

/chat handler

process_unified

authenticated_user handling

user_id handling

JCP admission behavior

H_people/private-state routing
```

The formal R2 theorem may remain valid as a theorem.

The implementation correspondence does not automatically transfer.

Preserve:

```text
proof object unchanged
    ≠
new source corresponded
```

---

# 27. Relationship to source-to-runtime correspondence

This document ends at source semantics.

The next layer asks:

```text
Is the running frontend/Gateway exactly the qualified source?
```

Later production evidence recorded a qualified Gateway source identity:

```text
a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f
```

and a corresponding production image/container identity.

Those records belong in:

```text
correspondence/conversational-admission/source-to-runtime.md
```

or the appropriate conversational-path runtime correspondence record.

They should not be collapsed into this file.

---

# 28. Relationship to live observation

Live behavioral evidence is another separate layer.

Examples include:

```text
unauthenticated /api/chat fails closed

authenticated /api/chat reaches the qualified Gateway path

real local /chat completes through current downstream services
```

Those observations may strengthen correspondence.

They are not source semantics.

This file therefore does not promote itself to a runtime closeout.

---

# 29. Relationship to authority

Neither theorem proof nor correspondence grants authority.

```text
R2 theorem proven
    ≠
deployment authorized
```

```text
source semantics correspond
    ≠
production mutation authorized
```

```text
authenticated identity available
    ≠
governance authority
```

```text
authenticated identity available
    ≠
H_people SECRET disclosure authority
```

Operational authority remains a separate governed object.

---

# 30. Normalized model-to-source crosswalk

```yaml
r2_model_to_source:
  domain: LEAN_R2_CONVERSATIONAL_ADMISSION
  layer: MODEL_TO_SOURCE

  formal:
    lean_version: "4.34.0"
    principal_theorems: 6
    proof_holes: 0
    final_theorem_level_axiom_dependencies: 0

  frontend_source_root:
    path: /home/cakidd/allis-conversational-investigation-20260925T204513Z/r16c4r18a3-correct-registration-notice-placement-20261002T190827Z-2402886/frontend-candidate

  frontend_objects:
    api_chat:
      path: app/api/chat/route.js
      role: server_side_ordinary_chat_admission
      trusted_identity_field: authenticated_user
      canonical_scalar_user_field: user_id
      canonical_scalar_user_value_when_absent: null

    server_auth:
      path: lib/server-auth.js
      role: server_side_authenticated_identity_source

    conversation_client:
      path: app/ask/ConversationClient.jsx
      role: browser_message_submission
      trusted_identity_authority: false

    ask_layout:
      path: app/ask/layout.js
      role: frontend_composition
      trusted_identity_authority: false

  gateway:
    qualified_source_sha256: a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f
    route: /chat
    fields:
      - authenticated_user
      - user_id
      - message
    functions:
      - process_unified
    semantics:
      chat_passes_payload_authenticated_user: true
      process_unified_accepts_authenticated_user: true
      process_unified_reads_authenticated_user: false
      authenticated_user_forwarded_downstream: false
      authenticated_user_enters_jcp: false
      authenticated_user_becomes_model_input: false
      authenticated_user_authority_effect: false
      authenticated_user_content_effect: false

  theorem_crosswalk:
    TCHAT-A:
      formal: TCHAT_A_server_derived_authenticated_identity
      source:
        - lib/server-auth.js
        - app/api/chat/route.js
        - authenticated_user

    TCHAT-B:
      formal: TCHAT_B_browser_identity_is_nonauthoritative
      source:
        - app/ask/ConversationClient.jsx
        - app/api/chat/route.js
        - lib/server-auth.js

    TCHAT-C:
      formal: TCHAT_C_canonical_scalar_user_id_not_invented
      source:
        - app/api/chat/route.js
        - user_id
      qualified_absent_value: null

    TCHAT-D:
      formal: TCHAT_D_distinct_authenticated_sessions_remain_identity_isolated
      source:
        - lib/server-auth.js
        - app/api/chat/route.js
        - authenticated_user
      bounded_behavior_contract: REAL_SESSION_A_B_ISOLATION

    TCHAT-E:
      formal: TCHAT_E_ordinary_chat_does_not_create_governance_authority
      source:
        - ChatPayload.authenticated_user
        - /chat
        - payload.authenticated_user
        - process_unified
      authority_effect: false

    TCHAT-F:
      formal: TCHAT_F_ordinary_chat_does_not_authorize_hpeople_secret_disclosure
      source:
        - ordinary_chat_path
      hp_query_permitted_by_ordinary_chat: false
      hpeople_retrieval_in_bounded_path: false

  boundaries:
    theorem_proof_equals_source_correspondence: false
    source_correspondence_equals_runtime_correspondence: false
    runtime_correspondence_equals_live_observation: false
    correspondence_equals_operational_authority: false
    system_proven: false
```

---

# 31. Final correspondence statement

```text
LEAN_R2_FORMAL_DOMAIN=QUALIFIED

R2_MODEL_TO_SOURCE_CROSSWALK=PRESENT

API_CHAT_SOURCE_BOUND=YES

SERVER_AUTH_SOURCE_BOUND=YES

AUTHENTICATED_USER_FIELD_BOUND=YES

USER_ID_NULL_NONINVENTION_BOUND=YES

GATEWAY_CHATPAYLOAD_BOUND=YES

GATEWAY_CHAT_ROUTE_BOUND=YES

PROCESS_UNIFIED_BOUND=YES

AUTHENTICATED_USER_USED_AS_AUTHORITY=NO

AUTHENTICATED_USER_USED_AS_MODEL_CONTENT=NO

AUTHENTICATED_USER_ADMITTED_TO_JCP=NO

ORDINARY_CHAT_AUTHORIZES_HPEOPLE_SECRET_DISCLOSURE=NO

MODEL_TO_SOURCE_EQUALS_SOURCE_TO_RUNTIME=NO

FORMAL_PROOF_EQUALS_IMPLEMENTATION_CORRESPONDENCE=NO

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **Theorem proof does not stand in for source correspondence.**

> **Trusted conversational identity is bound to the server-side authentication source, not browser-controlled content.**

> **`user_id: null` is a meaningful non-invention boundary, not missing implementation data to be silently filled.**

> **The Gateway may carry `authenticated_user` without consuming it as content or authority.**

> **Ordinary chat does not become an H_people SECRET-disclosure path merely because the caller is authenticated.**

> **Source correspondence is bounded to exact source objects and must be re-earned when claim-bearing source changes.**

> **SYSTEM_PROVEN remains NO.**
