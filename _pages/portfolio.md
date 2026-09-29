---
layout: archive
title: "Portfolio"
permalink: /portfolio/
author_profile: true
---

{% include base_path %}

Smart contract
======
#### CMTAT [Taurus SA / Solidity]

> Security token framework to tokenize financial instruments on Ethereum and EVM compatible blockchain.

- Project: CMTAT [Solidity]
- Role: Smart Contract Developer
- Duration: 2022 &mdash; Present
- [GitHub project](https://github.com/CMTA/CMTAT)

**Skills:** Solidity · EVM · Ethereum

#### CMTAT ACE [Taurus SA / CMTA / Solidity]

> Integration of the CMTAT security token with Chainlink ACE (Automated Compliance Engine) for programmable, on-chain compliance through policy-driven controls.

- Role: Smart Contract Developer
- Duration: 12/2025 &mdash; 06/2026
- [GitHub project](https://github.com/CMTA/CMTAT-ACE)
- Made in collaboration with Chainlink.
- Compliance rules are defined as on-chain policies and evaluated by the policy engine for each protected token operation.
- Issuers can configure transaction eligibility and conditions without redeploying the token or modifying its core business logic: KYC/allowlists, sanctions screening, transfer and volume limits, trading-hour restrictions, emergency pauses and reserve-backed minting.

**Skills:** Solidity · Chainlink ACE · Compliance · Security token · RWA

#### CMTAT FIX [Taurus SA / CMTA / Solidity]

> On-chain representation of FIX (Financial Information eXchange) data for CMTAT, using deterministic encoding and a Merkle root commitment instead of storing raw messages.

- Role: Smart Contract Developer (integration and review)
- Duration: 12/2025 &mdash; 05/2026
- [GitHub project](https://github.com/CMTA/CMTAT-FIX)
- The FIX encoding was implemented by Nethermind; it enables efficient verification of structured trade data without on-chain parsing.
- As part of my work at Taurus, I helped integrate the solution into CMTAT and provided feedback on the implementation.

**Skills:** Solidity · FIX protocol · Merkle tree · Security token · RWA

#### Smart Wallet 7702 [Taurus SA / Solidity]

> Smart wallet contract to which an EOA delegates its execution logic with EIP-7702.

- Role: Smart Contract Developer
- Duration: 02/2026 &mdash; 03/2026
- [GitHub project](https://github.com/taurushq-io/smart-wallet-7702)
- Inside the contract, `address(this)` is the EOA address, so multi-owner management is unnecessary: the EOA's private key is the sole authority.
- Features:
  - ERC-4337 UserOperation validation (signature recovery against `address(this)`)
  - Single-call execution (`execute`)
  - Deterministic contract deployment via CREATE2 (`deployDeterministic`)
  - ERC-1271 signature validation with ERC-7739 anti-replay protection
  - ERC-721 and ERC-1155 token reception (`onERC721Received`, `onERC1155Received`, `onERC1155BatchReceived`)
  - ETH receiving (`receive`, `fallback`)

**Skills:** Solidity · EIP-7702 · ERC-4337 · Account abstraction · Smart wallet

#### Chainlink CCIP Sender [Taurus SA / Solidity]

> Study of the CCIP cross-chain bridge by Chainlink with the transfer of USDC between different blockchains as proof-of-concept

- Role: Smart Contract Developer
- Duration: 12/2023 &mdash; 05/2024
- [Github project](https://github.com/taurushq-io/tg-bridge-contracts-CCIP)
- Two articles were published on the Taurus blog, as well as a github project (Sender contract to interact with CCIP).

**Skills:** Solidity · CCIP · Chainlink · cross-chain bridge · Stablecoin

#### IncomeVault [Taurus SA / Solidity]

> IncomeVault to distribute dividend on-chain, build with CMTAT

- Role: Smart Contract Developer
- Duration: 12/2023 &mdash; 05/2024
- [Github project](https://github.com/CMTA/IncomeVault)
- Publish a blog post on Taurus blog describing the architecture: <a href="https://www.taurushq.com/blog/equity-tokenization-how-to-pay-dividend-on-chain-using-cmtat/">Equity Tokenization - How to Pay Dividend On-Chain Using CMTAT</a>

**Skills:** Solidity · Smart Contracts · defi · Foundry · Stablecoin

## Hackathon

#### RuleSelf: Privacy Preserving Transfer Restrictions with Zero Knowledge Identity [ETHGlobal Cannes hackathon / Solidity]

> Privacy-focused transfer restriction rule integrating Self Protocol's zero-knowledge identity verification with CMTAT security tokens.

- Role: Hackathon project, developed during the ETHGlobal hackathon at EthCC 2025
- Duration: 07/2025
- [GitHub project](https://github.com/rya-sge/ruleself)
- Token issuers can apply compliance rules based on verified passport attributes while preserving user privacy through selective disclosure and zero-knowledge proofs.
- Potential use cases include restricting token ownership and transfers based on nationality, age, sanctions screening and verified identity.
- Designed to work with CMTAT and RuleEngine, so compliance checks apply directly to token transfers without exposing sensitive identity information on-chain.

**Skills:** Solidity · Zero-knowledge proofs · Self Protocol · Identity · Security token

## Rust

### Password manager [HEIG-VD]

[GitHub](https://github.com/rya-sge/password-manager)

A password manager to store password securely.

When a user creates an account on the application, an `RSA` key pair is generated. 

- The private key is encrypted using a key derived from the user's master password, and a hash of the master password is stored in `accounts.db`. 
- Passwords added by the user are encrypted with their RSA public key and stored in `passwords.db`. 
- To share a password with another user, the sender uses the recipient’s public key for encryption.

**Skills:** cryptography security
