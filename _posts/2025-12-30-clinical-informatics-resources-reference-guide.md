---
layout: post
title: "Clinical Informatics Resources: A Comprehensive Reference Guide"
subtitle: "Essential Links for OHDSI, FHIR, Clinical Data, and Healthcare AI"
date: 2025-12-30
author: DataGodzilla
categories: [resources]
tags: [ohdsi, fhir, omop-cdm, nlp, healthcare-ai, resources, tutorial]
toc: true
description: "A curated collection of essential resources for clinical informatics covering OHDSI tools, FHIR/HL7 standards, clinical data management, and healthcare NLP/AI."
reading_time: 15
pinned_bottom: true
---

This reference guide provides a curated collection of essential resources for clinical informatics professionals, researchers, and developers. Navigate to the section most relevant to your work.

---

## OHDSI Resources

Resources for Observational Health Data Sciences and Informatics (OHDSI) tools, OMOP CDM, and observational research.

### Official Documentation
- [OHDSI Website](https://ohdsi.org/) - Official OHDSI community portal
- [The Book of OHDSI](https://ohdsi.github.io/TheBookOfOhdsi/) - Comprehensive open-source textbook
- [OHDSI GitHub](https://github.com/ohdsi) - Open-source repositories
- [OMOP CDM Documentation](https://ohdsi.github.io/CommonDataModel/) - Common Data Model specification

### Vocabulary Resources
- [ATHENA](https://athena.ohdsi.org/) - OHDSI vocabulary repository
- [PHOEBE](https://github.com/OHDSI/Phoebe) - Vocabulary exploration tool
- [USAGI](https://github.com/OHDSI/Usagi) - Source code mapping tool

### Data Characterization Tools
- [ACHILLES](https://github.com/OHDSI/Achilles) - Automated database profiling
- [Data Quality Dashboard](https://github.com/OHDSI/DataQualityDashboard) - CDM data quality checks
- [ARES](https://github.com/OHDSI/Ares) - Analysis results viewer

### Analysis Tools
- [ATLAS](https://github.com/OHDSI/Atlas) - Web-based analysis platform
- [WebAPI](https://github.com/OHDSI/WebAPI) - RESTful services for ATLAS
- [HADES](https://ohdsi.github.io/Hades/) - Health Analytics Data-to-Evidence Suite

### Patient-Level Prediction
- [PatientLevelPrediction](https://ohdsi.github.io/PatientLevelPrediction/) - ML prediction models
- [CohortMethod](https://ohdsi.github.io/CohortMethod/) - Comparative effectiveness studies
- [SelfControlledCaseSeries](https://ohdsi.github.io/SelfControlledCaseSeries/) - SCCS analysis

### ETL Tools
- [WhiteRabbit](https://github.com/OHDSI/WhiteRabbit) - Source data profiling
- [Rabbit-in-a-Hat](https://github.com/OHDSI/WhiteRabbit) - ETL design tool
- [ETL-Synthea](https://github.com/OHDSI/ETL-Synthea) - Synthea to OMOP ETL

### Database Connectors
- [DatabaseConnector](https://github.com/OHDSI/DatabaseConnector) - R database connectivity
- [SqlRender](https://github.com/OHDSI/SqlRender) - SQL dialect translation
- [Eunomia](https://github.com/OHDSI/Eunomia) - Test CDM database

### Learning & Community
- [OHDSI Tutorials](https://www.ohdsi.org/past-events/) - Video tutorials from symposiums
- [OHDSI Forums](https://forums.ohdsi.org/) - Community discussion
- [OHDSI Workgroups](https://ohdsi.org/workgroups/) - Specialized working groups
- [EHDEN Academy](https://academy.ehden.eu/) - Free online courses

---

## FHIR & HL7 Resources

Resources for healthcare interoperability standards including FHIR, HL7, and clinical terminologies.

### FHIR Specifications
- [FHIR Official Site](https://hl7.org/fhir/) - HL7 FHIR specification
- [FHIR R4 (Current)](https://hl7.org/fhir/R4/) - R4 specification
- [FHIR R5 (Latest)](https://hl7.org/fhir/R5/) - R5 specification
- [FHIR Shorthand](https://build.fhir.org/ig/HL7/fhir-shorthand/) - FSH for authoring IGs

### HL7 Standards
- [HL7 International](https://www.hl7.org/) - HL7 organization
- [HL7 v2 Reference](http://www.hl7.eu/HL7v2x/index.html) - HL7 v2 messages
- [CDA (C-CDA)](https://www.hl7.org/implement/standards/product_brief.cfm?product_id=7) - Clinical Document Architecture

### Clinical Terminologies
- [LOINC](https://loinc.org/) - Laboratory observations codes
- [SNOMED CT](https://www.snomed.org/) - Clinical terminology
- [RxNorm](https://www.nlm.nih.gov/research/umls/rxnorm/) - Drug terminology
- [ICD-10-CM](https://www.cms.gov/medicare/coding-billing/icd-10-codes) - Diagnosis codes
- [CPT](https://www.ama-assn.org/amaone/cpt-current-procedural-terminology) - Procedure codes
- [UMLS](https://www.nlm.nih.gov/research/umls/) - Unified Medical Language System

### Implementation Guides
- [US Core IG](https://hl7.org/fhir/us/core/) - US Core profiles
- [USCDI](https://www.healthit.gov/isa/united-states-core-data-interoperability-uscdi) - US Core Data for Interoperability
- [Da Vinci Project](https://www.hl7.org/davinci/) - Payer-provider exchange
- [Bulk Data Access](https://hl7.org/fhir/uv/bulkdata/) - Backend services
- [SMART on FHIR](https://docs.smarthealthit.org/) - App authorization
- [CDS Hooks](https://cds-hooks.org/) - Clinical decision support

### Developer Tools
- [FHIR Validator](https://www.hl7.org/fhir/validation.html) - Resource validation
- [Inferno](https://inferno.healthit.gov/) - US Core testing
- [Touchstone](https://touchstone.aegis.net/) - FHIR testing platform

### FHIR Servers
- [HAPI FHIR](https://hapifhir.io/) - Open-source Java server
- [Microsoft FHIR Server](https://github.com/microsoft/fhir-server) - Azure FHIR
- [Google Cloud Healthcare API](https://cloud.google.com/healthcare-api) - GCP FHIR

### Development Libraries
- [HAPI FHIR (Java)](https://hapifhir.io/hapi-fhir/docs/) - Java library
- [fhir.resources (Python)](https://pypi.org/project/fhir.resources/) - Python models
- [fhirclient (Python)](https://github.com/smart-on-fhir/client-py) - SMART client

### Learning Resources
- [FHIR DevDays](https://www.devdays.com/) - Annual conference
- [HL7 FHIR Fundamentals](https://www.hl7.org/training/courses.cfm) - Official training
- [FHIR Chat (Zulip)](https://chat.fhir.org/) - Community chat

---

## Clinical Data Resources

Resources for clinical data management, ETL processes, data quality, and common data models.

### Common Data Models
- [OMOP CDM Specification](https://ohdsi.github.io/CommonDataModel/) - Official documentation
- [OMOP CDM Wiki](https://github.com/OHDSI/CommonDataModel/wiki) - GitHub wiki
- [PCORnet CDM](https://pcornet.org/data/) - PCORnet Common Data Model
- [i2b2 Data Model](https://www.i2b2.org/software/) - Informatics for Integrating Biology and the Bedside
- [Sentinel CDM](https://www.sentinelinitiative.org/) - FDA Sentinel System
- [CDISC Standards](https://www.cdisc.org/) - Clinical trial data standards

### ETL Platforms
- [Apache Airflow](https://airflow.apache.org/) - Workflow orchestration
- [Prefect](https://www.prefect.io/) - Modern data orchestration
- [dbt (data build tool)](https://www.getdbt.com/) - Data transformation
- [Great Expectations](https://greatexpectations.io/) - Data validation

### Data Quality Frameworks
- [Data Quality Dashboard](https://github.com/OHDSI/DataQualityDashboard) - OHDSI DQD
- [Kahn Framework](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5051581/) - DQ dimensions
- [DAMA DMBOK](https://www.dama.org/cpages/body-of-knowledge) - Data management body of knowledge

### Synthetic Data
- [Synthea](https://synthetichealth.github.io/synthea/) - Synthetic patient generator
- [Eunomia](https://github.com/OHDSI/Eunomia) - OMOP test database
- [Faker](https://faker.readthedocs.io/) - General fake data

### Privacy & De-identification
- [ARX](https://arx.deidentifier.org/) - Data anonymization
- [HIPAA Safe Harbor](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/) - De-identification standard

### Databases & Tools
- [PostgreSQL](https://www.postgresql.org/) - Popular OHDSI backend
- [DBeaver](https://dbeaver.io/) - Universal database tool
- [pgAdmin](https://www.pgadmin.org/) - PostgreSQL admin

---

## Healthcare NLP & AI Resources

Resources for clinical natural language processing, machine learning, and healthcare AI.

### Pre-trained Clinical Models
- [BioBERT](https://github.com/dmis-lab/biobert) - Biomedical BERT
- [ClinicalBERT](https://github.com/EmilyAlsentzer/clinicalBERT) - Clinical notes BERT
- [PubMedBERT](https://huggingface.co/microsoft/BiomedNLP-PubMedBERT-base-uncased-abstract-fulltext) - PubMed pre-trained
- [SciBERT](https://github.com/allenai/scibert) - Scientific text BERT
- [GatorTron](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/clara/models/gatortron_og) - Large clinical LLM

### Clinical NLP Tools
- [MedSpaCy](https://github.com/medspacy/medspacy) - Clinical NLP with spaCy
- [scispaCy](https://allenai.github.io/scispacy/) - Scientific/biomedical spaCy
- [cTAKES](https://ctakes.apache.org/) - Apache clinical NLP
- [MedCAT](https://github.com/CogStack/MedCAT) - Medical concept annotation
- [QuickUMLS](https://github.com/Georgetown-IR-Lab/QuickUMLS) - Fast UMLS matching
- [MetaMap](https://metamap.nlm.nih.gov/) - NLM concept extraction

### General NLP Libraries
- [Hugging Face Transformers](https://huggingface.co/transformers/) - Transformer models
- [spaCy](https://spacy.io/) - Industrial NLP
- [NLTK](https://www.nltk.org/) - NLP toolkit

### Clinical Datasets
- [MIMIC-III/IV](https://mimic.mit.edu/) - ICU clinical notes
- [i2b2 NLP Challenges](https://www.i2b2.org/NLP/DataSets/) - Annotated clinical text
- [n2c2 (formerly i2b2)](https://n2c2.dbmi.hms.harvard.edu/) - NLP challenges
- [PubMed](https://pubmed.ncbi.nlm.nih.gov/) - Biomedical literature

### ML Frameworks & Tools
- [scikit-learn](https://scikit-learn.org/) - General ML
- [PyTorch](https://pytorch.org/) - Deep learning
- [MLflow](https://mlflow.org/) - ML lifecycle
- [Weights & Biases](https://wandb.ai/) - Experiment tracking

### Model Interpretability
- [SHAP](https://github.com/slundberg/shap) - Feature importance
- [LIME](https://github.com/marcotcr/lime) - Local explanations
- [InterpretML](https://interpret.ml/) - Microsoft interpretability

### Research Venues
- [JAMIA](https://academic.oup.com/jamia) - Journal of AMIA
- [npj Digital Medicine](https://www.nature.com/npjdigitalmed/) - Nature
- [Papers With Code - Medical](https://paperswithcode.com/area/medical) - Medical ML papers

### Learning Resources
- [Hugging Face Course](https://huggingface.co/course/) - Transformers course
- [Fast.ai](https://www.fast.ai/) - Practical Deep Learning
- [MedSpaCy Tutorials](https://github.com/medspacy/medspacy/tree/master/notebooks) - Clinical NLP

---

## Related Posts on This Blog

### OHDSI
- [OHDSI Introduction: From Real-World Data to Reliable Evidence](/blog/ohdsi-introduction-real-world-data-reliable-evidence/)
- [From EHR Chaos to Research-Ready Data: A Complete OHDSI Learning Journey](/blog/ohdsi-learning-journey/)
- [Mastering ATLAS Cohort Definitions](/blog/mastering-atlas-cohort-definitions/)
- [Predicting GI Hemorrhage with OHDSI PLP](/blog/predicting-gi-hemorrhage-ohdsi-plp/)

### FHIR & Interoperability
- [From HL7 Pipes to FHIR APIs: Clinical Laboratory Interoperability](/blog/HL7-FHIR-Clinical-Lab-Interoperability/)
- [Healthcare Interoperability: FHIR, HL7, LOINC, SNOMED-CT](/blog/Healthcare-Interoperability-FHIR-HL7-LOINC-SNOMED-CT/)

---

*This resource page is regularly updated. Last updated: December 30, 2025.*
