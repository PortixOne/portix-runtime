> **This repository is a read-only mirror. Development happens in [PortixOne/portixone](https://github.com/PortixOne/portixone).**

# Portix Runtime

> The local bridge that lets web apps talk to printers, cash drawers, scales, and other hardware — without fighting the browser.

Part of [PortixOne](https://github.com/PortixOne/portixone), a secure edge runtime connecting web apps to local hardware.

---

This repo exists so the runtime is discoverable and browsable on its own — **it will not `npm install`/build standalone**, since it depends on `@portixone/protocol`, `@portixone/shared`, and `@portixone/escpos`, which live in the monorepo.

To actually run it: clone [`portixone`](https://github.com/PortixOne/portixone) and follow the [`runtime/README.md`](https://github.com/PortixOne/portixone/tree/master/runtime) there.

---

## What it does

- Accepts print jobs over a local HTTP API (`POST /print`) and reports live status over WebSocket.
- Detects installed printers on Windows.
- Validates every request with a local API key — no cloud dependency required to print.
- Currently MVP scope: **Windows, local printing only**. Cash drawer, scales, and other device capabilities are on the roadmap.

## Architecture

Config, Logger, Auth, Security, Storage, Protocol adapter/validator, HTTP + WebSocket API, Printer Manager (detectors + drivers), Queue Manager — see [`src/`](src) for the full module layout.

## License

MIT — see [`portixone`](https://github.com/PortixOne/portixone) for the canonical license file.
