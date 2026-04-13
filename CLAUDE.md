# CLAUDE.md — ErasmusDidactica KA1

## Project Context

ErasmusDidactica is an Erasmus+ KA1 staff mobility project (2026–2028) for secondary school teachers across Germany, France, Poland, and Spain. This repo manages all project documentation: application, curricula, training materials, admin, budget, reports, and dissemination.

## Language Rules

- Default working language: **Italian** (coordinating institution is Italian)
- Official documents and deliverables: **English**
- Country-specific materials: use the partner's language + English version
- Partner countries: DE (Germany), FR (France), PL (Poland), ES (Spain)
- Always use ISO country codes when referencing partners

## Document Standards

- All documents in **Markdown** unless a specific format is required (e.g., EU eForm, Excel budget)
- File naming: `YYYY-MM-DD_type_country_description.md` (e.g., `2027-01-15_curriculum_DE_stem-methodology.md`)
- Budget figures always in **EUR**, use EU unit cost tables as reference
- Dates in **ISO 8601** format (YYYY-MM-DD)
- Use ISCED level references (2 = lower secondary, 3 = upper secondary)

## Erasmus+ Specific Rules

- KA1 = Learning Mobility of Individuals (staff mobility)
- Activity types: structured courses, job shadowing, teaching assignments
- Always reference the current Erasmus+ Programme Guide for eligibility and rules
- Budget categories: travel, individual support, course fees, organizational support
- Participant reports are mandatory — use EU Participant Report template structure
- Europass Mobility documents required for all participants
- Dissemination is mandatory — plan outputs for each activity

## Project Priorities (Erasmus+ 2021–2027)

Map all activities to at least one EU horizontal priority:
1. Inclusion and diversity
2. Digital transformation
3. Environment and fight against climate change
4. Participation in democratic life

And at least one KA1 field-specific priority for school education.

## Key Constraints

- Max project duration: 24 months (Sep 2026 – Aug 2028)
- Participants must be staff of the sending organization
- Minimum 60 participants across all mobilities
- Each mobility: 2–30 days (excluding travel)
- Travel distance calculator: use EU Distance Calculator for band assignment
- Organizational support: per-participant lump sum

## Working with this Repo

- `docs/application/` — Do not modify after submission unless for amendment
- `src/curriculum/` — One subfolder per country (DE, FR, PL, ES)
- `src/materials/` — Tag materials with country code and activity type
- `admin/budget/` — Budget must reconcile with grant agreement at all times
- `meetings/` — One file per TPM, named `YYYY-MM-DD_tpm_N_location.md`
- `data/` is gitignored — never commit personal participant data

## Quality Assurance

- Every curriculum document must include: learning outcomes, methodology, assessment criteria, Europass mapping
- Materials must be peer-reviewed by at least one partner before use
- Pre/post assessment required for every structured course
- All outputs must reference the specific EU priority they address
