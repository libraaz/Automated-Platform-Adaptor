# 🚀 Automated Platform Adaptor — AI Social Media Content Automation

An AI-powered social media automation workflow built with **n8n, Google Gemini, Google Sheets, LinkedIn, and X**. The workflow takes input from Google Sheets and generates platform-specific content for LinkedIn and X using separate AI chains.

The goal is to automate content creation while adapting the writing style to each platform.

## 📌 Project Overview

Creating content for multiple social media platforms manually can be time-consuming. A single message also rarely suits every platform.

This project uses AI-powered workflow automation to generate tailored content for LinkedIn and X from a Google Sheets trigger.

## ✨ Key Features

- **Google Sheets Integration:** Triggers the workflow when the configured sheet receives an update.
- **AI-Powered Content Generation:** Uses Google Gemini models through n8n's Basic LLM Chain nodes.
- **Platform-Specific Adaptation:** Separates the generation process into dedicated LinkedIn and X branches.
- **LinkedIn Content Generation:** Produces content intended for a professional audience.
- **X Content Generation:** Produces concise, engaging content suited to X.
- **Automated Workflow Execution:** Connects input, AI processing, and platform-specific publishing nodes in one workflow.
- **API Integration:** Uses configured platform credentials to connect to the relevant services.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| Google Sheets | Input source and workflow trigger |
| Google Gemini | AI-powered content generation |
| LinkedIn API integration | Creating LinkedIn posts |
| X API v2 integration | Creating posts on X |
| JSON | Workflow export and data exchange |

## 🏗️ Workflow Architecture

The workflow follows this general structure:

1. **Google Sheets Trigger** — Detects updates in the configured spreadsheet.
2. **Initial Basic LLM Chain** — Processes the input using a Google Gemini model.
3. **LinkedIn Generation Branch** — Uses a dedicated LLM chain to adapt the content for LinkedIn.
4. **X Generation Branch** — Uses a separate LLM chain to adapt the content for X.
5. **LinkedIn Create a Post** — Sends the generated content to LinkedIn.
6. **X Create Tweet** — Sends the generated content to X.

Each platform has its own generation branch, allowing its prompt and output format to be customized independently.

## 📸 Screenshots

### 1. Workflow Overview

![Automated Platform Adaptor workflow](screenshots/workflow-overview.png)

### 2. Successful Execution

![Successful workflow execution](screenshots/successful-execution.png)

### 3. LinkedIn Content Output

![LinkedIn generated content](screenshots/linkedin-content-output.png)

### 4. X Content Output

![X generated content](screenshots/x-content-output.png)

## ⚙️ Setup and Configuration

### Prerequisites

- An n8n instance, either self-hosted or cloud-hosted.
- Access to Google Sheets.
- A Google Gemini API credential.
- A LinkedIn account and the required API permissions.
- An X Developer App attached to a Project, with the appropriate API access and authentication credentials.

### Installation

1. Download the workflow JSON file from the `workflow/` directory.
2. Open your n8n instance.
3. Import the JSON workflow into n8n.
4. Configure the Google Sheets trigger and select the appropriate spreadsheet.
5. Configure the Google Gemini credentials for the LLM nodes.
6. Configure LinkedIn and X credentials for the publishing nodes.
7. Review the prompts, spreadsheet fields, and node connections.
8. Test the workflow and verify the generated content and publishing results.

**Important:** API access, account permissions, and platform-specific authentication requirements must be satisfied before publishing can work. An imported workflow may require credentials and configuration before it can execute successfully.

## 🔐 Security

- Never commit API keys, access tokens, OAuth secrets, or passwords.
- Configure credentials securely inside n8n.
- Review exported workflow JSON files before uploading them to GitHub.
- Avoid including private spreadsheet data or personal information in screenshots.
- If a credential is accidentally exposed, revoke or rotate it immediately.

## 🧠 Concepts Demonstrated

This project demonstrates practical experience with:

- Low-code workflow automation and orchestration.
- Large language model integration.
- Prompt engineering for different content formats.
- Branching workflows and modular AI processing.
- Third-party API integration and authentication.
- JSON-based workflow portability
