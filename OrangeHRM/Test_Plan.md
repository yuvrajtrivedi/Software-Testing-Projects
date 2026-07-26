# 📑 Master Test Plan: OrangeHRM Application

**Document ID:** TP-OHRM-2026-V1  
**Author:** Lead QA Analyst  
**Target Application:** OrangeHRM Open Source (`https://opensource-demo.orangehrmlive.com/`)  
**Standard:** IEEE 829 Software Test Documentation  

---

## 1. Introduction & Test Objectives
The primary goal is to verify that OrangeHRM performs reliably across primary enterprise modules without functional regression, data truncation, or security role leaks.

---

## 2. Detailed Scope of Testing

### 2.1 In-Scope (Functional & Non-Functional)
* **Authentication Module:** Valid/Invalid logins, SQL injection basic checks, Remember Me, Reset Password flows.
* **Admin Module:** System User creation, role assignment (Admin vs ESS), searching, status updates (Enabled/Disabled).
* **PIM Module:** Employee addition, mandatory field checks, profile photo format validation, personal details updates.
* **Leave Module:** Applying for leave, balance deduction logic, overlaps detection, manager approval/rejection.
* **Cross-Browser Compatibility:** Google Chrome, Mozilla Firefox, Microsoft Edge.

### 2.2 Out-of-Scope
* Database Direct Querying (Backend DB Level).
* Load & Stress Testing beyond 100 concurrent requests.
* Third-party payroll integrations.

---

## 3. Test Strategy & Methodologies

```mermaid
graph LR
    A[Requirement Analysis] --> B[Test Case Design]
    B --> C[Boundary Value & EP]
    C --> D[Execution on Chrome & Firefox]
    D --> E[Defect Logging in Markdown]
    E --> F[Regression & Sign-off]