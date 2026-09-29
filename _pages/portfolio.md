---
layout: archive
title: "Portfolio"
permalink: /portfolio/
author_profile: true
---

{% include base_path %}

[CMTA](#cmta) · [Taurus](#taurus) · [Hackathons](#hackathons) · [HEIG-VD](#heig-vd) · [Personal](#personal)

## CMTA

Open-source projects of the CMTAT ecosystem, developed as part of my work at Taurus SA for the Capital Markets and Technology Association (CMTA).

### CMTAT [Taurus SA / CMTA / Solidity]

> Security token framework to tokenize financial instruments on Ethereum and EVM compatible blockchain.

- Project: CMTAT [Solidity]
- Role: Smart Contract Developer
- Duration: 2022 &mdash; Present
- [GitHub project](https://github.com/CMTA/CMTAT)

**Skills:** Solidity · EVM · Ethereum

### CMTAT ACE [Taurus SA / CMTA / Solidity]

> Integration of the CMTAT security token with Chainlink ACE (Automated Compliance Engine) for programmable, on-chain compliance through policy-driven controls.

- Role: Smart Contract Developer
- Duration: 12/2025 &mdash; 06/2026
- [GitHub project](https://github.com/CMTA/CMTAT-ACE)
- Made in collaboration with Chainlink.
- Compliance rules are defined as on-chain policies and evaluated by the policy engine for each protected token operation.
- Issuers can configure transaction eligibility and conditions without redeploying the token or modifying its core business logic: KYC/allowlists, sanctions screening, transfer and volume limits, trading-hour restrictions, emergency pauses and reserve-backed minting.

**Skills:** Solidity · Chainlink ACE · Compliance · Security token · RWA

### CMTAT FIX [Taurus SA / CMTA / Solidity]

> On-chain representation of FIX (Financial Information eXchange) data for CMTAT, using deterministic encoding and a Merkle root commitment instead of storing raw messages.

- Role: Smart Contract Developer (integration and review)
- Duration: 12/2025 &mdash; 05/2026
- [GitHub project](https://github.com/CMTA/CMTAT-FIX)
- The FIX encoding was implemented by Nethermind; it enables efficient verification of structured trade data without on-chain parsing.
- As part of my work at Taurus, I helped integrate the solution into CMTAT and provided feedback on the implementation.

**Skills:** Solidity · FIX protocol · Merkle tree · Security token · RWA

### CMTAT Confidential [Taurus SA / CMTA / Zama / Solidity]

> Confidential security token combining CMTAT compliance features with the Zama Confidential Blockchain Protocol for private balances.

- Role: Smart Contract Developer
- Duration: 02/2026 &mdash; 07/2026
- [GitHub project](https://github.com/CMTA/CMTAT-Confidential)
- Presented at CMTA x OpenZeppelin: [CMTAT-Confidential: From Public Amounts to Confidential Ones](/talks/2026-09-28-cmtat-confidential)

**Skills:** Solidity · Zama FHEVM · Fully Homomorphic Encryption · Security token

### CMTAT LayerZero [Taurus SA / CMTA / Solidity]

> Example of how a CMTA Token can be bridged with LayerZero.

- Role: Smart Contract Developer
- Duration: 01/2026 &mdash; 02/2026
- [GitHub project](https://github.com/CMTA/CMTAT-LayerZero)

**Skills:** Solidity · LayerZero · Cross-chain bridge

### CMTAT CCIP [Taurus SA / CMTA / Solidity]

> Example of how a CMTA Token can be bridged with Chainlink CCIP, using the Cross-Chain Token (CCT) standard that CMTAT already implements.

- Role: Smart Contract Developer
- Duration: 11/2025
- [GitHub project](https://github.com/rya-sge/CMTAT-CCIP)
- Foundry scripts to deploy a CMTAT token on two testnets (e.g. Sepolia and Avalanche Fuji) and bridge tokens between them with CCIP, adapted from the Chainlink examples repository.

**Skills:** Solidity · Foundry · Chainlink CCIP · Cross-chain bridge

### IncomeVault [Taurus SA / CMTA / Solidity]

> IncomeVault to distribute dividend on-chain, build with CMTAT

- Role: Smart Contract Developer
- Duration: 12/2023 &mdash; 05/2024
- [Github project](https://github.com/CMTA/IncomeVault)
- Publish a blog post on Taurus blog describing the architecture: <a href="https://www.taurushq.com/blog/equity-tokenization-how-to-pay-dividend-on-chain-using-cmtat/">Equity Tokenization - How to Pay Dividend On-Chain Using CMTAT</a>

**Skills:** Solidity · Smart Contracts · defi · Foundry · Stablecoin

## Taurus

### Smart Wallet 7702 [Taurus SA / Solidity]

> Smart wallet contract to which an EOA delegates its execution logic with EIP-7702.

- Role: Smart Contract Developer
- Duration: 01/2026 &mdash; 03/2026
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

### TERC-721 [Taurus SA / Solidity]

> Minimal ERC-721 token with mint and burn, deployable with a proxy (upgradeable) or standalone.

- Role: Smart Contract Developer
- Duration: 01/2025 &mdash; 04/2025
- [GitHub project](https://github.com/taurushq-io/TERC-721)

**Skills:** Solidity · ERC-721 · Upgradeable proxy · Smart contract security

### TERC-20 [Taurus SA / Solidity]

> Minimal ERC-20 token with mint and burn, deployable with a proxy (upgradeable) or standalone.

- Role: Smart Contract Developer
- Duration: 11/2024 &mdash; 03/2025
- [GitHub project](https://github.com/taurushq-io/TERC-20)

**Skills:** Solidity · ERC-20 · Upgradeable proxy · Smart contract security

### TERC-1155A [Taurus SA / Solidity]

> ERC-1155 implementation supporting fungible, non-fungible and semi-fungible tokens in a single contract.

- Role: Smart Contract Developer
- Duration: developed in 2023, published in 07/2025
- [GitHub project](https://github.com/taurushq-io/TERC1155A)
- Proxy support (upgradeable), gasless transactions with ERC-2771, `mint` and `mintBatch`, URI management, role-based access control and ERC-173 ownership.
- Audited; built with OpenZeppelin v4.

**Skills:** Solidity · ERC-1155 · Upgradeable proxy · Smart contract security

### Chainlink CCIP Sender [Taurus SA / Solidity]

> Study of the CCIP cross-chain bridge by Chainlink with the transfer of USDC between different blockchains as proof-of-concept

- Role: Smart Contract Developer
- Duration: 12/2023 &mdash; 05/2024
- [Github project](https://github.com/taurushq-io/tg-bridge-contracts-CCIP)
- Two articles were published on the Taurus blog, as well as a github project (Sender contract to interact with CCIP).

**Skills:** Solidity · CCIP · Chainlink · cross-chain bridge · Stablecoin

## Hackathons

### Sui Identity Hub [BSA Sui hackathon / Move]

> Decentralized identity (W3C) for Sui in Move, with document storage on Walrus through Tusky and wallet management with Dynamic.

- Role: Hackathon project, developed in a team of three during the BSA Sui hackathon
- Duration: 09/2025
- [GitHub project](https://github.com/rya-sge/sui-identity-hub)

**Skills:** Move · Sui · Walrus · Decentralized identity

### RuleSelf: Privacy Preserving Transfer Restrictions with Zero Knowledge Identity [ETHGlobal Cannes hackathon / Solidity]

> Privacy-focused transfer restriction rule integrating Self Protocol's zero-knowledge identity verification with CMTAT security tokens.

- Role: Hackathon project, developed during the ETHGlobal hackathon at EthCC 2025
- Duration: 07/2025
- [GitHub project](https://github.com/rya-sge/ruleself)
- Token issuers can apply compliance rules based on verified passport attributes while preserving user privacy through selective disclosure and zero-knowledge proofs.
- Potential use cases include restricting token ownership and transfers based on nationality, age, sanctions screening and verified identity.
- Designed to work with CMTAT and RuleEngine, so compliance checks apply directly to token transfers without exposing sensitive identity information on-chain.

**Skills:** Solidity · Zero-knowledge proofs · Self Protocol · Identity · Security token

### OTC derivative product on the Sui blockchain [BSA Sui hackathon / Move]

> Prototype to trade derivative products such as options over the counter (OTC).

- Role: Hackathon project, developed in a team during the BSA Sui hackathon
- Duration: 10/2024
- [GitHub project](https://github.com/rya-sge/flow_smart-derivatives)
- The result is a smart contract written in Move and a front-end application to interact with it on the Sui testnet.
- Implements American options on an asset represented by a coin (RWA):
  - Call: the right, but not the obligation, to buy the asset at a set price on or before a set date
  - Put: the right, but not the obligation, to sell the asset at a set price (the strike price) by a set date

**Skills:** Move · Sui · Derivatives · RWA

## HEIG-VD

Projects made during my studies at HEIG-VD.

### Password manager [Rust]

[GitHub](https://github.com/rya-sge/password-manager)

A password manager to store password securely.

When a user creates an account on the application, an `RSA` key pair is generated. 

- The private key is encrypted using a key derived from the user's master password, and a hash of the master password is stored in `accounts.db`. 
- Passwords added by the user are encrypted with their RSA public key and stored in `passwords.db`. 
- To share a password with another user, the sender uses the recipient’s public key for encryption.

**Skills:** Rust · Cryptography · Security

### 2FA with YubiKey [Rust]

[GitHub](https://github.com/rya-sge/2FA-yubikey)

Two-factor authentication (2FA) combining a password and a [YubiKey](https://www.yubico.com/), implemented with HMAC.

**Skills:** Rust · Cryptography · Security

### D-Flip-Flop e-commerce app [Java Spring Boot]

> E-commerce web application built with the Java Spring Boot framework.

- Duration: 09/2021 &mdash; 01/2022
- Team of 5; I was mainly in charge of the authentication part, built as a micro-service.

**Skills:** Java · Spring Boot · Micro-services · Authentication

### Barcodes, iBeacons, NFC [Android / Kotlin]

- Duration: 11/2021 &mdash; 12/2021
- [GitHub](https://github.com/rya-sge/SYM-Labo-3-Environnement)
- Application whose access is secured by the combination of a login/password and an NFC tag.
- Reading of one- or two-dimensional barcodes (e.g. QR codes) and display of their value.
- Listing of the iBeacons nearby.

**Skills:** Android · Kotlin · NFC

### Static site generator [Java]

> Static site generator like Jekyll or Hugo, developed as part of the Software Engineering course.

- Duration: 03/2021 &mdash; 06/2021
- [GitHub](https://github.com/rya-sge/generateur-site-statique-pellissier_ruckstuhl_sauge_viotti)

**Skills:** Java · Software engineering

### SwissCulture web application [Angular / PHP]

> Web application enabling cultural institutions to highlight their content and exhibitions digitally, by publishing images and illustrations with a description in the form of "virtual visits".

- Duration: 02/2021 &mdash; 06/2021
- [GitHub](https://github.com/rya-sge/PRO-Angular-Php)

**Skills:** Angular · PHP · Teamwork

### Spell checker [C++]

> English spell checker built on two duplicate-free hash table structures (linear probing and collision resolution by chaining).

- Duration: 11/2020 &mdash; 01/2021
- [GitHub](https://github.com/rya-sge/Spell-checker)

**Skills:** C++ · Data structures

## Personal

### Crypto Hack Alert

> Public Telegram channel with a configured bot to track and follow crypto hacks and major black swan events (stablecoin depegs, large liquidations).

- Duration: 07/2025 &mdash; Present

**Skills:** Security monitoring · DeFi · Telegram bot
