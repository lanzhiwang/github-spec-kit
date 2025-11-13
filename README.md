<div align="center">
    <img src="./media/logo_small.webp" alt="Spec Kit Logo"/>
    <h1>🌱 Spec Kit</h1>
    <h3><em>Build high-quality software faster.</em></h3>
</div>

<p align="center">
    <strong>An open source toolkit that allows you to focus on product scenarios and predictable outcomes instead of vibe coding every piece from scratch.</strong>
</p>

<p align="center">
    <a href="https://github.com/github/spec-kit/actions/workflows/release.yml"><img src="https://github.com/github/spec-kit/actions/workflows/release.yml/badge.svg" alt="Release"/></a>
    <a href="https://github.com/github/spec-kit/stargazers"><img src="https://img.shields.io/github/stars/github/spec-kit?style=social" alt="GitHub stars"/></a>
    <a href="https://github.com/github/spec-kit/blob/main/LICENSE"><img src="https://img.shields.io/github/license/github/spec-kit" alt="License"/></a>
    <a href="https://github.github.io/spec-kit/"><img src="https://img.shields.io/badge/docs-GitHub_Pages-blue" alt="Documentation"/></a>
</p>

---

## Table of Contents

- [🤔 What is Spec-Driven Development?](#-what-is-spec-driven-development)
- [⚡ Get Started](#-get-started)
- [📽️ Video Overview](#️-video-overview)
- [🤖 Supported AI Agents](#-supported-ai-agents)
- [🔧 Specify CLI Reference](#-specify-cli-reference)
- [📚 Core Philosophy](#-core-philosophy)
- [🌟 Development Phases](#-development-phases)
- [🎯 Experimental Goals](#-experimental-goals)
- [🔧 Prerequisites](#-prerequisites)
- [📖 Learn More](#-learn-more)
- [📋 Detailed Process](#-detailed-process)
- [🔍 Troubleshooting](#-troubleshooting)
- [👥 Maintainers](#-maintainers)
- [💬 Support](#-support)
- [🙏 Acknowledgements](#-acknowledgements)
- [📄 License](#-license)

## 🤔 What is Spec-Driven Development?

Spec-Driven Development **flips the script** on traditional software development. For decades, code has been king — specifications were just scaffolding we built and discarded once the "real work" of coding began. Spec-Driven Development changes this: **specifications become executable**, directly generating working implementations rather than just guiding them.

## ⚡ Get Started

### 1. Install Specify CLI

Choose your preferred installation method:

#### Option 1: Persistent Installation (Recommended)

Install once and use everywhere:

```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
```

Then use the tool directly:

```bash
specify init <PROJECT_NAME>
specify check
```

To upgrade specify run:

```bash
uv tool install specify-cli --force --from git+https://github.com/github/spec-kit.git
```

#### Option 2: One-time Usage

Run directly without installing:

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init <PROJECT_NAME>
```

**Benefits of persistent installation:**

- Tool stays installed and available in PATH
- No need to create shell aliases
- Better tool management with `uv tool list`, `uv tool upgrade`, `uv tool uninstall`
- Cleaner shell configuration

### 2. Establish project principles

Launch your AI assistant in the project directory. The `/speckit.*` commands are available in the assistant.

Use the **`/speckit.constitution`** command to create your project's governing principles and development guidelines that will guide all subsequent development.

```bash
/speckit.constitution Create principles focused on code quality, testing standards, user experience consistency, and performance requirements
```

### 3. Create the spec

Use the **`/speckit.specify`** command to describe what you want to build. Focus on the **what** and **why**, not the tech stack.

```bash
/speckit.specify Build an application that can help me organize my photos in separate photo albums. Albums are grouped by date and can be re-organized by dragging and dropping on the main page. Albums are never in other nested albums. Within each album, photos are previewed in a tile-like interface.
```

### 4. Create a technical implementation plan

Use the **`/speckit.plan`** command to provide your tech stack and architecture choices.

```bash
/speckit.plan The application uses Vite with minimal number of libraries. Use vanilla HTML, CSS, and JavaScript as much as possible. Images are not uploaded anywhere and metadata is stored in a local SQLite database.
```

### 5. Break down into tasks

Use **`/speckit.tasks`** to create an actionable task list from your implementation plan.

```bash
/speckit.tasks
```

### 6. Execute implementation

Use **`/speckit.implement`** to execute all tasks and build your feature according to the plan.

```bash
/speckit.implement
```

For detailed step-by-step instructions, see our [comprehensive guide](./spec-driven.md).

## 📽️ Video Overview

Want to see Spec Kit in action? Watch our [video overview](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)!

[![Spec Kit video header](/media/spec-kit-video-header.jpg)](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)

## 🤖 Supported AI Agents

| Agent                                                     | Support | Notes                                             |
|-----------------------------------------------------------|---------|---------------------------------------------------|
| [Claude Code](https://www.anthropic.com/claude-code)      | ✅ |                                                   |
| [GitHub Copilot](https://code.visualstudio.com/)          | ✅ |                                                   |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | ✅ |                                                   |
| [Cursor](https://cursor.sh/)                              | ✅ |                                                   |
| [Qwen Code](https://github.com/QwenLM/qwen-code)          | ✅ |                                                   |
| [opencode](https://opencode.ai/)                          | ✅ |                                                   |
| [Windsurf](https://windsurf.com/)                         | ✅ |                                                   |
| [Kilo Code](https://github.com/Kilo-Org/kilocode)         | ✅ |                                                   |
| [Auggie CLI](https://docs.augmentcode.com/cli/overview)   | ✅ |                                                   |
| [CodeBuddy CLI](https://www.codebuddy.ai/cli)             | ✅ |                                                   |
| [Roo Code](https://roocode.com/)                          | ✅ |                                                   |
| [Codex CLI](https://github.com/openai/codex)              | ✅ |                                                   |
| [Amazon Q Developer CLI](https://aws.amazon.com/developer/learning/q-developer-cli/) | ⚠️ | Amazon Q Developer CLI [does not support](https://github.com/aws/amazon-q-developer-cli/issues/3064) custom arguments for slash commands. |
| [Amp](https://ampcode.com/) | ✅ | |

## 🔧 Specify CLI Reference

The `specify` command supports the following options:

### Commands

| Command     | Description                                                    |
|-------------|----------------------------------------------------------------|
| `init`      | Initialize a new Specify project from the latest template      |
| `check`     | Check for installed tools (`git`, `claude`, `gemini`, `code`/`code-insiders`, `cursor-agent`, `windsurf`, `qwen`, `opencode`, `codex`) |

### `specify init` Arguments & Options

| Argument/Option        | Type     | Description                                                                  |
|------------------------|----------|------------------------------------------------------------------------------|
| `<project-name>`       | Argument | Name for your new project directory (optional if using `--here`, or use `.` for current directory) |
| `--ai`                 | Option   | AI assistant to use: `claude`, `gemini`, `copilot`, `cursor-agent`, `qwen`, `opencode`, `codex`, `windsurf`, `kilocode`, `auggie`, `roo`, `codebuddy`, `amp`, or `q` |
| `--script`             | Option   | Script variant to use: `sh` (bash/zsh) or `ps` (PowerShell)                 |
| `--ignore-agent-tools` | Flag     | Skip checks for AI agent tools like Claude Code                             |
| `--no-git`             | Flag     | Skip git repository initialization                                          |
| `--here`               | Flag     | Initialize project in the current directory instead of creating a new one   |
| `--force`              | Flag     | Force merge/overwrite when initializing in current directory (skip confirmation) |
| `--skip-tls`           | Flag     | Skip SSL/TLS verification (not recommended)                                 |
| `--debug`              | Flag     | Enable detailed debug output for troubleshooting                            |
| `--github-token`       | Option   | GitHub token for API requests (or set GH_TOKEN/GITHUB_TOKEN env variable)  |

### Examples

```bash
# Basic project initialization
specify init my-project

# Initialize with specific AI assistant
specify init my-project --ai claude

# Initialize with Cursor support
specify init my-project --ai cursor-agent

# Initialize with Windsurf support
specify init my-project --ai windsurf

# Initialize with Amp support
specify init my-project --ai amp

# Initialize with PowerShell scripts (Windows/cross-platform)
specify init my-project --ai copilot --script ps

# Initialize in current directory
specify init . --ai copilot
# or use the --here flag
specify init --here --ai copilot

# Force merge into current (non-empty) directory without confirmation
specify init . --force --ai copilot
# or 
specify init --here --force --ai copilot

# Skip git initialization
specify init my-project --ai gemini --no-git

# Enable debug output for troubleshooting
specify init my-project --ai claude --debug

# Use GitHub token for API requests (helpful for corporate environments)
specify init my-project --ai claude --github-token ghp_your_token_here

# Check system requirements
specify check
```

### Available Slash Commands

After running `specify init`, your AI coding agent will have access to these slash commands for structured development:

#### Core Commands

Essential commands for the Spec-Driven Development workflow:

| Command                  | Description                                                           |
|--------------------------|-----------------------------------------------------------------------|
| `/speckit.constitution`  | Create or update project governing principles and development guidelines |
| `/speckit.specify`       | Define what you want to build (requirements and user stories)        |
| `/speckit.plan`          | Create technical implementation plans with your chosen tech stack     |
| `/speckit.tasks`         | Generate actionable task lists for implementation                     |
| `/speckit.implement`     | Execute all tasks to build the feature according to the plan         |

#### Optional Commands

Additional commands for enhanced quality and validation:

| Command              | Description                                                           |
|----------------------|-----------------------------------------------------------------------|
| `/speckit.clarify`   | Clarify underspecified areas (recommended before `/speckit.plan`; formerly `/quizme`) |
| `/speckit.analyze`   | Cross-artifact consistency & coverage analysis (run after `/speckit.tasks`, before `/speckit.implement`) |
| `/speckit.checklist` | Generate custom quality checklists that validate requirements completeness, clarity, and consistency (like "unit tests for English") |

### Environment Variables

| Variable         | Description                                                                                    |
|------------------|------------------------------------------------------------------------------------------------|
| `SPECIFY_FEATURE` | Override feature detection for non-Git repositories. Set to the feature directory name (e.g., `001-photo-albums`) to work on a specific feature when not using Git branches.<br/>**Must be set in the context of the agent you're working with prior to using `/speckit.plan` or follow-up commands. |

## 📚 Core Philosophy

Spec-Driven Development is a structured process that emphasizes:

- **Intent-driven development** where specifications define the "*what*" before the "*how*"
- **Rich specification creation** using guardrails and organizational principles
- **Multi-step refinement** rather than one-shot code generation from prompts
- **Heavy reliance** on advanced AI model capabilities for specification interpretation

## 🌟 Development Phases

| Phase | Focus | Key Activities |
|-------|-------|----------------|
| **0-to-1 Development** ("Greenfield") | Generate from scratch | <ul><li>Start with high-level requirements</li><li>Generate specifications</li><li>Plan implementation steps</li><li>Build production-ready applications</li></ul> |
| **Creative Exploration** | Parallel implementations | <ul><li>Explore diverse solutions</li><li>Support multiple technology stacks & architectures</li><li>Experiment with UX patterns</li></ul> |
| **Iterative Enhancement** ("Brownfield") | Brownfield modernization | <ul><li>Add features iteratively</li><li>Modernize legacy systems</li><li>Adapt processes</li></ul> |

## 🎯 Experimental Goals

Our research and experimentation focus on:

### Technology independence

- Create applications using diverse technology stacks
- Validate the hypothesis that Spec-Driven Development is a process not tied to specific technologies, programming languages, or frameworks

### Enterprise constraints

- Demonstrate mission-critical application development
- Incorporate organizational constraints (cloud providers, tech stacks, engineering practices)
- Support enterprise design systems and compliance requirements

### User-centric development

- Build applications for different user cohorts and preferences
- Support various development approaches (from vibe-coding to AI-native development)

### Creative & iterative processes

- Validate the concept of parallel implementation exploration
- Provide robust iterative feature development workflows
- Extend processes to handle upgrades and modernization tasks

## 🔧 Prerequisites

- **Linux/macOS/Windows**
- [Supported](#-supported-ai-agents) AI coding agent.
- [uv](https://docs.astral.sh/uv/) for package management
- [Python 3.11+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)

If you encounter issues with an agent, please open an issue so we can refine the integration.

## 📖 Learn More

- **[Complete Spec-Driven Development Methodology](./spec-driven.md)** - Deep dive into the full process
- **[Detailed Walkthrough](#-detailed-process)** - Step-by-step implementation guide

---

## 📋 Detailed Process

<details>
<summary>Click to expand the detailed step-by-step walkthrough</summary>

You can use the Specify CLI to bootstrap your project, which will bring in the required artifacts in your environment. Run:

```bash
specify init <project_name>
```

Or initialize in the current directory:

```bash
specify init .
# or use the --here flag
specify init --here
# Skip confirmation when the directory already has files
specify init . --force
# or
specify init --here --force
```

![Specify CLI bootstrapping a new project in the terminal](./media/specify_cli.gif)

You will be prompted to select the AI agent you are using. You can also proactively specify it directly in the terminal:

```bash
specify init <project_name> --ai claude
specify init <project_name> --ai gemini
specify init <project_name> --ai copilot

# Or in current directory:
specify init . --ai claude
specify init . --ai codex

# or use --here flag
specify init --here --ai claude
specify init --here --ai codex

# Force merge into a non-empty current directory
specify init . --force --ai claude

# or
specify init --here --force --ai claude
```

The CLI will check if you have Claude Code, Gemini CLI, Cursor CLI, Qwen CLI, opencode, Codex CLI, or Amazon Q Developer CLI installed. If you do not, or you prefer to get the templates without checking for the right tools, use `--ignore-agent-tools` with your command:

```bash
specify init <project_name> --ai claude --ignore-agent-tools
```

### **STEP 1:** Establish project principles
步骤 1: 确立项目原则

Go to the project folder and run your AI agent. In our example, we're using `claude`.
进入项目文件夹并运行你的 AI 代理. 在我们的示例中, 我们使用的是 claude.

![Bootstrapping Claude Code environment](./media/bootstrap-claude-code.gif)

You will know that things are configured correctly if you see the `/speckit.constitution`, `/speckit.specify`, `/speckit.plan`, `/speckit.tasks`, and `/speckit.implement` commands available.
如果看到 /speckit.constitution, /speckit.specify, /speckit.plan, /speckit.tasks, 和 /speckit.implement 命令可用. 说明您的配置是正确的.

The first step should be establishing your project's governing principles using the `/speckit.constitution` command. This helps ensure consistent decision-making throughout all subsequent development phases:
第一步应该是使用 /speckit.constitution 命令建立项目的管理原则. 这有助于确保在后续所有开发阶段做出一致的决策:

```text
/speckit.constitution Create principles focused on code quality, testing standards, user experience consistency, and performance requirements. Include governance for how these principles should guide technical decisions and implementation choices.

制定以代码质量、测试标准、用户体验一致性和性能要求为核心的原则. 并明确这些原则应如何指导技术决策和实施方案的选择.
```

This step creates or updates the `.specify/memory/constitution.md` file with your project's foundational guidelines that the AI agent will reference during specification, planning, and implementation phases.
此步骤创建或更新 .specify/memory/constitution.md 文件, 其中包含 AI 代理在规范、规划和实施阶段将参考的项目基础指南.

### **STEP 2:** Create project specifications
步骤 2: 创建项目规范

With your project principles established, you can now create the functional specifications. Use the `/speckit.specify` command and then provide the concrete requirements for the project you want to develop.
项目原则确定后, 即可创建功能规格说明. 使用 /speckit.specify 命令, 然后提供您要开发的项目的具体需求.

>[!IMPORTANT]
>Be as explicit as possible about *what* you are trying to build and *why*. **Do not focus on the tech stack at this point**.
>[重要]请尽可能详细地说明您要构建什么以及为什么. 现阶段不要关注技术栈.

An example prompt:

```text
Develop Taskify, a team productivity platform. It should allow users to create projects, add team members,
assign tasks, comment and move tasks between boards in Kanban style. In this initial phase for this feature,
let's call it "Create Taskify," let's have multiple users but the users will be declared ahead of time, predefined.
I want five users in two different categories, one product manager and four engineers. Let's create three
different sample projects. Let's have the standard Kanban columns for the status of each task, such as "To Do,"
"In Progress," "In Review," and "Done." There will be no login for this application as this is just the very
first testing thing to ensure that our basic features are set up. For each task in the UI for a task card,
you should be able to change the current status of the task between the different columns in the Kanban work board.
You should be able to leave an unlimited number of comments for a particular card. You should be able to, from that task
card, assign one of the valid users. When you first launch Taskify, it's going to give you a list of the five users to pick
from. There will be no password required. When you click on a user, you go into the main view, which displays the list of
projects. When you click on a project, you open the Kanban board for that project. You're going to see the columns.
You'll be able to drag and drop cards back and forth between different columns. You will see any cards that are
assigned to you, the currently logged in user, in a different color from all the other ones, so you can quickly
see yours. You can edit any comments that you make, but you can't edit comments that other people made. You can
delete any comments that you made, but you can't delete comments anybody else made.
开发 Taskify, 一个团队生产力平台. 它应该允许用户创建项目、添加团队成员、
分配任务、评论以及以看板方式在看板之间移动任务. 在这个功能的初始阶段,
我们暂且称之为"创建 Taskify", 允许多个用户, 但这些用户将预先定义.
我希望有五个用户, 分为两个不同的类别: 一个产品经理和四个工程师. 我们创建三个
不同的示例项目. 每个任务的状态都使用标准的看板列, 例如"待办"、"进行中"、"审核中"和"已完成".
此应用程序无需登录, 因为它只是一个初步测试, 旨在确保我们的基本功能已设置完毕. 在任务卡片的 UI 中,
用户应该能够在看板工作板的不同列之间更改任务的当前状态.
用户应该能够为特定卡片留下无限数量的评论. 用户应该能够从该任务
卡片中分配一个有效的用户. 首次启动 Taskify 时, 系统会显示五个可供选择的用户列表. 无需密码.
点击用户后, 即可进入主视图, 其中显示项目列表. 点击项目后, 即可打开该项目的看板. 您将看到各个列.
您可以将卡片拖放到不同的列中. 分配给您(当前登录用户)的卡片会以与其他卡片不同的颜色显示, 方便您快速找到自己的卡片.
您可以编辑自己发表的评论, 但无法编辑其他用户发表的评论. 您可以删除自己发表的评论, 但无法删除其他用户发表的评论.
```

After this prompt is entered, you should see Claude Code kick off the planning and spec drafting process. Claude Code will also trigger some of the built-in scripts to set up the repository.
输入此提示后, 您应该会看到 Claude Code 启动规划和规范起草流程. Claude Code 还会触发一些内置脚本来设置存储库.

Once this step is completed, you should have a new branch created (e.g., `001-create-taskify`), as well as a new specification in the `specs/001-create-taskify` directory.
完成此步骤后, 您应该会创建一个新分支(例如, 001-create-taskify), 以及在 specs/001-create-taskify 目录中创建一个新规范.

The produced specification should contain a set of user stories and functional requirements, as defined in the template.
生成的规范应包含模板中定义的一系列用户故事和功能需求.

At this stage, your project folder contents should resemble the following:
此时, 您的项目文件夹内容应类似于以下内容:

```text
└── .specify
    ├── memory
    │  └── constitution.md
    ├── scripts
    │  ├── check-prerequisites.sh
    │  ├── common.sh
    │  ├── create-new-feature.sh
    │  ├── setup-plan.sh
    │  └── update-claude-md.sh
    ├── specs
    │  └── 001-create-taskify
    │      └── spec.md
    └── templates
        ├── plan-template.md
        ├── spec-template.md
        └── tasks-template.md
```

### **STEP 3:** Functional specification clarification (required before planning)
步骤 3: 功能规格说明(规划前需要)

With the baseline specification created, you can go ahead and clarify any of the requirements that were not captured properly within the first shot attempt.
有了基准规范, 就可以着手澄清第一次尝试中未正确捕捉到的任何要求.

You should run the structured clarification workflow **before** creating a technical plan to reduce rework downstream.
在制定技术方案之前, 您应该运行结构化澄清工作流程, 以减少后续返工.

Preferred order:

1. Use `/speckit.clarify` (structured) – sequential, coverage-based questioning that records answers in a Clarifications section.
   使用 /speckit.clarify (结构化) – 按顺序、基于覆盖率的提问, 将答案记录在"澄清"部分.

2. Optionally follow up with ad-hoc free-form refinement if something still feels vague.
   如果仍有模糊之处, 可以酌情进行自由形式的补充完善.

If you intentionally want to skip clarification (e.g., spike or exploratory prototype), explicitly state that so the agent doesn't block on missing clarifications.
如果您有意跳过澄清(例如, 探索性原型或实验性原型), 请明确说明, 以免代理因缺少澄清而受阻.

Example free-form refinement prompt (after `/speckit.clarify` if still needed):
示例自由格式优化提示(如果仍然需要, 可在 /speckit.clarify 之后执行):

```text
For each sample project or project that you create there should be a variable number of tasks between 5 and 15
tasks for each one randomly distributed into different states of completion. Make sure that there's at least
one task in each stage of completion.
对于您创建的每个示例项目或项目, 应包含 5 到 15 个任务, 且任务数量不固定, 并随机分布在不同的完成状态.
请确保每个完成阶段至少包含一个任务.
```

You should also ask Claude Code to validate the **Review & Acceptance Checklist**, checking off the things that are validated/pass the requirements, and leave the ones that are not unchecked. The following prompt can be used:
您还应该请 Claude Code 验证 "审核与验收清单", 勾选已验证/符合要求的项目, 未验证的项目则保持未勾选状态. 可以使用以下提示:

```text
Read the review and acceptance checklist, and check off each item in the checklist if the feature spec meets the criteria. Leave it empty if it does not.
请阅读审核验收清单, 如果功能规格符合标准, 则勾选清单中的每一项; 如果不符合, 则留空.
```

It's important to use the interaction with Claude Code as an opportunity to clarify and ask questions around the specification - **do not treat its first attempt as final**.
重要的是要利用与 Claude Code 的互动机会来澄清和提出有关规范的问题 - 不要把他的第一次尝试视为最终版本.

### **STEP 4:** Generate a plan
步骤 4: 制定计划

You can now be specific about the tech stack and other technical requirements. You can use the `/speckit.plan` command that is built into the project template with a prompt like this:
现在您可以具体指定技术栈和其他技术要求. 您可以使用项目模板内置的 /speckit.plan 命令, 并输入如下提示:

```text
We are going to generate this using .NET Aspire, using Postgres as the database. The frontend should use
Blazor server with drag-and-drop task boards, real-time updates. There should be a REST API created with a projects API,
tasks API, and a notifications API.
我们将使用 .NET Aspire 构建此系统, 数据库采用 Postgres. 前端应使用 Blazor 服务器, 支持拖放式任务看板和实时更新.
此外, 还应创建一个 REST API, 包含项目 API、任务 API 和通知 API.
```

The output of this step will include a number of implementation detail documents, with your directory tree resembling this:
此步骤的输出将包含若干实现细节文档, 您的目录结构将类似于以下示例:

```text
.
├── CLAUDE.md
├── memory
│  └── constitution.md
├── scripts
│  ├── check-prerequisites.sh
│  ├── common.sh
│  ├── create-new-feature.sh
│  ├── setup-plan.sh
│  └── update-claude-md.sh
├── specs
│  └── 001-create-taskify
│      ├── contracts
│      │  ├── api-spec.json
│      │  └── signalr-spec.md
│      ├── data-model.md
│      ├── plan.md
│      ├── quickstart.md
│      ├── research.md
│      └── spec.md
└── templates
    ├── CLAUDE-template.md
    ├── plan-template.md
    ├── spec-template.md
    └── tasks-template.md
```

Check the `research.md` document to ensure that the right tech stack is used, based on your instructions. You can ask Claude Code to refine it if any of the components stand out, or even have it check the locally-installed version of the platform/framework you want to use (e.g., .NET).
请查看 research.md 文档, 确保根据您的指示使用了正确的技术栈. 如果其中任何组件存在问题, 您可以请 Claude Code 对其进行完善, 甚至可以让它检查您想要使用的平台/框架(例如 .NET)的本地安装版本.

Additionally, you might want to ask Claude Code to research details about the chosen tech stack if it's something that is rapidly changing (e.g., .NET Aspire, JS frameworks), with a prompt like this:
此外, 如果所选技术栈变化迅速(例如 .NET Aspire、JS 框架), 您可能需要请 Claude Code 研究一下相关细节, 例如这样问:

```text
I want you to go through the implementation plan and implementation details, looking for areas that could
benefit from additional research as .NET Aspire is a rapidly changing library. For those areas that you identify that
require further research, I want you to update the research document with additional details about the specific
versions that we are going to be using in this Taskify application and spawn parallel research tasks to clarify
any details using research from the web.
我希望你仔细阅读实施计划和实施细节, 找出可能需要进一步研究的领域, 因为 .NET Aspire 是一个快速发展的库.
对于你发现的需要进一步研究的领域, 我希望你更新研究文档, 添加更多关于我们将在此 Taskify 应用程序中使用的具体版本的信息, 并同时启动并行研究任务, 利用网络资源来澄清任何细节.
```

During this process, you might find that Claude Code gets stuck researching the wrong thing - you can help nudge it in the right direction with a prompt like this:
在这个过程中, 你可能会发现 Claude Code 一直在研究错误的内容 - 你可以用类似这样的提示来帮助他朝着正确的方向前进:

```text
I think we need to break this down into a series of steps. First, identify a list of tasks
that you would need to do during implementation that you're not sure of or would benefit
from further research. Write down a list of those tasks. And then for each one of these tasks,
I want you to spin up a separate research task so that the net results is we are researching
all of those very specific tasks in parallel. What I saw you doing was it looks like you were
researching .NET Aspire in general and I don't think that's gonna do much for us in this case.
That's way too untargeted research. The research needs to help you solve a specific targeted question.
我认为我们需要将这项工作分解成一系列步骤. 首先, 列出你在实施过程中需要完成但不确定或需要进一步研究的任务清单.
把这些任务写下来. 然后, 针对每个任务, 我希望你启动一个单独的研究任务, 这样我们就能并行地研究所有这些非常具体的任务.
我看到你似乎在研究 .NET Aspire 的总体情况, 但我认为这对我们目前的情况帮助不大.
这样的研究太笼统了. 研究需要帮助你解决一个具体的、有针对性的问题.
```

>[!NOTE]
>Claude Code might be over-eager and add components that you did not ask for. Ask it to clarify the rationale and the source of the change.
>[注意]Claude Code 可能过于积极, 添加一些你没有要求的组件. 请询问它以澄清更改的理由和来源.

### **STEP 5:** Have Claude Code validate the plan
步骤 5: 请 Claude Code 验证该计划

With the plan in place, you should have Claude Code run through it to make sure that there are no missing pieces. You can use a prompt like this:
计划制定完毕后, 你应该让 Claude Code 检查一遍, 确保没有遗漏任何环节. 你可以使用类似这样的提示:

```text
Now I want you to go and audit the implementation plan and the implementation detail files.
Read through it with an eye on determining whether or not there is a sequence of tasks that you need
to be doing that are obvious from reading this. Because I don't know if there's enough here. For example,
when I look at the core implementation, it would be useful to reference the appropriate places in the implementation
details where it can find the information as it walks through each step in the core implementation or in the refinement.
现在, 我希望你去审核实施计划和实施细节文件.
仔细阅读, 重点在于确定是否存在一系列你需要执行的任务, 这些任务从本文内容中显而易见.
因为我不确定这里的信息是否足够. 例如,
当我查看核心实现时, 如果能在实施细节中找到相应的参考点, 以便它在执行核心实现或细化过程中的每个步骤时都能找到所需信息, 那就很有帮助了.
```

This helps refine the implementation plan and helps you avoid potential blind spots that Claude Code missed in its planning cycle. Once the initial refinement pass is complete, ask Claude Code to go through the checklist once more before you can get to the implementation.
这有助于完善实施计划, 并帮助您避免 Claude Code 在规划阶段可能遗漏的潜在盲点. 初步完善完成后, 请 Claude Code 在您开始实施之前再次核对清单.

You can also ask Claude Code (if you have the [GitHub CLI](https://docs.github.com/en/github-cli/github-cli) installed) to go ahead and create a pull request from your current branch to `main` with a detailed description, to make sure that the effort is properly tracked.
您还可以请 Claude Code(如果您安装了 GitHub CLI )从您当前的分支向 main 创建一个拉取请求, 并附上详细的描述, 以确保这项工作得到正确的跟踪.

>[!NOTE]
>Before you have the agent implement it, it's also worth prompting Claude Code to cross-check the details to see if there are any over-engineered pieces (remember - it can be over-eager). If over-engineered components or decisions exist, you can ask Claude Code to resolve them. Ensure that Claude Code follows the [constitution](base/memory/constitution.md) as the foundational piece that it must adhere to when establishing the plan.
>[注意]在让代理执行之前, 最好先让 Claude Code 核对细节, 看看是否存在过度设计的部分(记住, 它可能会过于积极). 如果存在过度设计的组件或决策, 您可以要求 Claude Code 解决这些问题. 务必确保 Claude Code 在制定计划时, 始终以章程为根本原则.

### **STEP 6:** Generate task breakdown with /speckit.tasks
步骤 6: 使用 /speckit.tasks 生成任务分解

With the implementation plan validated, you can now break down the plan into specific, actionable tasks that can be executed in the correct order. Use the `/speckit.tasks` command to automatically generate a detailed task breakdown from your implementation plan:
实施计划验证通过后, 您可以将计划分解为具体的、可执行的任务, 并按正确的顺序执行. 使用 /speckit.tasks 命令可以根据您的实施计划自动生成详细的任务分解:

```text
/speckit.tasks
```

This step creates a `tasks.md` file in your feature specification directory that contains:
此步骤会在功能规范目录中创建一个名为 tasks.md 文件, 其中包含:

- **Task breakdown organized by user story** - Each user story becomes a separate implementation phase with its own set of tasks
  任务分解按用户故事组织 - 每个用户故事都成为一个独立的实现阶段, 包含其自身的一系列任务.

- **Dependency management** - Tasks are ordered to respect dependencies between components (e.g., models before services, services before endpoints)
  依赖关系管理 - 任务的顺序要遵循组件之间的依赖关系(例如, 模型在前, 服务在后, 端点在前).

- **Parallel execution markers** - Tasks that can run in parallel are marked with `[P]` to optimize development workflow
  并行执行标记 - 可以并行运行的任务用 [P] 标记, 以优化开发工作流程

- **File path specifications** - Each task includes the exact file paths where implementation should occur
  文件路径规范 - 每个任务都包含实施所需的确切文件路径.

- **Test-driven development structure** - If tests are requested, test tasks are included and ordered to be written before implementation
  测试驱动开发结构 - 如果需要测试, 则会包含测试任务, 并要求在实现之前编写测试.

- **Checkpoint validation** - Each user story phase includes checkpoints to validate independent functionality
  检查点验证 - 每个用户故事阶段都包含检查点, 用于验证独立功能.

The generated tasks.md provides a clear roadmap for the `/speckit.implement` command, ensuring systematic implementation that maintains code quality and allows for incremental delivery of user stories.
生成的 tasks.md 为 /speckit.implement 命令提供了清晰的路线图, 确保系统化的实现, 从而保持代码质量并允许逐步交付用户故事.

### **STEP 7:** Implementation
步骤 7: 实施

Once ready, use the `/speckit.implement` command to execute your implementation plan:
准备就绪后, 使用 /speckit.implement 命令执行您的实施计划:

```text
/speckit.implement
```

The `/speckit.implement` command will:
/speckit.implement 命令将执行以下操作:

- Validate that all prerequisites are in place (constitution, spec, plan, and tasks)
  确认所有先决条件均已到位(章程、规范、计划和任务)

- Parse the task breakdown from `tasks.md`
  解析 tasks.md 中的任务分解信息

- Execute tasks in the correct order, respecting dependencies and parallel execution markers
  按正确的顺序执行任务, 注意任务间的依赖关系和并行执行标记.

- Follow the TDD approach defined in your task plan
  遵循任务计划中定义的 TDD 方法

- Provide progress updates and handle errors appropriately
  及时汇报进度并妥善处理错误.

>[!IMPORTANT]
>The AI agent will execute local CLI commands (such as `dotnet`, `npm`, etc.) - make sure you have the required tools installed on your machine.
>[重要]AI 代理将执行本地 CLI 命令(例如 dotnet、npm 等) - 请确保您的计算机上已安装所需的工具.

Once the implementation is complete, test the application and resolve any runtime errors that may not be visible in CLI logs (e.g., browser console errors). You can copy and paste such errors back to your AI agent for resolution.
实现完成后, 请测试应用程序并解决任何可能不会在 CLI 日志中显示的运行时错误(例如, 浏览器控制台错误). 您可以将此类错误复制并粘贴回您的 AI 代理进行解决.

</details>

---

## 🔍 Troubleshooting

### Git Credential Manager on Linux

If you're having issues with Git authentication on Linux, you can install Git Credential Manager:

```bash
#!/usr/bin/env bash
set -e
echo "Downloading Git Credential Manager v2.6.1..."
wget https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.6.1/gcm-linux_amd64.2.6.1.deb
echo "Installing Git Credential Manager..."
sudo dpkg -i gcm-linux_amd64.2.6.1.deb
echo "Configuring Git to use GCM..."
git config --global credential.helper manager
echo "Cleaning up..."
rm gcm-linux_amd64.2.6.1.deb
```

## 👥 Maintainers

- Den Delimarsky ([@localden](https://github.com/localden))
- John Lam ([@jflam](https://github.com/jflam))

## 💬 Support

For support, please open a [GitHub issue](https://github.com/github/spec-kit/issues/new). We welcome bug reports, feature requests, and questions about using Spec-Driven Development.

## 🙏 Acknowledgements

This project is heavily influenced by and based on the work and research of [John Lam](https://github.com/jflam).

## 📄 License

This project is licensed under the terms of the MIT open source license. Please refer to the [LICENSE](./LICENSE) file for the full terms.
