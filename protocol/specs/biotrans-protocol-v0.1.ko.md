# Biotrans Protocol 스펙 v0.1
*(앱 없이 구동 가능한 최소 규약)*

---

## 0. 목적·원칙

**목적**  
선한 행동의 **자발적 공명**만 유효하게 기록·보상한다.

**핵심 원칙 (헌장 발췌)**  
- **연동 금지**: 상점 기록은 신용·대출·고용 등 통제 시스템과 연동 금지  
- **비공개 기본**: 개인 총점은 기본 비공개 (요청 시 범위·합산 ZK 증명만 허용)  
- **다변성 요구**: 동질성 ≥80%면 무효 (집단 몰아주기 차단)  
- **동시 공명**: 같은 윈도 T 내 N≥3 신호 필요 (외식 방지)  
- **반복성/복리**: 동일 주제의 장기 반복에 가중치 부여  
- **용서/회심**: 벌점은 용서 서명 ≥1 또는 상점 누적 임계로 소각  
- **운영 최소화**: 거버넌스 권한 최소화, 규칙은 버전 고정 또는 타임락 변경  

---

## 1. 최소 아키텍처

- **체인**: 저비용 EVM L2 권장 (가스 절감), 영지식 도구 호환  
- **저장**: 온체인 = 해시/메타, 오프체인 = IPFS(또는 Arweave)  
- **익명성**: Semaphore/MACI류 ZK-신원 (1인1표, 중복방지)  
  - *초기 파일럿은 신원 없이도 가능하나, 시빌 방지 정확도 낮음*  

---

## 2. 데이터 모델 (핵심 개념)

- **Experiment**: 실험 단위 (제목, 목적, 태그, 메타 CID, 파라미터 T, N)  
- **Signal**: 참여자가 보내는 익명 상점 신호 (동일 실험 ID로 제출)  
- **Resonance**: T 내 집계된 신호 묶음 (수 ≥ N)  
- **DiversityProof**: 해당 묶음의 다변성 ZK-증명 (≥20% 요구)  
- **MeritSBT**: 유효 공명에 대한 양도불가 토큰 (개인/행위 증표)  
- **DemeritSBT**: 벌점용 SBT (용서/임계 조건 충족 시 소각)  

---

## 3. 컨트랙트 구성 (인터페이스 개요)

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
  // 검증은 오프체인 집계 → ZK 증명 제출 → 온체인 verify
  event DiversityVerified(uint256 expId, uint64 windowKey, bool passed);
  function verify(uint256 expId, uint64 windowKey, bytes calldata diversityProof) external returns (bool);
}

interface IMeritLedger {
  event ResonanceValidated(uint256 expId, uint64 windowKey, uint32 count);
  event MeritMinted(address indexed to, uint256 tokenId, uint256 expId, uint64 windowKey, uint16 weight);
  event DemeritForgiven(uint256 tokenId);
  function validateAndMint(uint256 expId, uint64 windowKey, bytes calldata diversityProof) external;
  function mintMerit(address to, uint256 expId, uint64 windowKey, uint16 weight) external;
  function forgive(uint256 demeritTokenId) external; // 용서 서명 요건은 별도 모듈
}
