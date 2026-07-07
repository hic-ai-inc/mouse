# Changelog

All notable changes to HIC Mouse will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).


## [0.10.39] - 2026-07-07

### Changed

- - Fix: find_in_file limit=0 now correctly treated as unlimited (capped at internal safety max) instead of erroring\n- Fix: Compact coordinate syntax (region, lineRange, colRange) now auto-normalizes string values to integers\n- Fix: Removed false 25-line cap language from read_lines, read_first_n_lines, and read_last_n_lines tool descriptions\n- Refactor: Removed stale version-history comments, empty section banners, and dead metadata for pruned tools from tool-metadata.js (-309 lines)


## [0.10.38] - 2026-04-30

### Changed

- Marketplace metadata fix: homepage URL now points to https://hic-ai.com (the /mouse subpage does not exist and was 404ing). No functional change.


## [0.10.37] - 2026-04-30

### Changed

- Marketplace metadata fix: package.json repository.url and bugs.url now point to the public hic-ai-inc/mouse repository. No change in functionality to Mouse tools.


## [0.10.36] - 2026-04-30

### Changed

- Release pipeline: unify version validation in mouse-version.js --action validate (single source of truth across VERSION + 5 package.json + 3 README + CHANGELOG); release script Step 5 git add now explicitly covers all README files and CHANGELOG.md; new --changelog-msg flag eliminates the validate-gate friction caused by TODO stubs; retired stale mouse/version.manifest.json (legacy dm-layer artifact). No change in functionality to Mouse tools.


## [0.10.35] - 2026-04-29

### Changed

- Release pipeline: SLSA build provenance attestation step gated behind `ENABLE_SLSA_ATTESTATIONS` repository variable; emits explicit warning to workflow summary when disabled (private-repo plan limitation, tracked in TECHNICAL_DEBT_LOG)
- Release pipeline: VSIX SHA-256 checksum now published to GitHub Actions step summary for artifact integrity verification

## [0.10.34] - 2026-04-29

### Changed

- Public-facing rebrand to "HIC Mouse" across package metadata, README, LICENSE, and activation surfaces
- Internal identifiers (commands, settings, walkthroughs, license prefix, bundle name) preserved for backward compatibility

### Added

- Release pipeline hardening: production-by-default DDB targeting and version-sync validation gate in `release-mouse.sh`


## [0.10.23] - 2026-04-10

### Fixed

- Trial heartbeat: removed `isLicensed()` gates so heartbeat fires for trial and licensed users
- `initializeWorkspace` now starts heartbeat immediately after workspace setup
- Belt-and-suspenders: `activate()` persists `installedVersion` unconditionally so `license_status` returns `currentVersion` before first heartbeat


## [0.9.9] - 2026-01-26

### Added

- Initial VS Code extension release
- MCP server integration
- 14-day free trial
- License key activation
- Status bar indicator
- Heartbeat for concurrent session management

### Features

- `quick_edit` — One-shot file editing
- `batch_quick_edit` — Multiple edits in atomic operation
- `find_in_file` — Pattern search with context
- `read_first_n_lines`, `read_last_n_lines`, `read_lines` — File navigation
- `jump_to_line_n` — Direct line access
- `get_file_metadata` — File information
- `save_changes`, `cancel_changes` — Staged edit workflow
- Math tools — `get_sum`, `get_difference`, `get_product`, `get_quotient`
- Date/time tools — `get_utc_date`, `get_utc_time`, `get_local_date`, `get_local_time`, `get_unix_timestamp`
- Notepad tools — `make_note`, `list_notes`, `read_note`, `search_notes`
