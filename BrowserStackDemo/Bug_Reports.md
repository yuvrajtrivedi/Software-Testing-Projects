# Defect Tracking Log

---

### 🐛 Bug ID: BUG-001
- **Title:** Postal Code field accepts non-alphanumeric special characters without validation during Checkout.
- **Severity:** High
- **Priority:** Medium
- **Environment:** Windows 11 / Chrome & BrowserStack Safari on macOS
- **Module:** Checkout Workflow

#### 📌 Steps to Reproduce:
1. Navigate to `https://bstackdemo.com/`.
2. Login using `demouser` / `testingpass`.
3. Add any product (e.g., iPhone 12) to the cart and click **Checkout**.
4. Fill valid data for First Name, Last Name, Address, and State.
5. In the **Postal Code** field, enter special characters: `@#$%^&*()`.
6. Click **Submit / Checkout**.

#### 🎯 Expected Result:
System should display an inline validation error stating *"Please enter a valid numeric/alphanumeric postal code"*.

#### ❌ Actual Result:
Form accepts special characters and proceeds to place the order successfully.

---

### 🐛 Bug ID: BUG-002
- **Title:** Cart item count icon overlap on mobile viewport (Samsung Galaxy S23).
- **Severity:** Low (UI/UX)
- **Priority:** Low
- **Environment:** Real Device via BrowserStack - Samsung Galaxy S23 (Chrome Mobile)
- **Module:** Cart UI Component

#### 📌 Steps to Reproduce:
1. Open BrowserStack Live and select **Samsung Galaxy S23**.
2. Navigate to `https://bstackdemo.com/`.
3. Add 3 distinct items to the cart.
4. Close the cart slider to view the main product feed.
5. Observe the Cart Bag icon on the top right header.

#### 🎯 Expected Result:
The numerical badge (showing '3') should sit neatly inside or beside the cart bag icon.

#### ❌ Actual Result:
The count badge overlaps the 'Logout' text label due to tight margin spacing in mobile resolutions (360px - 390px viewport width).

📌 BUG-001 Validation Defect Visual (Checkout Screen Mockup)
+-----------------------------------------------------------------------+
|  BStackDemo > Checkout                                                |
+-----------------------------------------------------------------------+
|  First Name:  [ John        ]                                         |
|  Last Name:   [ Doe         ]                                         |
|  Address:     [ 123 Main St ]                                         |
|  State:       [ NY          ]                                         |
|  Postal Code: [ @#$%^&*()   ]  <-- [ERROR EXPECTED HERE: INVALID ZIP] |
|                                                                       |
|  [ SUBMIT / PLACE ORDER ]                                             |
+-----------------------------------------------------------------------+
|  ACTUAL BEHAVIOR: Form submits successfully without error message!    |
+-----------------------------------------------------------------------+

📌 BUG-002 Mobile UI Overlap Visual (Samsung S23 Screen Mockup)
+---------------------------------------------------+
| BStackDemo                        [Logout](3)     | <-- BAD ALIGNMENT!
+---------------------------------------------------+  (Cart count '3' 
|                                                   |   overlaps 'Logout')
|  [ Product List ]                                 |
|                                                   |
+---------------------------------------------------+
| EXPECTED: Badge (3) positioned next to Cart Icon. |
+---------------------------------------------------+