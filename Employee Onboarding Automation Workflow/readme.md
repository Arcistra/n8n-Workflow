# Employee Onboarding Automation Workflow

This **n8n workflow** automates the onboarding process for new employees using **Google Sheets**, **Notion**, and **Gmail**. It handles employee data, assigns onboarding tasks, sends welcome emails, and updates records efficiently.

---

## 📌 Workflow Overview

This workflow consists of two main triggers:

1. **Employee Sheet Trigger** – Starts when HR adds or updates an employee in the Google Sheet.
2. **Tasks Sheet Trigger** – Starts when new tasks are added in the onboarding tasks Google Sheet.

It ensures that:

- Employee details are validated.
- Notion database pages are created for each new employee.
- Tasks are appended to the employee’s Notion page.
- Emails are sent automatically.
- Sheets are updated with statuses.

---

## 🗂 Workflow Nodes & Description

### **1. Employee Trigger**
- Triggered when a new row is added or updated in the **Employee Sheet**.
- **Sticky Note 1:**  
  `### ✅ Employee Trigger starts when HR updates Employee Sheet`
  
---

### **2. Switch1**
- Checks if the `Check` column is empty before creating a Notion page for the employee.
- **Sticky Note:**  
  `### ➡️ Switch checks 'Check' column before creating Employee Database page and then notion node will create Employee database page for each row that gets pass through the switch`

---

### **3. Create a Employee Database Page**
- Creates a new page in **Notion Employee Database** with employee details:
  - Name
  - Email
  - Role
  - Joining Date
  - Salary
  - Notes
- **Sticky Note 3:**  
  `### 📩 After page created → Email sent + Sheet updated`

---

### **4. Update_check_Employee**
- Updates the **Employee Sheet** with the Notion page URL.
- Resets the `Check` column.
- Prepares the record for email sending.

---

### **5. If Node**
- Validates the employee’s email address using regex.
- Sends email if valid, otherwise updates the sheet with `Invalid Email`.
- **Sticky Note:**  
  `### ➡️ iF-ELSE WILL VALIDATE eMAIL address BEFORE sENDING Email`

---

### **6. Send a Message**
- Sends a welcome email to the new employee with all onboarding details.

---

### **7. Google Sheets Trigger (Tasks)**
- Triggered when a new task is added in **Tasks Sheet**.
- **Sticky Note 4:**  
  `### ✅ Tasks Trigger starts when new row added in Tasks Sheet`

---

### **8. Switch**
- Checks the `Check` column of each task before processing.
- **Sticky Note 2:**  
  `### ➡️ Switch checks 'Check' column before Getting Notion Databases`

---

### **9. Get many database pages**
- Retrieves the employee’s Notion page to append tasks.

---

### **10. Set Node**
- Sets values for task assignment:
  - Task Name
  - Due Date
  - Task Details
  - Employee Email
  - ID for mapping back to Google Sheet

---

### **11. Loop Over Items**
- Loops through all tasks for the employee.
- **Sticky Note 5:**  
  `### 🔁 Loop over tasks → append them one by one to Notion`

---

### **12. Append a block**
- Appends each task to the employee’s Notion page.

---

### **13. Update_check_Task**
- Updates the task sheet marking each task as processed.
- **Sticky Note 6:**  
  `## ✔️ Each task marked processed → Google Sheet updated`

---

### **14. Error Trigger**
- Catches **any node failure** in the workflow.
- Can be used to:
  - Send error notifications
  - Log errors
  - Retry or alert manually
- **Sticky Note1:**  
  `### ⚠️ **Workflow Error Trigger** Catches ANY node failure in this workflow`
- **Sticky Note2:**  

---

## ⚠️ Error Data Available in Workflow Error Trigger

- **Workflow Name** → {{$json.workflow.name}}
- **Execution ID** → {{$json.execution.id}}
- **Execution URL** → {{$json.execution.url}}
- **Error Message** → {{$json.error.message}}
- **Stack Trace** → {{$json.error.stack}}
- **Failed Node** → {{$json.error.node.name}}

---

## ⚡ Features

- Automatic email sending with employee onboarding details.
- Validation of email addresses.
- Dynamic task assignment in Notion for each employee.
- Google Sheets updates to track status of employees and tasks.
- Error handling using the **Error Trigger node**.

---

## 🛠 Requirements

- **n8n Cloud or Self-Hosted**
- **Google Sheets OAuth2** credentials
- **Notion API** integration
- **Gmail OAuth2** credentials

---

## 💡 Usage

1. Copy the workflow JSON into your n8n instance.
2. Set up credentials for Gmail, Google Sheets, and Notion.
3. Update the sheet IDs, Notion database IDs, and mappings as required.
4. Trigger workflows automatically on sheet updates or task additions.

---

This workflow ensures **smooth onboarding** and reduces manual errors, making HR processes faster and more reliable.

---

*Note: Sticky notes in n8n provide context and guidance for each step.*

---
