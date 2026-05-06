# Changelog

All notable changes to HIC Mouse will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
