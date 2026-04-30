# VSIX Integrity Verification

This document explains how to verify that a HIC Mouse `.vsix` file is authentic and has not been tampered with.

## Method 1: Install from a Registry (Recommended)

The simplest and most secure method is to install directly from your editor's extension registry.

**VS Code (Marketplace):**
```bash
code --install-extension hic-ai.mouse
```
The VS Code Marketplace performs repository signing on all extensions. VS Code automatically verifies the signature on install and update. If the signature is invalid, VS Code will refuse to install the extension.

**Cursor / other Open VSX clients:**

Install HIC Mouse by HIC AI, Inc. from the Open VSX registry through your editor's built-in extension manager. Open VSX maintains its own publisher verification and repository signing mechanism. Extensions are verified automatically on install — no manual steps required.

## Method 2: Verify SHA-256 Checksum

If you downloaded a `.vsix` file directly (e.g., for offline installation), you can verify its integrity using the published checksum.

### Step 1: Download the Checksum

Checksums are published alongside each release at:

```
https://github.com/hic-ai-inc/mouse/releases/tag/vX.Y.Z
```

Download the `checksums.sha256` file from the release assets.

### Step 2: Compute the Local Checksum

**macOS / Linux:**
```bash
shasum -a 256 mouse-X.Y.Z.vsix
```

**Windows (PowerShell):**
```powershell
Get-FileHash mouse-X.Y.Z.vsix -Algorithm SHA256
```

## Method 3: SLSA Provenance (Planned)

SLSA provenance attestation is not yet available for HIC Mouse releases. GitHub Artifact Attestations (used for SLSA provenance) require GitHub Enterprise Cloud for private repository workflows. Since the Mouse build pipeline runs in a private repository, attestations cannot currently be generated.

We plan to implement attestation in a future release. In the meantime, Methods 1 and 2 above provide strong integrity guarantees:

- **Registry signing** (Method 1) cryptographically verifies that the extension was published by the verified `hic-ai` publisher account
- **SHA-256 checksums** (Method 2) verify that a directly downloaded `.vsix` file has not been modified since the official build

For details on this limitation, please contact [security@hic-ai.com](mailto:security@hic-ai.com).

## Questions?

If you have concerns about the authenticity of a Mouse installation, contact [security@hic-ai.com](mailto:security@hic-ai.com).
