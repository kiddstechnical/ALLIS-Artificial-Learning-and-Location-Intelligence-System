# Governed Evolution

## A careful approach to improving AI systems

This section describes an emerging part of the ALLIS baseline: a **governed evolution architecture** for carefully studying and improving certain AI system components over time.

In plain language, ALLIS is designed to allow limited, documented experimentation with proposed software improvements while keeping strong safeguards between:

1. **Research and experimentation**
2. **Technical review and evidence**
3. **Any possible production change**

The central principle is simple:

> A promising AI-generated improvement is not automatically allowed to change a live system.

ALLIS treats proposed changes as accountable infrastructure changes. Each proposal is intended to be traceable, evaluated, reviewed, bounded by defined authority, and kept separate from production deployment unless it passes later, independent safeguards.

---

## Why this matters

AI systems can assist with research, information organization, drafting, mapping, analysis, and software development. As these systems become more capable, they may also help identify or propose improvements to their own workflows.

That possibility creates opportunity, but it also creates responsibility.

An AI system that can suggest or test improvements must not be allowed to:

- Change live services simply because it generated a plausible idea
- Treat a benchmark score as the same thing as safety or public benefit
- Reuse an old approval for a new or altered change
- Blur the difference between an experiment and a production deployment
- Hide what changed, why it changed, or who authorized it
- Bypass community, institutional, or human accountability

The ALLIS governed-evolution approach is designed to ensure that learning and experimentation remain connected to clear evidence, oversight, and recovery options.

---

## What “governed evolution” means

In this context, **evolution** does not mean unrestricted or self-directed software change.

It means that a system may be allowed to create and evaluate a limited proposed variant of an existing component. If a variant is useful, safe enough for the relevant stage, and supported by documented evidence, it may be retained in a controlled research archive for future study.

A simplified lifecycle is:

```text
Existing qualified record
        ↓
Bounded proposed variation
        ↓
Isolated evaluation and testing
        ↓
Evidence review
        ↓
Qualified archive record
        ↓
Possible future research use
```

A separate process is required before any proposed change could affect a production system:

```text
Qualified research record
        ↓
Independent production review
        ↓
Separate, limited authorization
        ↓
Controlled implementation
        ↓
Verification, monitoring, and rollback readiness
```

A successful research result does **not** automatically authorize a production change.

---

## The qualified evolution archive

ALLIS is developing a **qualified evolution archive**: a protected record of proposed AI-system variants and the evidence associated with them.

A qualified archive record may include:

- The identity of the prior version or “parent” record
- The identity of the proposed variant or “child” record
- The relevant source and evaluation commitments
- The tests expected to be completed
- Evidence from review and scoring processes
- The status of the proposed change
- Records showing whether the proposal was accepted, rejected, or retained only for research
- Evidence of the authority and scope under which a particular action was considered

This archive is intended to make improvement work inspectable and reproducible. It creates a lineage: reviewers can understand where a proposal came from, what it was compared against, and what evidence supported its status.

The archive is not a deployment queue. Retention in the archive means that a result may be useful for learning, comparison, or later authorized research. It does not mean that the result is approved for public use or production operation.

---

## Safeguards and boundaries

The design uses several related safeguards.

### Separation of research and production

Research-stage work and production-stage changes have different purposes, rules, and authorities.

| Research and experiment | Production adoption |
|---|---|
| Tests bounded proposed variants | Changes a live or production-controlled system |
| May retain qualified results for further study | Requires independent approval and operational controls |
| Does not grant deployment authority | Must be separately authorized |
| Supports learning and evaluation | Requires verification, monitoring, and recovery readiness |
| Uses research-specific records and evidence | Uses production-specific authorization and audit records |

This separation helps prevent a common risk: treating a good experimental result as permission to deploy it automatically.

### Evidence before authority

A proposal is intended to carry evidence about what it is, how it was evaluated, and why it was considered.

For example, the process may record:

- The exact version being considered
- The prior state against which it was tested
- The evaluation results
- The relevant review criteria
- The expected tests
- The scope and duration of any authorization
- Whether the authority was used, expired, or rejected

This supports accountability when a partner, reviewer, or future administrator asks:

> What changed, why was it considered, what evidence supported it, and was it actually authorized?

### Limited, one-time permissions

Where a high-consequence action is considered, the intended model uses narrowly scoped, time-limited, and one-use authorization.

In plain language, an approval should be tied to one defined action—not serve as a standing permission that can be reused later for a different change.

This approach is designed to reduce the risk of:

- Replaying an old approval
- Substituting a different proposal after review
- Reusing authority after it expires
- Expanding a research authorization into a production authorization

### Independent verification

ALLIS is being designed so that important review and authorization records can be checked independently.

Some records may be cryptographically signed. This is similar in principle to using a tamper-evident seal: it allows a verifier to determine whether a record has been altered after it was issued and whether it came from the expected authority.

Cryptography is not a substitute for judgment, community accountability, or institutional oversight. It is one tool for preserving evidence integrity.

---

## Current baseline status

This repository documents an evolving baseline. It is important to distinguish among four different kinds of project status:

| Status | Meaning |
|---|---|
| **Designed** | A policy, model, or safeguard has been specified |
| **Implemented** | A technical component and supporting tests exist in a controlled development environment |
| **Qualified** | Evidence has been collected showing that a defined control worked at an identified version |
| **Operational** | A component is actively deployed with defined ownership, monitoring, incident response, and recovery procedures |

The governed-evolution work described here is being documented as part of the ALLIS baseline. Some elements have been designed, implemented, and qualified in controlled settings. This documentation does not claim that ALLIS operates an unrestricted self-improving system or that research-stage candidates automatically affect live services.

The distinction matters. Clear documentation should describe what has been demonstrated, what remains under development, and what requires separate institutional or community decision-making.

---

## What this is not

This architecture should not be understood as:

- A system that can independently rewrite or deploy any part of itself
- A claim of artificial general intelligence
- A substitute for faculty, staff, community members, institutional leadership, or public accountability
- A mechanism for bypassing normal review, security, or procurement processes
- A promise that an AI-generated change is correct merely because it performed well on a test
- An automated pathway from experimental result to public-facing deployment
- A replacement for data governance, privacy protection, cybersecurity, accessibility, or legal review

ALLIS is intended to support responsible learning and local capacity—not remove human responsibility.

---

## Relevance to higher education and community partners

For colleges, universities, libraries, local governments, nonprofit organizations, and community partners, the value of this approach is not simply technical novelty.

It is the ability to ask better questions before adopting AI-enabled tools:

- Who is accountable for a system change?
- What information was used to evaluate it?
- Can the decision be reviewed later?
- Can a result be reproduced or independently checked?
- Can an unauthorized or altered change be rejected?
- Can a harmful or unsuccessful change be reversed?
- Does a research result remain clearly separate from a production decision?
- Are local needs, community knowledge, and institutional values represented in the evaluation process?

ALLIS is intended to help institutions explore AI without requiring them to choose between innovation and accountability.

---

## Public documentation and private operations

This public portfolio repository shares the ALLIS architecture, governance approach, documentation standards, and selected non-sensitive evidence.

It intentionally does **not** publish:

- Operational source code
- Private keys, passwords, tokens, or secrets
- Live deployment configuration
- Active authorization artifacts
- Internal network, host, or runtime details
- Security-sensitive evaluator logic
- Private evidence records that could expose people, systems, or operational controls

Operational materials are retained privately and may be reviewed only through an appropriate controlled process.

This separation allows ALLIS to communicate its principles and assurance approach without exposing systems or materials that should remain protected.

---

## How to read this section

Readers new to AI governance may begin with:

1. **This page** for the overview
2. **System boundary documentation** for the distinction between research and production
3. **Trust and authority documentation** for how scope, accountability, and review are defined
4. **Acceptance documentation** for the evidence expected before a claim is upgraded from designed to qualified or operational

Technical readers may be interested in the planned documents on archive lineage, evaluation and admission, authority separation, assurance evidence, and threat modeling.

---

## Core commitment

ALLIS is built around a practical commitment:

> AI can help communities and institutions learn, organize, and improve—but systems that affect people, services, and public trust must remain understandable, accountable, and subject to meaningful human and institutional control.

The governed-evolution architecture is one way ALLIS is working toward that commitment.
