# NovaTrace

Built for Base

NovaTrace is a small Base ecosystem repository built to confirm wallet connectivity and basic onchain reads against Base Mainnet and Base Sepolia.

It is intentionally lightweight: the goal is to provide a repeatable “does Base work end-to-end?” probe using official Coinbase tooling rather than a feature-heavy dApp.

## What You Get

- OnchainKit wallet connection UI (browser-friendly onboarding)
- Viem-powered Base JSON-RPC reads (chainId, latest block, ETH balance)
- Explicit Base chain targets (8453 / 84532)
- Basescan deployment and verification references (mainnet + testnet)

## Networks

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

## Code Location

Primary file: app/novaTrace.ts

## How It Works

At runtime, the app:
- Binds an OnchainKitProvider to the selected Base chain
- Uses OnchainKit Wallet for connection UX
- Creates a Viem public client against the selected Base RPC
- Fetches:
  - RPC chainId
  - latest block number
  - native ETH balance for a supplied address
- Prints the relevant explorer URL for quick inspection

## Project Structure

app/  
- novaTrace.ts  
  React entry component that wires wallet UI to Base read operations.

Common supporting files for a complete repository:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env (optional)

## Dependencies

OnchainKit  
https://github.com/coinbase/onchainkit  

Viem  
EVM client library for Base RPC reads  

## Setup

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run with a standard React/Vite or Next.js dev server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL


## Author

GitHub: https://github.com/lashy-maidens0b
Public contact (email): carpals-grabby.0x@icloud.com
Public contact (X): https://x.com/mizevandrew

## License

MIT License

## Testnet Deployment (Base Sepolia)

**Network:** Base Sepolia  
**chainId (decimal):** 84532  
**Explorer:** https://sepolia.basescan.org  

**Deployed contract #1 address:**  
0x038ad43854f68b8976af70dd75111a8dec0aec72

**Deployed contract #2 address:**  
0xaa6dfcf4fac4bb5b5b92d98ec75b79a9a0758109

**Basescan deployment and verification links:**  
- Contract #1 address:  
  https://sepolia.basescan.org/address/0x038ad43854f68b8976af70dd75111a8dec0aec72 
- Contract #2 address:  
  https://sepolia.basescan.org/address/0xaa6dfcf4fac4bb5b5b92d98ec75b79a9a0758109 
- Contract #1 verification (source code):  
  https://sepolia.basescan.org/0x038ad43854f68b8976af70dd75111a8dec0aec72/0#code  
- Contract #2 verification (source code):  
  https://sepolia.basescan.org/0xaa6dfcf4fac4bb5b5b92d98ec75b79a9a0758109/0#code  

This deployment is used to validate Base-compatible tooling, account abstraction flows, and onchain read operations in a test environment prior to mainnet usage.

