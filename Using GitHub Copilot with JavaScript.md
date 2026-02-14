# Using GitHub Copilot with JavaScript
- Enable the GitHub Copilot extension in Visual Studio Code.
- Craft prompts that can generate useful suggestions from GitHub Copilot.
- Use GitHub Copilot to improve a JavaScript project.
----

## Module 1 – Introduction
- GitHub Copilot is an AI coding partner that provides code suggestions and completions as you type or describe behavior in natural language.
- It analyzes your current file and related open files to generate context-aware suggestions for JavaScript and other languages.
- GitHub Codespaces provides a cloud-hosted development environment (including VS Code, extensions, and dependencies) that you can use from the browser.
- Scenario focus: improving an existing JavaScript portfolio app by customizing scroll behavior and adding enhancements via Copilot.
- By the end of the module, you should be able to configure a repo in Codespaces, install/enable Copilot, and apply it to improve a JS project using prompts.
- Prerequisites: basic JavaScript, familiarity with text editors, basic Git/GitHub (clone, commit, push), and a GitHub account with Copilot access (Free tier is enough for learning).

**Quick quiz – Module 1 (multiple choice)**
1. What is the main objective of this JavaScript Copilot module?
	- A. Deploying Kubernetes clusters with Helm
	- B. Using prompts to customize a JavaScript project with GitHub Copilot in Codespaces
	- C. Learning only about Git commands
	- D. Building a C# backend API

	**Answer:** B

2. What does GitHub Copilot primarily provide while you work in your editor?
	- A. Network monitoring tools
	- B. Code suggestions and completions based on your context and prompts
	- C. Database hosting
	- D. Source control hosting

	**Answer:** B

3. Which statement about GitHub Codespaces is correct?
	- A. It is a local-only feature that runs only on your laptop
	- B. It is a cloud-hosted dev environment that you can open in the browser or VS Code
	- C. It replaces GitHub entirely
	- D. It only supports Python projects

	**Answer:** B

4. Which prerequisite is required for this module?
	- A. Deep knowledge of Docker internals
	- B. A GitHub account with Copilot enabled (Free or paid) and basic JS/Git familiarity
	- C. A private data center
	- D. Experience with machine learning frameworks

	**Answer:** B

5. How does Copilot get context for its suggestions?
	- A. Only from your terminal commands
	- B. From your currently open file and related open files in the editor
	- C. From your email inbox
	- D. From unrelated public repositories only

	**Answer:** B

## Module 2 – What is GitHub Copilot
- Copilot is an AI assistant integrated into your IDE that can generate code, documentation, and more from natural language prompts and existing code.
- A “prompt” can be a comment in code (for example, a JavaScript comment describing a function) or freeform text (for example, in Markdown or chat).
- Given a prompt like “Create a web API using JavaScript and Express,” Copilot proposes starter code that you can accept, reject, or edit.
- Copilot recognizes prompts when you:
  - Type comments in supported code files (such as .js).
  - Type instructions in markdown or chat and pause to let Copilot respond.
- Suggestions typically appear as ghost text; you accept them with Tab or cycle through alternatives with Ctrl+Enter (Cmd+Enter on Mac).
- You always stay in control: treat Copilot’s output as suggestions to review and refine, not as unquestioned final code.

**Quick quiz – Module 2 (multiple choice)**
1. Which of the following can serve as a Copilot prompt in JavaScript files?
	- A. A comment describing the desired function or behavior
	- B. Only terminal commands
	- C. Only Git commit messages
	- D. Only configuration files

	**Answer:** A

2. How do Copilot’s suggestions typically appear in the editor?
	- A. As comments in your GitHub issues
	- B. As grey/ghost text inline with your code
	- C. As standalone pop-up windows only
	- D. As email notifications

	**Answer:** B

3. How do you accept a Copilot suggestion in most editors like VS Code?
	- A. Press Tab
	- B. Run `git commit`
	- C. Click “Merge” on a pull request
	- D. Press Esc

	**Answer:** A

4. How can you see alternative suggestions for the same prompt?
	- A. You can’t; Copilot only provides one
	- B. By reloading the entire workspace
	- C. By using Ctrl+Enter (Cmd+Enter on Mac) to cycle suggestions
	- D. By deleting your current file

	**Answer:** C

5. What is your responsibility when using Copilot-generated code?
	- A. To accept all suggestions automatically
	- B. To review, test, and adapt suggestions as needed
	- C. To avoid changing them to keep AI happy
	- D. To disable tests

	**Answer:** B

## Module 3 – Exercise: Set up GitHub Copilot with Visual Studio Code
- Setup steps:
  - Create or use a GitHub account.
  - Enable GitHub Copilot (Free tier or Pro subscription; watch free trial billing rules if using Pro trial).
  - Install the GitHub Copilot extension in VS Code (optionally also GitHub Copilot Chat, Copilot for Azure, etc.).
  - Sign in to Copilot from VS Code and authorize with your GitHub account.
- For this module, you use a preconfigured JavaScript portfolio template via GitHub Codespaces.
- Codespaces spins up a containerized environment with dependencies, extensions, and `npm` tooling pre-installed.
- The template app uses `npm start` to run a React-based portfolio app (for example on port 1234 in the Codespace).
- All GitHub accounts get a monthly free allowance of Codespaces hours (with limits on cores and storage), which is sufficient for this learning module.

**Quick quiz – Module 3 (multiple choice)**
1. Which steps are required to start using Copilot in VS Code?
	- A. Install VS Code, create a GitHub account, enable Copilot, and install/sign in to the Copilot extension
	- B. Only install Git on your machine
	- C. Only create a Codespace without enabling Copilot
	- D. Set up a local Kubernetes cluster first

	**Answer:** A

2. What is a key benefit of using a Codespaces-based JavaScript template in this module?
	- A. It requires manual dependency installation
	- B. It provides a preconfigured environment with dependencies and Copilot ready to use
	- C. It can only be used offline
	- D. It doesn’t support npm

	**Answer:** B

3. What command does the portfolio template use to start the web app inside Codespaces?
	- A. `dotnet run`
	- B. `npm start`
	- C. `python app.py`
	- D. `docker run`

	**Answer:** B

4. Why should you pay attention to the Copilot Pro trial terms if you start a trial?
	- A. Because it changes your Git history
	- B. Because charges begin after the 30-day trial unless you cancel
	- C. Because it disables Codespaces access
	- D. Because it removes Free tier limits

	**Answer:** B

5. How does Codespaces help for this learning scenario?
	- A. It replaces GitHub entirely
	- B. It gives you a ready-to-use, cloud-hosted dev container so you can focus on JavaScript and Copilot
	- C. It only hosts databases
	- D. It forces you to use a specific operating system locally

	**Answer:** B

## Module 4 – Use GitHub Copilot with JavaScript
- Copilot can help with both new features and updates in existing JS projects (such as a portfolio site).
- Prompt engineering basics:
  - Prompts are instructions (often comments) that describe what you want Copilot to generate.
  - Vague prompts (for example, “Create an API endpoint”) produce less predictable results.
  - Specific prompts (for example, “Create an API endpoint using Express that accepts a JSON POST body”) guide Copilot toward better outputs.
- Best practices when prompting:
  - Start simple, then refine: begin with a high-level prompt, then add detail in follow-up comments or prompts.
  - Incrementally refine prompts if the output is off (clarify frameworks, data formats, or constraints).
  - Cycle between multiple suggestions (Ctrl+Enter/Cmd+Enter) and pick or edit the best one.
  - Combine inline suggestions with GitHub Copilot Chat (`@workspace`, file references) for more complex tasks.
- Copilot uses open files in your editor as extra context, so open relevant JS/HTML/CSS files to help it produce better suggestions.
- If stuck, start by writing partial code or function signatures and let Copilot autocomplete.

**Quick quiz – Module 4 (multiple choice)**
1. Why might the prompt `// Create an API endpoint` produce poor results?
	- A. It is too specific
	- B. It is too vague and doesn’t specify framework or behavior
	- C. Copilot doesn’t understand comments
	- D. JavaScript isn’t supported

	**Answer:** B

2. Which is a better prompt for generating a specific API in JavaScript?
	- A. `// Do something`
	- B. `// Create an API endpoint using Express that accepts a JSON payload in a POST request`
	- C. `// Code`
	- D. `// Fix everything`

	**Answer:** B

3. What should you do if Copilot’s first suggestion isn’t what you want?
	- A. Give up using Copilot
	- B. Accept it anyway
	- C. Cycle through more suggestions or refine the prompt
	- D. Delete the file

	**Answer:** C

4. How does opening additional files in your editor affect Copilot’s behavior?
	- A. It has no effect
	- B. Copilot can use them as extra context to improve suggestions
	- C. It disables Copilot
	- D. It slows down your computer with no benefit

	**Answer:** B

5. What’s a good pattern for working with Copilot on a new JS feature?
	- A. Write nothing and expect Copilot to do everything in one step
	- B. Iteratively refine prompts, review suggestions, and provide partial code for Copilot to autocomplete
	- C. Accept the first suggestion every time
	- D. Turn off tests

	**Answer:** B

## Module 5 – Exercise: Update a JavaScript portfolio with GitHub Copilot
- You work with a React-based JavaScript portfolio template in a Codespace.
- Customization starts by editing `src/App.jsx` and updating the `siteProps` object (name, title, links) to personalize the site.
- Copilot can help with UX enhancements like adding animations, scroll behavior tweaks, or new sections.
- Example exercise: add a hover animation to social media icons by writing a descriptive CSS comment prompt in `src/styles.css` (for example, “add an animation to the social icons”).
- Copilot then suggests a `@keyframes` block and hover styles; you can accept, test visually, and refine as needed.
- Live reload in Codespaces lets you instantly see visual changes in the running app.
- This exercise demonstrates using Copilot for real-world JS tasks: UI polish, small behavioral tweaks, and rapid iteration.

**Quick quiz – Module 5 (multiple choice)**
1. Where do you personalize the portfolio’s basic info (name, links) in the template?
	- A. In `.github/workflows`
	- B. In `src/App.jsx` inside the `siteProps` object
	- C. In the Dockerfile
	- D. In `package-lock.json`

	**Answer:** B

2. How do you ask Copilot to create an animation for social icons in the CSS file?
	- A. By editing the GitHub Settings page
	- B. By writing a descriptive CSS comment (prompt) in `src/styles.css`
	- C. By creating an issue only
	- D. By running a shell script

	**Answer:** B

3. What benefit does live reload in Codespaces provide for this exercise?
	- A. It disables debugging
	- B. It immediately shows UI changes as you accept Copilot’s suggestions
	- C. It forces you to restart the server manually each time
	- D. It hides errors

	**Answer:** B

4. What kind of work is this portfolio exercise designed to simulate?
	- A. Low-level kernel programming
	- B. Real-world front-end JavaScript updates and enhancements
	- C. Database schema design only
	- D. Network router configuration

	**Answer:** B

5. Besides code generation, what else can you use Copilot for in this scenario?
	- A. Only writing commit messages
	- B. Writing documentation, assisting with tests, and suggesting UI/UX improvements
	- C. Managing billing
	- D. Hosting production traffic

	**Answer:** B

## Exam cram – Using GitHub Copilot with JavaScript
- Copilot basics: an AI coding partner inside your IDE that uses prompts and existing code to generate suggestions—always review and test its output.
- Prompts: comments or text that describe the desired behavior; specificity (framework, data format, constraints) leads to better JavaScript suggestions.
- VS Code + Codespaces setup: enable Copilot on your GitHub account, install/sign in to the Copilot extension, and use a preconfigured Codespace template to quickly start JS projects.
- Working style: iterate—write a prompt or partial code, review Copilot’s suggestion, cycle alternatives, refine the prompt, and repeat.
- Context: Copilot uses open files in the editor as additional context; open relevant JS, CSS, and config files to guide better completions.
- Best practices: start with small tasks, keep prompts clear, avoid copying suggestions blindly, and use tests/linters to validate generated code.
- JavaScript portfolio pattern: personalize configuration objects (like `siteProps`), then use Copilot to add behaviors (scroll tweaks, animations, new sections) via targeted prompts.
- IDE + chat: combine inline completions with GitHub Copilot Chat (`@workspace`, file references) for more complex refactors or multi-file changes.
- Exam mindset: know how to set up Copilot, how prompts affect quality, how to use Codespaces for a JS portfolio, and how to safely integrate Copilot into everyday JavaScript development.

