---
name: cv-matcher
description: Produce a complete, tailored job application from a single job ad. Use when the user says "tailor my CV for this ad", "match my profile against this job", "write an application for this assignment", "run the standard prompt", or pastes/points to a job ad and wants a CV, cover letter, requirements matrix, screening answers, and references. Self-contained; no external service required.
---

# cv-matcher

> Version: 1.0.0 · Core skill of the `cv-matcher` project.

Drives the 20-step `standardprompt_v2` workflow that turns one job ad into a
complete, ATS-aware application package, tailored to the candidate's CV master.

## Inputs

- The job ad (text, file, or URL).
- `config.local` pointing at the candidate's CV master, applications root, and
  ATS/lessons banks (see `01_docs/SETUP_DATA.md`).

## Procedure

1. Read `01_docs/standardprompt_v2.md` and follow its steps in order. Do not skip
   numbering; each step builds on the previous.
2. Create a per-track folder `YYYY-MM Company Role` under the applications root.
3. Produce the per-track deliverables using the file-naming convention
   (`Annons`, `Analys och kravmatris`, `CV`, `Personligt brev`, `Urvalsfragor`,
   `Referenser`, plus a `Lessons Learned` file), each `v{major}.{minor}`.
4. Apply the `ats-optimizer` skill to ensure Tier 1-2 keyword coverage.
5. Validate everything against `04_tests/validation/promptval_checklist.md`
   before reporting "done".

## Optional automation

An external resume-tailoring tool can be plugged in (see
`01_docs/OPTIONAL_resume_matcher.md`), but is not required. Treat any automated
rewrite as raw input to be reviewed against the checklist.

## Guardrails

- Never fabricate experience, certifications, or claims not supported by the CV
  master. Distinguish "certified" from "trained/exam booked" precisely.
- Preserve the candidate's voice; avoid generic AI phrasing.
- Keep all personal data local; nothing here is committed to the repository.
