# Arc Savings Vault — ERC20 + DeFi Vault + dApp on Arc Testnet

A three-part dApp built from scratch on Circle's Arc Testnet: a standard ERC20 token, a savings vault contract using the approve/transferFrom pattern, and a browser frontend wired up with ethers.js v6.

## Deployed Contracts (Arc Testnet)

| Contract | Address |
|---|---|
| **WJT (ERC20)** | [`0x4E5c24615f1648879FBDb5b90288dDE8eb5Dc484`](https://testnet.arcscan.app/address/0x4E5c24615f1648879FBDb5b90288dDE8eb5Dc484) |
| **SavingsVault** | [`0x145Ad0A4fCd8c7A2fAb6A50fe0E801Ef751e23e5`](https://testnet.arcscan.app/address/0x145Ad0A4fCd8c7A2fAb6A50fe0E801Ef751e23e5) |

## Components

- **`src/MyToken.sol`** — OpenZeppelin-based ERC20 (WJT)
- **`src/SavingsVault.sol`** — deposit/withdraw vault; pulls tokens via `transferFrom` after user `approve`
- **`web/`** — single-page dApp: wallet connect, balances, approve → deposit → withdraw flow (ethers.js v6)

## Stack

Solidity · Foundry (forge/cast) · OpenZeppelin · ethers.js v6

## Run

```shell
forge build                          # compile
forge test                           # run tests
cd web && python3 -m http.server 8000   # frontend at localhost:8000
```

## Network

Arc Testnet — RPC: `https://rpc.testnet.arc.network` — Chain ID: `5042002` — gas paid in USDC ([faucet](https://faucet.circle.com))
