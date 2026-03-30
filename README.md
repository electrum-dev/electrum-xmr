[![License](https://img.shields.io/badge/license-repo--root-black.svg)](LICENSE)
[![Solana](https://img.shields.io/badge/network-Solana-14F195.svg)](https://solana.com/)
[![Yarn](https://img.shields.io/badge/package_manager-Yarn-2C8EBB.svg)](https://yarnpkg.com/)

# Sollet Wallet

Sollet is a full-featured wallet for Solana. This repository currently contains Sollet app sources under `sollet/` and `sollet-src/`, alongside other unrelated code.

| Area | Included in this repository |
| --- | --- |
| Wallet core | account creation, import, export, mnemonic handling, signing flows |
| Assets | SOL balances, SPL tokens, token account operations |
| Connectivity | Solana RPC interaction, custom clusters, connection management |
| Integrations | Ledger support, swap flows, Solana Name Service, wallet connection flows |

## Project Layout

```text
sollet/
  src/            UI, wallet actions, pages, and utilities
  extension/src/  extension manifest, background script, content script, injected script
  public/         base web assets
  .cert/          local HTTPS certificates for development

sollet-src/
  src/            duplicate Sollet source tree
  extension/src/  duplicate extension source tree
  public/         duplicate web assets
  .cert/          local HTTPS certificates for development
```

## Requirements

- Node.js 14.x or 16.x
- Yarn 1.x
- a Unix-like shell for shell-based build steps

The Sollet packages use `react-scripts` and Yarn scripts defined in:

- `sollet/package.json`
- `sollet-src/package.json`

## Installation

Choose the package directory you want to run and install dependencies there:

```bash
cd sollet
yarn
```

## Development HTTPS Setup

Local development is configured to run over HTTPS. `.env.development` points `react-scripts` to certificate files stored in `.cert/`:

```env
HTTPS=true
SSL_CRT_FILE=./.cert/cert.pem
SSL_KEY_FILE=./.cert/key.pem
```

Before starting the app, make sure these files exist:

```text
.cert/cert.pem
.cert/key.pem
```

If the certificate pair is missing, `yarn start` will fail or run with an invalid local HTTPS setup.

If HTTPS is not required for your local workflow, adjust `.env.development` accordingly. Do that only if your target flow does not depend on secure-context browser APIs.

## Running The App

Start the wallet in development mode from the package directory:

```bash
cd sollet
yarn start
```

The app entry is `src/index.js`, the main shell is wired through `src/App.js`, and the wallet screens live under `src/pages`.

## Development Commands

```bash
yarn start            # run local development server
yarn build            # build the main app
yarn build:extension  # build the extension package
yarn test             # run tests
```

## Notes

- Local development expects certificates in `.cert/`.
- The project uses Yarn scripts as the primary workflow inside the Sollet package directories.
- Browser extension sources live in `extension/src/`.
