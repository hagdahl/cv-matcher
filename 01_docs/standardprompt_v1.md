# Standard prompt - Job search (v1) - ARCHIVE

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> Archive copy. v2 is current - see `standardprompt_v2.md`.
> Kept for traceability of prompt development.
> Must not be edited (ADR-003).

---

# Standard prompt - Job search

Paste the prompt below into a new assistant conversation, fill in the bracketed fields, and attach or paste the ad text. The prompt assumes the assistant's auto-memory knows the candidate's profile; if not, load the master reference file in the applications folder first.

---

## PROMPT (copy from this line down)

Help me apply for the following job.

**Company:** [COMPANY NAME]
**Position:** [ROLE TITLE]
**Ad link:** [URL]
**Last official application date:** [DATE]
**Rolling handling / the position may be filled earlier:** [YES / NO]
**My own internal deadline for submission:** [DATE - set at least three days before the official deadline, shorter if rolling handling]
**Ad text:** [paste the full text if web retrieval is blocked - otherwise confirm that the URL is accessible]

### Sources in the folder `<APPLICATIONS_ROOT>\`

- Master reference: `cv_master.md` (complete CV timeline, competencies, filled-in requirements matrices, ATS keywords, positioning)
- CV template: `cv_template.docx` (visual style to emulate)
- Pipeline overview: `pipeline.md` in the applications root (create if it does not exist)
- Auto-memory: my profile, handle-with-care areas, project context

### Before you start

- Confirm that you have the ad's full text (ask me to paste it if web retrieval is blocked).
- Create a task list (TodoWrite) so I can see progress.
- If the Chrome MCP is needed to read an SPA-based ReachMee ad or similar: use it.
- Always convert relative dates to absolute before saving in Asana or scheduled tasks.
- Check the pipeline file to see whether I already have an application in with this company or a similar role.
- **Sandbox fallback:** if the Linux sandbox is not working and the .docx cannot be built, deliver in markdown and note that I convert it manually via Word. Markdown is fine for the content - it is the format I convert from, not the final product.

### A. Research and planning

**0. Save the ad text as a file.** Create the subfolder now (see "Files to create" below) and save the ad text in a file `Annons.md` in the subfolder. That way the original material is preserved even when the ad is taken down.

1. **Identify all requirements** in a table. Distinguish between must-have, merit, implicit (sector, culture, technology, reporting structure), and personal traits. **Mark explicitly whether OT/ICS security is relevant for the role** - many industrial, energy, real-estate and installation companies have an OT surface. If OT is relevant: flag it as a potential gap because the candidate's profile lacks deep OT/ICS experience.

2. **Company research beyond the ad.**
   - Latest annual report and quarterly figures (revenue, profitability, growth trend).
   - Management and board changes over the past 12 months.
   - Public security incidents, data breaches, or GDPR fines against the company or industry.
   - Ongoing regulatory processes (financial supervisory authority, data protection authority, civil-contingencies agency) concerning the company.
   - Competitive landscape and the company's strategic priorities.
   - Industry-specific regulatory requirements affecting the role (NIS2, CER, DORA, sector rules).
   - Summarize in at most one page - the things that give an edge in the interview.

3. **Salary research.** Propose a reasonable salary range based on:
   - Swedish salary statistics (lonestatistik.se, sacolonesok.se, union sources)
   - Glassdoor and LinkedIn for comparable roles
   - Sector, location, company size, and seniority
   - Collective agreement if relevant
   - Give a three-point range: lowest, market rate, upper quartile. Note what is included (base salary, bonus, benefits, pension).

4. **Match each requirement against my profile.** Honestly - mark a clear match, a borderline case, or a real gap. For borderline cases: propose how to address them in the cover letter. For gaps: propose whether to address or omit them.

### B. Produce material

5. **Propose a tailored CV** using the visual template as the visual model. Tailor:
   - The heading to the role title and positioning
   - A summary written in the ad's language, ideally with two or three verbatim terms
   - A new skills section (12-14 bullets) that together cover all must-have requirements
   - Reinforce the most relevant assignment with bullet points where each maps to a requirement
   - Correct periods (the template has incorrect dates)
   - CISSP phrasing: always "CISSP Exam Preparation", never "CISSP certified"

6. **Propose a cover letter** with relevant experience and ATS keywords. At most seven paragraphs, ideally five. **The letter must reference at least one finding from the company research** (strategic priority, regulatory situation, market position, or similar) - it shows that I read more than the ad. An opening that mirrors the company's character, two or three paragraphs with concrete evidence, optionally a paragraph addressing the education gap, a paragraph on why this company in particular.

7. **Identify ATS keywords** and show exactly where in the CV and letter they should be placed. Tier 1 (verbatim from the ad), Tier 2 (merit), Tier 3 (domain synonyms), Tier 4 (personality words for the letter/interview). **Flag words I should NOT include** - old terms from previous ads that do not belong here.

8. **Gap analysis** with clear matches (short), real gaps (with handling), implicit requirements (sector, reporting line, technical breadth).

9. **Change log** against the template, line by line.

10. **Urvalsfragor.md is always created** as an empty template in the subfolder, even if I do not know whether the ATS form has screening questions. Add the heading and a note "To be filled in when the ReachMee/other ATS form is opened". Should the ad explicitly show screening questions in advance, write complete answers per question, all starting with "Yes." and in the ad's own words.

### C. Prepare for interview and references

11. **Interview preparation.** Five to ten likely questions with a short answer hint based on my profile. For CISO/leadership roles: a 30-60-90-day plan.

12. **Sharp counter-questions for the interview.** Four to six questions I should ask that signal a deep understanding of the role and give me a basis for deciding.

13. **Reference list and request text.** Propose two or three referees from my profile that fit this particular role. Write the request text in the language the referee works in.

### D. Reminders and follow-up

14. Create an Asana task for submission with my internal deadline.

15. Create a Cowork scheduled reminder at 09:00 local time on the same day as the submission deadline.

16. Create Asana tasks for follow-up (7/14/28 fixed deadline, 3/7/14 rolling, interview -2/+1/+7).

17. Verification step if I later attach the submitted form: read it through and flag typos, overly short answers, or things that were forgotten.

### E. After an offer

18. **Negotiation support on an offer.** Against the salary research, counter-offer on salary/vacation/remote work/competency budget/sign-on/notice/pension, the whole package.

### F. Wrap-up of each run

19. Update the master reference if needed.

20. Update `pipeline.md` with a new row for this application.

---

(other sections identical to the master original)

## END OF PROMPT
