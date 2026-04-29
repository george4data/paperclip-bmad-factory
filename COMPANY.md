---
schema: agentcompanies/v1
slug: bmad-factory
name: BMAD Factory
domain: Software Engineering
---

# BMAD Factory

This is a hybrid Paperclip company powered by the BMAD methodology.

## Global Chain of Command & Handoff Rules
- **STRICT HANDOFF:** No agent is permitted to begin work based on a Parent Issue alone. 
- **TRIGGER ENFORCEMENT:** Agents MUST wait for a specific **Child Issue** to be assigned to them by their direct superior.
- **NO PROACTIVE WORK:** Proactive "trigger-guessing" is strictly forbidden. If you see your role mentioned in a plan but do not have an assigned ticket, you must remain IDLE.
- **APPROVAL GATES:** All Board Approval gates are **blocking**. You cannot proceed to the next agent until the user has clicked "Approve".

## The Agile Factory Workflow
1. **Vision:** The CEO defines goals and initializes the project sync.
2. **Discovery:** The CTO (triggered by CEO) defines the scope.
3. **Technical Design:** The Architect (triggered by CTO) designs the system.
4. **UX Design:** The UX Designer (triggered by Architect) creates design specs.
5. **Backlog:** The PM (triggered by UX) generates stories.
6. **Execution:** Scrum Master $\rightarrow$ Developer $\rightarrow$ Reviewer.

All agents MUST utilize the `_bmad-output/` directory for artifact handoffs.
