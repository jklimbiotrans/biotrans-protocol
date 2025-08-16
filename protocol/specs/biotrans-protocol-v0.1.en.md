# Biotrans Protocol Spec v0.1
(Minimal ruleset operable without apps)

---

## 0. Purpose & Principles
**Purpose**  
Only spontaneous resonance of good deeds is validly recorded and rewarded.  

**Core Principles (Charter excerpt)**  
- **No linkage**: Good-point records must not connect to credit, loans, employment, or control systems  
- **Privacy by default**: Individual totals stay private (only optional range/aggregate ZK proofs allowed)  
- **Diversity requirement**: Invalid if homogeneity ≥80% (prevents group collusion)  
- **Simultaneous resonance**: ≥3 signals required within the same window T (prevents staged acts)  
- **Repetition/compounding**: Repeated deeds on the same theme gain weighted value  
- **Forgiveness/repentance**: Demerit points are erased if ≥1 forgiveness signature is given, or if positive points surpass a threshold  
- **Minimal governance**: Governance rights are minimized; rules are version-locked or time-locked for change  

---

## 1. Minimal Architecture
- **Chain**: Low-cost EVM L2 recommended (gas efficiency), ZK tools compatible  
- **Storage**: On-chain = hash/meta only; off-chain = IPFS (or Arweave)  
- **Anonymity**: ZK identity like Semaphore/MACI (1-person-1-vote, duplicate prevention)  
- Pilot runs may operate without identity, but Sybil-resistance accuracy will be lower  

---

## 2. Data Model (Core Concepts)
- **Experiment**: Experimental unit (title, purpose, tags, meta CID, parameters T, N)  
- **Signal**: Anonymous merit signal submitted by participant (with experiment ID)  
- **Resonance**: Aggregated signals within T (count ≥ N)  
- **DiversityProof**: ZK-proof that resonance group meets diversity ≥20%  
- **MeritSBT**: Non-transferable token for valid resonance (personal/action proof)  
- **DemeritSBT**: Penalty SBT (burned if forgiveness/threshold met)  

---

## 3. Contract Interfaces (Outline)

```solidity
interface IExperimentRegistry {
  event ExperimentCreated(uint256 id, address creator, bytes32 metaHash, uint32 T, uint8 N);
  function create(bytes32 metaHash, uint32 T, uint8 N) external returns (uint256 id);
  function params(uint256 id) external view returns (uint32 T, uint8 N, bytes32 metaHash);
}

interface ISignalHub {
  event SignalSubmitted(uint256 expId, bytes32 nullifier, uint64 ts);
  function submit(uint256 expId, bytes calldata zkProof, bytes32 nullifier) external;
  function windowCount(uint256 expId, uint64 windowKey) external view returns (uint32);
}

interface IDiversityOracle {
  // Verification: off-chain aggregation → ZK proof submission → on-chain verify
  event DiversityVerified(uint256 expId, uint64 windowKey, bool passed);
  function verify(uint256 expId, uint64 windowKey, bytes calldata diversityProof) external returns (bool);
}

interface IMeritLedger {
  event ResonanceValidated(uint256 expId, uint64 windowKey, uint32 count);
  event MeritMinted(address indexed to, uint256 tokenId, uint256 expId, uint64 windowKey, uint16 weight);
  event DemeritForgiven(uint256 tokenId);
  function validateAndMint(uint256 expId, uint64 windowKey, bytes calldata diversityProof) external;
  function mintMerit(address to, uint256 expId, uint64 windowKey, uint16 weight) external;
  function forgive(uint256 demeritTokenId) external; // Forgiveness signature requirements handled in separate module
}
