# Inbound Lead Qualification Agent (n8n)

An **AI agent built in n8n** that automatically qualifies inbound leads for a (fictional) IT recruitment agency.

## How It Works

1. **`Main.json`**: a web form collects the lead's details. An HTTP request to a **Relevance AI** tool scrapes the lead's company website, and an **AI Agent** (Google Gemini) decides whether the lead is a good fit. Unqualified leads receive a polite reply via **Gmail**.
2. **`Qualified.json`**: qualified leads are passed to a sub-workflow where **OpenAI** classifies the company (e.g. *Agency* vs *SaaS*), and a tailored follow-up email is sent for each segment.

**Tech stack:** n8n · AI Agent · Google Gemini · OpenAI · Relevance AI · Gmail

## Usage

Import both JSON files into n8n (**Workflows → Import from File**), connect your own Gemini, OpenAI, Relevance AI and Gmail credentials, and link the *Call n8n Workflow Tool* node in `Main` to the `Qualified` workflow.
