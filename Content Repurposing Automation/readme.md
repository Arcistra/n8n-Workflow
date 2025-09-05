# 🚀 Medium Blog to Multi-Platform Social Snippets Workflow

Automatically extracts Medium blog posts, converts them into social media snippets, saves them to Google Drive, and notifies your Slack workspace! Powered by **n8n**, **OpenAI GPT**, **Google Drive**, and **Slack**. ✨

---

## 🌟 Features
- Monitors Medium blog RSS feed in real-time ⏰  
- Converts posts into snippets for:  
  - **LinkedIn**: 150–300 words, professional 💼  
  - **Twitter**: 3–5 tweets, 280 characters 🐦  
  - **Instagram**: Fun caption + 3 hashtags + emojis 📸  
  - **TikTok/YouTube Shorts**: 20–30 sec video script 🎬  
- Saves snippets as Google Docs 📄  
- Sends Slack notifications when new posts are processed 🔔  
- Fully automated workflow 🤖  

---

## 🔗 Workflow Overview
1. **RSS Feed Trigger** – Polls Medium feed every minute ⏱️  
2. **Code Node** – Extracts title, link & snippet 📝  
3. **OpenAI GPT Node** – Generates multi-platform social snippets 🤯  
4. **Set Node** – Prepares content for Google Drive & Slack ⚡  
5. **Google Drive Node** – Saves snippets as Docs 💾  
6. **Slack Node** – Sends notifications 📢  

---

## ⚙️ Prerequisites
- n8n account (self-hosted or cloud) 🖥️  
- OpenAI API key (GPT-4o-mini) 🔑  
- Google Drive account with OAuth2 access 📁  
- Slack workspace with OAuth2 access 💬  

---

## 🛠 Setup
1. **Import Workflow** – `Workflow → Import from JSON`  
2. **Configure Credentials** – OpenAI, Google Drive, Slack  
3. **RSS Feed URL** – Replace `feedUrl` with your Medium blog feed  
4. **Activate Workflow** – Enable it to run automatically ✅  

---

## 🧩 Node Breakdown
| Node                  | Function |
|-----------------------|---------|
| RSS Feed Trigger       | Polls Medium RSS feed |
| Code                   | Extracts title, link & snippet |
| OpenAI GPT Node        | Generates social snippets |
| Set                    | Prepares content for downstream nodes |
| Google Drive           | Saves snippets as a Google Doc |
| Slack                  | Sends notification message |

---

## 📌 Usage
- Every new Medium post automatically generates social media content 📝  
- Slack notifications let your team quickly review or post snippets 🔔  

---

## 🎨 Customization
- Edit GPT Node prompt to change social media formats ✍️  
- Change Google Drive folder for storage 📂  
- Customize Slack notification text or channel 🛎️  

---
