# Using GitHub Copilot with Python
- Enable the GitHub Copilot extension in Visual Studio Code.
- Craft prompts that can generate useful suggestions from GitHub Copilot.
- Use GitHub Copilot to improve a Python project.
----

## Module 1 – Introduction
- GitHub Copilot is an AI coding partner that provides autocomplete-style suggestions as you write or describe Python code in natural language.
- It analyzes your current Python file and related files to propose context-aware code (functions, classes, tests, docs).
- GitHub Codespaces is a cloud-hosted development environment that runs VS Code (or a browser-based editor) with extensions and dependencies preinstalled.
- Scenario: use Copilot to customize a Python web API via prompts (for example, adding endpoints) and live suggestions, improving an existing project.
- By the end of the module, you should be able to configure a repo in Codespaces, install/enable Copilot, and use prompts to enhance a Python project.
- Prerequisites: basic Python and editor knowledge, basic Git/GitHub usage, and a GitHub account with Copilot access (Copilot Free tier is sufficient for learning).

**Quick quiz – Module 1 (multiple choice)**
1. What is the main objective of this Python Copilot module?
	- A. Deploying machine-learning models to production
	- B. Using prompts to customize a Python project with GitHub Copilot in Codespaces
	- C. Learning Docker internals
	- D. Migrating databases

	**Answer:** B

2. How does Copilot typically help you in a Python project?
	- A. By hosting your application on GitHub
	- B. By generating context-aware code suggestions and completions as you type
	- C. By replacing your version control system
	- D. By configuring your operating system

	**Answer:** B

3. Which statement about GitHub Codespaces is correct?
	- A. It’s a local-only Python virtual environment
	- B. It’s a cloud-hosted dev environment you can open in the browser or VS Code
	- C. It’s only for JavaScript projects
	- D. It cannot run web apps

	**Answer:** B

4. Which prerequisites are recommended before taking this module?
	- A. Advanced Kubernetes administration
	- B. Basic Python, basic Git/GitHub, and a GitHub account with Copilot enabled
	- C. A private on-premises data center
	- D. Knowledge of three other programming languages

	**Answer:** B

5. What does the scenario in this module focus on?
	- A. Building a GUI desktop app
	- B. Customizing a Python API using prompts and Copilot suggestions
	- C. Writing SQL migrations only
	- D. Managing GitHub billing settings

	**Answer:** B

## Module 2 – What is GitHub Copilot?
- Copilot is an AI assistant integrated into your IDE that can generate Python code (and more) based on natural language prompts and existing code.
- A prompt is natural language text (often a comment) that describes the behavior you want; for example: `# Create a web API using FastAPI with a route to products.`
- Copilot uses the prompt plus surrounding context to propose Python code that you can accept, edit, or reject.
- Copilot recognizes prompts when:
  - You type a comment in a code file (.py, .js, etc.).
  - You type text in a markdown file and pause, or in Copilot Chat.
- Suggestions appear as ghost/gray text in the editor; you accept them with Tab.
- You can cycle through multiple suggestions with `Ctrl+Enter` (or `Cmd+Enter` on Mac) and choose the best fit.
- You remain responsible for reviewing, testing, and adapting generated code.

**Quick quiz – Module 2 (multiple choice)**
1. Which of the following is a valid Copilot prompt in a Python file?
	- A. A Python comment describing the desired FastAPI endpoint
	- B. A shell command in the terminal
	- C. A Git tag name
	- D. The repository description on GitHub

	**Answer:** A

2. How does Copilot typically present its suggestions in the editor?
	- A. As issues in your GitHub repo
	- B. As ghost/gray inline text in your code editor
	- C. Only in browser pop-ups
	- D. As email alerts

	**Answer:** B

3. How do you accept a suggestion from Copilot in most IDEs like VS Code?
	- A. Press Tab
	- B. Run `git push`
	- C. Press Esc
	- D. Restart the IDE

	**Answer:** A

4. How can you see alternative suggestions for a given prompt?
	- A. You can’t; Copilot only shows one option
	- B. By reopening the project
	- C. By using `Ctrl+Enter` (or `Cmd+Enter` on Mac) to cycle suggestions
	- D. By deleting the current file

	**Answer:** C

5. What is your responsibility when working with Copilot-generated Python code?
	- A. Accept everything automatically
	- B. Review, test, and adjust suggestions to meet your project’s needs
	- C. Avoid running any tests
	- D. Never modify generated code

	**Answer:** B

## Module 3 – Exercise: Set up GitHub Copilot to work with Visual Studio Code
- Setup steps:
  - Create a GitHub account if you don’t already have one.
  - Enable GitHub Copilot (Free tier or Pro; note free-trial billing rules for Pro).
  - Install the GitHub Copilot extension in VS Code (optionally Copilot Chat and Copilot for Azure).
  - Sign in to Copilot from VS Code and authorize the extension with your GitHub account.
- This module uses a preconfigured Python web API template via GitHub Codespaces.
- Launch the Codespace from the provided template link; Codespaces starts a dev container with Copilot and dependencies already installed.
- After setup, Codespaces runs a FastAPI-based app using `uvicorn`, exposing the API on port 8000 inside the Codespace.
- You can test the API via the built-in Simple Browser and FastAPI docs (`/docs`) UI to send sample requests.
- All GitHub accounts receive a free monthly allowance of Codespaces hours (two-core instances) suitable for learning.

**Quick quiz – Module 3 (multiple choice)**
1. Which of the following is required to use Copilot in VS Code?
	- A. A GitHub account with Copilot enabled and the Copilot extension installed/signed in
	- B. Only installing Python
	- C. A local Kubernetes cluster
	- D. A GitHub Enterprise Server license

	**Answer:** A

2. What is the role of the preconfigured Python Codespace template in this exercise?
	- A. It hosts production traffic
	- B. It provides a ready-to-use environment with Copilot and a sample FastAPI app
	- C. It only runs unit tests
	- D. It disables Copilot

	**Answer:** B

3. Which command is used to serve the Python web app inside the Codespace?
	- A. `npm start`
	- B. `uvicorn`
	- C. `node app.js`
	- D. `dotnet run`

	**Answer:** B

4. How do you interact with the sample FastAPI endpoints in this exercise?
	- A. Only via curl in the terminal
	- B. Via the built-in FastAPI docs (`/docs`) in the Simple Browser and its “Try it out” UI
	- C. Only through GitHub Actions
	- D. By editing a JSON file

	**Answer:** B

5. Why should you pay attention to Copilot Pro trial terms if you choose that option?
	- A. Because it removes your repository access
	- B. Because charges start after the 30-day trial unless you cancel
	- C. Because it disables Codespaces free hours
	- D. Because it downgrades your account

	**Answer:** B

## Module 4 – Use GitHub Copilot with Python
- Copilot can help both when starting new Python code and when updating existing projects (for example, extending a FastAPI app).
- Prompt engineering for Python:
  - Prompts are instructional comments or chat messages that describe what you want (for example, framework, HTTP method, payload).
  - Vague prompts (for example, `# Create an API endpoint`) can yield unpredictable or unhelpful code.
  - Specific prompts (for example, `# Create an API endpoint using FastAPI that accepts a JSON payload in a POST request`) guide Copilot effectively.
- Best practices:
  - Start with simple prompts, then add detail as you iterate.
  - Reword prompts or provide extra context (for example, existing function signatures) when suggestions aren’t satisfactory.
  - Use `Ctrl+Enter`/`Cmd+Enter` to cycle multiple suggestions and choose or edit the best one.
  - Use Copilot Chat with `@workspace` and file references for more complex multi-file changes or explanations.
- Copilot uses open files in your editor (Python, HTML, etc.) as context, so open relevant files to improve suggestion quality.
- If you’re stuck, start writing part of the function or class and let Copilot autocomplete the rest.

**Quick quiz – Module 4 (multiple choice)**
1. Why is `# Create an API endpoint` considered a weak prompt?
	- A. It is too specific
	- B. It is vague and doesn’t specify framework, method, or data format
	- C. Copilot doesn’t understand comments in Python
	- D. It is not valid Python syntax

	**Answer:** B

2. Which is a better prompt for generating a FastAPI endpoint in this module?
	- A. `# Do something`
	- B. `# Create an API endpoint using the FastAPI framework that accepts a JSON payload in a POST request`
	- C. `# Fix the code`
	- D. `# Magic`

	**Answer:** B

3. What should you do if Copilot’s initial suggestion is not what you want?
	- A. Accept it anyway
	- B. Stop using Copilot
	- C. Cycle to other suggestions or refine the prompt with more detail
	- D. Delete your project

	**Answer:** C

4. How does opening more relevant Python files affect Copilot’s output?
	- A. It has no effect
	- B. It provides extra context Copilot can use to generate better suggestions
	- C. It disables Copilot
	- D. It forces Copilot to ignore prompts

	**Answer:** B

5. What’s a good working pattern when using Copilot on a Python project?
	- A. Expect Copilot to write the entire project in one step
	- B. Iteratively refine prompts, review suggestions, and provide partial code for Copilot to autocomplete
	- C. Accept every suggestion without reading it
	- D. Turn off testing and linting

	**Answer:** B

## Module 5 – Exercise: Update a Python web API with GitHub Copilot
- The exercise uses a Python web API (FastAPI) that already has a token-generation endpoint.
- Goal: extend the API by adding an endpoint that accepts text and returns tokens (or a checksum) using Copilot-generated code.
- Step 1: In `main.py`, add a comment prompt asking Copilot to create a Pydantic model (for example, a `Text` model with a `text: str` field).
- Step 2: Add another comment prompting Copilot to create a new FastAPI POST endpoint that accepts a JSON body with a `text` field and returns processed data (for example, a checksum or token list).
- Step 3: Use Copilot Chat or manual edits to add any missing imports (for example, `base64`, `os`, or `BaseModel`), then verify the endpoint.
- You validate the new endpoint using the FastAPI docs UI (`/docs`) and “Try it out,” ensuring the new route appears and responds correctly.
- The exercise demonstrates an interactive workflow: prompting Copilot, accepting/editing generated code, and testing live in the running API.

**Quick quiz – Module 5 (multiple choice)**
1. What is the main goal of the Python web API exercise?
	- A. Build a GUI desktop app
	- B. Extend an existing FastAPI API with a new endpoint using Copilot
	- C. Migrate a database schema
	- D. Configure CI/CD pipelines

	**Answer:** B

2. What is the role of the Pydantic model `Text` in the exercise?
	- A. It configures logging
	- B. It defines the shape of incoming JSON data with a `text` field
	- C. It stores environment variables
	- D. It manages database connections

	**Answer:** B

3. How do you prompt Copilot to add the new FastAPI endpoint?
	- A. By creating a GitHub issue
	- B. By adding a descriptive Python comment in `main.py` explaining the desired endpoint behavior
	- C. By editing the README only
	- D. By running a shell script

	**Answer:** B

4. Why might you need to add imports like `base64` and `os` manually or via Copilot Chat?
	- A. Because they are always imported automatically
	- B. Because missing imports can cause the generated code to crash at runtime
	- C. Because they are unrelated to the API
	- D. Because FastAPI requires no imports

	**Answer:** B

5. How do you verify that your new endpoint is working?
	- A. By only reading the source code
	- B. By visiting the FastAPI docs (`/docs`), finding the endpoint, and using “Try it out” to send a request
	- C. By checking GitHub notifications
	- D. By restarting the Codespace without testing

	**Answer:** B

## Exam cram – Using GitHub Copilot with Python
- Copilot basics: AI coding partner inside your IDE that generates Python code from prompts and context; you must always review, test, and adapt its output.
- Prompts: clear, specific natural-language instructions (often comments) that describe frameworks, HTTP methods, payloads, and behavior yield better FastAPI/Python code.
- Setup essentials: GitHub account with Copilot enabled, Copilot extension installed and signed in on VS Code, and a Codespaces template for a ready-made Python web API.
- Codespaces workflow: open the preconfigured Python Codespace, let it install dependencies, run `uvicorn` to serve the FastAPI app, and test endpoints via the `/docs` UI.
- Prompt engineering: avoid vague prompts; refine iteratively, use multiple suggestions, and leverage Copilot Chat (with `@workspace`) for multi-file context and explanations.
- Context usage: Copilot considers open Python and related files as context, so open relevant modules (for example, `main.py`, models, routers) before prompting.
- Exercise pattern: use prompts to generate Pydantic models and FastAPI endpoints, then fix imports and behavior, and finally test the API end-to-end.
- Best practices: keep prompts small and incremental, validate generated code with tests or manual checks, and use Copilot to assist (not replace) your own understanding of Python and FastAPI.
- Exam focus: know how to set up Copilot, how prompts influence output, how Codespaces is used for Python APIs, and how to safely integrate Copilot into Python development workflows.
