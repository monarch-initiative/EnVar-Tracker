# EnVar: Environmental Variables for Health Outcomes

EnVar is a 12-month project aimed at improving how the **OMOP Common Data Model (CDM)** associates environmental variables with clinical outcomes. We focus on structuring large-scale environmental data into usable "nuggets" within a patient's record to facilitate better health research.

---

## 🎯 Project Scope & Objectives
The primary goal is to improve the OMOP model's ability to handle external exposures without losing metadata.
* **Environmental Micro-schemas:** Using **LinkML** to document environmental CDEs (Common Data Elements).
* **CDM Integration:** Proposing new tables for **External Exposures** and **Location History**.
* **Technical Pipeline:** Integrating data via the **GAIA catalog** and **LinkML-map**.
* **Validation Use Case:** Investigating climate change impacts on HIV diagnoses.

---

## 📂 Key PM Resources
* **[Main Project Drive](https://drive.google.com/drive/folders/0ADJCDDiDri_mUk9PVA)**: All administrative and technical documents.
* **[Scope of Work (SOW)](https://drive.google.com/file/d/1FA5_vDEitwFkncJJf_xXastQWpgyLXwz/view?usp=drive_link)**: Formal project definitions.
* **[Landscape Analysis Doc](https://docs.google.com/document/d/1d4XScW3MMMVdxP-3XDz_ecL27MZjxhR3fsxd6-RVPG4/edit?usp=drive_link)**: Gap analysis and standard mapping.

---

## 🗺️ Roadmap & Milestones
*Note: Technical requirements must be finalized by Oct 1, 2026, to meet OMOP governance windows.*

| Milestone | Deliverable | Target Date | Owner |
| :--- | :--- | :--- | :--- |
| **M1: Foundational Setup** | Infrastructure & Onboarding | Apr 15, 2026 | Corey / Sruthi |
| **M2: Landscape Discovery** | Final Landscape Synthesis Report | May 1, 2026 | Nico / Bryan |
| **M3: Requirements** | Technical & Social Specs | Jun 1, 2026 | Anne / Corey |
| **M4: Schema Drafts** | LinkML v1.0 & ESIP Presentation | Aug 1, 2026 | Madan / Anne |
| **M5: OMOP Governance** | OHDSI CDM Proposal Submission | Oct 1, 2026 | Bryan / Melissa |
| **M6: Pilot Integration** | ETL Pipeline & HIV Pilot Results | Jan 1, 2027 | Corey / Anne |
| **M7: Extension Enablement**| Documentation for Data Providers | Feb 1, 2027 | Nico / Corey |
| **M8: Project Completion** | Toolkit & Final Community Push | Mar 31, 2027 | Anne / Sruthi |

---

## 👥 Project Team
| Name | Core Responsibility |
| :--- | :--- |
| **Anne Thessen** | Project Lead / HIV Use Case Owner |
| **Nico Matentzoglu** | Landscape Analysis Lead |
| **Corey Cox** | Technical Infrastructure & ETL (GAIA/LinkML) |
| **Madan Krishnamurthy** | Micro-schema Research & LinkML Modeling |
| **Bryan Laraway** | OHDSI GIS Liaison & Clinical Standards |
| **Sruthi Magesh** | Operations & Project Management Support |
| **Melissa Haendel** | Strategic Advisor / AOU & CHEL Expert |
| **Julie McMurry** | Administrative & FTE Tracking |

---

## 🛠️ Tech Stack
* **Modeling Language:** [LinkML](https://github.com/linkml/linkml-microschema-profile)
* **ETL Tooling:** LinkML-Map / DMBIP
* **Catalog:** [GAIA Core](https://github.com/OHDSI/gaiaCore)
* **Data Model:** [OMOP CDM (OHDSI)] (https://ohdsi.github.io/TheBookOfOhdsi/)

---

## 📅 Communication & Governance
* **Meeting Cadence:** Monthly "Show & Tell" sessions.
* **Internal Rule:** Slide decks must be submitted to the Drive **one week prior** to the meeting for peer feedback.
* **Sprints:** 2-week technical sprint cycles.

---
*This project is managed under the Monarch Initiative organization.*
