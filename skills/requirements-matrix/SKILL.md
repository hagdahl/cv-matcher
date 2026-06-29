---
name: requirements-matrix
description: Turn a job ad into a requirements matrix (skall/bör) with evidence. Use when the user says "kravmatris", "requirements matrix", "do I meet the requirements", "gap analysis for this ad", or wants a must/should breakdown scored against the CV. Produces a table of each requirement, met/partial/gap, and CV evidence.
---

# requirements-matrix

> Version: 1.0.0 · Part of the `cv-matcher` project.

The analytical core of a strong application: a structured match of the ad's
requirements against the candidate's CV.

## Procedure

1. Extract requirements from the ad and classify each as **skall** (must) or
   **bör** (should/merit).
2. For each, score **Met / Partial / Gap** with **evidence** from the CV master
   (specific role, project, certification, years).
3. Summarize: % of must-haves met, the critical gaps, and how to address/frame each.
4. Output the per-track `Analys och kravmatris v{major}.{minor}` file; feed the
   matched terms to `ats-optimizer` and `cv-matcher`.

## Guardrails

- Evidence must be real and traceable to the CV master - mark unbacked items as
  Gap, never inflate to "Met".
- Distinguish "certified" from "trained/exam booked" precisely.
- A large share of unmet must-haves is a signal to reconsider applying - surface it.
