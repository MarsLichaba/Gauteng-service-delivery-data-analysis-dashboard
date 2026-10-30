# Data Lens: Gauteng Municipal Service Delivery Data Analysis Dashboard

> Optimizing municipal service delivery in Gauteng using the GCRO Quality of Life Survey, a Microsoft Access database and a Power BI KPI dashboard.

![Dashboard screenshot](images/dashboard.png)
<!-- Replace with your own screenshot: save it as images/dashboard.png -->

---

## Table of Contents

1. [Overview](#overview)
2. [The Problem](#the-problem)
3. [Key Findings](#key-findings)
4. [VMOSA Framework](#vmosa-framework)
5. [KPI Framework](#kpi-framework)
6. [Database Design](#database-design)
7. [Power BI Dashboard](#power-bi-dashboard)
8. [Methodology](#methodology)
9. [Repository Contents](#repository-contents)
10. [Tools and Technologies](#tools-and-technologies)
11. [Limitations](#limitations)
12. [Data Source](#data-source)
13. [Team](#team)

---

## Overview

Data Lens is a business intelligence project built for the INFO3002A Organisational Data and Databases course at the University of the Witwatersrand. It uses the Gauteng City-Region Observatory (GCRO) Quality of Life survey to help the Gauteng Provincial Government find where municipal services are failing and track whether interventions are working.

The project covers the full BI workflow:

1. Analysing a large, coded survey dataset (~300 columns, ~27,000 rows)
2. Designing and building a normalised relational database in Microsoft Access
3. Defining a strategy (VMOSA) with measurable KPIs
4. Monitoring those KPIs on a single-screen Power BI dashboard

## The Problem

The raw survey data was not ready for analysis. Columns were headed with question numbers instead of meaningful names, and answers were stored as numeric codes (for example, `798` for City of Johannesburg). It had to be cleaned, decoded and restructured before any analysis was possible.

## Key Findings

- **51.5%** of households are dissatisfied with their local municipality, compared with only **37.0%** who are satisfied.
- Dissatisfaction is concentrated in visible infrastructure: street lights (34.8%), roads (34.7%), stormwater (32.6%) and billing (27.8%).
- **44.9%** of residents who contacted government received no response, and only **12.1%** contacted government at all.
- There is a large equity gap between informal and formal dwellings. Dissatisfaction is about **5.6x** higher for sanitation, **5.3x** higher for water and **5.0x** higher for waste.
- Emfuleni stands out as the worst-performing municipality on roads, street lighting and stormwater, and it is the top priority for intervention.

## VMOSA Framework

**Vision:** A Gauteng where all communities have access to reliable, equitable and responsive municipal services that improve residents' quality of life and promote sustainable development.

**Mission:** To improve the quality and reliability of municipal services across Gauteng through targeted infrastructure maintenance, improved municipal accountability and more equitable service delivery.

### Objectives (five-year targets)

| Objective | Goal |
|---|---|
| **O1: Prioritised infrastructure maintenance** | Reduce dissatisfaction with street lights, roads and stormwater by 10 percentage points |
| **O2: Improved communication and accountability** | Raise billing and overall satisfaction by 10 points, and the enquiry response rate by 15 points |
| **O3: Equitable access to basic services** | Reduce water and sanitation dissatisfaction in informal dwellings by 15 percentage points |

### Strategy and Action Plan

| Objective | Action programme | Focus |
|---|---|---|
| O1 | **AP1: Infrastructure Improvement Programme** | Targeted repair of street lighting, roads and stormwater drains, guided by ward-level survey hotspots |
| O2 | **AP2: Municipal Accountability and Communication Programme** | Billing transparency, enquiry-response tracking and standardised response protocols |
| O3 | **AP3: Basic Service Equality Programme** | Targeted water and sanitation upgrades in informal settlements with the largest gaps |

Governance follows a "worst-first" logic: capital and technical capacity go to the lowest-performing hotspots first. The province coordinates strategy and monitoring, and municipalities deliver the programmes.

## KPI Framework

Satisfaction means "Satisfied" or "Very satisfied", and dissatisfaction means "Dissatisfied" or "Very dissatisfied", on a 1-5 Likert scale. "N/A" and missing responses are excluded, and all figures use GCRO survey weights.

| KPI | Measure | Survey question | Baseline | Target |
|---|---|---|---|---|
| KPI1 | Street lighting dissatisfaction | Q1.29 | 34.8% | 24.8% |
| KPI2 | Road dissatisfaction | Q1.28 | 34.7% | 24.7% |
| KPI3 | Stormwater drainage dissatisfaction | Q1.31 | 32.6% | 22.6% |
| KPI4 | Municipal billing satisfaction | Q1.27 | 44.2% | 54.2% |
| KPI5 | Government enquiry response rate | Q6.9 + Q6.10 | 55.1% | 70.1% |
| KPI6 | Informal-dwelling sanitation dissatisfaction | Q1.23 + H.3 | 56.8% | 41.8% |
| KPI7 | Informal-dwelling water dissatisfaction | Q1.22 + H.3 | 41.7% | 26.7% |
| KPI8 | Overall municipal performance satisfaction | Q6.7 | 37.0% | 47.0% |

## Database Design

The relevant survey fields are stored in a central table, with lookup tables that translate the numeric codes into readable values (municipality, dwelling type, satisfaction scale and so on).

![ERD](images/erd.png)
<!-- Add your ERD image here: images/erd.png -->

## Power BI Dashboard

A single-screen dashboard gives one visual per KPI, with a municipality slicer and target lines so progress is visible at a glance.

| KPI | Visual | Why |
|---|---|---|
| KPI1-3 | Bar charts by municipality | Easy to rank municipalities and compare each one with the target line |
| KPI4, KPI5, KPI8 | Gauge charts | A single percentage measured against a target |
| KPI6-7 | Bar charts (informal vs formal) | Shows the size of the gap between dwelling types directly |

<!-- Edit this table so it matches the visuals and justifications in your own submission. -->

## Methodology

1. Reviewed the survey questionnaire and chose municipal service delivery as the focus area.
2. Selected 10-20 relevant columns from the raw survey data.
3. Designed an ERD with a central table and code lookup tables.
4. Built the database in Microsoft Access and imported the data.
5. Applied survey weights and calculated each KPI.
6. Connected Power BI to the Access database and built the dashboard.

## Repository Contents

```
.
├── README.md
├── database/          # Microsoft Access database (.accdb)
├── dashboard/         # Power BI file (.pbix)
├── docs/              # Written report and presentation
└── images/            # Dashboard screenshot and ERD
```
<!-- Adjust this tree to match your actual folders. -->

## Tools and Technologies

- Microsoft Access (database design and data import)
- Power BI (dashboard)
- Microsoft Excel (source data)

## Limitations

- The data comes from the **GCRO QoL III (2013/14)** survey, which covers 27,490 weighted respondents. It is a static baseline, not a current picture.
- Targets are provisional recommendations anchored to that baseline.
- Tracking real progress would need comparable follow-up surveys.

## Data Source

[GCRO Quality of Life Survey dataset](https://docs.google.com/spreadsheets/d/1uoPkIrfFPA_KUH369FIvpwpSglWUTrjP/edit?gid=558633932#gid=558633932)

Survey data from the [Gauteng City-Region Observatory](https://gcro.ac.za), a partnership between the University of Johannesburg, the University of the Witwatersrand and the Gauteng Provincial Government.

## Team

- Zarmeen Ismail
- Klaas Maseogane
- Mavuyisi Chabane
- Mosa Lichaba

*INFO3002A, University of the Witwatersrand, 2026*(https://docs.google.com/spreadsheets/d/1uoPkIrfFPA_KUH369FIvpwpSglWUTrjP/edit?gid=558633932#gid=558633932)
