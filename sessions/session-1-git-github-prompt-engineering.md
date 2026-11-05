# Session 1: Git, GitHub and Prompt Engineering

**Duration:** 1.5 Hours  
**Topic:** Fundamentals of Version Control, Git, GitHub and Effective Prompting

---

## 1. Introduction

Software development involves writing, modifying, testing and maintaining code. During development, we frequently make changes to files. Sometimes these changes introduce errors, and we may need to return to an earlier working version.

To manage these changes efficiently, developers use **Version Control Systems (VCS)**.

In this session, we will learn:
- What version control is and why it is needed.
- Git and GitHub fundamentals.
- Basic Git commands.
- How to collaborate using GitHub.
- Introduction to Generative AI and Prompt Engineering.

---

## 2. Version Control System (VCS)

A Version Control System is a tool that records changes made to files over time.

It allows developers to:
- Track changes in their code.
- Restore previous versions.
- Work on different features independently.
- Collaborate with other developers.
- Identify who made particular changes.

### Example

Imagine you are developing a college management application.

You create the first version and save it as:

- project_v1
- project_v2
- project_final
- project_final_updated
- project_final_latest

Managing these files becomes confusing.

A version control system solves this problem by maintaining the history of changes in one project.

### Types of Version Control Systems

1. **Local Version Control:** Stores file versions on the same computer.
2. **Centralized Version Control:** Stores project history on a central server.
3. **Distributed Version Control:** Every developer has a complete copy of the project history.

Git is a distributed version control system.

---

## 3. Introduction to Git

**Git** is a free and open-source distributed version control system used to track changes in source code.

It was created by Linus Torvalds in 2005.

### Why use Git?

- Tracks every important change in a project.
- Helps recover previous versions.
- Supports multiple developers working together.
- Allows developers to create separate branches.
- Works locally without requiring an internet connection.

### Git Installation

Download Git from:

https://git-scm.com/

After installation, verify it using:

```bash
git --version
```

Configure your name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

These details are associated with your commits.

---

## 4. Introduction to GitHub

**GitHub** is an online platform used to host Git repositories and collaborate on software projects.

It provides features such as:
- Online code storage.
- Project collaboration.
- Pull requests and code reviews.
- Issue tracking.
- Project documentation.
- Open-source contributions.

### Git vs GitHub

| Git | GitHub |
|---|---|
| Version control system | Online code hosting platform |
| Installed on a computer | Accessed through the internet |
| Tracks changes locally | Hosts and shares repositories |
| Works offline | Requires internet for online collaboration |
| Command-line tool | Web platform with collaboration features |

**Remember:** Git is the tool used to manage versions. GitHub is a platform where Git repositories can be stored and shared.

---

## 5. Important Git Terminology

**Repository (Repo):** A project folder tracked by Git.

**Commit:** A saved snapshot of changes in the repository.

**Branch:** An independent line of development.

**Merge:** Combining changes from one branch into another.

**Clone:** Downloading an existing remote repository to your computer.

**Push:** Uploading local commits to a remote repository.

**Pull:** Fetching and integrating changes from a remote repository.

**Remote:** A reference to a repository hosted elsewhere, usually on GitHub.

---

## 6. Basic Git Workflow

Git mainly works through three areas:

1. **Working Directory:** Where you create and modify files.
2. **Staging Area:** Where you select changes to include in the next commit.
3. **Repository:** Where committed changes are stored.

### Basic workflow

Working Directory → Staging Area → Local Repository → Remote Repository

### Important Git Commands

| Command | Purpose |
|---|---|
| `git init` | Creates a new Git repository |
| `git status` | Displays the current status |
| `git add .` | Stages all changes in the current directory |
| `git commit -m "message"` | Saves staged changes |
| `git log` | Displays commit history |
| `git clone URL` | Copies a remote repository |
| `git push` | Uploads commits |
| `git pull` | Fetches and integrates remote changes |
| `git branch` | Lists branches |
| `git switch branch-name` | Switches to another branch |

### Example: Creating Your First Git Repository

Step 1: Create a project folder.

```bash
mkdir my-project
cd my-project
```

Step 2: Initialize Git.

```bash
git init
```

Step 3: Create a file.

```bash
echo "Hello Git" > README.md
```

Step 4: Check the status.

```bash
git status
```

Step 5: Add the file to the staging area.

```bash
git add README.md
```

Step 6: Commit the changes.

```bash
git commit -m "Initial commit"
```

Your first Git commit is now created.

---

## 7. Working with GitHub

To upload a local project to GitHub:

1. Create an account at https://github.com/
2. Click **New Repository**.
3. Enter a repository name.
4. Create the repository.
5. Connect your local project to the remote repository.

Commands:

```bash
git remote add origin <repository-url>
git branch -M main
git push -u origin main
```

Here:
- `remote add origin` connects the local repository to GitHub.
- `branch -M main` renames the current branch to main.
- `push -u origin main` uploads the commits and sets the upstream branch.

After the first push, you can generally use:

```bash
git push
```

To download an existing GitHub project:

```bash
git clone <repository-url>
```

---

## 8. Branching and Collaboration

A branch allows developers to work on a new feature without directly modifying the main project.

### Example

Suppose a team is developing an online shopping application.

- Developer 1 works on the login page.
- Developer 2 works on the payment page.
- Developer 3 works on the product page.

Each developer can work on a separate branch.

### Creating and switching branches

```bash
git branch login-feature
git switch login-feature
```

Alternatively, create and switch in one command:

```bash
git switch -c login-feature
```

After completing the feature:

```bash
git add .
git commit -m "Added login feature"
```

The changes can later be merged into the main branch.

### Pull Requests (PR)

A Pull Request is a request to merge changes from one branch into another on GitHub.

It allows team members to:
- Review code.
- Discuss changes.
- Suggest improvements.
- Identify errors before merging.

### Typical Collaboration Workflow

1. Clone the project.
2. Create a new branch.
3. Make changes.
4. Commit the changes.
5. Push the branch to GitHub.
6. Create a Pull Request.
7. Review and merge the changes.

---

## Part 2: Introduction to Prompt Engineering

## 9. What is Generative AI?

Generative Artificial Intelligence refers to AI systems that can generate new content based on the instructions and information provided by users.

It can generate:
- Text and explanations.
- Computer programs.
- Images and designs.
- Summaries and reports.
- Ideas and documentation.

Examples include:
- ChatGPT
- Google Gemini
- Claude
- GitHub Copilot

Generative AI can assist developers in understanding code, finding errors, generating solutions and improving productivity.

However, AI-generated responses should always be reviewed and tested.

---

## 10. What is Prompt Engineering?

Prompt Engineering is the process of designing clear and effective instructions (prompts) to obtain useful results from an AI system.

A prompt is simply the input or instruction given to an AI tool.

### Example

**Poor Prompt:**

"Create a website."

This does not explain what kind of website is required.

**Better Prompt:**

"Create a simple college event registration website using HTML, CSS and JavaScript. Include an event description, registration form and submit button. Use a clean layout and explain the code."

The second prompt provides clear requirements and produces a more relevant result.

---

## 11. Elements of a Good Prompt

A good prompt generally contains the following elements:

1. **Role:** Defines what the AI should act as.
2. **Context:** Explains the background or situation.
3. **Task:** Clearly describes what needs to be done.
4. **Constraints:** Specifies limitations or requirements.
5. **Output Format:** Explains how the response should be presented.

### Example

"You are an experienced Python developer. I am a beginner learning Python. Create a program to check whether a number is prime. Use simple code without advanced libraries and explain each step."

In this prompt:
- Role: Experienced Python developer.
- Context: Beginner learning Python.
- Task: Create a prime number program.
- Constraints: Avoid advanced libraries.
- Output: Code with explanation.

---

## 12. Common Prompting Techniques

### 1. Be Specific
Clearly mention what you want instead of giving general instructions.

### 2. Provide Context
Explain your project, programming language and current problem.

### 3. Break Large Tasks into Smaller Tasks
Instead of asking AI to build an entire application at once, divide it into smaller modules.

Example:
- First create the login page.
- Then implement authentication.
- Next connect the database.
- Finally test the application.

### 4. Set Constraints
Mention requirements such as:
- Programming language.
- Framework.
- Expected output.
- Code length.
- Design requirements.

### 5. Ask for Explanations
Ask AI to explain the generated code so that you understand what you are using.

### 6. Improve Prompts Iteratively
If the first response is not satisfactory, provide additional instructions and refine the prompt.

---

## 13. Using AI for Software Development

AI tools can assist developers in different stages of software development.

| Activity | Example Prompt |
|---|---|
| Code Generation | "Write a Python program to sort a list." |
| Code Explanation | "Explain this code line by line." |
| Debugging | "Find the error in this code and suggest a fix." |
| Code Improvement | "Improve this code without changing its output." |
| Documentation | "Generate a README file for this project." |
| Testing | "Write test cases for this function." |

### Example: Debugging with AI

Prompt:

"I am getting a TypeError in my Python program. Identify the reason for the error, explain it in simple terms and provide the corrected code."

Always provide the relevant code and complete error message for better results.

---

## 14. Limitations and Responsible Use of AI

AI tools are useful, but they are not always correct.

Important points:
- AI may generate incorrect or outdated information.
- Generated code may contain bugs.
- AI may misunderstand incomplete instructions.
- Generated solutions may have security issues.
- AI-generated work should not be blindly copied.

### Best Practices

1. Understand the code before using it.
2. Test generated code with different inputs.
3. Verify important technical information.
4. Never share passwords, API keys or confidential data.
5. Follow academic integrity rules.
6. Use AI as an assistant, not as a replacement for learning.

---

## 15. Practical Activity

### Activity: Build a Simple College Event Webpage

**Objective:** Understand Git, GitHub and basic prompt engineering through a small development task.

**Task:**

Create a simple college event webpage using HTML and CSS with the following sections:

- College event title.
- Event description.
- Date and venue.
- Registration button.

### Instructions

1. Ask an AI tool to generate the HTML and CSS.
2. Review and understand the generated code.
3. Create a project folder.
4. Initialize a Git repository.
5. Add and commit the files.
6. Create a GitHub repository.
7. Push the project to GitHub.

**Expected Outcome:** A simple webpage with its source code maintained in a Git repository and uploaded to GitHub.

---

## 16. Quick Revision

**1. What is Git?**  
Git is a distributed version control system used to track changes in files.

**2. What is GitHub?**  
GitHub is an online platform used to host Git repositories and collaborate on projects.

**3. What is a commit?**  
A commit is a saved snapshot of changes in a Git repository.

**4. What is a branch?**  
A branch is an independent line of development.

**5. What is a Pull Request?**  
A Pull Request is a request to merge changes from one branch into another.

**6. What is Prompt Engineering?**  
Prompt Engineering is the process of creating effective instructions to get useful responses from AI tools.

**7. Why should AI-generated code be tested?**  
Because AI can generate incorrect, incomplete or insecure code.

---

## Session 1 Summary

By the end of this session, students should understand:

- The importance of version control.
- The fundamentals of Git and GitHub.
- Basic Git commands and repository management.
- Branching and collaborative development.
- The concept of Generative AI.
- How to write clear and effective prompts.
- How AI can assist in software development.

**Next Session:** Introduction to AI Agents and AI-Assisted Coding Tools.
