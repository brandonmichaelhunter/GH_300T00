# Accelerate development with GitHub Copilot coding agent
- Explain what the Copilot coding agent is, how it differs from IDE assistants, and how to enable and budget for it.
- Describe the agent's built-in protections, main risks, mitigations, and its workflow and compatibility limits.
- Assign issues to Copilot, track its pull-request sessions, iterate with @copilot comments, and troubleshoot problems.
- Preconfigure the agent's environment, extend its capabilities with MCP, and test and validate its output before merging.
- Apply responsible-use practices, scope tasks effectively, secure environments, and improve performance.
----


## 🚀 What the GitHub Copilot Coding Agent *Is*
- An **autonomous development assistant** that runs **inside GitHub**, not just in your IDE.  
- Acts like a **background teammate** that performs scoped development tasks end‑to‑end.  
- Creates branches, writes commits, opens draft PRs, updates PR descriptions, and requests your review automatically.   [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

## 🌍 Availability & Eligibility
- Available on **Copilot Pro, Copilot Pro+**, **Copilot Business**, and **Copilot Enterprise** plans.  
- Works in **all GitHub‑hosted repositories**, except those owned by managed user accounts or where explicitly disabled.   [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

## 🧠 What the Coding Agent Can Do
The agent can autonomously complete a wide range of tasks, including:  
- Fixing bugs and regressions  
- Implementing incremental features  
- Improving or generating tests  
- Updating or creating documentation  
- Addressing technical debt and backlog items  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

## 📝 How You Delegate Work to the Agent
Two primary ways:  
- **Assign an issue** to Copilot (GitHub.com, Mobile, API/CLI).  
- **Ask Copilot to create a pull request** (Agents panel, Copilot Chat, IDE with MCP support, Raycast).  
When finished, the agent requests your review, and you can mention **@copilot** in PR comments to iterate.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

## 🆚 Coding Agent vs. IDE Assistants
### **Traditional IDE Assistants**
- Help write code locally  
- Require manual branch creation, commits, PR creation  
- Work happens privately and isn’t visible to the team  

### **Copilot Coding Agent**
- Runs in GitHub’s environment  
- Automates branches, commits, PRs, and descriptions  
- All work is visible in session logs and PR history  
- Collaboration and traceability are built‑in  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

## 🆚 Coding Agent vs. Agent Mode (IDE)
- **Coding Agent:**  
  - Runs autonomously in GitHub Actions environment  
  - Produces PRs as output  
  - Triggered via issues or Copilot Chat  

- **Agent Mode (Copilot Edits):**  
  - Runs locally in your IDE  
  - Performs autonomous edits directly in your workspace  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

## 🔧 Enabling the Coding Agent
- **Organization-owned repos:** Admins control availability.  
- **Personal repos:** Enable via account settings.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

## 💰 Usage Costs: GitHub Actions Minutes + PRUs
The coding agent consumes two resources:  
- **GitHub Actions minutes** — used for the ephemeral environment where the agent runs.  
- **Premium Request Units (PRUs)** — used for advanced model reasoning.  
  - From **June 4, 2025**, each model request consumes one PRU.  
  - Use PRUs strategically for multi-file edits, test generation, and complex diffs.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

---

# 📝 GH‑300 Exam Focus Areas
Expect questions on:
- What the coding agent is and how it differs from IDE assistants and Agent Mode.  
- Supported plans and repository requirements.  
- How to delegate tasks and how the agent completes them.  
- How PR review and iteration with @copilot works.  
----
Below is a **clear, exam‑focused summary** of the key concepts you need to know from the unit **“Security, risks, and limitations of the Copilot coding agent”**, based directly on the article content you provided.  
Citations reference the fetched page.   [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

---

## 🔐 **Security Model & Built‑In Protections**
The Copilot coding agent is designed to operate **inside your organization’s existing governance**, adding its own guardrails. Key points:

### **Governance & Permissions**
- Organization/enterprise settings fully govern agent availability.  
- All existing security policies continue to apply.  
- Only users with **write permissions** can trigger the agent; others are ignored.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

### **Sandboxed Execution**
- Runs inside a **restricted GitHub Actions sandbox**.  
- Internet access is **firewalled by default**.  
- Repository access is **read‑only**, preventing unauthorized writes.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

### **Branch & Workflow Controls**
- Can only push to branches starting with `copilot/`.  
- All branch protections and required checks still apply.  
- Draft PRs require approval from a user with write access before workflows run.  
- The requester **cannot** approve the agent’s PR.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

### **Compliance & Attribution**
- All commits are **co‑authored** with the developer who initiated the task.  
- Required approvals and compliance rules remain intact.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

---

## ⚠️ **Risks & GitHub’s Mitigations**

### **Risk: Agent pushes code**
**Mitigations:**  
- Only write‑permission users can trigger work.  
- Pushes restricted to `copilot/` branches.  
- Workflows don’t run until a write‑permission user approves.  
- Requestor cannot approve the PR.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

### **Risk: Access to sensitive information**
**Mitigation:**  
- Firewall‑restricted internet access; can be customized or disabled by policy.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

### **Risk: Prompt injection**
**Mitigation:**  
- Hidden characters (HTML comments, invisible text) are filtered before input reaches the agent.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

---

## 🚫 **Known Limitations**

### **Workflow Limitations**
- Can only modify code **within the same repository** as the assigned issue/PR.  
- Context limited to the repo unless expanded via MCP.  
- Creates **exactly one PR per task**.  
- Cannot modify PRs it didn’t create (but can be added as a reviewer).  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

### **Compatibility Limitations**
- Does **not** sign commits; signed‑commit workflows require manual rewriting.  
- Requires **GitHub‑hosted Ubuntu x64 runners** (no self‑hosted runner support).  
- Not available for personal repos owned by managed user accounts.  
- Ignores content‑exclusion rules; can see/update excluded files.  
- “Suggestions matching public code” policy not enforced.  
- Only works with GitHub‑hosted repositories.  
- AI model selection is fixed; you cannot change the model.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

---

# 📝 GH‑300 Exam Focus Areas
Expect exam questions on:

- How the coding agent enforces security and governance.  
- Branch restrictions, workflow approvals, and permission boundaries.  
- Risks (code pushes, sensitive data, prompt injection) and their mitigations.  
- Workflow limitations (single PR, repo‑scoped context).  
- Compatibility constraints (runners, commit signing, content exclusions).  
- Why developer oversight is still required despite guardrails.

---
Absolutely, Brandon — here’s a **clean, exam‑focused summary** of the key concepts you need to know from the unit **“Assigning, tracking, and troubleshooting Copilot coding agent tasks.”**  
This is distilled directly from the article content you provided.

---

## 🧩 What This Unit Covers
You should understand how to:
- Assign issues to the Copilot coding agent  
- Track its progress through PR timelines and session logs  
- Iterate with the agent using PR comments  
- Apply approval rules for agent‑generated PRs  
- Troubleshoot common problems  

---

# 🟦 1. Assigning Issues to Copilot

### **How assignment works**
- Assigning an issue to Copilot triggers the agent to:
  - Add an 👀 reaction to the issue  
  - Create a `copilot/` branch  
  - Open a **draft pull request** linked to the issue  
  - Start an **agent session** in a GitHub Actions environment  
  - Push commits and update the PR body with status messages  

### **Where you can assign issues**
- GitHub.com (Issues tab → Assignees → Copilot)  
- GitHub Mobile  
- GitHub Projects  
- GitHub CLI (`gh issue edit`)  

### **Important behavior**
- Copilot only sees the **issue title, description, and comments at assignment time**.  
- New information must be added as **comments on the PR**, not the issue.

---

# 🟦 2. Assigning via the API (GraphQL)

You should know the workflow at a high level:
- Check availability using `suggestedActors`  
- Fetch the repository ID  
- Create and assign a new issue using `createIssue`  
- Assign an existing issue using `replaceActorsForAssignable`  

This is useful for automation and integrating Copilot into workflows.

---

# 🟦 3. Tracking Copilot’s Progress

### **Key signals you’ll see**
- 👀 **Reaction** on the issue (acknowledgment)  
- **Draft PR creation** linked to the issue  
- **“Copilot started work”** event in the PR timeline  
- **Live session logs** available via the Agents page  
- **Commits pushed** to the `copilot/` branch  
- **“Copilot finished work”** event when done  
- Copilot **requests your review**  

### **Live session logs**
- Show real‑time actions  
- Allow you to stop the session if needed  

---

# 🟦 4. Iterating With Copilot

### **How to request changes**
- Comment on the PR and mention **@copilot**  
- Only users with **write access** can issue instructions  
- Copilot reacts with 👀 to confirm it received the request  
- A new **“Copilot started work”** event appears as it resumes  

This mirrors normal human code review workflows.

---

# 🟦 5. Approvals & Workflow Rules

### **Important governance behaviors**
- Copilot PRs are **always draft**  
- They require **human approval** before merge  
- GitHub Actions workflows **do not run automatically**  
- To run workflows, you must click **“Approve and run workflows”**  
- The person who requested the PR **cannot approve it**  
  - Ensures independent review  
  - Preserves required-review policies  

---

# 🟦 6. Troubleshooting Guide (Know These for GH‑300)

### **Common issues & resolutions**
- **Copilot not in Assignees list**  
  - Check plan eligibility  
  - Ensure agent isn’t disabled at org/repo level  
  - Verify at `github.com/settings/copilot/features`  

- **Not available for EMU personal repos**  
  - Must use org‑owned repos  

- **“Cannot create a pull request” from Chat**  
  - Ensure agent is enabled  
  - In IDEs, mention `@github` in the prompt  

- **Assigned issue but nothing happens**  
  - Look for 👀 reaction and draft PR  

- **PR created but no progress**  
  - Check for “Copilot started work”  
  - Open session logs  

- **Agent not responding to PR comments**  
  - Ensure you have write access  
  - Ensure you mentioned `@copilot`  

- **Agent appears stuck**  
  - Sessions timeout after 1 hour  
  - Retry by unassigning/reassigning or re‑commenting  

- **Actions not running**  
  - Click **Approve and run workflows**  

- **Pushes fail CI**  
  - Add `.github/copilot-instructions.md` for better guidance  

- **Firewall warnings**  
  - Internet is restricted by default  
  - Adjust firewall settings if needed  

- **Images not picked up**  
  - Max size is 3 MiB  

---

# 📝 GH‑300 Exam Focus Areas

Expect questions on:
- How to assign issues to Copilot (UI, CLI, API)  
- How Copilot signals progress (PR events, logs, reactions)  
- How to iterate using PR comments and @copilot  
- Approval rules and workflow restrictions  
- How to troubleshoot common agent issues  
- Why Copilot PRs require human approval  
- How session logs and agent sessions work  

---


# 🟦 1. Preseeding the Agent’s Development Environment  
The Copilot coding agent runs inside a **secure, ephemeral GitHub Actions environment**. You can customize this environment to improve reliability and speed.

### **Key Concepts**
- Create a workflow named:  
  **`.github/workflows/copilot-setup-steps.yml`**
- Must contain **one job** named:  
  **`copilot-setup-steps`**
- Use it to **preinstall tools, dependencies, and secrets** the agent needs.

### **Allowed configuration keys**
- `steps`  
- `permissions`  
- `runs-on`  
- `container`  
- `services`  
- `snapshot`  
- `timeout-minutes` (≤ 59)

### **Important behaviors**
- `actions/checkout` fetch-depth is overridden for safe rollback.  
- Workflow runs **standalone** (so you can validate it) and then **automatically before the agent starts**.

### **Larger GitHub-hosted runners**
- You can specify larger runners (e.g., `ubuntu-4-core`).  
- Only **Ubuntu x64 GitHub-hosted runners** are supported.  
- **Self-hosted runners are NOT supported.**

### **Git LFS support**
- Enable via checkout step:  
  `with: lfs: true`

### **Firewall customization**
- Internet access is **restricted by default**.  
- Can be customized or disabled per organization policy.

---

# 🟦 2. Extending the Agent with MCP (Model Context Protocol)

### **What MCP Is**
- An **open standard** that lets LLMs connect to external tools and data sources.  
- The coding agent can use **MCP tools** to expand its capabilities.

### **Important limitations**
- Only **MCP tools** are supported (not resources or prompts).  
- Remote MCP servers requiring **OAuth** are **not supported**.

### **Default MCP Servers**
- **GitHub MCP Server**  
  - Read-only access to issues, PRs, repo data.  
  - Uses a token scoped to the current repo (customizable).

- **Playwright MCP Server**  
  - Allows the agent to read, interact with, and screenshot web pages accessible inside its environment (localhost/127.0.0.1).

### **Repository Configuration**
- Admins declare MCP servers via a **JSON configuration file**.  
- Once configured, the agent uses tools **autonomously**—no approval prompts.

### **Best Practices**
- Review third‑party MCP servers for performance and quality.  
- Prefer **read-only** tools; allow write tools only when necessary.  
- Validate MCP configuration carefully before committing.

---

# 🟦 3. Testing & Validating Agent Output

### **Developer responsibility**
You remain accountable for **quality, security, and correctness**.

### **Best Practices**
- Run CI (tests, linting, scanning) on every agent PR.  
  - These checks **do not run** until you click **“Approve and run workflows.”**
- Manually inspect high‑impact or sensitive changes.  
- Ask the agent to generate tests (multi-file test generation uses PRUs).  
- Enforce rulesets requiring tests + scanning + linting before merge.  
- Label agent PRs (e.g., `agent-refactor`, `agent-tests`) for tracking.  
- Update `.github/copilot-instructions.md` when you see repeated mistakes.  
- Revert quickly if needed and request new changes.

### **Using PRUs intentionally**
Use PRUs for:
- Deep validation  
- Test coverage expansion  
- Directory-wide audits  
- Risky area scans  

Use lightweight checks when possible to conserve PRUs.

---

# 📝 GH‑300 Exam Focus Areas

Expect questions on:

### **Preseeding**
- Purpose of `copilot-setup-steps.yml`  
- Allowed configuration keys  
- Runner limitations (Ubuntu x64 only, no self-hosted)  
- Git LFS and firewall customization  

### **MCP**
- What MCP is and how it extends the agent  
- Default MCP servers (GitHub, Playwright)  
- Limitations (tools only, no OAuth servers)  
- Best practices for configuring MCP  

### **Validation**
- CI requirements and workflow approval  
- How to validate and test agent output  
- When and why to use PRUs  
- How `.github/copilot-instructions.md` improves results  

---
Here’s a **clear, exam‑focused summary** of the key concepts you need to know from the unit **“Responsible use of GitHub Copilot coding agent on GitHub.com”**, based directly on the article content you provided   [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/5-responsible-use-github-copilot-code-agent-github).

---

## **Unit: Responsible Use of GitHub Copilot Coding Agent on GitHub.com**

---

## 🟦 1. Purpose & Capabilities of the Coding Agent
- Autonomous, asynchronous software development agent integrated into GitHub.  
- Picks up tasks from **issues**, **PR comments**, or **Copilot Chat**.  
- Creates a **pull request**, iterates based on feedback, and updates the PR description.  
- Works inside an **ephemeral development environment** where it can:
  - Modify code  
  - Run tests  
  - Execute linters  
- Supports many languages; English is the primary supported language.  
- Handles tasks such as:
  - Bug fixes  
  - Incremental features  
  - Documentation updates  
  - Test improvements  
  - Codebase maintenance  
  - Prototyping new projects  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/5-responsible-use-github-copilot-code-agent-github)

---

## 🟦 2. How the Agent Works (End‑to‑End Workflow)
- **Prompt Processing:**  
  Combines issue/PR/chat input with contextual repo information. Accepts natural language, code, and images.
- **Language Model Analysis:**  
  Uses an LLM to reason about the task and determine required actions.
- **Response Generation:**  
  Produces code changes or natural language suggestions.
- **Output Formatting:**  
  Updates the PR description with changes, limitations, and next steps.  
- **Iteration:**  
  You can comment or mention **@copilot** to request updates; the agent re-analyzes and updates the PR.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/5-responsible-use-github-copilot-code-agent-github)

---

## 🟦 3. Responsible‑Use Practices (Critical for GH‑300)
### **Scope Tasks Clearly**
Provide:
- Clear problem description  
- Acceptance criteria  
- File hints or pointers  

### **Customize Context**
- Add **custom Copilot instructions** to guide build/test/validation steps.  
- Customize:
  - Development environment  
  - Firewall settings  
  - MCP extensions  

### **Use as a Tool, Not a Replacement**
- Always review and test agent-generated code.  
- Validate correctness, security, and alignment with requirements.

### **Follow Secure Coding Practices**
- Avoid hard-coded secrets.  
- Prevent injection vulnerabilities.  
- Use scanning, linting, and testing before merging.

### **Provide Feedback**
- Use thumbs-down or community forums to report issues.

### **Stay Updated**
- The agent evolves; keep up with new risks and best practices.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/5-responsible-use-github-copilot-code-agent-github)

---

## 🟦 4. Security Measures
### **Avoiding Privilege Escalation**
- Only users with **write access** can interact with the agent.  
- Workflows triggered by agent PRs require **manual approval**.  
- Hidden characters are filtered to reduce prompt injection.  

### **Permission Constraints**
- Agent only accesses the **current repository**.  
- Pushes only to branches starting with `copilot/`.  
- No access to org/repo secrets or variables unless explicitly added to the agent environment.  

### **Preventing Data Exfiltration**
- A firewall is enabled by default to block outbound data.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/5-responsible-use-github-copilot-code-agent-github)

---

## 🟦 5. Limitations of the Coding Agent
- **Language & structure limitations:**  
  May struggle with obscure languages or complex codebases.
- **Biases:**  
  May favor certain languages or styles.
- **Security risks:**  
  Generated code may expose sensitive info if not reviewed.
- **Inaccurate code:**  
  Code may look correct but be semantically wrong.
- **Public code matches:**  
  May output near-matches even if “Block” is enabled.
- **Legal/regulatory:**  
  Must comply with organizational and legal requirements.  
  [learn.microsoft.com](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/5-responsible-use-github-copilot-code-agent-github)

---

# 📝 GH‑300 Exam Focus Areas
Expect exam questions on:

- How the agent processes prompts and iterates on PRs.  
- Responsible-use practices (scoping, validation, secure coding).  
- Security measures: permissions, branch restrictions, firewall, secrets.  
- Limitations: accuracy, bias, language coverage, public code behavior.  
- Developer responsibilities: review, testing, compliance.  
- How to provide feedback and improve agent performance.

---

                                                                                                                                                                                      
