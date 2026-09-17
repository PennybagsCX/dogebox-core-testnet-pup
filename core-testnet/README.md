# Dogecoin Core (testnet) pup

Fork of the stock [Dogebox-WG core pup](https://github.com/Dogebox-WG/pups/tree/main/core) that runs
**Dogecoin Core v1.14.9 on the public testnet3 network** (`-testnet=1`), with a memory-capped
`-dbcache=800`. No txindex, wallet disabled (both stock behavior) — keeps RSS well inside a
16 GB box that already runs a mainnet txindex node.

Same layout as stock: RPC on pup-internal `:22555` (static bootstrap creds, overwritten to
`/storage/rpcuser.txt` / `rpcpassword.txt` on first boot), P2P `:22556` (host-listened), ZMQ `:28332`.

## Release rule

dogeboxd reads the version from `manifest.json` **inside the tag** — bump the manifest, commit,
then tag.
