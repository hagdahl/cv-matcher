# Standard prompt - Job search (v2)

> **Version:** 0.1.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> Master prompt for cv-matcher. Versioned - this file is an archive copy of the master as of 2026-05-31.
> The original still lives in `<APPLICATIONS_ROOT>\standardprompt_v2_source.md` (the source of truth during the transition period; future bumps are made here).

Paste the prompt below into a new assistant conversation, fill in the bracketed fields, and attach or paste the ad text. The prompt assumes the assistant's auto-memory knows the candidate's profile; if not, load the master reference file in the applications folder first.

**Changelog v1 -> v2** (lessons from several earlier tracks and one preparation track):

- **Deadline check as step -1** (one ad had already passed when we ran it - wasted work)
- **Ad-type marker** early: Permanent / Consultant / Interim / Staffing - drives salary, lead time, letter angle, and follow-up cadence
- **Reporting-line check** (CFO, general counsel, CRO, CIO, CEO) - signals where the role sits on the risk/compliance/technology axis
- **End-client question for intermediary** assignments (one track showed the end client is often unknown via a middleman)
- **IEC 62443 included** in the OT flag
- **Specific-tools strategy** (SailPoint, CyberArk, etc.) - address without lying
- **Equivalent-education phrasing** standardized (the candidate lacks a university degree)
- **Consultant hourly-rate research** for consulting assignments (instead of monthly salary)
- **Typo verification** explicit before submitting an ATS form
- **Complete education answer** for an ATS education question (not just one course)
- **Faster follow-up cadence** for consulting assignments (3/7/14 instead of 7/14/28)
- **Year-version mix-up:** check that we are reading the correct year's version if the folder contains several

---

## PROMPT (copy from this line down)

Help me apply for the following job.

**Company:** [COMPANY NAME]
**Position:** [ROLE TITLE]
**Ad link:** [URL]
**Ad type:** [PERMANENT / CONSULTING ASSIGNMENT / INTERIM / STAFFING via intermediary]
**Last official application date:** [DATE]
**Rolling handling / the position may be filled earlier:** [YES / NO]
**My own internal deadline for submission:** [DATE - set at least three days before the official deadline, shorter if rolling handling or a consulting assignment]
**Ad text:** [paste the full text if web retrieval is blocked - otherwise confirm that the URL is accessible]

### Sources in the folder `<APPLICATIONS_ROOT>\`

- Master reference: `cv_master.md`
- CV template: `cv_template.docx`
- Pipeline overview: `pipeline.md` in the applications root (create if it does not exist)
- Auto-memory: my profile, handle-with-care areas, project context

### Before you start - checks (do in this order)

**-1. Deadline sanity check.** Is today's date after the official deadline? If YES, switch directly to "direct-contact strategy": formulate an expression of interest to the hiring manager instead of a formal application. Create only Annons.md, a short Analys, and a Personligt brev - skip the CV tailoring and formal process until the ad reopens.

**0. Ad-text check.**
- Do you have the full ad text? If I only have a link: try web retrieval, then WebSearch, then the Chrome MCP (for Teamtailor/ReachMee SPAs).
- If the ad folder contains multiple versions (e.g. one folder had both a 2023 and a 2026 version): confirm which version is to be processed.
- Save the ad text in the subfolder as the first file (`Annons v0.1.md`).

**1. Sandbox fallback.** If the Linux sandbox is down and the .docx cannot be built: deliver in markdown. The candidate converts it manually via Word.

**2. Pipeline check.** Check `pipeline.md` to see whether I already have an application in with this company or a similar role. Prevent duplicates.

**3. Task list.** Create a TodoWrite so the candidate can see progress.

**4. Convert relative dates** to absolute before anything is saved in Asana or scheduled tasks.

### A. Research and planning

**0. Save the ad text as a file** (`Annons v0.1.md` in the subfolder - create the folder now per "Files to create" below).

**1. Identify all requirements** in a table. Distinguish between must-have, merit, implicit, and personal traits.

**Special flags to mark explicitly in the requirements table:**

- **OT/ICS security:** Is this relevant for the role? Industrial network, power company, building technology, installation, production, transport. If YES: flag it as a potential real gap (the candidate's profile lacks deep direct OT/ICS experience) and mention IEC 62443 explicitly. Be honest about the gap in the letter - do not try to hide it.
- **Reporting line:** Who does the role report to? CFO, general counsel, CRO, CIO, CEO, COO, legal line. This signals where the role sits on the risk/compliance/technology axis and drives the letter's angle. CFO/general counsel -> compliance-heavy. CRO -> enterprise risk. CIO -> technology-heavy. CEO/COO -> strategic business.
- **Specific tools that I do not have deep direct experience with** (SailPoint, CyberArk, IEC 62443, etc.): mark them and plan "honest handling" in the letter and interview preparation.
- **Academic degree as a must-have:** If the role requires "relevant university education or equivalent experience" - mark it. The letter must address it with the standard phrasing (see template in step 6).
- **Unknown end client (staffing/intermediary):** If a staffing agency is involved - mark that the end client should be asked for in the first call.

**2. Company research beyond the ad.**
- Latest annual report and quarterly figures.
- Management and board changes over the past 12 months.
- **Who is the current CISO/security manager?** Check LinkedIn, The Org, Crunchbase. If someone is already in the seat: is the role an expansion or a replacement?
- Public security incidents, data breaches, or GDPR fines against the company or industry.
- Ongoing regulatory processes (financial supervisory authority, data protection authority, civil-contingencies agency) concerning the company.
- Competitive landscape and strategic priorities.
- Industry-specific regulatory requirements (NIS2, CER, DORA, IEC 62443, sector rules).
- Summarize in at most one page - the things that give an edge in the interview.

**3. Salary/fee research.** Adapt to the ad type:

- **Permanent:** Salary statistics (lonestatistik.se, sacolonesok.se, Glassdoor, LinkedIn). Three-point range: lowest, market rate, upper quartile. Note base salary, bonus, benefits, pension. Public-sector roles: note that a bonus is usually absent.
- **Consulting assignment or interim:** Hourly rate (Cinode statistics, market data). Senior CISO consultant in Sweden: 1,500-2,200 SEK/h. Intermediaries take a 15-25% margin. Calculate the 6-month value: hourly rate x 40 x 4 x 6.
- **Staffing via intermediary:** The end client typically pays 15-25% above your fee.

**4. Match each requirement against my profile.** Honestly - mark a clear match, a borderline case, or a real gap. For borderline cases: propose how to address them in the letter. For gaps: propose whether to address or omit them.

### B. Produce material

**5. Propose a tailored CV** using the visual template as the visual model. Tailor:

- The heading to the role title and positioning
- A summary written in the ad's language, ideally with two or three verbatim terms
- A new skills section (12-14 bullets) that together cover all must-have requirements
- Reinforce the most relevant assignment with bullet points where each maps to a requirement
- Correct periods (the template has incorrect dates)
- CISSP phrasing: always "CISSP Exam Preparation", never "CISSP certified"

**For a consulting assignment:** Adjust the CV to the consulting format - shorter (1-2 pages optimal), focus on delivery results rather than hierarchy, highlight fast-start capability.

**6. Propose a cover letter** with relevant experience and ATS keywords. At most seven paragraphs, ideally five. **The letter must reference at least one finding from the company research** (strategic priority, regulatory situation, market position).

**Standard phrasings to use when relevant:**

- **Equivalent education** (if the ad requires an academic degree): "My educational background is not a traditional academic degree in [the area], but the ad leaves room for education that [the company] judges to be equivalent. My foundation is 30+ years in the IT industry, of which more than 15 years continuously within information security and IT governance, combined with executive-education programs and continuous further training: strategic information security, third-party risk management, ISO/IEC 27001, CISSP Exam Preparation, ITIL v3 Intermediate, SAFe 5 Agilist, and Prosci Change Practitioner."

- **OT/ICS gap (when relevant):** "My direct experience of OT/ICS security is limited - the closest is cybersecurity validation team work that touched on the area. It is an area I get up to speed on quickly and build up with the support of OT specialists in the organization."

- **Specific-tool gap (SailPoint, CyberArk, etc.):** "My IGA experience lies in Azure AD and SAP IdM. [Tool X] specifically I have not worked with deeply, but the governance perspective at the CISO level is well known. If the assignment requires deep platform administration I am not the right person; if it is about governing, quality-assuring, and further developing the program, I am."

**For a consulting assignment:** Shorter letter (3-4 paragraphs). Highlight fast-start capability, delivery evidence, previous CISO-function experiences.

**7. Identify ATS keywords** and show exactly where in the CV and letter they should be placed. Tier 1 (verbatim from the ad), Tier 2 (merit), Tier 3 (domain synonyms), Tier 4 (personality words for the letter/interview). **Flag words I should NOT include** - old terms from previous ads that do not belong here.

**8. Gap analysis** with clear matches (short), real gaps (with handling), implicit requirements (sector, reporting line, technical breadth).

**9. Change log** against the template, line by line.

**10. Urvalsfragor.md is always created** as a template. Add:

- The heading "To be filled in when the ATS form is opened"
- A list of likely questions based on the ad's must-have and merit requirements
- Prepared backup answers in short form

**Standard answer for the "education within the field" question** (lesson learned: the candidate once answered only with a single course name):

> I have completed strategic information security (2026), third-party risk management (2026), ISO/IEC 27001 (2018), CISSP Exam Preparation (2021), ITIL v3 Intermediate, SAFe 5 Agilist, and Prosci Change Practitioner, plus executive-education programs in insurance mediation and underwriting. Altogether an educational foundation that I judge to be equivalent per the ad's wording, combined with 30+ years in the IT industry and 15+ years continuously within information security.

**Note in particular:** Never write just a single course or just one program name - it comes across as too thin. Always list the whole picture.

**Spell check** (lesson learned): Before the candidate pastes answers into an ATS form, read the answers through yourself and flag: typos, overly short answers, missing words. Suggest a spell check.

### C. Prepare for interview and references

**11. Interview preparation.** Five to ten likely questions with a short answer hint based on my profile. For CISO/leadership roles: a 30-60-90-day plan (or 100-day/first-quarter, depending on the role type).

**For an intermediated consulting assignment:** Include the question "Who is the end client?" explicitly as the first counter-question.

**12. Sharp counter-questions for the interview.** Four to six questions that signal a deep understanding of the role. Cover: mandate and escalation path, budget and resources, the next 12 months in the organization, culture markers, how success is measured, why now.

**Standard counter-questions that are often valuable:**
- Is the current CISO/security manager known? Is this role an expansion or a replacement?
- What is the driver behind the role being advertised right now - regulation, an incident, an organizational change?
- What does the interplay look like between the CISO and [general counsel / CFO / CRO / CIO / CEO]?

**13. Reference list and request text.** Propose three referees from my profile. For each: justify, point out the angle, write a short request text.

**Standard profiles:**
- **Referee 1 (current CISO function):** a manager or coordinator from a recent public-sector assignment - Swedish
- **Referee 2 (global group and third-party risk):** a contact from a global-group assignment - English
- **Referee 3 (financially regulated / management role):** a partner from the insurance market or a finance-regulated engagement - Swedish

**Language matching:** Write the request text in the language the referee works in.

### D. Reminders and follow-up

**14. Create an Asana task for submission** with my internal deadline.

**15. Create a Cowork scheduled reminder** at 09:00 local time on the same day as the submission deadline.

**16. Create Asana tasks for follow-up.** The cadence depends on the ad's character:

**Fixed official deadline (no rolling handling):**
- Submission + 7 days - check whether a confirmation was received
- Submission + 14 days - friendly reminder to the recruiter
- Submission + 28 days - status update or close

**Rolling handling or consulting assignment:**
- Submission + 3 days - check whether a confirmation was received
- Submission + 7 days - friendly reminder
- Submission + 14 days - status update or close

**Interview-related (set when an interview date is booked):**
- Interview - 2 days - own interview preparation
- Interview + 1 day - thank-you email (write the finished text in the Asana task, paste-ready)
- Interview + 7 days - follow up if the decision is delayed

**17. Verification step if I attach the submitted form** (PDF or screenshot): read it through and flag typos, overly short answers, or things that were forgotten. Lesson learned: check in particular fields that get cut off in the PDF view.

### E. After an offer

**18. Negotiation support on an offer.** When I attach an offer, break it down:

- Against the salary/fee research from item 3 - where does the offer sit?
- For permanent employment: salary, bonus, vacation, remote/hybrid, competency budget, sign-on bonus, notice period, pension, LTI.
- For a consulting assignment: hourly rate, billing model (full/part), extension clauses, notice period, possible back-to-back option with the end client.
- Assess the whole package, not just base salary/hourly rate.
- Propose a tone and a first reply I can paste in.

### F. Wrap-up of each run

**19. Update the master reference if needed.** If the application or research reveals that the master reference file is out of date - e.g. a new assignment completed, a new certification, a new ATS keyword category - note the change explicitly in the wrap-up summary.

**Lesson learned: CER was added after one run. IEC 62443 should be added after the OT-related run.**

**20. Update `pipeline.md`** in the applications root with a new row: company, role, ad type, last official application, own deadline, status, next action, next date, folder name, latest CV and letter version. This is done as the LAST step.

---

### Files to create

Create a **subfolder** in `<APPLICATIONS_ROOT>\` with a name in the format:

```
YYYY-MM Company Role
```

Example: `2026-05 <REDACTED> CISO`.

In the subfolder, save files following the pattern:

```
YYYY-MM Company Role [FileType] vX.Y.md
```

**Versioning convention:**
- `v0.1`, `v0.2`, `v0.3` ... - drafts under development (default start version **v0.1**)
- `v1.0 (submitted YYYY-MM-DD)` - the actually submitted version
- `v1.1`, `v1.2` - minor updates after submission
- `v2.0` - major rework

**Always create a new file with a new version number on revision** - do not overwrite the old version.

File types:

- `Annons v0.1.md` - raw copy of the ad text (step 0)
- `Analys och kravmatris v0.1.md` - requirements table (with special flags: OT, reporting line, specific tools, end client), company research, salary/fee research, ATS keywords, gap analysis, change log, interview preparation and counter-questions
- `CV v0.1.md` - tailored CV
- `Personligt brev v0.1.md` - tailored letter (references at least one research finding)
- `Urvalsfragor v0.1.md` - template with likely questions and backup answers
- `Referenser v0.1.md` - proposed referees and request texts in the correct language
- `Forhandlingsstrategi v0.1.md` - created only when an offer arrives (step 18)
- `Lessons Learned v0.1.md` - after submission or interview (for the cv-matcher aggregate)

**With the direct-contact strategy** (deadline passed): create only Annons, a short Analys, and a Personligt brev (with variant A formal + variant B direct-contact text to the hiring manager).

---

### Overall work process

**Pipeline view.** Maintain `pipeline.md`. Per row: company, role, **ad type**, last official application, own deadline, latest CV and letter version, submitted version, submission date, status, next action, next date, folder name.

**CV versioning** (unchanged):
- The master is the source of truth, changed only when actual things happen.
- The visual CV is the visual template, not changed per application.
- For each application: a new tailored version in the subfolder.
- Revised version = a new file with a higher version number.
- Submitted version: a copy to `v1.0 (submitted YYYY-MM-DD).md`.

**Calendar and timing support:**
- With 2+ parallel applications: propose an order based on deadline, rolling handling, lead time.
- Flag conflicts with an interview in the same week.
- Hold-the-line strategy on an early offer.
- **Consulting assignments do not wait** - lead time is 1-3 weeks, not 1-3 months. Adjust the pace.

---

### Handle with care (known from auto-memory)

- **CISSP:** never write "CISSP certified" (only exam prep)
- **Internal auditor:** use "audit-adjacent review"
- **Critical societal operations:** check what the ad itself says
- **Security vetting / security clearance:** mention if relevant - NOT relevant for a non-government / non-security-protected role. RELEVANT for pension funds, central banks, and government agencies with security protection.
- **Internal hourly-rate notes:** must not end up in client-facing versions
- **Other AI tools' advice** (ChatGPT/LinkedIn AI): **always verify against the current ad text** - they often rely on older requirement documents. Lesson learned: an external AI analysis once included terms from older requirement documents that were not in the current ad. Filter them out.

---

### Ad-type-specific modes (summary)

**Permanent, government agency:**
- Bonus = no
- Pension = standard collective scheme
- Six weeks of vacation
- Security vetting often applicable
- Longer recruitment process (4-8 weeks)

**Permanent, listed industrial group:**
- Bonus 10-25% common
- LTI possible (if listed)
- Occupational pension + possible salary sacrifice
- Notice period 3-6 months
- Process 4-8 weeks

**Consulting assignment via intermediary:**
- Hourly rate 1,500-2,200 SEK/h for a senior CISO
- Intermediary margin 15-25%
- End client unknown -> ask outright
- Lead time 1-3 weeks
- Faster follow-up (3/7/14)

**Interim roles** (intermediate management):
- Paid via <YOUR COMPANY>
- Focus on fast deliveries
- Often a bridge to a permanent solution

---

## END OF PROMPT
