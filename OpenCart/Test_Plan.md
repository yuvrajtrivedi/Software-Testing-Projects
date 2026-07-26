# 📑 Master Test Plan: OpenCart E-Commerce System

**Document ID:** TP-OC-2026-V1  
**Author:** Lead QA Analyst  
**Target Application:** OpenCart Storefront & Admin Portal (`https://demo.opencart.com/`)  
**Standard:** IEEE 829 Software Test Documentation  

---

## 1. Scope of Testing

### 1.1 In-Scope
* **Customer Storefront:**
  * User Registration with valid/invalid data combinations.
  * Search engine keywords, category trees, and product comparison tools.
  * Shopping Cart price calculations, currency conversion rates, and coupon discount validation.
  * Multi-step Checkout (Address, Shipping Method, Payment Method selection).
* **Admin Management Panel:**
  * Adding/Editing Products, SKU assignment, and Stock quantity controls.
  * Managing Coupons (Percentage vs Fixed Amount discounts).
  * Order status workflow updates and customer management.

### 1.2 Out-of-Scope
* Real payment gateway transaction settlements (Sandboxed UI testing only).
* Database server stress testing.

---

## 2. Test Strategy & Methodologies

1. **Boundary Value Analysis (BVA):** Applied to product quantity fields (0, 1, Max Stock, Max+1).
2. **Equivalence Partitioning (EP):** Applied to discount coupon thresholds and input fields.
3. **State Transition Testing:** Applied to Order Status progression (`Pending` ➔ `Processing` ➔ `Shipped` ➔ `Complete`).

---

## 3. Test Environment Setup

| Parameter | Details |
| :--- | :--- |
| **Storefront URL** | `https://demo.opencart.com/` |
| **Admin URL** | `https://demo.opencart.com/admin/` |
| **Browsers Tested** | Google Chrome (Latest), Mozilla Firefox (Latest), MS Edge |
| **Test Artifacts** | Markdown Logs, RTM, Defect Reports |