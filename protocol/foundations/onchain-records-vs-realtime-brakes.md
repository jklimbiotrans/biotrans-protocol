# On-Chain Records vs. Real-Time Brakes

## Document Scope

This document clarifies the **role separation**
between blockchain-based records
and real-time safety mechanisms
within an Ethical OS for agentic AI systems.

It addresses a common misconception:
that recording approvals or actions on-chain
automatically provides real-time safety.

This document is **foundational**, not technical.
It defines boundaries of responsibility and timing,
not implementation details.

---

## Core Principle

> **Blockchains are suited for immutable proof,  
> not for real-time safety control.**

Autonomous incidents can occur
within milliseconds.
Blockchain finality operates
on fundamentally slower time scales.

Confusing these roles
creates false assurances of safety.

---

## Time-Scale Mismatch

| Layer | Typical Time Scale | Primary Function |
|---|---|---|
| Agent execution | milliseconds – 0.1 seconds | Act / escalate |
| Safety brakes (pause/kill) | immediate | Prevent harm |
| Human approval workflows | seconds – minutes | Accountability |
| Blockchain finality | seconds – minutes (or more) | Proof / audit |

Because of this mismatch,
**no real-time safety mechanism
should depend on on-chain confirmation.**

---

## Correct Role of Blockchain Records

Blockchain systems are well-suited for:

- Immutable audit trails
- Responsibility attribution
- Dispute resolution
- Post-incident accountability
- Verification of approvals or refusals

They are **not** suited for:

- Emergency stop mechanisms
- Real-time decision gating
- Safety-critical control loops

---

## Selective On-Chain Recording Model

Only **critical decision events**
should be recorded on-chain.

### Recommended On-Chain Events (Illustrative)

| Event Type | Purpose |
|---|---|
| Pause / Kill activation | Proof that a safety brake was triggered |
| Final human approval or rejection | Responsibility attribution |
| Responsibility cut point crossing | Evidence of human accountability |
| Explanation submission (existence only) | Proof of compliance, not content |
| Non-action decision | Evidence that restraint was chosen |

> On-chain records should contain  
> **signatures, hashes, timestamps, and reason codes** —  
> not full content or sensitive data.

---

## Off-Chain Responsibilities

The following should remain off-chain:

- Detailed explanations and justifications
- Conversations, deliberations, or internal reasoning
- Personal, medical, financial, or legal data
- Any information involving minors

This separation protects:
- Privacy
- Legal compliance
- Human dignity

---

## Relationship to Ethical OS Requirements

This document **does not replace**
the minimum operational requirements
defined in:

- `minimum-ethical-os-requirements.md`

Instead, it clarifies **how those requirements
should and should not be evidenced**
using blockchain technology.

In particular:

- Kill / Pause conditions must operate off-chain and in real time
- Human-in-the-loop approval must not wait for blockchain confirmation
- Blockchain records serve as **proof of responsibility**, not safety control

---

## Common Failure Mode to Avoid

Recording every approval or action on-chain
creates:

- Latency and operational friction
- Privacy and regulatory risk
- Illusions of safety
- Weaker, not stronger, accountability

Ethical robustness comes from
**clear boundaries**, not maximal logging.

---

## Conclusion

> **Safety is achieved by stopping harm in time.  
> Accountability is achieved by proving responsibility afterward.**

An Ethical OS must respect
this separation of roles.

Blockchain records strengthen accountability,
but **real-time brakes must remain local,
immediate, and independent of the ledger.**

---

## Document Status

- Foundational clarification
- Non-normative
- Implementation-agnostic
- Intended to complement minimum ethical OS requirements
