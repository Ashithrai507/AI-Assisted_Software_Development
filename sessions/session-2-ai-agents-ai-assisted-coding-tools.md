# Session 2: AI Agents and AI-Assisted Coding Tools

**Duration:** 1.5 Hours  
**Topic:** Understanding AI Agents, AI Coding Assistants and Modern Software Development Workflows

---

## 1. Introduction

Artificial Intelligence is changing the way software applications are developed.

Traditionally, developers write code manually, debug errors, search for solutions and test their applications.

Today, AI-powered tools can assist with many of these tasks. Some tools can even understand a project, modify multiple files, execute commands and help build complete applications.

In this session, we will learn:
- What AI coding assistants are.
- What AI agents are and how they work.
- Difference between AI assistants and AI agents.
- Popular AI-powered development tools.
- How to use AI tools in software development.
- Benefits, limitations and responsible usage.

---

## 2. What are AI Coding Assistants?

AI Coding Assistants are tools that use artificial intelligence to help developers write, understand, debug and improve code.

They understand instructions written in natural language and generate relevant code or suggestions.

### Common Uses

- Generating code from descriptions.
- Completing partially written code.
- Explaining complex code.
- Finding and fixing errors.
- Generating test cases.
- Improving code quality.
- Creating documentation.

### Example

A developer wants to create a Python function to calculate the factorial of a number.

Instead of writing everything manually, the developer can ask an AI coding assistant:

"Write a Python function to calculate the factorial of a number using recursion."

The tool generates the code, which the developer can review and use.

---

## 3. What is an AI Agent?

An AI Agent is an AI-powered system that can understand a goal, plan steps and perform actions using available tools to complete a task.

Unlike a basic chatbot that mainly responds to questions, an AI agent can interact with its environment and perform multiple operations.

### Example

Suppose you want to build a simple student management application.

You provide the instruction:

"Build a student management application with student registration, login and a dashboard."

An AI agent may:
1. Understand the requirements.
2. Plan the application structure.
3. Create frontend files.
4. Develop backend functionality.
5. Connect the database.
6. Run the application.
7. Identify and fix errors.

The developer can review and guide the process throughout.

**Important:** An AI agent does not automatically guarantee a correct or complete application. Its output must be reviewed and tested.

---

## 4. How Does an AI Agent Work?

An AI agent generally follows a cycle:

### 1. Understand
Receives the user's instruction and identifies the objective.

### 2. Plan
Breaks the objective into smaller tasks.

### 3. Act
Uses available tools to perform actions.

### 4. Observe
Checks the results of its actions.

### 5. Improve
Uses the results to decide the next step or correct errors.

### Example: Creating a Login Page

- Goal: Create a login page.
- Plan: Design the page and add input fields.
- Action: Generate HTML, CSS and JavaScript.
- Observation: Run the page and check its appearance.
- Improvement: Fix layout or validation issues.

This process continues until the task is completed or requires further instructions.

---

## 5. AI Assistant vs AI Agent

| AI Assistant | AI Agent |
|---|---|
| Mainly responds to instructions | Can work towards a defined goal |
| Usually generates suggestions or code | Can perform actions using tools |
| Often requires step-by-step user instructions | Can plan multiple steps |
| User performs most development actions | Can execute some development actions |
| Example: Basic code chatbot | Example: Agentic coding tool |

An AI assistant can help write a function, while an AI agent may create files, modify code, run tests and fix errors as part of a larger task.

The distinction is not always strict. Modern AI tools can combine both approaches.

---

## 6. Understanding AI Models, Tools and Agents

These terms are related but have different meanings.

**AI Model:** The underlying system that understands instructions and generates responses.

Examples: GPT, Claude and Gemini models.

**AI Tool:** A software application that provides access to AI capabilities.

Examples: ChatGPT, GitHub Copilot and OpenCode.

**AI Agent:** A system that uses an AI model and available tools to perform tasks with some level of autonomy.

An agent may use tools such as:
- File reading and editing.
- Terminal commands.
- Web search.
- Code execution.
- Testing tools.

---

## 7. Popular AI-Assisted Development Tools

### 1. GitHub Copilot

GitHub Copilot is an AI-powered coding assistant that integrates with development environments such as Visual Studio Code.

<https://github.com/features/copilot>

**Features:**
- Code completion.
- Code generation.
- Code explanation.
- Chat-based assistance.
- Support for debugging and testing.
- Agent capabilities in supported environments.

**Example:** While writing a Python program, Copilot can suggest the next lines of code based on the current context.

### 2. OpenCode

OpenCode is an open-source AI coding agent that can be used through a terminal or supported interfaces.

<https://opencode.ai/>

**Features:**
- Understands existing codebases.
- Creates and modifies files.
- Executes development commands.
- Supports different AI models and providers.
- Helps debug and improve applications.

**Example:** You can ask OpenCode to examine a project and add a new feature.

### 3. Cursor

Cursor is an AI-powered code editor designed to assist with software development.

<https://cursor.com/>

**Features:**
- AI-assisted code completion.
- Codebase understanding.
- Natural-language code editing.
- Multi-file modifications.
- AI-powered debugging assistance.

**Example:** Ask Cursor to modify the existing application to add a search feature.

### 4. Claude Code

Claude Code is an AI coding agent developed by Anthropic.

<https://www.anthropic.com/claude-code>

**Features:**
- Understands project structure.
- Edits multiple files.
- Runs terminal commands.
- Helps fix bugs.
- Supports software development workflows.

### 5. Windsurf

Windsurf is an AI-powered development environment designed to support agentic software development.

<https://windsurf.com/>

**Features:**
- AI-assisted coding.
- Codebase awareness.
- Multi-file editing.
- Agentic development workflows.
- Code generation and debugging.

**Note:** Features, pricing and model availability may change. Some tools require paid subscriptions or API access.

---

## 8. How AI Coding Agents Interact with a Project

An AI coding agent may use different tools to work with an existing project.

| Capability | Purpose |
|---|---|
| File Reading | Understand existing code |
| File Editing | Create or modify files |
| Terminal | Execute commands |
| Code Execution | Run programs |
| Testing | Check application behaviour |
| Debugging | Identify and fix errors |
| Git Integration | Review and manage code changes |

### Example Workflow

Suppose a developer has a basic React application and wants to add a login feature.

The agent can:

1. Read the existing project files.
2. Understand the current structure.
3. Identify where the login feature should be added.
4. Create or modify the required components.
5. Run the application.
6. Check for errors.
7. Suggest or implement corrections.

The developer should review the changes before accepting them.

---

## 9. How to Write Effective Instructions for AI Agents

The prompting techniques learned in Session 1 are also important when working with AI agents.

However, agent-based development requires additional clarity because the tool may modify project files or execute commands.

### Good Instructions Should Include

1. **Goal:** What should be developed?
2. **Context:** What is the existing project?
3. **Technology:** Which languages and frameworks should be used?
4. **Requirements:** What features are needed?
5. **Constraints:** What should not be changed?
6. **Verification:** How should the result be tested?

### Example

**Poor Prompt:**

"Create a website."

**Better Prompt:**

"You are a full-stack developer. Create a student management application using React for the frontend and Flask for the backend. Include student registration, login and a dashboard. Use simple code and maintain a clear project structure. First inspect the existing project before making changes. Run the application and check for errors after implementation."

The second instruction gives the agent enough context to work more effectively.

---

## 10. Agentic Development vs Traditional Development

| Traditional Development | Agentic Development |
|---|---|
| Developer writes most code manually | AI agent can generate and modify code |
| Developer manually navigates files | Agent can inspect project files |
| Developer executes commands | Agent can execute permitted commands |
| Developer manually identifies errors | Agent can help identify and fix errors |
| More direct manual control | Requires monitoring and review of AI actions |

AI-assisted development does not remove the need for programming knowledge. Developers must understand the code, architecture and output.

---

## 11. Benefits of AI Agents in Software Development

1. **Faster Development:** Helps complete repetitive coding tasks quickly.
2. **Reduced Manual Work:** Automates some routine development activities.
3. **Easy Learning:** Helps beginners understand unfamiliar code.
4. **Debugging Assistance:** Identifies possible errors and suggests fixes.
5. **Code Improvement:** Helps improve readability and maintainability.
6. **Rapid Prototyping:** Helps create initial versions of applications quickly.

---

## 12. Limitations and Risks

AI agents are powerful, but they also have limitations.

### Common Limitations

- May generate incorrect code.
- May misunderstand project requirements.
- Can introduce bugs while modifying existing files.
- May use outdated libraries or APIs.
- Can make unnecessary changes.
- May consume paid API credits or usage limits.

### Safety and Best Practices

1. Review code before accepting changes.
2. Keep backups or use Git before major modifications.
3. Avoid sharing API keys, passwords and confidential information.
4. Check commands before allowing execution.
5. Run tests after every major change.
6. Understand the generated code.
7. Give agents only the permissions they need.

**Important:** Never blindly allow an AI agent to execute destructive commands or modify important project files.

---

## 13. Practical Activity

### Activity: Explore an AI Coding Agent

**Objective:** Understand how an AI agent interacts with a software project.

### Task

Create a simple Python calculator using an AI coding tool.

The calculator should support:
- Addition.
- Subtraction.
- Multiplication.
- Division.

### Instructions

1. Open an AI coding tool such as OpenCode or another available agent.
2. Create or open a project folder.
3. Give the agent a clear instruction to build the calculator.
4. Ask it to explain the generated code.
5. Run the application.
6. Test all four operations.
7. Ask the agent to fix any errors found.
8. Review the final code.

### Suggested Prompt

"Create a simple command-line calculator using Python. It should support addition, subtraction, multiplication and division. Handle division by zero and invalid inputs. Keep the code beginner-friendly, explain the implementation and run basic tests."

**Expected Outcome:** Students understand how an AI coding agent can create, modify, execute and test a small application.

---

## 14. Quick Revision

**1. What is an AI Coding Assistant?**  
A tool that uses AI to help developers write, understand and debug code.

**2. What is an AI Agent?**  
An AI-powered system that can understand goals, plan tasks and perform actions using available tools.

**3. What is the difference between an AI assistant and an AI agent?**  
An assistant mainly provides suggestions and responses, while an agent can perform actions to complete tasks.

**4. Name any three AI coding tools.**  
GitHub Copilot, OpenCode and Cursor.

**5. What is the role of a terminal in agentic development?**  
It allows an agent to execute commands and interact with the development environment.

**6. Why is human supervision important?**  
AI-generated changes may contain errors, bugs or security issues.

**7. Why should Git be used when working with AI agents?**  
Git helps track changes and restore previous versions if something goes wrong.

---

## Session 2 Summary

By the end of this session, students should understand:

- The concept of AI coding assistants.
- What AI agents are and how they work.
- The difference between AI assistants and AI agents.
- Popular AI-assisted development tools.
- How agents interact with project files and terminals.
- How to give effective instructions to coding agents.
- Benefits, limitations and safety considerations.

**Next Session:** Building a Real-World Application Using AI-Assisted Development Tools.
