# USER_GUIDE - cv-matcher

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> Hands-on per B5.

---

## What this project does

Produces complete job applications by running Standard prompt v2 against a given ad. Built on the candidate's CV master and previous lessons.

## Where the data lives

`config.local` - six data sources in cloud storage (CV master, visual template, CV archive, per-track folders, pipeline.md, ad raw data).

## Typical session - new ad -> complete application

### Step 1 - Quickstart

Read `cv-matcher_quickstart.md`. Verify `config.local`.

### Step 2 - Inventory the ad

Locate the ad - either in `ads_root` (ads/) or directly from the user's input. Read the full ad text.

### Step 3 - Run Standard prompt v2

Open `01_docs/standardprompt_v2.md` and follow the 20 steps in order. Produce 6 files in a new per-track folder in `applications_root`.

### Step 4 - Verification

Run `04_tests/validation/promptval_checklist.md`. Fix any warnings.

### Step 5 - Pipeline + Asana

Update `pipeline.md` in the applications root. Create Asana tasks per the standard prompt's follow-up cadence.

### Step 6 - Lessons Learned

Write `YYYY-MM Company Role Lessons Learned v0.1.md` in the per-track folder. Update `01_docs/LESSONS_LEARNED_aggregerat.md` and `01_docs/ATS_keywords_aggregerat.md`.

## Typical session - upgrade v0.x

1. Read the existing files in the per-track folder.
2. Identify what the new information changes (new ad version, new insight, interview feedback).
3. Create new files with a bumped version (v0.1 -> v0.2; v1.0 -> v1.1).
4. Keep the old files for traceability.
5. Update `pipeline.md`.

## Typical session - build the ATS aggregate after a new ad

1. Open `01_docs/ATS_keywords_aggregerat.md`.
2. For each Tier 1-2 term in the new ad's analysis: add a row or bump the frequency.
3. Cite the source per term (which ad it comes from).

## Troubleshooting

### The assistant does not see files that Drive Explorer has

Drive Files On-Demand. Right-click the folder in Explorer, "Always keep on this device".

### Standard prompt v2 fails at step X

Read `01_docs/LESSONS_LEARNED_aggregerat.md` - likely already documented.

### Git complains about a corrupt index

`Remove-Item .git\index; git reset --mixed HEAD`. Pause Drive sync before larger Git operations.

### Encoding errors in PowerShell scripts

See `00_admin/LESSONS_LEARNED.md` "PowerShell scripts + Swedish characters".
