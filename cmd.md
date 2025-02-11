# AI-SWE PromptKit Commands for Cline

## Overview

These commands are designed for use within a chat box interface to manage project blueprints and development workflow. They are **not** intended to be executed directly in a terminal. Each command is linked to specific prompt templates that guide its execution. The AI agent should follow a plan-and-execute approach, using the provided prompts and information to generate the requested outputs.

## General AI Agent Behavior

For each command, the AI Agent will generally follow this behavior pattern:

- **Role:** Assume a specific role relevant to the command (e.g., Project Manager, DevOps Engineer, Software Architect).
- **Plan:** Develop a plan based on the command's purpose and available information (e.g., reading relevant blueprint documents, understanding user input).
- **Execution:** Carry out the plan, generating the required outputs (e.g., documents, reports, code).

Specific deviations from this general behavior will be noted in the individual command descriptions.

## General Principles

All commands and templates enforce:

- SOLID principles
- DRY practices
- KISS approach
- CLEAN architecture
- Modularity

## Command to Prompt Template Mapping

### ai-swe init

When you use the `ai-swe init` command, the AI, acting as a project manager and technical lead, will generate and validate the initial project blueprint.

Prompt Templates Used:
- All `gen_*.md` templates. Used to generate the initial project blueprint:
  * prompts/gen_project_idea.md
  * prompts/gen_user_stories.md
  * prompts/gen_modules.md
  * prompts/gen_tech_stack.md
  * prompts/gen_impl_plan.md
  * prompts/gen_tasks.md
  * prompts/gen_dev_setup.md
  * prompts/gen_architecture.md

**AI Agent Behavior:**

- **Role:** Project manager and technical lead.
- **Plan:**
    1. Generate the project blueprint using the `gen_*.md` templates.
    2. Validate the existence and basic structure of all blueprint documents.
    3. Check for consistency between documents (e.g., user stories referenced in the implementation plan).
    4. Identify any missing or incomplete sections.
- **Execution:**
    1. Create the `blueprint` directory if it doesn't exist.
    2. Generate the initial blueprint files (`project_idea.md`, `user_stories.md`, etc.) within the `blueprint` directory, using the corresponding `gen_*.md` prompts.
    3. Report any inconsistencies or missing information in the generated blueprint.
    4. Suggest improvements to the blueprint structure.

### ai-swe setup dev

When you use the `ai-swe setup dev` command, the AI, acting as a DevOps engineer, will suggest a development environment setup.

Blueprint Files Used:
- blueprint/dev_setup.md (primary)
  * Local/Docker setup
  * Package manager configuration
  * Automation scripts
- blueprint/tech_stack.md (reference)
  * Technology requirements
  * Tool versions

**AI Agent Behavior:**

- **Role:** DevOps engineer.
- **Plan:**
    1. Understand the required technologies and versions from `blueprint/tech_stack.md`.
    2. Understand the user's preferred development mode (local/docker).
    3. Use the information in `blueprint/dev_setup.md` to generate a setup guide and script suggestions.
- **Execution:** Generate suggestions for `local_dev.md` (for local setup) or `docker-compose.yml` (for Docker setup), and a `Makefile` with common development commands. This will help you set up your development environment quickly.

### ai-swe idea

The `ai-swe idea` command, along with its subcommands, is used to generate project documentation. The AI acts as a software architect and product owner.

Prompt Templates Used:
- See subcommands below.

**AI Agent Behavior (General for `ai-swe idea`):**

- **Role:** Software architect and product owner.
- **Plan:** Understand the overall project idea and any user input. Use the appropriate subcommand and corresponding prompt to generate the specific document.
- **Execution:** Generate the requested document (project idea, user stories, modules, tech stack, implementation plan, or architecture diagram). Ensure consistency between generated documents.

**Subcommands:**

*   `ai-swe idea project`: Generates the project idea document.
    *   Uses: `prompts/gen_project_idea.md`
    *   **Agent Plan:**  Use `prompts/gen_project_idea.md` to generate content for `blueprint/project_idea.md`.
*   `ai-swe idea stories`: Generates user stories.
    *   Uses: `prompts/gen_user_stories.md`
    *   **Agent Plan:** Use `prompts/gen_user_stories.md` to generate content for `blueprint/user_stories.md`.
*   `ai-swe idea modules`: Generates module analysis.
    *   Uses: `prompts/gen_modules.md`
    *   **Agent Plan:** Use `prompts/gen_modules.md` to generate content for `blueprint/modules.md`.
*   `ai-swe idea tech`: Generates the technology stack document.
    *   Uses: `prompts/gen_tech_stack.md`
    *   **Agent Plan:**  Use `prompts/gen_tech_stack.md` to generate content for `blueprint/tech_stack.md`.
*   `ai-swe idea plan`: Generates the implementation plan.
    *   Uses: `prompts/gen_impl_plan.md`
    *   **Agent Plan:** Use `prompts/gen_impl_plan.md` to generate content for `blueprint/impl_plan.md`.
*   `ai-swe idea architecture`: Generates the architecture diagram.
    *   Uses: `prompts/gen_architecture.md`
    *   **Agent Plan:** Use `prompts/gen_architecture.md` to generate architecture diagram content (e.g., in Mermaid format).
*   `ai-swe idea all`: Generates all project documentation.
    * **Agent Plan:** Execute the individual `ai-swe idea` subcommands in the logical order: `project`, `stories`, `modules`, `tech`, `plan`, `architecture`.

### ai-swe tasks

When you use the `ai-swe tasks` command, the AI, acting as a project manager, will generate tasks, plan sprints, and create task tracking files based on the `prompts/gen_tasks.md` prompt.

Prompt Templates Used:
- `prompts/gen_tasks.md`

Blueprint Files Used:
- `blueprint/user_stories.md` (reference)
  * Feature requirements
- `blueprint/modules.md` (reference)
  * Technical requirements
- `blueprint/impl_plan.md` (reference)
  * Implementation details
- `blueprint/project_idea.md` (reference)
 * Project details

**AI Agent Behavior:**

- **Role:** Project manager.
- **Plan:**
    1.  Read `blueprint/user_stories.md`, `blueprint/impl_plan.md`, and `blueprint/project_idea.md` to understand the project context.
    2.  Use the `prompts/gen_tasks.md` prompt to generate:
        -   Implementation Tasks (`impl_tasks.md`)
        -   Current Sprint (`current_sprint.md`)
        -   Current Task (`current_task.md`)
        -   Issues (`issues.md`)
    3.  Update files in the `task-tracking` directory.
- **Execution:**
    1.  Generate content for task breakdowns, sprint plan, and current task using the `prompts/gen_tasks.md` prompt.
    2.  Create and populate files in `blueprint/task-tracking/` (e.g., `blueprint/task-tracking/impl_tasks.md`, `blueprint/task-tracking/current_sprint.md`, `blueprint/task-tracking/current_task.md`, `blueprint/task-tracking/issues.md`).
    3.  Ensure that the generated tasks are consistent with the user stories, implementation plan, and overall project goals.
### ai-swe start task

When you use the `ai-swe start task` command, the AI, acting as a development team lead, will initiate the workflow for a specific task.

Blueprint Files Used:
- blueprint/tasks.md (primary)
  * Task validation
  * Sprint management
- blueprint/impl_plan.md (reference)
  * Implementation guidelines
- blueprint/user_stories.md (reference)
  * Feature context
- blueprint/modules.md (reference)
  * Technical context

**AI Agent Behavior:**

- **Role:** Development team lead.
- **Plan:**
    1. Select a task from `blueprint/tasks.md` or `blueprint/task-tracking/current_sprint.md`.
    2. Gather relevant context from: `blueprint/user_stories.md`, `blueprint/modules.md`, and `blueprint/impl_plan.md`.
- **Execution:**
    1. Update the status of the task to "In Progress" in `blueprint/task-tracking/tasks.md` and/or `blueprint/task-tracking/current_sprint.md`.
    2. Create/Update content for `blueprint/task-tracking/current_task.md` with all relevant information.
- **Execution:** Indicate that the task is "In Progress". Create content for a `current_task.md` file with all relevant information.

### ai-swe status

When you use the `ai-swe status` command, the AI, acting as a project auditor, will validate the project's status.

Blueprint Files Used:
- All blueprint files for validation:
  * blueprint/project_idea.md (project alignment)
  * blueprint/user_stories.md (feature progress)
  * blueprint/modules.md (technical progress)
  * blueprint/tech_stack.md (technology validation)
  * blueprint/impl_plan.md (implementation progress)
  * blueprint/tasks.md (task status)
  * blueprint/dev_setup.md (environment status)
  * blueprint/architecture.md (architecture validation)

**AI Agent Behavior:**

- **Role:** Project auditor.
- **Plan:** Understand all blueprint documents. Compare the current state of the project with the planned state. Identify any discrepancies, risks, or issues.
- **Execution:** Generate a status report summarizing the project's progress, including: Completed tasks and user stories, tasks in progress, upcoming tasks, and any identified risks or issues.

### ai-swe update [section]

When you use the `ai-swe update [section]` command, the AI, acting as a technical writer and project manager, will update the specified section of the blueprint.

Prompt Templates Used:
- Depends on the `[section]` argument. For example:
  * `ai-swe update idea`: Uses `prompts/gen_project_idea.md` to update `blueprint/project_idea.md`
  * `ai-swe update stories`: Uses `prompts/gen_user_stories.md` to update `blueprint/user_stories.md`
  * `ai-swe update modules`: Uses `prompts/gen_modules.md` to update `blueprint/modules.md`
  * `ai-swe update tech`: Uses `prompts/gen_tech_stack.md` to update `blueprint/tech_stack.md`
  * `ai-swe update plan`: Uses `prompts/gen_impl_plan.md` to update `blueprint/impl_plan.md`
  * `ai-swe update tasks`: Uses `prompts/gen_tasks.md` to update `blueprint/tasks.md`
  * `ai-swe update architecture`: Uses `prompts/gen_architecture.md` to update `blueprint/architecture.md`

**AI Agent Behavior:**

- **Role:** Technical writer and project manager.
- **Plan:** Identify the section to be updated. Understand the relevant existing blueprint document. Use the appropriate `gen_*.md` prompt to regenerate the section, incorporating any new information or changes. **Always check if the updates might necessitate changes in other requirements or files.**
- **Execution:** Update the specified section of the blueprint. Ensure consistency with other blueprint documents.

### ai-swe docs [library_name]

When you use the `ai-swe docs [library_name]` command, the AI, acting as a technical writer, will generate documentation for a specified third-party library.

Prompt Templates Used:
- prompts/gen_thirdparty.md

**AI Agent Behavior:**

- **Role:** Technical writer.
- **Plan:** Identify third-party dependencies or use the provided `[library_name]` argument. Use `prompts/gen_thirdparty.md` to generate documentation for the specified library.
- **Execution:** Generate content for a markdown file in `blueprint/docs/[library_name].md` with the library documentation.

### ai-swe tests [module/feature]

When you use the `ai-swe tests [module/feature]` command, the AI, acting as a QA engineer, will generate tests for the specified module or feature.

Blueprint Files Used:
- blueprint/tasks.md (reference)
- blueprint/user_stories.md (reference)
- blueprint/modules.md (reference)

**AI Agent Behavior:**

- **Role:** QA engineer.
- **Plan:**
    1. Understand the relevant module/feature or task from `blueprint/tasks.md`, `blueprint/user_stories.md`, and `blueprint/modules.md`.
    2. Identify the acceptance criteria and technical requirements from the blueprint.
    3. Generate unit, integration, and/or end-to-end tests based on the information.
- **Execution:** Generate test files in the appropriate format and location (determined by the project's technology stack).

## Template Relationships

### Primary Templates
- gen_project_idea.md: Project concept and requirements
- gen_user_stories.md: Feature specifications
- gen_modules.md: System architecture
- gen_tech_stack.md: Technology choices
- gen_impl_plan.md: Implementation strategy
- gen_tasks.md: Task management
- gen_dev_setup.md: Development environment
- gen_architecture.md: Architecture diagrams
- gen_thirdparty.md: Third-party library documentation

### Template Dependencies
1. Project Documentation Flow:
   idea (project, stories, modules, tech, plan, architecture) → user_stories → modules → tech_stack → impl_plan → architecture

2. Task Management Flow:
   impl_plan → tasks → user_stories/modules (reference)

3. Development Setup Flow:
   tech_stack → dev_setup

4. Third-Party Documentation Flow:
 tech_stack -> gen_thirdparty.md