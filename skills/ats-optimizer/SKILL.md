---
name: ats-optimizer
description: Extract and prioritize ATS keywords from a job ad and verify a CV/cover letter covers them. Use when the user says "optimize for ATS", "what keywords does this job want", "will my CV pass the ATS", "check keyword coverage", or wants a tiered keyword analysis of an ad. Produces a Tier 1-4 keyword table and a coverage gap report against the candidate's documents.
---

# ats-optimizer

> Version: 1.0.0 · Part of the `cv-matcher` project.

Extracts the keywords an Applicant Tracking System is likely to score, tiers them
by importance, and checks whether the candidate's CV and cover letter cover the
high-tier terms - without keyword stuffing or fabricating experience.

## Tiers

| Tier | Meaning | Action |
|---|---|---|
| 1 | Verbatim from the ad (must-have terms) | Must appear in CV + cover letter |
| 2 | Common synonym/paraphrase | Should appear |
| 3 | Domain vocabulary | Nice to have |
| 4 | Industry jargon | Opportunistic |

## Procedure

1. Parse the ad. Pull required skills, certifications, tools, methods, and the
   exact phrasings used (Tier 1).
2. Map synonyms/paraphrases (Tier 2) and domain/jargon terms (Tier 3-4).
3. Cross-check against the candidate's CV master and the reusable bank in
   `01_docs/ATS_keywords_aggregerat.md`.
4. Produce a coverage report: which Tier 1-2 terms are present, missing, or only
   implied; suggest where to add missing terms truthfully.
5. Append any new generic terms to the aggregated bank (no personal data).

## Guardrails

- Only claim skills/keywords the candidate genuinely has. Never insert a Tier 1
  term the candidate cannot back up - flag it as a genuine gap instead.
- Keep formatting ATS-friendly (no tables/graphics in the parsed CV layer; plain,
  parseable text).
- The keyword bank stays generic and reusable; it must not encode a person's
  application history.
