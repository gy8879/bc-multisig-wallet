# Provider API Keys

### (1) API 키란?

- **Ethers.js Provider**는 백엔드 서비스(Alchemy, Etherscan, INFURA 등)를 통해 Ethereum에 연결할 때, **API Key**를 사용해.
- API Key는 **각 프로젝트 식별 및 사용량 관리**를 위해 필요해.
- Ethers.js는 기본 공유 API 키를 제공해서, **설치하자마자** 아무 설정 없이 작동하게 되어있음.

✅ **하지만** 공유 키는 사용자 수가 많아서 **속도가 느리고 제한이 심함(=throttle)**.

✅ **따라서** **개별적으로** 무료 API 키를 발급받아서 사용하는 걸 **강력 추천**함.

---

### (2) 직접 API Key 발급받으면 좋은 점

- 요청 속도가 훨씬 빠름 (rate limit 상승)
- 오류 재시도(retry)나 시간 초과(timeout) 확률이 낮음
- 프로젝트별 사용량 추적 가능
- 고급 기능 (예: archive 데이터, 고급 로그 검색) 이용 가능

# 주요 API 서비스 소개

| 서비스 | 설명 및 특징 | 지원 네트워크 |
| --- | --- | --- |
| **Etherscan** | 이더리움 블록 탐색기. 이더리움 상태를 쉽게 조회할 수 있는 API 제공. | homestead, goerli, sepolia, matic 등 |
| **INFURA** | 안정적이고 오래된 Ethereum 노드 제공 서비스. JSON-RPC & WebSocket 지원. | homestead, goerli, sepolia, matic 등 |
| **Alchemy** | INFURA처럼 노드를 제공하고, 추가로 디버깅 도구/토큰 관련 고급 API도 제공. | homestead, goerli, matic 등 |
| **Pocket Gateway** | 탈중앙화된 노드 인프라 제공. 노드를 자체적으로 분산 운영. | homestead |
| **Ankr** | 비교적 고성능이고, 초기 개발에서는 API 키 없이도 사용 가능. | homestead, matic, arbitrum 등 |

✅ 각 서비스마다 가입해서 무료 API 키 발급 가능함.

# Default Provider 생성하기

- *기본 Provider (`ethers.getDefaultProvider`)**는 여러 API 서비스를 동시에 연결해서 결과를 비교 검증하는 방식으로 동작함.
- 기본 키를 쓰면 성능이 낮기 때문에, 직접 API 키를 제공하는 게 훨씬 좋음.

---

# 4. 예시 코드 설명

```jsx
const network = "homestead";  // 메인넷에 연결

// API 키를 설정
const provider = ethers.getDefaultProvider(network, {
    etherscan: YOUR_ETHERSCAN_API_KEY,
    infura: YOUR_INFURA_PROJECT_ID,
    // INFURA를 프로젝트 시크릿까지 설정할 수도 있음
    // infura: {
    //   projectId: YOUR_INFURA_PROJECT_ID,
    //   projectSecret: YOUR_INFURA_PROJECT_SECRET,
    // },
    alchemy: YOUR_ALCHEMY_API_KEY,
    pocket: YOUR_POCKET_APPLICATION_KEY,
    // Pocket도 시크릿까지 옵션으로 줄 수 있음
    // pocket: {
    //   applicationId: YOUR_POCKET_APPLICATION_ID,
    //   applicationSecretKey: YOUR_POCKET_SECRET,
    // },
    ankr: YOUR_ANKR_API_KEY
});
```

- `network`는 연결할 네트워크 이름 (예: "homestead" = 메인넷).
- `ethers.getDefaultProvider`의 두 번째 인자에 `{ 서비스명: API키 }` 형태로 넣음.
- 각 서비스에 대해 원하는 키만 제공해도 되고, 일부만 줘도 되고, 전부 줄 수도 있음.
- 키를 하나도 안 주면 Ethers 기본 키 사용 → 성능 떨어짐.

**참고:**

- 특정 Provider를 아예 쓰지 않으려면 키 값에 `"-"`를 넣으면 됨.