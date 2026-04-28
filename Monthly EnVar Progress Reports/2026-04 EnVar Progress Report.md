# EnVar Monthly Progress Report

**Reporting Period:** April 1 – April 30, 2026
**Project:** [EnVar](https://github.com/monarch-initiative/EnVar-Tracker)
**Project Board:** [Board View](https://github.com/orgs/monarch-initiative/projects/131/views/1)
**Generated:** 2026-04-28

---

## Deliverable Status

> **Filter applied:** Deliverables due this month (M1 milestone: Apr 15), currently In Progress, or overdue and not yet complete.

| Deliverable | Description | Milestone | Status | Projected Completion | Report Update | Plans for Next Month |
| :--- | :--- | :--- | :---: | :---: | :--- | :--- |
| **D1.1** [Project Infrastructure & Governance Hub](https://github.com/monarch-initiative/EnVar-Tracker/issues/1) | Establishment of central technical and administrative coordination points: GitHub repo, Google Drive folder hierarchy, and CLAD Slack channel for daily operations. | M1 – Foundational Setup & Onboarding | ✅ Complete | 2026-04-08 | **Apr 14:** Created EnVar GitHub repo, Milestones & Deliverables Tracker, Google Drive folder, and CLAD Slack channel (`niehs-standards`). | — |
| **D1.2** [Environment & Data Access Provisioning](https://github.com/monarch-initiative/EnVar-Tracker/issues/2) | Successful onboarding of technical leads (Corey and Madan) to the CLAD/All of Us (AOU) environment to access the CHEL dataset and environmental ETL pipelines. | M1 – Foundational Setup & Onboarding | ~~Deprecated~~ | 2026-04-21 | **Apr 24:** Onboarding to CLAD is not possible — technical leads must be paid staff to access the DLP platform. Decision made by Melissa and Julie. Issue deprecated. | — |
| **D2.1** [Environmental Data Standards Landscape Report](https://github.com/monarch-initiative/EnVar-Tracker/issues/3) | A synthesized report documenting existing work by the OHDSI GIS group, Epic "Healthy Planet" SDOH modules, and Monarch-affiliated geospatial projects identifying current methods for linking geospatial data to clinical outcomes. | M2 – Landscape Discovery & Gap Analysis | 🚨 Overdue | 2026-04-24 | **Apr 28:** Analysis progressing from broad identification to technical synthesis. Documented OHDSI GIS extension standards (External Exposure and Location History tables) and Epic SDOH modules. Key finding: "metadata loss" during clinical ingestion. Microschemas identified as standardized intermediary. Two primary linking methods identified via SOMA/CMDR coordination: direct OMOP integration via Gaia catalog and a pre-standardized pipeline to preserve environmental metadata. | — |
| **D2.2** [OMOP-GIS Technical Audit](https://github.com/monarch-initiative/EnVar-Tracker/issues/4) | A technical review of current OMOP CDM extensions and the GAIA catalog identifying why current OHDSI approaches are inadequate for complex environmental "nuggets" and setting the baseline for required model changes. | M2 – Landscape Discovery & Gap Analysis | 🔄 In Progress | 2026-05-01 | **Apr 28:** Substantial audit shared at project meeting. Completed review of OMOP CDM GIS extension (External Exposure, Location History tables; GIS/Expozone/SDOH vocabularies). Formally identified "metadata loss" as primary inadequacy in current OHDSI approaches. Active prototyping phase begun — two NIEHS data sources selected to demonstrate a full pipeline preserving environmental "nuggets" before Gaia catalog ingestion. | — |

---

## Summary

**Total deliverables tracked this period:** 4
**Complete:** 1 &nbsp;|&nbsp; **In Progress:** 1 &nbsp;|&nbsp; **Overdue:** 1 &nbsp;|&nbsp; **Deprecated:** 1

April marked the project's launch month, with Milestone 1 substantially completed — infrastructure is in place and the AOU access blocker was resolved by deprecating that deliverable. Landscape analysis work (M2) is actively underway with rich technical findings already documented, though D2.1 has slipped past its April 24 projected date. Looking ahead to May, D2.2 is due May 1 and flagged 🔥 Urgent, and the team should begin planning for M3 Requirements deliverables (D3.1 due May 22, D3.2 due June 1) which are both flagged 🔥 Urgent and not yet started.
