---
name: linkedin-profile-validator
description: Validate and improve a LinkedIn (or other consultant-profile) page against target roles and ATS/recruiter search. Use when the user says "review my LinkedIn", "optimize my profile for recruiters", "does my headline match these roles", "check my profile against this ad", or wants a gap analysis of a professional profile. Produces a section-by-section report with concrete, truthful edits.
---

# linkedin-profile-validator

> Version: 1.0.0 · Part of the `cv-matcher` project.

Reviews a professional profile (LinkedIn, marketplace consultant card, or similar)
against a set of target roles and recruiter/ATS search behavior, and proposes
concrete, truthful improvements.

## Inputs

- The profile content (export, paste, or URL the user provides).
- Target roles / a representative job ad.
- The candidate's CV master (for consistency and to avoid fabrication).

## Checks

1. **Headline & About** - do they surface the Tier 1 terms recruiters search for
   (role, seniority, domain), in the candidate's voice and truthfully?
2. **Skills/keywords** - alignment with `ats-optimizer` Tier 1-2 for the target
   roles; flag missing high-value terms the candidate genuinely has.
3. **Experience** - consistent titles/dates with the CV master; quantified impact
   where available; no claims unsupported by the CV.
4. **Certifications** - precise status. Never label something "certified" when it
   is "trained" or "exam booked".
5. **Consistency** - profile vs CV vs cover letter tell the same story.
6. **Discoverability** - location/remote settings, open-to-work signals, and
   searchable phrasing for the target market.

## Output

A section-by-section report: current state, gap, and a specific suggested edit
for each item. Mark each suggested edit as either "supported by CV" or "needs the
user to confirm".

## Guardrails

- Truthfulness first: surface real strengths; never invent or inflate.
- Respect the user's control over their public presence - propose, do not post.
  Do not notify the user's network or make changes without explicit approval.
