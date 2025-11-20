#  n8n AI Chat Flow with HTTP Actions & Email Automation

This repository contains an **n8n workflow** that implements a flexible AI-powered chat system using an **AI Agent**, dynamic model selection, memory storage, and automated actions such as HTTP requests and email sending.



##  Features

###  1. AI Chat Agent
The workflow includes an AI Agent node that can use:
- **OpenAI (ChatGPT)**  
- **Google Gemini**  

The user (or the configuration) decides which model to use, allowing flexibility depending on preferences, cost, or performance needs.



###  2. Simple Memory
The workflow stores a short context of the conversation using the **Simple Memory node**, allowing the AI to:
- Maintain context between messages  
- Improve responses  
- Handle multi-step actions  



### 🌐 3. HTTP Integrations (GET & UPDATE)
The Agent can trigger automated actions based on the instruction script, such as:

- **GET requests** (retrieve information)
- **PUT/PATCH/UPDATE requests** (modify external systems)

Useful for:
- Updating records  
- Querying APIs  
- Interacting with external services controlled by the AI  



###  4. Email Sending
Based on the instructions in the AI Agent script, the workflow can automatically send emails using the **Email node**.  
Typical use cases:
- Notifications  
- Reports  
- Alerts triggered by the chat flow  



## How It Works

1. A chat input enters the workflow (from UI, webhook, or another system).
2. The message is passed to the **AI Agent**, which:
   - Uses either OpenAI or Gemini
   - Maintains memory
   - Generates actions when required
3. If the AI requires an action:
   - The workflow performs the HTTP GET/UPDATE request
   - Or triggers an email sending node
4. The workflow returns a final response to the user with the results.



## Requirements

- **n8n** → latest version  
- At least one of:
  - OpenAI API Key  
  - Google Gemini API Key
- Email credentials (SMTP)  
- API endpoints for GET/UPDATE actions  



##  Files in this Repository

- `workflow.json` – Importable workflow for n8n
- `README.md` – Documentation (this file)



##  Installation

1. Clone this repo:
git clone https://github.com/your-repo/n8n-ai-chat.git
2. Import workflow.json into your n8n instance.
3. Add environment variables in n8n:

OPENAI_API_KEY=
GEMINI_API_KEY=
SMTP_USER=
SMTP_PASSWORD=

4. Start n8n and run the workflow.


##
Made with ❤️ using n8n, AI Models, and automation best practices.
