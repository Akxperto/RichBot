# RichBot Development Log: COMP 6110

## Project: Agentic AI for University Policy Navigation
**Author:** System Owner (Akxperto)
**Platform:** OpenClaw on Local Server

---

### Milestone 1: Environment & Tooling Setup
- **Action:** Initialized OpenClaw workspace on the local server.
- **Objective:** Establish a private, agentic environment capable of code execution and university data processing without external cloud reliance.
- **Hurdle:** Virtual environment pathing for the `docling` parser.
- **Resolution:** Manually re-pointed symlinks in the parser's configuration to ensure the GPU-accelerated extraction engine could access required libraries.

### Milestone 2: Automated Data Acquisition & Scraping
- **Action:** Executed automated retrieval of the university policy archive.
- **Objective:** Efficiently collect 100+ official policy PDFs from the university website to build the project's raw knowledge base.
- **Detail:** Instructed the system to navigate the university's policy page, identify all relevant PDF links, and automate the download process to a local repository.
- **Result:** Established the `university_rag/policy_data/` directory with verbatim official records, ensuring the system's "Source of Truth" was grounded in primary documents.

### Milestone 3: Multi-Agent Architecture Design
- **Action:** Implemented the Hub-and-Spoke Orchestration model.
- **Objective:** Separate the "Router" logic from the "Specialist" logic to maximize accuracy.
- **Implementation:** Configured the Main Orchestrator (RichBot) to analyze intent and delegate to sub-agents (Registry, Finance, IT, Student Affairs).
- **Control Logic:** Hard-coded `NO_REPLY` protocols for the Main Orchestrator to ensure the sub-agent provides the authoritative final response.

### Milestone 4: Knowledge Base Grounding & Semantic Mapping
- **Action:** Indexed the 51-page Senior Project Handbook and University Policies.
- **Hurdle:** Semantic ambiguity in policy nomenclature.
- **Detail:** Discovered that common student terms like "Academic Probation" are officially titled "Standing and Dismissal" in the administration database.
- **Resolution:** Developed a `policy_links.json` mapping system to translate natural language queries into exact administrative document titles.

### Milestone 5: Infrastructure & Browser Optimization
- **Action:** Browser engine alignment for real-time policy verification.
- **Hurdle:** Chromium port binding mismatch.
- **Detail:** The VPS browser instance was failing to bind to the default port.
- **Resolution:** Aligned the manual port to 18800 and updated the agent's web-automation configuration for stable navigation.

---
*Last edited: 2026-04-19 11:40 GMT*
