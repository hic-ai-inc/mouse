# HIC Mouse — Precision Editing Tools for AI Coding Agents

HIC Mouse gives your AI coding assistant surgical precision for file editing. Instead of rewriting entire files, your AI uses Mouse's tools to make targeted, line-level changes — faster, safer, and more accurate.

**Works with:** GitHub Copilot, Claude Code, Amazon Q Developer, Roo Code, Kilo Code, and other MCP-compatible AI coding assistants in VS Code, Cursor, and Kiro.

> This is the official public repository for HIC Mouse. It is used for documentation, issue tracking, security reporting, and community support. This repository does not publish the proprietary source code.

## Installation

### From VS Code (Recommended)

1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for **Mouse by HIC AI**
4. Click **Install**

### From the Terminal

```bash
code --install-extension hic-ai.mouse
```

### From Open VSX

If you use an Open VSX-compatible editor (such as Kiro or Cursor):

- **Registry:** https://open-vsx.org/extension/hic-ai/mouse
- Or search for **Mouse by HIC AI** in your editor's extension manager.

### Post-Installation Setup

1. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
2. Select **Mouse: Initialize Workspace**
3. Choose your AI assistant from the dropdown
4. Reload the window (`Developer: Reload Window`)

Full setup guide: [https://hic-ai.com/docs/installation](https://hic-ai.com/docs/installation)

## Features

- **Precision editing** — line-level insert, replace, delete, and range operations
- **Batch editing** — multiple atomic edits in a single operation
- **Content search** — regex and literal search within files
- **File navigation** — jump to line, read ranges, inspect structure
- **Safety guardrails** — automatic review for large operations
- **Works with all supported MCP-compatible AI assistants**

## Compatibility

**IDEs:** VS Code, Cursor, Kiro

**AI Clients:** GitHub Copilot, Claude Code, Amazon Q Developer, Roo Code, Kilo Code.

**Models:** Mouse is model-agnostic. Tested and compatible with:
- Anthropic: All Claude models (4.0+)
- Google: All Gemini models (2.5+)
- OpenAI: All GPT models (4o+)
- Other: Raptor mini, Deepseek (3.2+), Minimax (M2.5+), Qwen3 Coder Next, GLM (5+)

Compatibility depends primarily on the AI client's MCP/tool support, not on the underlying LLM provider. See the full [feature compatibility matrix](https://hic-ai.com/features/) for details.

**Platforms:** Windows, macOS, Linux. Requires Node.js 20+.

## Pricing

HIC Mouse includes a **14-day free trial** — no account or credit card required. After the trial, choose a plan at [hic-ai.com/pricing](https://hic-ai.com/pricing).

## Links

- [Documentation](https://hic-ai.com/docs/)
- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=hic-ai.mouse)
- [Open VSX Registry](https://open-vsx.org/extension/hic-ai/mouse)
- [Report a Bug](https://github.com/hic-ai-inc/mouse/issues/new?template=bug_report.yml)
- [Request a Feature](https://github.com/hic-ai-inc/mouse/issues/new?template=feature_request.yml)
- [Security Policy](SECURITY.md)

## Community

- [Website](https://hic-ai.com) — Documentation, research, and pricing
- [X (Twitter)](https://x.com/hic_ai_inc) — Product updates and technical insights
- [Discord](https://discord.gg/zCTWRYkeFb) — Real-time help and community
- [Issues](https://github.com/hic-ai-inc/mouse/issues) — Bug reports and feature requests
- [Discussions](https://github.com/hic-ai-inc/mouse/discussions) — Questions, tips, and announcements

## Verification

SHA-256 checksums for each published release are available in the [checksums/](checksums/) directory. Each version has files for both VS Code Marketplace and Open VSX artifacts.

For full verification instructions, see [VERIFICATION.md](VERIFICATION.md).

## Source Availability

HIC Mouse is proprietary commercial software. This repository does not publish the proprietary source code. The extension is distributed exclusively through the VS Code Marketplace and Open VSX.

## License

HIC Mouse is proprietary software. See [LICENSE](LICENSE) for terms.

© 2026 HIC AI, Inc. All rights reserved.
