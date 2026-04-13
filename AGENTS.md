# AGENTS.md — ErasmusDidactica 60 Agenti Paralleli

## REGOLA FONDAMENTALE
60 agenti sempre attivi in parallelo. Mai sequenziale. Mai meno di 60.
Ogni agente ha scope, fonte e output definiti. NON INVENTARE MAI dati.
Vuoto meglio che falso. Firecrawl + web + LinkedIn come fonti.

---

## BLOCCO 1 — SCRAPER SCUOLE ESEP PER PAESE (AG-01 → AG-16)

### AG-01 — Scraper ESEP Germania Wave 1
**Scope:** DE — Land: Bayern + Baden-Württemberg
**Fonte:** school-education.ec.europa.eu filtro DE + KA1
**Output:** `data/schools/DE_wave1.csv` (nome scuola, città, Land, OID, tipo ISCED)

### AG-02 — Scraper ESEP Germania Wave 2
**Scope:** DE — Land: NRW + Hessen
**Fonte:** school-education.ec.europa.eu filtro DE + KA1
**Output:** `data/schools/DE_wave2.csv`

### AG-03 — Scraper ESEP Germania Wave 3
**Scope:** DE — Land: Niedersachsen + Sachsen
**Fonte:** school-education.ec.europa.eu filtro DE + KA1
**Output:** `data/schools/DE_wave3.csv`

### AG-04 — Scraper ESEP Germania Wave 4
**Scope:** DE — Land: Berlin + Hamburg + restanti
**Fonte:** school-education.ec.europa.eu filtro DE + KA1
**Output:** `data/schools/DE_wave4.csv`

### AG-05 — Scraper ESEP Francia Wave 1
**Scope:** FR — Région: Île-de-France + Hauts-de-France
**Fonte:** school-education.ec.europa.eu filtro FR + KA1
**Output:** `data/schools/FR_wave1.csv`

### AG-06 — Scraper ESEP Francia Wave 2
**Scope:** FR — Région: Auvergne-Rhône-Alpes + Occitanie
**Fonte:** school-education.ec.europa.eu filtro FR + KA1
**Output:** `data/schools/FR_wave2.csv`

### AG-07 — Scraper ESEP Francia Wave 3
**Scope:** FR — Région: Nouvelle-Aquitaine + Grand Est
**Fonte:** school-education.ec.europa.eu filtro FR + KA1
**Output:** `data/schools/FR_wave3.csv`

### AG-08 — Scraper ESEP Francia Wave 4
**Scope:** FR — Région: Provence-Alpes-Côte d'Azur + restanti
**Fonte:** school-education.ec.europa.eu filtro FR + KA1
**Output:** `data/schools/FR_wave4.csv`

### AG-09 — Scraper ESEP Polonia Wave 1
**Scope:** PL — Voivodato: Mazowieckie + Małopolskie
**Fonte:** school-education.ec.europa.eu filtro PL + KA1
**Output:** `data/schools/PL_wave1.csv`

### AG-10 — Scraper ESEP Polonia Wave 2
**Scope:** PL — Voivodato: Śląskie + Wielkopolskie
**Fonte:** school-education.ec.europa.eu filtro PL + KA1
**Output:** `data/schools/PL_wave2.csv`

### AG-11 — Scraper ESEP Polonia Wave 3
**Scope:** PL — Voivodato: Dolnośląskie + Łódzkie
**Fonte:** school-education.ec.europa.eu filtro PL + KA1
**Output:** `data/schools/PL_wave3.csv`

### AG-12 — Scraper ESEP Polonia Wave 4
**Scope:** PL — Voivodato: Pomorskie + restanti
**Fonte:** school-education.ec.europa.eu filtro PL + KA1
**Output:** `data/schools/PL_wave4.csv`

### AG-13 — Scraper ESEP Spagna Wave 1
**Scope:** ES — Comunidad: Madrid + Cataluña
**Fonte:** school-education.ec.europa.eu filtro ES + KA1
**Output:** `data/schools/ES_wave1.csv`

### AG-14 — Scraper ESEP Spagna Wave 2
**Scope:** ES — Comunidad: Andalucía + Comunitat Valenciana
**Fonte:** school-education.ec.europa.eu filtro ES + KA1
**Output:** `data/schools/ES_wave2.csv`

### AG-15 — Scraper ESEP Spagna Wave 3
**Scope:** ES — Comunidad: País Vasco + Castilla y León
**Fonte:** school-education.ec.europa.eu filtro ES + KA1
**Output:** `data/schools/ES_wave3.csv`

### AG-16 — Scraper ESEP Spagna Wave 4
**Scope:** ES — Comunidad: Galicia + restanti
**Fonte:** school-education.ec.europa.eu filtro ES + KA1
**Output:** `data/schools/ES_wave4.csv`

---

## BLOCCO 2 — ENRICHER CONTATTI SCUOLE (AG-17 → AG-28)

### AG-17 — Enricher Contatti DE Wave 1
**Scope:** Scuole DE da AG-01/02
**Fonte:** Siti web scuole + pagine Kontakt/Impressum
**Output:** `data/contacts/DE_contacts1.csv` (coordinatore Erasmus, dirigente, email, telefono, fonte URL)

### AG-18 — Enricher Contatti DE Wave 2
**Scope:** Scuole DE da AG-03/04
**Fonte:** Siti web scuole + pagine Kontakt/Impressum
**Output:** `data/contacts/DE_contacts2.csv`

### AG-19 — Enricher LinkedIn DE
**Scope:** Scuole DE senza coordinatore trovato via web
**Fonte:** LinkedIn — profili "Erasmus Koordinator" + nome scuola
**Output:** `data/contacts/DE_linkedin.csv`

### AG-20 — Enricher Contatti FR Wave 1
**Scope:** Scuole FR da AG-05/06
**Fonte:** Siti web scuole + pages Contact/Équipe
**Output:** `data/contacts/FR_contacts1.csv`

### AG-21 — Enricher Contatti FR Wave 2
**Scope:** Scuole FR da AG-07/08
**Fonte:** Siti web scuole + pages Contact/Équipe
**Output:** `data/contacts/FR_contacts2.csv`

### AG-22 — Enricher LinkedIn FR
**Scope:** Scuole FR senza coordinatore trovato via web
**Fonte:** LinkedIn — profili "Coordinateur Erasmus" + nome école
**Output:** `data/contacts/FR_linkedin.csv`

### AG-23 — Enricher Contatti PL Wave 1
**Scope:** Scuole PL da AG-09/10
**Fonte:** Siti web scuole + pagine Kontakt/Kadra
**Output:** `data/contacts/PL_contacts1.csv`

### AG-24 — Enricher Contatti PL Wave 2
**Scope:** Scuole PL da AG-11/12
**Fonte:** Siti web scuole + pagine Kontakt/Kadra
**Output:** `data/contacts/PL_contacts2.csv`

### AG-25 — Enricher LinkedIn PL
**Scope:** Scuole PL senza coordinatore trovato via web
**Fonte:** LinkedIn — profili "Koordynator Erasmus" + nazwa szkoły
**Output:** `data/contacts/PL_linkedin.csv`

### AG-26 — Enricher Contatti ES Wave 1
**Scope:** Scuole ES da AG-13/14
**Fonte:** Siti web scuole + páginas Contacto/Equipo
**Output:** `data/contacts/ES_contacts1.csv`

### AG-27 — Enricher Contatti ES Wave 2
**Scope:** Scuole ES da AG-15/16
**Fonte:** Siti web scuole + páginas Contacto/Equipo
**Output:** `data/contacts/ES_contacts2.csv`

### AG-28 — Enricher LinkedIn ES
**Scope:** Scuole ES senza coordinatore trovato via web
**Fonte:** LinkedIn — profili "Coordinador Erasmus" + nombre centro
**Output:** `data/contacts/ES_linkedin.csv`

---

## BLOCCO 3 — SCRAPER FORMATORI EU (AG-29 → AG-40)

### AG-29 — Scraper Formatori LinkedIn DE Wave 1
**Scope:** DE — Formatori STEM / dual education
**Fonte:** LinkedIn — "Lehrerfortbildung" OR "STEM trainer" + Deutschland
**Output:** `data/trainers/DE_linkedin1.csv` (nome, ruolo, organizzazione, città, profilo URL)

### AG-30 — Scraper Formatori LinkedIn DE Wave 2
**Scope:** DE — Formatori inclusione / digitale
**Fonte:** LinkedIn — "Inklusion Fortbildung" OR "digitale Bildung" + Deutschland
**Output:** `data/trainers/DE_linkedin2.csv`

### AG-31 — Scraper Formatori EPALE DE
**Scope:** DE — Formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro DE + teacher training
**Output:** `data/trainers/DE_epale.csv`

### AG-32 — Scraper Formatori LinkedIn FR Wave 1
**Scope:** FR — Formatori pédagogie différenciée / inclusion
**Fonte:** LinkedIn — "formateur enseignants" OR "pédagogie inclusive" + France
**Output:** `data/trainers/FR_linkedin1.csv`

### AG-33 — Scraper Formatori LinkedIn FR Wave 2
**Scope:** FR — Formatori numérique éducatif / FLE
**Fonte:** LinkedIn — "formateur numérique éducatif" OR "formation continue enseignants" + France
**Output:** `data/trainers/FR_linkedin2.csv`

### AG-34 — Scraper Formatori EPALE FR
**Scope:** FR — Formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro FR + teacher training
**Output:** `data/trainers/FR_epale.csv`

### AG-35 — Scraper Formatori LinkedIn PL Wave 1
**Scope:** PL — Formatori kompetencje cyfrowe / e-learning
**Fonte:** LinkedIn — "szkoleniowiec nauczycieli" OR "e-learning" + Polska
**Output:** `data/trainers/PL_linkedin1.csv`

### AG-36 — Scraper Formatori LinkedIn PL Wave 2
**Scope:** PL — Formatori metodyka / innowacje edukacyjne
**Fonte:** LinkedIn — "trener edukacji" OR "innowacje w edukacji" + Polska
**Output:** `data/trainers/PL_linkedin2.csv`

### AG-37 — Scraper Formatori EPALE PL
**Scope:** PL — Formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro PL + teacher training
**Output:** `data/trainers/PL_epale.csv`

### AG-38 — Scraper Formatori LinkedIn ES Wave 1
**Scope:** ES — Formatori ABP / competencias interculturales
**Fonte:** LinkedIn — "formador docentes" OR "aprendizaje basado en proyectos" + España
**Output:** `data/trainers/ES_linkedin1.csv`

### AG-39 — Scraper Formatori LinkedIn ES Wave 2
**Scope:** ES — Formatori innovación educativa / TIC
**Fonte:** LinkedIn — "innovación educativa" OR "formación profesorado" + España
**Output:** `data/trainers/ES_linkedin2.csv`

### AG-40 — Scraper Formatori EPALE ES
**Scope:** ES — Formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro ES + teacher training
**Output:** `data/trainers/ES_epale.csv`

---

## BLOCCO 4 — FORMATORI ITALIA SEDI ADIUVA (AG-41 → AG-48)

### AG-41 — Scraper Formatori LinkedIn Milano Wave 1
**Scope:** IT — Milano e provincia, formatori didattica/lingue
**Fonte:** LinkedIn — "formatore docenti" OR "formazione insegnanti" + Milano
**Output:** `data/trainers_it/MI_linkedin1.csv`

### AG-42 — Scraper Formatori EPALE Milano
**Scope:** IT — Milano, formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro IT + Milano + teacher training
**Output:** `data/trainers_it/MI_epale.csv`

### AG-43 — Scraper Formatori LinkedIn Firenze Wave 1
**Scope:** IT — Firenze e provincia, formatori didattica/lingue
**Fonte:** LinkedIn — "formatore docenti" OR "formazione insegnanti" + Firenze
**Output:** `data/trainers_it/FI_linkedin1.csv`

### AG-44 — Scraper Formatori EPALE Firenze
**Scope:** IT — Firenze, formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro IT + Firenze + teacher training
**Output:** `data/trainers_it/FI_epale.csv`

### AG-45 — Scraper Formatori LinkedIn Mantova Wave 1
**Scope:** IT — Mantova e provincia, formatori didattica/lingue
**Fonte:** LinkedIn — "formatore docenti" OR "formazione insegnanti" + Mantova
**Output:** `data/trainers_it/MN_linkedin1.csv`

### AG-46 — Scraper Formatori EPALE Mantova
**Scope:** IT — Mantova, formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro IT + Mantova + teacher training
**Output:** `data/trainers_it/MN_epale.csv`

### AG-47 — Scraper Formatori LinkedIn Torino Wave 1
**Scope:** IT — Torino e provincia, formatori didattica/lingue
**Fonte:** LinkedIn — "formatore docenti" OR "formazione insegnanti" + Torino
**Output:** `data/trainers_it/TO_linkedin1.csv`

### AG-48 — Scraper Formatori EPALE Torino
**Scope:** IT — Torino, formatori registrati EPALE
**Fonte:** epale.ec.europa.eu filtro IT + Torino + teacher training
**Output:** `data/trainers_it/TO_epale.csv`

---

## BLOCCO 5 — QA, DEDUP, VALIDAZIONE (AG-49 → AG-54)

### AG-49 — Dedup Scuole Globale
**Scope:** Tutti i CSV in `data/schools/`
**Task:** Rimuovi duplicati per OID o nome+città. Merge wave diverse.
**Output:** `data/schools/ALL_schools_dedup.csv`

### AG-50 — Dedup Contatti Globale
**Scope:** Tutti i CSV in `data/contacts/`
**Task:** Rimuovi duplicati per email o nome+scuola. Priorità: coordinatore > dirigente > generico.
**Output:** `data/contacts/ALL_contacts_dedup.csv`

### AG-51 — Dedup Formatori EU Globale
**Scope:** Tutti i CSV in `data/trainers/`
**Task:** Rimuovi duplicati per nome+organizzazione o profilo LinkedIn.
**Output:** `data/trainers/ALL_trainers_dedup.csv`

### AG-52 — Dedup Formatori Italia Globale
**Scope:** Tutti i CSV in `data/trainers_it/`
**Task:** Rimuovi duplicati per nome+organizzazione o profilo LinkedIn.
**Output:** `data/trainers_it/ALL_trainers_it_dedup.csv`

### AG-53 — Validatore Email
**Scope:** Tutti i CSV dedup con campo email
**Task:** Verifica formato email, dominio attivo (MX check). Flag invalid.
**Output:** Aggiunge colonna `email_status` (valid/invalid/unverified) a ogni CSV dedup

### AG-54 — Completezza e Score
**Scope:** Tutti i CSV dedup
**Task:** Calcola completeness score per record (nome, ruolo, email, telefono, fonte).
**Output:** Aggiunge colonna `completeness_score` (0–100) + report `data/qa_report.md`

---

## BLOCCO 6 — OUTREACH E PITCH (AG-55 → AG-60)

### AG-55 — Template Outreach DE
**Scope:** Scuole tedesche con contatto validato
**Task:** Genera email template in tedesco per proposta KA1. Formale, riferimento ESEP.
**Output:** `src/materials/outreach/template_DE.md`

### AG-56 — Template Outreach FR
**Scope:** Scuole francesi con contatto validato
**Task:** Genera email template in francese per proposta KA1. Formale, riferimento ESEP.
**Output:** `src/materials/outreach/template_FR.md`

### AG-57 — Template Outreach PL
**Scope:** Scuole polacche con contatto validato
**Task:** Genera email template in polacco per proposta KA1. Formale, riferimento ESEP.
**Output:** `src/materials/outreach/template_PL.md`

### AG-58 — Template Outreach ES
**Scope:** Scuole spagnole con contatto validato
**Task:** Genera email template in spagnolo per proposta KA1. Formale, riferimento ESEP.
**Output:** `src/materials/outreach/template_ES.md`

### AG-59 — Template Outreach IT (Formatori)
**Scope:** Formatori italiani con contatto validato
**Task:** Genera email template in italiano per proposta collaborazione formativa KA1.
**Output:** `src/materials/outreach/template_IT.md`

### AG-60 — Pitch Deck Generator
**Scope:** Progetto ErasmusDidactica completo
**Task:** Genera pitch deck Markdown con: overview progetto, partner, attività, timeline, budget summary, EU priorities. Versione EN master + sommario IT.
**Output:** `docs/dissemination/pitch_deck_EN.md` + `docs/dissemination/pitch_deck_IT.md`

---

## WORKFLOW ESECUZIONE

```
WAVE 1 (parallelo):  AG-01→16  — scrape scuole ESEP tutti i paesi
WAVE 2 (parallelo):  AG-17→28  — enrich contatti web + LinkedIn
WAVE 3 (parallelo):  AG-29→40  — scrape formatori EU
WAVE 4 (parallelo):  AG-41→48  — scrape formatori Italia
WAVE 5 (parallelo):  AG-49→54  — QA dedup validazione
WAVE 6 (parallelo):  AG-55→60  — outreach templates + pitch deck
```

Ogni wave parte quando la wave precedente ha output. Wave 1 e Wave 3+4 possono partire in parallelo (fonti indipendenti).

## INTER-AGENT COMMUNICATION

- **File system** — Tutti gli output in `data/` (gitignored) o `src/materials/`
- **CSV standard** — Ogni CSV ha header riga 1, encoding UTF-8, separatore `,`
- **Naming** — `{COUNTRY}_{source}{N}.csv` per raw, `ALL_{type}_dedup.csv` per dedup
- **QA agent** — Gatekeeper: nessun dato va in outreach senza passare QA
- **Log** — Ogni agente scrive status in `data/agent_log.jsonl` (timestamp, agent_id, status, record_count)
