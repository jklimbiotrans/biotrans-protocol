# **Biotrans Protocol — Layer 1 Specification**
## **Event Mirror Layer (Public Specification)**
### *High-Level Specification for Financial Integrity & Transparency*

---

## **1. Purpose of the Event Mirror Layer**

The Event Mirror Layer provides a **tamper-resistant, privacy-preserving representation** of financial events (approvals, settlements, corrections, and delinquency states) without modifying or accessing the legacy financial core.

Its primary goals are:

### **Integrity**
Ensure that event sequences (approval → settlement → correction) are consistent and independently verifiable.

### **Privacy**
Maintain user confidentiality by storing **only hashed and summarized representations**, never raw financial or personal data.

---

## **2. What Is Mirrored**

Biotrans mirrors the following categories of financial events:

- **Approval Events** (transaction initiated, authorized)  
- **Settlement Events** (merchant batch settlement, completion)  
- **Correction Events** (reversals, adjustments, dispute resolutions)  
- **Delinquency States** (late fees, cleared penalties, resolved delinquencies)

Only the **event structure**, **timestamp**, and **logical relationships** are mirrored—  
**never the full transaction details.**

---

## **3. Privacy Model (Publicly Disclosed Guarantee)**

The Event Mirror Layer adheres to a strict privacy boundary:

| Component | Stored by Financial Institution | Stored by Biotrans |
|----------|--------------------------------|--------------------|
| Raw PII | ✔ Yes | ✘ No |
| Full transaction data | ✔ Yes | ✘ No |
| Amounts, merchant names | ✔ Yes | ✘ No |
| Event hash | ✘ No | ✔ Yes |
| Event summary (non-PII) | ✘ No | ✔ Yes |
| ZK-proof inputs | ✘ No | ✔ Yes (minimal) |

Biotrans stores only:

- **EventHash** — immutable fingerprint of the event  
- **EventSummary** — minimal, non-sensitive representation  
- **EventProof** — zero-knowledge proof ensuring integrity  

This guarantees:

> **“No transaction can be altered or misclassified without detection,  
while no personal or financial data is ever exposed.”**

---

## **4. Cryptographic Structure (Concept-Level Only)**

The following conceptual structures are publicly defined:

### **(1) EventHash**  
A deterministic hash representing the event state at time *t*.  
Used to verify immutability.

### **(2) EventSummary**  
A minimal representation containing only what is needed for:

- ordering  
- consistency checks  
- ZK proof generation  
- cross-layer verification  

This summary **does not** contain amounts, identifiers, merchant names, or PII.

### **(3) EventProof (Zero-Knowledge Proof)**  
A ZK proof demonstrating:

- correctness of event transitions  
- consistency between the financial institution’s event and the mirrored state  
- absence of unauthorized modifications  

All without leaking sensitive information.

---

## **5. Guarantees Provided by Layer 1 (Public Commitments)**

### ✔ **Immutability**  
Once mirrored, event fingerprints cannot be altered.

### ✔ **Privacy Preservation**  
No personal or financial details are uploaded or stored.

### ✔ **Consistency Verification**  
Approval → Settlement → Correction chains can be independently verified.

### ✔ **Dispute Resolution Support**  
Provides cryptographic grounding to correct misclassified or mislabeled events.

### ✔ **Non-Intrusive Integration**  
Does not require modifying or replacing the legacy financial core.

---

## **6. What Is *Not* Public (Non-Disclosed Internal Elements)**

The following details are intentionally excluded from the public specification:

- exact field-level data mappings  
- ZK circuit definitions or constraints  
- hash input composition  
- internal infrastructure or security configurations  
- backend API schemas with financial institutions  

These remain internal to protect privacy and maintain security.

This specification provides conceptual transparency  
**without exposing implementation-sensitive details.**

---

## **7. Summary**

The Event Mirror Layer forms the foundational transparency layer of the Biotrans Protocol’s financial integration model. It ensures:

- **integrity without intrusion**  
- **verification without exposure**  
- **fairness without revealing personal data**  

This layer enables higher layers—such as ethical verification, forgiveness logic, and trust-based recovery—to operate safely and securely.

---
