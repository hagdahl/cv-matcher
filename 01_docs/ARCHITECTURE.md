# ARCHITECTURE - cv-matcher

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> Architecture analysis per B1.

---

## 1. Goal

Produce complete job applications (CV, cover letter, requirements matrix, screening answers, references, lessons learned) tailored per ad, based on the candidate's CV master and a versioned master prompt. The data stores are external; this project owns the logic.

**Use cases:**

1. **New ad -> complete application** - run Standard prompt v2, produce 6 files in a new per-track folder.
2. **Ongoing track -> upgrade** - bump v0.x -> v0.x+1 based on new information.
3. **Submitted application -> lessons learned** - distill lessons into a per-ad file + update the aggregate.
4. **Cross-track comparison** - use the ATS aggregate to prepare new ads faster.

---

## 2. Core components

```text
+----------------------------------------------------------------+
| Data sources (untouched, via config.local)                     |
|  - CV master + visual template (applications root)             |
|  - Per-track folders (applications/YYYY-MM ...\)               |
|  - pipeline.md (applications root)                             |
|  - Ad raw data (ads/)                                          |
+-------------------------+--------------------------------------+
                          |  (read in assistant session)
                          v
+----------------------------------------------------------------+
| Standard prompt v2 (01_docs/standardprompt_v2.md)              |
|  20-step process:                                              |
|  1.  Sanity check (deadline, scope, scan screen)               |
|  2-3. Ad retrieval + parsing                                   |
|  4-6. Requirements table + special flags + company research   |
|  7-8. Salary research + ATS keywords                          |
|  9-10. Gap analysis + change log                              |
|  11-13. CV + cover letter + screening answers                 |
|  14-15. References + Asana follow-up                          |
|  16-18. Pipeline update + verification + lessons learned      |
|  19-20. Delivery + handover                                   |
+-------------------------+--------------------------------------+
                          |  (output)
                          v
+----------------------------------------------------------------+
| Per-track folder in applications/                              |
|  6+1 files:                                                    |
|  - YYYY-MM Company Role Annons v0.x.md                         |
|  - YYYY-MM Company Role Analys och kravmatris v0.x.md          |
|  - YYYY-MM Company Role CV v0.x.md                             |
|  - YYYY-MM Company Role Personligt brev v0.x.md                |
|  - YYYY-MM Company Role Urvalsfragor v0.x.md                   |
|  - YYYY-MM Company Role Referenser v0.x.md                     |
|  - YYYY-MM Company Role Lessons Learned v0.x.md (after)        |
+-------------------------+--------------------------------------+
                          |  (updates)
                          v
+----------------------------------------------------------------+
| Aggregates in cv-matcher\01_docs                               |
|  - LESSONS_LEARNED_aggregerat.md (cross-cutting)               |
|  - ATS_keywords_aggregerat.md (frequency per term)            |
+----------------------------------------------------------------+
```

---

## 3. Data sources

All read via the assistant's Read/Glob (Windows API). No writes to `ads/` (that is the `jobb-bevakning` project's domain via shared config).

**Write destinations:**

* Per-track folders in `applications/YYYY-MM ...\` (new files + Lessons Learned).
* `pipeline.md` in the applications root (one pipeline row per track).
* `01_docs/LESSONS_LEARNED_aggregerat.md` and `01_docs/ATS_keywords_aggregerat.md` (updated on each track).

---

## 4. Risks

| ID | Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|---|
| R-01 | Incorrect CV angling (under- or over-representation of a competency) | Medium | High | Standard prompt v2 has Section D verification checklist; promptval_checklist.md runs in Phase 6 of every run |
| R-02 | Typo in a submitted application (incident May 2026 - "Stategisk") | Medium | Medium | Standard prompt v2 step 18: explicit spell check against "Strategisk", "Strategiskt", "Strategi" and other commonly misspelled words |
| R-03 | Handle-with-care breach (e.g. "CISSP certified") | High (if unchecked) | High | GLOSSARY.md "Handle-with-care list"; promptval_checklist.md item 4 |
| R-04 | Outdated ad version processed (<REDACTED> incident: deadline passed) | Medium | High | Standard prompt v2 step 1: deadline sanity check (deadlines against today's date) |
| R-05 | Drive mount view stale -> file not read | High (known B14) | Medium | Use Glob/Read via Windows API, not bash |
| R-06 | Cross-version mixing (v1 file used for a v2 track) | Medium | Medium | `config.local [prompt] master_prompt_path` - explicit choice per run |
| R-07 | LLM output truncated mid-word (without noticing) | Medium | High | A4: read the API response's stop_reason; promptval_checklist.md item 9 |

---

## 5. Inputs and outputs

**In:** Ads (PDF, DOCX, HTML, .url), CV master (markdown), previous per-track files.

**Out:**

* Per-track folder with 6-7 markdown files.
* Updated `pipeline.md`.
* Updated aggregates (lessons + ATS).
* Optionally a Word conversion of the visual CV (outside this project's scope - manual via template).

---

## 6. Choice of data storage

* Project root (logic): synced cloud storage, traceability via Git.
* Pipeline state (cache): `<DATA_ROOT>` (local, not synced - A3/B1).
* All product data (per-track files): synced cloud storage (where it belongs).

---

## 7. Choice of automation

* v0.1: manual - an assistant session drives Standard prompt v2 step by step.
* v0.2: possible scheduling of aggregate updates and a pipeline-gap report.
* Escalation to Python is not justified at the current scope (B11).

---

## 8. Verification method (A4)

Per run: `04_tests/validation/promptval_checklist.md` with 11 items (typos, handle-with-care breach, ATS coverage, etc.).
