---
name: reference-manager
description: Select and tailor references per application. Use when the user says "which references for this role", "prepare my references", "referenser", or needs a reference list matched to a job ad. Picks the most relevant referees and frames each to the role's requirements.
---

# reference-manager

> Version: 1.0.0 · Part of the `cv-matcher` project.

Chooses and frames references for a specific application from a reference bank.

## Procedure

1. From the candidate's reference bank (local, not in the repo), select referees
   whose relationship and domain best match the ad's must-haves and seniority.
2. For each, draft a one-line framing (relationship, period, what they can speak
   to) aligned to the role.
3. Produce the per-track `Referenser v{major}.{minor}` file with name, role,
   relationship, and contact placeholder.
4. Flag if a referee should be pre-warned about a likely call.

## Guardrails

- Reference contact details are personal data - keep them in a local-only store,
  never in the repo or shared without consent.
- Only list referees who have agreed to be contacted.
