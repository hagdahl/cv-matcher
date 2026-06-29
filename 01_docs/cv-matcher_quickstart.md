# cv-matcher Quickstart

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> For a new assistant session picking up the work without memory.

---

## What this project is

cv-matcher produces complete job applications by running Standard prompt v2 against ads. The data stores live in cloud storage and are pointed to via `config.local`.

## First step in a new session

1. **Read `README.md`** - overview and data sources.
2. **Read `config.local`** - where the data sources point now.
3. **Read `01_docs/LESSONS_LEARNED_aggregerat.md`** - what we learned from 9 previous tracks.
4. **Read `pipeline.md`** in the applications root - what is active right now.

## Second step - what the user wants to do

Ask the user which of the following:

* **New ad -> run v2** - the user provides the ad, you produce 6 files.
* **Upgrade an existing track** - the user points to a track, you bump the version.
* **Lessons learned from a track** - the user wants to distill lessons from a track.
* **Pipeline check** - the user wants to know what needs action.
* **ATS aggregate update** - the user wants to see which terms have come up in multiple ads.

## Things-to-know lists

### Handle with care (from GLOSSARY.md)

* CISSP: never write "CISSP certified" - only "CISSP Exam Preparation".
* Internal auditor: "audit-adjacent review" or "can work according to internal-audit methodology".
* Critical societal operations: check what the ad itself says.
* Security vetting / security clearance: mention only if relevant.
* Internal hourly-rate notes: must never end up in client-facing versions.

### Ad-type flags (v2 special flags)

* OT/ICS role (Operational Technology / Industrial Control Systems)
* Reporting line (CISO -> CIO vs CISO -> CEO vs CISO -> Risk)
* Unknown end client (intermediated consulting assignment with no named client)
* Academic degree required (the candidate lacks a master's degree)
* Specific tools (if the ad requires named products)
* Current CISO (if the candidate would replicate a CISO role already filled)

### Versioning convention

* v0.1, v0.2, ... = drafts under development
* v1.0 = submitted
* v1.1, v1.2, ... = after submission (ahead of interview)
* v2.0 = major rework

### File types per track

Annons, Analys och kravmatris, CV, Personligt brev, Urvalsfragor, Referenser, Lessons Learned.

## Verification before reporting "done"

Run `04_tests/validation/promptval_checklist.md`.

## Common cases

### Drive Files On-Demand makes Glob blind

Ask the user to right-click the folder in Explorer -> "Always keep on this device".

### Bash cannot see Drive files

Use the assistant's Read/Write/Glob (Windows API) instead.

### PowerShell + Swedish characters break

See `00_admin/LESSONS_LEARNED.md`. Use ASCII-only code + UTF-8 data files with `-Encoding UTF8` in Get-Content.
