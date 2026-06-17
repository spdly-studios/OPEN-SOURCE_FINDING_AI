# Open-Source Contribution Guidelines

Welcome to our open-source project! To ensure smooth collaboration and maintain a high-quality codebase, we follow a structured contribution workflow. This guide outlines how contributors can add features, fix bugs, and verify changes.

---

## 👥 Contributor Roles

We have defined two distinct roles for contributors to maintain division of labor and high quality:

### 🚀 Role 1: Feature Adder
* **Responsibility**: Implement new features or tasks.
* **Workflow**:
  1. Pull the latest changes from the repository: `git pull origin main`.
  2. Select an open task/feature from [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md).
  3. Register yourself as the **Feature Adder** by adding your name to the task entry in [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md).
  4. Develop the feature in **separate, modular files** (do not merge everything into a single file or write massive monolithic files). Connect your files using standard imports/exports.
  5. Commit and push your changes.

### 🛡️ Role 2: Bug Fixer / Verifier
* **Responsibility**: Review, test, and merge/verify code pushed by Role 1.
* **Workflow**:
  1. When a Feature Adder (Role 1) pushes their changes, the task enters the **Verification Pending** state.
  2. Look into the implementation, check for bugs, merge conflicts, or style inconsistencies.
  3. Fix any bugs or conflicts directly in the feature code.
  4. Once verification is ready to be pushed or is actively being tested, update the registry status in [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md) to `Role 2 verification pending`.
  5. Once fully verified and working, change the status to `Verified / Closed` and add your name as the **Bug Fixer / Verifier** in [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md).

---

## 📋 Features & Tasks Registry

All features, tasks, and assignments are managed in the separate [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md) file. 

Before starting any work, please check [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md) to claim tasks, enter your name/username under the task you are taking, and update the task's status.

---

## 🤖 Rules for AI Agents

AI agents participating in this project MUST read and follow the instructions in the [AI_RULES.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/AI_RULES.md) file.
Key points include:
1. Always check the **Features & Tasks Registry** before beginning work.
2. Only claim tasks that are in `[Open]` status.
3. Respect role boundaries (Feature Adder vs. Bug Fixer).
4. **Modularity Principle**: Always write new features in separate, dedicated files to prevent git conflicts.
