# BMAD Factory Operations Manual

This document outlines the exact steps to boot up your [Paperclip](https://github.com/paperclipai/paperclip) control plane, configure the BMAD Factory, point it to your local codebase, and kick off your AI workforce.

## Prerequisites

Before you begin, you need to clone two repositories: **[Paperclip](https://github.com/paperclipai/paperclip)** (the control plane) and **this BMAD Factory** (the agent company configuration).

### 1. Clone Paperclip
```bash
git clone https://github.com/paperclipai/paperclip.git /path/to/paperclip
cd /path/to/paperclip
pnpm install
```

### 2. Clone the BMAD Factory
```bash
git clone https://github.com/george4data/paperclip-bmad-factory.git /path/to/bmad-factory
```

### 3. Ensure Node.js and pnpm are installed
- [Node.js](https://nodejs.org/) (v18+)
- [pnpm](https://pnpm.io/installation): `npm install -g pnpm`

---

## Phase 1: Booting the Server
To use [Paperclip](https://github.com/paperclipai/paperclip), the API and web server must be running.

1. Open a terminal and navigate to the Paperclip repository:
   ```bash
   cd /path/to/paperclip
   ```
2. Start the server:
   ```bash
   pnpm dev
   ```
3. Keep this terminal window open. The web dashboard is now accessible at `http://localhost:3100`.

## Phase 2: Installing the BMAD Skills to your Target Codebase
Your AI workers need their tools in the actual codebase they will be editing.

1. Open a **second** terminal window.
2. Navigate to your target project codebase (e.g., `my-project`):
   ```bash
   cd /path/to/your-project
   ```
3. Install the BMAD handbook into this specific project:
   ```bash
   npx bmad-method install
   ```
   *(Ensure you select Claude Code, Gemini CLI, Cursor, and Antigravity during setup).*

## Phase 3: Loading the Company into Paperclip
You only need to do this once, or whenever you modify the instructions in the `bmad-factory` folder.

> **⚠️ Important — Rename your company first!**
> Before importing, open `COMPANY.md` and update the `name` and `slug` fields to reflect your own company. If you skip this step, it will be loaded into [Paperclip](https://github.com/paperclipai/paperclip) as **"BMAD Factory"** instead of your company name.
>
> ```yaml
> ---
> schema: agentcompanies/v1
> slug: your-company-name      # ← change this
> name: Your Company Name      # ← change this
> domain: Software Engineering
> ---
> ```

1. In your second terminal window, run the import command:
   ```bash
   npx paperclipai company import /path/to/bmad-factory
   ```


## Phase 4: Linking the Codebase and Assigning Work
Now you orchestrate the work through the web interface.

1. Open `http://localhost:3100` in your browser.
2. Select **BMAD Factory** from the company selector.
3. Navigate to **Repositories** (or Projects) and click **Add Repository**. Provide the local path to your codebase:
   `/path/to/your-project`
4. Go to **Issues** and create a new Parent Issue (e.g., *"Design and implement the monetization strategy"*).
5. Attach this issue to your newly linked repository.
6. Assign the issue to the **CEO** or **CTO**.

The agents will wake up inside your project folder, use Git, run BMAD skills, and orchestrate the handoffs automatically!

---

> Built on top of [Paperclip](https://github.com/paperclipai/paperclip) — the open-source AI agent control plane.
