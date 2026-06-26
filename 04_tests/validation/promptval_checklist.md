# Prompt validation - verification checklist after a cv-matcher run

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> A4 (verification before reporting "done"). Run after every cv-matcher run that produces new or updated per-track material.

---

## 11-item checklist

### 1. Deadline

* Is the deadline in the ad verified against today's date?
* Is the deadline in `pipeline.md`?
* Has an "Own deadline" been set if "Last application date" is rolling/unspecified?

### 2. Folder and file naming standard

* Is the per-track folder named `YYYY-MM <Company> <Role>`?
* Are all 6 files produced (Annons, Analys, CV, Brev, Urvalsfragor, Referenser)?
* Version suffix `v0.x` on all files?
* No spaces or special characters that break Glob?

### 3. CV-master consistency

* Do all employment years/dates in the per-track CV match the CV master?
* No "improved" claims that are not in the master?

### 4. Handle-with-care breaches

Search the CV + letter for the following exact strings - they must not appear (Swedish source tokens kept verbatim):

* `CISSP-certifierad`, `CISSP certifierad`, `certifierad CISSP` (and English: `CISSP certified`)
* `Internrevisor` (without the context "kan arbeta enligt internrevisionsmetodik")
* `prisnotering`, `timpris`, `dagspris` (internal hourly/day rates)

### 5. Typos and language checking

* Search for recurring misspellings: `Stategisk`, `Strateegi`, `Strategiskt managementkonsult`
* Search for `informationsäkerhet` (one s - wrong) vs `informationssäkerhet` (correct)
* Consistent upper/lower case in abbreviations (ISO 27001, NIS2, DORA, GDPR)

### 6. ATS coverage

* Are all Tier 1 keywords from the analysis in both the CV and the letter?
* Tier 2 in at least one of CV/letter?
* Aggregate (`ATS_keywords_aggregerat.md`) updated?

### 7. Letter structure check

* Does the opening connect to the ad (not generic)?
* Block structure: background -> four blocks -> handle-with-care phrasings -> culture connection -> practical -> closing?
* At most 1 page (unless otherwise stated)?

### 8. Pipeline update

* Does `pipeline.md` have a row for this track?
* Status, next action, next date, folder name filled in?

### 9. LLM/AI output integrity

* If anything was generated with an LLM call: is the stop reason checked (not truncated mid-word)?
* No "..." or interrupted sentences in the delivered files?

### 10. References and links

* Do external links work (the ad's URL, the company's contact)?
* References with the correct role title and contact details?

### 11. Lessons Learned

* Lessons Learned file created for this track?
* Aggregate (`LESSONS_LEARNED_aggregerat.md`) updated?

---

## Reporting template

After the checklist, write a short status report:

```
## Verification report - <track>, <date>

* Item 1 (deadline): OK / YELLOW: <short>
* Item 2 (file names): OK
* Item 3 (CV master): OK
...
* Summary: <X/11 OK, Y YELLOW, Z RED>
* Actions: <what needs fixing before submission>
```

RED = blocking for submission. YELLOW = nice-to-fix but not blocking. OK = green.
