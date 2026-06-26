# Lessons Learned template - per ad track

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> Use this template when creating `YYYY-MM <folder name> Lessons Learned v0.1.md` in a per-track folder.
> The template's purpose is a consistent format so that the aggregate in `cv-matcher\01_docs\LESSONS_LEARNED_aggregerat.md` can be built mechanically.
> When the lessons are lifted to the aggregate, the source must be referenced as SP-NNN (not the company name) per ADR-005.

---

# Lessons Learned - <Company or SP-NNN> <Role>

**Version:** v0.1
**Date:** YYYY-MM-DD
**Track folder:** `YYYY-MM Company Role\`
**Track pseudonym for aggregate:** SP-NNN (per `private/track_index.md`)
**Track status at the time of writing:** [Preparation / Submitted / Invited to interview / Rejection / Offer / Parked]

---

## 1. Track summary

* **Ad type:** Permanent / Consultant / Interim / Staffing
* **Sector:** Government agency / Listed group / Private / Intermediated
* **Reporting line:** CEO / CFO / general counsel / CRO / CIO / other
* **Special flags triggered:** OT/ICS, Unknown end client, Academic degree as a must-have, Specific tools, Current CISO in seat, ...
* **Outcome:** Submitted / Direct contact / Parked / Rejection / ...

## 2. What went well

(Concrete - what succeeded in this run that should be replicated)

## 3. What was sub-optimal

(Concrete - what the assistant session did that should not be repeated)

## 4. What should change in the next run

(Concrete actions for Standard prompt v2 or checklists)

## 5. ATS outcome

| Tier 1 term (verbatim) | In CV? | In letter? | Source row in analysis |
|---|---|---|---|
| ... | yes/no | yes/no | ... |

Tier 2 terms added: ...
Terms that were "carried over from an earlier run" and filtered out: ...

## 6. Gap actions

| Gap | Handling | Outcome |
|---|---|---|
| Master's degree | Equivalent-education phrasing (`private/candidate_profile.md`) | ... |
| OT/ICS | Honest phrasing with a support perspective | ... |

## 7. Handle-with-care hits

(List each time the handle-with-care rule was triggered and how it was handled)

* Certification phrasing correct?
* Title phrasing?
* Societally important?
* Security vetting?

## 8. Technical/process incidents

(Bash was stale, sync placeholders, ATS form clips the PDF, etc.)

## 9. Lessons to lift to the aggregate

For each lesson: category in `LESSONS_LEARNED_aggregerat.md` + a short phrasing to go in there.
**The source reference in the aggregate must be SP-NNN, not the company name.**

| Category in aggregate | Phrasing to insert (source SP-NNN) |
|---|---|
| Ad interpretation | ... |
| Typos and language checking | ... |
| ATS strategy | ... |

## 10. Source files

* `YYYY-MM Company Role Annons v0.x.md`
* `YYYY-MM Company Role Analys och kravmatris v0.x.md`
* `YYYY-MM Company Role CV v0.x.md`
* `YYYY-MM Company Role Personligt brev v0.x.md`
* (and more)
