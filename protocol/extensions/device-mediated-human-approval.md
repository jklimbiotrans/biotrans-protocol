# Device-Mediated Human Approval with SBT-Linked Identity

## Document Scope

This document describes an **optional extension pattern**
for implementing Human-in-the-Loop (HITL) approval
within an Ethical OS for agentic AI systems.

It introduces a model where **end-user devices**
(e.g., mobile phones or personal terminals)
are used to capture human approval or refusal
in real time, linked to **SBT-based identity**.

This document is **not normative**.
It does not replace foundational requirements,
nor does it define a mandatory implementation.

---

## Core Idea

> **Human approval should be captured as close as possible  
> to the human, in real time,  
> and proven later without delaying safety decisions.**

Device-mediated approval allows:

- Immediate human response
- Clear responsibility attribution
- Separation between execution control and proof

---

## Role Within the Ethical OS

This pattern primarily supports:

- Human-in-the-Loop approval
- Responsibility cut points
- Right to non-action
- Post-event accountability

It does **not** replace real-time Kill / Pause mechanisms,
which must remain system-local and immediate.

---

## Conceptual Architecture (High-Level)

### Real-Time Flow

1. A high-risk or gated action is detected
2. Agent execution enters **paused state**
3. Approval request is sent to a registered human device
4. The human selects one of:
   - Approve
   - Reject
   - Defer / No action
5. The decision is:
   - Recorded immediately in local device storage (cache)
   - Signed using SBT-linked identity

### Post-Decision Flow

- The decision event (not full content) may be:
  - Hashed
  - Timestamped
  - Selectively recorded on-chain
- On-chain records serve as **proof**, not control

---

## Why End-User Devices Matter

End-user devices provide:

- Faster response than blockchain finality
- Lower latency than centralized approval servers
- Direct coupling between human intent and action

Local caching ensures that:
- Approval is captured even during network delay
- Human intent is preserved independently of ledger timing

---

## SBT-Linked Identity Function

SBT-based identity is used to:

- Bind approval or refusal to a specific human
- Prevent anonymous or transferable approvals
- Support responsibility attribution

Only minimal data should be associated:

- Identity reference
- Signature
- Timestamp
- Decision code (approve / reject / defer)

---

## Relationship to On-Chain Records

This model follows a **selective recording principle**:

### On-Chain (Optional)

- Final approval or rejection events
- Responsibility cut point confirmation
- Non-action decisions
- Hashes or signatures only

### Off-Chain (Required)

- Detailed explanations
- Contextual reasoning
- Personal or sensitive information
- Device-local interaction logs

This preserves privacy
while enabling auditability.

---

## Strengths and Limitations

### Strengths

- Near real-time human input
- Strong responsibility linkage
- Natural support for refusal and restraint
- Reduced dependence on ledger latency

### Limitations

- Device loss or compromise risk
- Human availability constraints
- Not suitable as an emergency stop mechanism

Accordingly:

> **Kill / Pause must remain local and automatic.  
> Device-mediated approval governs resumption and execution.**

---

## Relationship to Foundational Documents

This extension complements, but does not modify:

- `minimum-ethical-os-requirements.md`
- `onchain-records-vs-realtime-brakes.md`

It provides a **practical pattern**
for implementing human approval
within the boundaries those documents define.

---

## Conclusion

> **Human approval is most meaningful  
> when it is immediate, personal, and attributable.**

Using end-user devices with SBT-linked identity
allows Ethical OS implementations
to capture human intent in real time,
while preserving the separation between
safety control and immutable proof.

---

## Document Status

- Extension pattern
- Non-normative
- Implementation-agnostic
- Optional design reference
