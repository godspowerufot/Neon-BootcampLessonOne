# ERC-20-for-SPL Deployment and Composability Request Task
## Overview

This project showcases how to:

1. Create an ERC-20 token that's compatible with Solana SPL tokens
2. Deploy a custom token contract with cross-chain capabilities
3. Execute token transfers between Neon EVM and Solana ecosystems

## Prerequisites

- Node.js v16+ and npm
- Hardhat
- Solana CLI tools
- Account with SOL on Solana devnet
- Account with NEON on Neon EVM devnet

## Environment Setup

Create a `.env` file with the following variables:

```
PRIVATE_KEY_OWNER=your_ethereum_private_key
USER1_KEY=additional_ethereum_private_key
PRIVATE_KEY_SOLANA=your_solana_private_key_in_base58
```

## Installation

```bash
npm install
```

## Running the Demo

Execute the demonstration script:

```bash
npx hardhat run scripts/TestNeonOracleToken.js --network neondevnet
```

## Script Execution Results

When run successfully, the script performs the following operations:

### 1. Token Creation

The script creates a new ERC-20/SPL compatible token called ["Neon Oracle Token"](https://neon-devnet.blockscout.com/address/0x60828360df667893a4696632706A2cC20CFDe41C) with symbol "nOracle" and 9 decimals.

```bash
0x60828360df667893a4696632706A2cC20CFDe41C ERC20ForSPLMintableAddress
0xb591df3002a67e89fe5b342386f3b4a7dbefddeec070bea8a06636a65ad00292 tokenMint
```

### 2. Token Minting

1000 tokens are minted to the deployer's address.

### 3. Contract Deployment

The [TestNeonOracleToken contract](https://neon-devnet.blockscout.com/address/0xbB13958d820189336e04d86FC292134C691F8f9C) is deployed on Neon EVM.

And it's corresponding [Neon Address/Public Key](https://explorer.solana.com/address/GPTjmtiSJfu12YK7DrUJ6crLzZ87WjyFxAdUdnr1VRN?cluster=devnet) is created


```bash
TestNeonOracleToken deployed to 0xbB13958d820189336e04d86FC292134C691F8f9C
GPTjmtiSJfu12YK7DrUJ6crLzZ87WjyFxAdUdnr1VRN contractPublicKey
```

### 4. Solana Account Setup

Associated Token Accounts (ATAs) are [created](https://explorer.solana.com/tx/5yoPvUBkLYNJRUDfuQcLJYKmxrJqZsVYwADpZJbssXQLGG4jkgQLazGAsh4bzQqUyFUynnuW6U6SEWQxm539fqeo?cluster=devnet) on Solana for both the contract and a random recipient account.

```bash
PublicKey [PublicKey(3cHQW7CmNw7vWgBw5om5HAWushNie8DSSgwUp6SSWXe8)] {
  _bn: <BN: 26c14068749286375fc06c3f441def0968003f3df2e2538ec47b2352acc00419>
} senderATA
```

```bash
PublicKey [PublicKey(9WscvyZUAV6gjetSyQ24vTNQuTocEVEWdm1HWNM6y8vn)] {
  _bn: <BN: 7e84931393362fff3f574856e50e5b49b5bce8ba715436c25426f4d0a7e7767b>
} recipientATA

```

```bash
5yoPvUBkLYNJRUDfuQcLJYKmxrJqZsVYwADpZJbssXQLGG4jkgQLazGAsh4bzQqUyFUynnuW6U6SEWQxm539fqeo ---- transaction sender & recipient ATA's creation
```

### 5. Cross-Chain Transfer

10 tokens are transferred from Neon EVM to the Solana account.

```bash
ContractTransactionResponse {
  provider: HardhatEthersProvider {
    _hardhatProvider: LazyInitializationProviderAdapter {
      _providerFactory: [AsyncFunction (anonymous)],
      _emitter: [EventEmitter],
      _initializingPromise: [Promise],
      provider: [BackwardsCompatibilityProviderAdapter]
    },
    _networkName: 'neondevnet',
    _blockListeners: [],
    _transactionHashListeners: Map(0) {},
    _eventListeners: [],
    _isHardhatNetworkCached: false,
    _transactionHashPollingTimeout: undefined
  },
  blockNumber: null,
  blockHash: null,
  index: undefined,
  hash: '0x06032ef6bea0d3a0e049b18ca6b8d0394cfe861a5c33922625233f5662fa0f2e',
  type: 2,
  to: '0x60828360df667893a4696632706A2cC20CFDe41C',
  from: '0x9c383a628Ce60F5CE4EFAd90AD3835F39eBbA6ce',
  nonce: 3,
  gasLimit: 1243135n,
  gasPrice: 2512005768117n,
  maxPriorityFeePerGas: 1984794680981n,
  maxFeePerGas: 2512005768117n,
  maxFeePerBlobGas: null,
  data: '0x095ea7b3000000000000000000000000bb13958d820189336e04d86fc292134c691f8f9c00000000000000000000000000000000000000000000000000000002540be400',  value: 0n,
  chainId: 245022926n,
  signature: Signature { r: "0x30c8c2c17621be066a26dd1b31a9ee88eb4040e9df9cfbe6ea1f0db5ba2460e3", s: "0x0325ae9302eebd2ca355a651ef697f4e4ea29cea9835e907bed6d3116fddb759", yParity: 0, networkV: null },
  accessList: null,
  blobVersionedHashes: null,
  authorizationList: null
} erc20forspl approve

```

```bash
ContractTransactionResponse {
  provider: HardhatEthersProvider {
    _hardhatProvider: LazyInitializationProviderAdapter {
      _providerFactory: [AsyncFunction (anonymous)],
      _emitter: [EventEmitter],
      _initializingPromise: [Promise],
      provider: [BackwardsCompatibilityProviderAdapter]
    },
    _networkName: 'neondevnet',
    _blockListeners: [],
    _transactionHashListeners: Map(0) {},
    _eventListeners: [],
    _isHardhatNetworkCached: false,
    _transactionHashPollingTimeout: undefined
  },
  blockNumber: null,
  blockHash: null,
  index: undefined,
  hash: '0x58d4273f01ec22d87988a2b90d2d4e5696bc089992052e8569e492331a5954cd',
  type: 2,
  to: '0xbB13958d820189336e04d86FC292134C691F8f9C',
  from: '0x9c383a628Ce60F5CE4EFAd90AD3835F39eBbA6ce',
  nonce: 4,
  gasLimit: 2230271n,
  gasPrice: 2512005768117n,
  maxPriorityFeePerGas: 1984794680981n,
  maxFeePerGas: 2512005768117n,
  maxFeePerBlobGas: null,
  data: '0x74ee1fb500000000000000000000000000000000000000000000000000000002540be400acb4b3f9e2263a0c8f74556b1936b4a9568c8c8bc1ab060af6c6a950cdd7c865',  value: 0n,
  chainId: 245022926n,
  signature: Signature { r: "0xd033aeacec9eac9437622f61c3e0c9bb722fded988dd94435b11eef46a4bf118", s: "0x52890ad3b076007fd7689b4668d706c87bff306ced79ce2498940c602fa79491", yParity: 1, networkV: null },
  accessList: null,
  blobVersionedHashes: null,
  authorizationList: null
} TestNeonOracleToken transfer
```

## Verification

After running the script, you can verify the token transfer:

1. **On Neon EVM**: Check the ERC20 token balance of your account

   ```
   // The balance should be 990 tokens (1000 minted - 10 transferred)
   ```

2. **On Solana**: Check the SPL token balance of the random account. The balance should be 10 tokens (received from Neon EVM)

    https://explorer.solana.com/address/9WscvyZUAV6gjetSyQ24vTNQuTocEVEWdm1HWNM6y8vn/tokens?cluster=devnet

You can use blockchain explorers to verify:

- Neon EVM Explorer: https://neon-devnet.blockscout.com/
- Solana Explorer: https://explorer.solana.com/?cluster=devnet
