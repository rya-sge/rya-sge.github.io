---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Work experience
======
### Security engineer [12/2022 - present]

- Company: [Taurus SA](https://www.taurushq.com)
- Position: Security engineer
- Summary: 

Development of smart contracts (Solidity) with Foundry, Hardhat and Truffle.

Analysis of smart contracts written in Solidity and SmartPy (Tezos)

Consultant for clients on issues related to Blockchain and smart contracts

R&D in cross-chain bridges and new innovations in the field of blockchain (e.g. account abstraction with EIP-7702 and ERC-4337)

Development of the CMTAT security token framework and its security process: audits for major releases, static analysis and AI audit tools for minor releases

Integrations of CMTAT with partners: Chainlink ACE (on-chain compliance), Chainlink CCIP and LayerZero (cross-chain), and FIX messages on-chain with Nethermind

Privacy for security tokens: CMTAT-Confidential with Zama FHE (confidential balances), alongside the Aztec version of CMTAT

Several publications on the Taurus blog on Tokenization and cross-chain bridge ([Chainlink CCIP](https://chain.link/cross-chain))

Conference speaking on CMTAT and security: EthCC 2026, BSA - EPFL Stablecoins & Payments Conference 2026, CMTA x OpenZeppelin 2026 and Black Alps 2024 (see [Talks](/talks/))

- Public projects for CMTA (CMTAT ecosystem)

[CMTAT](https://github.com/CMTA/CMTAT): ERC-20 for on-chain financial instruments

[CMTAT-Confidential](https://github.com/CMTA/CMTAT-Confidential): Confidential version of CMTAT with private balances, built with Zama FHEVM

[CMTAT-ACE](https://github.com/CMTA/CMTAT-ACE): Integration of CMTAT with Chainlink ACE for policy-driven on-chain compliance

[CMTAT-FIX](https://github.com/CMTA/CMTAT-FIX): Integration of on-chain FIX (Financial Information eXchange) data in CMTAT, with Nethermind

[CMTAT-LayerZero](https://github.com/CMTA/CMTAT-LayerZero): Example of how CMTAT can be bridged with LayerZero

[CMTAT-CCIP](https://github.com/rya-sge/CMTAT-CCIP): Example of how CMTAT can be bridged with Chainlink CCIP

[IncomeVault](https://github.com/CMTA/IncomeVault): Solidity contracts to perform coupon payment on-chain

- Public projects for Taurus

[Smart Wallet 7702](https://github.com/taurushq-io/smart-wallet-7702): Smart wallet for EOAs with EIP-7702 delegation and ERC-4337 support

[TERC-20](https://github.com/taurushq-io/TERC-20): Minimal ERC-20 with mint and burn (simple and batch version), deployment available in standalone or through a proxy (upgradeable)

[TERC-721](https://github.com/taurushq-io/TERC-721/): Minimal ERC-721 tokens with mint and burn (simple and batch version), deployment available in standalone or through a proxy (upgradeable). Issuer can decide to use the token internal counter as token id or submit it during minting.

[TERC-1155A](https://github.com/taurushq-io/TERC1155A): ERC-1155 implementation for NFT

[Chainlink CCIP Sender](https://github.com/taurushq-io/tg-bridge-contracts-CCIP): Sender contract to interact with CCIP bridge (Proof of concept)

### Penetration Tester [10/2021 - 02/2022]

- Company: Confidential
- Position: Penetration Tester (external consultant / internship)
- Summary: Security audit in a software company carried out as part of a course at HEIG-VD, about 200 hours performed

Education
======
* ### Bachelor of Science

  - Degree: Bachelor of Science - BS, Information security
  - Uni: [HEIG-VD](https://heig-vd.ch)
  - Year: 2018 &mdash; 2022
  - Association: Co-Founder and Member of the [Y-CTF](https://yctf.ch) Committee (CTF Club of HEIG-VD)
  - Summary: The IS orientation trains engineers with advanced skills in security to give them a global "attack-defense" vision of computer systems. These specialists analyze the security of complex computer systems (threat analysis and intrusion tests), design secure architectures, select and develop the appropriate protection measures.
  - Project

  [Password manager](https://github.com/rya-sge/password-manager): Rust-based application to store passwords securely.

  [D-flip flop](https://github.com/AMT-D-Flip-Flop/Authentication) (group project): Authentication microservice with Spring Boot Java

  [Static site generator](https://github.com/rya-sge/generateur-site-statique-pellissier_ruckstuhl_sauge_viotti) (group project): developed in Java

  [PHP angular project](https://github.com/rya-sge/PRO-Angular-Php) (group project): Development of a web application with Angular (front-end) and PHP (backend).

Skills
======
* Smart contract development
  * Solidity (EVM): Foundry, Hardhat, Truffle
  * SmartPy (Tezos)
  * Move (Sui)
  * Solana
* Tokenization and standards
  * Security tokens (CMTAT), ERC-20, ERC-721, ERC-1155
  * Account abstraction: ERC-4337, EIP-7702
* Cross-chain and integrations
  * Chainlink CCIP, Chainlink ACE, LayerZero
* Privacy
  * Fully Homomorphic Encryption (Zama FHEVM)
  * Zero-knowledge identity (Self Protocol)
* Security
  * Smart contract security analysis
  * Penetration testing
  * Applied cryptography
  * CTF (co-founder of Y-CTF)
* Other languages
  * Rust, Java, C++, Kotlin

Publications
======
See [Publications](/publications/) for my articles on the Taurus blog and on my blog Access Denied.

Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
