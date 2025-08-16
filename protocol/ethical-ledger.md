# Biotrans Protocol — Ethical Ledger (Promises & Proofs)

> **One-line Goal**  
> A **public ledger** for recording ethical promises and proofs, open to verification and audit.  
> *(Focus on record · proof · audit — not money or speculation)*

---

## 🔒 Security Notice
- **No PII:** Do **not** record personal data, client secrets, or sensitive identifiers on-chain.  
  - Store originals in Google Drive, IPFS, or S3.  
  - Only commit the **hash** (e.g., SHA256) on-chain for integrity.
- **Keys / Seeds:** Never commit wallet seeds, private keys, or API tokens in this repository.  
- **Testnet First:** Use testnet deployment only. Mainnet is allowed **after external review and audit**.  
- **Off-chain Priority:** Prefer off-chain storage (Google Drive etc.) for documents; blockchain is for hashes + timestamps.

---

## 👥 Roles
- **Issuer:** Registers a promise (individual or team)  
- **Verifier:** Reviews submitted proof and attaches a stamp (approve / hold / reject)  
- **Observer:** Anyone. Reads and confirms transparency

---

## 📦 Data Objects
- **Principle:** The ethical rule (e.g., deadline, transparency, copyright)  
- **Promise:** “What will be done, by when”  
- **Proof:** Link or file hash + short description  
- **Stamp:** Verifier’s judgment (approve / hold / reject) with optional note  
- **Challenge:** Raise an objection to a proof or stamp  
- **Resolution:** Final decision on the challenge

---

## 🔗 On-chain vs Off-chain
- **On-chain:**  
  - Hashes (e.g., SHA256 of document)  
  - Minimal metadata (promise ID, timestamp)  
  - Event logs (who / when / what action taken)  
- **Off-chain:**  
  - Actual documents (Google Drive / IPFS / S3)  
  - Public or selective access  
  - Integrity verified via hash comparison

---

## ⚙️ Minimal Contract API (Conceptual Only)
```solidity
registerPrinciple(name, summaryURI)
registerPromise(principleId, title, dueDate, summaryURI) -> promiseId
submitProof(promiseId, proofURI, proofHash)
stamp(promiseId, verdict, noteURI)      // approve | hold | reject
challenge(promiseId, reasonURI)
resolve(promiseId, resolutionURI)
