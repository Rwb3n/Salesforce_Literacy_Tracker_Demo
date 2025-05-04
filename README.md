# 📚 Literacy Tracker - Salesforce Declarative Build

## 🚧 Overview

This repository documents the **work-in-progress** development of the **Literacy Tracker**, a custom-built application developed **entirely using Salesforce declarative tools**—no Apex, no LWC, no unmanaged packages like DLRS. Despite being under active development, a functional demo is live and accessible.

Built for **non-profit organizations**—modeled after children’s literacy programs like **Bookmark Reading**—the Literacy Tracker enables staff, volunteers, and managers to track reading sessions, student progress, and programme health with clarity and precision.

> 🎯 **Core Goal:** Deliver a fully native, scalable CRM solution using only Flows, standard objects, and configuration—maximizing maintainability and transparency.

⚠️ **Documentation is not final.** Features are being actively refined, but the system is stable enough for demonstration and evaluation.

---

## ✨ Key Features (Live & In Progress)

- **👦 Student Tracking:** Manage demographics, reading levels, and recency data.
- **📖 Session Logging:** Dedicated Screen Flow to log duration, book, focus, location, and status.
- **📚 Book Catalogue:** Centralized record of books used, mapped by reading level.
- **📍 Location Management:** Track session locations tied to Accounts and Contacts.
- **📊 Assessment Tracking:** Record scores, reading level results, and level transitions.
- **💬 Confidence Monitoring:** Periodic student confidence surveys using ratings.

### 🤝 Volunteer Management

- Dedicated **Contact Record Type** for volunteers.
- Student-volunteer relationship managed via `Student_Volunteer__c` junction object.
- **🕒 Volunteer Aggregator Flow:** Scheduled to calculate hours served and current assignments.
- **🏅 Milestone Generator:** Auto-creates achievements based on reading level-ups, time, or session count.
- **🔁 Recency Flows:** Automatically update Last Session Date, Focus Area, and Book Read.
- **📈 Reading Level Sync:** Always reflects latest/highest reading assessment.
- **🚦 Student Path UI:** Visual guidance tied to reading levels via Salesforce Path.
- **🔐 Role-Based Security:** Managed with Profiles, Permission Sets, and Permission Set Groups.
- **📉 Dashboards:** Volunteer Impact live; others in final polish.
- **🧪 Demo Data Tools:** Admin Flows generate realistic sample data with cleanup tags.

---

## 🛠️ Technical Architecture

- **100% Declarative:** No Apex, no LWC, no external packages.
- ❌ Apex  
- ❌ Custom LWC  
- ❌ DLRS / Unmanaged Packages

### 💡 Performance Patterns

- **Collection Slice Pattern** for bulk-safe DML inside Flows.
- **Optimized SOQL**: Pre-fetches to avoid loops.
- **Scheduled Paths**: Async logic for scalable demo data flows.

### 🧱 Data Model

Uses standard (`Contact`, `Account`) and custom objects linked by Master-Detail or Lookup relationships.

### 🔐 Security Model

Role-based access using Salesforce native features: Profiles, PS, PSGs, and Record Type sharing logic.

---

## 🚦 Project Roadmap

Development follows structured phases. Current progress:

- ✅ **Phase 1: Foundation**  
  Core data model (Student, Session, Book, Location), logging flows, basic access control.

- ✅ **Phase 2: Assessments & Confidence**  
  Reading assessments, confidence surveys, level syncing, milestone generation.

- ✅ **Phase 3: Volunteer & Location**  
  Volunteer assignments, aggregator logic, dashboards, demo data tools.

- ✅ **Phase 4: Milestones & Dashboards**  
  Final milestone logic, celebration system, programme health and student progress dashboards.

- 🟡 **Phase 5: Data Generation Kit (90%)**  
  Demo data flows complete; finalizing demo records for **assessments** and **confidence surveys**.

- 🔵 **Phase 6: Polish & UAT (50%)**  
  Mobile tweaks, permission hardening, training materials, and user testing underway.

---

## 🚀 Demo Access

A live sandbox is available for preview and testing:

🔗 [https://rubenpires-dev-ed.develop.lightning.force.com/](https://rubenpires-dev-ed.develop.lightning.force.com/)

**🧪 Test Credentials (Literacy Specialist Role):**  
- 👤 Username: `jvolu@ruben.pires`  
- 🔑 Password: `VOLUNTEER123`  

> *Please use responsibly. Demo data is reset periodically.*
