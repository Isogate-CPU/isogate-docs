# Security and Trust Boundaries

## Execution

Native Node executes only supported built-in deterministic workloads. It does not intentionally upload local files, hostnames, environment-variable contents, or credentials.

## Verification

A wallet signature identifies a signer; it does not prove computation correctness. Provider submissions are accepted only after canonical server recomputation agrees with the submitted result.

## Credentials

Provider credentials authorize provider API operations and must remain private. Repository examples contain variable names and placeholders only, never live credentials.

## Genesis

Creators control irreversible wallet transactions. The bootstrap verifier and protocol configuration accounts remain explicit operational trust boundaries. Token and hook exact source matches are required before the launch workflow reports completion.

## Market and audit boundary

Verified source does not guarantee economic safety, market value, liquidity depth, or freedom from every vulnerability. The contracts must not be described as independently audited unless an official audit report is published.

Report vulnerabilities privately using the process in the repository root [SECURITY.md](../SECURITY.md).
