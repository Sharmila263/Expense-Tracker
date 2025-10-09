# 🧾 Salesforce Expense Tracker

---

## 🌟 Project Overview
The **Salesforce Expense Tracker** is a full-featured application that helps employees submit and track expenses efficiently.  
It automatically flags high-value expenses for CEO approval, sends email notifications upon approval/rejection, and provides insightful dashboards and reports for management.  

> “Streamline expense management, improve approvals, and gain real-time insights!”

---

## 🛠 Key Features

- **Expense Submission** 📝  
  Employees can create expenses with Name, Amount, Date, Category, and Submitter Email.  

- **High-Value Expense Flagging** ⚠️  
  Expenses above 500 are automatically flagged for CEO approval using Salesforce Flows.  

- **CEO Approval / Rejection** ✅❌  
  CEO can manually approve or reject expenses.   

- **Email Notifications** 📧  
  Apex trigger sends automatic notifications to the submitter when the CEO updates the status.  

- **Reports & Dashboards** 📊  
  Summarizes expenses by category and status, providing management real-time insights.

---

## 📂 Object & Fields

**Custom Object:** `Expense__c`  

| Field Name | Type | Description |
|------------|------|------------|
| Name | Text | Expense Name |
| Amount__c | Currency(16,2) | Expense amount |
| Date__c | Date | Expense date |
| Category__c | Picklist | Travel, Food, Office, Other |
| Status__c | Picklist | Submitted, Need Approval, Approved, Rejected |
| Approved_By__c | Lookup(User) | CEO who approves/rejects (manual) |
| Approval_Date__c | Date/Time | Timestamp of approval/rejection (manual) |
| Rejection_Reason__c | Text Area | Reason for rejection (manual) |
| Submitter_Email__c | Email | Employee email to receive notifications |

---

## ⚡ Automation

- **Flow:** Auto-flag high-value expenses (>500) → Status = Need Approval  
- **Apex Trigger (`ExpenseApprovalNotifier`)** ✉️  
  Sends email notifications to the submitter when the CEO updates status.

> 🔹 Note: All approval fields are entered manually by the CEO. Validation rules for read-only fields are **not implemented** in this version.

---

## 👥 Roles & Profiles

- **CEO (System Administrator)** – Reviews and approves/rejects expenses.  
- **Finance Manager** – Submits expenses.  

**Sharing Settings:**  
- Default Internal Access: Private  
- Role Hierarchy: Enabled  
- CEO sees all expenses, Finance Manager sees only their own.

---

## 📝 Sample Data

| Expense Name | Amount | Date | Category | Status | Submitter Email |
|--------------|-------|------|---------|--------|----------------|
| Flight to Delhi | 600 | Today | Travel | Submitted | fm@example.com |
| Lunch | 150 | Today | Food | Submitted | fm@example.com |
| Office Supplies | 300 | Today | Office | Submitted | fm@example.com |

---

## 🎬 Demo Workflow

1. Finance Manager submits a new expense.  
2. High-value expenses (>500) are automatically flagged.  
3. CEO manually approves/rejects expense and enters approval details.  
4. Apex trigger sends email notification to submitter.  
5. Reports and dashboards provide summaries by category and status.  

---

## 📊 Reports & Dashboards

- **Expense Report:** Grouped by Category and Status with sum of Amounts.  
- **Dashboard:** Pie/Bar charts for quick visual overview.  

---

## 📦 Installation / Deployment

1. Create custom object `Expense__c` with all fields.  
2. Create Flow for high-value expense flagging.  
3. Create Apex trigger `ExpenseApprovalNotifier` for email notifications.  
4. Configure Roles & Profiles with sharing rules.  
5. Assign Permission Set for Finance Manager to create expenses.  
6. Create Reports & Dashboard.

---

## 🚀 Future Enhancements

- Add file upload for receipts 📎  
- Slack/Teams notifications for approvals 💬  
- PDF generation for approved expenses 🖨  
- Scheduled Apex for monthly summaries 📅  
- Advanced dashboards with filters by month/category 📈  

---

## 📜 License

Open-source project for **learning and demonstration purposes**.

---


## Created By 
Sharmila Beeraka
Demo video : https://drive.google.com/file/d/1HwX1NyTIA4F_g44EBy8kjtTKzWDhGLkY/view?usp=sharing



