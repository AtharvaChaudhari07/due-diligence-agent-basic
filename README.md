# Due Diligence Research and Analysis System

A structured company due-diligence research workflow built using **LangGraph** and **Google Gemini**. 

The system takes a broad company research objective, breaks it into focused subtasks, performs targeted web research for each area, verifies important findings, and consolidates the results into a final executive assessment.

---

## What It Does

The workflow organizes company due diligence across four key areas:

*   **Financial Health** — Revenue, profitability, financial position, funding, and financial concerns.
*   **News & Recent Developments** — Important events, controversies, positive developments, and overall sentiment.
*   **Competitive Position** — Market position, competitors, competitive advantages, and competitive threats.
*   **Business Risks** — Legal, regulatory, operational, reputational, strategic, and technology risks.

The purpose is to turn a broad and time-consuming research problem into smaller, focused investigations that can be handled systematically.

---

## Workflow

### 1. Research Planning
The workflow starts at the **Research Planning** node. 
The user provides the company and the research objective. Gemini analyzes this objective and produces a structured research plan containing:
*   Company context
*   Focus areas
*   Specific subtasks for each research area
*   Initial risk hypothesis

The broad due-diligence objective is therefore converted into smaller, clearly defined research tasks.

### 2. Fan-Out to Focused Research Nodes
After planning, LangGraph fans out the shared state to four research nodes:

```text
                    Research Planning
                           │
                           ▼
                     Research Plan
                           │
            ┌──────────────┼──────────────┐
            ▼              ▼              ▼              ▼
       Financial         News       Competitive        Risk
        Research       Research      Research         Research

        
