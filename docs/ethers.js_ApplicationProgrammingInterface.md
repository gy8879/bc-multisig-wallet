# Application Programming Interface

<aside>
💡

Wallet + Provider + BigNumber + Units

</aside>

- **Wallet 생성** (랜덤, 니모닉, 프라이빗 키)
- **Provider 연결** (MetaMask, RPC URL, Infura 등)
- **잔액 조회** (`wallet.getBalance()`)
- **트랜잭션 전송** (`wallet.sendTransaction()`)
- **서명(Signing) 및 메시지 인증(Optional)** (`wallet.signMessage()`)

An Application Programming Interface (API) is the formal specification of the library.

## [Providers](https://docs.ethers.org/v5/api/providers/)

[[Provider](https://docs.ethers.org/v5/api/providers/provider/)](https://www.notion.so/Provider-1e3ef8c12b88806bb80fe081a70b3a25?pvs=21)

- [Accounts Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--account-methods)
- [Blocks Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--block-methods)
- [Ethereum Naming Service (ENS) Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--ens-methods)
- [EnsResolver](https://docs.ethers.org/v5/api/providers/provider/#EnsResolver)
- [Logs Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--log-methods)
- [Network Status Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--network-methods)

[[Transactions Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--transaction-methods)](https://www.notion.so/Transactions-Methods-1e3ef8c12b8880bb98b4f82e60b26f29?pvs=21)

- [Event Emitter Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--event-methods)
- [Inspection Methods](https://docs.ethers.org/v5/api/providers/provider/#Provider--inspection-methods)
- [BaseProvider](https://docs.ethers.org/v5/api/providers/provider/#BaseProvider)

[[JsonRpcProvider](https://docs.ethers.org/v5/api/providers/jsonrpc-provider/)](https://www.notion.so/JsonRpcProvider-1e3ef8c12b8880e7a999e483ba5cb9db?pvs=21)

- [JsonRpcSigner](https://docs.ethers.org/v5/api/providers/jsonrpc-provider/#JsonRpcSigner)
- [JsonRpcUncheckedSigner](https://docs.ethers.org/v5/api/providers/jsonrpc-provider/#UncheckedJsonRpcSigner)
- [StaticJsonRpcProvider](https://docs.ethers.org/v5/api/providers/jsonrpc-provider/#StaticJsonRpcProvider)
- [Node-Specific Methods](https://docs.ethers.org/v5/api/providers/jsonrpc-provider/#JsonRpcProvider--other)

### [API Providers](https://docs.ethers.org/v5/api/providers/api-providers/)

- [EtherscanProvider](https://docs.ethers.org/v5/api/providers/api-providers/#EtherscanProvider)
- [InfuraProvider](https://docs.ethers.org/v5/api/providers/api-providers/#InfuraProvider)
- [AlchemyProvider](https://docs.ethers.org/v5/api/providers/api-providers/#AlchemyProvider)
- [CloudflareProvider](https://docs.ethers.org/v5/api/providers/api-providers/#CloudflareProvider)
- [PocketProvider](https://docs.ethers.org/v5/api/providers/api-providers/#PocketProvider)
- [AnkrProvider](https://docs.ethers.org/v5/api/providers/api-providers/#AnkrProvider)

### [Other Providers](https://docs.ethers.org/v5/api/providers/other/)

[[FallbackProvider](https://docs.ethers.org/v5/api/providers/other/#FallbackProvider)](https://www.notion.so/FallbackProvider-1e3ef8c12b8880e0b367dd2692b270aa?pvs=21)

- [IpcProvider](https://docs.ethers.org/v5/api/providers/other/#IpcProvider)
- [JsonRpcBatchProvider](https://docs.ethers.org/v5/api/providers/other/#JsonRpcBatchProvider)
- [UrlJsonRpcProvider](https://docs.ethers.org/v5/api/providers/other/#UrlJsonRpcProvider)

[[Web3Provider](https://docs.ethers.org/v5/api/providers/other/#Web3Provider)](https://www.notion.so/Web3Provider-1e3ef8c12b888060ae27c8032145ce2d?pvs=21)

- [WebSocketProvider](https://docs.ethers.org/v5/api/providers/other/#WebSocketProvider)

### [Types](https://docs.ethers.org/v5/api/providers/types/)

- [BlockTag](https://docs.ethers.org/v5/api/providers/types/#providers-BlockTag)
- [Networkish](https://docs.ethers.org/v5/api/providers/types/#providers-Networkish)
- [Network](https://docs.ethers.org/v5/api/providers/types/#providers-Network)
- [FeeData](https://docs.ethers.org/v5/api/providers/types/#providers-FeeData)
- [Block](https://docs.ethers.org/v5/api/providers/types/#providers-Block)
- [Events and Logs](https://docs.ethers.org/v5/api/providers/types/#types--events-and-logs)
- [Transactions](https://docs.ethers.org/v5/api/providers/types/#types--transactions)
- [Access Lists](https://docs.ethers.org/v5/api/providers/types/#types--access-lists)

## [Signers](https://docs.ethers.org/v5/api/signer/)

[[Signer](https://docs.ethers.org/v5/api/signer/#Signer)](https://www.notion.so/Signer-1e3ef8c12b8880d3a520cbcd52e7072d?pvs=21)

[[Wallet](https://docs.ethers.org/v5/api/signer/#Wallet)](https://www.notion.so/Wallet-1e3ef8c12b88800b8169e59fb6094d15?pvs=21)

[[VoidSigner](https://docs.ethers.org/v5/api/signer/#VoidSigner)](https://www.notion.so/VoidSigner-1e3ef8c12b88809bb3b0c7b56cb441e1?pvs=21)

[[ExternallyOwnedAccount](https://docs.ethers.org/v5/api/signer/#ExternallyOwnedAccount)](https://www.notion.so/ExternallyOwnedAccount-1e3ef8c12b88803895b7eedd07ed08c9?pvs=21)

## [Contract Interaction](https://docs.ethers.org/v5/api/contract/)

### [Contract](https://docs.ethers.org/v5/api/contract/contract/)

- [Creating Instances](https://docs.ethers.org/v5/api/contract/contract/#Contract--creating)
- [Properties](https://docs.ethers.org/v5/api/contract/contract/#Contract--properties)
- [Methods](https://docs.ethers.org/v5/api/contract/contract/#Contract--methods)
- [Events](https://docs.ethers.org/v5/api/contract/contract/#Contract--events)
- [Meta-Class](https://docs.ethers.org/v5/api/contract/contract/#Contract--metaclass)

### [ContractFactory](https://docs.ethers.org/v5/api/contract/contract-factory/)

- [Creating Instances](https://docs.ethers.org/v5/api/contract/contract-factory/#ContractFactory--creating)
- [Properties](https://docs.ethers.org/v5/api/contract/contract-factory/#ContractFactory--properties)
- [Methods](https://docs.ethers.org/v5/api/contract/contract-factory/#ContractFactory--methods)

### [Example: ERC-20 Contract](https://docs.ethers.org/v5/api/contract/example/)

- [Deploying a Contract](https://docs.ethers.org/v5/api/contract/example/#example-erc-20-contract--deploying-a-contract)
- [Connecting to a Contract](https://docs.ethers.org/v5/api/contract/example/#example-erc-20-contract--connecting-to-a-contract)
- [Properties](https://docs.ethers.org/v5/api/contract/example/#example-erc-20-contract--properties)
- [Methods](https://docs.ethers.org/v5/api/contract/example/#example-erc-20-contract--methods)
- [Events](https://docs.ethers.org/v5/api/contract/example/#erc20-events)
- [Meta-Class Methods](https://docs.ethers.org/v5/api/contract/example/#erc20-meta-methods)
- [Meta-Class Filters](https://docs.ethers.org/v5/api/contract/example/#erc20-meta-events)

## [Utilities](https://docs.ethers.org/v5/api/utils/)

### [Application Binary Interface](https://docs.ethers.org/v5/api/utils/abi/)

- [AbiCoder](https://docs.ethers.org/v5/api/utils/abi/coder/)
- [Creating Instance](https://docs.ethers.org/v5/api/utils/abi/coder/#AbiCoder--creating)
- [Coding Methods](https://docs.ethers.org/v5/api/utils/abi/coder/#AbiCoder--methods)
- [ABI Formats](https://docs.ethers.org/v5/api/utils/abi/formats/)
- [Human-Readable ABI](https://docs.ethers.org/v5/api/utils/abi/formats/#abi-formats--human-readable-abi)
- [Solidity JSON ABI](https://docs.ethers.org/v5/api/utils/abi/formats/#abi-formats--solidity)
- [Solidity Object ABI](https://docs.ethers.org/v5/api/utils/abi/formats/#abi-formats--object)
- [Converting Between Formats](https://docs.ethers.org/v5/api/utils/abi/formats/#abi-formats--converting-between-formats)
- [Fragments](https://docs.ethers.org/v5/api/utils/abi/fragments/)
- [Formats](https://docs.ethers.org/v5/api/utils/abi/fragments/#fragments--formats)
- [Fragment](https://docs.ethers.org/v5/api/utils/abi/fragments/#Fragment)
- [ConstructorFragment](https://docs.ethers.org/v5/api/utils/abi/fragments/#ConstructorFragment)
- [ErrorFragment](https://docs.ethers.org/v5/api/utils/abi/fragments/#ErrorFragment)
- [EventFragment](https://docs.ethers.org/v5/api/utils/abi/fragments/#EventFragment)
- [FunctionFragment](https://docs.ethers.org/v5/api/utils/abi/fragments/#FunctionFragment)
- [ParamType](https://docs.ethers.org/v5/api/utils/abi/fragments/#ParamType)
- [Interface](https://docs.ethers.org/v5/api/utils/abi/interface/)
- [Creating Instances](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--creating)
- [Properties](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--properties)
- [Formatting](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--formatting)
- [Fragment Access](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--fragments)
- [Signature and Topic Hashes](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--selectors)
- [Encoding Data](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--encoding)
- [Decoding Data](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--decoding)
- [Parsing](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--parsing)
- [Types](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--types)
- [Specifying Fragments](https://docs.ethers.org/v5/api/utils/abi/interface/#Interface--specifying-fragments)

[[Addresses](https://docs.ethers.org/v5/api/utils/address/)](https://www.notion.so/Addresses-1e3ef8c12b8880a383bad092681b93d8?pvs=21)

- [Address Formats](https://docs.ethers.org/v5/api/utils/address/#address-formats)
- [Converting and Verifying](https://docs.ethers.org/v5/api/utils/address/#utils--address)
- [Derivation](https://docs.ethers.org/v5/api/utils/address/#utils--address-derivation)
- [Contracts Addresses](https://docs.ethers.org/v5/api/utils/address/#utils--contract-addresses)

[[BigNumber](https://docs.ethers.org/v5/api/utils/bignumber/)](https://www.notion.so/BigNumber-1e3ef8c12b888018a5a7edf1e3488475?pvs=21)

- [Types](https://docs.ethers.org/v5/api/utils/bignumber/#BigNumber--types)
- [Creating Instances](https://docs.ethers.org/v5/api/utils/bignumber/#BigNumber--creating)
- [Methods](https://docs.ethers.org/v5/api/utils/bignumber/#BigNumber--methods)
- [Notes](https://docs.ethers.org/v5/api/utils/bignumber/#BigNumber--notes)

### [Byte Manipulation](https://docs.ethers.org/v5/api/utils/bytes/)

- [Types](https://docs.ethers.org/v5/api/utils/bytes/#byte-manipulation--types)
- [Inspection](https://docs.ethers.org/v5/api/utils/bytes/#byte-manipulation--inspection)
- [Converting between Arrays and Hexstrings](https://docs.ethers.org/v5/api/utils/bytes/#byte-manipulation--converting-between-arrays-and-hexstrings)
- [Array Manipulation](https://docs.ethers.org/v5/api/utils/bytes/#byte-manipulation--array-manipulation)
- [Hexstring Manipulation](https://docs.ethers.org/v5/api/utils/bytes/#byte-manipulation--hexstring-manipulation)
- [Signature Conversion](https://docs.ethers.org/v5/api/utils/bytes/#byte-manipulation--signature-conversion)
- [Random Bytes](https://docs.ethers.org/v5/api/utils/bytes/#byte-manipulation--random-bytes)

### [Constants](https://docs.ethers.org/v5/api/utils/constants/)

- [Bytes](https://docs.ethers.org/v5/api/utils/constants/#constants--bytes)
- [Strings](https://docs.ethers.org/v5/api/utils/constants/#constants--strings)

[[BigNumber](https://docs.ethers.org/v5/api/utils/constants/#constants--bignumber)](https://www.notion.so/BigNumber-1e3ef8c12b88804e8753d1a1dd1ac542?pvs=21)

### [Display Logic and Input](https://docs.ethers.org/v5/api/utils/display-logic/)

[[Units](https://docs.ethers.org/v5/api/utils/display-logic/#display-logic--units)](https://www.notion.so/Units-1e3ef8c12b88806e9973d3b232bd0ec9?pvs=21)

- [Functions](https://docs.ethers.org/v5/api/utils/display-logic/#display-logic--functions)

### [Encoding Utilities](https://docs.ethers.org/v5/api/utils/encoding/)

- [Base58](https://docs.ethers.org/v5/api/utils/encoding/#Bse58)
- [Base64](https://docs.ethers.org/v5/api/utils/encoding/#Base64)
- [Recursive-Length Prefix](https://docs.ethers.org/v5/api/utils/encoding/#rlp--methods)

### [FixedNumber](https://docs.ethers.org/v5/api/utils/fixednumber/)

- [Creating Instances](https://docs.ethers.org/v5/api/utils/fixednumber/#FixedNumber--creating-instances)
- [Properties](https://docs.ethers.org/v5/api/utils/fixednumber/#FixedNumber--properties)
- [Methods](https://docs.ethers.org/v5/api/utils/fixednumber/#FixedNumber--methods)
- [FixedFormat](https://docs.ethers.org/v5/api/utils/fixednumber/#FixedFormat)

[[Hashing Algorithms](https://docs.ethers.org/v5/api/utils/hashing/)](https://www.notion.so/Hashing-Algorithms-1e3ef8c12b8880a9ac8fce2bbb915cc0?pvs=21)

- [Cryptographic Hash Functions](https://docs.ethers.org/v5/api/utils/hashing/#cryptographic-hash-functions)
- [HMAC](https://docs.ethers.org/v5/api/utils/hashing/#utils--hmac)
- [Hashing Helpers](https://docs.ethers.org/v5/api/utils/hashing/#utils--hashing-helpers)
- [Solidity Hashing Algorithms](https://docs.ethers.org/v5/api/utils/hashing/#utils--solidity-hashing)

[[HD Wallet](https://docs.ethers.org/v5/api/utils/hdnode/)](https://www.notion.so/HD-Wallet-1e3ef8c12b8880e2add1f6b7296fe1bf?pvs=21)

- [Types](https://docs.ethers.org/v5/api/utils/hdnode/#hdnodes--types)
- [HDNode](https://docs.ethers.org/v5/api/utils/hdnode/#HDNode)
- [Other Functions](https://docs.ethers.org/v5/api/utils/hdnode/#HDNode--utilities)

### [Logging](https://docs.ethers.org/v5/api/utils/logger/)

- [Logger](https://docs.ethers.org/v5/api/utils/logger/#Logger)
- [Errors](https://docs.ethers.org/v5/api/utils/logger/#errors)
- [Log Levels](https://docs.ethers.org/v5/api/utils/logger/#Logger-levels)

### [Property Utilities](https://docs.ethers.org/v5/api/utils/properties/)

### [Signing Key](https://docs.ethers.org/v5/api/utils/signing-key/)

- [Other Functions](https://docs.ethers.org/v5/api/utils/signing-key/#SigningKey--other-functions)

### [Strings](https://docs.ethers.org/v5/api/utils/strings/)

- [Bytes32String](https://docs.ethers.org/v5/api/utils/strings/#Bytes32String)
- [UTF-8 Strings](https://docs.ethers.org/v5/api/utils/strings/#strings-utf8)
- [UnicodeNormalizationForm](https://docs.ethers.org/v5/api/utils/strings/#strings--unicode-normalization-form)
- [Custom UTF-8 Error Handling](https://docs.ethers.org/v5/api/utils/strings/#strings--error-handling)

### [Transactions](https://docs.ethers.org/v5/api/utils/transactions/)

- [Types](https://docs.ethers.org/v5/api/utils/transactions/#transactions--types)
- [Functions](https://docs.ethers.org/v5/api/utils/transactions/#transactions--functions)

### [Web Utilities](https://docs.ethers.org/v5/api/utils/web/)

### [Wordlists](https://docs.ethers.org/v5/api/utils/wordlists/)

- [Wordlist](https://docs.ethers.org/v5/api/utils/wordlists/#Wordlist)
- [Languages](https://docs.ethers.org/v5/api/utils/wordlists/#wordlists--languages)

## [Other Libraries](https://docs.ethers.org/v5/api/other/)

### [Assembly](https://docs.ethers.org/v5/api/other/assembly/)

- [Ethers ASM Dialect](https://docs.ethers.org/v5/api/other/assembly/dialect/)
- [Opcodes](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-opcode)
- [Labels](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-label)
- [Literals](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-literal)
- [Comments](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-comment)
- [Scopes](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-scope)
- [Data Segment](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-datasegment)
- [Links](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-links)
- [Stack Placeholders](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-placeholder)
- [Evaluation and Execution](https://docs.ethers.org/v5/api/other/assembly/dialect/#asm-dialect-scripting)
- [Utilities](https://docs.ethers.org/v5/api/other/assembly/api/)
- [Assembler](https://docs.ethers.org/v5/api/other/assembly/api/#asm-utilities--assembler)
- [Disassembler](https://docs.ethers.org/v5/api/other/assembly/api/#asm-utilities--disassembler)
- [Opcode](https://docs.ethers.org/v5/api/other/assembly/api/#asm-opcode)
- [Abstract Syntax Tree](https://docs.ethers.org/v5/api/other/assembly/ast/)
- [Types](https://docs.ethers.org/v5/api/other/assembly/ast/#asm-ast--types)
- [Nodes](https://docs.ethers.org/v5/api/other/assembly/ast/#asm-ast--nodes)

### [Hardware Wallets](https://docs.ethers.org/v5/api/other/hardware/)

- [LedgerSigner](https://docs.ethers.org/v5/api/other/hardware/#hw-ledger)

## [Experimental](https://docs.ethers.org/v5/api/experimental/)

- [BrainWallet](https://docs.ethers.org/v5/api/experimental/#experimental-brainwallet)
- [EIP1193Bridge](https://docs.ethers.org/v5/api/experimental/#experimental-eip1193bridge)
- [NonceManager](https://docs.ethers.org/v5/api/experimental/#experimental-noncemanager)