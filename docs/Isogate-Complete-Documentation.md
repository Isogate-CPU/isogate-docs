# Isogate — Complete Product and Contract Documentation

> Official technical documentation for Isogate's inspectable virtual CPU, Native Node provider workflow, canonical verification, Genesis v2 launch system, Robinhood Chain contracts, security boundaries, use cases, and developer resources.

**Document status:** Technical beta  
**Last updated:** 14 September 2026  
**Network:** Robinhood Chain mainnet  
**Chain ID:** `4663`  
**Official website:** [https://isogate.tech](https://isogate.tech)

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [What Is Isogate?](#2-what-is-isogate)
3. [Product Architecture](#3-product-architecture)
4. [Inspectable Virtual CPU](#4-inspectable-virtual-cpu)
5. [CPU Console](#5-cpu-console)
6. [Native Node](#6-native-node)
7. [Provider Job and Verification Flow](#7-provider-job-and-verification-flow)
8. [Network Explorer and Verification Receipts](#8-network-explorer-and-verification-receipts)
9. [Isogate Genesis](#9-isogate-genesis)
10. [Genesis Token Design](#10-genesis-token-design)
11. [Uniswap v4 Liquidity and FeeVault](#11-uniswap-v4-liquidity-and-feevault)
12. [Creator Dashboard and Public Launches](#12-creator-dashboard-and-public-launches)
13. [Robinhood Chain Mainnet Contracts](#13-robinhood-chain-mainnet-contracts)
14. [Contract Responsibilities](#14-contract-responsibilities)
15. [Source Verification and Finality](#15-source-verification-and-finality)
16. [Security and Trust Boundaries](#16-security-and-trust-boundaries)
17. [Use Cases](#17-use-cases)
18. [Current Product Status](#18-current-product-status)
19. [Installation and Getting Started](#19-installation-and-getting-started)
20. [Troubleshooting](#20-troubleshooting)
21. [Frequently Asked Questions](#21-frequently-asked-questions)
22. [Official Links](#22-official-links)

---

## 1. Executive Summary

Isogate is an inspectable deterministic computing ecosystem. It combines a browser-based virtual CPU, real bounded workloads executed by Native Nodes, canonical server recomputation, browser replay comparison, public verification records, and CPU-generated Genesis assets on Robinhood Chain.

The core principle is straightforward:

> When the input, engine version, and execution rules are identical, the resulting state should also be identical.

This enables results to be replayed, compared, independently recomputed, rejected when they do not match, and used as a deterministic source for on-chain applications.

Isogate is not only a CPU simulator, distributed-compute dashboard, AI interface, or token launchpad. It is an integrated execution and verification system in which each layer has a defined role:

- The **browser CPU** makes deterministic execution understandable.
- **Native Node** performs supported workloads on provider hardware.
- The **server** independently recomputes the canonical result.
- The **browser worker** provides an additional replay comparison.
- **Public records** expose providers, jobs, receipts, and Genesis launches.
- **Genesis v2** turns approved canonical CPU output into an on-chain identity.
- **Robinhood Chain** records creator-signed approvals, deployments, launches, and contract state.

---

## 2. What Is Isogate?

Isogate is a live technical beta focused on visible, reproducible, and inspectable deterministic computation.

### Available product surfaces

| Surface | Status | Purpose |
|---|---|---|
| Browser Virtual CPU | Live beta | Demonstrates instructions, registers, RAM, flags, NAND logic, cycles, and local checkpoints. |
| CPU Console | Live beta | Registers providers, binds wallets, queues supported jobs, and compares replay results. |
| Native Node | Live beta | Diagnoses provider hardware, sends heartbeats, claims bounded jobs, executes them locally, and submits results. |
| Provider App | Live beta | Supports provider onboarding and operational status. |
| Network Explorer | Live beta | Displays public providers, jobs, network activity, and verification records. |
| Verification Receipts | Live beta | Exposes accepted deterministic replay records. |
| Agent Integration | Live beta | Supports bounded job submission, policy, events, wallet binding, and credential lifecycle. It is one product surface, not the definition of the entire ecosystem. |
| Isogate Genesis v2 | Live on-chain beta | Generates deterministic identities and launches constrained assets on Robinhood Chain. |
| Creator Dashboard | Live beta | Displays creator launches, contract bindings, verification state, and FeeVault claims. |
| Public Genesis Launches | Live beta | Provides public launch identity, contract, transaction, liquidity, and source-verification records. |
| Integration Hub | Live beta | Organizes currently available integration entry points. |

### Planned expansion

The following should not be described as available today:

- Permissionless arbitrary-workload execution
- A general-purpose compute marketplace
- An independent decentralized verifier network
- Token staking and slashing
- Open provider reward settlement
- Production Machine Visualizer
- Production Token and Settlement application
- Production Earn application
- Completed public MCP server and general developer SDK

---

## 3. Product Architecture

### 3.1 Frontend application

The React web application provides the public website and operational interfaces. It includes the CPU demonstration, CPU Console, provider flows, Network Explorer, verification receipts, Genesis, Creator Dashboard, public launch records, documentation, product status, repository links, security information, privacy, terms, and legal boundaries.

### 3.2 API service

The API manages:

- Health checks
- Deterministic replay requests
- Provider registration
- Wallet ownership challenges and binding
- Provider credential rotation and revocation
- Heartbeats and online status
- Job queueing, claiming, and completion
- Canonical result recomputation
- Network summaries and verification records
- Genesis identity generation and state
- Creator approval data
- Deployment evidence
- Public Genesis launch reconciliation

### 3.3 Shared deterministic runtime

Browser, API, scripts, and Native Node use the same bounded replay model. This reduces ambiguity between the provider result and the canonical server result.

The comparison includes the engine, input, cycle count, structured result, and digest. JSON objects are compared structurally; object-key ordering is not treated as a meaningful execution difference.

### 3.4 Blockchain layer

Robinhood Chain records Genesis approvals, deployed contracts, creator-signed transactions, launch events, ownership state, liquidity bindings, and FeeVault accounting.

On-chain records and off-chain deterministic verification are separate layers:

- Off-chain recomputation determines whether a supported CPU result is canonical.
- Creator signatures authorize the relevant launch actions.
- Smart contracts enforce Genesis deployment, token, liquidity, and fee rules.
- Public reconciliation confirms that receipts, events, and contract state agree.

---

## 4. Inspectable Virtual CPU

The virtual CPU on the Isogate landing page is a browser simulation designed to make deterministic execution visible.

### Visible machine state

- Current instruction
- Program counter
- Cycle counter
- Registers
- RAM values
- Machine flags
- NAND-gate activity
- Trace progression
- Local checkpoint state
- Simulated local verification result

### Controls

Users can:

- Start execution
- Pause execution
- Advance one cycle
- Reset the simulation
- Adjust the demonstration clock
- Observe state transitions
- Follow the gate-level visualization

### Important boundary

The landing-page CPU is an educational and product-model simulation. It is not proof that a physical provider CPU executed a wallet-bound job. Real provider execution occurs through the separate Native Node and CPU Console workflow.

---

## 5. CPU Console

CPU Console is the main operational interface for provider registration and supported Native Node jobs.

### Standard workflow

1. Install Isogate Native Node.
2. Run `isogate-node diagnose --json`.
3. Import the generated diagnostic JSON into CPU Console.
4. Register the provider.
5. Copy the provider ID and one-time provider credential.
6. Connect a wallet on Robinhood Chain.
7. Sign the gasless wallet-binding challenge.
8. Start Native Node using the provider ID.
9. Enter the private credential through the hidden prompt or environment variable.
10. Queue a supported deterministic job in CPU Console.
11. Keep Native Node online while it claims and completes the job.
12. Inspect canonical server verification and browser replay agreement.

### Wallet role

Wallet binding associates a provider with a blockchain identity. It does not prove that the provider returned a correct computation. The result must still match canonical server recomputation.

### Credential role

The one-time provider credential authenticates heartbeats, job claims, and completions. It is separate from wallet ownership.

---

## 6. Native Node

**Package:** `@isogate/node`  
**Current documented version:** `0.3.1`  
**Runtime requirement:** Node.js 20 or newer  
**License:** MIT  
**npm:** [https://www.npmjs.com/package/@isogate/node](https://www.npmjs.com/package/@isogate/node)

Native Node is cross-platform provider software for Windows, macOS, and Linux.

### Supported architecture families

- x86-64 and x86, including Intel, AMD, VIA, and Zhaoxin
- ARM64 and ARM32, including Apple Silicon, Qualcomm Snapdragon, Ampere, Broadcom, and generic ARM
- RISC-V 64
- IBM Z
- PowerPC 64
- MIPS and MIPS little-endian when supported by Node.js
- LoongArch 64 when supported by Node.js

### Diagnostic output

The diagnostic report includes:

- CPU model
- Classified CPU vendor
- Architecture
- Logical processor count
- Reported processor speed
- Memory information
- Real SHA-256 benchmark output
- Canonical report digest

Exported diagnostic JSON does not include hostname or uptime.

### Execution safety

Native Node:

- Claims only built-in bounded Isogate jobs.
- Does not execute arbitrary remote code.
- Does not upload local files.
- Does not upload hostnames.
- Does not upload environment-variable contents.
- Does not include credentials in public records or job inputs.

### Credential lifecycle

Registration returns a cryptographically random one-time credential. The server stores only its SHA-256 hash. Native Node keeps the credential in process memory and does not intentionally write or log it.

The credential must be supplied again after a process restart. If it is lost, register again or follow the supported credential-rotation flow.

---

## 7. Provider Job and Verification Flow

1. **Detect:** Native Node reads supported operating-system CPU data and runs the fixed SHA-256 benchmark.
2. **Register:** CPU Console and the API validate the diagnostic report and digest.
3. **Bind:** The provider signs a wallet challenge for Robinhood Chain.
4. **Start:** Native Node authenticates with its provider ID and private credential.
5. **Heartbeat:** The node periodically reports availability.
6. **Queue:** CPU Console creates a bounded deterministic job.
7. **Claim:** An eligible online provider claims the job.
8. **Execute:** Native Node runs the supported workload locally.
9. **Submit:** The complete replay result is returned to the API.
10. **Recompute:** The server independently derives the expected canonical result.
11. **Compare:** Engine version, input, cycles, structured output, and digest must match.
12. **Accept or reject:** Matching results are accepted; mismatches fail explicitly.
13. **Replay:** CPU Console can compare the accepted result with an independent browser worker replay.
14. **Inspect:** Network and receipt pages expose the accepted record.

The server does not treat the provider's claim, wallet signature, or submitted digest as sufficient proof by itself.

---

## 8. Network Explorer and Verification Receipts

### Network Explorer

The Network Explorer provides public visibility into:

- Network summary
- Registered providers
- Online and offline status
- Queued and completed jobs
- Verification activity
- Job details

### Verification receipts

Verification receipt pages expose accepted replay data so users can inspect the recorded provider, job, engine, input, result, and digest where available.

These receipts document canonical server acceptance. They are not zero-knowledge proofs, hardware attestations, or independent decentralized-verifier certificates.

---

## 9. Isogate Genesis

Genesis is the first live on-chain application of the Isogate deterministic execution model.

Most launch systems allow a creator to manually choose a name, symbol, description, and artwork. Isogate Genesis instead derives the approved identity from canonical Native Node output.

### Deterministic identity fields

A Genesis identity can include:

- Token name
- Token symbol
- Description
- Visual output
- Logo or image data
- Image digest
- Metadata digest
- Canonical identity digest

The creator initiates the process and explicitly approves the launch, but cannot replace the approved canonical identity with unrelated manually selected content.

### Genesis v2 launch lifecycle

1. A supported Native Node flow produces deterministic output.
2. The server recomputes and validates the canonical result.
3. Metadata and image content are bound to cryptographic digests.
4. A versioned verifier attestation is produced for the creator and identity.
5. The creator submits Registry approval from the connected wallet.
6. The creator deploys the token and per-launch infrastructure through Factory.
7. The creator supplies the required native amount and executes the launch through Coordinator.
8. Reconciliation verifies canonical receipts, events, runtime bytecode, token state, FeeVault, hook, pool, liquidity, and position lock.
9. Token and hook source bundles are submitted for public verification.
10. The launch workflow waits for exact source matches before reporting completion.
11. The finalized launch can be indexed on the public launch pages.

No token exists merely because an off-chain identity was generated. On-chain existence begins only after the creator signs and confirms the required transactions.

---

## 10. Genesis Token Design

Every Genesis token follows constrained rules:

- 1,000,000,000 tokens are minted once in the constructor.
- 1,000,000 tokens are sent to the canonical dead address.
- Final total supply is 999,000,000 tokens.
- No additional mint function exists.
- No creator token allocation is provided.
- No hidden developer buy is built into the launch flow.
- No mutable transfer tax exists.
- No blacklist function exists.
- No upgradeable token proxy is used.
- Temporary constructor ownership is renounced to the zero address.
- Creator and zero-address balances are checked during launch reconciliation.
- Residual post-liquidity token dust is sent to the dead address.

These constraints make the token design easier to inspect. They do not guarantee price, demand, trading activity, liquidity depth, profitability, or complete financial safety.

---

## 11. Uniswap v4 Liquidity and FeeVault

Genesis uses Uniswap v4 infrastructure on Robinhood Chain.

### Liquidity design

- One asymmetric liquidity position is created for each launch.
- The position is held through the launch-specific lock infrastructure.
- The creator does not receive control of the locked position.
- Excess native value supplied to Coordinator is refunded.
- The launch uses an immutable token/native ratio defined by the Coordinator.

The fixed token/native ratio is not a guaranteed USD valuation. A USD market capitalization requires a recognized executable market price and real trading data.

### Fees

- Pool swap fee: **1%**
- Creator allocation through FeeVault: **70%**
- Protocol allocation through FeeVault: **30%**

FeeVault can account for native currency, WETH, and the Genesis token. Exact-balance checks reject unsupported fee-on-transfer behavior.

Creators receive no initial token allocation. Their designed revenue path is the creator share of accrued fees.

---

## 12. Creator Dashboard and Public Launches

### Creator Dashboard

The Creator Dashboard can display:

- Generated Genesis identities
- Launch stage and recovery state
- Token address
- FeeVault address
- Hook address
- Pool and position-lock information
- Deployment and launch transactions
- Source-verification status
- Creator fee balances
- Creator claim actions

Before requesting a fee-claim transaction, the frontend rechecks Factory and FeeVault bindings and simulates the claim.

Historical v1 Factory support remains in the Creator Dashboard so eligible older launches can still be inspected and claimed. It is not the active route for new Genesis launches.

### Public Genesis launches

Public launch records can expose:

- Generated identity
- Creator wallet
- Genesis version
- Token address
- FeeVault address
- Hook address
- Position-lock address
- Pool identifier
- Position token ID
- Canonical identity digest
- Deployment transaction
- Launch transaction
- Supply and ownership state
- Source-verification and scanner-indexing state

Local browser session data is only a recovery hint. Canonical Registry, Factory, Coordinator, receipt, event, and contract state determine whether an interrupted launch can resume.

---

## 13. Robinhood Chain Mainnet Contracts

**Active Genesis version:** v2  
**Network:** Robinhood Chain mainnet  
**Chain ID:** `4663`  
**Explorer:** [https://robinhoodchain.blockscout.com](https://robinhoodchain.blockscout.com)

### Active Genesis v2 infrastructure

| Component | Address | Explorer |
|---|---|---|
| Identity Registry v2 | `0xB946ad99b17d741ABFCBCAec85F5a896a02C62fC` | [Open](https://robinhoodchain.blockscout.com/address/0xB946ad99b17d741ABFCBCAec85F5a896a02C62fC) |
| Genesis Factory v2 | `0x100D6f949c1C6751799EB510765Bcd7a3e65834A` | [Open](https://robinhoodchain.blockscout.com/address/0x100D6f949c1C6751799EB510765Bcd7a3e65834A) |
| Launch Coordinator v2 | `0xf3c2CAe988356112a9584389DDb6bc7bf3258c52` | [Open](https://robinhoodchain.blockscout.com/address/0xf3c2CAe988356112a9584389DDb6bc7bf3258c52) |

### External dependencies

| Dependency | Address |
|---|---|
| Uniswap v4 PoolManager | `0x8366a39CC670B4001A1121B8F6A443A643e40951` |
| Uniswap v4 PositionManager | `0x58daec3116aae6D93017bAAea7749052E8a04fA7` |
| Permit2 | `0x000000000022D473030F116dDEE9F6B43aC78BA3` |
| WETH | `0x0Bd7D308f8E1639FAb988df18A8011f41EAcAD73` |

These are infrastructure addresses. They are not an ISOC token address and should not be presented as one.

Earlier v1 deployment records remain historical data. New Genesis launches use the v2 Registry, Factory, and Coordinator listed above.

---

## 14. Contract Responsibilities

### Identity Registry v2

The Registry checks:

- Versioned verifier signature
- Creator address binding
- Identity digest
- Metadata and image bindings
- Attestation expiry
- Replay protection

The verifier key is a bootstrap trust boundary because it determines which identities can be approved.

### Genesis Factory v2

Factory consumes an approved identity and deploys the token plus per-launch infrastructure. It records the relationships between the identity, token, FeeVault, hook, and position lock.

The protocol account selects and configures the Coordinator under dependency and parameter checks. This is an explicit bootstrap operational trust boundary.

### Genesis Token

The token contract:

- Mints once
- Performs the canonical burn
- Transfers the liquidity allocation according to the launch design
- Renounces temporary ownership
- Exposes no privileged mint, blacklist, mutable-tax, or upgrade function

### Launch Coordinator v2

Coordinator:

- Confirms approved identity and deployment bindings
- Checks expected final supply and balances
- Calculates required native liquidity from the immutable ratio
- Initializes the Uniswap v4 pool
- Creates the liquidity position
- Locks the resulting position
- Burns residual token dust
- Refunds excess native value
- Records canonical hook, pool, lock, token ID, and liquidity bindings

### FeeVault

FeeVault:

- Records the creator, protocol, and Genesis token
- Accepts supported native, WETH, and token fee deposits
- Applies the 70% creator and 30% protocol accounting split
- Uses pull-based claims
- Performs exact-balance checks

### Hook and position lock

The hook is deployed per launch and bound to the relevant pool design. The position lock holds the liquidity position so the creator cannot withdraw it through the normal launch path.

---

## 15. Source Verification and Finality

### Genesis v2 infrastructure verification

The v2 deployment manifest records Sourcify exact creation and runtime matches:

| Contract | Sourcify match ID | Creation | Runtime |
|---|---:|---|---|
| Identity Registry v2 | `50624344` | Exact match | Exact match |
| Genesis Factory v2 | `50624364` | Exact match | Exact match |
| Launch Coordinator v2 | `50624399` | Exact match | Exact match |

### Per-launch verification

For every new Genesis v2 launch, the launch workflow:

1. Builds transaction-bound Solidity standard JSON verification inputs.
2. Confirms the expected deployment and launch transactions.
3. Validates token and hook runtime bytecode against compiled artifacts.
4. Submits source material for both the token and hook.
5. Polls until both return public exact matches.
6. Fails closed if the verification requirement is not met.
7. Continues final reconciliation only after the verification gate succeeds.

### Scanner indexing

Sourcify exact matching and third-party scanner display are related but separate states. Block explorers and market scanners can import or refresh records on different schedules.

A delayed scanner badge does not invalidate an existing Sourcify exact match, but the public interface should distinguish verified source from pending scanner indexing.

### Finality and reconciliation

A launch is not accepted from a frontend transaction response alone. Reconciliation checks:

- Successful receipts
- Canonical block hashes
- Expected Factory and Coordinator events
- Registry approval
- Creator binding
- Token metadata and digest
- Final supply and canonical burn
- Creator and Factory balances
- FeeVault binding
- Hook and pool binding
- Liquidity amount
- Position token ID and lock
- Runtime bytecode
- Residual dust handling

---

## 16. Security and Trust Boundaries

### Native Node boundary

Native Node executes only supported built-in deterministic jobs. It is intentionally not a remote arbitrary-code runner.

### Verification boundary

Result acceptance currently depends on canonical server recomputation. This is not yet a permissionless independent verifier network or cryptographic proof system.

### Wallet boundary

A wallet signature proves control of the signing key for the stated message. It does not prove that a workload was executed correctly.

### Credential boundary

Provider credentials authorize provider API operations. They are not proof of wallet ownership and must remain private.

### Genesis verifier boundary

The verifier key authorizes deterministic identities for Registry approval. Compromise or misuse of the verifier is a critical bootstrap risk.

### Protocol configuration boundary

The protocol account participates in initial Genesis infrastructure configuration and protocol fee claims. Operational security remains important.

### Creator boundary

The creator controls whether and when to sign the irreversible Registry, Factory, and launch transactions and supplies the required native amount.

### Market boundary

Isogate does not guarantee:

- Token price
- USD valuation
- Trading volume
- Market-maker activity
- Third-party routing support
- Scanner indexing speed
- Profitability
- Absence of every possible smart-contract or market risk

### Audit boundary

Do not describe the contracts as independently audited unless an official audit report is published through Isogate's official channels.

---

## 17. Use Cases

### CPU education

Users can explore deterministic instruction execution, registers, memory, cycles, flags, NAND logic, and checkpoints through an interactive browser interface.

### Reproducible workloads

Supported workloads can be executed across Native Node, server, and browser environments and compared using structured results and digests.

### Provider reliability measurement

The network can record provider availability, job completion, canonical agreement, and verification history.

### Transparent automated rules

Deterministic execution is useful where a final output is insufficient and the decision path must be reproducible.

### Deterministic digital identity

Canonical CPU output can generate names, symbols, descriptions, images, metadata, and immutable identity digests.

### Constrained on-chain assets

Genesis connects approved identity output to fixed token, ownership, liquidity, fee, and source-verification rules.

### Public execution records

Providers, jobs, receipts, transactions, and launch state can be exposed through public inspection surfaces.

### Future applications

The architecture may support deterministic games, simulations, financial rules, auditable automation, additional workload classes, and broader provider participation. These are directions, not guarantees of current availability.

---

## 18. Current Product Status

### Available now

- Browser virtual CPU and NAND simulation
- CPU Console
- Native Node diagnostics
- Provider registration
- Wallet binding
- Provider credential rotation and revocation
- Native Node heartbeats and bounded job execution
- Canonical server recomputation
- Browser worker replay comparison
- Network Explorer
- Public verification receipts
- Agent integration controls for bounded jobs
- Genesis v2 identity generation
- Robinhood Chain Registry, Factory, and Coordinator
- Creator Dashboard
- Public Genesis launch records
- Locked Uniswap v4 liquidity launch path
- FeeVault creator and protocol accounting
- Transaction-bound token and hook source verification

### Not yet available as completed production systems

- Arbitrary remote workload execution
- Permissionless compute marketplace
- Independent decentralized verifier network
- Staking and slashing economy
- General provider reward settlement
- Production Machine Visualizer
- Production Token and Settlement app
- Production Earn app

---

## 19. Installation and Getting Started

### Browser-only CPU demonstration

1. Open [https://isogate.tech](https://isogate.tech).
2. Navigate to the processor simulation.
3. Select **Execute**.
4. Observe instructions, NAND activity, registers, RAM, flags, and checkpoints.
5. Pause or step the simulation to inspect state changes.

### Install Native Node

Requirements:

- Node.js 20 or newer
- Windows, macOS, or Linux
- Network access to the Isogate HTTPS API

Install globally:

```bash
npm install -g @isogate/node
```

Run a diagnostic:

```bash
isogate-node diagnose
```

Export JSON:

```bash
isogate-node diagnose --json
```

Or write the report to a file:

```bash
isogate-node diagnose --output isogate-diagnostic.json
```

### Start provider mode

After registration in CPU Console:

```bash
isogate-node start \
  --server https://isogate.tech/api \
  --provider YOUR_PROVIDER_ID
```

Supply the provider credential through the hidden prompt. For non-interactive operation, use the `ISOGATE_PROVIDER_CREDENTIAL` environment variable without printing or committing its value.

### Begin Genesis

1. Register and bind a Native Node provider.
2. Keep Native Node online.
3. Connect the intended creator wallet on Robinhood Chain.
4. Open Genesis.
5. Generate the deterministic identity.
6. Review every generated value and digest.
7. Read each transaction before signing.
8. Complete Registry approval, Factory deployment, and launch transactions.
9. Wait for finality, reconciliation, and source verification.

---

## 20. Troubleshooting

### Native Node remains offline

- Confirm the Native Node process is running.
- Confirm the provider ID matches the registered provider.
- Re-enter the current credential after a process restart.
- Confirm the server URL ends with `/api`.
- Check network access and system time.

### A queued job does not complete

- Keep Native Node online so it can send heartbeats and claim the job.
- Confirm the provider credential has not been rotated or revoked.
- Confirm the job is a supported bounded workload.
- Inspect the provider and job record in Network Explorer.

### Wallet binding fails

- Confirm the connected wallet matches the address used for the challenge.
- Confirm Robinhood Chain is selected.
- Request a fresh challenge if the previous one expired.
- Sign the exact message displayed by Isogate.

### Genesis cannot proceed

- Confirm the Native Node result is canonical.
- Confirm the creator wallet matches the attested creator.
- Confirm the identity proof has not expired unless resuming an identity already approved on-chain.
- Confirm sufficient native balance for gas and required liquidity.
- Confirm each preceding transaction is finalized before continuing.

### Source verification is pending

- Token and hook must both reach exact source matches.
- Third-party scanners may update later than Sourcify.
- Inspect public source-verification records and contract explorer pages directly.
- Do not treat a pending scanner badge as proof that source submission did not occur.

### A market scanner shows zero price or market capitalization

Contract deployment and liquidity creation do not guarantee recognized executable trading data. A scanner may display zero until it identifies a supported route, price, and sufficient market activity.

---

## 21. Frequently Asked Questions

### Is Isogate only an AI-agent product?

No. Agent integration is one application surface. The broader ecosystem covers inspectable CPU execution, Native Node providers, deterministic verification, public receipts, Genesis identity generation, smart contracts, liquidity, and launch records.

### Is the browser CPU a real Native Node job?

No. It is an inspectable browser simulation. Real provider jobs use Native Node and CPU Console.

### Does Native Node execute arbitrary code?

No. It executes only built-in bounded deterministic workloads supported by the current runtime.

### Does Isogate upload my files or hostname?

Native Node does not intentionally upload local files, environment-variable contents, or hostname. Exported diagnostic JSON excludes hostname and uptime.

### What proves a provider result is correct?

The server independently recomputes the supported workload and compares the complete canonical result. This is canonical recomputation, not an independent decentralized proof network.

### Is wallet binding the verification proof?

No. Wallet binding identifies the provider. Computation acceptance still depends on result agreement.

### Is Isogate decentralized today?

The current provider and verification system is a technical beta with centralized canonical server recomputation. A permissionless independent verifier network is not yet live.

### What makes Genesis different?

The token identity originates from canonical Native Node output instead of manual creator selection. The creator initiates and approves the launch, while deterministic execution determines the identity.

### Can the creator mint more tokens?

No. The Genesis token has no additional mint function after constructor minting.

### What is the final token supply?

999 million tokens after the canonical one-million-token constructor burn.

### Does the creator receive tokens?

No creator token allocation is built into the Genesis launch design. Creator revenue is designed to come from the creator share of FeeVault-accounted liquidity fees.

### Can liquidity be withdrawn by the creator?

The Genesis position is assigned to the launch-specific position lock rather than the creator.

### What is the pool fee?

The static Uniswap v4 pool fee is 1%.

### How are fees split?

FeeVault accounting assigns 70% to the creator and 30% to the protocol.

### Are Genesis contracts upgradeable?

The Genesis token is not an upgradeable proxy. Refer to each infrastructure contract's verified source for its exact immutable and administrative boundaries.

### Is ownership renounced?

The token's temporary constructor ownership is renounced to the zero address. Reconciliation checks the expected ownership and balance state.

### Is source code verified?

The active v2 infrastructure records exact Sourcify matches. New Genesis launches require exact token and hook source matches before the workflow reports completion.

### Does verified source guarantee safety?

No. Verified source links deployed bytecode to source material. It does not guarantee economic safety, market value, audit quality, or freedom from every vulnerability.

### Does Genesis guarantee a specific market capitalization?

No. The immutable launch ratio does not guarantee a USD value. A real market capitalization requires recognized executable price and trading data.

### Is there an official token address for Isogate itself?

The documented Registry, Factory, and Coordinator are Genesis infrastructure contracts. They are not an ISOC token address.

### Which contract version is active?

Genesis v2 is the active route for new launches. Earlier v1 records remain available for historical compatibility.

### Is Isogate affiliated with Robinhood, Uniswap, Intel, or AMD?

No affiliation is implied. Robinhood Chain is the deployment network, Uniswap v4 is liquidity infrastructure, and processor vendors are relevant hardware context.

### Where can I verify official information?

Use the Isogate website, documentation, GitHub organization, npm package, official X account, Robinhood Chain explorer, and verified contract source records linked below.

---

## 22. Official Links

| Resource | URL |
|---|---|
| Website | [https://isogate.tech](https://isogate.tech) |
| Documentation | [https://isogate.tech/?page=docs](https://isogate.tech/?page=docs) |
| CPU Console | [https://isogate.tech/?page=console](https://isogate.tech/?page=console) |
| Product Status | [https://isogate.tech/?page=status](https://isogate.tech/?page=status) |
| Security and Trust | [https://isogate.tech/?page=security](https://isogate.tech/?page=security) |
| Repository Page | [https://isogate.tech/?page=repository](https://isogate.tech/?page=repository) |
| GitHub | [https://github.com/Isogate-CPU](https://github.com/Isogate-CPU) |
| Native Node on npm | [https://www.npmjs.com/package/@isogate/node](https://www.npmjs.com/package/@isogate/node) |
| Official X | [https://x.com/Isogate_CPU](https://x.com/Isogate_CPU) |
| Robinhood Chain Explorer | [https://robinhoodchain.blockscout.com](https://robinhoodchain.blockscout.com) |

---

## Preferred Product Description

> Isogate makes deterministic computation visible and replayable, verifies supported Native Node workloads through canonical recomputation, and turns approved CPU output into transparent on-chain Genesis assets on Robinhood Chain.

## Final Notice

Isogate is a technical beta. Always verify current product status, package versions, contract addresses, source matches, transaction details, and network conditions through official channels before relying on them or signing an irreversible transaction.

---

© 2026 Isogate. This document does not imply affiliation with Robinhood, Vlad Tenev, Uniswap Labs, Intel, AMD, or any other referenced company or protocol.
