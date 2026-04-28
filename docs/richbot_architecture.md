# RichBot: Agentic AI for University Policy Navigation
## Technical Architecture & System Notes

### 1. Overview
RichBot is a multi-agent system designed to provide students with accurate, grounded, and verbatim information regarding university policies. It operates as a central **Orchestrator** that delegates specific queries to a specialized team of **Sub-Agents**.

### 2. Multi-Agent Architecture
The system follows a "Hub-and-Spoke" model to ensure modularity and high accuracy in document retrieval.

#### A. The Orchestrator (RichBot)
- **Role:** Central Router and Dispatcher.
- **Responsibility:** Analyzes the user's query, identifies the relevant department, and spawns the appropriate sub-agent.
- **Turn Management:** Uses `NO_REPLY` protocols to step back once a sub-agent is triggered, allowing the specialist to provide the final answer directly to the user.

#### B. Specialized Sub-Agents (The Experts)
Each sub-agent is grounded in a specific directory of policy documents:
- **Registry Bot:** Academic standing, grading, transcripts, and admissions.
- **Finance Bot:** Tuition fees, scholarships, refund policies, and payment plans.
- **Student Affairs Bot:** Conduct, housing, appeals, and misconduct procedures.
- **IT Bot:** Data privacy, recording policies, and usage rules.

### 3. Communication & Knowledge Retrieval
#### A. Grounding Protocol (The RAG Engine)
- **Data Acquisition:** The knowledge base was initialized via automated scraping of the university's official policy portal, resulting in a local repository of 100+ PDF documents.
- **Data Processing:** A curated library of Markdown files converted from these official PDFs using the `docling` parser.
- **Mapping:** A central `policy_links.json` file maps policy titles to their official URLs to provide "Source of Truth" links in every response.
- **Context Management:** Sub-agents are instructed to only provide information found within their assigned document scope to prevent "hallucinations."

#### B. In-System Communication
1. **User Request:** "What is the policy on late submission?"
2. **Orchestrator Analysis:** Identifies this as an "Academic/Registry" concern.
3. **Sub-Agent Spawn:** Spawns `Registry-Bot` with access to `policies_markdown/Registry/`.
4. **Sub-Agent Execution:** `Registry-Bot` reads the "Late Submission of Coursework Policy," extracts the verbatim penalty rules, and replies.
5. **Final Output:** The user receives the exact rule and a link to the official PDF.

### 4. Technical Hurdles & Implementations
- **Semantic Translation:** The system translates common student terms (e.g., "Probation") into official administrative titles (e.g., "Standing and Dismissal") using internal logic mappings.
- **Browser Automation:** Uses a headless Chromium instance (Port 18800) for real-time web verification when policy documents reference external web resources.
- **GPU-Accelerated Parsing:** Utilizes the `docling` engine with local virtual environments to handle high-fidelity text extraction from complex university handbooks.

---
*Created: 2026-04-19 11:35 GMT*
<!-- Last edited: 2026-04-19 11:35 GMT -->
