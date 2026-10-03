<div align="center">

# ALLIS — Gateway-to-Synthesis Conversational Path

### Qualified observed server-side path from Unified Gateway through BBB, `llm20production`, and LM Synthesizer, with browser E2E kept separate

<br>

![Path](https://img.shields.io/badge/PATH-GATEWAY_%E2%86%92_BBB_%E2%86%92_LLM20PRODUCTION_%E2%86%92_SYNTHESIZER-2563eb?style=for-the-badge)
![Observation](https://img.shields.io/badge/QUALIFIED_OBSERVATION-PASS-22c55e?style=for-the-badge)
![Gateway](https://img.shields.io/badge/GATEWAY-PRODUCTION_SOURCE_MATCHED-0ea5e9?style=for-the-badge)
![Browser](https://img.shields.io/badge/BROWSER_E2E-SEPARATE_NOT_YET_DEMONSTRATED-f59e0b?style=for-the-badge)
![System](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document records the **qualified observed server-side conversational path**:
>
> ```text
> Unified Gateway
>     ↓
> BBB
>     ↓
> llm20production
>     ↓
> LM Synthesizer
>     ↓
> response
> ```
>
> It does **not** claim that the current browser user interface has separately demonstrated a complete authenticated browser-to-response E2E path.
>
> Preserve:
>
> ```text
> qualified server-side conversational path
>     ≠
> demonstrated browser E2E
> ```

---

# 1. Purpose

The purpose of this record is to preserve the current observed conversational correspondence after the Unified Gateway production cutover.

The evidence shows that the current qualified Gateway path completed through:

```text
BBB
    ↓
llm20production
    ↓
LM Synthesizer
```

and returned a response through the server-side conversational path.

This is the present downstream reasoning/synthesis baseline.

---

# 2. Qualified observed path

The observed path is:

```text
/chat
    ↓
Unified Gateway
    ↓
BBB
    ↓
llm20production
    ↓
LM Synthesizer
    ↓
response
```

This record focuses on the server-side portion beginning at the Unified Gateway boundary.

---

# 3. Gateway production state

The corrected production Gateway cutover succeeded under:

```text
R16C4R20R4
```

The live Gateway source matched the qualified candidate source.

Qualified Gateway source SHA-256:

```text
a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f
```

---

# 4. Production cutover record

Production record:

```text
R16C4R20R4
```

Full record label:

```text
R16C4R20R4 - r16c4r20r4-corrected-production-gateway-cutover-20261003T011108Z-2966359
```

Final SHA-256:

```text
1aaccf30781dc38f2ad10446bce30f3d9f8eb047a560e9b34de2cb94aa0b6f44
```

Manifest SHA-256:

```text
213eeb4ab6511ff78d5c1df9791d46917e0c055342bc65e2ab054e4a75e5bcbc
```

---

# 5. Production Gateway runtime identity

Production container:

```text
6056e7c7848af2e676bbc53c6c909e3844bdec2f1c5a5832b7599e237bce3481
```

Production image:

```text
sha256:f2ee4e106373a321f65ab2eef00cf7d3b09cf1bdcf61bfb44ed79ec977f6444b
```

Qualified production source:

```text
a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f
```

---

# 6. Production cutover result

The corrected cutover established:

```text
PRODUCTION_CUTOVER=PASS

FROZEN_RUNTIME_CONTRACT=PASS

HTTP_READINESS=PASS

REAL_CHAT_REQUEST=PASS

BBB_COMPLETE=PASS

ENSEMBLE_COMPLETE=PASS

LM_SYNTHESIZER_COMPLETE=PASS
```

This is the core observed conversational-path evidence.

---

# 7. Gateway boundary

The Unified Gateway is the server-side rejoin/orchestration point for the qualified current conversational path.

Its role in this record is:

```text
receive bounded conversational request
    ↓
preserve current Gateway/JCP contract
    ↓
invoke downstream reasoning path
```

The current production source identity is explicit and sealed.

---

# 8. BBB stage

The observed server-side path completed through:

```text
BBB
```

BBB is therefore part of the qualified observed current conversational path.

The presence of BBB in this path should be treated as a runtime/source correspondence fact, not as a whole-system theorem.

---

# 9. `llm20production` stage

After BBB, the observed path completed through:

```text
llm20production
```

Preserve:

```text
llm20production
    =
current service/path name
```

not:

```text
formal theorem that exactly twenty model instances always participate
```

The name is an implementation/service identity, not a cardinality proof.

---

# 10. Ensemble completion

The production cutover recorded:

```text
ENSEMBLE_COMPLETE=PASS
```

This means the bounded current server-side request reached and completed the ensemble stage under the qualified runtime.

It does not prove:

```text
all possible ensemble branches

all future ensemble versions

all model-quality properties
```

---

# 11. LM Synthesizer stage

The observed path then completed through:

```text
LM Synthesizer
```

The production cutover recorded:

```text
LM_SYNTHESIZER_COMPLETE=PASS
```

The synthesizer remains the downstream response-composition stage in the current observed path.

---

# 12. End-to-end server-side completion

The strongest bounded statement is:

```text
Unified Gateway
    ↓
BBB
    ↓
llm20production
    ↓
LM Synthesizer
    ↓
response
```

completed under the qualified production runtime.

---

# 13. Real local `/chat` observation

The production qualification included a real local:

```text
/chat
```

request.

That request completed through the downstream reasoning/synthesis chain.

Preserve:

```text
REAL_LOCAL_CHAT=PASS
```

for the qualified bounded observation.

---

# 14. `/chat` and `/api/chat` are different boundaries

The local production Gateway observation used the Gateway `/chat` path.

The browser-facing server route remains:

```text
/api/chat
```

These are related but distinct boundaries.

Preserve:

```text
/api/chat
    ≠
Gateway /chat
```

even though `/api/chat` may call into the Gateway `/chat` contract.

---

# 15. Browser E2E is intentionally separate

The current browser-facing route has not been separately demonstrated as a complete authenticated browser E2E flow under the current UI state.

Therefore preserve:

```text
SERVER_SIDE_CONVERSATIONAL_PATH_QUALIFIED=YES

AUTHENTICATED_BROWSER_CHAT_E2E_DEMONSTRATED=NO
```

---

# 16. Durable server/UI-boundary closeout

The later durable server/UI-boundary closeout was:

```text
R16C4R20R5R1
```

Full record label:

```text
R16C4R20R5R1 - r16c4r20r5r1-durable-server-closeout-ui-boundary-20261003T012222Z-2987101
```

Final SHA-256:

```text
79c7ceaf7549543e194176881b9b4b77c8766057c8f2d8f281d3f596502ffbb6
```

Manifest SHA-256:

```text
37b1811a20107c08a0d1eb11c9d0e10a69fcec3e8bc7589f203d9c006d3461f6
```

---

# 17. Durable server closeout result

The durable closeout preserved:

```text
Gateway identity = PASS

frontend identity = PASS

auth identity = PASS

unauthenticated /api/auth/me = fail closed

unauthenticated /api/chat = fail closed

server-side authenticated route = qualified/deployed
```

This strengthens the server-side path without converting the current UI into a demonstrated browser E2E path.

---

# 18. Browser UI current-state flags

The durable closeout recorded:

```text
CURRENT_BROWSER_CONVERSATIONAL_UI_READY=NO

CURRENT_BROWSER_CONVERSATIONAL_SEND_SURFACE=NO

AUTHENTICATED_BROWSER_CHAT_E2E=NOT_EXECUTABLE_CURRENT_UI
```

These flags must remain explicit.

---

# 19. Why browser E2E is not implied

The following is invalid:

```text
server-side /api/chat route qualified
    +
Gateway /chat qualified
    +
downstream synthesis qualified
    =
browser E2E demonstrated
```

The browser user-facing surface must be separately exercised.

---

# 20. Browser E2E successor requirement

A future browser E2E qualification should demonstrate:

```text
actual user-facing send surface
    ↓
authenticated browser session
    ↓
/api/chat
    ↓
Unified Gateway
    ↓
BBB
    ↓
llm20production
    ↓
LM Synthesizer
    ↓
browser-visible response
```

under the actual production UI.

---

# 21. Browser E2E evidence should be independent

The future browser E2E closeout should have its own:

```text
source identity

frontend build identity

auth identity

browser session identity

request evidence

response evidence

runtime identities

manifest/seal
```

Do not retroactively relabel the server-side record as browser E2E.

---

# 22. Current frontend deployment identity

The current production frontend cutover used:

```text
/opt/msjarvis-rebuild/allis-frontend-runtime/deploy-9KyheKDYXyNCclA1YrUAX-fullnm-3ace386dedd9
```

BUILD_ID:

```text
9KyheKDYXyNCclA1YrUAX
```

Service:

```text
allis-frontend.service
```

This identifies the deployed frontend generation associated with the current server-side route.

---

# 23. Current frontend source lineage

The live frontend was produced from:

```text
r16c4r18a3-correct-registration-notice-placement-20261002T190827Z-2402886/frontend-candidate
```

This source lineage is relevant to the `/api/chat` server route.

It does not by itself demonstrate browser send-surface execution.

---

# 24. Frontend cutover record

The controlling frontend production cutover was:

```text
r16c4r18a4-frontend-production-cutover-20261002T191856Z-2417338
```

Final SHA-256:

```text
48156cf5595ea93093439c9d199d91e60d1236603b971d4b4938fc0cbb3a2cb6
```

Manifest SHA-256:

```text
40f79d6ce944ce7be096fe4d3ccc286457ed3d0de72f65203bfb9b1fb747c95d
```

---

# 25. `/chatlight` is not canonical

Preserve:

```text
/chatlight
    ≠
canonical ordinary conversational route
```

It was a prior inventory artifact.

The current ordinary browser-facing server route is:

```text
/api/chat
```

and the current Gateway route is:

```text
/chat
```

---

# 26. `/api/chat/async` remains separate

Preserve:

```text
/api/chat/async
    ≠
ordinary /api/chat route
```

The asynchronous route is a separate path and should not be substituted for this qualified conversational record.

---

# 27. Current downstream observation and R2

The Gateway-to-synthesis path complements R2 conversational-admission correspondence.

R2 establishes:

```text
trusted server-derived identity

browser identity non-authority

ordinary chat noncreation of governance authority
```

The Gateway-to-synthesis record establishes the observed downstream server path.

These are related but separate evidence domains.

---

# 28. Current downstream observation and R3

The Gateway-to-synthesis path also complements R3.

R3 establishes the current four-field JCP and Hilbert nonadmission.

The production Gateway path completing through BBB/ensemble/synthesis did not imply a Hilbert schema expansion.

Preserve:

```text
successful synthesis
    ≠
Hilbert JCP admission
```

---

# 29. Cognition relation

The current architecture intends cognition rejoin through:

```text
llm_packet
    ↓
Gateway/JCP
    ↓
ensemble
    ↓
synthesizer
```

The present Gateway-to-synthesis observation qualifies the downstream side of that future cognition rejoin.

It does not by itself prove the upstream cognition-stage composition.

---

# 30. MainBrain relation

The current Gateway-to-synthesis path is separate from MainBrain activation history.

Do not infer:

```text
MainBrain activated
```

merely because:

```text
Gateway -> BBB -> llm20production -> LM Synthesizer
```

completed.

---

# 31. Authority boundary

The observed conversational path does not create:

```text
DGM adoption authority

publication authority

H_people SECRET disclosure authority

protected-state mutation authority
```

Completion through the synthesizer is a conversational response event, not a governance transition.

---

# 32. Response is not governed publication

Preserve:

```text
synthesized conversational response
    ≠
governed publication
```

Publication remains a separate authority path.

---

# 33. Response is not persistent learning

Likewise:

```text
synthesized response
    ≠
persistent corpus admission
```

and:

```text
synthesized response
    ≠
qualified Hilbert state
```

---

# 34. Qualified observation is point-in-time

The Gateway-to-synthesis observation is:

```text
POINT_IN_TIME
```

A future source/runtime change requires requalification.

Preserve:

```text
current qualified path
    ≠
permanent path guarantee
```

---

# 35. Revalidation triggers

Revalidate this path if claim-bearing changes occur to:

```text
Unified Gateway

/chat route

BBB

llm20production

ensemble adapter

LM Synthesizer

response assembly

/api/chat Gateway adapter

frontend browser send surface
```

---

# 36. What is currently qualified

The strongest safe current statement is:

```text
QUALIFIED_OBSERVED_SERVER_PATH=
Unified Gateway
-> BBB
-> llm20production
-> LM Synthesizer
-> response
```

with the production Gateway source identity and cutover evidence sealed.

---

# 37. What is not currently qualified by this record

This document does not establish:

```text
AUTHENTICATED_BROWSER_CHAT_E2E=PASS
```

It does not establish:

```text
CURRENT_BROWSER_CONVERSATIONAL_UI_READY=YES
```

It does not establish:

```text
FULL_BROWSER_USER_JOURNEY_QUALIFIED=YES
```

---

# 38. What is not a theorem claim

This record does not assert formal proof that:

```text
every request always reaches synthesis
```

or:

```text
all downstream model outputs are correct
```

or:

```text
llm20production always invokes an exact fixed number of models
```

It records a bounded observed production path.

---

# 39. Rollback state

The production Gateway cutover retained rollback:

```text
jarvis-unified-gateway.rollback-r20r4-20261003T011108Z-2966359
```

Rollback image:

```text
sha256:d52c4a716d491158c66240251c7e158752c2c9afa0a03afaffd9ed747bf2107b
```

State:

```text
stopped retained
```

Rollback retirement was not authorized.

---

# 40. Rollback retention does not weaken path qualification

Preserve:

```text
rollback retained
    ≠
production path unqualified
```

Rollback retention is a deployment-safety property.

It does not negate the successful qualified cutover.

---

# 41. Server-side path matrix

| Boundary | Current status |
|---|---|
| Unified Gateway production source | qualified/live |
| `/chat` local production request | PASS |
| BBB | completed |
| `llm20production` | completed |
| LM Synthesizer | completed |
| server-side response completion | PASS |
| `/api/chat` server-side route | qualified/deployed |
| unauthenticated `/api/chat` | fail closed |
| browser send surface | not currently ready |
| authenticated browser E2E | not executable in current UI |

---

# 42. Normalized correspondence record

```yaml
gateway_to_synthesis:
  status: QUALIFIED_OBSERVED_SERVER_PATH

  path:
    - Unified_Gateway
    - BBB
    - llm20production
    - LM_Synthesizer
    - response

  gateway:
    qualified_source_sha256:
      a007f51d53b0c253260d3ca28413de00c2abd4c29ca62bde2adccda5423f5e1f

    production:
      record: R16C4R20R4
      final_sha256:
        1aaccf30781dc38f2ad10446bce30f3d9f8eb047a560e9b34de2cb94aa0b6f44
      manifest_sha256:
        213eeb4ab6511ff78d5c1df9791d46917e0c055342bc65e2ab054e4a75e5bcbc
      container:
        6056e7c7848af2e676bbc53c6c909e3844bdec2f1c5a5832b7599e237bce3481
      image:
        sha256:f2ee4e106373a321f65ab2eef00cf7d3b09cf1bdcf61bfb44ed79ec977f6444b

  observations:
    production_cutover: PASS
    frozen_runtime_contract: PASS
    http_readiness: PASS
    real_local_chat: PASS
    BBB_complete: PASS
    ensemble_complete: PASS
    LM_synthesizer_complete: PASS

  frontend:
    build_id: 9KyheKDYXyNCclA1YrUAX
    service: allis-frontend.service

  durable_server_closeout:
    record: R16C4R20R5R1
    final_sha256:
      79c7ceaf7549543e194176881b9b4b77c8766057c8f2d8f281d3f596502ffbb6
    manifest_sha256:
      37b1811a20107c08a0d1eb11c9d0e10a69fcec3e8bc7589f203d9c006d3461f6

  browser_boundary:
    current_browser_conversational_ui_ready: false
    current_browser_send_surface: false
    authenticated_browser_chat_e2e: NOT_EXECUTABLE_CURRENT_UI

  rollback:
    retained: true
    retired: false

  nonclaims:
    browser_e2e_demonstrated: false
    whole_system_proven: false
    model_accuracy_proven: false
    permanent_correspondence: false
```

---

# 43. Final correspondence statement

```text
GATEWAY_TO_SYNTHESIS_CORRESPONDENCE=QUALIFIED_OBSERVED

PATH:
Unified_Gateway
-> BBB
-> llm20production
-> LM_Synthesizer
-> response

REAL_LOCAL_CHAT=PASS

BBB_COMPLETE=PASS

ENSEMBLE_COMPLETE=PASS

LM_SYNTHESIZER_COMPLETE=PASS

SERVER_SIDE_CONVERSATIONAL_PATH_QUALIFIED=YES

CURRENT_BROWSER_CONVERSATIONAL_UI_READY=NO

CURRENT_BROWSER_CONVERSATIONAL_SEND_SURFACE=NO

AUTHENTICATED_BROWSER_CHAT_E2E=NOT_EXECUTABLE_CURRENT_UI

BROWSER_E2E_DEMONSTRATED=NO

CORRESPONDENCE_IS_POINT_IN_TIME=YES

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **The current server-side conversational path has been observed through Unified Gateway → BBB → `llm20production` → LM Synthesizer → response.**

> **The Gateway production source and runtime identities are sealed independently of the observation.**

> **A real local `/chat` request completed the qualified downstream path.**

> **The ordinary browser-facing route remains `/api/chat`; `/chatlight` is not canonical.**

> **`/api/chat/async` is a separate route.**

> **Server-side qualification does not imply browser E2E qualification.**

> **The current browser conversational send surface remains not ready, so authenticated browser E2E remains separately unproven.**

> **The browser E2E successor must demonstrate the actual user-facing route under the real production UI.**

> **Successful conversational synthesis does not create governance authority, publication authority, persistent learning, or Hilbert admission.**

> **This correspondence is point-in-time and must be re-earned after claim-bearing implementation changes.**

> **SYSTEM_PROVEN remains NO.**
