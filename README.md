# cv-matcher

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

A logic-and-prompt project that matches a candidate's CV and consulting profile
against job ads and consulting assignments, and produces a tailored CV, cover
letter, requirements matrix, screening answers, and references per application
("track").

**No personal data is stored in this repository.** All data sources are pointed
to via `config.local` (your machine-specific copy of `config.example`).

**Related project:** [`jobb-bevakning`](../jobb-bevakning) - watches sources for
new ads/assignments and triages them; `cv-matcher` then produces the application.
The two projects are independent and can be used separately (see
[Cross-project use](#cross-project-use)).

---

## Purpose

`cv-matcher` is the core of the application workflow. It contains:

- **Standard prompt v2** (`01_docs/standardprompt_v2.md`) - a 20-step process that
  turns a single job ad into a complete, ATS-aware application.
- **ATS keyword bank** (`01_docs/ATS_keywords_aggregerat.md`) - a reusable,
  tiered (1-4) vocabulary bank.
- **Aggregated lessons** (`01_docs/LESSONS_LEARNED_aggregerat.md`) - what has
  worked across tracks, with sources pseudonymized.
- **Quickstart** (`01_docs/cv-matcher_quickstart.md`) - pick up the work in a new
  session without prior context.

## Getting started

1. Copy `config.example` to `config.local` and fill in your paths
   (`config.local` is `.gitignored`).
2. Read `01_docs/SETUP_DATA.md` to set up the folder/file conventions and your
   CV master.
3. Read `01_docs/cv-matcher_quickstart.md`.
4. For a new ad: run `01_docs/standardprompt_v2.md`.
5. Validate every deliverable against
   `04_tests/validation/promptval_checklist.md` before submitting.

## Cross-project use

`cv-matcher` and `jobb-bevakning` reference each other but share no code or data
at runtime. `jobb-bevakning` produces a shortlist of relevant ads; `cv-matcher`
consumes one ad at a time. Each repository is self-contained and versioned
independently, so you can clone either one alone.

## Optional automation

See `01_docs/OPTIONAL_resume_matcher.md` for plugging in an external
resume-tailoring tool (for example the open-source `srbhr/Resume-Matcher`). It is
optional and not required - this project is self-contained.

## Project conventions

This project follows the `cowork-projektinstruktioner` standard (platform-
independent rules) and its application appendix. Per-machine instance values
(absolute paths, model names, ports, account IDs) live in a local-only
`cowork-configurations.md` - copy the committed template
`cowork-configurations.example.md` and keep your copy out of git.

## What is intentionally NOT in this repository

No personal CV, cover letters, references, or application history; no real
company/customer/contact names; no `config.local`; no
`cowork-configurations.md`. See `01_docs/SETUP_DATA.md`.

## License

See [`LICENSE`](LICENSE). (Choose/confirm a license before making the repository
public - see the pre-publication recommendations.)
