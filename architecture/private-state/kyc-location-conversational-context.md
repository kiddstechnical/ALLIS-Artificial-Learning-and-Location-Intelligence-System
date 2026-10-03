<div align="center">

# ALLIS — KYC Location Conversational Context

### Protected location boundary for authoritative KYC/SECRET state, minimum-necessary conversational context, disclosure control, and non-public persistence semantics

<br>

![Domain](https://img.shields.io/badge/DOMAIN-H__PEOPLE_LOCATION-7c3aed?style=for-the-badge)
![Source](https://img.shields.io/badge/AUTHORITATIVE_LOCATION-KYC_SECRET-f97316?style=for-the-badge)
![Conversation](https://img.shields.io/badge/CONVERSATIONAL_USE-MINIMUM_NECESSARY-2563eb?style=for-the-badge)
![Disclosure](https://img.shields.io/badge/USE_%E2%89%A0_DISCLOSURE-22c55e?style=for-the-badge)
![Public](https://img.shields.io/badge/PUBLIC_PROMOTION-NO-f59e0b?style=for-the-badge)
![Status](https://img.shields.io/badge/QUALIFICATION-FUTURE_WORK-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> Exact authoritative location belongs to the protected KYC/SECRET identity domain.
>
> Ordinary conversation does **not** receive unrestricted access to that precise SECRET location.
>
> A separately authorized, minimum-necessary derived location context may be used for bounded conversational recognition.
>
> Preserve:
>
> ```text
> location known
>     ≠
> location disclosed
> ```
>
> ```text
> location used for permitted context
>     ≠
> location made PUBLIC
> ```
>
> Current status:
>
> ```text
> KYC_LOCATION_CONTEXT_USE_QUALIFIED=NO
> ```

---

# 1. Purpose

This document defines the protected location mechanism for conversational use.

The design separates:

```text
authoritative precise location
```

from:

```text
derived minimum-necessary conversational context
```

and from:

```text
PUBLIC location state
```

These are different states with different authority requirements.

---

# 2. Authoritative location source

The authoritative location source belongs to:

```text
KYC / H_people SECRET
```

This may include precise identity-correspondence location material such as:

- exact street address;
- verified residential location;
- custody-linked address;
- KYC-derived location;
- other protected identity-bound location records.

The exact authoritative location remains protected.

---

# 3. Location privacy classification

The starting classification is:

```text
PRECISE_AUTHORITATIVE_LOCATION=SECRET
```

That classification does not change merely because the system can technically access the value.

Preserve:

```text
available
    ≠
disclosable
```

and:

```text
authenticated user
    ≠
authorized recipient of raw SECRET location
```

---

# 4. Ordinary conversation boundary

Ordinary authenticated conversation does not receive unrestricted KYC/SECRET location.

Therefore:

```text
ORDINARY_CHAT_RAW_SECRET_LOCATION_ACCESS=NO
```

and:

```text
ORDINARY_CHAT_SECRET_LOCATION_DISCLOSURE_AUTHORITY=NO
```

This is consistent with the broader H_people rule that ordinary authenticated chat does not itself authorize SECRET disclosure.

---

# 5. Minimum-necessary derived context

A future qualified mechanism may derive a bounded conversational location context from the authoritative SECRET source.

Conceptually:

```text
precise KYC/SECRET location
    ↓
authorized minimum-necessary projection
    ↓
derived conversational location context
```

The derived context may be less precise than the source.

Examples may include:

```text
city
county
region
state
service area
generalized geographic context
```

depending on the actual conversational need and authorization.

---

# 6. Minimum-necessary rule

The projection should disclose or expose only the least precise context needed for the permitted conversational purpose.

The governing rule is:

```text
minimum necessary
```

not:

```text
maximum available precision
```

The system should ask:

- What conversational purpose requires location?
- What precision is actually necessary?
- Can the purpose be satisfied with city/county/region rather than street address?
- Does the model need the raw value or only a derived label?
- Can the response be generated without exposing the source location at all?

---

# 7. Conversational recognition

The intended use is bounded recognition/contextualization.

For example:

```text
system recognizes relevant geographic context
```

without:

```text
system reveals exact address
```

This permits a future architecture in which ALLIS can reason with a minimum-necessary location context while protecting the underlying SECRET record.

---

# 8. Use is not disclosure

The central rule is:

```text
USE ≠ DISCLOSURE
```

The system may use protected state internally under authority without revealing the source value outward.

Therefore:

```text
location used to inform response
    ≠
location disclosed in response
```

This distinction must remain explicit in code, formal models, and documentation.

---

# 9. Disclosure boundary

A response should not expose the exact authoritative location unless a separate SECRET-disclosure authority exists.

Preserve:

```text
CONTEXTUAL_USE_AUTHORITY
    ≠
SECRET_DISCLOSURE_AUTHORITY
```

A permitted contextual-use path may authorize:

```text
derive general location context
```

while prohibiting:

```text
return exact source location
```

---

# 10. PUBLIC-state boundary

A location does not become PUBLIC merely because it influenced a response.

Preserve:

```text
used in conversation
    ≠
PUBLIC
```

and:

```text
derived from SECRET
    +
used internally
    ≠
PUBLIC projection
```

PUBLIC classification requires its own governed basis.

---

# 11. Persistence boundary

A derived location context should not automatically become persistent conversational state.

Preserve:

```text
derived for one request
    ≠
persisted
```

and:

```text
used for response
    ≠
saved to public profile
```

The mechanism should explicitly decide whether the derived context is:

```text
REQUEST_SCOPED

SESSION_SCOPED

PRIVATE_PERSISTENT

PUBLIC

NOT_PERSISTED
```

The default should not silently promote to durable/public state.

---

# 12. Request-scoped use

The safest initial conversational design is:

```text
REQUEST_SCOPED
```

where the derived location context exists only for the current request/response cycle unless a stronger qualified persistence rule exists.

This minimizes unnecessary retention.

---

# 13. Session-scoped use

A future implementation may permit:

```text
SESSION_SCOPED
```

location context if the purpose requires continuity.

Even then:

```text
session scope
    ≠
PUBLIC
```

and:

```text
session scope
    ≠
long-term durable profile
```

---

# 14. Private persistence

If derived location context is persisted privately, the system must define:

```text
why persistence is needed

what precision is stored

retention period

who can retrieve it

whether it can be refreshed

whether the source SECRET record remains separate
```

Private persistence requires separate authority.

---

# 15. Public promotion prohibition

The following transition is invalid by default:

```text
SECRET location
    ↓
used in conversation
    ↓
PUBLIC location
```

A public location claim requires separate publication/projection authority.

Use cannot silently create publication.

---

# 16. Precision reduction

A minimum-necessary location projection may reduce precision.

Conceptually:

```text
street address
    ↓
city / county / region
```

or:

```text
precise coordinate
    ↓
generalized area
```

The reduction should be deterministic/auditable enough to explain what precision was released.

---

# 17. Precision should match purpose

Example principle:

```text
need = recommend county-level resource
```

does not justify:

```text
street-level location
```

Likewise:

```text
need = identify state law
```

may require only:

```text
state
```

The purpose should constrain precision.

---

# 18. Recipient scope

The mechanism should identify the recipient of the derived context.

Possible recipients include:

```text
server-side routing logic

conversation reasoning context

specific tool

specific response renderer
```

Raw SECRET location should not be exposed to more recipients than necessary.

---

# 19. Model visibility

The design should explicitly decide whether the model receives:

```text
raw precise location
```

or:

```text
derived generalized context
```

The intended bounded design is:

```text
MODEL_RAW_SECRET_LOCATION=NO
```

unless separately justified.

Preferred:

```text
MODEL_DERIVED_MINIMUM_NECESSARY_CONTEXT=YES
```

when authorized.

---

# 20. Gateway boundary

If location context is passed through the Unified Gateway, the interface should be explicit.

Recommended fields:

```text
location_context
location_precision
location_source_class
location_use_scope
```

Do not pass the full KYC record merely to supply geographic context.

---

# 21. JCP boundary

Current R3 state does not include H_people as a live JCP field.

Therefore:

```text
H_PEOPLE_CURRENT_JCP_ADMISSION=NO
```

A future location-context mechanism must not silently convert the whole H_people SECRET domain into JCP state.

If a location-derived context later enters JCP, it requires a bounded successor design.

---

# 22. Derived context is not H_people admission

Preserve:

```text
derived location context
    ≠
H_people JCP admission
```

A derived geographic label may be a narrow contextual projection while the underlying H_people SECRET domain remains nonadmitted.

---

# 23. H_geo relationship

A future location-derived context may also relate to H_geo.

That relationship must be explicit.

Preserve:

```text
H_people SECRET location
    ↓
derived geographic projection
```

does not automatically mean:

```text
H_geo persistent admission
```

or:

```text
H_geo JCP admission
```

Both remain separate transitions.

---

# 24. KYC source identity

The mechanism should retain source-class identity internally.

Recommended metadata:

```text
source_class = KYC_SECRET

source_record_id

subject_id

verification_status

verified_at

precision_class
```

This helps distinguish authoritative KYC location from weaker inferred or public location sources.

---

# 25. Web-inferred location is not authoritative KYC location

Preserve:

```text
web-inferred location
    ≠
verified KYC location
```

and:

```text
public location clue
    ≠
identity-correspondence source
```

The system should not silently upgrade public research into authoritative SECRET KYC state.

---

# 26. Location confidence

A confidence score does not replace source classification.

For example:

```text
high-confidence inferred city
```

is still not:

```text
verified KYC city
```

The system should preserve:

```text
source type
```

separately from:

```text
confidence
```

---

# 27. Freshness

Location can change.

The mechanism should track:

```text
verified_at

valid_from

valid_until if known

last_confirmed

stale_after
```

A once-authoritative location may become stale.

---

# 28. Stale location

If the authoritative location is stale or uncertain:

```text
do not silently present it as current
```

Possible states:

```text
CURRENT

STALE

UNVERIFIED_CURRENTNESS

HISTORICAL
```

The derived conversational context should reflect the source state.

---

# 29. Geographic generalization

A future generalization function should define its precision output.

Examples:

```text
street → city

coordinate → county

city → state
```

The transformation should be explicit and reviewable.

---

# 30. Generalization is not anonymization guarantee

Preserve:

```text
less precise
    ≠
anonymous
```

A county or small locality can still be identifying in some contexts.

Privacy analysis must consider the subject and surrounding information.

---

# 31. Minimum-necessary contextual packet

A bounded packet may look conceptually like:

```yaml
location_context:
  source_class: KYC_SECRET_DERIVED
  precision: COUNTY
  value: <derived county>
  purpose: conversational_recognition
  disclosure_allowed: false
  persistence: REQUEST_SCOPED
```

This is illustrative architecture, not a current implementation claim.

---

# 32. Disclosure flag

The context packet should distinguish:

```text
usable_for_context = true
```

from:

```text
disclosable = false
```

This makes:

```text
use ≠ disclosure
```

machine-visible rather than relying only on prose.

---

# 33. Persistence flag

Likewise, the packet should distinguish:

```text
usable_now
```

from:

```text
may_persist
```

Possible fields:

```text
persistence_allowed

retention_scope

expires_at
```

---

# 34. Public-promotion flag

A separate field should indicate whether the derived context may become public.

Default:

```text
public_promotion_allowed = false
```

unless a separate public-state authority exists.

---

# 35. Authority dimensions

Location authority should be transition-specific.

Recommended matrix:

| Transition | Authority required |
|---|---|
| Read exact KYC location | KYC/SECRET read authority |
| Derive generalized context | contextual-use authority |
| Pass derived context to model | model-context authority |
| Reveal derived context in response | disclosure authority |
| Reveal exact location | SECRET disclosure authority |
| Persist derived context privately | persistence authority |
| Promote to PUBLIC | publication/public-state authority |

One authorization must not stand in for all seven.

---

# 36. Ordinary chat identity is insufficient

The fact that a user is authenticated establishes conversational identity.

It does not establish:

```text
KYC_SECRET_READ_AUTHORITY

SECRET_DISCLOSURE_AUTHORITY

PUBLICATION_AUTHORITY
```

Preserve:

```text
AUTHENTICATED
    ≠
AUTHORIZED_FOR_SECRET_LOCATION
```

---

# 37. Permanent SECRET disclosure rule

For exact protected identity correspondence, preserve the existing authority rule:

```text
VERIFIED_LEGAL_PROCESS_AUTHORITY
+
permitted disclosure class
+
subject/scope match
+
minimum necessary disclosure
+
receipt
+
immutable audit record
```

for the permitted external SECRET disclosure classes governed by that rule.

Ordinary conversational contextual use is a different transition.

---

# 38. Conversation should not expose source metadata unnecessarily

Even if the system uses an authoritative source, the user-facing response need not reveal:

```text
"this came from your KYC record"
```

unless there is a reason to do so.

Minimum necessary applies to source disclosure as well as value disclosure.

---

# 39. Recognition example

Permitted conceptual behavior:

```text
system knows the authorized derived context is:
Fayette County, West Virginia
```

and can use that to interpret:

```text
"my county"
```

without saying:

```text
"your exact address is ..."
```

The system uses the context.

It does not disclose the raw source.

---

# 40. Response example

A permitted response may say:

```text
For your county, the relevant rule is ...
```

if the derived county-level context is authorized for use.

That does not mean the county value becomes PUBLIC or permanently stored.

---

# 41. Non-disclosure response

The system may also use location without explicitly naming it.

For example:

```text
select correct jurisdictional information
```

then provide the answer without exposing the location itself.

This is a strong example of:

```text
use
    ≠
disclosure
```

---

# 42. Derived context should be purpose-bound

Recommended fields:

```text
purpose

permitted_consumer

permitted_action

precision

expiry
```

A context derived for:

```text
jurisdiction lookup
```

should not automatically be reusable for:

```text
public profile enrichment
```

---

# 43. Purpose change requires re-evaluation

Preserve:

```text
authorized for purpose A
    ≠
authorized for purpose B
```

If use changes, re-evaluate minimum necessary precision and authority.

---

# 44. Location context and automated learning

A location context used in conversation must not automatically enter the Automated Learning Graph as persistent knowledge.

Preserve:

```text
context used
    ≠
learning candidate
```

and:

```text
learning candidate
    ≠
persistent H_people state
```

---

# 45. Location context and research-to-corpus ingestion

The research-to-corpus pipeline must not ingest protected KYC-derived context as ordinary public research state.

KYC-derived location should remain in the protected private-state path unless separately transformed and authorized.

---

# 46. Location context and publication

A response informed by location does not create public-state authority.

Preserve:

```text
response used location
    ≠
location published
```

and:

```text
derived context existed
    ≠
public record created
```

---

# 47. Location context and DGM

The protected location mechanism is not itself a DGM authorized-adoption path.

If a future protected mutation requires DGM authority, that must be explicit.

Do not infer DGM from the fact that the state is sensitive.

---

# 48. Failure: no authority

If contextual-use authority is absent:

```text
DERIVED_LOCATION_CONTEXT=WITHHELD
```

The system should proceed without protected location if possible.

---

# 49. Failure: precision cannot be reduced safely

If the purpose cannot be satisfied without exposing excessive precision:

```text
CONTEXT_USE=BLOCKED_OR_HUMAN_REVIEW
```

Do not default to the raw location.

---

# 50. Failure: source stale

If authoritative source location is stale:

```text
CURRENT_LOCATION_CONTEXT=UNRESOLVED
```

The system should not fabricate currentness.

---

# 51. Failure: subject mismatch

If the protected location record does not match the authenticated subject:

```text
LOCATION_CONTEXT_USE=BLOCKED
```

Subject correspondence is required.

---

# 52. Failure: scope mismatch

If the authority covers one purpose/geographic scope and the requested use exceeds it:

```text
USE=BLOCKED
```

Authority must match the requested scope.

---

# 53. Failure: disclosure attempted from use-only context

If a component tries to disclose a context marked:

```text
disclosure_allowed=false
```

the system should fail closed.

---

# 54. Audit record

A future qualified mechanism should produce an audit record for protected-context use sufficient to reconstruct:

```text
subject

source class

derived precision

purpose

consumer

authority

use time

whether disclosure occurred

whether persistence occurred
```

The audit does not need to duplicate the raw SECRET value unnecessarily.

---

# 55. Receipt model

A bounded receipt may contain:

```yaml
location_context_receipt:
  subject_id:
  source_class: KYC_SECRET
  derived_precision:
  purpose:
  authority_id:
  used_at:
  disclosure_performed: false
  persistence_performed: false
  public_promotion_performed: false
```

This is a future architecture example.

---

# 56. Formalization candidates

A future formal family may include bounded properties such as:

```text
exact_kyc_location_is_secret

ordinary_chat_does_not_receive_raw_secret_location

authorized_context_use_may_derive_minimum_necessary_location

context_use_does_not_imply_disclosure

context_use_does_not_imply_public_promotion

use_only_context_blocks_disclosure

request_scoped_context_does_not_persist

subject_mismatch_blocks_location_context
```

These are candidate theorem areas.

Exact statements should follow the implementation.

---

# 57. Source implementation targets

A future implementation should make explicit:

```text
authoritative location source

subject correspondence function

minimum-necessary projection function

precision enum

context packet schema

context-use authority check

disclosure authority check

persistence flag

public-promotion flag

audit receipt
```

The implementation should not hide these semantics inside generic metadata.

---

# 58. Qualification tests

Before qualification, test:

```text
raw exact location withheld from ordinary chat

authorized city/county/state projection works

use-only context does not appear verbatim in response unless separately allowed

response can be correctly localized without revealing source location

derived context is not persisted when request-scoped

derived context is not promoted PUBLIC

subject mismatch blocks use

stale source blocks current-location assertion

no-authority path fails closed
```

---

# 59. Current status flags

```text
KYC_LOCATION_CONTEXT_DESIGN_DEFINED=YES

PRECISE_AUTHORITATIVE_LOCATION_CLASS=SECRET

ORDINARY_CHAT_RAW_SECRET_LOCATION_ACCESS=NO

MINIMUM_NECESSARY_DERIVED_CONTEXT_PLANNED=YES

CONTEXT_USE_EQUALS_DISCLOSURE=NO

CONTEXT_USE_EQUALS_PUBLIC_PROMOTION=NO

CONTEXT_USE_EQUALS_PERSISTENCE=NO

KYC_LOCATION_CONTEXT_USE_QUALIFIED=NO

SYSTEM_PROVEN=NO
```

---

# 60. Normalized architecture record

```yaml
kyc_location_conversational_context:
  status: FUTURE_QUALIFICATION_TARGET

  authoritative_source:
    domain: H_people
    class: SECRET
    kind: KYC_IDENTITY_CORRESPONDENCE

  ordinary_conversation:
    raw_secret_location_access: false
    raw_secret_location_disclosure: false

  derived_context:
    planned: true
    rule: MINIMUM_NECESSARY
    examples:
      - state
      - county
      - city
      - generalized_region

    source_remains_secret: true

  semantics:
    use_equals_disclosure: false
    use_equals_public_promotion: false
    use_equals_persistence: false

  authority:
    exact_location_read: separate_required
    derive_context: separate_required
    model_context_use: separate_required
    disclose_derived_context: separate_required
    disclose_exact_location: secret_disclosure_authority_required
    persist_derived_context: separate_required
    public_promotion: separate_required

  persistence:
    default_target: REQUEST_SCOPED_OR_NONE
    automatic_public_promotion: false

  jcp:
    H_people_current_admission: false
    derived_context_does_not_imply_H_people_admission: true

  H_geo:
    derived_context_does_not_imply_H_geo_persistence: true
    derived_context_does_not_imply_H_geo_jcp_admission: true

  failures:
    no_authority: WITHHOLD
    subject_mismatch: BLOCK
    stale_source: UNRESOLVED
    excessive_precision: BLOCK_OR_REDUCE
    use_only_context_disclosure_attempt: FAIL_CLOSED

  current_status:
    kyc_location_context_use_qualified: false
    system_proven: false
```

---

# 61. Final architecture statement

```text
KYC_LOCATION_CONVERSATIONAL_CONTEXT=FUTURE_DESIGN

AUTHORITATIVE_LOCATION_SOURCE=KYC_SECRET

PRECISE_LOCATION_CLASS=SECRET

ORDINARY_CHAT_RAW_SECRET_LOCATION_ACCESS=NO

ORDINARY_CHAT_SECRET_LOCATION_DISCLOSURE_AUTHORITY=NO

MINIMUM_NECESSARY_DERIVED_CONTEXT=PLANNED

DERIVED_CONTEXT_CAN_SUPPORT_CONVERSATIONAL_RECOGNITION=YES_WHEN_AUTHORIZED

LOCATION_USE_EQUALS_DISCLOSURE=NO

LOCATION_USE_EQUALS_PUBLIC_STATE=NO

LOCATION_USE_EQUALS_PERSISTENCE=NO

RAW_SECRET_LOCATION_AUTOMATICALLY_ENTERS_MODEL_CONTEXT=NO

H_PEOPLE_CURRENT_JCP_ADMISSION=NO

DERIVED_LOCATION_CONTEXT_IMPLIES_H_GEO_ADMISSION=NO

KYC_LOCATION_CONTEXT_USE_QUALIFIED=NO

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **Exact authoritative location lives in KYC/H_people SECRET state.**

> **Ordinary conversation does not receive unrestricted SECRET location.**

> **A minimum-necessary derived context may be used only under separate authority.**

> **Use does not equal disclosure.**

> **A response may be informed by location without revealing the source location.**

> **Location context does not become PUBLIC merely because it informed a response.**

> **Contextual-use authority, disclosure authority, persistence authority, and public-promotion authority are different transitions.**

> **The browser/session authentication boundary does not mint SECRET location authority.**

> **Derived location context does not imply H_people JCP admission or H_geo admission.**

> **KYC_LOCATION_CONTEXT_USE_QUALIFIED remains NO until implementation and qualification are complete.**

> **SYSTEM_PROVEN remains NO.**
