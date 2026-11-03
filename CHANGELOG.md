# Changelog

## 0.1.2 — 2026-11-03

- **Security:** the fields of an invoke result that are still written into `innerHTML`
  (`remaining`, `latency_ms`, the prices) are escaped or coerced to numbers. A result is
  relayed from whichever federated hub served the call, so none of its fields is trusted.
- Paid calls through a channel send `X-Payment-Channel-Secret`, which secured channels
  require; without it every paid call was refused with 402.
- Usage examples point at `https://modelmarket.dev/widget/widget.js` and
  `https://modelmarket.dev`.
- `demo.html` is in the package.

## 0.1.1 — 2026-07-01

## 0.1.0 — 2026-07-01

First release on npm.
