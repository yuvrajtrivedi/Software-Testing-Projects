# 🛒 OpenCart E-Commerce Platform - End-to-End QA Portfolio

![QA Status](https://img.shields.io/badge/QA%20Status-Completed-brightgreen)
![Testing Type](https://img.shields.io/badge/Testing-Manual%20%7C%20E--Commerce%20%7C%20Admin-blue)
![AUT](https://img.shields.io/badge/AUT-OpenCart%20v4.x-orange)

## 📌 Executive Summary
This repository contains a comprehensive Manual QA portfolio for **OpenCart**, an enterprise-grade open-source e-commerce platform. The project validates end-to-end user journeys including User Registration, Product Catalog Navigation, Cart Price Calculations, Coupon/Discount Engine Validations, Checkout Operations, and Backend Admin Stock/Order Management.

---

## 📐 System Workflow Architecture

```mermaid
flowchart TD
    subgraph STOREFRONT ["🛍️ Customer Storefront"]
        A[👤 User Reg / Login] --> B[🔍 Search & Product Filter]
        B --> C[🛒 Add to Cart & Apply Coupon]
        C --> D[💳 Guest / Account Checkout]
        D --> E[📦 Order Placed & Invoice Gen]
    end

    subgraph ADMIN_PANEL ["🛠️ Merchant Admin Portal"]
        F[🔑 Admin Auth] --> G[📦 Catalog & Stock Mgmt]
        G --> H[📑 Order Status Processing]
        H --> I[🏷️ Coupon & Discount Rules]
    end

    E -.-> H