# 🐛 Defect Tracking Log - OpenCart

---

### 🚨 DEFECT ID: BUG-OC-001
* **Summary:** Checkout system permits order completion for out-of-stock items when stock checkout setting is disabled.
* **Module:** Checkout & Inventory Synchronization
* **Severity:** Critical (Business Logic & Inventory Corruption)
* **Priority:** High
* **Environment:** Desktop Chrome v125

#### 📌 Steps to Reproduce:
1. Log in as Customer or proceed as Guest.
2. Locate a product with stock quantity = `0` (e.g., `iPhone`).
3. Click **Add to Cart**.
4. Open Shopping Cart and click **Checkout**.
5. Complete Billing Address, Shipping Method, and Payment Method steps.
6. Click **Confirm Order**.

#### 🎯 Expected Result:
The system should halt checkout at Step 1 with a red alert:  
`"Products marked with *** are not available in the desired quantity or not in stock!"`.

#### ❌ Actual Result:
The checkout completes successfully, generating an Order Confirmation ID and deducting negative inventory values in the backend DB.

---

### 🚨 DEFECT ID: BUG-OC-002
* **Summary:** Coupon Code field in Admin Portal accepts unsanitized HTML/JS payloads leading to Stored XSS vulnerability.
* **Module:** Admin Portal - Marketing > Coupons
* **Severity:** High (Security Vulnerability)
* **Priority:** High
* **Environment:** macOS Firefox v124

#### 📌 Steps to Reproduce:
1. Log in to **OpenCart Admin Panel**.
2. Navigate to **Marketing > Coupons**.
3. Click **Add New (+)**.
4. In the **Coupon Name** field, paste: `<script>alert('XSS_VULN')</script>`.
5. Fill required discount values and click **Save**.
6. Refresh the Coupons list page.

#### 🎯 Expected Result:
System strips HTML/Script tags or displays validation error: *"Special characters not allowed"*.

#### ❌ Actual Result:
Payload is saved to the database and executes JavaScript alert popup whenever an Admin views the Coupon grid.