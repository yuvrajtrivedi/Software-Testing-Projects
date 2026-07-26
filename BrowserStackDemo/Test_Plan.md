# Comprehensive Test Plan Document: BStackDemo Application

**Document Version:** 1.0  
**Project:** BStackDemo E-Commerce Manual & Cross-Browser Testing  
**Prepared By:** Software Test Engineer  
**Status:** Approved  

---

## 1. Document Control & Revision History

| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| **v1.0** | July 2026 | QA Engineer | Initial Deep Draft of BStackDemo Test Plan |

---

## 2. Introduction & Purpose
The objective of this Test Plan is to define the full scope, test strategy, resource allocation, environment setup, and execution workflow for validating the **BStackDemo** e-commerce application (`https://bstackdemo.com/`).

This document serves as the primary roadmap to ensure that critical user pathways—such as user authentication, catalog navigation, shopping cart interactions, and checkout validations—are thoroughly tested for functionality, edge cases, and cross-browser/device compatibility.

---

## 3. Scope of Testing

### 3.1 In-Scope Features (To Be Tested)
1. **User Authentication & Session Management:**
   * Login with valid credentials (`demouser` / `testingpass`).
   * Session persistence upon page navigation and refresh.
   * Logout functionality and session termination.
2. **Product Catalog & Search/Filter Engine:**
   * Vendor filter application (Apple, Samsung, Google, OnePlus).
   * Multi-vendor filtering and unchecking logic.
   * Sorting mechanisms (Price: Low to High, High to Low).
3. **Cart & Inventory Management:**
   * Adding single/multiple items to the cart slider.
   * Quantity increment (`+`) and decrement (`-`) controls.
   * Boundary testing for cart item removal (quantity reaching 0).
   * Max quantity checks and cart state persistence across reloads.
4. **Checkout & Order Processing:**
   * Mandatory field validation (First Name, Last Name, Address, State, Postal Code).
   * Data format validation (alphanumeric checks on input fields).
   * Unauthenticated checkout block and login redirection.
   * Order summary and placement confirmation screen.
5. **Cross-Browser & Responsive UI (via BrowserStack):**
   * Responsive layout rendering on Desktop (Chrome, Safari, Edge).
   * Mobile viewport alignment and gesture responsiveness on real devices (iOS/Android).

### 3.2 Out-of-Scope Features (Not To Be Tested)
* Real credit card payment gateway integration (mocked behavior only).
* Backend database performance and load testing (JMeter/Gatling).
* Security vulnerability penetration testing (OWASP ZAP).
* Admin portal and backend product inventory upload functions.

---

## 4. Test Approach & Methodology

Testing will follow an **Agile Manual Testing Approach**, incorporating the following testing types:

* **System Functional Testing:** Verifying that every feature operates in accordance with expected e-commerce business logic.
* **UI/UX & Usability Testing:** Checking visual alignment, typography, button clickability, and responsive layouts.
* **Boundary Value Analysis (BVA) & Equivalence Partitioning (EP):** Validating input text fields and numeric cart counters against minimum/maximum limits.
* **Negative & Error-Handling Testing:** Intentionally providing invalid inputs (e.g., special characters in Zip Code, empty required fields) to ensure proper validation messages.
* **Cross-Browser / Real-Device Testing:** Utilizing **BrowserStack Live** to test application behavior on various OS-Browser combinations.

---

## 5. Test Environment & Tool Matrix

| Component | Platform / Tool Details |
| :--- | :--- |
| **Application Under Test (AUT)** | BStackDemo (`https://bstackdemo.com/`) |
| **Cross-Browser Cloud Platform** | **BrowserStack Live** |
| **Desktop Browsers** | Google Chrome, Apple Safari (macOS), Microsoft Edge |
| **Mobile Real Devices** | Apple iPhone 15 (Safari - iOS), Samsung Galaxy S23 (Chrome - Android) |
| **Developer Tools** | Chrome DevTools (Console Logs, DOM Inspector, Network tab) |
| **Documentation & Tracking** | GitHub Markdown (`.md`), GitHub Issues |

---

## 6. Entry and Exit Criteria

### 6.1 Entry Criteria (When Testing Starts)
* BStackDemo application URL is live and responsive.
* Test environment credentials (`demouser` / `testingpass`) are active and validated.
* Test Plan and Test Cases are drafted, reviewed, and ready for execution.
* BrowserStack Live account is configured with available real devices.

### 6.2 Exit Criteria (When Testing Concludes)
* 100% of planned test cases (TC-001 through TC-016) have been executed.
* All identified bugs/defects are logged with full steps to reproduce, screenshots, and severity ratings in `Bug_Reports.md`.
* No Critical or Blocker bugs remain open that completely prevent the checkout journey.
* Test Summary Report is compiled and signed off.

---

## 7. Defect Severity & Priority Guidelines

| Severity Level | Definition | Example |
| :--- | :--- | :--- |
| **Critical / Blocker** | System crashes, unhandled errors, or complete blockage of primary checkout flow. | User unable to click 'Checkout' button or cart fails to open. |
| **High** | Major functional flaw or invalid data acceptance without proper validation. | Postal code field accepts invalid special characters without error during checkout. |
| **Medium** | Non-critical functionality fails, or workaround exists. | Filter selection requires two clicks to uncheck. |
| **Low** | Cosmetic or minor UI alignment issues. | Cart badge overlapping text on small mobile viewports. |

---

## 8. Deliverables
1. `README.md` (Project Summary & Environment Config)
2. `Test_Plan.md` (This Document)
3. `Test_Cases.md` (16 Detailed Test Execution Logs)
4. `Bug_Reports.md` (Defect Logs with Reproducible Steps)
5. `Test_Summary_Report.md` (Final Sign-off Metrics)