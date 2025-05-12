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
npx hardhat run scripts/TGpUfotToken.js --network neondevnet
```

## Script Execution Results

When run successfully, the script performs the following operations:

### 1. Token Creation

The script creates a new ERC-20/SPL compatible token called ["Neon Oracle Token"](https://neon-devnet.blockscout.com/address/0xF23C09369FAEDaeAfbC83eD4388ea961d976a53f) with symbol "nOracle" and 9 decimals.

```bash
0xF23C09369FAEDaeAfbC83eD4388ea961d976a53f  ERC20ForSPLMintableAddress
0x2b2f139e35f88ad9629f7570feeca3593e19bc18f6cb61cba14f8698ad9fba29 tokenMint
```

### 2. Token Minting

1000 tokens are minted to the deployer's address.

### 3. Contract Deployment

The [TGpUfotToken contract](https://neon-devnet.blockscout.com/address/0xF23C09369FAEDaeAfbC83eD4388ea961d976a53f ) is deployed on Neon EVM.

And it's corresponding [Neon Address/Public Key](https://explorer.solana.com/address/6M7JeB538VpDaUaavJoH62yTTx7J2FYrZdRGvuVGFmPr?cluster=devnet) is created

