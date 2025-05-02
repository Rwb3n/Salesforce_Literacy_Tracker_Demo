# Literacy Tracker - Salesforce Declarative Build

## Overview
This repository/project documents the development of the "Literacy Tracker," a custom application built entirely on the Salesforce platform using declarative tools only (no Apex, LWC custom code, or external packages like DLRS).
The application is designed for non-profit organizations, specifically modelled around the needs of a children's literacy charity like Bookmark Reading, to manage and track key aspects of their reading programs end-to-end. It empowers programme staff, volunteers, and managers to monitor student progress, volunteer contributions, and overall programme health.
Core Goal: To provide a comprehensive, scalable, and maintainable CRM solution built natively on Salesforce without relying on custom code development, maximizing the use of Flows, standard configuration, and declarative best practices.
Key Features (Implemented & Planned)
This application provides (or will provide upon completion of all phases) the following capabilities:
Student Tracking: Manage student participant records, including demographics and current reading level status.
Session Logging: Easy logging of individual reading sessions via a dedicated Screen Flow, capturing duration, book read, focus areas, location, and status.
Book Catalogue: Maintain a simple catalogue of books used within the program, including reading levels.
Location Management: Track physical locations where sessions occur, linked to parent Organizations (Accounts) and Contact Persons (Contacts).
Assessment Tracking: Log formal reading assessments, including skill scores, determined reading levels, and level changes.
Confidence Monitoring: Capture periodic student confidence surveys using simple rating scales.
Volunteer Management:
Identify Volunteers using a dedicated Contact Record Type.
Track volunteer assignments to specific students using a junction object (Student_Volunteer__c), including roles and status.
Automated Aggregation: A nightly scheduled flow calculates and updates Total Hours Served and Active Student Assignments directly on the Volunteer (Contact) record.
Milestone Generation: Automatically create celebratory Milestone records based on student achievements (e.g., reading level advancement, reaching session count or reading minute thresholds).
Automated Recency Tracking: Flows automatically update key fields on the Student record like Last Session Date/Time, Latest Session Focus Area, and Latest Book Read.
Reading Level Synchronization: A flow automatically updates the student's primary reading level based on their latest, highest assessment result.
Student Path: Visual progress tracking on the Student record page using Salesforce Path based on Current Reading Level, displaying key fields and guidance at each stage.
Role-Based Security: Utilizes Profiles, Permission Sets, and Permission Set Groups (Literacy Specialist Role, Literacy Program Manager Role) to provide appropriate access levels.
Reporting & Dashboards: Includes source reports and dedicated dashboards for Volunteer Impact, Student Progress, and Programme Health (built across phases).
Demo Data Generation: Administrator tools (Flows) to generate realistic test data for multiple objects, respecting governor limits using batching and scheduled paths. Includes a Demo_Data__c flag for easy cleanup.
Technical Approach & Constraints
100% Declarative: Built entirely using standard Salesforce configuration and Flow automation.
NO Apex Classes or Triggers.
NO Lightning Web Components (Custom).
NO External/Unmanaged Packages (like Declarative Lookup Rollup Summaries - DLRS).
Scalability Considerations: Flows are designed with governor limits in mind, employing techniques like:
Collection Slice Pattern: For DML operations within loops (e.g., Demo Data generation, Volunteer Aggregator updates).
SOQL Query Optimization: Avoiding queries inside loops where possible (e.g., Volunteer Aggregator fetches all assignments once).
Scheduled Paths: Offloading potentially long-running operations (like bulk session creation in demo data) to asynchronous transactions.
Data Model: Utilizes standard objects (Contact, Account) and custom objects, linked via appropriate Master-Detail and Lookup relationships.
Security: Leverages standard Salesforce security features (Profiles, Permission Sets, Permission Set Groups, Record Types, Sharing controlled by Parent where applicable).
Project Status & Roadmap
The project is being developed in phases:
Phase 1: Foundation (COMPLETE): Core objects (Student, Session, Book, Location), session logging flow, student recency updates, basic security.
Phase 2: Assessments & Confidence (COMPLETE): Assessment, Confidence Survey, Milestone objects; data capture flows; reading level sync; initial milestone generation logic.
Phase 3: Volunteer & Location (COMPLETE): Volunteer Record Type, Student-Volunteer junction object, scheduled volunteer hours aggregation flow, UI updates for volunteer visibility, Volunteer Impact dashboard, initial Demo Data flows.
Phase 4: Milestones & Dashboards (Planned): Refine milestone triggers, implement celebration toasts, build remaining dashboards (Student Progress, Programme Health), implement Student Inactivity flag flow.
Phase 5: Data Generation Kit (Planned): Enhance demo data flows, build cleanup utility, potentially add load scripts/documentation.
Phase 6: Polish & UAT (Planned): Mobile optimizations, final permission hardening, user training materials, User Acceptance Testing.
Demo Access
A development environment demonstrating the current state is available at:
[Link: https://rubenpires-dev-ed.develop.lightning.force.com/]
Login Credentials (Test User - Specialist Role):
Username: jvolu@ruben.pires
Password: VOLUNTEER123
(Note: Please use responsibly for evaluation purposes. Data may be reset periodically).
