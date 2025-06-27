
# Asset Management Portal

## 1. INTRODUCTION

### 1.1 Project Overview
The Asset Management Portal is developed on the ServiceNow platform to automate and streamline the tracking, management, and lifecycle of organizational assets. It empowers both employees and administrators by enabling requests, assignments, maintenance tracking, and reports in a centralized system.

### 1.2 Purpose
The purpose of this project is to minimize manual asset tracking, reduce asset loss, and provide real-time insights and alerts on asset usage, condition, and maintenance requirements.

---

## 2. IDEATION PHASE

### 2.1 Problem Statement
Managing assets manually can lead to inefficiencies, errors, and asset losses. A centralized portal improves visibility, automates workflows, and ensures effective asset utilization and control.

### 2.2 Empathy Map Canvas
Stakeholders like IT admins, employees, and procurement officers were considered. We identified their needs such as ease of request, quick asset assignment, timely maintenance, and accurate reporting.

### 2.3 Brainstorming
Ideas included automated status change, repair tracking, assignment logs, scheduled alerts, and graphical reporting—all consolidated within ServiceNow.

---

## 3. REQUIREMENT ANALYSIS

### 3.1 Customer Journey Map
- **Request Asset** → **Approval** → **Assignment** → **Use** → **Maintenance** → **Disposal**

### 3.2 Solution Requirement
- Create Asset Inventory Table
- UI Actions for changing asset status
- Scheduled Job for alerting warranty expiry
- Graphical Reports on asset usage

### 3.3 Data Flow Diagram
```
[User] --> [Asset Request Form]
          --> [Asset Inventory Table]
          --> [Assignment/Status Update]
          --> [Reports | Alerts | Notifications]
```

### 3.4 Technology Stack
- **Platform:** ServiceNow
- **Scripting:** GlideScript (JavaScript)
- **Visualization:** ServiceNow Reports
- **Scheduling:** ServiceNow Scheduled Jobs

---

## 4. PROJECT DESIGN

### 4.1 Problem-Solution Fit
Employees can easily request assets, and admins manage the full asset lifecycle in a simplified and automated manner.

### 4.2 Proposed Solution
Use ServiceNow tables, UI actions, and scheduled jobs to provide a centralized asset management platform.

### 4.3 Solution Architecture
- **Front-end:** Forms and UI Actions
- **Back-end:** Tables, Business Rules, Scheduled Jobs
- **Reports:** Pie Chart on asset status

---

## 5. PROJECT PLANNING & SCHEDULING

### 5.1 Project Planning
| Module              | Duration |
|---------------------|----------|
| Create Table        | 1 hour   |
| UI Actions          | 1.5 hour |
| Scheduled Job       | 1 hour   |
| Report Generation   | 30 mins  |
| Testing & Debugging | 1 hour   |

---

## 6. FUNCTIONAL AND PERFORMANCE TESTING

### 6.1 Performance Testing
- Tested with large data records.
- Confirmed the accuracy of status change under UI actions.
- Verified execution timing of scheduled jobs.

---

## 7. RESULTS

### 7.1 Output Screenshots
- Table: Asset Inventory
- Fields: Assigned to, Type, Status, etc.
- UI Actions: Mark as Lost, Damaged, Repaired
- Report: Pie chart of Available vs Assigned
- Scheduled Alert: Warranty Expiry

---

## 8. ADVANTAGES & DISADVANTAGES

### ✅ Advantages
- Automated lifecycle tracking
- Real-time visibility into assets
- Reduced manual errors
- Scheduled maintenance alerts

### ⚠️ Disadvantages
- Requires ServiceNow access
- Custom scripting complexity for beginners

---

## 9. CONCLUSION
The Asset Management Portal helps track and manage assets efficiently within ServiceNow. It reduces overhead, improves tracking, and enables quick decision-making through automation and reporting.

---

## 10. FUTURE SCOPE
- Integration with procurement systems
- Mobile-friendly asset request interface
- Advanced analytics on asset lifespan and usage
