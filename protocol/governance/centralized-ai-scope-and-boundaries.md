# Centralized AI Scope and Boundaries

This document defines the **operational and governance boundaries**
for centralized Artificial Intelligence systems (including AGI-like systems)
within the Biotrans Protocol.

This is not a philosophical statement.
It is a **practical boundary definition** for system design and operation.

---

## 1. Fundamental Principles

1. AI is treated as a **tool**, not an entity.
2. AI shall not possess a persistent self, intrinsic purpose,
   or self-justifying authority.
3. Final responsibility always remains with **human actors**.
4. Performance improvement is allowed; **concentration of decision authority is not**.

---

## 2. Position on Centralized AGI

Biotrans Protocol adopts the following position:

- ❌ A single centralized AGI that performs cross-domain judgment
  and autonomous decision-making is not permitted.
- ✅ A **centralized AI orchestrator** is conditionally permitted.

### Definitions

- **Centralized AGI (Not Permitted)**  
  A unified intelligence that integrates multiple domains,
  generates goals, or redefines priorities autonomously.

- **Centralized Orchestrator (Permitted)**  
  A coordinating system that dispatches, sequences,
  and reconciles outputs from specialized AI modules
  **without holding decision authority**.

---

## 3. Cache-Based, On-Demand AI Architecture

Biotrans Protocol recommends a **cache-based, on-demand AI architecture**.

### Structural Characteristics

- AI systems are **not persistently active**
- AI is invoked only upon specific events or requests
- Execution state is discarded after task completion
- Only outputs may be cached or logged
- No persistent self, long-term agency, or autonomous goal formation exists

### Examples

- Translation request → `translate(input)` → output returned → terminated
- Map query → `route_query(context, t)` → result cached → terminated
- Traffic analysis → `traffic_snapshot(time_window)` → terminated

Under this architecture, AI:
- Does not plan subsequent actions
- Does not perform global or continuous judgment
- Does not function as an ongoing decision-making subject

---

## 4. Domains Where Centralization Is Conditionally Allowed

### 4.1 Transportation and Infrastructure
- Signal optimization
- Congestion prediction
- Incident response

Conditions:
- No direct authority over human life-or-death decisions
- No autonomous policy modification rights

### 4.2 Defense and Security (Defensive Use Only)
- Threat detection
- Interception support
- Cyber defense

Conditions:
- Offensive actions require explicit human authorization
- Autonomous AI-initiated attacks are prohibited

---

## 5. Domains Where Centralization Is Prohibited

The following authorities shall never be assigned to centralized AI systems:

- Final decisions on human life or death
- Legal or ethical liability judgments
- Rights deprivation or classification
- Autonomous goal redefinition
- Self-expansion of structure or authority

---

## 6. Human Final Authority

All centralized AI systems must comply with:

1. Human-controlled shutdown and override mechanisms
2. Human authority over exception handling
3. Post-hoc auditability of AI outputs
4. No bypass of human approval due to performance or efficiency arguments

---

## 7. Precedence

This document has **governing precedence** over:

- AI-related specifications
- Protocol implementations
- Future AGI or ASI-related extensions

Any system design that violates this document
is considered **outside the scope of the Biotrans Protocol**.

---

## 8. Summary

- Centralized **AGI** ❌  
- Centralized **orchestration AI** ✅  
- Cache-based, on-demand AI execution ✅  
- Final judgment and responsibility remain human

This document exists to preserve **control, accountability,
and structural sustainability** in advanced AI systems.
