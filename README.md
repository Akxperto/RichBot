# RichBot: AI Policy Navigator

RichBot is an advanced AI orchestration system designed to assist students at Richmond American University London in navigating complex university policies. Built on the **OpenClaw** framework, it employs a robust **Hub and Spoke** (Multi-Agent System) architecture to ensure 100% data grounding, minimal hallucinations, and strict data sovereignty.

## 🏗️ Architecture: Hub & Spoke (MAS)

RichBot operates as a **Central Orchestrator** (the Hub) that delegates specialized queries to a fleet of **Domain Experts** (the Spokes).

### The Hub: RichBot
- **Role:** Central router and synthesis engine.
- **Function:** Analyzes student queries, identifies relevant departments, dispatches tasks to specialists, and synthesizes findings into a single, cohesive response.
- **Protocol:** Follows a strict 3-step sequence: Intent Identification, Departmental Dispatch, and Synthesis with Verbatim Verification.

### The Spokes: Domain Experts
Each specialist has access to a dedicated, partitioned knowledge base (RAG) within their specific domain:
- **Registry Expert:** Admissions, attendance, and grading policies.
- **Finance Expert:** Fees, refunds, and debt management.
- **IT Expert:** Cookies, copyright, and digital privacy.
- **Student Affairs Expert:** Conduct, housing, and safeguarding.
- **General Expert:** Academic appeals, petitions, and university-wide regulations.

## 🛡️ Key Features

- **Data Sovereignty:** All private policy data is hosted locally on a private VPS. Queries are processed without uploading sensitive documentation to third-party training sets.
- **Verbatim Grounding:** Specialists are required to provide exact snippets from policy documents, including page numbers and official URLs, to ensure maximum integrity.
- **Docling Integration:** Uses `docling` for high-fidelity PDF-to-Markdown parsing, enabling the agents to accurately read complex tables and nested policy structures.
- **Conflict Resolution:** The orchestrator manages multi-agent 'Group Chats' to resolve conflicting policy interpretations before the final answer reaches the student.

## 📁 Repository Structure

- `meta/`: Contains the master system prompts that define the logic for RichBot and the Specialists.
- `workspaces/`: Individual agent workspaces containing persona definitions (`SOUL.md`) and domain-specific logic.
- `docs/`: Technical documentation, including the architecture overview, development logs, and the Process Audit Report.
- `config/`: Configuration templates for the OpenClaw environment.

## 📊 Validation: The Gold Standard
The system has been validated against a "Gold Standard" dataset of the 8 most frequently asked student queries, achieving 100% successful user resolution through structural verification and process auditing.

---
**Developed by Alish Salim Andani**
*BSc Computer Science Dissertation, Richmond American University London*
<!-- Last edited: 2026-04-28 14:15 GMT -->
