# Architecture

Isogate separates execution, verification, public inspection, and on-chain settlement into explicit layers.

## Browser layer

The web client presents the inspectable virtual CPU, CPU Console, provider controls, Network Explorer, verification receipts, Genesis, Creator Dashboard, and public launch records. The landing-page CPU is a simulation; real provider jobs use Native Node.

## Native Node layer

Native Node detects supported CPU information, runs a fixed benchmark, sends authenticated heartbeats, claims built-in bounded jobs, executes the shared deterministic runtime locally, and submits complete replay results. It does not execute arbitrary remote code.

## Verification layer

The API independently recomputes supported results and compares engine version, canonical input, cycles, structured output, and digest. Browser replay provides an additional comparison surface. Current acceptance is canonical recomputation, not permissionless consensus.

## Genesis layer

Approved deterministic CPU output becomes a versioned Genesis identity. Creator-signed Registry, Factory, and Coordinator transactions deploy the constrained token and launch-specific liquidity infrastructure on Robinhood Chain.

See the [complete reference](Isogate-Complete-Documentation.md) for detailed flows and contract addresses.
