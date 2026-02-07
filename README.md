# 🏛️ Service Matters Digitalization Portal (Ondo State)

![Status](https://img.shields.io/badge/Status-Production-success?style=for-the-badge)
![Role](https://img.shields.io/badge/Role-Solutions_Architect-blue?style=for-the-badge)
![Tech](https://img.shields.io/badge/Tech-AppSheet_|_Google_Workspace_Ent-yellow?style=for-the-badge)

## 📋 Executive Summary
Architected by **Adewole Felix Bamidele**, this project is a "Zero-Touch" digital registry designed for the **Service Matters Department (Head of Service, Ondo State)**. It replaces legacy paper file movement with an automated, cloud-native indexing system, reducing file retrieval time from **hours to <2 minutes**.

## 🏗️ Architectural Design
The system utilizes a **Serverless Low-Code Architecture** to ensure high availability and low maintenance costs for the government.

##  🛠️ Technical Know-How & Implementation
1. Data Security & Access Control (RBAC)
UserEmail() Logic: Implemented strictly governed "Security Filters" ensuring that Junior Officers can only view files assigned to their desk, while the Permanent Secretary has a global view.

Audit Trail: A separate, immutable Audit_Log table records every Edit, View, and Sync action with a timestamp and GPS location.

2. Automation Workflows (Bots)
The "Overdue" Bot: Runs a daily scheduled task at 8:00 AM to check for files that have been on a single desk for >48 hours and auto-escalates them to the Director.

The "Movement" Bot: Automatically generates a PDF "Movement Slip" whenever a file status changes from Pending to Approved, emailing it to the relevant parties.

3. Offline-First Engineering
The application is engineered to cache 100% of the active registry locally, allowing civil servants to continue indexing files during internet outages. Sync occurs automatically via a "Store & Forward" mechanism upon reconnection.
🚀 Impact
100% Digitization of active Service Matters files.
Zero-Loss Record: Eliminated incidents of "missing files" via digital tracking.

Transparency: Real-time dashboard visibility for the Head of Service.

Architected by: Adewole Felix Bamidele Master's Degree (2015) | Solutions Architect


```mermaid
graph TD
    A[Physical Memo/File] -->|OCR Scan| B(Digital Input Interface)
    B -->|Validation & Indexing| C{AppSheet Core Engine}
    C -->|Metadata| D[(Google Sheets / Cloud SQL)]
    C -->|File Storage| E[Google Drive Secure Vault]
    D -->|Trigger| F[Automation Bot]
    F -->|Action 1| G[Generate Movement Slip PDF]
    F -->|Action 2| H[Email Notification to HOS]
    F -->|Action 3| I[Update Analytics Dashboard]
