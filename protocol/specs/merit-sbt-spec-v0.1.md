# Merit SBT Specification (v0.1)

> **Biotrans Protocol – Core Ethical Token Architecture**  
> Layer: *Post–Self-Purification (Quantified Conscience Layer)*  
> Author: jklimbiotrans  
> Visibility: Public Concept Spec  

---

### Purpose

The **Merit SBT (Soul-Bound Token)** encodes verified ethical resonance into an immutable, non-transferable digital proof.  
It is not a currency, not a reputation score, but a *record of conscience alignment* validated through collective resonance.

This document defines the **conceptual structure and governance logic** of Merit SBTs while excluding any sensitive implementation details (key schemes, ZK parameters, and weighting formulas).

---

### Core Principles

1. **Non-Transferability** – A Merit SBT cannot be traded, sold, or delegated.  
2. **Forgiveness Over Permanence** – Negative records can be nullified through verified repentance or forgiveness.  
3. **Collective Validation** – Merits become valid only when multiple distinct consciences resonate (≥ 3 validators + diversity proof).  
4. **Privacy by Default** – All identity data remain zero-knowledge bound; only aggregate resonance data may be public.  
5. **Alignment with Conscience** – Every token must trace its origin to an ethically validated action or reflection.  

---

### Abstract Data Model

| Field | Type | Description |
|--------|------|-------------|
| `merit_id` | Hash | Unique identifier for each SBT. |
| `issuer_hash` | Hash | Zero-knowledge commitment of the verifier group. |
| `receiver_hash` | Hash | Commitment of the participant’s identity (non-reversible). |
| `merit_score` | Integer (0 – ∞) | Weighted index of moral resonance. |
| `forgiveness_index` | Float (0 – 1) | Degree of forgiveness / repentance processed through the Forgiveness DAO. |
| `diversity_proof` | Proof Object | ZK Proof that validators represent diverse origins (geo, belief, ethic). |
| `timestamp` | ISO8601 | Moment of final resonance validation. |
| `metadata_uri` | URI (IPFS/Arweave) | Optional reference to off-chain narrative or evidence. |

---

### Life-Cycle Flow

1. **Action Registered** → Good-faith action or moral decision logged by participant.  
2. **Peer Resonance** → At least 3 independent verifiers confirm ethical alignment.  
3. **Merit SBT Minted** → Smart-contract issues non-transferable token to participant’s identity.  
4. **Cross-Feedback Loop** → Validators also receive fractional “resonance credit” for participation.  
5. **Forgiveness Path** → If prior demerits exist, forgiveness DAO may partially or fully dissolve them.  

---

### Security & Privacy Considerations

- All commitments use **zero-knowledge proof structures** (e.g., Semaphore-like anonymity).  
- No public linkage between real identity and on-chain hash.  
- Forgiveness and repentance transactions are *ephemeral*; only net ethical state remains visible.  
- Exploit prevention through **multi-diversity validation** (≥ 3 distinct conscience nodes).  

---

### Ethical Integration

The Merit SBT framework directly inherits its moral logic from  
[`../team-operations/self-purification-mechanism-v0.1.md`](../team-operations/self-purification-mechanism-v0.1.md).

> “Data follows conscience, never the reverse.”  

Each token therefore represents **a crystallized moment of ethical resonance**,  
ensuring that technological validation does not precede human sincerity.

---

### Public Release Scope

This version intentionally excludes:  
- Internal weighting formulas.  
- ZK circuit parameters.  
- Identity encryption schema.  

These remain within the private technical repository (`biotrans-protocol-private/zk-specs/`).  
Future releases may include pseudocode once security audits complete.

---

### Summary

- **Layer Type:** Ethical Proof Token (Soul-Bound).  
- **Function:** Record and preserve verified acts of conscience.  
- **Visibility:** Public philosophy + data model only.  
- **Goal:** Transform ethical resonance into immutable yet forgivable digital form.

---

*“Merit is not a score; it is a memory of sincerity.”*  
— **Biotrans Protocol, Ethics OS Core**
