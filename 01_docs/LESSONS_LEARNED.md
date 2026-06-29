# Lessons learned (engineering)

> Version: 1.0.0 · Last updated: 2026-06-30

Engineering lessons from preparing cv-matcher for public release. (Per-track
application lessons are aggregated separately in `LESSONS_LEARNED_aggregerat.md`.)

- **Decouple from third-party projects; keep a recommendation, not a runner.** The
  old Resume-Matcher integration (a runner + scripts pinned to a moving API) was
  removed and replaced by a single optional doc (`OPTIONAL_resume_matcher.md`). A
  bundled runner against someone else's API breaks for other users.
- **Ship logic and prompts, never personal data.** No CV, cover letters,
  references, or real company/contact names in the repo. Data sources are pointed
  to via `config.local` (gitignored); the data structure is documented in
  `SETUP_DATA.md`.
- **Keep the file-naming tokens and the standard prompt structure stable** - they
  are the contract the workflow depends on; translate language deliberately.
- **Truthfulness is a hard rule in the prompts.** Never add logic that fabricates
  experience, certifications, or keywords; distinguish "certified" from
  "trained/exam booked".
- **Cross-repo links must be full URLs once public** - relative paths only work in
  a monorepo.
- **Choose a license before publishing** (MIT here) and publish from a clean
  snapshot so no pre-sanitization history is exposed.
