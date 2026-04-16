# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in Mouse, please report it responsibly.

**Do NOT open a public GitHub issue for security vulnerabilities.**

### How to Report

1. **GitHub Security Advisories (preferred):** Use the [Report a vulnerability](https://github.com/hic-ai-inc/mouse/security/advisories/new) feature on this repository.
2. **Email:** Send details to [security@hic-ai.com](mailto:security@hic-ai.com).

### What to Include

- Description of the vulnerability
- Steps to reproduce
- Affected version(s)
- Potential impact
- Any suggested fix (optional)

### What to Expect

- **Acknowledgment:** Within 2 business days
- **Initial assessment:** Within 5 business days
- **Resolution target:** Critical vulnerabilities within 14 days; others within 30 days
- **Credit:** We will credit reporters in release notes (unless you prefer anonymity)

### Scope

This policy covers:
- The Mouse VS Code extension (`hic-ai.mouse`)
- The Mouse MCP server
- The Mouse licensing system
- The hic-ai.com website and API

Out of scope:
- Third-party dependencies (report to the upstream maintainer)
- Social engineering attacks
- Denial of service attacks against hic-ai.com

## Supported Versions

| Version | Supported |
|---------|-----------|
| Latest  | Yes       |
| < Latest | Best-effort security patches for the previous minor version |

## Security Practices

- All releases are built in CI with audited dependencies (`npm audit`)
- VSIX artifacts are verified via SHA-256 checksums (see [VERIFICATION.md](VERIFICATION.md))
- The VS Code Marketplace performs repository signing and malware scanning
- GitHub Actions workflows use SHA-pinned action references
- No secrets or credentials are included in distributed artifacts
