# Biotrans Protocol — Operation Principles: Resonance Diversity

## 0. Purpose
To prevent *善點 (Good Points)* from degenerating into political or ideological loyalty scores.  
Only **resonances that demonstrate diversity and simultaneity** are recognized as valid.  
Privacy, autonomy, and separation from basic rights are the foundational guarantees.

---

## 1. Core Definitions
- **Resonance**: An act of granting a Good Point after being moved by another person’s good action.  
- **Valid Resonance**: A resonance event that meets all four criteria — simultaneity, diversity, repetition, and trust weighting.  
- **Diversity**: The degree to which resonators come from sufficiently different backgrounds.  
- **Repentance Burn**: A mechanism to nullify politically contaminated or erroneous points through community declaration.  
- **ZK Proof**: Zero-Knowledge proof used to confirm diversity thresholds without revealing sensitive attributes.

---

## 2. Criteria for Valid Resonance

### 2.1 Simultaneity
- At least `k` participants (default **k=3**) must grant points within a time window `w` (default **24h**).  
- This reduces manipulation or staged performances.

### 2.2 Diversity
- No single cluster (same organization, nation, ideology, etc.) may exceed **80%** of total resonances.  
- At least **3 distinct clusters** are required for validation.  
- Recommended metrics:  
  - Simpson’s Diversity Index ≥ **0.5** or Shannon Entropy ≥ **1.0**.  
- Proof is provided via **ZK-Diversity verification** (original attributes remain private).

### 2.3 Repetition & Time Compounding
- Repeated good actions increase weight progressively.  
- Example formula:  
  - Repetition weight: `W_rep(r) = 1 + 0.2·√r`  
  - Time compounding: `W_time(Δt) = 1 + 0.15·log(1+Δt_months)`  

### 2.4 Trust Weighting
- Each giver’s past *resonance credibility* adds weight (`τᵢ`), capped at 1.5.  
- Low scorers or repentant newcomers receive a small positive bonus (+10–20%) to encourage recovery.

---

## 3. Safeguards Against Politicization

1. **Constitutional Ban**  
   - Points cannot be tied to political loyalty, ideology, or religion.  
   - Points cannot be linked to citizenship, survival, or basic rights.  
   - Points cannot be used as currency for taxes, permits, or financial purposes.

2. **Automatic Neutralization**  
   - If >80% of points come from one cluster, the excess is automatically nullified.  
   - Suspicious concentration triggers a diversity challenge.

3. **Repentance Burn**  
   - Politically motivated or campaign-driven points can be nullified through external challenges or forgiveness declarations.  
   - Once burned, points are erased from validity but remain in audit logs.

4. **Minimal Governance**  
   - Normal validation is automatic via protocol and ZK proofs.  
   - Human panels appear only in rare cases (large-scale manipulation, systemic political misuse) and are randomly selected.

---

## 4. Privacy & ZK Architecture
- All attributes are **optional** and **non-identifiable** (region, age band, organization type, language group, etc.).  
- Attributes are committed (`H(attr || nonce)`) and aggregated via ZK proofs.  
- Public chain records only proofs and Merkle roots, never raw data.  
- Default: **non-disclosure**, only statistical diversity results are shown.

---

## 5. Example Scenarios
1. **Street Cleaning**  
   - Local residents grant points (high bias).  
   - Later, passersby and a new participant add points → diversity threshold reached → Valid.

2. **Political Rally**  
   - 90% of points come from same party domain → excess nullified, flagged as “political suspicion.”  

3. **Repentance Testimony**  
   - Initially few points.  
   - Months later, resonances from multiple regions accumulate → compounding boosts score validity.

---

## 6. Public Disclosure Policy
- Publish only *minimal statistics*: diversity indices, proof validity.  
- Never disclose raw attributes or individual identities.  
- Research or third-party use requires explicit opt-in consent.

---

## 7. Key Parameters (Beta Defaults)
- Simultaneity: `k=3`, `w=24h`  
- Max cluster ratio: ≤ 0.8  
- Diversity threshold: Simpson ≥ 0.5, Shannon ≥ 1.0  
- Repetition weight: `1 + 0.2·√r`  
- Time compounding: `1 + 0.15·log(1+Δt_months)`  
- Trust cap: `τ_max = 1.5` (+0.1–0.2 for repentant newcomers)  

---

## 8. Guiding Principle
Good Points are **ethical and emotional records**, not political or financial instruments.  
They exist to promote resonance, forgiveness, and conscience, independent of state or market control.
