# Asset Management Portal

## Problem Statement

The **Asset Management Portal** is designed to streamline the tracking, management, and allocation of both physical and digital assets within an organization using ServiceNow. Employees can request and receive assets through a user-friendly portal, while administrators manage the asset lifecycle from procurement to disposal. The portal automates assignment, maintains accurate records, generates reports, and triggers alerts for maintenance or replacement, ensuring optimal asset performance and reduced downtime.

---

## 📁 Table

Asset data is stored in a custom table to enable proper tracking and reporting.

### 🔸 Create Table

**Steps:**
1. Open ServiceNow.
2. Navigate to: `All >> Tables` or `System Definition >> Tables`.
3. Click **New**.
4. Fill in:
   - **Name:** Asset Inventory
5. Click **Save**.

---

### 🔸 Create Fields

After saving the table:
1. Scroll down and create the following fields:

| Field Name       | Type   |
|------------------|--------|
| Assigned to      | String |
| Status           | Choice |
| Purchase date    | Date   |
| Warranty Expire  | Date   |
| Asset name       | String |
| Type             | Choice |
| Number           | String |

2. Click **Save**.

---

## 🧩 Create UI Actions

### 🔸 UI Action 1: Mark As Lost

**Navigation:** System Definition >> UI Actions  
**Configuration:**
- **Name:** Mark As Lost
- **Table:** Asset Inventory
- **Action name:** mark_as_lost
- **Condition:** `current.u_status != 'Lost'`
- **Script:**
  ```javascript
  current.u_status = 'Lost';
  current.update();
  action.setRedirectURL(current);
  ```
- Check the **Form button** option and click **Save**.

---

### 🔸 UI Action 2: Mark As Repaired

**Navigation:** System Definition >> UI Actions  
**Configuration:**
- **Name:** Mark As Repaired
- **Table:** Asset Inventory
- **Action name:** mark_as_repaired
- **Condition:** `current.u_status == 'Damaged' || current.u_status == 'Lost'`
- **Script:**
  ```javascript
  current.u_status = 'Available';
  current.update();
  action.setRedirectURL(current);
  ```
- Check the **Form button** option and click **Save**.

---

### 🔸 UI Action 3: Mark As Damaged

**Navigation:** System Definition >> UI Actions  
**Configuration:**
- **Name:** Mark As Damaged
- **Table:** Asset Inventory
- **Action name:** mark_as_damaged
- **Condition:** `current.u_status != 'Damaged'`
- **Script:**
  ```javascript
  current.u_status = 'Damaged';
  current.update();
  action.setRedirectURL(current);
  ```
- Check the **Form button** option and click **Save**.

---

## 🕒 Scheduled Job

### 🔸 Create Scheduled Job

**Navigation:** System Definition >> Scheduled Job  
**Configuration:**
- **Name:** Warranty Expiry Alert
- **Run:** Daily
- **Time:** 12:00 PM
- **Script:** *(custom script to trigger alerts before warranty expires)*
- Click **Save**.

---

## 📊 Report

### 🔸 Create Report

**Navigation:** Reports >> Create New  
**Configuration:**
- **Report Name:** Available vs Assigned Assets
- **Source Type:** Table
- **Table:** Asset Inventory
- **Type:** Pie Chart
- **Group By:** Status
- **Aggregation:** Count

Click **Save**, then **Run** to view the report.

---

## ✅ Testing

### 🔸 Testing UI Action

**Steps:**
1. Go to the Asset Inventory table.
2. Click **New** and fill in:
   - Asset name: Laptop
   - Type: Laptop
   - Assigned to: Abel Tutor
   - Status: Available
   - Choose Purchase and Warranty Expiry dates
3. Click **Submit**.
4. Reopen the record and click **Mark As Lost**.
5. Confirm the status changes to **Lost**.

---

### 🔸 Testing Scheduled Job

**Steps:**
1. Navigate to **System Definition >> Background Scripts**.
2. Paste the script used in the Scheduled Job.
3. Click **Run Script**.
4. Check logs or notifications to confirm job execution.

---

## 🔚 Conclusion

This ServiceNow-based Asset Management Portal simplifies asset lifecycle management by automating workflows, enhancing visibility, and supporting timely decisions. It ensures effective tracking, reduces asset loss, and boosts organizational efficiency.

