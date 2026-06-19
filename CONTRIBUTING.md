# Open-Source Contribution Guidelines

Welcome to **FINDING_AI**! We are thrilled to have you here. To ensure smooth collaboration, maintain a high-quality codebase, and minimize merge conflicts, we follow a structured contribution workflow. 

---

## 👥 Contributor Roles

We separate duties into two distinct roles to support division of labor, code quality, and active validation.

### 🚀 Role 1: Feature Adder
* **Responsibility**: Implement new features or tasks listed in `TASKS.md`.
* **Workflow**:
  1. Pull the latest changes from the main branch: `git pull origin main`.
  2. Select an `[Open]` task from **[TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md)**.
  3. Register yourself as the **Feature Adder** by adding your name/GitHub handle to the task entry in `TASKS.md` and setting status to `[Claimed - Role 1]`.
  4. Develop the feature in **separate, modular files** (do not write large monolithic files or modify unrelated files). Connect files using standard import/export structures.
  5. Write tests for your feature.
  6. Commit your changes and open a Pull Request. Update the task status to `[Role 2 verification pending]`.

### 🛡️ Role 2: Bug Fixer / Verifier
* **Responsibility**: Review, merge-conflict check, test, and verify code submitted by Role 1.
* **Workflow**:
  1. Select a task with status `[Role 2 verification pending]`.
  2. Register yourself as the **Bug Fixer / Verifier** in `TASKS.md` under the task.
  3. Review the code. Pull the PR locally and run tests. Look for edge cases, performance issues, or architectural alignment.
  4. Fix any bugs, style deviations, or merge conflicts directly in the feature's dedicated files.
  5. Once fully verified, update the task status in `TASKS.md` to `[Verified / Closed]`.

---

## 🌿 Git Branching Conventions

Name your branches according to the purpose of the work:
* **Features**: `feature/module-<number>-<short-description>` (e.g. `feature/module-1-login-jwt`)
* **Bug Fixes**: `bugfix/module-<number>-<short-description>` (e.g. `bugfix/module-3-ollama-timeout`)
* **Documentation**: `docs/<description>` (e.g. `docs/setup-instructions`)
* **Refactoring**: `refactor/<description>` (e.g. `refactor/skill-graph-indexes`)

---

## ✍️ Commit Conventions

We follow the **Conventional Commits** specification. Commits should be structured as follows:
`<type>(<scope>): <description>`

**Common Types**:
* `feat`: A new feature (corresponds to Role 1)
* `fix`: A bug fix (corresponds to Role 2 or immediate patches)
* `docs`: Documentation changes only
* `style`: Changes that do not affect the meaning of the code (white-space, formatting)
* `refactor`: A code change that neither fixes a bug nor adds a feature
* `test`: Adding missing tests or correcting existing tests

**Examples**:
* `feat(auth): implement employer account registration schema`
* `fix(matching): resolve divide-by-zero bug in experience decay`
* `docs(readme): add link to local LLM configuration`

---

## 📐 Modularity & Coding Standards

To prevent merge conflicts in a highly collaborative environment, we enforce the **Strict Modularity Rule**:
1. **Never append unrelated code** to existing monolithic files.
2. Every new feature, UI widget, database helper, or API routing file must be created as a **new, dedicated file** and imported explicitly.
3. Keep frontend components reusable and isolated.
4. Keep backend routing handlers thin; move business logic into dedicated service files (e.g. `services/matching.py`, `services/ollama_client.py`).
5. **Code Style**:
   - **Frontend**: Follow ESLint and Prettier formatting (configured in the repository root). Use TypeScript types strictly; avoid `any`.
   - **Backend**: Follow PEP 8 guidelines for Python code. Document API functions with clear type hints.

---

## 📤 Pull Request Checklist

When submitting a Pull Request (PR):
1. Use our standard **[Pull Request Template](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/.github/PULL_REQUEST_TEMPLATE.md)** to document your changes.
2. Link the issue or specify the `TASKS.md` task number being addressed.
3. Ensure all tests pass.
4. Explicitly state whether you are acting as **Role 1 (Feature Adder)** or **Role 2 (Verifier)**.

---

## 🤖 AI Agent Guidelines

If you are using an AI assistant (like Roo-Code, Cline, or Cursor) to help you code, please ensure the agent complies with our strict protocols in **[AI_RULES.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/AI_RULES.md)** and **[.cursorrules](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/.cursorrules)**. AI agents must ask for your identity and register tasks in `TASKS.md` prior to code generation.
