<!-- aicom-mirror-notice -->
> **📖 Read-only mirror.** `aimarket-widget` is published from the canonical AI-Factory monorepo.
> **Pull requests are not accepted** — any commit pushed here is overwritten by
> `scripts/mirror_satellites.sh` on the next sync.
> 🐞 Found a bug or have a request? Please **[open an issue](https://github.com/alexar76/aimarket-widget/issues)**.

# AIMarket Widget v2.0.0

<!-- aicom-readme-badges -->
<p align="center">
  <a href="https://github.com/alexar76/aimarket-widget/actions/workflows/ci.yml"><img src="docs/badges/ci.svg" alt="CI" /></a>
  <a href="docs/badges/coverage.svg"><img src="docs/badges/coverage.svg" alt="Test coverage" /></a>
  <a href="LICENSE"><img src="docs/badges/license.svg" alt="License: MIT" /></a>
</p>
<!-- /aicom-readme-badges -->










> **Ecosystem:** [AICOM overview & live demos](https://modeldev.modelmarket.dev) · **Oracles:** [oracles.modelmarket.dev](https://oracles.modelmarket.dev) · [GitHub](https://github.com/alexar76/oracles) · **Community:** [Discord · Pollux](https://discord.gg/aimarket) · [Telegram · Castor](https://t.me/just_for_agents)

**Embeddable AI capability search + invoke widget. One `<script>` tag.**

## 1-Click Agent Embed

**~60 seconds to production.** One `<script>` tag gives your site **discover + wallet channel + invoke UI** with theme auto-detect and affiliate economics.

| | |
|---|---|
| **What** | `data-intent`, `data-budget`, `data-affiliate-id` → full agent surface |
| **Why** | Stripe-Checkout simplicity for AI capabilities — no weeks of API glue |
| **Deep dive** | [docs/killer-feature-one-click-embed.md](docs/killer-feature-one-click-embed.md) · [Ecosystem capabilities](../docs/killer-features.md) |

## Live Demo

- **Live:** https://alexar76.github.io/aimarket-widget/
- **Docs:** https://github.com/alexar76/aimarket-widget/blob/main/README.md

**[GitHub Pages demo](https://alexar76.github.io/aimarket-widget/)** — static embed demo (enable Pages → GitHub Actions in repo settings)

**[modelmarket.dev/widget/demo](https://modelmarket.dev/widget/demo)** — interactive demo with all 6 themes

**[modelmarket.dev/live](https://modelmarket.dev/live)** — AI Economy live ticker (Bloomberg Terminal)

## Quick Start

```html
<script src="https://modelmarket.dev/widget/widget.js"
        data-theme="auto"
        data-intent="translate to 5 languages"
        data-budget="3.00"
        data-hub-url="https://modelmarket.dev"
        data-affiliate-id="my_blog"></script>
```

## Themes

| Theme | `data-theme` | Preview |
|-------|-------------|---------|
| Cyber (dark) | `cyber` | GitHub-style dark |
| Neon | `neon` | High-contrast cyberpunk |
| Light | `light` | Clean white |
| Paper | `paper` | Warm minimalist |
| Midnight | `midnight` | Dark blue enterprise |
| Ocean | `ocean` | Teal & coral |
| **Auto** | `auto` | **Detects parent page theme** |

`data-theme="auto"` detects the parent page's `data-theme-bg`, `<html>` class, background luminance, and `prefers-color-scheme` media query. Switches live when system theme changes.

## Affiliate Program

Set `data-affiliate-id="my_site"` — earn 30% of every widget invocation spend from your visitors.

## Security

- **No inline event handlers** — all events via `addEventListener`. XSS-safe.
- **Safe DOM** — user data rendered via `textContent`, never `innerHTML`
- **Content escaping** — `<`, `>`, `&` escaped before any HTML insertion
- **Safety gate** — injection attempts return HTTP 403 with signed rejection receipt

## Try-before-buy (sandbox)

The **Try free (N)** button calls Hub with `X-AIMarket-Sandbox-Visitor` (stored in `localStorage`). No payment channel is opened until the visitor exhausts free trials (default 3 per visitor, hub-configurable).

Paid flow (programmatic): `window.__aimwTryPaid(productId, capabilityId, sourceHub)` — opens v2 channel, invokes, settles.

See [docs/ecosystem-integration.md](../docs/ecosystem-integration.md).

## API

The widget calls the hub's v2 API:

| Call | Endpoint |
|------|----------|
| Search | `GET /ai-market/v2/search?intent=...&limit=6` |
| Channel open | `POST /ai-market/v2/channel/open` |
| Invoke | `POST /ai-market/v2/invoke` (with `X-Payment-Channel` header) |
| Channel close | `POST /ai-market/v2/channel/close` |

## License

MIT — see [LICENSE](LICENSE).

## Governance

| Doc | Purpose |
|-----|---------|
| [LICENSE](LICENSE) | MIT terms |
| [SECURITY.md](SECURITY.md) | Vulnerability reporting |
| [CONTRIBUTING.md](CONTRIBUTING.md) | How to contribute |
| [CONTRIBUTORS.md](CONTRIBUTORS.md) | Maintainers & recognition |

Maintained by AI-Factory · [Demo](https://modelmarket.dev/widget/demo) · [Live Stream](https://modelmarket.dev/live) · [Hub](https://modelmarket.dev)

## Community

The [DIOSCURI](https://github.com/alexar76/dioscuri) twins answer questions from synced GitHub docs.

| Channel | Twin | Best for |
|---------|------|----------|
| [Discord](https://discord.gg/aimarket) | Pollux | Help, ideas, show-and-tell |
| [Telegram](https://t.me/just_for_agents) | Castor | Releases, digests, quick news |

**Ecosystem map:** [Alien Monitor](https://magic-ai-factory.com/monitor/) · [AICOM](https://magic-ai-factory.com)
