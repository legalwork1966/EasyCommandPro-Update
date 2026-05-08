# Easy Command PRO


![Main Window](EASYCOMMANDPRO-UPDATE/page1.png)
![Main Window](EASYCOMMANDPRO-UPDATE/page2.jpg)
![Main Window](EASYCOMMANDPRO-UPDATE/page3.jpg)
© 2019–2026 Starlight IT Solutions  
Designed and programmed by Anthony W. Marinello  
---
# Disclaimer
⚠️ This software drafts system commands for review. 
The user is fully responsible for reviewing and approving any command before execution.

## Overview

Easy Command is a Windows WPF utility that converts natural language into drafted PowerShell or CMD commands, requires explicit user review, and executes only after approval.

**Workflow:**

Natural language → Drafted Windows command → User review → Approved execution

This Community Edition requires users to supply their own OpenAI API key.

---

## Safety Model

- Commands are never auto-executed.
- All drafts are displayed for review before execution.
- Potentially destructive commands require additional confirmation.
- Execution occurs locally on the user’s system.
- Users remain fully responsible for reviewing all generated scripts.

---

## API Configuration

On first launch, the application prompts for your OpenAI API key and stores it as a per-user environment variable (`OPENAI_API_KEY`).

No API keys are bundled or committed with this project.

Users are responsible for managing their own OpenAI API usage and billing.




## Notes
This branch adds a compliance-aware audit pipeline to the WPF app:

- local legal receipts always written first
- optional mirrored telemetry to a PythonAnywhere Flask endpoint
- endpoint outages do not interrupt local logging
- pseudonymous `LicenseId` + stable `InstallId`
- EULA and telemetry consent with maximally defensible retention defaults
- local retention default: 365 days
- remote basic telemetry default: 180 days
- remote full telemetry default: 90 days

## Local files

Stored under:

`%LOCALAPPDATA%\EasyCommand.AgentWorkbench`

Important files:

- `settings.json`
- `app-log.jsonl`
- `legal-receipts.jsonl`
- `pending-telemetry\*.json`

## Notes

- Local legal receipts remain the primary evidence trail.
- Remote upload is best-effort and non-blocking.
- If the endpoint is unavailable, the app keeps writing local receipts and logs the endpoint outage.
