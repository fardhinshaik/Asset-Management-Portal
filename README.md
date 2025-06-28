# 🧾 Asset Management Portal – ServiceNow

A centralized ServiceNow-based portal for tracking, managing, and maintaining physical and digital assets across an organization. This portal streamlines asset allocation, automates lifecycle tracking, sends proactive warranty alerts, and provides real-time reporting.

---

## 📌 Features

- 🔐 Role-based access to manage and track assets.
- 📄 Custom Asset Inventory table with key asset details.
- 🖱️ UI Actions for quick status updates:
  - Mark as Lost
  - Mark as Damaged
  - Mark as Repaired
- ⏰ Scheduled Job to notify IT before warranty expiry.
- 📊 Pie chart report to visualize asset status distribution.

---

## 🏗️ Technologies

- Platform: ServiceNow
- Modules Used:
  - Custom Tables
  - UI Actions
  - Scheduled Jobs
  - Background Scripts
  - Reports

---

## 📁 Table Structure

| Field Name       | Type   | Description                        |
|------------------|--------|------------------------------------|
| Asset Name       | String | Name of the asset                  |
| Type             | Choice | Type of asset (Laptop, Monitor…)  |
| Assigned To      | String | User to whom asset is assigned     |
| Status           | Choice | Current status of asset            |
| Purchase Date    | Date   | Date of asset purchase             |
| Warranty Expire  | Date   | Warranty expiry date               |
| Number           | String | Unique identifier                  |

🟡 Choice values:

- Type: Laptop, Monitor, Mobile, Tablet, Printer  
- Status: Available, Assigned, Lost, Damaged, Repaired

---

## 🚀 Setup Instructions

### 1. Create Asset Inventory Table

- Navigate to: All → System Definition → Tables → New
- Table Name: asset_inventory  
- Add the fields listed in the structure above.

### 2. Add Choice Values

- Open each Choice field (Type and Status).
- Go to Choices → New.
- Enter appropriate labels and values for dropdowns.

### 3. Insert Sample Data

Manually create 5–10 records via the Asset Inventory table form.  
Example:

- Asset Name: Dell Laptop  
- Type: Laptop  
- Status: Available  
- Assigned To: Abel Tutor  
- Purchase Date: 2023-01-10  
- Warranty Expire: 2025-01-10  
- Number: LAP001  

### 4. Create UI Actions

Go to:  
All → System Definition → UI Actions → New

Create the following buttons with associated scripts:

- Mark as Lost  
- Mark as Damaged  
- Mark as Repaired  

Each updates the u_status field and redirects to the updated record.

### 5. Create Scheduled Job

Navigate to:  
All → System Definition → Scheduled Jobs → New

- Select: Automatically run a script of your choosing  
- Name: Warranty Expiry Alert  
- Run: Daily at 12:00 PM  
- Paste the GlideRecord + email alert script

### 6. Generate Report

- Navigate to Reports → Create New  
- Report Name: Available vs Assigned Assets  
- Table: Asset Inventory  
- Type: Pie Chart  
- Group By: Status  
- Aggregation: Count  

---

## ✅ Testing Summary

### ✔️ UI Action Test

- Created a record for “Abel Tutor”
- Clicked “Mark As Lost” → status changed to “Lost”

🖼️ Screenshot: [Asset Creation]  
🖼️ Screenshot: [Status Changed via UI Action]

### ✔️ Scheduled Job Test

- Executed job script in Background Scripts  
- Assets with warranty expiring within 30 days were found  
- Emails sent to IT support  
- Logs showed confirmation message

🖼️ Screenshot: [Job Script]  
🖼️ Screenshot: [Log Output]

---

## 📊 Sample Report Output

- Pie chart displayed based on asset Status  
- Categories: Available, Assigned, Lost, Damaged, etc.  
- Helped visualize utilization distribution of assets.

---

## 📌 Conclusion

The Asset Management Portal is a scalable, automated solution for enterprise asset tracking and lifecycle management. Through ServiceNow’s platform, this system delivers:

- Efficient asset tracking
- Lifecycle visibility
- Proactive warranty alerts
- Real-time status updates
- Data-driven decision support

It improves asset utilization, reduces downtime, and enhances IT operational efficiency.

---

