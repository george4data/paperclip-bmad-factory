# BMAD Factory Operations Manual

This document outlines the exact steps to boot up your Paperclip control plane, configure the BMAD Factory, point it to your local codebase, and kick off your AI workforce.

## Phase 1: Booting the Server
To use Paperclip, the API and web server must be running.

1. Open a terminal and navigate to the Paperclip repository:
   ```bash
   cd /Users/georgesp/Dev/paperclip-master
   ```
2. Start the server:
   ```bash
   pnpm dev
   ```
3. Keep this terminal window open. The web dashboard is now accessible at `http://localhost:3100`.

## Phase 2: Installing the BMAD Skills to your Target Codebase
Your AI workers need their tools in the actual codebase they will be editing.

1. Open a **second** terminal window.
2. Navigate to your target project codebase (e.g., QueueHamster):
   ```bash
   cd /Users/georgesp/Dev/QueueHamster
   ```
3. Install the BMAD handbook into this specific project:
   ```bash
   npx bmad-method install
   ```
   *(Ensure you select Claude Code, Gemini CLI, Cursor, and Antigravity during setup).*

## Phase 3: Loading the Company into Paperclip
You only need to do this once, or whenever you modify the instructions in the `bmad-factory` folder.

1. In your second terminal window, run the import command:
   ```bash
   npx paperclipai company import /Users/georgesp/Dev/bmad-factory
   ```
   *(Note: If you want to rename the company locally, edit `COMPANY.md` before running this).*

## Phase 4: Linking the Codebase and Assigning Work
Now you orchestrate the work through the web interface.

1. Open `http://localhost:3100` in your browser.
2. Select **BMAD Factory** from the company selector.
3. Navigate to **Repositories** (or Projects) and click **Add Repository**. Provide the local path to your codebase:
   `/Users/georgesp/Dev/QueueHamster`
4. Go to **Issues** and create a new Parent Issue (e.g., *"Design and implement the monetization strategy"*).
5. Attach this issue to your newly linked QueueHamster repository.
6. Assign the issue to the **CEO** or **CTO**.

The agents will wake up inside the `/Users/georgesp/Dev/QueueHamster` folder, use Git, run BMAD skills, and orchestrate the handoffs automatically!
