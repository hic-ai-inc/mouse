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

### Step 1: Find the Checksum

Checksums are published in this repository at:

```
https://github.com/hic-ai-inc/mouse/tree/main/checksums
```

Each version has two checksum files: `vX.Y.Z.marketplace.sha256` (VS Code Marketplace) and `vX.Y.Z.openvsx.sha256` (Open VSX).

### Step 2: Compute the Local Checksum

**macOS / Linux:**
```bash
shasum -a 256 mouse-X.Y.Z.vsix
```

**Windows (PowerShell):**
```powershell
Get-FileHash mouse-X.Y.Z.vsix -Algorithm SHA256
```

### Step 3: Compare

The output hash should exactly match the corresponding line in the checksum file. If it does not match, do not install the file — it may have been tampered with.

VS Code does not retain the original `.vsix` after installation. To verify an installed version, download the corresponding `.vsix` from the registry and compare that file against the published checksum.

## Questions?

If you have concerns about the authenticity of a Mouse installation, contact [security@hic-ai.com](mailto:security@hic-ai.com).
