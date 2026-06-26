# Optional integration: external resume-tailoring tool

> **Version:** 1.0.0 · **Last updated:** 2026-06-26 · **Status:** Optional, not required

## Summary

`cv-matcher` is **self-contained**. Its matching logic, ATS keyword bank, and the
`standardprompt_v2` workflow do not depend on any external service.

If you want an extra, automated pass that rewrites a resume against a single job
description, you can optionally plug in an external open-source tool such as
[**srbhr/Resume-Matcher**](https://github.com/srbhr/Resume-Matcher). This is a
**recommendation only** -- nothing in this repository calls it, ships it, or
requires it to be running.

This project previously contained a thin PowerShell "runner" that drove a local
Resume-Matcher backend over HTTP. That coupling was **removed** before public
release because Resume-Matcher is a separate public project with its own
lifecycle, license, and API surface; bundling a runner against a moving API would
break for other users. The notes below are enough to rebuild the integration
locally if you want it.

## How to use it (optional, local-only)

1. Install Resume-Matcher from its own repository and start its backend locally
   (it exposes a FastAPI service, by default on `http://localhost:8000`, API
   prefix `/api/v1`). Follow that project's README -- do not rely on details
   here, which may be out of date.
2. Run the `cv-matcher` workflow as normal to produce a tailored CV and cover
   letter. Treat any Resume-Matcher output as **raw input** for review, not a
   finished deliverable.
3. Always validate the result against `04_tests/validation/promptval_checklist.md`
   before submitting an application. An automated rewrite can drop nuance,
   invent keywords, or weaken the candidate's voice.

## Why it is decoupled

- **Independent lifecycle.** Resume-Matcher's API can change; a pinned runner
  here would silently break.
- **Licensing/distribution.** Keeping it external avoids redistributing another
  project's code under this repository's license.
- **Privacy.** A local Resume-Matcher install may be configured with a cloud LLM
  provider, in which case CV and job text leave your machine on every call.
  Review that tool's configuration before sending real CV content through it.

## If you want to wire it back up

Re-implement a small client in your **local-only** configuration (see
`cowork-configurations.example.md`), keeping it out of version control. A minimal
flow is: health check -> upload resume -> upload job description ->
request improved/tailored output -> save outputs using this project's
per-track naming convention. Keep the endpoint base URL configurable rather than
hardcoded.
