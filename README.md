# 🛡️ CBL LU Sukkur Plant — HSE Management System & Database Dashboard

[![Domain](https://img.shields.io/badge/Domain-HSE%20%26%20KPI%20Analytics-991B1B?style=for-the-badge)](#%E2%B8%8F-overview--problem-statement)
[![Organization](https://img.shields.io/badge/Plant-Continental%20Biscuits%20Limited-D97706?style=for-the-badge)](#%E2%B8%8F-overview--problem-statement)
[![Stack](https://img.shields.io/badge/Architecture-Full--Stack%20Web-0F766E?style=for-the-badge)](#%EF%B8%8F-detailed-tech-stack)
[![GitHub](https://img.shields.io/badge/GitHub-nishali26-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/nishali26)

A centralized, data-driven **Health, Safety & Environment (HSE) Management System and Database Dashboard** designed for **Continental Biscuits Limited (CBL) – LU Sukkur Plant** to digitize workplace safety reporting, streamline Corrective & Preventive Actions (CAPA), and provide real-time KPI visibility for supervisors and management.

---

## 📋 Table of Contents

- [Overview & Problem Statement](#-overview--problem-statement)
- [Why Digitization Matters](#-why-digitization-matters)
- [Current Workflow vs. Gap Analysis](#-current-workflow-vs-gap-analysis)
- [Proposed Solution & System Architecture](#-proposed-solution--system-architecture)
- [Proposed End-to-End Digital Workflow](#-proposed-end-to-end-digital-workflow)
- [Core HSE Modules & Standard Pattern](#-core-hse-modules--standard-pattern)
- [Dashboard & KPI Monitoring Layer](#-dashboard--kpi-monitoring-layer)
- [Detailed Tech Stack](#-detailed-tech-stack)
- [Interactive UI & CSS Styling Architecture](#-interactive-ui--css-styling-architecture)
- [Expected Benefits](#-expected-benefits)
- [Repository Structure & Local Setup](#-repository-structure--local-setup)
- [Role & Contribution](#-role--contribution)

---

## 🎯 Overview & Problem Statement

In industrial manufacturing and plant environments like **Continental Biscuits Limited (CBL) – LU Sukkur Plant**, Health, Safety, and Environment operations directly impact **worker safety, operational continuity, regulatory compliance, risk reduction, and management accountability**.

### Current Challenges
When HSE records and KPIs are handled through manual sheets, paper forms, informal follow-ups, or disconnected files, plant teams face several operational limitations:

- **Scattered & Manual Records:** Safety data split across manual logs or sheets with no single source of truth.
- **Delayed Reporting & Follow-Up:** Slow updates and manual tracking of open, overdue, and closed actions.
- **Unclear Ownership & Accountability:** Difficulty linking departments, responsible owners, due dates, and closure outcomes.
- **Reactive KPI Compilation:** Management KPIs compiled periodically rather than monitored in real time.
- **Disconnected Modules:** Hazards, near misses, incidents, CAPA, training, audits, and inspections lack unified tracking.

**Goal:** Replace scattered, manual HSE record-keeping with a **unified, brand-aligned digital platform** that improves visibility, accountability, and timely decision-making.

---

## ⚠️ Why Digitization Matters

Without a centralized digital system and live monitoring:

- **Hazards & Near Misses:** Potential hazards can remain unresolved or fail to convert into preventive actions.
- **Incidents & CAPA:** Investigations and follow-ups can lose visibility or fall behind schedule.
- **Training, Audits & Inspections:** Compliance tracking and training manhours/effectiveness are harder to monitor consistently.
- **Management Visibility:** Supervisors and plant leadership cannot quickly see real-time plant safety performance, slowing risk mitigation.

---

## 🔄 Current Workflow vs. Gap Analysis

### Current Manual / Semi-Digital Workflow
```text
Event Occurs → Manual Report (Paper / Sheet / Verbal) → Supervisor / HSE Review
→ Informal Action Assignment → Manual Follow-Up → Periodic Sheet Compilation → Management Meeting



+-----------------------------------------------------------------------+
|                        FRONTEND DASHBOARD LAYER                       |
|   LU-Branded Web Interface | Live KPI Cards | Charts | Filters | CRUD |
|   Consistent Module Pattern: Form -> Table -> Filter -> Update -> Export|
+-----------------------------------+-----------------------------------+
                                    |
                                    | Authenticated Requests
                                    v
+-----------------------------------------------------------------------+
|                         BACKEND REST API LAYER                        |
|   Auth (JWT / Microsoft SSO Verify-Email) | Role-Based Access Control |
|   Endpoints for Hazards, Near Miss, Incidents, CAPA, Training, Audits |
+-----------------------------------+-----------------------------------+
                                    |
                                    | Structured Persistence
                                    v
+-----------------------------------------------------------------------+
|                       CENTRAL DATABASE LAYER                          |
|   Unified HSE Records | Department & Plant Linkage | Status & Owners  |
+-----------------------------------------------------------------------+


User Authentication: Authorized users sign in via secure authentication (JWT / Microsoft SSO verify-email flow) with role-based access.

Dashboard Overview: Users inspect live KPI cards, indicators, and visual charts.

Digital Event Reporting: Users submit records for Hazards, Near Misses, Incidents, Training, Audits, or Inspections through digital forms.

Structured Data Storage: Entries are saved with department mapping, timestamps, ownership, and workflow status.

CAPA Assignment: Corrective & preventive actions are assigned to responsible owners with clear due dates.

Lifecycle Status Tracking: Action progress is updated across stages (Open → In Progress → Completed → Closed / Verified).

Live KPI Refresh: Dashboard metrics and charts refresh dynamically to support management reviews and decisions.

🧩 Core HSE Modules & Standard Pattern
The platform centralizes 7 core HSE modules:

Hazard Reporting: Identify, report, and track workplace hazards proactively.

Near Miss Events: Log close-call situations to prevent future incidents.

Incident Logs: Record incidents/injuries, root causes, and investigation follow-ups.

Action Tracker (CAPA): Assign owners, set due dates, and track corrective/preventive closure.

Training Records: Manage safety training sessions, participants, and manhours.

Audit Management: Plan audits, document findings, and track remediation.

Inspection Records: Capture routine inspection observations and compliance results.

Each module follows a consistent operational pattern:

Form → Table → Filter → Update → Export

📊 Dashboard & KPI Monitoring Layer
Supervisors and management can monitor key plant metrics without waiting for manual monthly compilations:

Total Hazards Reported and Open vs. Closed Actions

Incident Counts, Categories & Risk Rating Distribution

Training Activity & Manhours

Audit & Inspection Status

Department-Wise Trends across plant operations
