# Contributing to awesome-n8n-agent-workflows

Thank you for your interest in contributing 🎉  
This project curates **n8n AI Agent workflows** with OpenClaw & MCP integration.

## 🧠 Workflow Data Format

Each workflow item follows a JSON schema:

```json
{
  "category": "ai",
  "title": "Your workflow title",
  "url": "https://n8n.io/workflows/xxxx",
  "difficulty": 3,
  "has_warning": false,
  "openclaw_usage": "",
  "source": "community"
}
category: One of ai, social, data, devops, email, mcp, hr, memory, rag, ecommerce, support, finance.

difficulty: Integer 1–5 (number of ⭐ in README).

has_warning: Mark irreversible actions (delete, publish, send).

openclaw_usage: Optional tip on how to invoke in OpenClaw.

source: “community” or “official”.

🚀 Submitting a PR
Fork the repository.

Add your JSON entry to data/enriched_workflows.json in your local copy.

Run the generator script (or describe your workflow details clearly).

Commit and submit a pull request.

We’ll review your PR and approve it once the entry passes validation.

🧩 License: MIT
Contribution = Agreement to the MIT License