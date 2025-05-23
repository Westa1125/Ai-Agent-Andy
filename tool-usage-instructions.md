# Tool Usage Instructions

## Overview
These MCP tools are accessed by the AI agent (Andy) during live customer calls. The tools are built as individual HTTP request nodes inside n8n and are triggered with parameters passed dynamically from Andy's AI logic.

## General Usage Pattern
- Agent decides which tool to use based on call content.
- Required parameters are extracted from the conversation.
- Tool is invoked via HTTP node using REST API syntax.
- Response is processed and interpreted to form a reply or next step.

## Example: create-customer
- Required fields: firstName, lastName, phone
- AI checks if customer exists → If not, calls `create-customer`
- Parses the API response to confirm success
- Then logs a note or schedules a job if needed

## Example: get-jobs-by-customer-id
- Input: customerId
- Agent fetches job history to see if customer is active or a candidate for follow-up
- Response used to summarize job count, types, or dates

## Naming Convention
- Tool names match this format: `verb-object` (e.g., `create-customer`)
- All tools return JSON and should gracefully handle errors

## Error Handling
- If a tool fails or returns an error:
  - Agent should log the issue
  - Optionally fallback to creating a task for human follow-up

## Notes
All tools follow the ServiceTitan v2 API documentation structure.
