# Ai-Agent-Andy

**Andy** is an AI-powered voice agent built for Anderson Plumbing, Heating & Electric. This agent handles real-time customer service calls, automates ServiceTitan tasks, and communicates with a set of MCP tools to perform actions like scheduling jobs, updating customer data, and retrieving invoices.

This repo is the full workspace for developing, maintaining, and scaling Andy’s toolset and backend automation using:
- **n8n** (for workflows)
- **ServiceTitan API** (for job, customer, invoice, and appointment data)
- **Codex / ChatGPT** (for AI-assisted dev work)
- **GitHub** (for version control and collaboration)

---

## 🧠 Project Purpose

Build a fully autonomous AI voice agent that:
- Books new jobs using ServiceTitan APIs
- Handles customer account updates
- Looks up invoices, payments, and memberships
- Applies business rules (e.g. service area, after-hours logic, memberships)
- Grows over time with new automations and sales intelligence

---

## 🗂 Repo Structure

```bash
/workflows/              # Core n8n workflows
  mcp-server.json        # Master toolset used by the AI agent

/docs/                   # API reference docs (from ServiceTitan)
  crm-v2.md
  jobs-v2.md
  invoices-v2.md
  ...

/samples/                # Example API request/response payloads
  create-customer-example.json

/prompts/                # AI agent instructions and usage context
  andy-system-prompt.md
  tool-usage-instructions.md

tools-mcp-list.json      # JSON list of all expected tools and endpoints
tool-test-checklist.md   # Manual tracking of tool status
README.md                # This file
