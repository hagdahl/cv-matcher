---
name: cover-letter-writer
description: Write or refine a tailored cover letter for one job ad. Use when the user says "write a cover letter", "personligt brev", "make my letter for this role", or wants just the letter (not the full application). Produces a concise, ATS-aware letter in the candidate's voice, grounded in the CV master.
---

# cover-letter-writer

> Version: 1.0.0 · Part of the `cv-matcher` project.

A focused skill for the cover letter alone (the full application is `cv-matcher`).

## Inputs

- The job ad and the candidate's CV master (`config.local`).
- Optional tone: formal / warm / direct (default: professional and concise).

## Procedure

1. Pull the role's top requirements and Tier 1-2 ATS terms (see `ats-optimizer`).
2. Open with why this role/employer specifically; map 2-4 concrete, CV-backed
   achievements to the ad's must-haves; close with a clear, confident call to action.
3. Keep it to ~250-350 words, the candidate's voice, no generic AI filler.
4. Save as the per-track `Personligt brev v{major}.{minor}` file.

## Guardrails

- Never claim anything not supported by the CV master.
- Mirror the ad's language (Swedish/English) and key terminology truthfully.
- Validate against `04_tests/validation/promptval_checklist.md` before submitting.
