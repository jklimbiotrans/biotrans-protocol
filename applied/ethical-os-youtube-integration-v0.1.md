# Selective Transparency Donation Protocol v0.1  
### — An SBT-based Ethical Transparency Model (Biotrans Draft)

---

## 1. Purpose
This protocol proposes an experimental model that enables  
**selective proof of integrity** rather than complete exposure  
in donation, funding, or political contribution systems.  

Its goal is to digitize the structure of **conscience, empathy, and autonomy**  
that exists before any legal or institutional framework.

---

## 2. Core Philosophy
- **Transparency ≠ Exposure**  
  True transparency is not about revealing everything —  
  it is about *proving truth when necessary* through verifiable integrity.
- **Autonomy over Disclosure**  
  Individuals can choose what to reveal.  
  Unrevealed data still remains in a *verifiable* state.
- **Ethical Neutrality**  
  The protocol aligns with no political faction; it evaluates only ethics, trust, and contribution.

---

## 3. Key Concepts

### 3.1. SBT (Soul-Bound Token)
- A **non-transferable ethical trust token**.  
- Connects donor identity, contribution record, and attestation signatures — but is *non-tradable*.  
- Acts as a **trust fingerprint**, recording *intent and transparency* rather than amount.

---

## 4. Design Overview

### 4.1. Data Layer
| Layer | Description |
|--------|--------------|
| **On-chain** | Immutable timestamp, hash, signature |
| **Off-chain (IPFS, Arweave)** | Encrypted donation details |
| **Selective Disclosure Keys** | Donors choose which data fields to reveal |

| Field | Disclosure | Description |
|-------|-------------|-------------|
| Amount | Optional | Reveal only if desired |
| Category | Always visible | e.g., education, environment, public welfare |
| Message / Memo | Optional | Reason or note, can remain private |
| Identity | Optional | Shown as anonymized DID if preferred |

---

### 4.2. Anonymous Attestation
Users may receive SBTs under anonymous DIDs.  
The fact that *someone donated* is public,  
but *who* it was remains private, proven through zero-knowledge proofs (ZKPs).  

Thus, **trust remains without exposure.**

---

### 4.3. Selective Disclosure Levels
| Level | Description | Example |
|--------|--------------|----------|
| **0** | Full anonymity (only hash stored) | Private or personal donation |
| **1** | Partial disclosure (category & intent) | “Donation for environmental protection” |
| **2** | Full transparency (amount, note, donor) | NGO campaigns, public collaborations |

---

## 5. Process Flow

1. **Donor Creation**  
   - Generate DID → Optional KYC  
2. **Donation Execution**  
   - Send funds → Generate hash & issue SBT  
3. **Select Disclosure Level**  
   - Choose Level 0–2  
4. **Attestation (Verification)**  
   - NGOs / media / public institutions may sign the SBT  
5. **Optional Publication**  
   - Donor may reveal off-chain data voluntarily  
6. **Public Quorum Audit**  
   - When disputes arise, quorum nodes can request verification

---

## 6. Technical Minimalism

This protocol operates **without bureaucracy or governance overhead**.  

> Trust without institutions  
> Ethics before logic  
> Proof without exposure  

The smart contract functions solely as **a cryptographic witness**.  
The concept itself stands without revealing full source code.

---

## 7. Use Cases
- Transparent donation systems for NGOs and civic funds  
- Political funding accountability (nonpartisan)  
- Creator or artist fan-support systems  
- Ethical DAO contribution tracking  
- Blockchain-based public trust experiments (ESG / civic integrity)

---

## 8. Ethical Note
This framework is **not for surveillance**,  
but for **resonance and ethical restoration**.  
Records serve not as punishment tools but as **evidence of sincerity and repentance**.  

> The SBT represents not a “penalty,” but a “trace of genuine intent.”

---

## 9. License
**MIT License**  

All implementations must include the **Ethical Use Clause**:  
> “This protocol must be used solely for transparency, trust, and repentance.  
> It must never be used to violate human dignity, privacy, or autonomy.”

© 2025 Biotrans Protocol — For Transparent, Ethical, and Forgivable Systems.

---

**Note:**  
The example structure below is intentionally placed at the very end of this Markdown document  
to prevent GitHub’s Markdown renderer from breaking or misinterpreting code blocks.  
Placing the JSON here ensures a clean display and preserves the document’s logical flow.

---

### Example Structure
```json
{
  "holder": "did:example:xyz123",
  "issuer": "did:biotrans:donation-protocol",
  "category": "public_fund",
  "disclosure_level": "partial",
  "data_hash": "0xA93F...",
  "attestor_signature": "0xB6C1..."
}
