<div align="center">

# ALLIS — Current System Manifest

### Qualified objects, authority roles, and correspondence relationships

**Current technical manifest · September 2026**

<br>

![Manifest](https://img.shields.io/badge/CURRENT_SYSTEM_MANIFEST-COMPOSITE-7c3aed?style=for-the-badge)
![Workstream F](https://img.shields.io/badge/WORKSTREAM_F-CLOSED-16a34a?style=for-the-badge)
![Step 12](https://img.shields.io/badge/DGM_STEP_12-CLOSED_WITH_RESIDUALS-f59e0b?style=for-the-badge)
![Step 17](https://img.shields.io/badge/PUBLICATION_STEP_17-GREEN_COMPLETE-22c55e?style=for-the-badge)
![System Proof](https://img.shields.io/badge/SYSTEM_PROVEN-NO-64748b?style=for-the-badge)

<br>

**Kidd’s Technical Services · ALLIS**

</div>

---

> [!IMPORTANT]
> This manifest identifies the **qualified objects that support the current ALLIS technical record** and the **explicit relationships established among them**.
>
> It does not reduce ALLIS to one commit, one runtime image, one theorem, or one publication artifact.

---

# 👀 Manifest at a glance

The current ALLIS technical record is a **composite system manifest**.

Different objects establish different kinds of technical authority:

| Object class | What it establishes |
|---|---|
| ✅ **Qualified source** | Which implementation object is admitted for a bounded workstream |
| 📐 **Proof/source anchor** | Which source object a bounded formal analysis refers to |
| 🔐 **Production source** | Which production implementation a formal/correspondence package binds |
| 🔑 **Trust object** | Which verification trust state was sealed and compared |
| 🧭 **Governance object** | Which governance state was sealed and compared |
| 🧾 **Evidence seal** | Which completed bounded evidence state identifies a workstream close |
| 🌐 **Publication object** | Which immutable public projection was served |
| 🖥️ **Frontend object** | Which frontend build consumed the governed publication at the final observation |

The governing rule is:

> **An object is authoritative only for the role and scope established by its qualification record.**

---

# 🧩 Current System Object Graph

The manifest is a graph of qualified objects and established relationships.

```mermaid
flowchart TB
    subgraph WF["✅ Workstream F"]
        F["Qualified source baseline<br/>65b9f7db…"]:::source
        FC["Formal close<br/>F1–F5 · 5/5 proofs"]:::close
        F -->|"qualified source for"| FC
    end

    subgraph A5["📐 A5 formalization domain"]
        A["A5 source anchor<br/>35f1aa55…<br/>tree 36dd9f24…"]:::proof
        AP["Bounded A5 / A5A analysis"]:::formal
        A -->|"source anchor for"| AP
    end

    subgraph S12["🔐 DGM Step 12"]
        D["Production source<br/>20c8cbe1…"]:::dgm
        M["DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1"]:::formal
        T["Public trust object<br/>4809a1af…"]:::trust
        V["Governance view<br/>26523c0b…"]:::governance
        SEAL["Step-12 final seal<br/>b00a954a…"]:::seal

        D -->|"model-to-source binding"| M
        T -->|"trust correspondence"| SEAL
        V -->|"governance correspondence"| SEAL
        M -->|"bounded theorem state"| SEAL
    end

    subgraph S17["🌐 Publication Step 17"]
        P["Publication<br/>allis-publication-step6-retention-v2<br/>SHA d6ab6352…"]:::publication
        H["Direct + public HTTP<br/>body correspondence"]:::http
        G["Frontend build<br/>5By6R3…"]:::gui

        P -->|"served through"| H
        H -->|"consumed by"| G
    end

    C["🧾 CURRENT ALLIS TECHNICAL RECORD<br/>composite qualified-object manifest"]:::current

    FC --> C
    AP --> C
    SEAL --> C
    G --> C

    classDef source fill:#22c55e,stroke:#166534,color:#ffffff,stroke-width:2px;
    classDef close fill:#86efac,stroke:#15803d,color:#14532d,stroke-width:2px;
    classDef proof fill:#8b5cf6,stroke:#5b21b6,color:#ffffff,stroke-width:2px;
    classDef formal fill:#c4b5fd,stroke:#7c3aed,color:#3b0764,stroke-width:2px;
    classDef dgm fill:#ef4444,stroke:#991b1b,color:#ffffff,stroke-width:2px;
    classDef trust fill:#f97316,stroke:#9a3412,color:#ffffff,stroke-width:2px;
    classDef governance fill:#f59e0b,stroke:#92400e,color:#111827,stroke-width:2px;
    classDef seal fill:#facc15,stroke:#854d0e,color:#111827,stroke-width:2px;
    classDef publication fill:#14b8a6,stroke:#115e59,color:#ffffff,stroke-width:2px;
    classDef http fill:#06b6d4,stroke:#155e75,color:#ffffff,stroke-width:2px;
    classDef gui fill:#2563eb,stroke:#1e3a8a,color:#ffffff,stroke-width:2px;
    classDef current fill:#ec4899,stroke:#9d174d,color:#ffffff,stroke-width:3px;
```

### How to read the graph

The diagram shows **established roles and relationships**.

It does **not** claim that these three source identities form a single replacement chain:

```text
65b9f7db…
35f1aa55…
20c8cbe1…
```

Each source object belongs to a different bounded technical role.

No source object silently inherits the authority of another.

---

# 🏷️ Manifest object classes

Each manifest entry uses one primary object class.

| Class | Meaning |
|---|---|
| `QUALIFIED_SOURCE` | Source object admitted for a bounded acceptance or qualification scope |
| `PROOF_SOURCE_ANCHOR` | Source identity used to anchor a bounded formal analysis |
| `PRODUCTION_SOURCE` | Production implementation identity used by a bounded formal/correspondence package |
| `TRUST_OBJECT` | Sealed public verification trust identity |
| `GOVERNANCE_OBJECT` | Sealed governance-state identity |
| `EVIDENCE_SEAL` | Immutable identity for a closed bounded evidence state |
| `PUBLICATION_OBJECT` | Governed immutable public projection |
| `FRONTEND_BUILD` | Frontend build identity observed in the qualified publication path |

These classes describe **roles**, not maturity rankings.

A `PRODUCTION_SOURCE` is not automatically stronger than a `QUALIFIED_SOURCE`; it answers a different question.

---

# 📋 Current object registry

| ID | Object | Class | Identity | Workstream | State |
|---|---|---|---|---|---|
| `OBJ-F01` | Workstream-F qualified baseline | `QUALIFIED_SOURCE` | `65b9f7dbd594ec9d225152aabd705eefc9216dbb` | Workstream F | **CLOSED source authority** |
| `OBJ-A501` | A5 source anchor | `PROOF_SOURCE_ANCHOR` | `35f1aa5586e1a23e1ab88f4d757c451b44506893` | A5 / mathematical audit | **Qualified anchor** |
| `OBJ-D1201` | Step-12 production DGM source | `PRODUCTION_SOURCE` | `20c8cbe175781c8a1c05d65c03977859ceca884a` | DGM Step 12 | **Closed bounded source** |
| `OBJ-D1202` | Step-12 public trust object | `TRUST_OBJECT` | `4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5` | DGM Step 12 | **Correspondence PASS at final seal** |
| `OBJ-D1203` | Step-12 governance view | `GOVERNANCE_OBJECT` | `26523c0bad40ff06a75c62a802f20195295534764dce45cfa6acdcdaecc3fcc2` | DGM Step 12 | **Correspondence PASS at final seal** |
| `OBJ-D1204` | Step-12 final evidence seal | `EVIDENCE_SEAL` | `b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b` | DGM Step 12 | **GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS** |
| `OBJ-P1701` | Step-17 publication | `PUBLICATION_OBJECT` | ID `allis-publication-step6-retention-v2` | Publication Step 17 | **GREEN COMPLETE** |
| `OBJ-P1702` | Step-17 publication body | `PUBLICATION_OBJECT` | SHA-256 `d6ab63522f9080fae440578ebbb6ed42140595155c9a30253f5b8eeeef8009b7` | Publication Step 17 | **Direct/public correspondence PASS** |
| `OBJ-P1703` | Step-17 frontend build | `FRONTEND_BUILD` | `5By6R3CWTM7NDXc-4lmSi` | Publication Step 17 | **Observed at final seal** |

---

# ✅ `OBJ-F01` — Workstream-F qualified baseline

<div align="center">

![Class](https://img.shields.io/badge/CLASS-QUALIFIED_SOURCE-16a34a?style=flat-square)
![State](https://img.shields.io/badge/STATE-CLOSED-22c55e?style=flat-square)

</div>

## Identity

```text
Branch:
remediation/active-source-baseline-20260902

HEAD:
65b9f7dbd594ec9d225152aabd705eefc9216dbb

Tag:
stage10-auth-identity-65b9f7dbd594
```

## Role

`OBJ-F01` is the qualified source object for the formal Workstream-F close.

Workstream F records:

```text
F1 = CLOSED
F2 = CLOSED
F3 = CLOSED
F4 = CLOSED
F5 = CLOSED

proofs = 5 / 5

WORKSTREAM_F_STATUS = CLOSED
```

## Authority scope

This object establishes the source authority used for the bounded Workstream-F acceptance state.

## Supported statement

> **Workstream F is formally closed against its qualified source object.**

## Scope boundary

`OBJ-F01` does not automatically identify:

- the later A5 proof/source anchor;
- the Step-12 production DGM source;
- the Step-17 publication object; or
- the complete ALLIS runtime.

---

# 📐 `OBJ-A501` — A5 proof/source anchor

<div align="center">

![Class](https://img.shields.io/badge/CLASS-PROOF_SOURCE_ANCHOR-8b5cf6?style=flat-square)
![Scope](https://img.shields.io/badge/SCOPE-BOUNDED_FORMALIZATION-7c3aed?style=flat-square)

</div>

## Identity

```text
HEAD:
35f1aa5586e1a23e1ab88f4d757c451b44506893

Tree:
36dd9f2425db4b23bacfce1cb258603cace25f1b
```

## Role

`OBJ-A501` anchors the later bounded A5 formal/wiring analysis.

The A5 record freezes and analyzes a bounded source domain rather than redefining the complete ALLIS production baseline.

## Authority scope

This object is authoritative for the source identity used by that bounded formalization tract.

## Supported statement

> **The A5 bounded formal analysis is anchored to the identified committed source object.**

## Scope boundary

No automatic equivalence is asserted between:

```text
OBJ-F01
    and
OBJ-A501
```

or between:

```text
OBJ-A501
    and
OBJ-D1201
```

Any stronger source-equivalence claim requires its own correspondence evidence.

---

# 🔐 `OBJ-D1201` — Step-12 production DGM source

<div align="center">

![Class](https://img.shields.io/badge/CLASS-PRODUCTION_SOURCE-ef4444?style=flat-square)
![Workstream](https://img.shields.io/badge/WORKSTREAM-DGM_STEP_12-f97316?style=flat-square)

</div>

## Identity

```text
20c8cbe175781c8a1c05d65c03977859ceca884a
```

## Formal object

```text
DGM_PRODUCTION_AUTHORIZED_ADOPTION_MODEL_V1
```

## Role

`OBJ-D1201` is the controlling production source identity for the bounded Step-12 authorized-adoption formal and correspondence package.

The sealed source domain contains:

```text
11 governed production source files
```

The Step-12 record establishes model-to-source binding to that sealed set and reports runtime source correspondence for both NBB and worker execution paths.

## Supported statement

> **The Step-12 bounded authorized-adoption formal object is tied to the identified production source commit and its sealed governed source set.**

## Scope boundary

`OBJ-D1201` is not a source identity for every ALLIS subsystem.

---

# 🔑 `OBJ-D1202` — Step-12 public trust object

<div align="center">

![Class](https://img.shields.io/badge/CLASS-TRUST_OBJECT-f97316?style=flat-square)
![Correspondence](https://img.shields.io/badge/CORRESPONDENCE-PASS-22c55e?style=flat-square)

</div>

## Identity

```text
SHA-256:
4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5
```

## Role

`OBJ-D1202` identifies the public verification trust object used by the bounded Step-12 production verification path.

## Correspondence state

```text
PUBLIC_TRUST = PASS
```

at the Step-12 final seal.

## Supported statement

> **The inspected production verification trust state corresponded to the sealed public trust object at the Step-12 final observation.**

## Scope boundary

Possession or publication of this public verification object does not grant private signing authority.

```text
can verify authority
    ≠
can create authority
```

---

# 🧭 `OBJ-D1203` — Step-12 governance view

<div align="center">

![Class](https://img.shields.io/badge/CLASS-GOVERNANCE_OBJECT-f59e0b?style=flat-square)
![Correspondence](https://img.shields.io/badge/CORRESPONDENCE-PASS-22c55e?style=flat-square)

</div>

## Identity

```text
SHA-256:
26523c0bad40ff06a75c62a802f20195295534764dce45cfa6acdcdaecc3fcc2
```

## Role

`OBJ-D1203` identifies the sealed governance object used at the Step-12 NBB boundary.

## Correspondence state

The final Step-12 record establishes:

```text
Governance view = PASS
```

for the inspected NBB governance view.

## Supported statement

> **The live NBB governance view inspected at Step-12 final seal matched the sealed governance object.**

## Scope boundary

A governance view can represent governed state without creating mutation authority.

```text
governance state exists
    ≠
authorization exists
```

---

# 🧾 `OBJ-D1204` — Step-12 final evidence seal

<div align="center">

![Class](https://img.shields.io/badge/CLASS-EVIDENCE_SEAL-facc15?style=flat-square)
![State](https://img.shields.io/badge/STATE-GREEN_CLOSED_WITH_RESIDUALS-f59e0b?style=flat-square)

</div>

## Identity

```text
SHA-256:
b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
```

## Final Step-12 status

```text
GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS
```

## Formal result

```text
12 propositions
11 proven
1 disproven
0 unadjudicated
```

Principal validation states:

| Proposition | State |
|---|---|
| `T12D-A` | 🤖 `MACHINE_CHECKED` |
| `T12D-B` | 🔗 `CORRESPONDENCE_VERIFIED` |
| `T12D-C` | 🔗 `CORRESPONDENCE_VERIFIED` |
| `P12C-09` | 🔴 `MACHINE_CHECKED_DISPROVEN` |

## Residual state

The Step-12 close preserves eight explicit residuals and seven explicit non-promotions.

The controlling system-level boundary remains:

```text
PRODUCTION_MUTATION_SAFETY_THEOREM_PROVEN=NO

WHOLE_SYSTEM_SAFETY_THEOREM_PROVEN=NO

SYSTEM_PROVEN=NO
```

## Supported statement

> **The bounded Step-12 authorized-adoption workstream is closed with all formal obligations adjudicated and its residual claim boundaries preserved.**

---

# 🌐 `OBJ-P1701` — Step-17 publication

<div align="center">

![Class](https://img.shields.io/badge/CLASS-PUBLICATION_OBJECT-14b8a6?style=flat-square)
![State](https://img.shields.io/badge/STATE-GREEN_COMPLETE-22c55e?style=flat-square)

</div>

## Identity

```text
Publication ID:
allis-publication-step6-retention-v2
```

## Role

`OBJ-P1701` is the governed public publication object for the completed Step-17 fixed goal.

## Final workstream state

```text
Steps 0–17:
GREEN

Completion criteria:
25 / 25 PASS

Final network continuity:
GREEN

ALLIS_LIVE_PUBLICATION_ENDPOINT:
COMPLETE

ALLIS_EVIDENCE_GOVERNANCE_PORTAL:
LIVE at final sealed observation
```

## Supported statement

> **The Step-17 fixed goal completed a governed read-only publication path from qualified state to public evidence and GUI consumption.**

## Scope boundary

Publication does not expose unrestricted internal ALLIS state.

---

# 🧾 `OBJ-P1702` — Step-17 publication body

<div align="center">

![Class](https://img.shields.io/badge/CLASS-PUBLICATION_OBJECT-14b8a6?style=flat-square)
![Identity](https://img.shields.io/badge/BODY_IDENTITY-SEALED-0f766e?style=flat-square)

</div>

## Identity

```text
SHA-256:
d6ab63522f9080fae440578ebbb6ed42140595155c9a30253f5b8eeeef8009b7
```

## Role

`OBJ-P1702` identifies the immutable publication body used for the final direct/public correspondence check.

## Correspondence state

At the final Step-17 closeout:

```text
direct publication HTTP = 200
public publication HTTP = 200
direct/public publication body = identical
final network continuity = PASS
```

## Supported statement

> **The direct and public publication bodies corresponded to the same sealed publication identity at final Step-17 verification.**

## Scope boundary

This is a point-in-time correspondence result.

A future publication-body change requires a new identity and renewed correspondence.

---

# 🖥️ `OBJ-P1703` — Step-17 frontend build

<div align="center">

![Class](https://img.shields.io/badge/CLASS-FRONTEND_BUILD-2563eb?style=flat-square)
![Observation](https://img.shields.io/badge/OBSERVATION-FINAL_STEP_17-0ea5e9?style=flat-square)

</div>

## Identity

```text
5By6R3CWTM7NDXc-4lmSi
```

## Role

`OBJ-P1703` identifies the frontend build observed during final Step-17 continuity and GUI verification.

## Correspondence state

The Step-17 close establishes that the GUI consumed the governed publication through the authorized public path without unrestricted direct ALLIS access.

## Supported statement

> **The identified frontend build consumed the governed publication at the final Step-17 observation boundary.**

## Scope boundary

This build identifier is not an identity for the complete ALLIS runtime.

---

# 🔗 Correspondence registry

The manifest records only explicit correspondence relationships.

```mermaid
flowchart LR
    M["📐 Step-12 formal model"]:::model
    S["💻 Sealed Step-12 source set<br/>OBJ-D1201"]:::source
    N["🖥️ NBB runtime"]:::runtime
    W["👷 Worker runtime"]:::runtime
    T["🔑 Trust state<br/>OBJ-D1202"]:::trust
    V["🧭 Governance state<br/>OBJ-D1203"]:::gov
    P["🌐 Publication body<br/>OBJ-P1702"]:::pub
    H["🌍 Public HTTP"]:::http
    G["🔎 GUI<br/>OBJ-P1703"]:::gui

    M -->|"model → source"| S
    S -->|"11/11 source correspondence"| N
    S -->|"11/11 source correspondence"| W
    T -->|"verification trust PASS"| N
    V -->|"governance view PASS"| N
    P -->|"direct/public body PASS"| H
    H -->|"governed consumption"| G

    classDef model fill:#ddd6fe,stroke:#7c3aed,color:#3b0764,stroke-width:2px;
    classDef source fill:#bbf7d0,stroke:#16a34a,color:#14532d,stroke-width:2px;
    classDef runtime fill:#bae6fd,stroke:#0284c7,color:#0c4a6e,stroke-width:2px;
    classDef trust fill:#fed7aa,stroke:#ea580c,color:#7c2d12,stroke-width:2px;
    classDef gov fill:#fde68a,stroke:#ca8a04,color:#713f12,stroke-width:2px;
    classDef pub fill:#99f6e4,stroke:#0f766e,color:#134e4a,stroke-width:2px;
    classDef http fill:#a5f3fc,stroke:#0891b2,color:#164e63,stroke-width:2px;
    classDef gui fill:#bfdbfe,stroke:#2563eb,color:#172554,stroke-width:2px;
```

## Explicit correspondence edges

| Edge | From | To | State | Scope |
|---|---|---|---|---|
| `EDGE-01` | Step-12 formal model | `OBJ-D1201` sealed production source set | **ESTABLISHED** | Model → source |
| `EDGE-02` | `OBJ-D1201` source set | NBB runtime source | **11/11 PASS** | Point-in-time source → runtime |
| `EDGE-03` | `OBJ-D1201` source set | Worker runtime source | **11/11 PASS** | Point-in-time source → runtime |
| `EDGE-04` | `OBJ-D1202` sealed public trust | Inspected production verification trust | **PASS** | Point-in-time trust correspondence |
| `EDGE-05` | `OBJ-D1203` sealed governance view | Inspected NBB governance view | **PASS** | Point-in-time governance correspondence |
| `EDGE-06` | `OBJ-P1702` direct publication body | Public publication body | **PASS** | Step-17 publication correspondence |
| `EDGE-07` | Governed public publication | `OBJ-P1703` GUI | **PASS** | Step-17 publication → GUI consumption |

---

# 🚫 Relationships this manifest does not assert

The absence of an edge is meaningful.

This manifest does **not** assert:

```text
OBJ-F01 == OBJ-A501
```

It does not assert:

```text
OBJ-A501 == OBJ-D1201
```

It does not assert:

```text
Workstream-F close
    ⇒
Step-12 production source equivalence
```

It does not assert:

```text
Step-12 bounded theorem
    ⇒
whole-system theorem
```

It does not assert:

```text
Step-17 publication correspondence
    ⇒
unrestricted internal ALLIS access
```

It does not assert:

```text
point-in-time runtime correspondence
    ⇒
permanent runtime correspondence
```

This is intentional.

> **Manifest edges are explicit. Unrecorded relationships are not inferred.**

---

# 🪜 Validation status across the manifest

```mermaid
flowchart BT
    A["🛠️ IMPLEMENTED"]:::l1
    B["👁️ OBSERVED"]:::l2
    C["🧪 DEMONSTRATED"]:::l3
    D["📐 FORMALLY SPECIFIED"]:::l4
    E["✅ PROVEN"]:::l5
    F["🤖 MACHINE-CHECKED"]:::l6
    G["🔗 CORRESPONDENCE-VERIFIED"]:::l7

    A --> B --> C --> D --> E --> F --> G

    classDef l1 fill:#dbeafe,stroke:#2563eb,color:#172554,stroke-width:2px;
    classDef l2 fill:#bae6fd,stroke:#0284c7,color:#0c4a6e,stroke-width:2px;
    classDef l3 fill:#a7f3d0,stroke:#059669,color:#064e3b,stroke-width:2px;
    classDef l4 fill:#fde68a,stroke:#d97706,color:#78350f,stroke-width:2px;
    classDef l5 fill:#fdba74,stroke:#ea580c,color:#7c2d12,stroke-width:2px;
    classDef l6 fill:#e9d5ff,stroke:#9333ea,color:#581c87,stroke-width:2px;
    classDef l7 fill:#f0abfc,stroke:#c026d3,color:#701a75,stroke-width:2px;
```

A manifest object can support more than one validation level, depending on the claim.

The validation level belongs to the **claim and evidence relationship**, not to the object name by itself.

---

# 📊 Workstream closeout registry

| Workstream | Close state | Primary manifest objects | Current boundary |
|---|---|---|---|
| ✅ **Workstream F** | `CLOSED` | `OBJ-F01` | Bounded acceptance close |
| 🔐 **DGM Step 12** | `GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS` | `OBJ-D1201`–`OBJ-D1204` | Bounded authorized-adoption formal/correspondence package |
| 🌐 **Publication Step 17** | `GREEN_COMPLETE` | `OBJ-P1701`–`OBJ-P1703` | Bounded governed-publication fixed goal |

Closed workstreams remain valid within their documented scope.

```text
closed
    ≠
scope expanded
```

```text
green
    ≠
whole system proven
```

---

# 🎯 Manifest claim boundaries

The manifest supports the following current top-level statements.

| Claim | Support |
|---|---|
| Workstream F is closed | `OBJ-F01` + Workstream-F close |
| The bounded Step-12 authorized-adoption workstream is closed with explicit residuals | `OBJ-D1201`–`OBJ-D1204` |
| T12D-B and T12D-C are correspondence-verified | Step-12 theorem/correspondence package |
| P12C-09 is disproven | Step-12 theorem and counterexample records |
| Step-17 publication fixed goal is complete | `OBJ-P1701`–`OBJ-P1703` |
| Direct/public publication-body correspondence passed | `OBJ-P1702` |
| The GUI consumed the governed publication at final Step-17 observation | `OBJ-P1703` + Step-17 correspondence |
| Runtime correspondence is time-specific | Step-12 and Step-17 correspondence records |
| `SYSTEM_PROVEN=NO` | Step-12 residual/non-promotion boundary |

The manifest does not support stronger whole-system claims.

---

# ⚪ Current system-level nonclaim

<div align="center">

## Whole-system proof

# `SYSTEM_PROVEN=NO`

</div>

This does not invalidate closed workstreams.

It states the current scope of the evidence.

The bounded formal and correspondence work establishes meaningful technical results without promoting them into a universal theorem over every ALLIS component, runtime path, side effect, external dependency, or state transition.

---

# 👤 Private-state boundary in the manifest

The public manifest contains **no current H_people runtime object**.

That omission is deliberate.

The current public record supports the architectural private-state boundary:

```text
person-linked state exists
    ≠
identity authority established
    ≠
use authority established
    ≠
disclosure authority established
    ≠
publication authority established
```

Historical Gate05c source and runtime evidence remains part of the engineering provenance, but it is not promoted here into a current runtime-authoritative H_people object.

A future H_people runtime object should enter this manifest only after its own:

- source qualification;
- authority qualification;
- runtime observation;
- required correspondence; and
- public-safe evidence record.

---

# 🔄 Manifest update rule

A manifest object changes only when its evidence authority changes.

```mermaid
flowchart LR
    A["🔧 Claim-bearing object changes"]:::change
    B["🧾 Capture new evidence"]:::evidence
    C["🛡️ Requalify scope + authority"]:::qualify
    D["🔗 Re-run required correspondence"]:::corr
    E["✅ Issue new seal / identity"]:::seal
    F["📋 Update manifest"]:::manifest

    A --> B --> C --> D --> E --> F

    classDef change fill:#fecaca,stroke:#dc2626,color:#7f1d1d,stroke-width:2px;
    classDef evidence fill:#bae6fd,stroke:#0284c7,color:#0c4a6e,stroke-width:2px;
    classDef qualify fill:#fde68a,stroke:#ca8a04,color:#713f12,stroke-width:2px;
    classDef corr fill:#ddd6fe,stroke:#7c3aed,color:#3b0764,stroke-width:2px;
    classDef seal fill:#bbf7d0,stroke:#16a34a,color:#14532d,stroke-width:2px;
    classDef manifest fill:#facc15,stroke:#854d0e,color:#111827,stroke-width:2px;
```

Changes that can require a new manifest identity or correspondence state include:

- source commit or tree change;
- runtime image or mounted-source change;
- trust-anchor change;
- governance-object change;
- candidate/authorization semantic change;
- publication-body change;
- frontend-build change;
- public-routing change; or
- addition of a new protected transition.

---

# 🕒 Correspondence is time-specific

The manifest distinguishes object identity from runtime persistence.

```text
object identity
    =
stable identity of the sealed object
```

```text
runtime correspondence
    =
evidence that an inspected runtime matched the object
at a defined observation boundary
```

Therefore:

```text
correspondence at seal time
    ≠
guaranteed correspondence at every future time
```

A changed runtime requires renewed correspondence for affected claims.

---

# 🔐 Semantic completeness

The Step-12 authorization model preserves a second manifest-level rule:

> **Cryptographic validity does not replace semantic completeness.**

Where an authorization decision depends on an authority-bearing semantic input, that input belongs inside the committed authorization context.

The bounded candidate envelope includes:

```text
proposal
target
expected prestate
candidate content
evaluation
scores
expected tests
```

A signature can authenticate the object that was signed.

It does not authenticate an omitted authority-bearing field.

---

# 🧯 Recovery semantics

The current Step-12 formal record disproves unconditional terminal totality.

```mermaid
flowchart TD
    A["📥 Incoming"] -->|"worker claims"| B["🟣 Claimed"]
    B -->|"finish succeeds"| C["✅ Completed"]
    B -->|"rejected"| D["⛔ Rejected"]
    B -->|"terminalization fails"| E["⚠️ Remains Claimed"]
    E --> F["🔧 Recovery / reconciliation"]

    classDef default stroke-width:2px;
    style A fill:#dbeafe,stroke:#2563eb,color:#172554
    style B fill:#ddd6fe,stroke:#7c3aed,color:#3b0764
    style C fill:#bbf7d0,stroke:#16a34a,color:#14532d
    style D fill:#fecaca,stroke:#dc2626,color:#7f1d1d
    style E fill:#fde68a,stroke:#ca8a04,color:#713f12
    style F fill:#fed7aa,stroke:#ea580c,color:#7c2d12
```

The manifest therefore preserves:

```text
claimed
    ≠
guaranteed terminal
```

This is a current formal boundary, not an unresolved theorem.

---

# 📦 Human-readable normalized manifest

The following compact view summarizes the registered objects and relationships.

```yaml
allis_current_system_manifest:
  status: COMPOSITE

  objects:
    - id: OBJ-F01
      class: QUALIFIED_SOURCE
      identity: 65b9f7dbd594ec9d225152aabd705eefc9216dbb
      role: workstream_f_qualified_baseline
      state: CLOSED

    - id: OBJ-A501
      class: PROOF_SOURCE_ANCHOR
      identity: 35f1aa5586e1a23e1ab88f4d757c451b44506893
      tree: 36dd9f2425db4b23bacfce1cb258603cace25f1b
      role: a5_bounded_formalization_anchor

    - id: OBJ-D1201
      class: PRODUCTION_SOURCE
      identity: 20c8cbe175781c8a1c05d65c03977859ceca884a
      role: step12_authorized_adoption_source
      state: GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS

    - id: OBJ-D1202
      class: TRUST_OBJECT
      sha256: 4809a1af3dd8fad1767dc5a8a9d67aa763388a055e00ec818c15f9fe0321fbb5
      role: step12_public_verification_trust
      correspondence: PASS_AT_FINAL_SEAL

    - id: OBJ-D1203
      class: GOVERNANCE_OBJECT
      sha256: 26523c0bad40ff06a75c62a802f20195295534764dce45cfa6acdcdaecc3fcc2
      role: step12_nbb_governance_view
      correspondence: PASS_AT_FINAL_SEAL

    - id: OBJ-D1204
      class: EVIDENCE_SEAL
      sha256: b00a954a924d3aa3490a5bcb8d4473da2b6885b8c41e116cf03545fee975c23b
      role: step12_final_evidence_state
      state: GREEN_CLOSED_WITH_EXPLICIT_RESIDUALS

    - id: OBJ-P1701
      class: PUBLICATION_OBJECT
      identity: allis-publication-step6-retention-v2
      role: governed_public_projection
      state: GREEN_COMPLETE

    - id: OBJ-P1702
      class: PUBLICATION_OBJECT
      sha256: d6ab63522f9080fae440578ebbb6ed42140595155c9a30253f5b8eeeef8009b7
      role: step17_publication_body
      correspondence: DIRECT_PUBLIC_BODY_PASS

    - id: OBJ-P1703
      class: FRONTEND_BUILD
      identity: 5By6R3CWTM7NDXc-4lmSi
      role: step17_gui_build
      observation: FINAL_STEP17_SEAL

  explicit_edges:
    - model_to_step12_source
    - step12_source_to_nbb_runtime
    - step12_source_to_worker_runtime
    - trust_object_to_verification_runtime
    - governance_object_to_nbb_governance_view
    - direct_publication_to_public_publication
    - public_publication_to_gui

  system_boundary:
    system_proven: false
    whole_system_safety_theorem_proven: false
    production_mutation_safety_theorem_proven: false
```

> [!NOTE]
> This YAML block is a **human-readable normalized summary**, not a standalone machine-authority artifact.

---

# 📚 Related repository records

## Current state

- [`../CURRENT.md`](../CURRENT.md) — current qualified state and validation summary
- [`../README.md`](../README.md) — public front door and architectural orientation

## Qualified baseline

- [`qualified-baseline/README.md`](qualified-baseline/README.md)
- [`qualified-baseline/Qualified Baseline Manifest.md`](qualified-baseline/Qualified%20Baseline%20Manifest.md)

## Step-12 formal verification

- [`../formal-verification/authorized-adoption/formal-model.md`](../formal-verification/authorized-adoption/formal-model.md)
- [`../formal-verification/authorized-adoption/theorem-registry.md`](../formal-verification/authorized-adoption/theorem-registry.md)
- [`../formal-verification/authorized-adoption/counterexample-registry.md`](../formal-verification/authorized-adoption/counterexample-registry.md)

## Step-12 correspondence

- [`../correspondence/README.md`](../correspondence/README.md)
- [`../correspondence/authorized-adoption/model-to-source.md`](../correspondence/authorized-adoption/model-to-source.md)
- [`../correspondence/authorized-adoption/source-to-runtime.md`](../correspondence/authorized-adoption/source-to-runtime.md)

## Step-12 evidence

- [`../evidence/governed-evolution/README.md`](../evidence/governed-evolution/README.md)
- [`../evidence/governed-evolution/source-identity.md`](../evidence/governed-evolution/source-identity.md)
- [`../evidence/governed-evolution/trust-anchor.md`](../evidence/governed-evolution/trust-anchor.md)
- [`../evidence/governed-evolution/governance-view.md`](../evidence/governed-evolution/governance-view.md)
- [`../evidence/governed-evolution/residuals.md`](../evidence/governed-evolution/residuals.md)
- [`../evidence/governed-evolution/step12-final-seal.md`](../evidence/governed-evolution/step12-final-seal.md)

---

# 🧭 Manifest maintenance rules

1. **Keep object roles separate.**  
   Do not replace the composite manifest with one global commit identifier.

2. **Record explicit edges only.**  
   Do not infer correspondence between objects that have no qualified relationship.

3. **Preserve point-in-time runtime semantics.**  
   Runtime correspondence must name its observation or seal boundary.

4. **Preserve closed workstream scope.**  
   A later workstream may build on an earlier close without rewriting its bounded result.

5. **Issue new identities after claim-bearing changes.**  
   Changed source, trust, governance, publication, frontend, or authorization semantics may require requalification.

6. **Keep system-level nonclaims visible.**  
   Successful bounded results do not change `SYSTEM_PROVEN=NO` without a separate whole-system proof.

7. **Keep public and private authority separate.**  
   Public documentation may identify hashes, proofs, correspondence, and public trust objects without publishing private keys, credentials, or local source.

---

# 🧾 Manifest summary

<div align="center">

### ✅ `OBJ-F01`
**Workstream-F qualified source · CLOSED**

### 📐 `OBJ-A501`
**A5 proof/source anchor · BOUNDED FORMALIZATION**

### 🔐 `OBJ-D1201`–`OBJ-D1204`
**DGM Step 12 · GREEN CLOSED WITH EXPLICIT RESIDUALS**

### 🌐 `OBJ-P1701`–`OBJ-P1703`
**Publication Step 17 · GREEN COMPLETE**

<br>

### 🔗 Explicit correspondence
**model → source · source → runtime · trust → runtime · governance → runtime · publication → public HTTP → GUI**

<br>

### ⚪ Whole-system proof
# `SYSTEM_PROVEN=NO`

</div>

---

# Governing principles

> **State does not become authority merely because it exists.**

> **Every manifest object has a role, scope, and evidence boundary.**

> **Manifest relationships are explicit; unrecorded relationships are not inferred.**

> **Correspondence is time-specific.**

> **A closed workstream does not imply whole-system proof.**

> **The current ALLIS technical record is a composite of qualified objects and established correspondence.**
