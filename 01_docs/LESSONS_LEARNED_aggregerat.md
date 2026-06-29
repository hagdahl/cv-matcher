---
name: LESSONS_LEARNED_aggregerat
description: Consolidated list of all per-ad lessons from the application tracks
version: 0.2.0
last_updated: 2026-06-26
scope: 9 tracks (8 active + 1 parked)
next_update_when: a new ad is processed or a pipeline status changes
---

# LESSONS_LEARNED - aggregated

> **Version:** 0.2.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> Cross-cutting lessons from all cv-matcher runs.
> Source files: `YYYY-MM Company Role Lessons Learned v0.1.md` in each per-track folder.
> Track codes in parentheses (SP-NN) refer to the pseudonymized source track per ADR-005.

---

## Categories

* [Deadline handling](#deadline-handling)
* [Ad interpretation](#ad-interpretation)
* [Handle-with-care breaches](#handle-with-care-breaches)
* [Typos and language checking](#typos-and-language-checking)
* [Requirements-matrix patterns](#requirements-matrix-patterns)
* [ATS strategy](#ats-strategy)
* [Phrasing choices](#phrasing-choices)
* [Technical/process incidents](#technicalprocess-incidents)
* [AI-tool usage](#ai-tool-usage)
* [Visual CV conversion](#visual-cv-conversion)
* [Tools and environment](#tools-and-environment)

---

## Deadline handling

* When a formal deadline has passed - apply Standard prompt v2 step -1 (direct contact) rather than skipping the track. The strategy switches to an expression of interest with an honest opening, three experiences in four sentences, and contact info (SP-01).
* The direct-contact strategy must have a time box (suggestion: submission + 14 days without a reply -> archive). Otherwise tracks risk "hanging" indefinitely (SP-01).
* Consultant tracks: a faster follow-up cadence of 3/7/14 days (suits a 1-3 week process) - not the slower 7/14/28 used for permanent employment (SP-04).

## Ad interpretation

* **Unusual reporting line as the first-paragraph hook.** When the reporting line deviates from the norm (general counsel, CFO, CRO) - make it the first-paragraph hook in the cover letter, not a plain mention. The pattern worked for a general-counsel track and a CFO track and should be replicated (SP-01, SP-02).
* **Parallel writing of related regulations.** Write "NIS2 and CER" in parallel when both are triggered by the sector - it is v2 standard and ensures an ATS hit on both terms without exaggerating direct CER implementation (SP-01).
* **Intermediary flag.** On an intermediary track: "Who is the end client?" is ALWAYS the first counter-question. Specific tool names (SailPoint, CyberArk, IEC 62443) must be identified in the FIRST pass of the ad analysis - the risk is drowning in the volume of requirements if identified late (SP-04).
* **Public sector.** A government agency requires a particular salary structure (public-sector pension scheme, no bonus) - mark this in the salary recommendation as the default, not an exception. Add a footnote about pension. When the ad states explicit tone words ("team player, unpretentious") - add a checklist item for the letter read-through (SP-02).
* **Group culture.** For a large group's subsidiaries, the group culture is a recurring special flag that earns plus points for candidates with regulatory/supervisory background (SP-01).
* **LARGE real gap -> go/no-go assessment.** When the ad requires "strong knowledge" in an area where the candidate lacks depth (OT/ICS + IEC 62443; a master's degree): make a formal go/no-go assessment with three criteria (1: does the ad's own wording offer an opening?, 2: are there compensating strengths on the right axis?, 3: is the learning curve reasonable in the first 90 days?) (SP-05, SP-07).
* **Over-qualified positioning.** With 30+ years vs the ad's 2-6 years: position EXPLICITLY to the right level (Manager, not Senior consultant) and highlight mentoring/team development as the value of being over-qualified (SP-06).
* **Role type other than CISO.** For Consultant Manager, Head of Practice, etc.: an EXPLICIT "role-type recalibration" section in the analysis is mandatory. Otherwise the CV/letter risks being angled toward the wrong experience block. For consulting-manager roles, the partner / competence-area-lead experience is the primary match - de-prioritize CISO assignments (SP-10).
* **"Applying for what you already do".** EXPLICIT special flag: handle the angle of longevity/mandate/identification; risks of over-familiarity/reactivity/taking-for-granted/lack of wow factor. SP-08 is the benchmark case.
* **Filter out terms from adjacent tracks.** Discipline: match the role's language, not the candidate's entire tool belt. One public-sector CV had previously been contaminated by terms from a CISO track (CISO/ISMS/NIS2/MSBFS/DORA) that were actively filtered out (SP-08, SP-04, SP-10).
* **Parking requires decision documentation.** When a track is parked: document an EXPLICIT decision point (why, who, date, any reactivation condition) - otherwise institutional memory is lost. SP-09 is the benchmark case for missing decision documentation.

## Handle-with-care breaches

* **CISSP phrasing.** One letter is the BENCHMARK: "CISSP Exam Preparation (2021)" - use as the template in all tracks. Never "CISSP certified". A requirements-matrix section 4 is the source of the rule (SP-01, SP-08, SP-02, SP-06).
* **Internal-auditor phrasing.** "Audit-adjacent review", "compliance review", or "can work according to internal-audit methodology". Never "internal auditor" as a title. Use verbatim in all tracks where internal audit is triggered (SP-01, SP-08).
* **Societally important.** Safe to mirror if the employer itself states it is societally important in the ad. Otherwise: fact-based ("critical infrastructure", "society-critical role") - applies e.g. to companies that deliver TO societally important infrastructure but are not it themselves (SP-01, SP-05, SP-08).
* **Security vetting.** Standard phrasing: "Security-vetted in previous assignments and a conscript crypto technician. Available for renewed or deeper vetting." Never "security-classified person" (SP-02, SP-08).
* **A requirements-matrix section 4 is the BENCHMARK for the "handle with care" section in all tracks.** Replicate the 4-point structure (CISSP, internal auditor, security vetting, societally important) as a mandatory part of the analysis template (SP-01).

## Typos and language checking

* "Strategisk" is spelled with an R - reminder from a v1.1 interview preparation (SP-08).
* CV date consistency: two factual date overlaps were found and corrected (one assignment "May 2022 - ongoing" -> "May 2022 - Feb 2024"; another "Nov 2020 - Jun 2022" -> "Dec 2018 - Oct 2019"). Add a DATE consistency check as a mandatory quality-assurance step (SP-08).
* Other tracks: explicit typo/language checking not documented - should be filled in by the candidate when reading the submitted version. (Generally: this category is under-documented in this round.)

## Requirements-matrix patterns

* **Complete template:** ATS table + salary research + company research beyond the requirement match + 30-60-90-day plan + counter-questions. The v2 standard prompt has all of these sections as mandatory - if they are missing (as in a requirements matrix from an old run) they must be completed on reactivation (SP-09).
* **Win conditions explicit.** The requirements matrix must cover all must-have requirements + all merits with concrete evidence. One requirements matrix (12 must-have + 3 merit) is an example - the outcome was an interview invitation (SP-08).
* **Handle-with-care section (section-4 format).** Replicate the pattern: CISSP / internal auditor / security vetting / societally important as four explicit points (SP-01).
* **Change log.** On a version bump (v0.1 -> v0.2): replicate critical sections (change log, 30-60-90) rather than just referring to the previous version. Make the file self-contained (SP-09).

## ATS strategy

* **One ATS table is the BENCHMARK format:** explicit Tier 1 + Tier 2 + CV placement + letter placement per keyword. Use as the template for all tracks (SP-01).
* **Tool gap (the candidate lacks depth).** Standard phrasing (v2): "My experience lies in [adjacent tool]. [Tool] specifically I have not worked with, but the governance perspective at the CISO level is well known. If the assignment requires deep platform administration I am not the right person; if it is about governing, quality-assuring, and further developing [the area], I am." Use for SailPoint, CyberArk, etc. (SP-04).
* **Technical tool/standard gap in Tier 1.** Take the term into ATS Tier 1 but mark it "with an honest maturity level" - so the ATS scanner hits it without the candidate exaggerating. Applies to IEC 62443, OT/ICS (SP-05, SP-07).
* **OT/ICS as a real gap.** Use the v2 standard phrasing verbatim (honest + highlight IT/OT interface + supplier governance + security by design); mention IEC 62443 in the skills section with an honest maturity level, but never in the CV heading or summary (SP-05, SP-07).
* **Direct contact de-prioritizes ATS density.** On direct contact: the content goes to humans - shift focus to clarity and four-sentence discipline (SP-01).
* **Financial sector: DORA in Tier 1.** Handle direct implementation honestly (a TPRM proxy is a conceptual parallel, not direct experience) (SP-02, SP-03, SP-04).
* **Role types other than CISO: actively FILTER OUT** CER, OT/ICS, IEC 62443, DORA, NIS2-heavy phrasings that are irrelevant. Include leadership/business/coaching terms instead (SP-10).
* **Management-consultant roles:** GRC, frameworks, regulatory requirements, business resilience are Tier 1 ahead of technology-heavy terms (SOC, SIEM, etc.) (SP-07).
* **Government agency:** data-protection law/OSL/archive law as Tier 1/2 - often missed in CISO templates, mark explicitly as "raised for the public sector" (SP-08).

## Phrasing choices

* **"I hope this combination carries weight" -> "My assessment is that this combination constitutes an equivalent foundation for the role".** Assertive without arrogance (SP-07).
* **Salary recommendation on a stretch hire:** give a triple range (opening request + negotiation range + lowest accept) rather than a single figure (SP-07).
* **Bonus-heavy employers** (consulting firms): negotiate on the upside (commission, delivery bonus) rather than base salary (SP-10).
* **Fee strategy for a consultant track without a known end client:** a range (1,600-1,800 SEK/h) + sector-dependent adjustment (bank -> up, insurance -> mid, public -> down) (SP-04).
* **Likely-interview-question section** must be based on the company's actual context - avoid speculative comparisons that have no basis in the ad or the company's history (SP-05).
* **Equivalent-education phrasing** on a hard master's-degree requirement: a complete block (education timeline + existing certifications + a concrete reference to the ad's "determined based on background" wording if present). Outcome on one track: invited to interview -> the phrasing was accepted (SP-07, SP-08).

## Technical/process incidents

* Generally under-documented in this round - only one track notes the risk that a direct-contact email may be filtered as spam -> it should be sent in parallel via LinkedIn (SP-01).
* One track notes Teamtailor ATS as a potential field limitation to check (SP-06).
* One track notes a required reference code in their ATS (SP-07).
* **Action:** on future runs - explicitly document any Drive placeholders, stale bash, ATS-PDF clipping, or portal-specific limitations under "Technical/process incidents" in the lessons file.

## AI-tool usage

* No consistent lessons distilled from this round - to be filled in next run. (Standard prompt v2 is the AI tool's primary governing document; any friction between AI output and the candidate's voice should start being logged in upcoming lessons files.)

## Visual CV conversion

* No consistent lessons distilled from this round - to be filled in next run. (PDF appearance, page breaks, and heading formatting should start being logged in upcoming lessons files when word->pdf export happens.)

## Tools and environment

* **Naming convention v2:** `YYYY-MM Company Role <document type> v0.x.md`. Some files still use the old convention - convert to the new convention on reactivation (SP-01, SP-08).
* **Version-bump routine:** v0.1 -> v0.2 should replicate critical sections in the file (change log, 30-60-90) rather than referring back - so the files are self-contained if v0.1 is archived (SP-09).
* **Interview-preparation template (one v1.1).** 10-section structure: angle, "why are you applying", future vision 3-horizons, personal traits with concrete examples, work-psychology test, security vetting, likely questions, counter-questions, practical pre-day prep, prepared thank-you email. Benchmark for the portfolio (SP-08).
* **LinkedIn research on the reporting manager** should be a standard checklist, not ad hoc (SP-10).
* **"Current CISO via LinkedIn" verification before submission.** Today only the action is noted, not the result. Add a timestamp + optional screenshot as a mandatory outcome (SP-02, SP-05, SP-08).

---

## Suggested extra category (for future bootstrap)

* **Verification chain** - all tracks noted a lack of documented outcome for LinkedIn/CISO verification, lead-implementer status, and tool status. Add as its own category in Standard prompt v2 with a standardized verification stamp (date, source, outcome).
* **Follow-up cadence** - one track introduced the consultant-track cadence (3/7/14 d) and another introduced the direct-contact time box (14 d). Worth its own category.

---

## Update routine

On each new cv-matcher run that produces a `Lessons Learned` file:

1. Read the new per-ad file.
2. For each lesson: identify the category (create a new one if needed).
3. Add the lesson with a source reference to the track + date.
4. Bump `last_updated` in the frontmatter.
