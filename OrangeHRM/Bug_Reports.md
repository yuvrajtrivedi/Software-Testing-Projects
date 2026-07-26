# 🐛 Defect Tracking Log - OrangeHRM

---

### 🚨 DEFECT ID: BUG-OHRM-001
* **Summary:** Profile picture upload input accepts invalid file formats (`.pdf`, `.docx`) causing broken UI avatars.
* **Module:** PIM - Employee Profile Setup
* **Severity:** High (Data Validation Failure)
* **Priority:** High
* **Environment:** Windows 11 Chrome v125

#### 📌 Steps to Reproduce:
1. Log in as System Administrator (`Admin`).
2. Navigate to **PIM > Employee List** from the left navigation bar.
3. Click on any employee record to open **Personal Details**.
4. Click on the **Profile Photo / Avatar** placeholder.
5. In the file explorer, upload a non-image file (e.g., `sample_resume.pdf`).
6. Click **Save**.

#### 🎯 Expected Result:
The application should validate client-side & server-side MIME types and display an explicit error:  
`"Invalid File Extension. Supported formats: .jpg, .png, .jpeg"`.

#### ❌ Actual Result:
The form submits successfully. The avatar box shows a broken image icon (`img src` load failure).

#### 📷 Visual Evidence:
`![BUG-001 Avatar Upload Defect](./screenshots/bug001_avatar_broken.png)`

---

### 🚨 DEFECT ID: BUG-OHRM-002
* **Summary:** 'Reset' button fails to clear selected option state in Admin User Management filter form.
* **Module:** Admin - System Users Search
* **Severity:** Low (Usability Defect)
* **Priority:** Medium
* **Environment:** macOS Firefox v124

#### 📌 Steps to Reproduce:
1. Navigate to **Admin > User Management > Users**.
2. Set **User Role** dropdown to `ESS`.
3. Set **Status** dropdown to `Disabled`.
4. Click the **Reset** button.

#### 🎯 Expected Result:
Form inputs and custom select dropdowns should revert to `-- Select --` default state.

#### ❌ Actual Result:
The grid table resets, but the dropdown UI elements retain the visual labels `ESS` and `Disabled`, causing confusion for subsequent searches.

#### 📷 Visual Evidence:
`![BUG-002 Reset Button UI State](./screenshots/bug002_reset_ui.png)`