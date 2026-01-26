---
title: Template - [Executive Vote] November and December Monthly Settlement Cycles and Treasury Management Function, Pattern Onboarding, Skybase Onboarding and Genesis Capital Funding, DAO Resolution for 6s Capital, Prime Agent Proxy Spells - January 29, 2026
summary: Execute Monthly Settlement Cycle and Treasury Management Function for November and December, onboard Pattern with ALLOCATOR-PATTERN-A and StarGuard instance, onboard Skybase with StarGaurd instance, approve DAO Resolution for RWA001-A, whitelist proxy spells for Spark and Grove.
date: 2026-01-26T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] November and December Monthly Settlement Cycles and Treasury Management Function, Pattern Onboarding, Skybase Onboarding and Genesis Capital Funding, DAO Resolution for 6s Capital, Prime Agent Proxy Spells - January 29, 2026

The The Core Facilitators, Sidestream, and Dewiz have placed an executive proposal into the voting system. SKY holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- The Monthly Settlement Cycle and Treasury Management Function for November and December 2025 will be executed.
- The Pattern SubProxy and StarGuard will be initialized.
- Skybase StarGuard will be initialized.
- Skybase Genesis Capital Allocation will be distributed.
- A DAO Resolution relating to 6s Capital (RWA001-A) will be approved.
- Star Agent proxy spells for Spark and Grove will be whitelisted in the respective StarGuard modules.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.io/#A.1.9.3.1). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**24 hours**](https://sky-atlas.io/#A.1.9.3.1.2).

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**.

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### Monthly Settlement Cycle and Treasury Management Function for November and December

- **Authorization**: [A.2.4 - Sky Core Monthly Settlement Cycle](https://sky-atlas.io/#A.2.4), [A.2.3 - Treasury Management](https://sky-atlas.io/#A.2.3)
- **Proposal**: [Forum Post](https://forum.sky.money/t/msc-4-settlement-summary-november-and-december-2025-spark-grove/27617/5)

If this executive proposal passes, then If this executive proposal passes, then the November and December 2025 Monthly Settlement Cycles will be executed by taking the following steps.

#### Spark

- Mint **25,547,255 USDS** debt in ALLOCATOR-SPARK-A and transfer the amount to the Surplus Buffer.
- Transfer **7,071,339 USDS** from the surplus buffer to the SPARK_SUBPROXY located at [0x3300f198988e4C9C63F75dF86De36421f06af8c4](https://etherscan.io/address/0x3300f198988e4C9C63F75dF86De36421f06af8c4).

#### Grove

- Mint **14,311,822 USDS** debt in ALLOCATOR-BLOOM-A and transfer the amount to the Surplus Buffer.

#### Obex

- Mint **1,768,819 USDS** debt in ALLOCATOR-OBEX-A and transfer the amount to the Surplus Buffer.
- Transfer **442,327 USDS** from the Surplus Buffer to the OBEX_SUBPROXY located at [0x8be042581f581E3620e29F213EA8b94afA1C8071](https://etherscan.io/address/0x8be042581f581e3620e29f213ea8b94afa1c8071).

#### Treasury Management Function

- Transfer **6,632,421 USDS** from the Surplus Buffer to the Core Council Buffer located at [0x210CFcF53d1f9648C1c4dcaEE677f0Cb06914364](https://etherscan.io/address/0x210CFcF53d1f9648C1c4dcaEE677f0Cb06914364).
- Transfer **331,620 USDS** from the Surplus Buffer to the Aligned Delegates Buffer located at [0x37FC5d447c8c54326C62b697f674c93eaD2A93A3](https://etherscan.io/address/0x37FC5d447c8c54326C62b697f674c93eaD2A93A3).

### Pattern Onboarding

- **Authorization**: [$TBD]($TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/technical-scope-of-the-new-pattern-allocator-instance/27641)

If this executive proposal passes, then Pattern will be onboarded as a Prime. The onboarding will consist of adding the allocator instance, setting the SP-BEAM for the new allocator vault, and creating a Pattern StarGuard instance for future proxy spells.

#### Add Allocator Instance

Init new Allocator instance by calling [AllocatorInit.initIlk](https://github.com/sky-ecosystem/dss-allocator/blob/226584d3b179d98025497815adb4ea585ea0102d/deploy/AllocatorInit.sol#L97-L164) with:

- sharedInstance.oracle: PIP_ALLOCATOR from chainlog
- sharedInstance.roles: ALLOCATOR_ROLES from chainlog
- sharedInstance: ALLOCATOR_REGISTRY from chainlog
- ilkInstance.owner: MCD_PAUSE_PROXY from chainlog
- ilkInstance.vault: 0xbd34fc6AAa1d3F52B314CB9D78023dd23eAc3B0E
- ilkInstance.buffer: 0x823459b55D79F0421f24a4828237F7ecb8D7F1ef
- cfg.ilk: ALLOCATOR-PATTERN-A
- cfg.duty: 0
- cfg.gap: 10 million USDS
- cfg.maxLine: 10 million USDS
- cfg.ttl: 86,400 seconds
- cfg.AllocatorProxy: 0xbC8959Ae2d4E9B385Fe620BEF48C2FD7f4A84736
- cfg.ilkRegistry: ILK_REGISTRY from chainlog

The initialization script will create a PIP_ALLOCATOR_PATTERN_A entry in the Chainlog; this entry is not necessary and will be removed.

ALLOCATOR-PATTERN-A will be added to the Debt Ceiling Breaker (LINE_MOM).

#### Add New Pattern Allocator to the SP-BEAM

ALLOCATOR-PATTERN-A ilk will be added to the SP-BEAM with the following parameters:

- max: 3,000 bps
- min: 0 bps
- step: 400 bps

#### Add Pattern StarGaurd instance

Init new StarGuard module by calling [StarGuardInit.init](https://github.com/sidestream-tech/sky-star-guard/blob/7398ffb283c4490c6e29bea28b92cd57285d4889/deploy/StarGuardInit.sol#L44-L63) with:

- chainlog: DssExecLib.LOG
- cfg.subProxy: [0xbC8959Ae2d4E9B385Fe620BEF48C2FD7f4A84736](https://etherscan.io/address/0xbC8959Ae2d4E9B385Fe620BEF48C2FD7f4A84736)
- cfg.subProxyKey: PATTERN_SUBPROXY
- cfg.starGuard: [0x2fb18b28fB39Ec3b26C3B5AF5222e2ca3B8B2269](https://etherscan.io/address/0x2fb18b28fB39Ec3b26C3B5AF5222e2ca3B8B2269)
- cfg.starGuardKey: PATTERN_STARGUARD
- cfg.maxDelay: 7 days

PATTERN_STARGUARD module will then be added to the [StarGuardJob](https://etherscan.io/address/0xb18d211fa69422a9a848b790c5b4a3957f7aa44e).

### Skybase Onboarding and Genesis Capital Funding

- **Authorization**: [$TBD]($TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/technical-scope-of-the-new-skybase-agent/27642)

If this executive proposal passes, then the Skybase Prime will be onboarded to their own StarGaurd instance and recieve Genesis Capital Funding, as described below.

#### Add Skybase StarGaurd instance

Initialize new StarGuard module by calling StarGuardInit.init with:

- chainlog: DssExecLib.LOG
- cfg.subProxy: [0x08978E3700859E476201c1D7438B3427e3C81140](https://etherscan.io/address/0x08978E3700859E476201c1D7438B3427e3C81140)
- cfg.subProxyKey: SKYBASE_SUBPROXY
- cfg.StarGuard: [0xA170086AeF9b3b81dD73897A0dF56B55e4C2a1F7](https://etherscan.io/address/0xA170086AeF9b3b81dD73897A0dF56B55e4C2a1F7)
- cfg.starGuardKey: SKYBASE_STARGUARD
- cfg.maxDelay: 7 days

SKYBASE_STARGUARD module will then be added to the [StarGuardJob](https://etherscan.io/address/0xb18d211fa69422a9a848b790c5b4a3957f7aa44e).

#### Skybase Genesis Funding

The following transfers will be made as part of Skybase's Gensis funding:

- Transfer **10 million USDS** to SKYBASE_SUBPROXY located at [0x08978E3700859E476201c1D7438B3427e3C81140](https://etherscan.io/address/0x08978E3700859E476201c1D7438B3427e3C81140).
- Transfer **5 million USDS** to the USDS Demand Subsidies Multisig at [0x3F32bC09d41eE699844F8296e806417D6bf61Bba](https://etherscan.io/address/0x3F32bC09d41eE699844F8296e806417D6bf61Bba).

### DAO Resolution for 6s Capital (RWA001-A)

- **Authorization**: [Core Facilitator Approval](https://forum.sky.money/t/rwa-001-6s-capital-update-and-stability-fee-proposal/24624/5)
- **Proposal**: [Forum Post](https://forum.sky.money/t/rwa-001-6s-capital-update-and-stability-fee-proposal/24624/4)

If this executive proposal passes, then a DAO Resolution with IPFS hash [bafkreiczdjq55zsxvxcf4le3oaqvhp4jgvls4n4b7xbnzvkwilzen3a2te](https://gateway.pinata.cloud/ipfs/bafkreiczdjq55zsxvxcf4le3oaqvhp4jgvls4n4b7xbnzvkwilzen3a2te) will be approved. This DAO Resolution authorizes the return of the full balance of funds held in the Trust.

## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
