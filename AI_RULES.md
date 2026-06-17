# 🤖 AI Agent Guidelines & Rules

This repository contains strict protocols for all AI coding assistants and agents (e.g., Cursor, Roo-Code, Cline, Antigravity, GitHub Copilot). These rules prevent merge conflicts, promote clean modularity, and maintain contribution tracking.

---

## 📋 Rule 1: Identity, Role & Task Verification
Before initiating any code generation, code modification, or file creation:
1. **Ask/Verify Identity**: The AI agent **MUST ask the user** to specify or confirm:
   - Who they are (Contributor's Name / Github username).
   - What role they are acting in (`Role 1: Feature Adder` or `Role 2: Bug Fixer / Verifier`).
   - Which specific task or feature from [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md) they want the agent to perform.
2. Locate and read the [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md) file.
3. Verify that the task is registered in the file.
4. Verify if the contributor's name is already entered under the correct role for that task. If not, the AI agent must update [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md) to register the user's name under the task before writing any codebase files.
5. This same verification must also be done manually by human contributors when they claim a task.

---

## 🗂️ Rule 2: Strict Modularity (Separate Files for Every Feature)
To prevent merge conflicts and preserve architecture separation:
1. **Create separate, dedicated files** for every new feature, component, utility, or sub-module.
2. **Do NOT merge** different features into a single file during development.
3. Keep files single-purpose (e.g., separate logic, styles, and templates if applicable).
4. Connect files using explicit and standard import/export mechanisms (e.g., standard ES Modules, Python imports, depending on the language).
5. **No Consolidation**: Under no circumstances should you combine multiple modules/features into a single monolithic file unless the user explicitly tells you: *"make it in a single file now that the project is complete"*.

---

## 🔄 Rule 3: Role-Based Workflow Execution

Depending on your assigned role for the current workspace session:

### If you are acting as Role 1 (Feature Adder):
* Make sure you pull changes before beginning coding.
* Write feature code in a **new separate file**.
* Once the feature is complete and pushed, update the status in the `TASKS.md` registry to indicate it is ready for Role 2 verification.

### If you are acting as Role 2 (Bug Fixer / Verifier):
* Verify the feature added by Role 1.
* Check for bugs, edge cases, and merge issues.
* Make any bug fixes in the feature's dedicated files.
* While verifying/fixing, update the status to `[Role 2 verification pending]`.
* Once verified and fixed, update the status to `[Verified / Closed]`.

---

## ⚠️ Compliance & Verification
* **Check before you build**: The first tool call of your workspace session should involve inspecting the registry and verifying your task status.
* **Refuse monolithic code requests**: If asked to append a new feature directly into an existing unrelated module, refer to these rules and propose creating a separate module/file first.
