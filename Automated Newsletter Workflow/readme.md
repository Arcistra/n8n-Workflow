# 📰 Automated Newsletter Workflow
  This n8n workflow automatically fetches news from multiple BBC RSS feeds, summarizes the content using OpenAI, and saves the results to a Notion    database.

# ✨ Features
  Automatic news fetching from multiple BBC RSS feeds:
  - Top Stories
  - World News
  - Business News
  - Technology News
  - Science & Environment
  - Entertainment & Arts
  Content deduplication based on unique GUIDs.
  Batch processing with delays to prevent API rate limits.
  Summarization using OpenAI GPT-4o-mini for concise bullet points.
  Storage in Notion database with title, link, content, and GUID.

# 🛠 Workflow Overview
1️⃣ Schedule Trigger
	-	Purpose: Automatically triggers the workflow at a defined interval. ⏰
	-	Comment: Triggers the workflow at a set interval to fetch latest news from multiple RSS feeds.

 2️⃣ RSS Feed Nodes
    - Purpose: Fetch news items from different BBC RSS feeds. 🌐
      - Feeds:
        - BBC TOP STORIES NEW
        - BBC World News
        - BBC Business NEWS
        - BBC Technology NEWS
        - BBC Science and Environment NEWS
        - BBC Entertainment and Arts NEWS
   - Comment: Reads the RSS feed for <category>.

 3️⃣ Code Node
   - Purpose: Combine all fetched RSS items and remove duplicates. 🔄
   - Logic:
     - Collects data from all RSS feeds.
     - Extracts key fields: title, link, content, guid.
     - Deduplicates items using GUID.
  - Comment: Combines all RSS feed items, extracts required fields, and deduplicates by GUID.

 4️⃣ Split in Batches
  - Purpose: Process news items in small batches. 📦
  - Comment: Splits combined news items into batches for sequential processing.

 5️⃣ Wait Node
  - Purpose: Pause workflow between batches to avoid hitting API limits. ⏳
  - Delay: 20 seconds
  - Comment: Pauses the workflow for 20 seconds between processing each item to prevent API rate limit issues.

 6️⃣ OpenAI Node
  - Purpose: Summarize news content into 3–5 concise bullet points using GPT-4o-mini. 🤖
  - Comment: Sends each news item's content to OpenAI GPT model for summarization in concise bullet points.

 7️⃣ Notion Node
  - Purpose: Save summarized news into a Notion database. 📒
  - Stored Fields:
    - Title
    - Link
    - GUID
    - Content (summarized)
  - Comment: Creates a new page in Notion database with summarized news content.

# ⚙️ Setup Instructions 
 Install n8n (if not installed)
  - npm install n8n -g
 Import Workflow
  - Copy the workflow JSON (Automated Newsletter Workflow) into n8n.
 Set Credentials
  - Notion: Add your Notion API token.
  - OpenAI: Add your OpenAI API key.
 Configure Schedule Trigger
  - Set the desired interval for fetching news (e.g., every hour).
 Test Workflow
  - Manually trigger once to ensure all nodes work properly.

# 📌 Notes
Make sure your Notion database has the following properties:
  - title (Title)
  - link (URL)
  - guid (URL)
  - content (Rich Text)
Delay node ensures OpenAI’s API rate limits are not exceeded.

# 🛡 Security Considerations
- Do not share your API keys publicly.
- Database IDs and workflow node IDs are not sensitive but keep credentials safe.
- Always use .env or n8n’s credential management for API keys. 🔑

📈 Workflow Diagram


<img width="1662" height="737" alt="image" src="https://github.com/user-attachments/assets/9cd7659f-834f-4317-94a5-38d91ccb1a0f" />

# 💡 Future Improvements
-	Add more RSS sources or custom sources.
-	Enable multilingual summaries. 🌎
-	Add notifications (email/Slack) for new summaries. 📧
