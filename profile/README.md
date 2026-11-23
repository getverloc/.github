# verloc

**Self-hosted, single-binary LLM gateway with an embedded operations dashboard.**

Point your applications and coding agents at one OpenAI-compatible endpoint. Manage upstream providers, encrypted credentials, adaptive model routing, client API keys, rate limits, deterministic caching, and SQLite usage analytics directly from your browser — with zero external database or Redis required.

<p align="center">
  <a href="https://github.com/getverloc/verloc">
    <img src="https://raw.githubusercontent.com/getverloc/verloc/master/assets/overview.png" alt="verloc operations dashboard" width="100%" />
  </a>
</p>

## Quick Start

Install as a background service on Linux (`systemd`) or macOS (`launchd`):

```sh
curl -fsSL https://raw.githubusercontent.com/getverloc/verloc/master/install.sh | sh -s -- --service
```

Or deploy system-wide on a Linux server:

```sh
curl -fsSL https://raw.githubusercontent.com/getverloc/verloc/master/install.sh | sudo sh -s -- --system
```

## Repositories

| Repository | Description |
| :--- | :--- |
| [**getverloc/verloc**](https://github.com/getverloc/verloc) | Core Go LLM gateway, adaptive router, SQLite telemetry store, and embedded React operations dashboard |

## Why verloc

- **Single static binary:** Compiled Go gateway + embedded React dashboard + embedded SQLite. No Postgres, Redis, or Node.js runtime needed.
- **Built for low-latency inference:** Zero-copy SSE streaming, adaptive Peak-EWMA / weighted routing, speculative hedging, per-provider concurrency bulkheads, and circuit recovery.
- **Multi-protocol & multi-provider:** Chat Completions, Responses, Anthropic Messages, Embeddings, Images, and live upstream model discovery across providers.
- **Operational control:** Encrypted upstream credentials, scoped client API keys with RPM/TPM/concurrency limits, audit logs, backups, and checksum-verified zero-data-loss self-updates.

## Community & Security

- **Questions & ideas:** [GitHub Discussions](https://github.com/getverloc/verloc/discussions)
- **Bug reports & feature requests:** [GitHub Issues](https://github.com/getverloc/verloc/issues)
- **Releases & changelogs:** [GitHub Releases](https://github.com/getverloc/verloc/releases)
- **Security vulnerabilities:** Report privately via [GitHub Security Advisories](https://github.com/getverloc/verloc/security/advisories/new)
