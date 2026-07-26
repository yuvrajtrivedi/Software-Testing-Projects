# 🏢 OrangeHRM Enterprise Open-Source - End-to-End Manual QA Portfolio

![QA Status](https://img.shields.io/badge/QA%20Status-Completed-brightgreen)
![Test Type](https://img.shields.io/badge/Testing-Manual%20%7C%20Functional%20%7C%20Security-blue)
![AUT](https://img.shields.io/badge/AUT-OrangeHRM%20v7.x-orange)

## 📌 Executive Project Overview
This repository houses a comprehensive, real-world Manual Software Testing portfolio conducted on the **OrangeHRM (Open Source Human Resource Management System)**. The objective of this project was to perform rigorous end-to-end functional validation, boundary testing, role-based access control (RBAC) security checks, and cross-browser usability testing on core enterprise HR workflows.

---

## 📐 System Workflow Architecture

```mermaid
flowchart TD
    A[🔑 Authentication & Session] --> B{User Role?}
    B -->|Admin Role| C[🛠️ Admin Module: User & Job Setup]
    B -->|ESS Role| D[👤 PIM Module: Self Profile]
    
    C --> E[👥 PIM: Add / Manage Employees]
    E --> F[🏖️ Leave Entitlements Allocation]
    
    D --> G[📝 Apply for Leave]
    G --> H[⏳ Manager Workflows: Approve / Reject]
    F --> H
    H --> I[📊 Reports & Analytics Audit]