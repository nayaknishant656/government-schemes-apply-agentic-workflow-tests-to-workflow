

# 🏛️ GovAgent-OS: Autonomous Government Benefits Orchestrator

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Tech: Agentic-AI](https://img.shields.io/badge/Tech-Agentic--AI-blueviolet)](https://github.com/topics/agentic-ai)

An end-to-end agentic system that transforms how citizens interact with bureaucracy. By combining **Voice-to-Action (TTS/STT)** with **Autonomous Web Agents**, this system identifies, verifies, and applies for government schemes on behalf of the user with minimal friction.

---

## 🚀 The Vision

Navigating government portals is often a "tax on the poor" due to its complexity. **GovAgent-OS** flips the script:
1.  **Proactive Discovery:** Automatically finds new schemes matching user profiles.
2.  **Autonomous Execution:** Navigates brittle government websites using LLM-based web drivers.
3.  **Minimal Verification:** Uses cross-departmental data syncing to reduce redundant "upload document" steps.

---

## 🛠️ System Architecture

### 1. Input Interface (Multimodal)
* **Voice Engine:** High-fidelity STT (Speech-to-Text) and TTS for accessibility.
* **User Context Vault:** Encrypted storage of citizen attributes (age, income, location, occupation).

### 2. The Orchestration Layer (The "Agent")
* **Scheme Scraper:** A background worker that monitors official PDFs, gazettes, and portals.
* **Reasoning Engine:** Uses an LLM (e.g., Gemini 1.5 Pro) to map natural language queries to legal eligibility criteria.
* **Action Planner:** Breaks down a scheme application into a sequence of browser-level tasks.

### 3. Execution Layer (Web Automation)
* **Browser-Use / Playwright:** Headless agents that navigate non-API-based government portals.
* **Auto-Form Filler:** Maps User Context Vault data to dynamic form fields.
* **Verification Bridge:** Interfaces with digital identity lockers (like DigiLocker or eID) to fetch verified credentials.

---

## 🔄 Technical Workflow

```mermaid
graph TD
    A[User Voice Query/App Request] --> B{Intent Parser}
    B --> C[Profile Analysis]
    C --> D[Latest Scheme Database]
    D --> E{Eligibility Match}
    E -- Match Found --> F[Agentic Browser Session]
    F --> G[Auto-Verification/Document Fetch]
    G --> H[Form Submission]
    H --> I[Push Notification / TTS Confirmation]
