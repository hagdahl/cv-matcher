---
name: profile-sync
description: Keep LinkedIn, marketplace consultant cards, and the CV master consistent from one source of truth. Use when the user says "sync my profiles", "is my LinkedIn consistent with my CV", "update my consultant card", or after editing the CV master. Reports drift between profiles and proposes aligned edits.
---

# profile-sync

> Version: 1.0.0 · Part of the `cv-matcher` project. Extends `linkedin-profile-validator`.

Treats the **CV master** as the single source of truth and keeps external profiles
(LinkedIn, consultant marketplace cards, etc.) consistent with it.

## Procedure

1. Take the CV master as canonical (titles, dates, skills, certifications, summary).
2. Compare each external profile against it; list **drift**: outdated titles/dates,
   missing or extra skills, inconsistent certification status, divergent summaries.
3. Propose specific, truthful edits per profile to realign, in the candidate's voice.
4. For LinkedIn specifically, also run `linkedin-profile-validator` checks
   (discoverability, ATS/recruiter terms).

## Guardrails

- Propose, do not post. Never notify the user's network or publish changes without
  explicit approval.
- Truthfulness first - never introduce a claim the CV master doesn't support.
- Certification status must be precise ("certified" vs "trained" vs "exam booked").
