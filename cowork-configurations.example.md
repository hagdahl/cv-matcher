# cowork-configurations (TEMPLATE)

> **Version:** 1.0.0 · **Last updated:** 2026-06-26
> **This is a committed TEMPLATE.** Copy it to `cowork-configurations.md`, which is
> **`.gitignored` and must never be committed.** Create one **per install and per
> environment** -- it is not transferable between machines.

## What this file is

Three layers govern how this project is built and run:

| Layer | File | Character | Public |
|---|---|---|---|
| Rule | `cowork-projektinstruktioner.md` (upstream standard) | Platform-independent principles | yes |
| Pattern | `cowork-tillampningsbilaga.md` (upstream appendix) | Generalized environment behaviors, ranges | yes |
| **Instance** | **`cowork-configurations.md` (your local file)** | **Absolute values for THIS machine** | **no** |

`cowork-configurations.md` holds the concrete instantiation for exactly one
machine: absolute paths to your CV master, applications folders, prompt versions,
and any optional tool endpoints. It contains identifying data and is therefore
local-only. It must contain **no secret values**.

Fill in the sections below on each new install. Delete what does not apply.

---

## 1. Machine / environment baseline

| Property | Value (fill in) |
|---|---|
| OS / shell | e.g. Windows + PowerShell, or Linux + bash |
| Project working copy | `<absolute path to this repo>` |
| Local data disk (`<DATA_ROOT>`) | `<absolute path, NOT on a synced cloud drive>` |

## 2. config.local mapping

Record which `config.example` placeholders you set and to what (no secrets):

```
project_root       = ...
cv_master          = ...   # your consolidated CV / requirements-matrix reference
cv_visual_template = ...   # Word template
ads_root           = ...
applications_root  = ...
pipeline_file      = ...
data_root          = ...   # local disk
```

## 3. Prompt versions in use

| Item | Value |
|---|---|
| Master prompt | `01_docs/standardprompt_v2.md` (version `v2.0`) |
| Archived | `v1.0` |

## 4. Optional external tools

If you wire up an external resume-tailoring tool (see
`01_docs/OPTIONAL_resume_matcher.md`), record its local endpoint here, e.g.
`http://localhost:8000`. Keep the base URL configurable; never hardcode it in
committed files. If that tool is configured with a cloud LLM provider, note that
CV/job text leaves the machine on each call.

## 5. Integrations and secrets

- Record only the **names** of credential-store entries / env vars here, never
  values. Tokens for any connector come from your MCP connector or OS credential
  store.

## 6. Known local quirks

Note anything machine-specific you have already solved (encoding of Swedish
characters, drive-letter drift, Word/COM rendering for the visual CV) so the next
session does not re-solve it.

---

> See the upstream `cowork-projektinstruktioner` project for the full reference
> structure.
