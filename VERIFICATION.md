# VSIX Integrity Verification

This document explains how to verify that a Mouse `.vsix` file is authentic and has not been tampered with.

## Method 1: Install from a Registry (Recommended)

The simplest and most secure method is to install directly from your editor's extension registry.

**VS Code (Marketplace):**
```bash
code --install-extension hic-ai.mouse
```
The VS Code Marketplace performs repository signing on all extensions. VS Code automatically verifies the signature on install and update. If the signature is invalid, VS Code will refuse to install the extension.

**Cursor / other Open VSX clients:**

Install Mouse from the Open VSX registry through your editor's built-in extension manager. Open VSX maintains its own publisher verification and repository signing mechanism. Extensions are verified automatically on install — no manual steps required.

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

### Step 3: Compare

The output hash should exactly match the corresponding line in `checksums.sha256`. If it does not match, do not install the file — it may have been tampered with.

## Method 3: Verify SLSA Provenance (Advanced)

Once SLSA provenance attestation is available, you can verify the build provenance:

```bash
gh attestation verify mouse-X.Y.Z.vsix --owner hic-ai-inc
```

This cryptographically proves the `.vsix` was built by the official GitHub Actions workflow from a specific source commit.

## Questions?

If you have concerns about the authenticity of a Mouse installation, contact [security@hic-ai.com](mailto:security@hic-ai.com).
