# CODO Presale dApp

The website and token presale app for CODO, a Web3 project. Visitors read about the project and its roadmap, connect a crypto wallet and buy CODO tokens in the presale with ETH or USDT.

## Features

- **Wallet connection** with Web3Modal (MetaMask and WalletConnect), showing the connected address and balances
- **Presale:** buy tokens with ETH, or with USDT after an ERC-20 approval, against a tiered-pricing presale contract
- **Live sale status:** current tier and price, and a progress bar for tokens sold
- **Landing page:** project introduction with video, countdown timer, roadmap and links to the litepaper and documentation
- **Multicall** batches contract reads to load balances quickly

## Tech stack

Next.js · React · Redux · ethers.js · web3.js · Web3Modal + WalletConnect · Ethereum Multicall · Tailwind CSS · Chakra UI · Swiper

## Getting started

Requires Node.js and a browser wallet such as MetaMask.

Copy `.env.example` to `.env.local` and fill in the network and contract settings:

```
NEXT_PUBLIC_CODO_PRESALE=0x...     # presale contract address
NEXT_PUBLIC_USDC=0x...             # stablecoin (USDT) contract address
NEXT_PUBLIC_RPCURL=https://...     # RPC endpoint for the network
NEXT_PUBLIC_CHAINID=...            # chain ID
NEXT_PUBLIC_NETWORK_NAME=...       # network name shown to users
```

Then:

```bash
npm install
npm run dev        # http://localhost:3000
```

Rebuild the Tailwind styles after changing them with `npm run build:css`.

## Project structure

```
pages/index.js       Landing page: introduction, countdown, roadmap
pages/presale.js     Wallet connection and token purchase
state/eth.js         Wallet connection, balances and contract reads
abi/                 Presale and ERC-20 contract ABIs
components/          Layout, header, footer, modal, progress bar
store/               Redux store
```
