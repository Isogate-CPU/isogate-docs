# Contract references

The following are public reference points for the active Genesis v2 route. They
are documentation references, not deployment instructions or endorsements.
Verify addresses, network configuration, source matches, and transaction state
independently before signing or integrating.

## Robinhood Chain mainnet

| Field | Value |
|---|---|
| Network | Robinhood Chain mainnet |
| Chain ID | `4663` |
| RPC | [rpc.mainnet.chain.robinhood.com](https://rpc.mainnet.chain.robinhood.com/) |
| Explorer | [Robinhood Chain Blockscout](https://robinhoodchain.blockscout.com) |

## Genesis v2 infrastructure

| Component | Address | Explorer |
|---|---|---|
| Identity Registry v2 | `0xB946ad99b17d741ABFCBCAec85F5a896a02C62fC` | [View](https://robinhoodchain.blockscout.com/address/0xB946ad99b17d741ABFCBCAec85F5a896a02C62fC) |
| Genesis Factory v2 | `0x100D6f949c1C6751799EB510765Bcd7a3e65834A` | [View](https://robinhoodchain.blockscout.com/address/0x100D6f949c1C6751799EB510765Bcd7a3e65834A) |
| Launch Coordinator v2 | `0xf3c2CAe988356112a9584389DDb6bc7bf3258c52` | [View](https://robinhoodchain.blockscout.com/address/0xf3c2CAe988356112a9584389DDb6bc7bf3258c52) |

## External infrastructure dependencies

| Dependency | Address |
|---|---|
| Uniswap v4 PoolManager | `0x8366a39CC670B4001A1121B8F6A443A643e40951` |
| Uniswap v4 PositionManager | `0x58daec3116aae6D93017bAAea7749052E8a04fA7` |
| Permit2 | `0x000000000022D473030F116dDEE9F6B43aC78BA3` |
| WETH | `0x0Bd7D308f8E1639FAb988df18A8011f41EAcAD73` |

These are infrastructure addresses and are not an ISOC token address. Earlier
v1 records remain historical data; new Genesis launches use the v2 components.
For responsibilities, source verification, reconciliation, and limitations,
read sections 13–16 of the [canonical documentation](Isogate-Complete-Documentation.md).