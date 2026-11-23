# Security Policy

## Supported Versions

Security fixes are released for the latest minor version on the active major release line:

| Version | Supported |
| :--- | :--- |
| `1.x` (latest release) | Yes |
| `< 1.0` | No |

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues or discussions.**

Use GitHub's Private Vulnerability Reporting to notify maintainers confidentially:

- **Report privately:** https://github.com/getverloc/verloc/security/advisories/new

Please include as much of the following as possible:

- Affected component and version (`verloc -version`)
- Deployment context (OS/architecture, Docker vs. bare-metal, reverse proxy setup)
- Clear reproduction steps or proof-of-concept
- Potential impact (e.g., auth bypass, credential disclosure, SSRF, DoS)

## Response Expectations

- **Initial acknowledgment:** within 72 hours
- **Triage & severity assessment:** within 7 days
- **Fix & coordinated disclosure:** we will work with you on a patch, release a new SemVer version with SHA-256 verified artifacts, and credit you in the security advisory unless you prefer anonymity.

## Security Architecture Notes

verloc is designed for single-host self-hosted deployments. When evaluating or deploying verloc:

- Bind to loopback (`127.0.0.1`) and terminate TLS at a reverse proxy (Caddy, nginx, Traefik) with `VERLOC_SECURE_COOKIES=true` for any non-local access.
- Protect `master.key` and the data directory (`0700` permissions); upstream provider credentials are encrypted at rest with `master.key`.
- Self-updates enforce HTTPS to official GitHub release hosts, dial-time SSRF protection, constant-time SHA-256 checksum verification against `checksums.txt`, and pre-swap binary validation.
