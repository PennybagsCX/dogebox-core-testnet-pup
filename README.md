# Dogecoin Core testnet3 pup for Dogebox

![version](https://img.shields.io/badge/version-0.0.1-blue) ![license](https://img.shields.io/badge/license-MIT-green) ![platform](https://img.shields.io/badge/platform-Dogebox-8A65C3)

A [Dogebox](https://github.com/Dogebox-WG) pup that runs **Dogecoin Core v1.14.9 on the public testnet3 network** — a fork of the stock [Dogebox-WG core pup](https://github.com/Dogebox-WG/pups/tree/main/core) with `-testnet=1` and a memory-capped `-dbcache=800`.

## Why this fork

The stock core pup targets mainnet. This fork flips it to testnet3 with `-dbcache=800`, keeping RSS well inside a 16 GB box that already runs a mainnet txindex node. Wallet is disabled and there is no txindex (both stock behavior) — this pup is for **testing against the public testnet3 chain**, not for development tooling. For a local dev chain with a wallet and instant blocks, use the [Dogecoin Core Regtest pup](https://github.com/PennybagsCX/dogebox-dogecoin-regtest-pup) instead.

## Using it

Same layout as the stock core pup:

- RPC on pup-internal `:22555` (static bootstrap creds, overwritten to `/storage/rpcuser.txt` / `rpcpassword.txt` on first boot)
- P2P `:22556` (host-listened)
- ZMQ `:28332`

Testnet3 DOGE has no value; get faucet coins from [faucet.doge.toys](https://faucet.doge.toys).

## Changelog

| Version | Change |
|---|---|
| 0.0.1 | Initial release: stock core pup + `-testnet=1`, `-dbcache=800` |

## Related pups

- [Dogecoin Core Regtest pup](https://github.com/PennybagsCX/dogebox-dogecoin-regtest-pup) — private wallet-enabled dev chain with auto-miner
- [Dogecoin Core txindex pup](https://github.com/PennybagsCX/dogebox-core-txindex-pup) — mainnet Core with `txindex=1` for indexers/explorers

## License

MIT for the packaging. Dogecoin Core and the upstream core pup remain the property of their respective projects and are subject to their own licenses.
