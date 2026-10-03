<div align="center">

# ALLIS — Read-Only Web Research

### Future bounded research mechanism for scheduled evaluation, conversational fallback, source-preserving retrieval, and zero external-side mutation

<br>

![Architecture](https://img.shields.io/badge/ARCHITECTURE-READ_ONLY_WEB_RESEARCH-2563eb?style=for-the-badge)
![Schedule](https://img.shields.io/badge/EVALUATION-%E2%89%88_EVERY_5_MINUTES-f59e0b?style=for-the-badge)
![Access](https://img.shields.io/badge/EXTERNAL_ACCESS-READ_ONLY-22c55e?style=for-the-badge)
![Writes](https://img.shields.io/badge/EXTERNAL_SIDE_WRITES-NO-f97316?style=for-the-badge)
![Provenance](https://img.shields.io/badge/PROVENANCE-SOURCE_DATE_QUERY_PRESERVED-7c3aed?style=for-the-badge)
![Status](https://img.shields.io/badge/QUALIFICATION-FUTURE_WORK-64748b?style=for-the-badge)

<br>

**Kidd's Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This document defines the **future read-only web-research mechanism** for ALLIS.
>
> It is an architecture and qualification target.
>
> It does **not** claim that autonomous web research or research-to-corpus ingestion is currently qualified.
>
> Current status remains:
>
> ```text
> AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED=NO
>
> RESEARCH_TO_CORPUS_INGESTION_QUALIFIED=NO
> ```
>
> The research mechanism is intentionally bounded:
>
> ```text
> external read
>     ≠
> external write
>     ≠
> qualified persistent knowledge
> ```

---

# 1. Purpose

The read-only web-research mechanism is intended to help ALLIS when the current qualified corpus does not contain enough information to answer a bounded user question or system research need.

Its role is:

```text
detect corpus insufficiency
    ↓
form bounded research query
    ↓
retrieve external information read-only
    ↓
preserve provenance
    ↓
evaluate source/result
    ↓
use result for current response where appropriate
```

It is not intended to:

- publish content externally;
- edit websites;
- submit forms;
- create accounts;
- alter records;
- make purchases;
- post messages;
- accept terms;
- create external transactions;
- persist every retrieved result into ALLIS.

---

# 2. Future scheduled evaluation

The intended research mechanism includes a scheduled evaluation loop running approximately every five minutes.

Target cadence:

```text
APPROXIMATE_EVALUATION_INTERVAL ≈ 5 minutes
```

The scheduler's job is not to browse continuously without purpose.

Its job is to inspect whether there is a bounded outstanding research need that requires evaluation.

Conceptually:

```text
every ~5 minutes
    ↓
check pending research needs
    ↓
evaluate whether bounded external lookup is required
    ↓
research only if permitted and still relevant
```

---

# 3. Scheduled evaluation is not unrestricted crawling

The five-minute cadence must not be interpreted as:

```text
crawl the web every five minutes
```

The intended behavior is:

```text
evaluate research queue every ~5 minutes
```

A cycle may legitimately perform:

```text
NO_RESEARCH_REQUIRED
```

if:

- no information gap exists;
- a prior gap is already resolved;
- the request expired;
- the research authority is absent;
- the source class is unavailable;
- the current corpus is sufficient.

---

# 4. Scheduler state

The future scheduler should operate on explicit research-need objects.

Recommended states:

```text
PENDING

READY_FOR_EVALUATION

WAITING_FOR_RESEARCH

RESEARCH_IN_PROGRESS

CANDIDATE_AVAILABLE

RESOLVED_FOR_RESPONSE

EXPIRED

BLOCKED

UNRESOLVED
```

The scheduler should not infer work from vague memory or model curiosity.

---

# 5. Trigger sources

A research need may originate from:

```text
ordinary conversation

cognition informational-insufficiency detection

scheduled monitoring task

manual research request

system maintenance / validation
```

Each trigger should preserve its purpose and scope.

---

# 6. Conversational fallback

The primary conversational behavior should remain corpus-first.

Conceptually:

```text
user asks question
    ↓
consult qualified current corpus / governed context
    ↓
is available knowledge sufficient?
```

If YES:

```text
answer from qualified available knowledge
```

If NO:

```text
consider bounded read-only web research
```

The external research path is therefore a fallback, not the default replacement for internal knowledge.

---

# 7. Corpus insufficiency condition

The research fallback should activate only when a bounded insufficiency can be identified.

Examples:

```text
missing current fact

missing recent update

missing official source

stale corpus item

insufficient geographic detail

insufficient technical documentation

conflicting internal evidence requiring external verification
```

The insufficiency should be recorded before querying.

---

# 8. Conversational fallback flow

```text
authenticated conversation
    ↓
current corpus / JCP / governed context
    ↓
insufficiency detected
    ↓
bounded research need
    ↓
read-only web research
    ↓
research candidate
    ↓
provenance validation
    ↓
candidate accepted for current-response use?
    ↓
yes → include in current response with provenance
no  → return uncertainty / insufficient information
```

Persistence is not implied by current-response use.

---

# 9. External access class

The future mechanism must use:

```text
READ_ONLY_EXTERNAL_WEB_ACCESS
```

This means external interactions are limited to information retrieval.

Allowed classes may include:

```text
HTTP GET / equivalent read

public API read

public document retrieval

public search

public metadata retrieval
```

subject to source and policy constraints.

---

# 10. Prohibited external actions

The research mechanism should not perform:

```text
POST

PUT

PATCH

DELETE
```

against external systems for research purposes.

It should also not:

- send emails;
- post comments;
- upload files;
- edit records;
- create tickets;
- submit applications;
- place orders;
- change account state;
- create credentials;
- follow actions that alter external state.

If such an action is ever needed, it belongs to a different authorized workflow.

---

# 11. Read-only invariant

A core future invariant should be:

```text
RESEARCH_EXTERNAL_SIDE_EFFECTS=NONE
```

Equivalent architectural rule:

```text
web research
    →
read external state
```

never:

```text
web research
    →
mutate external state
```

---

# 12. Source preservation

Every retrieved research result must preserve its source identity.

Recommended fields:

```text
source_url

source_domain

source_title

source_author

source_organization

source_type

source_identifier

retrieval_timestamp

publication_date

last_updated_date
```

where available.

Do not detach content from its source during research processing.

---

# 13. Date preservation

The research record should preserve at least:

```text
retrieved_at

source_published_at

source_updated_at
```

when available.

This prevents:

```text
old evidence
    →
presented as current
```

and supports freshness rules.

---

# 14. Query preservation

The system should preserve the exact or normalized research query that produced a candidate.

Recommended fields:

```text
query_text

query_scope

query_reason

research_need_id

requested_time_scope

requested_geographic_scope
```

This allows later reconstruction of why a source was retrieved.

---

# 15. Research provenance record

A minimum provenance object should contain:

```yaml
research_provenance:
  research_need_id:
  query:
  source_url:
  source_title:
  source_domain:
  source_author:
  source_organization:
  publication_date:
  updated_date:
  retrieved_at:
  source_class:
  transformation_history: []
```

This provenance travels with the research candidate.

---

# 16. Research result remains candidate state

The external result initially becomes:

```text
RESEARCH_CANDIDATE
```

not:

```text
QUALIFIED_KNOWLEDGE
```

Preserve:

```text
web result
    ≠
truth
```

and:

```text
web result
    ≠
persistent corpus state
```

---

# 17. Current-response use

A research candidate may be suitable for the **current user response** before it is suitable for persistent ingestion.

This distinction is intentional.

Conceptually:

```text
candidate
    ↓
source/provenance/relevance evaluation
    ↓
ACCEPTED_FOR_CURRENT_RESPONSE
```

without:

```text
PERSISTED_TO_CORPUS
```

---

# 18. Current-response eligibility

A candidate may be used for the current answer when:

```text
source is sufficiently relevant

source identity is preserved

date/currentness is suitable

claim scope matches source scope

material uncertainty is disclosed

privacy rules permit use

no stronger domain-specific admission is required merely to cite/use it ephemerally
```

This should remain separate from persistent learning.

---

# 19. Response citation/source trace

Where appropriate, the current response should preserve enough provenance to show:

```text
what external source supports the claim

when it was published/updated

when it was retrieved

why it was used
```

The response layer should not erase source boundaries.

---

# 20. Ephemeral use

A successful research fallback may terminate at:

```text
EPHEMERAL_RESPONSE_USE
```

with:

```text
PERSISTENCE=NO
```

This is especially appropriate for:

- recent news;
- current operating status;
- changing prices;
- current weather;
- volatile schedules;
- temporary public notices;
- time-sensitive technical status.

---

# 21. Ephemeral use is not learning persistence

Preserve:

```text
used in response
    ≠
learned durably
```

and:

```text
helpful in this conversation
    ≠
approved for corpus ingestion
```

---

# 22. Research candidate evaluation

Before current-response use, evaluate:

```text
relevance

source quality

freshness

jurisdiction/geographic match

time-period match

primary vs secondary source

conflicting sources

claim type

uncertainty

privacy
```

The evaluation can be lighter than persistent-ingestion qualification while still preserving provenance and scope.

---

# 23. Primary-source preference

Where the user asks for factual current information, prefer authoritative primary sources when available.

Examples include:

```text
official agency

official project documentation

original research publication

official product/service documentation

official public record
```

Secondary sources may still be useful but should retain their source class.

---

# 24. Conflict handling

If credible sources conflict:

```text
do not silently select one
```

Instead:

```text
preserve conflict
    ↓
identify source differences
    ↓
state uncertainty
```

The research mechanism should not turn disagreement into false certainty.

---

# 25. Freshness rules

Every research need should define an expected freshness horizon.

Examples:

```text
breaking event → hours / same day

software/runtime status → current build/version

policy/regulation → current effective version

historical fact → stable source acceptable

scientific fact → latest authoritative synthesis may matter
```

The scheduler should not re-research stable topics every five minutes.

---

# 26. Five-minute scheduler and freshness

The approximately five-minute evaluation loop does not mean every research candidate expires after five minutes.

The scheduler cadence and source freshness are separate concepts.

Preserve:

```text
scheduler frequency
    ≠
knowledge expiry
```

---

# 27. Research queue deduplication

The scheduler should deduplicate substantially identical pending needs.

Recommended identity may include:

```text
subject

question

time window

geographic scope

source class

target purpose
```

Duplicate research needs may share one retrieval result when appropriate.

---

# 28. Research backoff

If an external source is unavailable, the scheduler should avoid aggressive repeated access.

Recommended behavior:

```text
failure
    ↓
record failure
    ↓
bounded backoff
    ↓
re-evaluate later
```

The approximately five-minute evaluation cadence need not mean retrying a failing site every five minutes indefinitely.

---

# 29. Research budget

Each research need should have a bounded budget.

Possible limits:

```text
maximum sources

maximum search rounds

maximum elapsed time

maximum candidate count

maximum geographic scope

maximum temporal scope
```

This prevents unbounded exploration.

---

# 30. Scheduled queue evaluation

Conceptual scheduled loop:

```text
every ~5 minutes:
    inspect pending research needs

    for each eligible need:
        if still relevant
        and corpus still insufficient
        and research permitted:
            conduct bounded read-only research
        else:
            no external request
```

The loop evaluates need state before network use.

---

# 31. Research failure

If external research fails:

```text
information gap remains
```

The system should not fabricate a result.

Possible current-response outcomes:

```text
INSUFFICIENT_INFORMATION

SOURCE_UNAVAILABLE

CURRENT_INFORMATION_UNVERIFIED
```

depending on the case.

---

# 32. Source unavailable is not empty result

Preserve:

```text
source unavailable
    ≠
source says nothing exists
```

Likewise:

```text
search returned no result
    ≠
fact does not exist
```

The architecture should distinguish absence of evidence from negative evidence.

---

# 33. Query transformation lineage

If the original user question is transformed into multiple search queries, preserve:

```text
original question

research need

derived queries
```

This allows audit of model-generated search terms.

---

# 34. Extraction lineage

If source material is summarized or extracted, preserve:

```text
source material
    ↓
extraction
    ↓
candidate claim
```

The candidate should retain a reference to the original source.

---

# 35. No external-side writes invariant

The research system should record:

```text
EXTERNAL_WRITE_PERFORMED=NO
```

for every read-only research session.

If a tool or API requires mutation to retrieve information, that source should not be used under this mechanism.

---

# 36. Authentication to read-only sources

If future external research uses authenticated read-only APIs, authentication does not change the external-side-write invariant.

Preserve:

```text
authenticated read access
    ≠
write authority
```

The access token scope should be read-only wherever technically possible.

---

# 37. Secrets and credentials

Research credentials should never be inserted into:

```text
research candidate content

model-facing source text

persistent corpus content

response citations
```

Credential handling belongs to the secure runtime boundary.

---

# 38. Robots / source policy boundary

The future research adapter should respect applicable source access rules, API terms, and technical restrictions.

The read-only designation does not imply:

```text
every public URL may be scraped without constraint
```

The adapter should use permitted access methods.

---

# 39. Research result classification

Candidate information should retain its class:

```text
FACT

CLAIM

OPINION

MEASUREMENT

ESTIMATE

FORECAST

POLICY

LEGAL_TEXT

RESEARCH_FINDING

UNVERIFIED_REPORT
```

The response layer must not silently convert one class into another.

---

# 40. Research result and confidence

A confidence field may help prioritize review.

But:

```text
confidence score
    ≠
truth
```

and:

```text
confidence score
    ≠
persistence authority
```

---

# 41. Current-user availability

Where a result passes current-response evaluation, it should become available to the active conversational task.

Conceptually:

```text
RESEARCH_CANDIDATE
    ↓
CURRENT_RESPONSE_ELIGIBLE
    ↓
response composer
```

The research result should not necessarily enter long-term system state.

---

# 42. Conversational response integration

The response layer should be able to combine:

```text
qualified internal corpus context
    +
eligible current research
```

while preserving which claims come from which source class.

The answer should not imply all content was already in the internal corpus.

---

# 43. Current-response provenance packet

A bounded packet may include:

```yaml
response_research_context:
  research_need_id:
  query:
  retrieved_at:
  sources:
    - url:
      title:
      source_class:
      publication_date:
      claim_scope:
  candidate_status: ACCEPTED_FOR_CURRENT_RESPONSE
```

This packet is not equivalent to persistent learned state.

---

# 44. Research-to-corpus handoff

If a candidate should be considered for persistence, the graph should route it into a separate:

```text
research-to-corpus admission
```

workflow.

That workflow should perform stronger:

```text
provenance

schema

authority

privacy

duplicate

conflict

domain

persistence
```

checks.

The read-only research mechanism itself should not perform the final admission implicitly.

---

# 45. No direct research-to-Hilbert write

Preserve:

```text
web research
    ≠
direct H_* write
```

The correct path is:

```text
web research
    ↓
candidate
    ↓
domain qualification
    ↓
authority
    ↓
optional H_* admission
```

---

# 46. No direct research-to-JCP write

Likewise:

```text
web result
    ≠
JCP field
```

A current response may use eligible research through a bounded response/reasoning adapter, but persistent or structural JCP admission requires separate qualification.

---

# 47. H_geo research use

A geographic research result may support a current response.

Persistent H_geo admission requires the H_geo domain contract.

Current R3 state remains:

```text
H_GEO_CURRENT_JCP_ADMISSION=NO
```

---

# 48. H_p research use

A civic research result may support a current answer.

Persistent H_p admission requires the H_p-specific qualification path.

Do not equate:

```text
public civic source
```

with:

```text
qualified H_p state
```

---

# 49. H_people research use

Person-related web research requires privacy-sensitive handling.

Public availability does not automatically authorize:

```text
H_people admission

H_people PRIVATE use

H_people SECRET classification

SECRET disclosure
```

The H_people governance boundary remains separate.

---

# 50. KYC/protected-location boundary

Read-only web research does not replace authoritative KYC location.

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
SECRET identity correspondence authority
```

---

# 51. DGM boundary

Read-only web research is not DGM authorized adoption.

Preserve:

```text
research result
    ≠
DGM package
```

and:

```text
response use
    ≠
authorized production mutation
```

---

# 52. Publication boundary

Research results used in a conversation are not automatically governed publication objects.

Preserve:

```text
current response
    ≠
public corpus publication
```

Publication remains a separate transition.

---

# 53. Automated-learning boundary

The read-only web mechanism is one component of the larger Automated Learning Graph.

Its responsibility ends at:

```text
candidate research result
```

plus, where permitted:

```text
current-response eligibility
```

Persistent learning belongs downstream.

---

# 54. Formalization candidates

A future theorem family may formalize properties such as:

```text
read_only_research_performs_no_external_write

research_result_initially_candidate

candidate_for_current_response_does_not_imply_persistence

failed_provenance_blocks_persistent_admission

query_provenance_is_preserved

source_identity_is_preserved

research_failure_preserves_information_gap
```

These are candidate theorem areas only.

Exact theorem statements should follow the implementation.

---

# 55. Runtime qualification targets

Before production qualification, test:

```text
scheduled queue evaluation

no-request cycle

bounded GET/search cycle

source provenance capture

date capture

query capture

external write detection

response-only use

no-persistence path

failed-source path

conflicting-source path

stale-source path
```

---

# 56. External-write sentinel

A future runtime qualification should verify that the research client cannot issue mutation methods.

Possible guard:

```text
allowed methods:
GET
HEAD
```

or the equivalent read methods for the source adapter.

Any attempted mutation should fail closed.

---

# 57. Five-minute schedule qualification

The scheduler should be tested for:

```text
approximately five-minute evaluation cadence

no overlapping duplicate run

bounded execution

backoff

expired need removal

no external request when no eligible need exists
```

The architecture does not require exact wall-clock execution at precisely 300.000 seconds.

---

# 58. Scheduler authority

The scheduler may evaluate research eligibility.

It does not gain authority to:

```text
persist candidate knowledge

change H_* admission

alter JCP

publish

perform external writes
```

unless a separate transition explicitly permits one of those actions.

---

# 59. Recommended scheduler state record

```yaml
research_scheduler:
  cadence_target_seconds: 300
  cadence_semantics: approximate

  external_access: READ_ONLY

  pending_need_count:
  eligible_need_count:

  last_evaluation_at:
  next_evaluation_target:

  overlap_allowed: false

  external_write_allowed: false
```

---

# 60. Recommended research-result record

```yaml
web_research_result:
  research_need_id:
  query:

  source:
    url:
    title:
    domain:
    author:
    organization:
    source_class:
    publication_date:
    updated_date:

  retrieval:
    retrieved_at:
    method: READ_ONLY

  content:
    extracted_claims: []

  evaluation:
    relevance:
    freshness:
    conflicts:
    privacy:
    uncertainty:

  disposition:
    current_response_eligible:
    persistence_status: NOT_ADMITTED
```

---

# 61. Current response path

The future ordinary conversation path may become:

```text
authenticated browser/session
    ↓
/api/chat
    ↓
Unified Gateway
    ↓
current corpus / JCP
    ↓
information sufficient?
       ├─ YES → normal reasoning path
       └─ NO  → bounded read-only web research
                    ↓
               candidate evidence
                    ↓
               current-response evaluation
                    ↓
               Gateway / ensemble / synthesizer
                    ↓
               response
```

This future fallback should preserve the current authority boundaries.

---

# 62. Research result lifetime

Research candidates should have explicit lifetime semantics.

Possible states:

```text
REQUEST_SCOPED

SHORT_LIVED_CACHE

RESEARCH_ARCHIVE

PERSISTENCE_CANDIDATE
```

The default current-response result should not automatically become:

```text
DURABLE_QUALIFIED_KNOWLEDGE
```

---

# 63. Cache boundary

A short-lived technical cache may be used to prevent repeated external retrieval.

If so, preserve:

```text
cache
    ≠
qualified corpus
```

The cache should retain provenance and expiry.

---

# 64. Source refresh

If a source is revisited later, keep prior observations distinct.

Do not silently overwrite:

```text
source state at T1
```

with:

```text
source state at T2
```

when historical trace matters.

---

# 65. Research receipt

A completed research episode should create a read-only receipt containing:

```text
need ID

queries

sources

retrieval times

result disposition

external writes = NO

current-response use = YES/NO

persistence admission = NO / separate pending process
```

This supports later audit.

---

# 66. Qualification flags

Until implementation and evidence close:

```text
READ_ONLY_WEB_RESEARCH_DESIGN_DEFINED=YES

SCHEDULED_RESEARCH_EVALUATION_DESIGN_DEFINED=YES

APPROXIMATE_EVALUATION_INTERVAL=5_MINUTES

EXTERNAL_SIDE_WRITES_ALLOWED=NO

PROVENANCE_PRESERVATION_REQUIRED=YES

CURRENT_RESPONSE_USE_ALLOWED_WHEN_QUALIFIED=YES

AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED=NO

RESEARCH_TO_CORPUS_INGESTION_QUALIFIED=NO

SYSTEM_PROVEN=NO
```

---

# 67. Normalized architecture record

```yaml
read_only_web_research:
  status: FUTURE_QUALIFICATION_TARGET

  scheduler:
    approximate_interval_minutes: 5
    purpose: evaluate_pending_bounded_research_needs
    continuous_unbounded_crawl: false
    overlapping_runs: false

  trigger:
    corpus_insufficiency: true
    bounded_research_need_required: true

  access:
    external_mode: READ_ONLY
    external_writes: false
    allowed_semantics:
      - search
      - fetch
      - read_api
      - read_document

  provenance:
    preserve_source: true
    preserve_url: true
    preserve_publication_date: true
    preserve_updated_date: true
    preserve_retrieval_time: true
    preserve_query: true
    preserve_research_need_id: true
    preserve_transformations: true

  result:
    initial_state: RESEARCH_CANDIDATE
    automatically_qualified_knowledge: false
    current_response_use_possible: true
    current_response_use_requires_evaluation: true
    automatically_persisted: false

  persistence:
    direct_corpus_write: false
    direct_H_star_write: false
    direct_JCP_write: false
    separate_admission_workflow_required: true

  failure:
    research_failure_fabricates_answer: false
    provenance_failure_allows_persistence: false
    unavailable_source_equals_negative_fact: false

  current_status:
    automated_learning_web_research_qualified: false
    research_to_corpus_ingestion_qualified: false
    system_proven: false
```

---

# 68. Final architecture statement

```text
READ_ONLY_WEB_RESEARCH=FUTURE_DESIGN

SCHEDULED_EVALUATION_APPROXIMATELY_EVERY_5_MINUTES=YES

SCHEDULER_EVALUATES_NEEDS_NOT_UNBOUNDED_WEB=YES

CORPUS_INSUFFICIENCY_CAN_TRIGGER_RESEARCH=YES

EXTERNAL_WEB_ACCESS=READ_ONLY

EXTERNAL_SIDE_WRITES=NO

SOURCE_PRESERVED=YES

DATE_PRESERVED=YES

QUERY_PRESERVED=YES

RETRIEVAL_TIME_PRESERVED=YES

RESEARCH_RESULT_INITIAL_STATE=CANDIDATE

CURRENT_RESPONSE_USE_ALLOWED_WHEN_APPROPRIATE=YES

CURRENT_RESPONSE_USE_IMPLIES_PERSISTENCE=NO

DIRECT_RESEARCH_TO_CORPUS_WRITE=NO

DIRECT_RESEARCH_TO_HILBERT_WRITE=NO

DIRECT_RESEARCH_TO_JCP_WRITE=NO

AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED=NO

RESEARCH_TO_CORPUS_INGESTION_QUALIFIED=NO

SYSTEM_PROVEN=NO
```

---

# Governing principles

> **The scheduler evaluates research needs approximately every five minutes; it does not perform unbounded continuous crawling.**

> **Corpus insufficiency may trigger bounded read-only external research.**

> **External research reads; it does not write.**

> **Source, date, retrieval time, and query provenance travel with every research result.**

> **Every web result begins as candidate state.**

> **Candidate state may support the current user response when appropriately evaluated.**

> **Use in the current response does not imply persistent learning.**

> **Persistent corpus/Hilbert admission remains a separate governed workflow.**

> **Research never writes directly into JCP.**

> **Failure or missing provenance preserves the information gap rather than fabricating certainty.**

> **AUTOMATED_LEARNING_WEB_RESEARCH_QUALIFIED remains NO until the mechanism is implemented and qualified.**

> **SYSTEM_PROVEN remains NO.**
