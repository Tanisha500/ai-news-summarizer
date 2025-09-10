# AI News Summarizer
 
# Overview

This project is an AI-powered news automation workflow built in n8n.
It automatically fetches news articles from Google News RSS, summarizes them using Groq’s LLaMA model, and posts the summaries to Slack with:

1. Summary
2. Relevant hashtags

## Tools & Technologies

1. n8n → Workflow automation platform

2. Groq LLaMA-3.1-70B → Fast LLM inference for text summarization

3. Slack API → For posting AI-generated content to channels

4. Google News RSS → News source for fetching latest articles

## Nodes Explanation

1. Cron Trigger → Runs the workflow automatically (e.g., every 1 hour).

2. Fetch Article → Pulls latest articles from Google News RSS feed.

3. XML → Converts RSS XML into structured JSON.

4. Edit Fields → Extracts only required fields (title, link, description).

5. Code → Cleans & restructures data into a simpler JSON format.

6. HTML Extract → Extracts content (paragraphs) if available.

7. Summarization Chain → Uses Groq Chat Model with custom prompts to:

   Summarize the article

   Add hashtags

   Format output for Slack

8. Groq Chat Model → LLaMA-3.1-70B model hosted on Groq (fast inference).

9. Send a message (Slack) → Posts the AI-generated summary into your chosen Slack channel.


## Features

1. Automated RSS to Slack pipeline
2. Summarization powered by Groq LLaMA-3.1-70B
3. Lightweight workflow with minimal nodes
4. Flexible → You can replace Slack with Email, Telegram, or 

## Setup Instructions

1. Clone Repository
   git clone <your-repo-link>
   cd ai-news-summarizer-slack

2. Import Workflow in n8n

   Open n8n dashboard

   Go to Workflows → Import from File

   Upload the file: ai-news-summarizer.json

3. Configure Credentials

  Groq API Key → Add under Groq Chat Model node

  Slack API Credentials → Connect your Slack workspace in Send a message node

4. Run the Workflow

  Trigger manually or wait for the Cron schedule

  AI summaries will start appearing in your Slack channel
