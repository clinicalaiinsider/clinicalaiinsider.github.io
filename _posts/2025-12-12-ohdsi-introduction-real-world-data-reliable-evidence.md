---
layout: post
title: "OHDSI Introduction: From Real-World Data to Reliable Evidence"
subtitle: "A Comprehensive Guide to Observational Health Data Sciences and Informatics"
date: 2025-12-12
author: DataGodzilla
categories: [ohdsi, clinical]
tags: [ohdsi, omop, cdm, real-world-data, observational-research, healthcare-analytics]
mermaid: true
toc: true
description: "Learn how OHDSI transforms messy healthcare data into reliable clinical evidence. This guide explains the OMOP Common Data Model, standardized vocabularies, and tool ecosystem using the Feynman technique."
reading_time: 25
---

# OHDSI Introduction: From Real-World Data to Reliable Evidence

> **Listen to the Podcast**
>
> Prefer audio? Listen to this article as a conversational podcast (~18 min):
>
> <audio controls style="width: 100%; max-width: 500px;">
>   <source src="/assets/audio/ohdsi_podcast.mp3" type="audio/mpeg">
>   Your browser does not support the audio element.
> </audio>
>
> [Download MP3](/assets/audio/ohdsi_podcast.mp3) | [View Transcript](/podcasts/ohdsi_podcast_script/)

---

Picture this: You're a hospital administrator who just received a troubling report. Three patients developed aortic aneurysms after taking a common antibiotic. Is this a coincidence, or have you stumbled onto a serious safety signal?

To answer this question, you'd need to compare your data with hundreds of other hospitals. But here's the problem—every hospital stores data differently. One uses ICD-10 codes, another SNOMED-CT. One stores medications by brand name, another by generic. It's like trying to compare apples and oranges, except the apples are labeled in French and the oranges in Mandarin.

This is where OHDSI changes everything.

In this post, we'll explore how a global community of 4,751+ collaborators across 88 countries built a "universal translator" for healthcare data, enabling researchers to answer questions that would be impossible to tackle alone.

---

## What is OHDSI?

**Think of OHDSI like the United Nations of healthcare data.** Just as the UN brings countries together with a common framework for diplomacy, OHDSI brings healthcare organizations together with a common framework for data analysis.

<div class="mermaid">
mindmap
  root((OHDSI<br/>Ecosystem))
    Data Standards
      OMOP CDM
        Person Table
        Visit Table
        Condition Table
        Drug Table
        Procedure Table
        Measurement Table
      Vocabularies
        SNOMED-CT
        RxNorm
        LOINC
        ICD-10
        CPT
    Methods
      Characterization
        Patient Profiles
        Disease Natural History
      Estimation
        Comparative Effectiveness
        Safety Studies
      Prediction
        Risk Models
        ML/AI
    Tools
      Athena
        Browse Concepts
        Download Vocabularies
      Atlas
        Cohort Builder
        Study Design
      HADES
        R Packages
        Analysis Pipeline
      Strategus
        Orchestration
        Reproducibility
    Community
      Working Groups
        CDM
        Vocabularies
        HADES
        Phenotypes
      Events
        Symposium
        Tutorials
        Chapters
</div>

### Key Facts

| Metric | Value |
|--------|-------|
| Founded | 2014 |
| Collaborators | 4,751+ |
| Countries | 88 |
| Time Zones | 21 |
| Continents | 6 |
| Central Hub | Columbia University |

### The Mission

> **Mission**: Improve health by empowering a community to collaboratively generate the evidence that promotes better health decisions and better care.

---

## The Data Standardization Problem

Here's the thing that confused me for weeks when I first started learning about healthcare interoperability: **why can't hospitals just share data?**

The answer is painfully simple once you understand it.

### The Electrical Outlet Analogy

Imagine traveling internationally with your laptop. Your laptop (the analytical method) works the same everywhere—it's designed to run identically regardless of location. But every country has different electrical outlets (the data).

Without OMOP, you need a different adapter for every outlet. With OMOP, you have a universal adapter that works everywhere.

<div class="mermaid">
flowchart TB
    subgraph Sources["Source Data (Different Formats)"]
        EHR["EHR Systems<br/>(Epic, Cerner)"]
        Claims["Claims Data"]
        Registry["Registries"]
    end

    subgraph ETL["ETL Process"]
        Extract["Extract"]
        Transform["Transform"]
        Load["Load"]
    end

    subgraph Vocab["Standardized Vocabularies"]
        Athena["Athena<br/>12M+ Concepts"]
        Mapping["Source → Standard<br/>Concept Mapping"]
    end

    subgraph CDM["OMOP CDM (Common Format)"]
        Person["Person"]
        Visit["Visit"]
        Condition["Condition"]
        Drug["Drug"]
        Procedure["Procedure"]
        Measurement["Measurement"]
    end

    subgraph Analysis["Analysis Tools"]
        Atlas["Atlas<br/>(Web UI)"]
        HADES["HADES<br/>(R Packages)"]
    end

    subgraph Output["Evidence"]
        Characterization["Characterization"]
        Estimation["Estimation"]
        Prediction["Prediction"]
    end

    EHR --> Extract
    Claims --> Extract
    Registry --> Extract
    Extract --> Transform
    Transform --> Load

    Athena --> Mapping
    Mapping --> Load

    Load --> Person
    Load --> Visit
    Load --> Condition
    Load --> Drug
    Load --> Procedure
    Load --> Measurement

    Person --> Atlas
    Visit --> Atlas
    Condition --> Atlas
    Drug --> Atlas

    Atlas --> HADES
    HADES --> Characterization
    HADES --> Estimation
    HADES --> Prediction
</div>

### Real-World Mapping Example

Let me show you what this actually looks like. Say Hospital A and Hospital B both want to analyze their use of Ciprofloxacin (a common antibiotic).

<div class="mermaid">
flowchart TB
    subgraph HospA["Hospital A (Uses RxNorm)"]
        CodeA["Ciprofloxacin<br/>Code: 2551"]
    end

    subgraph HospB["Hospital B (Uses HMOG)"]
        CodeB["Ciprofloxacin<br/>Code: 104"]
    end

    subgraph OMOP["OMOP Standard"]
        Standard["Standard Concept ID<br/>1797513<br/>(Ciprofloxacin)"]
    end

    subgraph Shared["Shared Analysis"]
        Compare["✓ Can Compare<br/>✓ Can Share<br/>✓ Can Analyze"]
    end

    CodeA -->|"Map"| Standard
    CodeB -->|"Map"| Standard
    Standard --> Compare
</div>

The same drug has code "2551" in Hospital A and code "104" in Hospital B. But after mapping to OMOP, both become **Concept ID 1797513**. Now they can be analyzed together.

---

## The OMOP Common Data Model

Okay, now things get interesting. Let's look at how the OMOP CDM actually works.

### Core Principles

The CDM was built around these foundational ideas:

| Principle | What It Means | Why It Matters |
|-----------|---------------|----------------|
| **Patient-Centric** | Everything revolves around the patient | Not for billing—purely for research |
| **Standard Vocabulary** | Common terminology for all data | Enables cross-institutional comparison |
| **Domain-Oriented** | Concepts organized by clinical domain | Intuitive navigation |
| **Source Preservation** | Original codes are kept | Can trace back if needed |
| **Extensible** | Can evolve and add features | Future-proof design |
| **Database Independent** | Works with any database | PostgreSQL, SQL Server, Oracle, etc. |

### The Table Structure

<div class="mermaid">
erDiagram
    PERSON ||--o{ VISIT_OCCURRENCE : has
    PERSON ||--o{ CONDITION_OCCURRENCE : has
    PERSON ||--o{ DRUG_EXPOSURE : has
    PERSON ||--o{ PROCEDURE_OCCURRENCE : has
    PERSON ||--o{ MEASUREMENT : has
    PERSON ||--o{ OBSERVATION : has

    VISIT_OCCURRENCE ||--o{ CONDITION_OCCURRENCE : contains
    VISIT_OCCURRENCE ||--o{ DRUG_EXPOSURE : contains
    VISIT_OCCURRENCE ||--o{ PROCEDURE_OCCURRENCE : contains

    CONCEPT ||--|| CONDITION_OCCURRENCE : defines
    CONCEPT ||--|| DRUG_EXPOSURE : defines
    CONCEPT ||--|| PROCEDURE_OCCURRENCE : defines
    CONCEPT ||--|| MEASUREMENT : defines

    PERSON {
        int person_id PK
        int gender_concept_id
        int year_of_birth
        int race_concept_id
    }

    VISIT_OCCURRENCE {
        int visit_occurrence_id PK
        int person_id FK
        int visit_concept_id
        date visit_start_date
    }

    CONDITION_OCCURRENCE {
        int condition_occurrence_id PK
        int person_id FK
        int condition_concept_id
        date condition_start_date
    }

    DRUG_EXPOSURE {
        int drug_exposure_id PK
        int person_id FK
        int drug_concept_id
        date drug_exposure_start_date
    }
</div>

The PERSON table is central—everything connects back to it. This patient-centric design is what makes OMOP different from billing-focused data models.

---

## Standardized Vocabularies

This is where OHDSI gets really powerful. The vocabularies are a massive "Rosetta Stone" for healthcare data.

### By the Numbers

| Metric | Count |
|--------|-------|
| Total Concepts | 12+ million |
| Vocabularies | 142 |
| Domains | 44 |
| Concept Relationships | 80+ million |

### Key Vocabulary Sources

| Vocabulary | Domain | Examples |
|------------|--------|----------|
| [SNOMED-CT](https://www.snomed.org/) | Conditions | Diseases, findings |
| [RxNorm](https://www.nlm.nih.gov/research/umls/rxnorm/) | Drugs | Medications |
| [LOINC](https://loinc.org/) | Measurements | Lab tests |
| [ICD-10](https://www.who.int/standards/classifications/classification-of-diseases) | Conditions | Diagnosis codes |
| [CPT](https://www.ama-assn.org/practice-management/cpt) | Procedures | Procedure codes |

### Concept ID vs Concept Code

This distinction tripped me up at first. Let me explain:

| Attribute | Concept ID | Concept Code |
|-----------|------------|--------------|
| Source | OHDSI-assigned | External (SNOMED, RxNorm, etc.) |
| Uniqueness | Globally unique | Unique within vocabulary only |
| Format | Integer | String |
| Example | 1797513 | "2551" |

**Why this matters**: The same concept code "2551" might mean different things in different vocabularies. The Concept ID ensures uniqueness across the entire OMOP ecosystem.

---

## Study Types

OHDSI supports three main types of studies, each answering a different kind of question:

<div class="mermaid">
flowchart LR
    subgraph Building["Study Building Blocks"]
        direction TB
        DB["📊 Databases<br/>14 OMOP Sites"]
        Phenotype["🎯 Phenotypes<br/>Cohort Definitions"]
        Design["📐 Study Design<br/>Estimation"]
        Methods["📈 Methods<br/>Propensity Scores"]
        Tools["🔧 Tools<br/>Atlas, HADES"]
    end

    subgraph Study["Fluoroquinolone Study"]
        Question["Does fluoroquinolone<br/>increase aortic<br/>aneurysm risk?"]
        Results["📋 Results"]
    end

    DB --> Question
    Phenotype --> Question
    Design --> Question
    Methods --> Question
    Tools --> Question
    Question --> Results
</div>

### 1. Characterization
**Question**: "Who are these patients?"

Examples:
- What are the demographics of diabetic patients?
- What medications do heart failure patients take?
- What's the natural history of Parkinson's disease?

### 2. Estimation (Population-Level Effect)
**Question**: "Does treatment A cause outcome B?"

Template: "Does exposure to [TREATMENT] have different risk of [OUTCOME] within [TIME] vs [COMPARATOR]?"

Examples:
- Do ACE inhibitors reduce stroke risk vs ARBs?
- Does metformin cause lactic acidosis?
- Do fluoroquinolones increase aortic aneurysm risk?

### 3. Prediction (Patient-Level)
**Question**: "What will happen to this specific patient?"

Examples:
- What's this patient's 5-year heart attack risk?
- Will this patient be readmitted within 30 days?
- What's the probability of treatment response?

---

## The OHDSI Tool Ecosystem

Here's where it gets fun—the tools that make all of this possible.

<div class="mermaid">
graph TB
    subgraph Community["OHDSI Community"]
        direction TB

        subgraph Vocab["Vocabulary Layer"]
            Athena["🔍 Athena<br/>athena.ohdsi.org<br/>───────────<br/>• Browse Concepts<br/>• Download Vocabs<br/>• 12M+ Concepts"]
        end

        subgraph Design["Design Layer"]
            Atlas["🎨 Atlas<br/>atlas.ohdsi.org<br/>───────────<br/>• Cohort Builder<br/>• Study Design<br/>• Concept Sets"]
        end

        subgraph Analysis["Analysis Layer"]
            HADES["📦 HADES<br/>R Packages<br/>───────────<br/>• CohortGenerator<br/>• CohortMethod<br/>• PatientLevelPred"]

            Strategus["⚙️ Strategus<br/>Pipeline<br/>───────────<br/>• Orchestration<br/>• Reproducibility<br/>• Automation"]
        end

        subgraph QA["Quality Layer"]
            DQD["📊 Data Quality<br/>Dashboard<br/>───────────<br/>• ETL Validation<br/>• Issue Detection<br/>• Quality Metrics"]
        end
    end

    Athena --> Atlas
    Atlas --> HADES
    HADES --> Strategus
    DQD --> Atlas
</div>

### Tool Summary

| Tool | Purpose | URL |
|------|---------|-----|
| **Athena** | Vocabulary browser and download | [athena.ohdsi.org](https://athena.ohdsi.org) |
| **Atlas** | Web-based study design and cohort building | [atlas.ohdsi.org](https://atlas.ohdsi.org) |
| **HADES** | R packages for analysis | [ohdsi.github.io/Hades](https://ohdsi.github.io/Hades/) |
| **Strategus** | Study execution pipeline | Part of HADES |
| **Data Quality Dashboard** | ETL validation | [ohdsi.github.io/DataQualityDashboard](https://ohdsi.github.io/DataQualityDashboard/) |

---

## Real-World Example: The Fluoroquinolones Study

Let me bring this all together with a real example.

**The Question**: Do fluoroquinolones (common antibiotics like Ciprofloxacin) increase the risk of aortic aneurysm or dissection?

**The Approach**:
1. **14 databases** converted to OMOP CDM participated
2. **Phenotypes** defined patients exposed to fluoroquinolones and patients with UTIs
3. **Study design** compared fluoroquinolone users to other UTI treatments
4. **Methods** used propensity score matching to control for confounding
5. **Tools**: Atlas for cohort definition, HADES for analysis

This kind of study would be nearly impossible without OHDSI. Each hospital would need its own study team, and results couldn't be directly compared.

---

## Getting Started

Ready to join the community? Here's how:

### Ways to Participate

| Level | Description | Time Commitment |
|-------|-------------|-----------------|
| **Observer** | Join working groups, listen, learn | 1-2 hours/month |
| **Consumer** | Use OHDSI tools and data | As needed |
| **Contributor** | Convert data, run studies | 10+ hours/month |
| **Developer** | Build tools, improve packages | Ongoing |
| **Leader** | Lead working groups, mentor others | Significant |

### Essential Resources

| Resource | URL |
|----------|-----|
| Main Website | [ohdsi.org](https://www.ohdsi.org) |
| Vocabularies | [athena.ohdsi.org](https://athena.ohdsi.org) |
| Web Tools | [atlas.ohdsi.org](https://atlas.ohdsi.org) |
| R Packages | [ohdsi.github.io/Hades](https://ohdsi.github.io/Hades) |
| Documentation | [ohdsi.github.io/CommonDataModel](https://ohdsi.github.io/CommonDataModel) |
| Community | [forums.ohdsi.org](https://forums.ohdsi.org) |
| Book of OHDSI | [ohdsi.github.io/TheBookOfOhdsi](https://ohdsi.github.io/TheBookOfOhdsi) |

---

## Key Takeaways

1. **OHDSI is a global community** of 4,751+ collaborators working to standardize healthcare data analysis
2. **The OMOP CDM** is the universal "adapter" that allows different healthcare systems to share and compare data
3. **Standardized vocabularies** (12M+ concepts) provide a common language for clinical concepts
4. **Three study types** (Characterization, Estimation, Prediction) cover the major research questions
5. **Open-source tools** (Athena, Atlas, HADES) make analysis accessible to everyone

---

## Learning Resources

### Study Materials

Test your understanding and reinforce key concepts:

- [**Flashcard Deck**](/flashcards/ohdsi_flashcards.md) - 30 cards for spaced repetition learning
- [**Self-Assessment Quiz**](/quizzes/ohdsi_quiz.md) - 30 questions (multiple choice, true/false, short answer)
- [**Presentation Slides**](/slides/ohdsi_slides.md) - 27 slides for teaching or review

---

## References & Resources

### Official OHDSI Resources

| Resource | Description | Link |
|----------|-------------|------|
| **OHDSI Website** | Main community hub | [ohdsi.org](https://www.ohdsi.org) |
| **OHDSI 2025 Symposium** | Annual global conference | [ohdsi.org/ohdsi2025](https://www.ohdsi.org/ohdsi2025/) |
| **OHDSI GitHub** | Open-source code repositories | [github.com/OHDSI](https://github.com/OHDSI) |
| **The Book of OHDSI** | Comprehensive guide (free online) | [ohdsi.github.io/TheBookOfOhdsi](https://ohdsi.github.io/TheBookOfOhdsi/) |
| **OHDSI Forums** | Community Q&A and discussions | [forums.ohdsi.org](https://forums.ohdsi.org) |
| **OHDSI YouTube** | Tutorials and presentations | [youtube.com/@OHDSI](https://www.youtube.com/@OHDSI) |

### Tools & Documentation

| Tool | Purpose | Link |
|------|---------|------|
| **Athena** | Browse and download vocabularies | [athena.ohdsi.org](https://athena.ohdsi.org) |
| **Atlas** | Web-based cohort building and study design | [atlas-demo.ohdsi.org](https://atlas-demo.ohdsi.org) |
| **HADES** | Health Analytics Data-to-Evidence Suite (R packages) | [ohdsi.github.io/Hades](https://ohdsi.github.io/Hades/) |
| **OMOP CDM** | Common Data Model documentation | [ohdsi.github.io/CommonDataModel](https://ohdsi.github.io/CommonDataModel/) |
| **Data Quality Dashboard** | Validate your OMOP CDM conversion | [ohdsi.github.io/DataQualityDashboard](https://ohdsi.github.io/DataQualityDashboard/) |
| **ACHILLES** | Database characterization and visualization | [ohdsi.github.io/Achilles](https://ohdsi.github.io/Achilles/) |

### Standardized Vocabularies

| Vocabulary | Domain | Link |
|------------|--------|------|
| **SNOMED-CT** | Clinical findings, diseases, procedures | [snomed.org](https://www.snomed.org/) |
| **RxNorm** | Medications and drug products | [nlm.nih.gov/rxnorm](https://www.nlm.nih.gov/research/umls/rxnorm/) |
| **LOINC** | Laboratory tests and measurements | [loinc.org](https://loinc.org/) |
| **ICD-10** | Diagnosis classification | [who.int/icd](https://www.who.int/standards/classifications/classification-of-diseases) |
| **CPT** | Procedure codes | [ama-assn.org/cpt](https://www.ama-assn.org/practice-management/cpt) |

### Getting Involved

| Activity | Description | Link |
|----------|-------------|------|
| **Working Groups** | Join specialized community groups | [ohdsi.org/working-groups](https://www.ohdsi.org/working-groups/) |
| **Regional Chapters** | Connect with local OHDSI communities | [ohdsi.org/regional-chapters](https://www.ohdsi.org/who-we-are/regional-chapters/) |
| **Study-a-thons** | Collaborative research events | [ohdsi.org/studyathon](https://www.ohdsi.org/studyathon/) |
| **OHDSI Network Studies** | Participate in global research | [ohdsi.org/network-studies](https://www.ohdsi.org/network-research-studies/) |

### Key GitHub Repositories

| Repository | Description |
|------------|-------------|
| [OHDSI/CommonDataModel](https://github.com/OHDSI/CommonDataModel) | OMOP CDM specifications and DDL scripts |
| [OHDSI/Athena](https://github.com/OHDSI/Athena) | Vocabulary download and management |
| [OHDSI/Atlas](https://github.com/OHDSI/Atlas) | Web application for cohort building |
| [OHDSI/WebAPI](https://github.com/OHDSI/WebAPI) | Backend services for Atlas |
| [OHDSI/Hades](https://github.com/OHDSI/Hades) | R package ecosystem for analysis |
| [OHDSI/CohortMethod](https://github.com/OHDSI/CohortMethod) | Comparative effectiveness studies |
| [OHDSI/PatientLevelPrediction](https://github.com/OHDSI/PatientLevelPrediction) | Machine learning for patient outcomes |
| [OHDSI/ETL-Synthea](https://github.com/OHDSI/ETL-Synthea) | Convert Synthea data to OMOP CDM |

---

*The next time you see a medication order or lab result in a patient chart, you'll know there's an entire global infrastructure working behind the scenes to make that data meaningful—not just for one patient, but for millions of patients around the world.*

---

**Source**: [OHDSI Introduction Tutorial (YouTube)](https://www.youtube.com/watch?v=lELiY5B27ps)

*Generated using the Feynman Technique: Complex concepts explained simply, with analogies and practical examples.*
