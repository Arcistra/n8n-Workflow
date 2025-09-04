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
- **Webhook**  
  Entry point that receives JSON data from Google Forms via Apps Script.  

- **Append row in sheet**  
  Stores lead data (Name, Email, Phone, Address, Comments) in Google Sheets.  

- **Send a message**  
  Sends email notification with lead details using Gmail integration.  

---

## 📝 Requirements

- **n8n account** (self-hosted or cloud)  
- **Google Sheets API credentials** (OAuth2)  
- **Gmail API credentials** (OAuth2)  
- **Google Apps Script** attached to the Form’s linked Sheet to forward form data.  

---

## ⚙️ Setup Instructions

1. Clone/Import this workflow into your n8n instance.  
2. Connect your **Google Sheets** and **Gmail** credentials.  
3. Replace the **Webhook URL** in Google Apps Script with your own n8n Webhook URL.  
4. Update email addresses in the **Send a message** node.  
5. Test by submitting the Google Form.

---

## 🗒️ Notes

- Make sure the form’s linked Sheet has the following columns:  
  **Name | Email | Address | Phone number | Comments**  
- Gmail notifications use plain text for simplicity. You can enhance with HTML templates.  
- Add more nodes if you want to push leads into a CRM (e.g., HubSpot, Pipedrive, Airtable).  

---

## 📌 Example Email Output

- **Name**: John Doe
- **Email**: john@example.com
- **Phone Number**: +123456789
- **Address**: 123 Main Street
- **Reviews**: Interested in pricing details.

---

## 🔖 Tags

`n8n` `google-forms` `automation` `lead-capture` `google-sheets` `gmail`

---
