# Version compatibility

This matrix records the versions and network identifiers documented by the
canonical reference. It is a compatibility aid, not a promise that an older
client remains supported indefinitely. Confirm current releases through the
official links before integrating.

| Surface | Documented version or requirement | Compatibility note |
|---|---|---|
| Native Node package | `@isogate/node` `0.3.1` | Requires Node.js 20 or newer; supports Windows, macOS, and Linux. |
| Deterministic replay engine | `isogate-deterministic-replay-v1` | Browser, API, scripts, and Native Node must use matching execution rules for canonical comparison. |
| Genesis launch route | v2 | Active route for new launches; v1 records remain historical compatibility data. |
| Robinhood Chain | Mainnet, chain ID `4663` | Confirm RPC and explorer availability independently. |
| Genesis identity registry | v2 | Checks verifier signature, creator binding, digests, expiry, and replay protection. |
| Genesis factory | v2 | Deploys token and per-launch infrastructure from an approved identity. |
| Launch coordinator | v2 | Coordinates pool initialization, position lock, reconciliation, and refund behavior. |
| Source verification | Transaction-bound exact matches | Token and hook source matches are required before a new launch reports completion. |

## Compatibility rules

- Do not mix a legacy v1 deployment route with v2 launch assumptions.
- Treat engine, input, cycle count, structured result, and digest as one
  compatibility unit.
- Verify contract addresses and runtime/source matches on the configured
  network, rather than relying on a copied address.
- Read the [canonical documentation](Isogate-Complete-Documentation.md) for
  product availability and planned versus live features.