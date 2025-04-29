# Documentation

# 1. 설치 (Installing)

- **Ethers.js**는 Ethereum과 통신할 수 있게 도와주는 JavaScript 라이브러리야.
- `@ethersproject`라는 작은 하위 패키지들도 있지만, 보통은 그냥 **통합 패키지인 `ethers`** 하나 설치하면 됨.

```bash
npm install --save ethers
```

# 2. 불러오기 (Importing)

- **Node.js 환경**에서 사용할 때
    
    ```jsx
    const { ethers } = require("ethers");
    ```
    
- **ES6이나 TypeScript** 환경에서 사용할 때
    
    ```jsx
    import { ethers } from "ethers";
    ```
    
- **웹 브라우저**에서는
    - **빠르게 데모**나 테스트할 때는 CDN(ethers.io)에서 가져옴.
    - 실제 서비스에서는 보안상 **직접 다운받아**서 자기 서버에서 제공하는 걸 추천.
    
    ### 브라우저에 ES6 방식으로 가져오기
    
    ```html
    <script type="module">
      import { ethers } from "https://cdn.ethers.io/lib/ethers-5.2.esm.min.js";
      // Your code here...
    </script>
    ```
    
    ### 브라우저에 ES3(UMD) 방식으로 가져오기
    
    ```html
    <script src="https://cdn.ethers.io/lib/ethers-5.2.umd.min.js"
            type="application/javascript"></script>
    ```
    

# 3. 주요 용어 (Common Terminology)

| 용어 | 설명 |
| --- | --- |
| **Provider** | 이더리움 네트워크에 연결하고 읽을 수 있게 해주는 객체 (읽기 전용) |
| **Signer** | 개인키를 가지고 있고, 트랜잭션이나 메시지를 "서명"할 수 있는 객체 |
| **Contract** | 이더리움 스마트컨트랙트와 연결해서 메소드를 호출하거나 상태를 읽을 수 있게 해주는 객체 |

# 4. 이더리움 연결 방법

## (1) MetaMask를 통한 연결

```jsx
const provider = new ethers.providers.Web3Provider(window.ethereum);

// 사용자에게 연결 허가 요청
await provider.send("eth_requestAccounts", []);

// signer 가져오기 (트랜잭션 보낼 때 필요)
const signer = provider.getSigner();
```

→ **MetaMask**는 `window.ethereum`을 브라우저에 주입해줘서 쉽게 접근 가능함.

## (2) RPC를 통한 연결

(직접 노드나 INFURA 같은 서비스에 연결)

```jsx
const provider = new ethers.providers.JsonRpcProvider();
// 기본적으로 localhost:8545 연결
const signer = provider.getSigner(
```

# 5. 블록체인 조회 (Querying the Blockchain)

Provider를 통해 읽기 작업을 할 수 있어.

### 예시

```jsx
// 현재 블록 번호 조회
await provider.getBlockNumber();

// 주소의 잔액 조회 (wei 단위로 나옴)
let balance = await provider.getBalance("ethers.eth");

// 보기 좋게 ether 단위로 변환
ethers.utils.formatEther(balance);

// 입력값(ether)을 wei로 변환
ethers.utils.parseEther("1.0");

```

---

# 6. 블록체인 쓰기 (Writing to the Blockchain)

## (1) 이더 송금하기

```jsx
const tx = signer.sendTransaction({
    to: "ricmoo.firefly.eth",
    value: ethers.utils.parseEther("1.0")
});
```

→ 1 ether를 보내는 트랜잭션 발생.

---

# 7. 스마트컨트랙트 사용하기 (Contracts)

**Contract 객체**를 만들면 자바스크립트처럼 스마트컨트랙트를 쉽게 조작할 수 있음.

- **필수**: Contract의 주소, ABI(인터페이스), Provider 또는 Signer

### 예시

```jsx
const daiAddress = "dai.tokens.ethers.eth"; // ENS 주소 사용 가능
const daiAbi = [
  "function name() view returns (string)",
  "function symbol() view returns (string)",
  "function balanceOf(address) view returns (uint)",
  "function transfer(address to, uint amount)",
  "event Transfer(address indexed from, address indexed to, uint amount)"
];
const daiContract = new ethers.Contract(daiAddress, daiAbi, provider);

```

---

## (1) 읽기 메소드 호출 (읽기 전용)

```jsx
await daiContract.name();    // "Dai Stablecoin"
await daiContract.symbol();  // "DAI"
await daiContract.balanceOf("ricmoo.firefly.eth");
```

> 결과는 BigNumber로 나오니까 ethers.utils.formatUnits를 사용해서 사람이 읽을 수 있게 변환.
> 

---

## (2) 쓰기 메소드 호출 (상태 변경)

- 상태를 바꾸려면 **Signer**가 연결된 Contract 객체 필요

```jsx
const daiWithSigner = daiContract.connect(signer);
const dai = ethers.utils.parseUnits("1.0", 18); // 1 DAI = 10^18

const tx = daiWithSigner.transfer("ricmoo.firefly.eth", dai);

```

---

# 8. 이벤트 듣기 (Listening to Events)

- 특정 이벤트 발생을 실시간으로 수신 가능

```jsx
// 모든 Transfer 이벤트 듣기
daiContract.on("Transfer", (from, to, amount, event) => {
    console.log(`${from} sent ${ethers.utils.formatEther(amount)} to ${to}`);
});

// 특정 주소로 전송된 Transfer만 듣기
const myAddress = "0x8ba1f109551bD432803012645Ac136ddd64DBA72";
const filter = daiContract.filters.Transfer(null, myAddress);

daiContract.on(filter, (from, to, amount, event) => {
    console.log(`I got ${ethers.utils.formatEther(amount)} from ${from}`);
});

```

---

# 9. 과거 이벤트 조회 (Querying Historic Events)

- 과거 블록 범위로 이벤트를 필터링해서 조회 가능

```jsx
// 특정 주소가 보낸 Transfer만 조회
const filterFrom = daiContract.filters.Transfer(myAddress, null);
const logs = await daiContract.queryFilter(filterFrom, 9843470, 9843480);
```

---

# 10. 메시지 서명하기 (Signing Messages)

- 개인키로 임의의 메시지를 서명할 수 있음
- 주로 로그인, 인증 등에 사용됨

```jsx
// 문자열 서명
const signature = await signer.signMessage("Hello World");

// 해시(32바이트) 서명
const messageHash = "0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef";
const messageBytes = ethers.utils.arrayify(messageHash);
const signatureHash = await signer.signMessage(messageBytes);
```