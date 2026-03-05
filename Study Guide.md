
# Use GitHub Copilot responsibly (15–20%)
## Understand responsible AI principles
- **Describe risks and limitations of Generative AI tools**
  - Identify potential biases and ethical considerations in AI-generated content
  - Explain the importance of human oversight and critical evaluation of AI outputs
  - Discuss the implications of AI-generated content on privacy and security
  - Recognize the potential for misuse of AI tools and the importance of responsible usage
  - Explain the need for transparency and accountability in AI development and deployment
  - Describe the role of developers in ensuring ethical AI usage
  - Discuss the impact of AI on society and the workforce, and the importance of preparing for these changes
- **Describe ethical and responsible AI usage**
  - AI usage should be guided by several key principles that ensure AI systems are developed and operated in a manner that is fair, safe, and beneficial to society. These principles include:
    - Fairness - AI systems should treat all people fairly: 
        - AI systems should be designed to avoid bias and discrimination, ensuring that they treat all users equitably regardless of their background or characteristics.
    - Transparency - AI systems should be understandable: 
        - The workings of AI systems should be transparent and understandable to users, allowing them to know how decisions are made and what data is being used.
    - Accountability - People should be accountable for AI systems: 
      - Developers and organizations should be accountable for the outcomes of their AI systems, taking responsibility for any harm or unintended consequences that may arise.
    - Privacy and Security - AI systems should be secure and respect privacy: 
        - AI systems should respect user privacy and protect personal data, ensuring that it is collected, stored, and used in a secure and responsible manner.
        - AI systems should be designed to operate safely, minimizing risks to users and society while maximizing benefits.
    - Reliability and Safety - AI systems should be reliable and safe: 
        - AI systems should be designed to operate reliably and safely, minimizing risks to users and society while maximizing benefits.
    - Inclusivity - AI systems should be inclusive and accessible: 
        - AI systems should be designed to be inclusive and accessible to all users, regardless of their abilities or backgrounds, ensuring that everyone can benefit from AI technologies.
- **Identify potential harms and mitigation strategies of AI usage**
  - Potential harms of AI usage include:
    - Bias and Discrimination: 
      - AI systems can perpetuate or amplify existing biases in data, leading to unfair treatment of certain groups. 
      - Mitigation strategies include using diverse and representative training data, regularly auditing AI systems for bias, and implementing fairness-aware algorithms.
    - Privacy Violations: 
      - AI systems can collect and use personal data in ways that violate user privacy. 
      - Mitigation strategies include implementing strong data protection measures, obtaining informed consent from users, and adhering to privacy regulations.
    - Misinformation and Manipulation: 
      - AI-generated content can be used to spread misinformation or manipulate public opinion. 
      - Mitigation strategies include developing tools to detect and flag AI-generated content, promoting media literacy, and encouraging responsible use of AI technologies.
    - Job Displacement: 
      - AI automation can lead to job displacement in certain industries. 
      - Mitigation strategies include investing in workforce retraining programs, promoting the development of new job opportunities in the AI sector, and fostering a culture of lifelong learning.
    - Security Risks: 
      - AI systems can be vulnerable to attacks that exploit their weaknesses. 
      - Mitigation strategies include implementing robust security measures, regularly testing AI systems for vulnerabilities, and developing incident response plans.

## Validate and operate AI tools
- Explain the need to validate AI output
    - Validating AI output is crucial to ensure that the generated content is accurate, relevant, and appropriate for the intended use. 
    - It helps to identify and correct any errors, biases, or inappropriate content that may arise from AI-generated outputs, ensuring that the results are reliable and trustworthy.
    - Validation also helps to maintain the integrity of the development process and ensures that AI tools are used effectively and responsibly, minimizing potential risks and maximizing benefits.
    - It is important to critically evaluate AI outputs, especially in contexts where accuracy and ethical considerations are paramount, such as in healthcare, finance, or content creation.
- Identify how to operate GitHub Copilot responsibly
  - Use GitHub Copilot as a tool to assist and augment human creativity and productivity, rather than relying on it as a sole source of truth or decision-making.
  - Regularly review and validate the code suggestions provided by GitHub Copilot to ensure they are accurate, relevant, and appropriate for the specific use case.
  - Be mindful of potential biases in the suggestions generated by GitHub Copilot, and take steps to mitigate them by providing diverse and representative input and feedback.
  - Use GitHub Copilot in a way that respects user privacy and data security, ensuring that sensitive information is not inadvertently exposed through AI-generated content.
  - Stay informed about the latest developments and best practices in responsible AI usage, and continuously evaluate and improve your use of GitHub Copilot to align with ethical principles and mitigate potential harms.

# Use GitHub Copilot features (25–30%)
## Use GitHub Copilot in the IDE
- **Enable Copilot in the IDE**
  - Identify supported IDEs and platforms for GitHub Copilot
  - Must have a GitHub account and be signed in to use GitHub Copilot in the IDE
  - Install the GitHub Copilot extension or plugin for your IDE. Extension called GitHub Copilot.
  - Enable or Display GitHub Copilot from the bottom pane of the IDE. Click on the GitHub Copilot icon to access settings and features.On the bottom pane of the VS Code window, select the status icon, and then select Enable or Disable.
- **Trigger Copilot through inline suggestions, chat, CLI, and Plan Mode**
  - Trigger inline suggestions by typing code in the editor, and GitHub Copilot will automatically provide suggestions based on the context of your code.
  - Triggering GitHub Copilot Chat by opening the chat interface within the IDE, allowing you to ask questions and receive code suggestions in a conversational manner. For Windows its Ctrl + Shift + C, for Mac its Cmd + Shift + C.
  - Triggering CLI you must have GitHub Copilot CLI installed and configured. You can then use the command line interface to interact with GitHub Copilot for various tasks, such as generating code snippets, managing files, and more.
  - Triggering Plan Mode by using the appropriate command or interface within the IDE to enter Plan Mode, which allows you to create and manage plans for your development tasks with the assistance of GitHub Copilot.
- **Exclude specific files or repositories (app knowledge)**
  - At the repository level, GitHub-> Settings -> Code & automation -> select Copilot -> Respositories and paths to exclude.
    - Exclude specific repositories or paths within a repository to prevent GitHub Copilot from providing suggestions for those areas.
    - Exclude reporitories or paths that contain sensitive information, legacy code, or areas where you do not want AI-generated suggestions to be provided.
  - At the organizations level, Your organizations -> (sidebar) Copilot -> Content exclusions -> 
    - Exclude specific repositories or paths within an organization to prevent GitHub Copilot from providing suggestions for those areas across all repositories in the organization.
  - At the IDE level, you can configure GitHub Copilot settings to exclude specific files or directories from receiving suggestions. This can typically be done through the settings or preferences of the GitHub Copilot extension in your IDE, where you can specify patterns or paths to exclude from suggestions.
  - Excluding specific files or repositories can help to ensure that GitHub Copilot does not provide suggestions for sensitive or irrelevant code, and can help to improve the relevance and accuracy of suggestions in other areas of your codebase.
  - Within the IDE settings to exclude files or directories you can in a file called .copilotignore, which is similar to .gitignore, where you can specify patterns for files or directories that you want GitHub Copilot to ignore when providing suggestions. This allows you to have more granular control over which parts of your codebase receive AI-generated suggestions and which parts are excluded.
## Use GitHub Copilot CLI
- **Define GitHub Copilot CLI and how it benefits developers**
  - GitHub Copilot CLI is a command-line utility that allows developers to interact with GitHub Copilot directly from the terminal.
  - User GitHub authentication to access GitHub Copilot features and capabilities through the command line interface.
  - Benefits of GitHub Copilot CLI include:
    - Seamless integration with the command line, allowing developers to access GitHub Copilot features without leaving their terminal environment.
    - Enhanced productivity by enabling developers to generate code snippets, manage files, and perform various tasks using GitHub Copilot directly from the command line.
    - Flexibility in how developers can interact with GitHub Copilot, providing an alternative to the IDE-based experience and allowing for more efficient workflows in certain scenarios.  
  - One shot mode: copilot -i - for question answers.
  - Session mode: copilot -s - for multiple interactions and context retention.
  - Copilot CLI configuration is managed through permission prompts, command-line flags, and local configuration files.
    - Configuration options (common):
    - Trusted directories: Define trusted directories where GitHub Copilot CLI can operate using flags like --trusted-dir or configuration files.
    - Path permissions: Specify which paths GitHub Copilot CLI can access or modify using flags like --allow-path or --deny-path.
    - URL permissions: Control access to specific URLs or domains for GitHub Copilot CLI using flags like --allow-url or --deny-url.
    - Tools permissions:
      - Allow or restrict Copilot from running shell commands or modifying files using flags like --allow-tool or --deny-tool.
  - Configuration is handle via:
    - Slash commands: copilot config set <option> <value>
    - Copilot CLI configurations: (non-interactive mode)
- **Identify the steps for installing GitHub Copilot CLI**
  - Ensure you have Node.js installed on your system, as GitHub Copilot CLI is built on Node.js.
  - Install GitHub Copilot CLI globally using npm (Node Package Manager) by running the following command in your terminal:
    ```
    npm install -g @githubnext/copilot-cli
    ```
  - After installation, you can verify that GitHub Copilot CLI is installed correctly by running:
    ```
    copilot --version
    ```
  - This should display the version of GitHub Copilot CLI that you have installed, confirming that the installation was successful.
  - Using brew, you can install GitHub Copilot CLI on macOS by running the following command in your terminal:
    ```
    brew install github/copilot/copilot-cli
    ```
  - Using bash script, you can install GitHub Copilot CLI by running the following command in your terminal:
    ```
    curl -fsSL https://raw.githubusercontent.com/githubnext/copilot-cli/main/install.sh | sh
    ```
- **Describe key GitHub Copilot CLI features and commands**
  - **One-shot mode**: Use the `copilot -i` command to ask a single question or request a code snippet, and receive an immediate response from GitHub Copilot.
  - **Session mode**: Use the `copilot -s` command to start an interactive session with GitHub Copilot, allowing for multiple interactions and context retention throughout the session.
  - **Configuration commands**: Use the `copilot config set <option> <value>` command to configure various settings for GitHub Copilot CLI, such as trusted directories, path permissions, URL permissions, and tool permissions.
  - **File management commands**: Use commands like `copilot generate <file>` to generate code snippets or files based on prompts, and `copilot manage <file>` to manage existing files with GitHub Copilot CLI.
  - **Help commands**: Use the `copilot help` command to access documentation and information about available commands and features of GitHub Copilot CLI, providing guidance on how to use the tool effectively in various scenarios
- **Use GitHub Copilot CLI interactively and in sessions**
  - copilot -s to start a session and maintain context across multiple interactions, allowing for a more conversational and iterative experience with GitHub Copilot CLI.
    - Within a session, you can ask follow-up questions, request code modifications, or provide additional context to refine the suggestions provided by GitHub Copilot CLI, enhancing the overall development workflow and productivity.
  - copilot -i for one-shot interactions, where you can ask a single question or request a code snippet without maintaining context across multiple interactions, providing a quick and efficient way to get specific information or code suggestions from GitHub Copilot CLI.
- **Generate scripts and manage files with GitHub Copilot CLI**
  - copilot generate <file> to generate code snippets or files based on prompts, allowing you to quickly create new code or files with the assistance of GitHub Copilot CLI.
  - copilot manage <file> to manage existing files with GitHub Copilot CLI, enabling you to modify, refactor, or enhance existing code with the help of AI-generated suggestions and improvements, streamlining your development workflow and improving code quality.
  
## Use GitHub Copilot features and capabilities
- **Use Agent Mode, Edit Mode, and MCP for enhanced development and workflows; manage Agent Sessions and delegate tasks to Sub‑Agents for optimized context usage**
- **Use Copilot for code review and coding assistance**
- **Utilize Spaces, Spark, Pull Request summaries, and customizable review standards via instructions files**
- **Understand the limits, options, feedback, and commands of GitHub Copilot Chat; include prompt file reuse for consistent responses**

## Manage organization-wide settings and policies
- **Configure organization-wide policy management; enable Copilot Code Review policies and manage feature availability across IDEs and github.com**
- **Utilize audit log events**
- **Manage subscriptions using the REST API**

# Understand GitHub Copilot data and architecture (10–15%)
## Describe data handling and flow
- **Explain data usage, flow, and sharing**
- **Describe input processing and prompt building**
- **Explain proxy filtering and post-processing**

## Understand lifecycle and limitations
- **Visualize code suggestion lifecycle**
- **Describe limitations of LLMs and Copilot**

# Apply prompt engineering and context crafting (10–15%)
## Craft effective prompts
- **Describe prompt structure and context**
- **Understand how context is determined**
- **Use zero-shot and few-shot prompting**
- **Apply best practices for prompt crafting**

## Engineer prompts for performance
- **Explain prompt engineering principles**
- **Describe prompt process flow and chat history usage**

# Improve developer productivity with GitHub Copilot (10–15%)
## Enhance productivity and code quality
- **Use Copilot for code generation, refactoring, and documentation**
- **Accelerate learning and reduce context switching**
- **Generate sample data and modernize legacy code**

## Support testing and security
- **Generate unit and integration tests**
- **Identify edge cases and write assertions**
- **Suggest security improvements and performance optimizations**

# Configure privacy, content exclusions, and safeguards (10–15%)
## Manage privacy settings and exclusions
- **Configure content exclusions and editor settings**
- **Describe ownership and limitations of outputs**

## Apply safeguards and troubleshoot
- **Enable duplication detection and security warnings**
- **Resolve issues with suggestions and exclusions**
