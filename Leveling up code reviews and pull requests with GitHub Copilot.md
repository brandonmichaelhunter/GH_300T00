# Leveling up code reviews and pull requests with GitHub Copilot
- Explain how GitHub Copilot streamlines code reviews and pull requests.
- Identify the key features Copilot adds to the review process.
- Request and interpret Copilot reviews on GitHub.com and understand their limits.
- Run Copilot reviews locally in your IDE and apply custom instructions.
- Leverage Premium Request Units (PRUs) for deeper, context-rich analysis.
- Automate Copilot reviews across repositories with rulesets and status checks.
- Apply Copilot's suggestions responsibly, combining them with human judgment and testing.
----

## Module 1 – Introduction
- Traditional code reviews can be slow, inconsistent, and mentally taxing, especially across large PRs and multiple languages.
- GitHub Copilot acts as an AI reviewer and assistant: it spots issues, drafts comments, suggests refactors, and summarizes changes.
- Copilot complements—not replaces—human reviewers; you still rely on humans for architecture, trade-offs, and final approval.
- You can tune Copilot’s behavior with custom review instructions so it follows your team’s standards (security, style, readability, etc.).
- Premium Request Units (PRUs) power Copilot’s deeper review capabilities: whole-PR analysis, agent mode, and complex multi-step suggestions.
- Recommended prerequisites: GitHub account, Copilot-enabled plan (Pro/Pro+/Business/Enterprise for full review features), and basic PR/code review experience.
- Optional but helpful: an IDE like VS Code or JetBrains where you can run Copilot reviews locally before opening PRs.

**Quick quiz – Module 1 (multiple choice)**
1. What is the primary goal of using GitHub Copilot in code reviews?
	- A. To completely replace human reviewers
	- B. To automate merges without any human input
	- C. To act as a collaborative reviewer that speeds up and improves reviews
	- D. To enforce a single programming language for all projects

	**Answer:** C

2. How does Copilot help reduce review bottlenecks?
	- A. By limiting the size of pull requests
	- B. By automatically merging all changes
	- C. By catching common issues, drafting comments, and summarizing changes
	- D. By disabling comments from human reviewers

	**Answer:** C

3. What do Premium Request Units (PRUs) enable?
	- A. Access to GitHub Enterprise Server
	- B. Deeper, context-rich Copilot review features for large or complex tasks
	- C. Unlimited free usage of Copilot for all users
	- D. Automatic test generation for every repository

	**Answer:** B

4. Which of the following is a recommended prerequisite for this workflow?
	- A. A Copilot-enabled GitHub plan and basic familiarity with pull requests
	- B. A local GitHub Enterprise Server instance only
	- C. Knowledge of Kubernetes and Docker
	- D. Direct access to GitHub’s production infrastructure

	**Answer:** A

5. What is Copilot’s role relative to human reviewers?
	- A. It replaces them entirely
	- B. It overrides their decisions
	- C. It assists them by providing suggestions and context, while humans make final judgments
	- D. It only reviews documentation, not code

	**Answer:** C

## Module 2 – What GitHub Copilot adds to the review process
- Copilot provides PR summaries that describe changes and impacted files, giving reviewers immediate context.
- It can identify security issues (for example, unsafe APIs) and suggest safer patterns, often integrated with GitHub code scanning.
- Line-by-line explanations let reviewers or authors ask Copilot to explain specific code sections.
- Copilot can draft review comments based on best practices or repository-specific guidelines.
- In PRs, reviewers can highlight code and ask Copilot for improvements or refactors; the response can be pasted into review comments.
- Copilot reviews work across many languages, helping you review code outside your primary expertise using language-appropriate patterns.
- Copilot can detect and fix formatting issues in PR descriptions (such as tables), applying style rules from `.github/copilot-instructions.md`.
- From the PR UI, Copilot can generate or refine PR descriptions, making it easier to write clear, structured summaries.
- Copilot can run initial reviews on your own PRs, catching small issues before teammates look at them.

**Quick quiz – Module 2 (multiple choice)**
1. How do Copilot-generated PR summaries help reviewers?
	- A. They automatically approve the PR
	- B. They remove the need for any human comments
	- C. They provide a clear overview of changes and affected files, giving context quickly
	- D. They hide details of the diff

	**Answer:** C

2. Which is an example of Copilot helping with security during reviews?
	- A. Automatically deploying code to production
	- B. Suggesting a safer alternative when it detects an unsafe API usage
	- C. Disabling all security checks
	- D. Ignoring repository security guidelines

	**Answer:** B

3. How can reviewers use Copilot to improve specific lines of code in a PR?
	- A. They must download the repo and run a separate tool
	- B. They highlight code in the Files changed view and ask Copilot for a suggestion
	- C. They can only use Copilot from the command line
	- D. They must rewrite the code manually first

	**Answer:** B

4. What is a benefit of Copilot reviewing across multiple languages?
	- A. It enforces using only one language per organization
	- B. It lets reviewers give high-quality feedback even when the language isn’t their primary expertise
	- C. It blocks PRs written in unfamiliar languages
	- D. It ignores language-specific best practices

	**Answer:** B

5. How does Copilot help with PR descriptions and formatting?
	- A. It deletes any existing description
	- B. It generates structured summaries and can reformat content like tables according to repo guidelines
	- C. It only supports plain-text descriptions
	- D. It changes the target branch automatically

	**Answer:** B

## Module 3 – Using Copilot as a reviewer in GitHub.com
- On GitHub.com, you add Copilot as a reviewer from the PR Reviewers menu, just like a human teammate.
- Once assigned, Copilot analyzes the PR and posts a comment review, typically within seconds.
- Copilot’s comments appear inline on relevant lines and can include suggestions, refactors, or warnings.
- You can ask Copilot to draft fixes for review comments (for example, replacing unsafe code); you still test and commit the changes.
- PRUs power this analysis so Copilot can consider code context and review comments together when suggesting fixes.
- Copilot’s review is advisory only: it never counts as an approval, rejection, or required review.
- Human reviewers remain responsible for final decisions, high-level design, and trade-off discussions.
- You can tune Copilot’s review behavior on GitHub.com using `.github/copilot-instructions.md` so it follows your team’s priorities.

**Quick quiz – Module 3 (multiple choice)**
1. How do you request a Copilot review on GitHub.com?
	- A. By pushing a tag named `copilot-review`
	- B. By enabling it in your local IDE only
	- C. By adding Copilot from the PR Reviewers menu
	- D. By merging the PR first

	**Answer:** C

2. What is the nature of Copilot’s review on GitHub.com?
	- A. It can approve and merge PRs automatically
	- B. It posts comment reviews with suggestions but doesn’t approve or reject
	- C. It blocks all PRs until tests pass
	- D. It replaces required human approvals

	**Answer:** B

3. How can Copilot help apply fixes suggested in a review comment?
	- A. It directly edits production code without a PR
	- B. You prompt it to propose a patch, then you test and commit the change
	- C. It forces you to write the code manually
	- D. It only adds TODO comments

	**Answer:** B

4. Which statement best describes Copilot’s limits in PR reviews?
	- A. Copilot can override branch protection rules
	- B. Copilot’s comments count as the only required approval
	- C. Copilot is advisory; humans still own design decisions and final sign-off
	- D. Copilot can change repository settings

	**Answer:** C

5. How do custom Copilot instructions affect reviews on GitHub.com?
	- A. They are ignored by Copilot
	- B. They guide Copilot to follow your repository’s specific review rules and priorities
	- C. They disable Copilot for that repo
	- D. They only apply to CI pipelines

	**Answer:** B

## Module 4 – Catching issues early and automating reviews with Copilot
- You can run Copilot reviews locally in IDEs (VS Code, JetBrains) before committing or opening a PR.
- Local reviews can use `.github/copilot-instructions.md` to focus on concerns like security, style, or documentation.
- Copilot can flag issues such as duplication or unsafe patterns early, reducing noise and rework later in PR reviews.
- Path-specific instructions in `.github/instructions/*.instructions.md` let you target guidance to certain languages, folders, or file types via `applyTo` rules.
- PRUs allocated to IDE reviews enable deeper, context-aware analysis on large diffs, using your custom guidance.
- You can enable automatic Copilot reviews for your own PRs (Copilot Pro/Pro+), so every PR you open gets a review automatically.
- Repository admins can use branch rulesets to require a Copilot review on protected branches.
- Organization owners can define rulesets that apply Copilot reviews across many repositories for consistent standards.
- Combining Copilot reviews with tests and code scanning in rulesets creates an automated quality gate (style, security, and correctness).

**Quick quiz – Module 4 (multiple choice)**
1. Why run Copilot reviews locally in your IDE before opening a PR?
	- A. To bypass review policies on GitHub
	- B. To catch style, security, and best-practice issues earlier and reduce PR churn
	- C. To avoid writing tests
	- D. To disable Copilot on GitHub.com

	**Answer:** B

2. What is the purpose of `.github/instructions/*.instructions.md` files with `applyTo` rules?
	- A. To define build scripts
	- B. To target custom Copilot guidance to specific paths or file types
	- C. To store environment variables
	- D. To configure branch protection

	**Answer:** B

3. How do PRUs enhance Copilot reviews in your IDE?
	- A. They disable local reviews
	- B. They allow deeper analysis of larger diffs with your custom instructions applied
	- C. They only count when running tests
	- D. They force reviews to be slower

	**Answer:** B

4. How can you ensure all PRs to a protected branch get a Copilot review?
	- A. Require contributors to @mention Copilot manually
	- B. Enable a branch ruleset that requests Copilot reviews for PRs
	- C. Disable branch protection
	- D. Use only local reviews

	**Answer:** B

5. What is a benefit of automating Copilot reviews with rulesets and status checks?
	- A. Reviews happen inconsistently based on reviewer availability
	- B. Only large PRs are ever reviewed
	- C. Even small or routine changes receive consistent automated checks for style, security, and tests
	- D. Human reviews are no longer needed

	**Answer:** C

## Module 5 – Measuring impact and optimizing Premium Request Units (PRUs)
- PRUs are premium units that fund Copilot’s most advanced review capabilities (full-PR analysis, deep IDE reviews, agentic workflows).
- Lightweight suggestions (for example, small refactors on a single line) may not use PRUs; large, complex requests typically do.
- With PRUs, Copilot can scan large diffs, apply your `.github/copilot-instructions.md` rules, and surface detailed, repo-specific suggestions.
- PRUs are critical for teams that need scalable, high-quality automated reviews across many services and languages.
- They help enforce consistent security, style, and readability checks across all PRs, even during busy release cycles.
- To measure impact, track metrics such as PR lead time, post-merge issue rates, and developer feedback on review quality.
- Teams can optimize PRU usage by reserving PRU-heavy reviews for high-risk or large changes and using standard suggestions for trivial edits.
- Good practices include setting usage alerts (for example, at 75%, 90%, 100%) and adjusting plans if your team consistently hits limits.
- Refining prompts and workflows (for example, avoiding repeated, vague requests) helps prevent unnecessary PRU consumption.

**Quick quiz – Module 5 (multiple choice)**
1. What do Premium Request Units (PRUs) enable for Copilot?
	- A. Access to GitHub billing data
	- B. Advanced, context-rich review capabilities for large or complex tasks
	- C. Automatic promotion of users to org owners
	- D. Free hardware upgrades

	**Answer:** B

2. Which scenario is most likely to consume PRUs?
	- A. Suggesting a variable rename in a single line
	- B. Asking Copilot to review a large multi-file refactor using your custom instructions
	- C. Viewing repository settings
	- D. Opening an issue with no description

	**Answer:** B

3. Which metric best indicates the impact of PRU-powered reviews?
	- A. Number of open GitHub issues overall
	- B. PR lead time before and after enabling PRU-based reviews
	- C. Total size of the repository in MB
	- D. Number of branches in the repo

	**Answer:** B

4. How can teams avoid wasting PRUs?
	- A. Use PRU-powered reviews only for trivial documentation changes
	- B. Disable Copilot entirely
	- C. Reserve premium reviews for high-risk or large changes and keep prompts focused
	- D. Run duplicate reviews on the same PR repeatedly without changes

	**Answer:** C

5. Why do PRUs matter especially for larger organizations?
	- A. They limit the number of repositories allowed
	- B. They make it possible to scale consistent, deep reviews across many services and languages
	- C. They replace the need for any security tooling
	- D. They are only used for billing reports

	**Answer:** B

## Exam cram – Copilot code reviews module summary
- Copilot’s role: an AI reviewer and assistant that speeds up code reviews, surfaces issues, and drafts suggestions, while humans keep ownership of architecture and final sign-off.
- Key features in reviews: PR summaries, security and best-practice checks, line-by-line explanations, drafted comments, multi-language support, formatting fixes, and self-reviews for your own PRs.
- PRUs: premium units that power advanced, context-rich analysis for whole-PR reviews, deep IDE reviews, and agentic workflows; reserve them for large or high-impact changes.
- GitHub.com workflow: add Copilot as a reviewer from the PR Reviewers menu; it posts comment reviews (not approvals), suggests fixes, and follows custom instructions from `.github/copilot-instructions.md`.
- IDE workflow: run Copilot reviews locally in VS Code/JetBrains to catch issues early; use PRUs for deeper analysis of large diffs before you even open a PR.
- Custom instructions: use `.github/copilot-instructions.md` for repo-level guidance and `.github/instructions/*.instructions.md` with `applyTo` patterns for path-specific rules (for example, only TypeScript or Ruby models).
- Automation at scale: use rulesets and branch protection to require Copilot reviews on protected branches or across organizations, pairing them with tests and code scanning for comprehensive quality gates.
- Measuring impact: watch PR lead time, post-merge issue rates, and developer satisfaction; adjust when and where you use PRU-powered reviews to maximize value.
- Best practices: keep Copilot’s role advisory, review and test its suggestions, craft clear prompts, and continuously refine custom instructions so Copilot aligns with your team’s standards.
