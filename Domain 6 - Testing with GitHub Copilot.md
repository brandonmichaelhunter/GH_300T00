# Domain 6: Testing with GitHub Copilot (9%)
## Describe the options for generating testing for your code
- Describe how GitHub Copilot can be used to add unit tests, integration tests, and other test types to your code
  - In Agent mode, agents can create/add unit test, integration test and other types of tests.
    - As part of an orchestrated AI workflow - we can create a Test Agent and provide it skills to create test code for your current project.   
  - '/test' - generates unit testse for the selected code snippet.
  - Copilot for Chat
    -  Generate tests through prompts
  -  Subscription Plans
    - Pro, Pro+, Business, Enterprise
      - Features
        - Automated test generation and code explanation features.
  - Copilot can enhance your SDLC
    - Testing and quality assurance
      - Unit test creation
      - Test data generation
    - Automated testing workflows
      - Test suite architecture
      - Test autoamtion pipelines
      - Quality gates
      - Performance testing
- Explain how GitHub Copilot can assist in identifying edge cases and suggesting tests to address them
  - Role prompting for specialized tasks
    - You can create a role for testing specialist.
    - The role can produce edge case handling
    - Suggest tests to address each edge case.
  - Few-shot learning can help genearting sophisticated implementations that handle unique scenarios and edge cases, which in turn can help copilot suggest tests to address the edge cases.  
  - You can ask copilot to review a function to avoid any null checks.
    - Question: Copilot suggests a test case that fails because the function does not handle a null input correctly. What should you do?
    - Answer: ask Copilot Chat to rewrite the function to avoid any null checks
    - Reason:
      - This addresses the root cause of the failing test case.
      - Ensure that the functions handles null inputs correctly
      - You can prevent future test failures and improve overall reliability of the code.   

## Describe the different SKUs for GitHub Copilot
- Describe the different SKUs and the privacy considerations for GitHub Copilot
- Describe the different code suggestion configuration options on the organization level
- Describe the GitHub Copilot Editor config file

Take a look this - https://learn.microsoft.com/en-us/training/modules/develop-unit-tests-using-github-copilot-tools/
