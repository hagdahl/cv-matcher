---
name: ATS_keywords_aggregerat
description: Aggregated ATS bank with Tier classification, frequency, and source reference across all ads
version: 0.2.0
last_updated: 2026-06-26
scope: 9 tracks (8 active + 1 parked)
next_update_when: a new ad is analyzed
---

# ATS_keywords - aggregated

> **Version:** 0.2.0 · **Last updated:** 2026-06-26 · **Status:** Prepared for public release

> Cross-cutting ATS keyword bank across all cv-matcher runs.
> Sorted primarily by frequency (how many ads the term appears in), secondarily by Tier (ascending).
> This is a reusable keyword bank of generic information-security vocabulary; track sources are pseudonymized as SP-NN.
> Source files: `Analys och kravmatris v0.x.md` section ATS keywords in each per-track folder.

---

## Tier definitions

| Tier | Definition |
|---|---|
| **1** | Verbatim from the ad - must appear in CV+letter to pass the ATS |
| **2** | Common synonym/paraphrase - should appear, often equivalent |
| **3** | Domain vocabulary - a merit, signals competence |
| **4** | Industry jargon or personality words - opportunistic, only if genuinely relevant |

---

## Aggregated word bank (frequency >= 2)

| Term | Tier | Frequency |
|---|---|---|
| information security | 1 | 9 |
| ISO 27001 (incl. ISO/IEC 27001/27002, ISO 2700x) | 1 | 9 |
| risk / risk management / operational risk | 1 | 8 |
| incident handling / incident response / incident escalation | 1 | 7 |
| governance / GRC / information security governance | 1 | 7 |
| GDPR / data protection / data protection law | 1 | 7 |
| CISO / Chief Information Security Officer | 1 | 6 |
| cybersecurity / cyber risk | 1 | 6 |
| compliance / regulatory compliance | 1 | 6 |
| management / board / executive / reporting to management | 1 | 6 |
| management system / ISMS / security management system | 1 | 6 |
| framework / security framework / control framework | 1 | 6 |
| supplier governance / third-party risk / supply chain | 1 | 6 |
| policies / guidelines / governing documents | 1 | 5 |
| NIS2 / NIS / cybersecurity act | 1 | 5 |
| DORA | 1 | 5 |
| NIST / NIST CSF | 1 | 5 |
| crisis preparedness / continuity planning / mission-critical | 1 | 4 |
| training / awareness / knowledge and awareness | 1 | 5 |
| procurement / requirements setting at acquisition / sales / B2B | 1 | 4 |
| information classification | 1 | 3 |
| leadership / leading teams / driving change / transformation | 1 | 6 |
| project / project management skills | 1 | 4 |
| presentation and communication skills / communicative | 1 | 4 |
| Swedish / English (spoken and written, fluent) | 1 | 4 |
| security by design / secure SDLC | 2 | 4 |
| SOC / SIEM / SOAR | 2 | 4 |
| IAM / PAM / IGA | 1 | 3 |
| CISSP exam prep (never "certified") | 2 | 6 |
| ITIL | 2 | 5 |
| SAFe | 2 | 4 |
| Prosci / change management | 2 | 4 |
| trusted advisor / management reporting / executive presence | 2 | 4 |
| Zero Trust | 2 | 3 |
| Azure AD / cloud / cloud security / Azure-AWS-GCP | 2 | 3 |
| TISAX / SOC2 | 2 | 3 |
| MSBFS / MSBFS 2020:6/7 | 2 | 3 |
| IEC 62443 | 1 | 2 |
| OT/ICS / industrial environments / IT/OT interface | 1 | 2 |
| CER (Critical Entities Resilience) | 1 | 1 |
| pension-fund act | 1 | 1 |
| security protection / security vetting / security clearance | 1 | 3 |
| societally important / critical infrastructure | 1 | 4 |
| strategic advisory / strategy-business-security | 1 | 4 |
| current-state analyses / maturity assessments / business resilience | 1 | 2 |
| first/second line of defense | 1 | 1 |
| process-oriented / process mapping | 1 | 2 |
| ITSM / pm3 | 2 | 2 |
| KPI / measurable results / audits and tests | 1 | 2 |
| stakeholder management / cross-functional teams | 1 | 3 |
| CISM | 2 | 2 |
| CIS Controls / Center for Internet Security | 2 | 3 |
| Swedish citizenship | 1 | 2 |
| security-cleared / pragmatic / driven / strategic (personality) | 4 | 4 |

---

## Track-specific terms (frequency = 1)

Terms that occur in only one ad but are load-bearing for that track. Not taken into the general template - listed for reference. Track-identifying details have been pseudonymized.

### SP-01 (listed industrial group)
* personal-data processing, group experience (listed industrial group), Acceptable Use Policy

### SP-02 (asset management / public pension fund)
* asset management, bank/insurance/asset-management (sector list), business support and control, pension-fund act, public-sector pension scheme

### SP-03 (financial services, global group)
* cyber risk posture, secure digital transformation, security in the cloud, regulated organizations, global organizations, business impact, German as a working language

### SP-04 (identity and access)
* SailPoint (tool gap), CyberArk (tool gap), least privilege, microsegmentation, identity-first, MDR/XDR/EDR

### SP-05 (industrial / OT)
* Industrial Data Communications, customer security requirements, data governance, IT/OT interface (Tier 2)

### SP-06 (consulting management role)
* Consultant Manager (role title), strategic competence supply, employee development, forecasting, tactical initiatives, business-oriented, partner management, P&L, delivery responsibility, competence-area responsibility

### SP-07 (management consulting)
* management consultant (role title), entrepreneurial, role reference code, lead implementer/auditor (training), AI-driven transformation

### SP-08 (public-sector agency)
* information security coordinator (role title), governing documents, cybersecurity self-assessment, IT services and security solutions, patient-data law, public-access and secrecy law (OSL), archive law, collaboration with legal/IT architect/DPO, environmental scanning

### SP-09 (central bank, parked)
* group manager information security, security-sensitive operations, security manager (reporting line), ICT third-party risk, newly established security organization

---

## Terms NOT to mix between tracks (filter actively)

Documented per track in the v0.2 upgrades:

* **SP-08** - filter out CISO-function, ISMS, security management system, cybersecurity act, NIS2, MSBFS 2020:6/7, DORA, security protection, security clearance, security vetting, ICT third-party risk (terms from adjacent tracks).
* **SP-02** - filter out CER/OT, pension-fund act (from another track), consulting sales, IEC 62443.
* **SP-06** - filter out CER, OT/ICS, IEC 62443, DORA-heavy, NIS2-heavy (irrelevant for a consulting-manager role).
* **SP-01** - filter out CER/installation language and pension-fund act (from other tracks).

---

## Update routine

On each new cv-matcher run that produces an `Analys och kravmatris` file:

1. Read the ATS keywords section in the new analysis.
2. For each term:
   * If the term already exists: bump the frequency, add the source.
   * If new: create a row with Tier classification + frequency=1 + source.
3. Re-sort the table primarily by frequency (descending), secondarily by Tier (ascending).
4. Bump `last_updated` in the frontmatter.
