# Introduction to MCP Server
- Understand what MCP and GitHub MCP Server are and why they're useful for developers.
- Set up and configure GitHub MCP Server in Visual Studio Code for your projects.
- Use the GitHub MCP Server with Copilot Chat to automate development tasks.
- Identify and resolve common issues when working with GitHub MCP Server.
----

## Module 1 – Introduction
- GitHub MCP Server is a hosted, secure, scalable implementation of the Model Context Protocol (MCP) that connects AI tools (like GitHub Copilot) to GitHub resources.
- MCP is a standard protocol that lets AI models talk to tools and data sources in a consistent, structured way.
- GitHub MCP Server extends Copilot with tools to automate tasks such as managing repositories, issues, and pull requests using context-aware AI.
- The server is currently available in Visual Studio Code and is designed to expand to other editors and platforms over time.
- Using a hosted server removes the need to run and manage your own MCP server infrastructure.
- Typical prerequisites: GitHub account, an editor that supports MCP (for now VS Code), and appropriate Copilot plan and policy settings in your organization.
- Optional prerequisites: a GitHub Personal Access Token (PAT) for finer-grained control over permissions, and Docker if you want to experiment with running a server locally.

**Quick quiz – Module 1 (multiple choice)**
1. What main problem does the Model Context Protocol (MCP) solve?
	- A. It replaces all existing GitHub APIs
	- B. It provides a standard way for AI models to connect to tools and data sources
	- C. It is a new programming language for AI agents
	- D. It is only used for deploying Docker containers

	**Answer:** B

2. What does GitHub MCP Server add on top of MCP?
	- A. A generic AI model that runs locally on your machine
	- B. A hosted server that exposes GitHub-specific tools to AI clients
	- C. A replacement for GitHub Enterprise Server
	- D. A browser-only interface that doesn’t support IDEs

	**Answer:** B

3. Why is a hosted GitHub MCP Server often easier to start with than running your own server?
	- A. It requires custom hardware and on-premises networking
	- B. It can only be used from the command line
	- C. It removes the need to manage server infrastructure and configuration yourself
	- D. It doesn’t require any authentication at all

	**Answer:** C

4. Which of the following are required prerequisites for using GitHub MCP Server in VS Code?
	- A. GitHub account and an editor that supports MCP
	- B. Docker and a PAT are always required
	- C. Only a PAT with admin:org scope
	- D. A self-hosted GitHub Enterprise Server instance

	**Answer:** A

5. Which items are typically optional when first experimenting with GitHub MCP Server?
	- A. GitHub account and VS Code
	- B. Copilot plan and policy configuration
	- C. PAT and Docker for advanced or local setups
	- D. Internet connectivity

	**Answer:** C

## Module 2 – Simplify your AI workflow with GitHub MCP Server
- MCP acts like a common connector standard for AI tools, allowing them to use a shared way to reach tools and data, regardless of the underlying AI provider.
- MCP gives access to a growing ecosystem of tools that models can call immediately instead of writing custom integrations for every scenario.
- It helps you keep workflows consistent even if you switch AI models or providers, because the integrations live in the MCP layer.
- MCP clients (for example, IDEs or chat UIs) can connect to MCP servers in three common patterns:
	- Local client to local server with local data: best for private, on-device resources and fast access.
	- Local client to local server that bridges to remote services: good when you want a local control point that calls remote APIs (caching, security checks, preprocessing).
	- Local client to remote server over the internet: ideal when compute or data lives entirely in the cloud or SaaS services.
- GitHub MCP Server removes much of the friction of traditional MCP setups (no Docker or complex config required for hosted use).
- Authentication is handled via simple OAuth sign-in, so you avoid manual token wiring for common scenarios.
- Because it is hosted by GitHub, the same MCP tools are available across environments (web, desktop, mobile) instead of being tied to one machine.
- GitHub MCP Server integrates with enterprise identity (for example, Entra ID or Auth0) to respect organizational sign-in and security controls.
- The server scales automatically with usage, so you do not need to plan capacity for different teams or projects.
- The toolset includes capabilities such as semantic code search, automated fixes, repository triage, branch and file operations, and prioritization of issues and pull requests.

**Quick quiz – Module 2 (multiple choice)**
1. Which option best describes the three common MCP connection patterns?
	- A. Local-only, hybrid cloud, and offline-only
	- B. Local client to local server with local data; local server bridging to remote services; client to remote server over the internet
	- C. Browser-only, mobile-only, and desktop-only
	- D. Public, private, and protected networks

	**Answer:** B

2. How does MCP help keep workflows consistent when you switch AI providers?
	- A. MCP stores your entire codebase in the cloud
	- B. MCP dynamically rewrites your prompts
	- C. Tool integrations live behind a common protocol layer that different models can use
	- D. MCP forces all providers to use the same model architecture

	**Answer:** C

3. Why does using the hosted GitHub MCP Server often mean you don’t need Docker or complex config files?
	- A. Because the hosted server runs only on your local machine
	- B. Because GitHub pre-hosts and manages the MCP server infrastructure for you
	- C. Because Docker is no longer supported in modern development
	- D. Because MCP doesn’t require any configuration

	**Answer:** B

4. Which activities are typical candidates for automation with GitHub MCP Server tools?
	- A. Repository triage, semantic code search, branch and file operations, and issue/pr management
	- B. Managing your operating system updates
	- C. Configuring your network hardware
	- D. Running database migrations on non-GitHub systems only

	**Answer:** A

5. When is it most appropriate to use the “local client to local server with local data” MCP pattern?
	- A. When all data must stay on your machine and you want fast, private access
	- B. When you must avoid using any local resources
	- C. When your client and server must always be on different networks
	- D. When you only use SaaS tools

	**Answer:** A

## Module 3 – Configure, connect, and use GitHub MCP Server in VS Code
- You add GitHub MCP Server to VS Code by using the Command Palette and the MCP: Add server command.
- For the hosted server, you configure an HTTP / Server-Sent Events endpoint pointing at the GitHub MCP Server URL (https://api.githubcopilot.com/mcp/).
- When prompted for a server ID, you can keep the default or choose a custom name to distinguish this server from others.
- The configuration can be stored at the user level (available to all projects) or workspace level (scoped to the current repo).
- OAuth setup flow:
	- Trigger MCP server creation in VS Code.
	- Choose the HTTP option and supply the hosted MCP endpoint URL.
	- Accept the OAuth prompt and sign in with your GitHub account.
	- After authorization, the MCP server becomes available in VS Code.
- PAT-based setup is used when you need explicit token-based authorization instead of OAuth.
- For PAT-based setup you:
	- Create a PAT with appropriate scopes (for example, `repo` and `read:packages`).
	- Add an `Authorization: Bearer ${input:github_token}` header section in the MCP configuration.
	- Define a secure input prompt (`promptString` with `password: true`) to collect the token at runtime.
	- Restart the MCP server and provide the PAT when requested.
- Optional local Docker setup is used if you must run the server locally (for example, with GitHub Enterprise Server or strict PAT policies).
- In the Docker scenario you:
	- Ensure Docker is installed and running.
	- Generate a PAT with the required scopes.
	- Configure the MCP server to run the `ghcr.io/github/github-mcp-server` container with the PAT supplied through an environment variable.
	- Restart the MCP server and enter the PAT when prompted.
- Troubleshooting basics:
	- Confirm you are signed into GitHub in VS Code.
	- Verify PAT scopes and that the token value is correct if you use PAT auth.
	- Check for typos or missing fields in the MCP configuration file.
	- Make sure Docker is installed and running for local container-based setups.
	- Restart VS Code or the MCP server if you suspect a transient connection issue.

**Quick quiz – Module 3 (multiple choice)**
1. When is OAuth typically the best choice for connecting VS Code to GitHub MCP Server?
	- A. When you never want to log in through a browser
	- B. When you want a quick, user-friendly sign-in that doesn’t require handling tokens manually
	- C. When you must hard-code tokens in config files
	- D. When you are fully offline

	**Answer:** B

2. Which key pieces of information do you configure when adding the hosted GitHub MCP Server in VS Code?
	- A. The MCP URL, server ID, and where to store the configuration (user or workspace)
	- B. Your local Docker image name only
	- C. Only your GitHub username
	- D. A custom operating system path

	**Answer:** A

3. How does the PAT-based configuration help keep tokens secure while still allowing MCP to use them?
	- A. PATs are stored in plain text in your repository
	- B. Tokens are passed as command-line arguments that are committed to Git
	- C. The config uses a prompt-based input so you enter the PAT at runtime, and it’s referenced via variables instead of being hard-coded
	- D. PATs are emailed to the MCP server on startup

	**Answer:** C

4. When might you choose the local Docker-based MCP server option?
	- A. When your organization requires local control (for example, GitHub Enterprise Server) or has strict PAT policies
	- B. When you have no need to control where the server runs
	- C. When you cannot install Docker at all
	- D. When you only work in GitHub.com in the browser

	**Answer:** A

5. Which of the following are good first troubleshooting steps if the MCP server isn’t working?
	- A. Confirm GitHub sign-in, validate PAT scopes and values, and check for typos or missing fields in the configuration
	- B. Reinstall your operating system
	- C. Delete the entire VS Code settings folder
	- D. Disable all network connections

	**Answer:** A

## Module 4 – Using GitHub MCP Server with Copilot Chat
- Once the server is configured, you can use it from Copilot Chat in VS Code by switching to Agent mode.
- In Agent mode, you select which MCP tools are available to Copilot, such as tools for repository analysis, issue management, or code changes.
- You can drive workflows with natural language prompts (for example, ask Copilot to summarize a repo, open an issue, or prioritize pull requests) and the agent will call MCP tools as needed.
- Agentic capabilities allow Copilot to execute multi-step workflows, make decisions about which tools to call, and iterate toward a result instead of only answering one prompt at a time.
- Combining MCP with agent mode lets Copilot reach external data, APIs, and enterprise systems that are exposed through MCP servers.
- MCP-aware agents can keep context across multiple tools and platforms, reducing the need for you to manually switch applications or copy data between them.
- Agent mode can perform “agentic loops”: gather information, analyze it, take an action via tools, then re-evaluate and continue until goals are met.
- Benefits of combining MCP and agent mode include extended context, automation of repetitive tasks (for example, issue creation or triage), and smoother cross-tool workflows.
- Best practices when using MCP with Copilot agent mode:
	- Be explicit about goals and what a “done” outcome looks like.
	- Provide relevant context (links, prior steps, constraints) up front.
	- Set boundaries, such as limiting which tools the agent can use or asking it to only plan rather than apply changes.
	- Ask the agent to present a plan and confirm it before it performs large or risky operations.
	- Use prompt files or instructions to define reusable guidance for how Copilot should behave with particular MCP servers.

**Quick quiz – Module 4 (multiple choice)**
1. How does Copilot in Agent mode differ from standard Copilot usage?
	- A. It only answers single prompts with no follow-up
	- B. It cannot call any tools
	- C. It can run multi-step workflows, choose tools, and iterate toward a goal
	- D. It only works outside of VS Code

	**Answer:** C

2. How does MCP extend what Copilot can do during an agentic workflow?
	- A. By limiting Copilot to local files only
	- B. By exposing external data, APIs, and enterprise tools through MCP servers
	- C. By blocking access to GitHub entirely
	- D. By turning off all automation

	**Answer:** B

3. Why might you limit which tools are enabled for an agent session?
	- A. To force Copilot to ignore context
	- B. To prevent Copilot from accessing any data at all
	- C. To keep the agent focused, reduce risk, and avoid unintended changes
	- D. To make configuration more difficult

	**Answer:** C

4. What should you provide Copilot to help it succeed with multi-step MCP-based tasks?
	- A. Only a vague, one-word prompt
	- B. Clear goals, relevant context, and any constraints up front
	- C. A list of unrelated repositories
	- D. Only the name of the MCP server

	**Answer:** B

5. How do prompt files or instructions help when using MCP servers with Copilot?
	- A. They are only used to store access tokens
	- B. They automatically upgrade your Copilot license
	- C. They define reusable guidance so Copilot behaves consistently across sessions and projects
	- D. They disable Agent mode

	**Answer:** C

## Exam cram – MCP Server module summary
- MCP (Model Context Protocol) is a standard way for AI models to talk to tools and data sources, decoupling integrations from any one provider or model.
- GitHub MCP Server is a hosted, GitHub-managed MCP server that exposes GitHub-aware tools (issues, PRs, semantic search, repository triage, branch/file operations) to AI clients like Copilot.
- Key value: it removes local setup friction (no Docker or complex config for hosted use), scales automatically, and works across environments (VS Code, web, mobile) while respecting enterprise identity.
- Three common MCP connection patterns:
  - Local client ↔ local server ↔ local data: best for private on-device data and speed.
  - Local client ↔ local server ↔ remote services: when you want a local “bridge” that calls remote APIs and can add caching, security, or preprocessing.
  - Client ↔ remote server over internet ↔ remote services: when compute/data is in the cloud or SaaS only.
- Core hosted setup steps in VS Code: use `MCP: Add server`, select HTTP/SSE, provide the hosted MCP URL, choose a server ID, pick user or workspace scope, then complete OAuth sign-in.
- Use OAuth for quick, user-friendly sign-in; use a PAT (with scopes like `repo` and `read:packages`) when you need explicit token-based control, custom scopes, or when OAuth isn’t available.
- PAT-based configs typically:
  - Add an `Authorization: Bearer ${input:github_token}` header.
  - Define a secure `promptString` input so the PAT is entered at runtime and not stored in source control.
- Optional local Docker setup runs `ghcr.io/github/github-mcp-server` with a PAT in an environment variable; useful for GitHub Enterprise Server, restricted PAT policies, or when you must control where the server runs.
- Basic troubleshooting checklist: confirm GitHub sign-in, validate PAT scopes/values, re-check MCP config for typos, ensure Docker (if used) is running, and restart VS Code or the MCP server.
- Copilot Agent mode + MCP: Agent mode lets Copilot plan and execute multi-step workflows, while MCP gives it access to external tools and data so it can complete “agentic loops” (gather → analyze → act → refine).
- Good agent-mode practices: clearly state goals and desired outputs, provide relevant context (links, repos, constraints), limit enabled tools where appropriate, ask for a plan before large changes, and use prompt files to encode reusable instructions.

