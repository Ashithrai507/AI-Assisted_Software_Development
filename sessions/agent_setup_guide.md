# Complete Guide: Setting Up OpenCode on Windows

> **Last reviewed:** 13 November 2026\
> **Applies to:** Windows 10/11, Windows Terminal, PowerShell, WSL2, VS
> Code\
> **Project:** OpenCode --- an open-source AI coding agent
>
> Official documentation: <https://opencode.ai/docs>\
> Official downloads: <https://opencode.ai/download>

------------------------------------------------------------------------

## Table of Contents

1.  [What is OpenCode?](#1-what-is-opencode)
2.  [Choose your installation
    method](#2-choose-your-installation-method)
3.  [Prerequisites](#3-prerequisites)
4.  [Option A --- Install OpenCode
    Desktop](#4-option-a--install-opencode-desktop)
5.  [Option B --- Install the CLI natively on
    Windows](#5-option-b--install-the-cli-natively-on-windows)
6.  [Option C --- Install OpenCode using
    WSL2](#6-option-c--install-opencode-using-wsl2)
7.  [Connect an AI provider and choose a
    model](#7-connect-an-ai-provider-and-choose-a-model)
8.  [Open your first project](#8-open-your-first-project)
9.  [Initialize a project with
    AGENTS.md](#9-initialize-a-project-with-agentsmd)
10. [Essential OpenCode commands](#10-essential-opencode-commands)
11. [Configure OpenCode](#11-configure-opencode)
12. [Permissions and safe usage](#12-permissions-and-safe-usage)
13. [VS Code workflow](#13-vs-code-workflow)
14. [Git and project workflow](#14-git-and-project-workflow)
15. [MCP servers, agents, and skills](#15-mcp-servers-agents-and-skills)
16. [Troubleshooting](#16-troubleshooting)
17. [Recommended setup checklist](#17-recommended-setup-checklist)
18. [Useful official links](#18-useful-official-links)

------------------------------------------------------------------------

## 1. What is OpenCode?

OpenCode is an open-source AI coding agent. It can inspect a codebase,
explain code, generate and edit files, help debug errors, run
development commands, and work with supported AI models.

It is available in several forms:

-   **CLI / TUI:** Run OpenCode inside a terminal.
-   **Desktop:** Use OpenCode through a graphical desktop application.
-   **IDE integrations:** Use supported editor integrations.
-   **Web / server workflows:** Run a local OpenCode server and connect
    a client.

OpenCode is the coding agent, not the AI model itself. You connect a
model provider (or use an available free model) to supply the AI
capabilities.

### What you need to pay for

OpenCode itself is open source. Model usage depends on the provider and
model you select. Some providers offer free models; others require an
API key, subscription, or prepaid credits. A ChatGPT subscription and an
OpenAI API account are separate products, so check the sign-in option
and billing terms shown by the provider before using it.

------------------------------------------------------------------------

## 2. Choose your installation method

  -----------------------------------------------------------------------
  Method                  Best for                Recommendation
  ----------------------- ----------------------- -----------------------
  OpenCode Desktop        Beginners and users who Easiest start
                          prefer a GUI            

  Native Windows CLI      Users comfortable with  Good for direct Windows
                          PowerShell or Windows   workflows
                          Terminal                

  WSL2 CLI                Developers who use      Best terminal
                          Linux tools, shells,    development environment
                          and runtimes            on Windows
  -----------------------------------------------------------------------

### My recommendation

-   If you want the simplest setup, install **OpenCode Desktop**.
-   If you want to run commands directly in PowerShell, install the
    **Windows CLI binary** or the current npm CLI package.
-   If you use Git, Python, Node.js, Docker, Linux utilities, and
    terminal-based development heavily, use **WSL2**.

**Important version note:** OpenCode has had more than one major
installation generation. The current documentation may show a V2
installer and package name, while older tutorials show the V1 package
name. Do not mix commands from different generations. Follow the current
official download page and check `opencode --version` after
installation.

------------------------------------------------------------------------

## 3. Prerequisites

### Recommended Windows environment

-   Windows 11, or a supported updated Windows 10 installation.
-   Internet connection.
-   Windows Terminal (recommended).
-   Git for Windows: <https://git-scm.com/download/win>
-   VS Code (optional): <https://code.visualstudio.com/>
-   Node.js LTS (only needed if you choose an npm-based installation):
    <https://nodejs.org/>

### Check your system

Open PowerShell:

``` powershell
winver
```

Check whether Git is installed:

``` powershell
git --version
```

Check Node.js and npm if you plan to use npm:

``` powershell
node --version
npm --version
```

If PowerShell says a command is not recognized, install the relevant
program and open a new terminal.

------------------------------------------------------------------------

## 4. Option A --- Install OpenCode Desktop

This is the simplest option if you prefer a graphical interface.

### Step 1: Download

1.  Open <https://opencode.ai/download>.
2.  Find the **OpenCode Desktop** section.
3.  Select the Windows build matching your computer:
    -   Windows x64 for most Intel and AMD PCs.
    -   Windows ARM64 for ARM-based Windows PCs.
4.  Download the installer.

To check your system architecture, open PowerShell:

``` powershell
$env:PROCESSOR_ARCHITECTURE
```

Common values are `AMD64` for x64 and `ARM64` for ARM64.

### Step 2: Install

1.  Run the downloaded installer.
2.  Follow the installation prompts.
3.  Launch OpenCode from the Start menu.

Only download installers from the official OpenCode website or its
official release links.

### Step 3: Connect a provider

Use the provider connection flow in the application. If the interface
opens a terminal-style session, the `/connect` command is also available
there.

1.  Choose a provider.
2.  Complete its authentication or enter its API key.
3.  Select a model.
4.  Start a session.

See [Connect an AI provider and choose a
model](#7-connect-an-ai-provider-and-choose-a-model).

------------------------------------------------------------------------

## 5. Option B --- Install the CLI natively on Windows

Use this option when you want to run OpenCode from PowerShell, Windows
Terminal, or an integrated terminal.

### Method 1: Download the standalone Windows binary

1.  Open <https://opencode.ai/download>.
2.  Find the **OpenCode Terminal / CLI** download.
3.  Select the Windows x64 or ARM64 binary that matches your system.
4.  Download and extract it if the download is packaged in an archive.
5.  Place the executable in a permanent folder, for example:

``` text
C:\Tools\OpenCode\
```

6.  Add that folder to your Windows `PATH`:
    -   Open Start and search for **Edit the system environment
        variables**.
    -   Select **Environment Variables**.
    -   Under your user variables, select `Path` and choose **Edit**.
    -   Add `C:\Tools\OpenCode\`.
    -   Confirm all dialogs.
7.  Close and reopen PowerShell.

Check that Windows can find OpenCode:

``` powershell
where.exe opencode
opencode --version
```

If `where.exe` cannot find it, check that the executable is in the
folder you added and that you reopened the terminal.

### Method 2: Install using npm

Use this method if Node.js and npm are already installed.

``` powershell
npm install -g @opencode/cli
```

Then verify:

``` powershell
opencode --version
```

The current CLI package uses a native-binary installation step. If
installation fails, check the official installation page for current
platform support and package instructions.

> Older guides may tell you to install `opencode-ai`. That is an older
> package name. Do not copy it blindly when setting up the current CLI;
> use the package shown on the current official download page.

### Start OpenCode

Navigate to a project:

``` powershell
cd C:\Users\YourName\Projects\my-project
```

Start the agent:

``` powershell
opencode
```

The first run may ask you to connect a provider or select a model.

------------------------------------------------------------------------

## 6. Option C --- Install OpenCode using WSL2

WSL2 gives Windows a real Linux development environment. It is useful
when your projects depend on Linux command-line tools or Linux-specific
workflows.

### Step 1: Install WSL2

Open **PowerShell as Administrator**:

``` powershell
wsl --install
```

Restart Windows if requested.

The default installation normally includes Ubuntu. To see installed
distributions:

``` powershell
wsl --list --verbose
```

If Ubuntu is not installed, install it:

``` powershell
wsl --install -d Ubuntu
```

Launch Ubuntu from the Start menu. On the first launch, create a Linux
username and password.

### Step 2: Update Ubuntu

Inside the Ubuntu terminal:

``` bash
sudo apt update
sudo apt upgrade -y
```

Install common development tools:

``` bash
sudo apt install -y curl git unzip build-essential
```

Check Git:

``` bash
git --version
```

### Step 3: Install OpenCode inside WSL

Use the installer command documented for the OpenCode version you are
installing. For the current V2 CLI, the official documentation lists:

``` bash
curl -fsSL https://opencode.ai/v2/install | bash
```

Close and reopen the WSL terminal if necessary, then verify:

``` bash
opencode --version
```

If you intentionally follow an older V1 guide, use that version's
official installation instructions instead. Do not run multiple
installers just to make the command work.

### Step 4: Open a Windows project from WSL

Windows drives are mounted under `/mnt`.

For example, a Windows project at:

``` text
C:\Users\YourName\Projects\demo
```

is available in WSL at:

``` bash
/mnt/c/Users/YourName/Projects/demo
```

Navigate to it:

``` bash
cd /mnt/c/Users/YourName/Projects/demo
```

Start OpenCode:

``` bash
opencode
```

### Step 5: Recommended WSL project location

For projects that you mainly build and run inside Linux, store them in
the Linux filesystem:

``` bash
mkdir -p ~/Projects
cd ~/Projects
```

This usually gives better filesystem performance than repeatedly working
across the Windows/Linux filesystem boundary.

For projects that must be accessed directly by Windows applications, you
can keep them under `/mnt/c/Users/...`.

### Optional: Use Desktop with a WSL server

If you want the Desktop app as a client but want the project and agent
process to run in WSL, follow the current Windows/WSL documentation:

<https://docs.dev.opencode.ai/docs/windows-wsl/>

The general pattern is to start the server in WSL and connect the
Desktop client to its local address. If you expose a server beyond
localhost, configure authentication and firewall restrictions. Do not
expose an unauthenticated coding-agent server to your network or the
public internet.

------------------------------------------------------------------------

## 7. Connect an AI provider and choose a model

OpenCode supports multiple model providers. You can connect a provider
interactively rather than manually writing API keys into a project
configuration file.

### Step 1: Open the connection menu

Start OpenCode:

``` powershell
opencode
```

or, in WSL:

``` bash
opencode
```

Inside the OpenCode session, enter:

``` text
/connect
```

### Step 2: Select a provider

Choose a provider from the list. Depending on the provider, you may be
asked to:

-   Sign in through a browser.
-   Complete a device authorization flow.
-   Paste an API key.
-   Select an account or organization.

Follow the prompts shown by OpenCode and the provider.

### Step 3: Select a model

Inside OpenCode, run:

``` text
/models
```

Choose a model that is available to your connected provider.

### Provider considerations

  -----------------------------------------------------------------------
  Provider type                       What to check
  ----------------------------------- -----------------------------------
  OpenCode-hosted options             Current availability, free-tier
                                      limits, and billing

  OpenAI                              Supported sign-in method, model
                                      availability, and plan/API billing

  Anthropic                           API access, account credits, and
                                      model availability

  Google                              Gemini access, API key or supported
                                      authentication

  OpenRouter                          Provider credits, model pricing,
                                      and routing

  Local model provider                Local runtime, model size, memory,
                                      and context length
  -----------------------------------------------------------------------

The provider list and model names can change. Use `/connect` and
`/models` to see what is currently available rather than copying an old
model identifier from a tutorial.

### API key safety

-   Never paste API keys into source code.
-   Do not commit API keys to Git.
-   Do not put secrets in `AGENTS.md`.
-   Do not share screenshots or logs that reveal credentials.
-   Prefer OpenCode's provider authentication flow.
-   If a key is exposed, revoke or rotate it with the provider.

------------------------------------------------------------------------

## 8. Open your first project

Open a project folder before starting OpenCode.

### PowerShell

``` powershell
cd C:\Users\YourName\Projects\my-project
opencode
```

### WSL2

``` bash
cd ~/Projects/my-project
opencode
```

### Start with a clean project

If you want to test OpenCode without risking an existing project:

``` powershell
mkdir opencode-test
cd opencode-test
git init
opencode
```

In WSL:

``` bash
mkdir -p ~/Projects/opencode-test
cd ~/Projects/opencode-test
git init
opencode
```

### Example prompts

Once the session starts, try:

``` text
Explain the structure of this project. Do not modify any files.
```

``` text
Find potential bugs in the authentication module. Explain the issues before changing anything.
```

``` text
Add input validation to the registration form. Keep the existing architecture and explain the files you change.
```

``` text
Run the existing tests and summarize any failures. Do not modify the tests.
```

Start with read-only requests while you learn how the agent works.

------------------------------------------------------------------------

## 9. Initialize a project with AGENTS.md

`AGENTS.md` is a project instruction file. It tells the coding agent
about the project's architecture, conventions, commands, and
constraints.

Inside OpenCode, run:

``` text
/init
```

OpenCode analyzes the project and can create an `AGENTS.md` file in the
project root.

Review the generated file. Make sure it describes the actual project
rather than assuming the generated content is always correct.

### Example AGENTS.md

You can adapt this starter file:

``` markdown
# Project Instructions

## Project Overview
Briefly describe what this application does.

## Technology Stack
- Frontend:
- Backend:
- Database:
- Testing:

## Architecture
Explain the main folders and important modules.

## Coding Guidelines
- Follow the existing project structure.
- Reuse existing components and utilities.
- Avoid unnecessary dependencies.
- Keep functions small and readable.
- Handle errors explicitly.

## Development Commands
- Install:
- Run:
- Test:
- Build:

## Important Rules
- Do not expose secrets or credentials.
- Do not delete existing functionality without approval.
- Do not change database schemas without explaining the migration.
- Run relevant tests after making changes.
```

Commit this file if it contains project-wide instructions that your team
should share. Keep personal secrets and machine-specific values out of
it.

------------------------------------------------------------------------

## 10. Essential OpenCode commands

Commands are entered inside the OpenCode session unless otherwise noted.

  Command       Purpose
  ------------- ------------------------------------------------------------
  `/connect`    Connect or manage a provider
  `/models`     View and select available models
  `/init`       Analyze the project and create/update project instructions
  `/help`       View available help and commands
  `/undo`       Undo the most recent agent changes where supported
  `/redo`       Redo an undone change where supported
  `/new`        Start a new session
  `/sessions`   Browse or switch sessions where supported
  `/compact`    Compact the conversation context where supported
  `/details`    Inspect session or message details where supported

Available commands can vary by OpenCode version. Use `/help` in your
installed version for the authoritative list.

### Useful terminal commands

Run these in PowerShell or your shell, not as OpenCode slash commands:

``` powershell
opencode --version
opencode --help
```

To start OpenCode in a particular directory:

``` powershell
cd path\to\project
opencode
```

------------------------------------------------------------------------

## 11. Configure OpenCode

OpenCode supports JSON and JSONC configuration. JSONC allows comments
and trailing commas.

### Project-level configuration

Create this file in your project root:

``` text
opencode.jsonc
```

Example:

``` jsonc
{
  "$schema": "https://opencode.ai/config.json"
}
```

You can add settings supported by your installed version. For example,
to set a default model, use the exact provider/model identifier shown by
`/models`:

``` jsonc
{
  "$schema": "https://opencode.ai/config.json",
  "model": "provider/model-id"
}
```

Replace `provider/model-id` with a real model identifier available to
your account. It is a placeholder, not a model you can select as
written.

### Where configuration lives

The exact paths depend on the operating system and OpenCode version.
Common locations include:

-   Windows user configuration: `%USERPROFILE%\.config\opencode\`
-   WSL/Linux user configuration: `~/.config/opencode/`
-   Project configuration: the project root, such as `opencode.json` or
    `opencode.jsonc`
-   Windows machine-wide configuration: `%ProgramData%\opencode\`

Check the current configuration documentation for precedence and any
version-specific path changes:

<https://opencode.ai/docs/config>

### Open the Windows user config folder

In PowerShell:

``` powershell
explorer "$env:USERPROFILE\.config\opencode"
```

If the folder does not exist yet, create it:

``` powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.config\opencode"
```

### Open the WSL config folder

``` bash
mkdir -p ~/.config/opencode
cd ~/.config/opencode
```

Do not assume Windows and WSL installations share the same configuration
or provider credentials. They may use separate home directories and
separate authentication stores.

------------------------------------------------------------------------

## 12. Permissions and safe usage

An AI coding agent may read files, edit code, and run commands. Treat
its actions like changes made by another developer: review them.

### Recommended habits

1.  Use Git before asking the agent to make significant changes.
2.  Ask it to explain a proposed change before implementing high-impact
    work.
3.  Review diffs before accepting or committing changes.
4.  Be cautious with shell commands that delete files, modify system
    settings, or install software.
5.  Keep `.env`, credentials, private keys, and production data out of
    prompts.
6.  Do not give an agent unrestricted access to sensitive folders.
7.  Check the permissions configuration supported by your installed
    version.

### Example safe prompt

``` text
Inspect the project and propose a plan first.
Do not edit files or run destructive commands until I approve the plan.
```

### Example change-review prompt

``` text
Summarize every file you changed, explain why it changed,
and identify any tests that still need to be run.
```

OpenCode supports configurable permissions. Read the current
documentation before setting a broad allow rule:

<https://opencode.ai/docs/permissions>

------------------------------------------------------------------------

## 13. VS Code workflow

You can use OpenCode alongside VS Code.

### Step 1: Install VS Code

Download it from:

<https://code.visualstudio.com/>

### Step 2: Open your project

PowerShell:

``` powershell
cd C:\Users\YourName\Projects\my-project
code .
```

WSL:

``` bash
cd ~/Projects/my-project
code .
```

For WSL projects, install the Microsoft **WSL** extension in VS Code if
prompted, and open the folder in the WSL environment.

### Step 3: Open a terminal

In VS Code:

1.  Open **Terminal**.
2.  Select **New Terminal**.
3.  Navigate to your project directory if necessary.
4.  Run:

``` bash
opencode
```

This gives you an editor for inspecting files and a terminal session for
interacting with OpenCode.

### Recommended workflow

-   Keep the project open in VS Code.
-   Run OpenCode from the integrated terminal.
-   Ask for one focused task at a time.
-   Review changed files in the editor or Source Control panel.
-   Run tests and inspect the Git diff before committing.

------------------------------------------------------------------------

## 14. Git and project workflow

Git is strongly recommended when using an AI coding agent.

### Create a checkpoint before changes

``` bash
git status
git add .
git commit -m "Checkpoint before OpenCode changes"
```

If the project is not already a Git repository:

``` bash
git init
```

### Ask OpenCode to make a focused change

For example:

``` text
Add pagination to the products endpoint.
First inspect the existing API structure.
Follow the current naming conventions.
Do not change unrelated files.
Add or update tests.
```

### Review the result

``` bash
git status
git diff
```

Run your project's tests, then commit only after reviewing the changes:

``` bash
git add .
git commit -m "Add product pagination"
```

Never rely only on an agent's statement that a task is complete. Verify
the code and run the relevant checks yourself.

------------------------------------------------------------------------

## 15. MCP servers, agents, and skills

OpenCode can be extended with additional tools and reusable workflows.

### MCP servers

Model Context Protocol (MCP) servers can provide an agent with access to
external tools and services.

Examples include:

-   Documentation search.
-   Database tools.
-   Browser automation.
-   Issue trackers.
-   Other developer services.

Only connect MCP servers you trust. Review what data and actions they
can access before enabling them.

Official documentation:

<https://opencode.ai/docs/mcp-servers>

### Custom agents

You can configure specialized agents for different tasks, such as:

-   Code review.
-   Debugging.
-   Test generation.
-   Documentation.
-   Architecture analysis.

Read the current agents documentation:

<https://opencode.ai/docs/agents>

### Skills

Skills provide reusable instructions for particular workflows. A skill
is typically described in a `SKILL.md` file.

Use skills from trusted sources and inspect their instructions before
relying on them.

Official documentation:

<https://opencode.ai/docs/skills>

------------------------------------------------------------------------

## 16. Troubleshooting

### Problem 1: `opencode` is not recognized

Example:

``` text
'opencode' is not recognized as an internal or external command
```

**Fix:**

1.  Confirm the installation completed.
2.  If using the standalone binary, confirm its folder is in `PATH`.
3.  Close and reopen PowerShell.
4.  Run:

``` powershell
where.exe opencode
```

5.  If using npm, check:

``` powershell
npm list -g --depth=0
npm prefix -g
```

Make sure npm's global executable directory is available in `PATH`.

### Problem 2: npm installation fails

Check Node.js and npm:

``` powershell
node --version
npm --version
```

Update to a supported Node.js LTS release if necessary. Then retry the
package command from the current official documentation:

``` powershell
npm install -g @opencode/cli
```

If it still fails, read the full error output. Do not randomly install
multiple OpenCode packages.

### Problem 3: OpenCode starts but no model is available

Inside OpenCode:

``` text
/connect
```

Complete provider authentication, then:

``` text
/models
```

Confirm that the provider account has access to at least one model.

### Problem 4: API authentication fails

Check:

-   Whether you selected the correct provider.
-   Whether the key was copied completely.
-   Whether the key is active and has sufficient credits or billing
    enabled.
-   Whether the provider requires browser/device sign-in instead of an
    API key.

If a key has been exposed, revoke it and create a new one.

### Problem 5: WSL cannot find OpenCode

Inside Ubuntu:

``` bash
which opencode
opencode --version
```

If it is missing, verify the installation output and follow the
installer instructions for the version you intend to use. Open a new WSL
terminal after installation.

### Problem 6: WSL cannot access a Windows project

Check that the Windows drive is mounted:

``` bash
ls /mnt/c/Users
```

Then navigate to the correct user and project folder:

``` bash
cd /mnt/c/Users/YourName/Projects/my-project
```

If the drive is not mounted, inspect your WSL configuration and Windows
drive-mount settings.

### Problem 7: Permission denied in WSL

Check file ownership and permissions:

``` bash
ls -la
```

Avoid using `sudo` to run OpenCode or to edit an entire project unless
you have a specific reason. Fix ownership only when you understand why
it is wrong.

### Problem 8: OpenCode is using the wrong model

Inside the session:

``` text
/models
```

Select the intended model. Also check the project's `opencode.jsonc` and
your global configuration for a default model setting.

### Problem 9: Changes are not appearing in VS Code

-   Confirm VS Code and OpenCode are working in the same project
    directory.
-   In WSL, check whether VS Code opened the WSL folder or a separate
    Windows copy.
-   Check `git status` and the file path.
-   Reload the editor window if necessary.

### Problem 10: Unsure which version is installed

Run:

``` powershell
opencode --version
opencode --help
```

Then compare the output with the official documentation for that
version. Avoid mixing V1 and V2 installation instructions.

------------------------------------------------------------------------

## 17. Recommended setup checklist

Use this checklist to confirm that your environment is ready.

### Installation

-   [ ] Windows is updated.
-   [ ] Windows Terminal or PowerShell is available.
-   [ ] Git is installed.
-   [ ] OpenCode Desktop or CLI is installed.
-   [ ] `opencode --version` works.
-   [ ] You know whether you installed the current CLI or an older
    version.

### AI provider

-   [ ] A provider is connected using `/connect`.
-   [ ] At least one model is available through `/models`.
-   [ ] You understand the provider's billing or free-tier limits.
-   [ ] API keys and credentials are not stored in source code.

### Project

-   [ ] VS Code is installed (if you use it).
-   [ ] Your project opens in the correct environment.
-   [ ] Git is initialized and a checkpoint exists.
-   [ ] OpenCode can inspect the project.
-   [ ] `/init` has generated or updated `AGENTS.md`.
-   [ ] You have reviewed the project instructions.

### Safe workflow

-   [ ] You review changes before committing.
-   [ ] You run tests after code changes.
-   [ ] You do not expose production credentials.
-   [ ] You understand and review agent permissions.

------------------------------------------------------------------------

## 18. Useful official links

  ---------------------------------------------------------------------------------------
  Resource                            Link
  ----------------------------------- ---------------------------------------------------
  OpenCode homepage                   <https://opencode.ai/>

  Official documentation              <https://opencode.ai/docs>

  Download page                       <https://opencode.ai/download>

  Windows / WSL documentation         <https://docs.dev.opencode.ai/docs/windows-wsl/>

  Configuration                       <https://opencode.ai/docs/config>

  Providers                           <https://opencode.ai/docs/providers>

  Permissions                         <https://opencode.ai/docs/permissions>

  MCP servers                         <https://opencode.ai/docs/mcp-servers>

  Agents                              <https://opencode.ai/docs/agents>

  Skills                              <https://opencode.ai/docs/skills>

  Git for Windows                     <https://git-scm.com/download/win>

  Visual Studio Code                  <https://code.visualstudio.com/>

  Microsoft WSL installation          <https://learn.microsoft.com/windows/wsl/install>
  ---------------------------------------------------------------------------------------

------------------------------------------------------------------------

## Final recommendation

For a Windows development machine, choose one of these two setups:

**Simple setup** - OpenCode Desktop - VS Code - Git for Windows - A
connected AI provider

**Developer-focused setup** - WSL2 + Ubuntu - OpenCode CLI installed
inside WSL - VS Code with the WSL extension - Git inside WSL - A
connected AI provider

The developer-focused setup is especially useful when your projects rely
on Linux tooling. Keep your project, terminal, Git environment, and
OpenCode process aligned so that you do not accidentally edit one copy
of a project while running commands in another.

**Start small:** open a test repository, connect a model, ask OpenCode
to explain the project without editing it, and then try one small code
change. Review the diff and run the tests before moving on to larger
tasks.
