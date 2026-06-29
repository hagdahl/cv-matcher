---
name: interview-prep
description: Prepare for an interview for a specific role. Use when the user says "interview prep", "förbered inför intervju", "likely questions for this job", or a track reaches the interview stage. Generates likely questions with evidence-backed answers and questions to ask the employer.
---

# interview-prep

> Version: 1.0.0 · Part of the `cv-matcher` project.

Turns the ad + CV master into a focused interview brief.

## Output

1. **Likely questions** derived from the ad's must-haves and the role
   (competency, scenario/STAR, and role-specific technical questions).
2. **Evidence-backed answers** drawn from the CV master - concise STAR notes, real
   examples, quantified impact where available.
3. **Gaps to handle** - how to address requirements the candidate only partially
   meets, honestly.
4. **Questions to ask** the employer (scope, team, success criteria, security
   posture for infosec roles).

## Guardrails

- Ground every answer in real experience from the CV master; never coach
  fabrication.
- Keep notes the candidate can deliver in their own voice, not a script to recite.
