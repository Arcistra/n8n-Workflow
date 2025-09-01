# 📋 Lead Capture to Google Sheets (n8n Workflow)

This n8n workflow captures Google Form submissions, stores them in a Google Sheet, and notifies the team via email.  
It’s designed for simple **lead management** and **instant alerts**.

---

## 🚀 How It Works

1. **Google Form Submission**  
   - A user submits a form.  
   - A Google Apps Script trigger (`onFormSubmit`) sends the form data to the n8n **Webhook**.

2. **n8n Workflow**  
   - **Webhook Node**  
     Receives form data as JSON payload.  
   - **Google Sheets Node**  
     Appends the captured data to a dedicated Google Sheet (`Lead Capture Sheet`).  
   - **Gmail Node**  
     Sends an email notification with the lead details.

3. **Result**  
   - Leads are automatically logged in Google Sheets.  
   - Your team receives instant email notifications.

---

## 📂 Workflow Structure

