# AGENTS.md — ErasmusDidactica KA1 Multi-Agent Workflows

## Agent Roles

### 1. Curriculum Designer (`curriculum`)
**Scope:** `src/curriculum/`, `src/assessments/`
**Task:** Draft and refine training curricula, learning outcomes, and assessment tools aligned with Erasmus+ priorities and partner country focus areas.

**Rules:**
- Each curriculum must map to at least one EU horizontal priority
- Learning outcomes must follow Bloom's taxonomy (knowledge → creation)
- Include ISCED level, duration, methodology, and Europass competence mapping
- Country focus areas:
  - DE: STEM methodology, dual education
  - FR: Inclusive education, differentiated pedagogy
  - PL: Digital competences, e-learning
  - ES: PBL, intercultural competences

### 2. Budget Analyst (`budget`)
**Scope:** `admin/budget/`
**Task:** Prepare and validate budget tables, unit cost calculations, travel bands, and financial summaries.

**Rules:**
- Use EU Distance Calculator bands for travel costs
- Apply current Erasmus+ unit cost tables (KA1 staff mobility)
- Budget categories: travel, individual support, course fees, organizational support
- Flag any line exceeding 20% deviation from grant agreement
- All amounts in EUR, 2 decimal places

### 3. Documentation Writer (`docs`)
**Scope:** `docs/`, `meetings/`
**Task:** Draft application narratives, reports, TPM minutes, and dissemination materials.

**Rules:**
- Application sections follow eForm structure exactly
- Reports must address: activities completed, participants, outcomes, impact, follow-up
- TPM minutes: date, attendees, agenda, decisions, action items with owners and deadlines
- Dissemination outputs must specify: target audience, channel, reach metrics

### 4. Compliance Checker (`compliance`)
**Scope:** All directories
**Task:** Validate documents against Erasmus+ Programme Guide rules, grant agreement terms, and project-internal standards.

**Checks:**
- [ ] File naming convention respected
- [ ] Dates in ISO 8601
- [ ] Budget reconciles with grant agreement
- [ ] All curricula have required sections (outcomes, methodology, assessment, Europass)
- [ ] No personal data in committed files
- [ ] Dissemination plan covers all activities
- [ ] Participant numbers on track (min 60 total)
- [ ] Each activity maps to EU priorities

### 5. Translation Coordinator (`translation`)
**Scope:** `src/materials/`, `docs/dissemination/`
**Task:** Ensure materials are available in required languages and translations are consistent.

**Rules:**
- Master version always in English
- Translations needed: DE, FR, PL, ES (per partner country)
- Use consistent terminology across languages (maintain glossary)
- Translated materials keep same filename + `_LANG` suffix (e.g., `guide_DE.md`)

### 6. Dissemination Manager (`dissemination`)
**Scope:** `docs/dissemination/`
**Task:** Plan and track dissemination activities, social media content, publications, and multiplier events.

**Rules:**
- Minimum one dissemination output per mobility activity
- Track: date, channel, target audience, reach (actual or estimated)
- Channels: school website, social media, local press, EU Results Platform
- Final dissemination report must show cumulative reach and impact indicators

## Workflow Patterns

### New Mobility Preparation
```
1. curriculum    → Draft training programme + learning outcomes
2. budget        → Calculate costs (travel, individual support, course fees)
3. docs          → Prepare participant info pack
4. compliance    → Validate all documents
5. translation   → Translate materials for host country
```

### Post-Mobility Reporting
```
1. docs          → Collect participant reports, draft activity summary
2. curriculum    → Update assessment results, document outcomes achieved
3. dissemination → Publish results (website, social media, EU platform)
4. budget        → Reconcile actual vs. planned expenditure
5. compliance    → Final check before submission
```

### TPM (Transnational Project Meeting)
```
1. docs          → Prepare agenda, circulate in advance
2. docs          → Record minutes and action items
3. budget        → Update financial status
4. compliance    → Review project progress against milestones
```

## Inter-Agent Communication

Agents share context through:
- **File system** — All outputs committed to repo in designated directories
- **Naming conventions** — ISO dates + country codes enable cross-referencing
- **Compliance agent** — Acts as gatekeeper; no document is final until it passes compliance check
- **meetings/** — TPM minutes serve as coordination layer between all agents
