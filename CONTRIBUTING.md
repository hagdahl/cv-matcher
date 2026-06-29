# Contributing to cv-matcher

Thanks for your interest! cv-matcher is a logic-and-prompt project that tailors a
CV and application to a single job ad. It ships no personal data.

## Setup

1. `cp config.example config.local` and fill in your paths (gitignored).
2. Read `01_docs/SETUP_DATA.md` for the folder/file conventions and your CV master.

## Conventions (please follow)

- **Never commit personal data.** No real CVs, cover letters, references,
  application history, or real company/contact names. `config.local` and
  `cowork-configurations.md` stay gitignored.
- **The standard prompt is the core deliverable.** Keep
  `01_docs/standardprompt_v2.md` step numbering and structure stable; change the
  language/logic deliberately.
- **File-naming tokens are a contract.** The per-track file types
  (`Annons`, `Analys och kravmatris`, `CV`, `Personligt brev`, ...) are the naming
  convention the workflow relies on - keep them stable.
- **Truthfulness first.** Never add prompt logic that fabricates experience,
  certifications, or keywords a candidate cannot back up.
- **UTF-8, no BOM.**

## Before opening a PR

- Validate any workflow change against `04_tests/validation/promptval_checklist.md`.
- Update `CHANGELOG.md` and bump `VERSION` for user-facing changes.

Open an issue first for larger changes so we can align on the approach.
