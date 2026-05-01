# EnVar Monthly Progress Report

**Reporting Period:** April 1 – April 30, 2026 &nbsp;|&nbsp; **Project:** [EnVar](https://github.com/monarch-initiative/EnVar-Tracker) &nbsp;|&nbsp; **Project Board:** [Board View](https://github.com/orgs/monarch-initiative/projects/131/views/1)

---

## Deliverable Status

<table>
<thead>
<tr>
<th width="70">Deliverable ID</th>
<th width="170">Deliverable Title</th>
<th width="160">Description</th>
<th width="170">Milestone</th>
<th width="80">Status</th>
<th width="80">Due Date</th>
<th width="320">Progress Update</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center"><a href="https://github.com/monarch-initiative/EnVar-Tracker/issues/1">D1.1</a></td>
<td>Project Infrastructure &amp; Governance Hub</td>
<td><details><summary>View</summary>Establishment of the central technical and administrative coordination points. This includes the EnVar GitHub repository under the Monarch Initiative organization, a standardized Google Drive folder hierarchy, and the configuration of the CLAD Slack channel for daily operations.</details></td>
<td>Milestone 1 – Foundational Setup &amp; Onboarding</td>
<td align="center">Complete</td>
<td align="center">Apr 8, 2026</td>
<td><strong>Progress Report – April 14:</strong><br>• Created EnVar GitHub repository under the Monarch Initiative organization: https://github.com/monarch-initiative/envar<br>• Created Milestones &amp; Deliverables Tracker in GitHub: https://github.com/monarch-initiative/EnVar-Tracker<br>• Created Google Drive folder: https://drive.google.com/drive/folders/0ADJCDDiDri_mUk9PVA<br>• Created CLAD Slack channel for daily operations: niehs-standards</td>
</tr>
<tr>
<td align="center"><a href="https://github.com/monarch-initiative/EnVar-Tracker/issues/2">D1.2</a></td>
<td>Environment &amp; Data Access Provisioning</td>
<td><details><summary>View</summary>Successful onboarding of technical leads (Corey and Madan) to the CLAD/All of Us (AOU) environment. This ensures the team has the necessary permissions to access the CHEL dataset and existing environmental ETL pipelines.</details></td>
<td>Milestone 1 – Foundational Setup &amp; Onboarding</td>
<td align="center">Deprecated</td>
<td align="center">Apr 21, 2026</td>
<td><strong>Progress Report – April 24:</strong><br>We cannot onboard them to CLAD as they need to be paid staff to access the DLP platform. This was decided by Melissa and Julie. Deprecating this issue.</td>
</tr>
<tr>
<td align="center"><a href="https://github.com/monarch-initiative/EnVar-Tracker/issues/3">D2.1</a></td>
<td>Environmental Data Standards Landscape Report</td>
<td><details><summary>View</summary>A synthesized report led by Nico, documenting existing work by the OHDSI GIS group, Epic "Healthy Planet" SDOH modules, and Monarch-affiliated geospatial projects. It identifies current methods for linking geospatial data to clinical outcomes.</details></td>
<td>Milestone 2 – Landscape Discovery &amp; Gap Analysis</td>
<td align="center">In Progress</td>
<td align="center">Apr 24, 2026</td>
<td><strong>Progress Report – April 28:</strong><br>Work on Deliverable 2.1 is progressing steadily, with the landscape analysis now moving from broad identification to technical synthesis. To date, we have documented the emerging OHDSI GIS extension standards, specifically the structural utility of the new External Exposure and Location History tables, while simultaneously evaluating the integration of patient specific data from Epic's Healthy Planet SDOH modules. A critical finding of this report is the "metadata loss" phenomenon, where high resolution environmental metrics, such as spatial uncertainty and temporal aggregation methods, are often stripped away during clinical data ingestion. To address this, we are currently documenting the use of microschemas as a standardized intermediary. By coordinating with Monarch affiliated projects like SOMA and CMDR, the report now identifies two primary methods for linking geospatial data to outcomes: a direct OMOP integration via the Gaia catalog and a "pre-standardized" pipeline designed to preserve granular environmental metadata before it enters the clinical model.</td>
</tr>
<tr>
<td align="center"><a href="https://github.com/monarch-initiative/EnVar-Tracker/issues/4">D2.2</a></td>
<td>OMOP-GIS Technical Audit</td>
<td><details><summary>View</summary>A technical review of current OMOP CDM extensions and the GAIA catalog. This document identifies why current OHDSI approaches are "inadequate" for complex environmental "nuggets" and sets the baseline for required model changes.</details></td>
<td>Milestone 2 – Landscape Discovery &amp; Gap Analysis</td>
<td align="center">In Progress</td>
<td align="center">May 1, 2026</td>
<td><strong>Progress Report – April 28:</strong><br>Work on Deliverable 2.2 is currently in progress, with a substantial technical audit shared during the recent project meeting. We have completed a review of the emerging OMOP CDM GIS extension, documenting the utility of the new External Exposure and Location History tables alongside new vocabularies for GIS, Expozone, and SDOH. A primary outcome of this audit is the formal identification of why current OHDSI approaches are inadequate for complex environmental data: specifically, the "metadata loss" that occurs when high resolution spatial and temporal metrics, such as uncertainty values and grid resolution, are stripped away during ingestion into standard clinical tables. To set the baseline for required model changes, the team has moved into an active prototyping phase, selecting two critical NIEHS data sources to demonstrate a full pipeline that preserves these essential environmental "nuggets" before they enter the Gaia catalog.</td>
</tr>
</tbody>
</table>

---

## Summary

-
-
-

## Plans for Next Month

-
-
-
