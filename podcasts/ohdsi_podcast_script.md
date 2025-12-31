---
layout: page
title: "OHDSI Introduction Podcast Transcript"
description: "Full transcript of the OHDSI podcast episode: From Real-World Data to Reliable Evidence"
permalink: /podcasts/ohdsi_podcast_script/
---

**Episode**: From Real-World Data to Reliable Evidence
**Duration**: ~18 minutes
**Style**: Conversational, Educational
**Hosts**: Alex (Host) and Sam (Expert)

[Listen to the audio](/assets/audio/ohdsi_podcast.mp3) | [Back to article](/blog/ohdsi-introduction-real-world-data-reliable-evidence/)

---

## [INTRO - 0:00]

**Alex**: Welcome to the Healthcare Data Deep Dive podcast! I'm Alex, and today we're exploring something that could fundamentally change how we understand health and disease—it's called OHDSI, and if you work with healthcare data or clinical research, you're going to want to pay attention.

**Sam**: Hey everyone! I'm Sam, and I've been working in the OHDSI community for a few years now. I remember my first introduction to this world—I was completely overwhelmed. But today, we're going to break it all down in a way that actually makes sense.

**Alex**: Perfect. So Sam, let's start with the basics. What exactly is OHDSI?

---

## [SEGMENT 1: What is OHDSI? - 1:30]

**Sam**: Great question. OHDSI stands for Observational Health Data Sciences and Informatics. It's a global community—and I mean truly global, we're talking 4,750 plus collaborators across 88 countries and six continents.

**Alex**: That's massive! When was it founded?

**Sam**: 2014, with Columbia University as the central coordinating hub. But here's what makes OHDSI special—it's not a company, it's not a product. It's an open-source collaborative where researchers, data scientists, clinicians, and companies all work together toward a common goal.

**Alex**: And what is that goal?

**Sam**: The mission is beautifully simple: "Improve health by empowering a community to collaboratively generate evidence that promotes better health decisions and better care." Basically, we want to turn messy real-world healthcare data into reliable clinical evidence that actually helps patients.

---

## [SEGMENT 2: The Data Problem - 3:30]

**Alex**: Okay, but why do we need something like OHDSI? Can't hospitals just analyze their own data?

**Sam**: Ah, here's where it gets interesting. Let me paint a picture for you. Imagine you're a researcher who wants to know: "Does this new diabetes drug cause more heart problems than the older one?" To answer that, you'd need data from multiple hospitals, right? The more data, the better your evidence.

**Alex**: That makes sense.

**Sam**: But here's the problem—Hospital A uses Epic, Hospital B uses Cerner. Hospital A codes medications using RxNorm, Hospital B uses a different system. Hospital A is in the US with ICD-10, Hospital B might be in Europe with different standards. It's like trying to have a conversation where everyone is speaking a different language!

**Alex**: So you can't just combine the data?

**Sam**: Exactly! Without standardization, every time you want to collaborate, you're starting from scratch. You're writing new code, figuring out their data structure, mapping their codes to yours—it's expensive, time-consuming, and error-prone.

**Alex**: I love the analogy from the tutorial—the electrical outlet thing.

**Sam**: Oh yes! Think about your laptop. It works the same everywhere in the world, right? But if you travel internationally, you need different adapters because every country has different electrical outlets. The US has one type, the UK has another, Europe has another.

**Alex**: And OHDSI provides a universal adapter?

**Sam**: Exactly! The OMOP Common Data Model is like a universal adapter for healthcare data. Once everyone converts their data to this common format, all the tools and analyses work everywhere.

---

## [SEGMENT 3: OMOP Common Data Model - 6:00]

**Alex**: So let's dig into this OMOP thing. What does it stand for?

**Sam**: OMOP stands for Observational Medical Outcomes Partnership. It was actually a five-year US government project that ended before OHDSI was born. The project's main output was this Common Data Model—basically, a standardized way to organize healthcare data.

**Alex**: And OHDSI picked it up from there?

**Sam**: Right. When OMOP ended, the scientists involved didn't want to stop. They wanted to continue the work with a broader scope—not just studying drug effects, but all kinds of observational research. That's when OHDSI was born, and they've been maintaining and evolving the OMOP CDM ever since.

**Alex**: What makes the data model "patient-centric"?

**Sam**: Great catch—that's one of the key principles. In OMOP, everything revolves around the patient. The PERSON table is at the center, and all other data—visits, conditions, drugs, procedures, lab tests—connects back to that person. It's designed specifically for research about people, not for billing or insurance processing.

---

## [SEGMENT 4: Standardized Vocabularies - 8:00]

**Alex**: Now I hear there are millions of concepts in this system. What's that about?

**Sam**: This is the secret sauce of OMOP—the standardized vocabularies. Imagine having a master dictionary that can translate between every healthcare coding system in the world.

**Alex**: Every coding system?

**Sam**: Well, 142 of them! We're talking SNOMED-CT for clinical conditions, RxNorm for medications, LOINC for lab tests, ICD-10 for diagnosis codes, CPT for procedures. All of these get mapped to what we call "standard concepts."

**Alex**: Give me an example.

**Sam**: Sure. Let's take Ciprofloxacin—it's a common antibiotic. Hospital A might code it as RxNorm 2551. Hospital B might code it as HMOG 104. Different numbers, right? But in OMOP, both of these get mapped to the same Standard Concept ID: 1797513. Now suddenly both hospitals are speaking the same language!

**Alex**: And there's a tool to browse all these concepts?

**Sam**: Yes—it's called Athena, at athena.ohdsi.org. You can search for any clinical concept, see what codes map to it, and even download the entire vocabulary to load into your own database. And here's the best part—it's completely free!

---

## [SEGMENT 5: Study Types - 10:30]

**Alex**: Okay, so we've got standardized data. Now what can we actually do with it?

**Sam**: OHDSI focuses on three main types of studies. First is Characterization—basically answering "who are these patients?" What are the demographics? What medications do they take? What's the natural progression of their disease?

**Alex**: Like patient profiling?

**Sam**: Exactly. The second type is Estimation—this is where it gets really powerful. We're asking "does treatment A cause outcome B?" Does this drug cause heart problems? Is one treatment safer than another?

**Alex**: Isn't that what clinical trials do?

**Sam**: Yes, but clinical trials are small, expensive, and take years. With OHDSI, we can use real-world data from millions of patients to study these questions much faster. Of course, there are statistical challenges to address—confounding factors and such—but that's where our methods come in.

**Alex**: And the third type?

**Sam**: Prediction—answering "what will happen to this specific patient?" Building risk models using machine learning. What's this patient's risk of heart attack in the next five years? Will they be readmitted within 30 days?

---

## [SEGMENT 6: Real-World Example - 12:30]

**Alex**: Can you give us a concrete example?

**Sam**: Sure. There was a study on fluoroquinolones—these are common antibiotics like Ciprofloxacin that doctors prescribe for UTIs. Some researchers noticed that patients taking these drugs seemed to have more aortic aneurysms—that's when the main artery from your heart bulges dangerously.

**Alex**: That sounds serious.

**Sam**: Very serious—it can be fatal. So the question was: does taking these common antibiotics actually increase your risk of this rare but dangerous outcome?

**Alex**: How did OHDSI approach this?

**Sam**: They assembled the building blocks. Fourteen databases, all converted to OMOP. Phenotypes—basically algorithms to find patients who took fluoroquinolones, patients who had UTIs, patients who had aortic events. A standardized study design. Rigorous statistical methods to control for confounding. And open-source tools to run the analysis.

**Alex**: And all of this could run across fourteen sites?

**Sam**: That's the magic. Because everyone uses the same data model, the same analysis code can run at each site. The results get combined—it's called federated analysis—without ever sharing patient-level data.

---

## [SEGMENT 7: Tools of the Trade - 14:30]

**Alex**: Speaking of tools, what are the main ones in the OHDSI ecosystem?

**Sam**: There are a few key ones. Athena we already mentioned—that's for vocabularies. Then there's Atlas, which is a web-based application for designing studies. You can build cohort definitions—finding specific patient populations—without writing any code.

**Alex**: No programming required?

**Sam**: Not for basic cohort building! Atlas has a visual interface. Of course, for complex analyses, you'll want HADES—that's a suite of R packages. CohortMethod for comparative effectiveness studies, PatientLevelPrediction for building risk models, CohortDiagnostics for validating your cohort definitions.

**Alex**: And there's something called Strategus?

**Sam**: Yes—Strategus is the orchestration layer. It ties all the HADES packages together so you can run a complete study end-to-end in a reproducible way. Very important for regulatory-grade evidence.

---

## [SEGMENT 8: Getting Involved - 16:00]

**Alex**: This all sounds amazing, but how does someone actually get involved?

**Sam**: This is my favorite part because the community is incredibly welcoming. You don't have to be an expert! There are working groups you can join—CDM, Vocabularies, HADES, Phenotypes—and you can just show up, listen, and learn.

**Alex**: You don't have to contribute right away?

**Sam**: Not at all. Roger Carlson, one of the speakers in the original tutorial, said he joined multiple working groups when he was new. He just listened, asked questions—even "naive" questions—and gradually learned. Now, seven years later, he's teaching the intro class!

**Alex**: That's a great trajectory.

**Sam**: The community has what I call a "secret agenda"—they want to expose you to different topics, get you excited about something, and then hope you take action to join. Whatever area interests you—data modeling, vocabulary mapping, statistics, clinical applications—there's a place for you.

---

## [OUTRO - 17:30]

**Alex**: Sam, this has been incredibly enlightening. Any final thoughts for our listeners?

**Sam**: Just remember—you don't have to understand everything at once. OHDSI is huge, and no one person does all of it. Pick the piece that interests you, dive in, and the rest will come over time.

**Alex**: Where can people learn more?

**Sam**: Start with ohdsi.org—that's the main website. The Book of OHDSI is a fantastic free resource at ohdsi.github.io/TheBookOfOhdsi. And the forums at forums.ohdsi.org are super active and friendly.

**Alex**: Perfect. Thanks so much, Sam, and thanks to all our listeners. Until next time—keep diving deep into that healthcare data!

**Sam**: Thanks everyone!

---

**Total Runtime**: ~18 minutes
