# Data setup -- creating the data structure on a new install

> **Version:** 1.0.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

`cv-matcher` ships **logic and prompts only -- no personal data**. There is no
database; the "data structure" is a set of folder and file conventions plus a few
reference documents you provide. This document explains how to set those up.

## 1. What you provide (kept local, never in git)

| Item | Placeholder | What it is |
|---|---|---|
| Master CV | `<CV_MASTER>` | A consolidated markdown CV / requirements-matrix reference -- the single source of truth for your experience, skills, and certifications. |
| Visual CV template | `<CV_TEMPLATE_DOCX>` | A Word template for the formatted CV output. |
| Ads folder | `<ADS_ROOT>` | Where you keep job ads to match against (one subfolder per opportunity). |
| Applications root | `<APPLICATIONS_ROOT>` | Per-track output folders (one per application). |
| Pipeline file | `<PIPELINE_FILE>` | A cross-cutting markdown view of all tracks/status. |

Keep all of the above **outside** this repository. Point the project at them via
`config.local` (copied from `config.example`).

## 2. Per-track folder convention

Each application ("track") is one folder under `<APPLICATIONS_ROOT>`:

```
<APPLICATIONS_ROOT>/
  YYYY-MM Company Role/
    Annons v0.1.md                    # the job ad
    Analys och kravmatris v0.1.md     # analysis + requirements matrix
    CV v0.1.md                        # tailored CV
    Personligt brev v0.1.md           # cover letter
    Urvalsfragor v0.1.md              # screening questions
    Referenser v0.1.md                # references
    <folder> Lessons Learned v0.1.md  # per-track lessons
```

- Folder name pattern: `{YYYY-MM} {Company} {Role}` (`[matching].folder_pattern`).
- File-type tokens and the `v{major}.{minor}` version suffix are a **naming
  contract** the prompt relies on -- keep them stable (see `config.example`).

## 3. Reference banks (in this repository, generic)

- `01_docs/ATS_keywords_aggregerat.md` -- a reusable ATS keyword bank, tiered 1-4.
  Grow it as you analyze new ads. It contains generic domain vocabulary, not
  personal data.
- `01_docs/LESSONS_LEARNED_aggregerat.md` -- cross-track lessons, with track
  sources pseudonymized (SP-NN).

## 4. Run the workflow

1. Read `01_docs/cv-matcher_quickstart.md`.
2. Confirm `config.local` exists and points at your real sources.
3. For a new ad: run `01_docs/standardprompt_v2.md` (the 20-step process).
4. Validate every deliverable against
   `04_tests/validation/promptval_checklist.md` before submitting.

## 5. Optional automation

See `01_docs/OPTIONAL_resume_matcher.md` for plugging in an external
resume-tailoring tool. It is optional and not required.

## What is intentionally NOT in this repository

- No personal CV, cover letters, references, or application history.
- No company, customer, or contact names tied to real applications.
- No `config.local` (your machine-specific paths) and no
  `cowork-configurations.md` (your environment instance values).
