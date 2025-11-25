# Blog-Writer
# ✍️ Agentic Blog Writer: From Inbox to Article

This repository contains a **Langflow** workflow that acts as your autonomous research assistant and writer. It scans your Gmail inbox for newsletters, identifies the most interesting story, and automatically drafts a high-quality blog post or article based on that content.

> **Note:** This workflow is pre-configured to use **Google Gemini** for speed and cost efficiency, but it is **model-agnostic**. You can easily swap nodes to use OpenAI, Anthropic, or Grok.

## 🚀 What This Workflow Does
1.  **Scans Your Inbox:** Connects to your Gmail via **Composio** to fetch recent emails (newsletters, updates, etc.).
2.  **Curates Content (The Editor):** An AI Agent reviews the links in your emails and selects the single most relevant or interesting URL to write about.
3.  **Reads the Source:** It visits the chosen URL and scrapes the full text content.
4.  **Writes the Article (The Writer):** A Generative AI model drafts a structured article (Introduction, Deep Dive, Key Takeaways) based on the source material.

## 📋 Prerequisites
* **Web-Based Langflow:** No local installation required. Use a hosted version of Langflow (e.g., DataStax Langflow).
* **Google API Key:** For the Gemini models (Get it from [Google AI Studio](https://aistudio.google.com/)).
* **Composio API Key:** To connect Gmail (Get it from [Composio.dev](https://composio.dev)).
* **Gmail Account:** The inbox you want the agent to scan.

## 🛠️ Setup Instructions

### Step 1: Import the Workflow
1.  Open your **Web-based Langflow** dashboard.
2.  Click **"New Project"** -> **"Import"**.
3.  Upload the `Generic_Blog_Writer.json` file provided in this repo.

### Step 2: Configure Credentials
1.  **Composio (Gmail Integration):**
    * Find the **"Composio Tools"** node.
    * Paste your `Composio API Key`.
    * *Tip:* Ensure you have connected your Gmail account in the Composio dashboard first.
2.  **Google Gemini (The Brains):**
    * Find the **"Agent"** node (The Editor). Paste your `Google API Key` in the API Key field.
    * Find the **"Google Generative AI"** node (The Writer). Paste the same `Google API Key` there.

### Step 3: Run & Customize
1.  Click the **Playground** (⚡) button.
2.  Type a command like: *"Check my emails for the latest tech news and write a blog post about it."*
3.  **The Result:** The workflow will output a fully written article in the Chat Output window, ready to be published on Medium, Substack, LinkedIn, or your personal blog.

## 🧠 Logic Flow
* **Input:** User Request.
* **Agent (Editor):** Reads email summaries and decides which URL is the "Hero Story."
* **Tool:** Scrapes the specific URL content.
* **Generator (Writer):** Formats the content into an engaging article.

## 📄 License
Open source. Feel free to modify the prompts to change the writing style!
