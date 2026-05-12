# n8n-seo-article-generator
AI-powered SEO article automation using n8n + Groq AI (Llama 3.3) for Herbs Are My World - a herbal wellness brand in Cyprus
# 🌿 AI-Powered SEO Article Generator

> **Automated SEO content generation system built with n8n + Groq AI for Herbs Are My World — a premium herbal wellness brand based in Cyprus 🇨🇾**

![n8n](https://img.shields.io/badge/n8n-Workflow-FF6D5A?style=for-the-badge&logo=n8n)
![Groq](https://img.shields.io/badge/Groq-AI-orange?style=for-the-badge)
![Llama](https://img.shields.io/badge/Llama%203.3-70B-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Solution](#-solution)
- [Architecture](#-architecture)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [Sample Output](#-sample-output)
- [Business Impact](#-business-impact)
- [Future Roadmap](#-future-roadmap)
- [Author](#-author)

---

## 🎯 Overview

This project automates SEO article writing for herbal wellness products using n8n workflow automation and Groq's Llama 3.3 AI model. It generates complete, ready-to-publish SEO articles in just 5 seconds.

## 🚨 Problem Statement

Manual SEO content writing has several pain points:
- ⏰ **Time-consuming:** 2-3 hours per article
- 💰 **Expensive:** $50-200 per outsourced article
- 📊 **Inconsistent SEO:** Quality varies article to article
- 📉 **Slow scaling:** Cannot publish 30+ articles/month manually

## 💡 Solution

An automated workflow that:
1. Takes a herb-related keyword as input
2. Sends it to Groq AI with optimized prompts
3. Returns a complete SEO-ready article
4. Includes FAQs and Schema markup for Google

## 🏗️ Architecture
┌─────────────────┐ ┌──────────────┐ ┌──────────────┐
│ Manual Trigger │───▶│ Edit Fields │───▶│ HTTP Request │
│ (Start) │ │ (Keyword) │ │ (Groq AI) │
└─────────────────┘ └──────────────┘ └──────┬───────┘
│
▼
┌──────────────────┐
│ SEO Article │
│ + FAQs │
│ + Schema (JSON) │
└──────────────────┘
## ✨ Features

- ✅ **SEO Title** (max 60 characters)
- ✅ **Meta Description** (max 155 characters)
- ✅ **URL Slug** (SEO-friendly)
- ✅ **Focus Keyword** + 5-7 LSI keywords
- ✅ **Article Content** (1000+ words with H2/H3 headings)
- ✅ **Image Alt Texts** (3-7 suggestions)
- ✅ **7 FAQs** with structured answers
- ✅ **FAQ Schema** (JSON-LD) for Google rich snippets

## 🛠️ Tech Stack

| Tool | Purpose | Cost |
|------|---------|------|
| **n8n** | Workflow automation platform | Free (open-source) |
| **Groq API** | AI provider | Free tier |
| **Llama 3.3 70B** | LLM model | Free via Groq |

## 📦 Installation

### Prerequisites
- Node.js v18+ installed
- Groq API key ([Get free key](https://console.groq.com))

### Setup Steps

1. **Install n8n:**
   ```bash
   npx n8n
   n8n-seo-article-generator/
├── README.md                    # You are here
├── seo-workflow.json            # n8n workflow file
├── docs/
│   ├── architecture.md          # System design
│   └── setup-guide.md           # Detailed setup
├── examples/
│   ├── chamomile-tea.md         # Sample article 1
│   ├── ashwagandha.md           # Sample article 2
│   └── turmeric.md              # Sample article 3
├── prompts/
│   └── seo-prompt.md            # AI prompt used

└── LICENSE


---

## **FILE 2: examples/chamomile-tea.md**

This shows a real generated article. Paste your AI output here!

---

## **FILE 3: prompts/seo-prompt.md**

The AI prompt you used:

```markdown
# SEO Article Generation Prompt

## System Message
You are an SEO expert for Herbs Are My World, a herbal wellness brand. Output only valid JSON.

## User Message Template
Write a complete SEO article for keyword: {{ keyword }}.

Return JSON with keys:
- seo_title (max 60 chars)
- meta_description (max 155 chars)
- url_slug (lowercase with hyphens)
- focus_keyword
- related_keywords (array of 5-7)
- article_content (1000+ words markdown)
- image_alt_texts (array of 3-7)
- faqs (array of 7 question-answer objects)
- faq_schema (JSON-LD format)
