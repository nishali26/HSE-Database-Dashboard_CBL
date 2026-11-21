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


## ⚡ End-to-End Digital Workflow & Operational Lifecycle

The proposed platform replaces fragmented, manual record-keeping with a structured, traceable, and real-time operational workflow across plant departments. Every step is designed to maintain data integrity, enforce accountability, and support rapid decision-making.

### 1. User Authentication & Role-Based Access Control (RBAC)
- **Secure Sign-In Flow:** Authorized plant personnel, supervisors, HSE officers, and managers authenticate through a secure access flow supporting **JSON Web Tokens (JWT)** and **Microsoft Single Sign-On (SSO) verify-email** verification.
- **Role-Based Permissions:** Access levels and visible actions are governed by user roles so sensitive records, administrative settings, and verification steps remain protected and auditable.
- **Session & Identity Integrity:** Verified user identity links submissions, reviews, and status changes to real accounts rather than anonymous or unverified sheets.

### 2. Dashboard Overview & Executive Snapshot
- **Immediate Situational Awareness:** Upon signing in, users land on a centralized dashboard displaying live **Key Performance Indicator (KPI) cards**, status indicators, and visual charts.
- **Cross-Module Visibility:** Supervisors and leadership can inspect current plant safety health at a glance before diving into specific module tables or forms.
- **Exception & Bottleneck Spotting:** Highlights overdue items, open actions, and shifting department trends early so teams can intervene proactively.

### 3. Digital Event Reporting Across HSE Activities
- **Standardized Digital Forms:** Users report safety events and operational records directly through structured web forms rather than paper sheets or ad-hoc messages.
- **Comprehensive Coverage:** Supports digital entry for **Hazards**, **Near Miss Events**, **Incidents**, **Training Records**, **Audits**, and **Inspections**.
- **Consistent Input Quality:** Required fields, categories, and structured inputs reduce missing details and standardize reporting across shifts and teams.

### 4. Structured Data Storage & Relational Context
- **Unified Central Storage:** Every submitted record is persisted into a structured central database so all HSE data lives in a single source of truth.
- **Metadata & Context Tagging:** Each entry is stored with **department mapping**, **timestamps**, **record ownership**, and **current workflow status**.
- **Auditability & Traceability:** Clear timestamps and structured linkages make it straightforward to trace when an event occurred, who logged it, and how it progressed.

### 5. Corrective & Preventive Action (CAPA) Assignment
- **Actionable Follow-Through:** Findings and safety risks are translated into concrete **Corrective & Preventive Actions (CAPA)**.
- **Clear Ownership:** Each action item is assigned to a specific responsible owner within the relevant department or function.
- **Target Deadlines:** Explicit **due dates** set clear expectations for timely remediation and prevent tasks from lingering indefinitely.

### 6. Lifecycle Status Tracking & Verification
- **Transparent Progression:** Action items and records move through defined lifecycle stages:
  `Open` → `In Progress` → `Completed` → `Closed / Verified`
- **Controlled Closure:** Moving items toward closure/verification ensures actions are not merely marked done on paper, but actually verified against the underlying risk.
- **Accountability Trail:** Status transitions keep supervisors and owners aligned on what is pending, active, awaiting verification, or closed.

### 7. Live KPI Refresh & Data-Driven Decision Support
- **Real-Time Metric Updates:** As new events are logged and statuses change, dashboard KPIs and charts refresh dynamically rather than relying on delayed manual compilation.
- **Faster Management Reviews:** Supervisors and plant leadership can review up-to-date metrics during daily/weekly huddles and safety reviews.
- **Proactive Risk Decisions:** Timely insights help allocate resources, prioritize high-risk areas, and strengthen overall plant safety governance.

---

## 🧩 Core HSE Modules & Standardized Operational Pattern

The platform centralizes **7 core HSE modules** into one cohesive workspace so teams do not have to jump between disconnected spreadsheets or tools.

### Core HSE Modules Breakdown

1. **Hazard Reporting**
   - **Purpose:** Identify, log, and track workplace hazards proactively before they result in injury, equipment damage, or operational disruption.
   - **Operational Value:** Encourages early floor-level hazard spotting and structured risk mitigation.

2. **Near Miss Events**
   - **Purpose:** Capture close-call events or unsafe conditions where harm was narrowly avoided.
   - **Operational Value:** Helps uncover latent risks early and prevent future incidents through proactive learning.

3. **Incident Logs**
   - **Purpose:** Record workplace incidents and injuries along with root-cause analysis and investigation follow-ups.
   - **Operational Value:** Maintains a reliable historical record and ensures lessons learned drive concrete corrective measures.

4. **Action Tracker (CAPA)**
   - **Purpose:** Assign responsible owners, set due dates, and track the end-to-end closure of corrective and preventive actions.
   - **Operational Value:** Turns safety findings and audit/inspection observations into measurable, time-bound execution.

5. **Training Records**
   - **Purpose:** Manage safety training sessions, participant attendance, and logged training **manhours**.
   - **Operational Value:** Helps verify workforce readiness, compliance coverage, and training engagement across teams.

6. **Audit Management**
   - **Purpose:** Plan HSE audits, document audit findings, and track remediation progress through to completion.
   - **Operational Value:** Improves audit readiness, follow-up discipline, and systematic compliance tracking.

7. **Inspection Records**
   - **Purpose:** Capture routine workplace inspection observations, checklist outcomes, and compliance findings.
   - **Operational Value:** Standardizes recurring safety checks and links inspection issues directly to follow-up actions.

### Consistent Operational Pattern Across All Modules

Every module follows a uniform, predictable interaction model so users can learn the system quickly and work consistently across all workflows:

```text
Form (Data Entry) → Table (Structured View) → Filter (Slice & Search) → Update (Status & CAPA) → Export (Reporting)
