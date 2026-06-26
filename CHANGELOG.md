# Changelog - cv-matcher

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

All notable changes to this project are documented in this file.
The format is based on Keep a Changelog, and this project adheres to semantic versioning.

## [0.2.0] - 2026-06-26 - Public release preparation

### Changed
- Internationalization: all docs and prompts (including `standardprompt_v1/v2`) translated Swedish -> English. File-type naming tokens kept as data contracts.
- PII sanitized: candidate name/email, company name, absolute paths, and personal file/folder names replaced with placeholders across all publishable files.
- `config.example` rewritten with `<PLACEHOLDER>` values.

### Removed
- Decoupled from the third-party Resume-Matcher project: deleted `03_src/resume-matcher-runner/` (skill, 6 PowerShell scripts, endpoint config), the packaged `.skill` export, and the integration plan doc. No runtime dependency on any external/localhost service remains.

### Added
- `01_docs/OPTIONAL_resume_matcher.md` - optional, clearly-marked recommendation for plugging in an external resume-tailoring tool (e.g. `srbhr/Resume-Matcher`).
- `01_docs/SETUP_DATA.md` - how to set up the folder/file data structure on a new install.
- `cowork-configurations.example.md` (per-install template); `cowork-configurations.md` gitignored.
- Skills: `skills/cv-matcher`, `skills/ats-optimizer`, `skills/linkedin-profile-validator`.

### Excluded from publication (kept locally, gitignored)
- `00_admin/` internal docs and the upstream Swedish standard copies.

### Verification
- PII sweep over publishable files is clean; no resume-matcher / localhost references remain outside the single optional note.

## [0.1.0] - 2026-05-31

### Added
- Initial project structure (`00_admin`, `01_docs`, `03_src`, `04_tests`, `05_logs`, `06_exports`).
- Standard prompt v2 - the 20-step process that produces a complete application from a given ad.
- Standard prompt v1 - archived first version, kept for traceability.
- Aggregated lessons learned and ATS keyword bank across previous tracks.
- Quickstart, user guide, and architecture documentation.
- Verification checklist (`04_tests/validation/promptval_checklist.md`).
