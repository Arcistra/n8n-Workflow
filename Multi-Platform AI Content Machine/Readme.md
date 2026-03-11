# 🚀 Multi-Platform AI Content Machine

**Automate your content creation and posting across Twitter/X and LinkedIn using AI!**  

This n8n workflow reads an RSS feed, generates engaging social media posts with AI, creates images, and automatically posts content to multiple platforms. Perfect for content creators, marketers, or anyone who wants to streamline social media management.  

---

## 🌟 Features

- 📰 **RSS Feed Trigger**: Automatically fetches new articles from any RSS feed.  
- 🤖 **AI Content Generation**: Uses OpenAI GPT-4.1-mini to generate engaging posts for Twitter/X and LinkedIn.  
- 🖼️ **AI Image Generation**: Generates platform-specific images based on content prompts.  
- 🌐 **Image Hosting**: Uploads generated images to IMGBB and retrieves the URL.  
- 🔄 **Platform Posting**: Posts content + images to Twitter/X and LinkedIn via Blotato nodes.  
- ⚠️ **Error Handling**: Sends email alerts via Gmail if the workflow fails.  
- 🕒 **Looping & Batching**: Processes multiple items efficiently with batching and waiting nodes.  

---

## 🛠️ How It Works

1. **RSS Feed Trigger**  
   - Polls your specified RSS feed every hour for new content.

2. **Python Code Processing**  
   - Extracts title, link, and snippet from the feed.  
   - Prepares structured data for AI content generation.

3. **Generate Post Content (AI)**  
   - Generates **short, engaging posts** for both Twitter/X and LinkedIn.  
   - Creates **image prompts** for each platform.  

4. **Split Prompts & Generate Images**  
   - Loops over items to generate images using OpenAI.  
   - Uploads images to IMGBB and retrieves the hosted URL.

5. **Merge Image URL & Platform Data**  
   - Ensures each post has its corresponding image URL for the correct platform.

6. **Platform Posting**  
   - Automatically posts to Twitter/X and LinkedIn with the content + image.  

7. **Error Handling**  
   - If anything fails, an alert email is sent via Gmail.  

---

## ⚡ Requirements

- n8n Cloud or self-hosted n8n instance  
- OpenAI API Key  
- IMGBB API Key  
- Blotato accounts for Twitter/X and LinkedIn  
- Gmail OAuth2 credentials for error notifications  

---

## 🎯 Workflow Overview

```text
RSS Feed Trigger → Python Extraction → Generate Post Content (AI) → Edit Fields → 
Split Prompts → Loop & Generate Images → Upload to IMGBB → Merge URL → Post to Platforms → Wait/Batch → Repeat
