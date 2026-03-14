<h1 align="center">ELECTRUM MONERO (XMR)</h1>

[![Language](https://img.shields.io/badge/language-C%2B%2B17-111827?style=for-the-badge)](./CMakeLists.txt)
[![Build](https://img.shields.io/badge/build-CMake-1f2937?style=for-the-badge)](./CMakeLists.txt)
[![Network](https://img.shields.io/badge/network-Monero-b45309?style=for-the-badge)](#project-scan)
[![License](https://img.shields.io/badge/license-BSD--3--Clause-374151?style=for-the-badge)](./LICENSE)

```text
Privacy-first codebase. Full node, wallet tools, and core protocol logic in one tree.
```

<p align="center">
  <img src="./screen/photo_2026-03-14_15-27-41.jpg" alt="Electrum Monero screenshot" width="720">
</p>

## Project Scan

This repository contains the Monero core source tree: the daemon, wallet CLI, wallet RPC service, tests, build tooling, and supporting docs.
It is not a thin client and not a UI wrapper. It is the main implementation layer.

| Area | Value |
| --- | --- |
| Runtime | Native binaries |
| Stack | `C++17`, `C11`, `CMake` |
| Main targets | `monerod`, `monero-wallet-cli`, `monero-wallet-rpc` |
| Core code | [`src/`](/home/frank/githubs/GITS/electrum-xmr-/src) |
| Docs and tooling | [`docs/`](/home/frank/githubs/GITS/electrum-xmr-/docs), [`contrib/`](/home/frank/githubs/GITS/electrum-xmr-/contrib), [`utils/`](/home/frank/githubs/GITS/electrum-xmr-/utils) |

## Inside The Tree

`src/daemon/` -> node process and daemon flow  
`src/simplewallet/` -> terminal wallet layer  
`src/wallet/` -> wallet engine and RPC side  
`tests/` -> regression and behavior coverage  
`external/` + `.gitmodules` -> bundled dependency surface

## Build Path

```text
sync deps   -> git submodule update --init --recursive
configure   -> cmake -S . -B build
compile     -> cmake --build build -j
```

## First Launch

```text
node        -> ./build/bin/monerod
wallet      -> ./build/bin/monero-wallet-cli
```

<p align="center">
  <img src="./assets/xmr_2.png" alt="Electrum Monero XMR" width="280">
</p>
