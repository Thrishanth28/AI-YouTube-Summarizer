# AI-YouTube-Summarizer
# 🎯 AI YouTube Summarizer — Advanced n8n Automation Workflow

An advanced automated YouTube video summarization system built with **n8n**, **RapidAPI**, **Google Gemini**, and **JavaScript**. Paste any YouTube URL — AI fetches the transcript, processes 10,000+ characters and delivers a clean summary directly in n8n — no email needed!

---

## 🚀 What It Does

In just one form submission, this workflow automatically:

1. 📋 **Collects YouTube URL + preferences** via a clean n8n form
2. 🔍 **Extracts the Video ID** using JavaScript code node
3. 📡 **Fetches the full transcript** via RapidAPI YouTube Transcript API
4. 🧹 **Parses and cleans** the raw transcript data
5. ✅ **Checks if transcript exists** using IF node logic
6. 🧠 **Summarizes using Google Gemini** in your chosen style
7. 📊 **Displays clean output** directly in n8n — no email required!

---

## 📸 Workflow Overview

```
YouTube Form (n8n Form Trigger)
        │
        ▼
Extract Video ID (JavaScript Code Node)
        │
        ▼
Fetch Transcript via RapidAPI (HTTP Request)
        │
        ▼
Parse Transcript (JavaScript Code Node — cleans HTML)
        │
        ▼
Has Transcript? (IF Node — smart error handling)
    │                       │
   YES                      NO
    │                       │
    ▼                       ▼
Summarize with Gemini   No Transcript Error
    │                   (explains why + fix)
    ▼
Format Output
(shows result directly in n8n ✅)
```

---

## 📋 Form Fields

| Field | Example |
|-------|---------|
| Your Name | Thrishanth Reddy |
| YouTube Video URL | https://www.youtube.com/watch?v=xxxxx |
| Summary Style | Key Points / Study Notes / Action Items etc |

---

## 🎯 5 Summary Styles

| Style | Best For | Output |
|-------|---------|--------|
| **Key Points** | Quick overview | 5–8 bullet points |
| **Short Paragraph** | Just the main idea | 2–3 sentences |
| **Detailed Summary** | Deep understanding | 200–250 words |
| **Study Notes** | Learning & revision | Sections: Topic, Concepts, Facts, Takeaways |
| **Action Items** | How-to videos | Numbered steps to implement |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **n8n** | Workflow automation platform |
| **RapidAPI — youtube-transcript3** | Fetch YouTube video transcripts |
| **Google Gemini (PaLM API)** | AI summarization engine |
| **JavaScript (Code Nodes)** | Video ID extraction + transcript parsing |
| **IF Node** | Smart error handling logic |
| **n8n Form Trigger** | Clean input form |

---

## 📊 Sample Output

```
╔══════════════════════════════════════╗
       AI YOUTUBE SUMMARIZER RESULT
╚══════════════════════════════════════╝

User: Thrishanth Reddy
Video: https://youtu.be/aGrMOowjMag
Style: Key Points (bullet list)
Transcript: 10000 characters processed
Status: SUCCESS ✅

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SUMMARY:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

KEY POINTS FROM THE VIDEO

• The interviewer built a multi-million dollar business
  by interviewing 30+ billionaires and 1000 successful
  individuals including Will Smith and Mark Cuban

• Key lesson 1: Only take advice from people who have
  achieved the exact goal you are working towards

• Key lesson 2: Build your own brand and personal value
  to attract the right connections and opportunities

• Key lesson 3: Investing — not just saving — is the
  true path to long-term wealth creation

• The speaker earns $6M+ annually through a marketing
  agency, consulting, and brand partnership ventures

---
VIDEO INFO
- URL: https://youtu.be/aGrMOowjMag
- Watch time saved: ~7 minutes
- Best for: Entrepreneurs and aspiring business builders
---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Powered by n8n + Google Gemini
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## ⚙️ Setup Instructions

### Prerequisites
- [n8n](https://n8n.io) installed (cloud or self-hosted)
- RapidAPI account + YouTube Transcript API key (free)
- Google Gemini API key

### Step 1 — Get Free RapidAPI Key

1. Go to [rapidapi.com](https://rapidapi.com) and sign up free
2. Search for `youtube-transcript3`
3. Subscribe to the **FREE plan** (500 requests/month)
4. Copy your **X-RapidAPI-Key** from the dashboard ✅

### Step 2 — Import Workflow

1. Open your n8n dashboard
2. Go to **Workflows → Import from File**
3. Select `AI_YouTube_Summarizer_Advanced.json`

### Step 3 — Configure Credentials

1. Open the **"Fetch Transcript via RapidAPI"** node
2. Replace `YOUR_RAPIDAPI_KEY_HERE` with your actual key
3. Add your **Google Gemini API** credentials to the Gemini node

### Step 4 — Test the Workflow

1. Click **Execute Workflow** — form link appears
2. Paste any YouTube URL with captions
3. Choose your summary style
4. Click **Submit**
5. Click the **"Format Output"** node → **Output tab**
6. See your clean summary! ✅

---

## ✅ Videos That Work Best

```
✅ TED Talks (always have captions)
✅ Tech tutorials and coding videos
✅ News videos (BBC, CNN, CNBC)
✅ Educational YouTube channels
✅ Any video with CC button visible
```

```
❌ Videos with no subtitles/captions
❌ Private or age-restricted videos
❌ Live streams without replay captions
```

---

## 🔧 Customization

**Add more summary styles:**
Update the Gemini prompt to include:
```
Tweet Thread → 5 tweets summarizing the video
Blog Post → Full article based on video content
Quiz → 5 MCQ questions to test understanding
```

**Save summaries to Google Sheets:**
Add a Google Sheets node after Format Output
to automatically log every summary with timestamp.

**Send to WhatsApp:**
Add a WhatsApp node to receive summaries
on your phone instead of viewing in n8n.

**Batch process multiple videos:**
Add a Google Sheets trigger + SplitInBatches node
to summarize an entire playlist automatically.

---

## 💡 Real World Use Cases

- 🎓 **Students** — Summarize lecture recordings for quick revision
- 📰 **Researchers** — Extract key insights from long interview videos
- 💼 **Professionals** — Get action items from training videos fast
- 📱 **Content Creators** — Repurpose YouTube content into blog posts
- 🏢 **Teams** — Summarize webinar recordings for team members

---

## 🏆 Why This Is An Advanced Project

This workflow uses **8 different node types** working together:

| Node Type | Skill Demonstrated |
|-----------|-------------------|
| Form Trigger | UI/UX design |
| Code Node (x2) | JavaScript programming |
| HTTP Request | External API integration |
| IF Node | Conditional logic |
| LLM Chain | AI/Prompt engineering |
| Gemini Model | API credential management |
| Code Node (output) | Data formatting |

Built and tested successfully — processing **3,106 tokens** and **10,000 characters** in **34 seconds**! ⚡

---

## 🔐 Security Note

> ⚠️ Never commit real API keys to GitHub.
> Replace all keys with placeholders before pushing.
> Add real keys only inside your n8n credential manager.

---

## 🙋‍♂️ Built By

**S. Thrishanth Reddy** — AI Automation Developer
Skills: n8n · Prompt Engineering · JavaScript · RapidAPI · HTML/CSS · Python · SQL
📎 [LinkedIn](https://linkedin.com/in/thrishanth-reddy) | 🔗 [GitHub](https://github.com/Thrishanth28)

---

## 📄 License

MIT License — free to use, modify, and share!
