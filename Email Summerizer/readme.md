# 📩 Email Summarizer Workflow (n8n + OpenAI + Google Sheets)
This repository contains an n8n automation workflow that automatically:
  Fetches the latest Gmail messages (every minute).
  Summarizes the email content using OpenAI GPT-4o-mini.
  Appends the summarized email details (ID, Subject, From, Date, Summary) into a Google Sheet for easy tracking and review.
It’s a simple yet powerful example of combining email automation, AI summarization, and structured data storage.

# ✨ Features
  ⏰ Runs automatically every minute using a Gmail Trigger.
  🤖 Summarizes email content with OpenAI GPT-4o-mini.
  📊 Logs results into Google Sheets with columns:
    Email ID
    From
    Subject
    Date
    Summary
  🔒 Credentials are managed via n8n’s built-in credential manager (no keys are stored in the workflow export).

# 🛠️ Requirements
  n8n (self-hosted or cloud)
  A Google account with Gmail + Google Sheets access
  An OpenAI API key

# 🚀 Setup Instructions
  # Import the Workflow
    Download the .json file from this repo.
    Import it into your n8n instance.
  # Connect Credentials
    In n8n, configure the following credentials:
      Gmail OAuth2 → Connect your Gmail account
      Google Sheets OAuth2 → Connect your Google Sheets account
      OpenAI API → Add your OpenAI key
  # Update Google Sheet Info
    Replace the placeholder Sheet ID in the workflow with your own Google Sheet.
    Make sure the sheet has columns matching: id, from, subject, date, text.
  
  # Activate Workflow
    Enable the workflow.
    Every new email in your Gmail inbox will now be summarized and appended to your Google Sheet.

# 📂 Example Use Cases
  Quickly scan email inbox summaries without reading full messages.
  Maintain a running log of important client communications. 
  Use as a base workflow for more advanced AI-powered email assistants.

# ⚠️ Security Notes
  No API keys are stored in this repository.
  The provided .json is sanitized for safe sharing (you must connect your own credentials).
  Ensure your Google Sheet is private/restricted unless you intend to share it.

# 🧑‍💻 Author
  Created as part of my automation + AI portfolio.
  If you’d like similar automations built for your business (AI workflows, web automation, or integrations), feel free to connect with me on LinkedIn
   or via Upwork.
