# AI-SWE PromptKit Commands for Cline

## Overview

These commands manage project blueprints and development workflow. Each command is linked to specific prompt templates that guide its execution. The AI agent should follow a plan-and-execute approach, using the provided prompts and information to generate the requested outputs.

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

Primary function: Project initialization and validation
Prompt Templates Used:
- All `gen_*.md` templates for structure validation:
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
- **Plan:** Validate the existence and basic structure of all blueprint documents. Check for consistency between documents (e.g., user stories referenced in the implementation plan). Identify any missing or incomplete sections.
- **Execution:** Report any inconsistencies or missing information. Suggest improvements to the blueprint structure. Do not generate new content, only validate existing.

### ai-swe setup dev

Primary function: Development environment setup
Prompt Templates Used:
- prompts/gen_dev_setup.md (primary)
  * Local/Docker setup
  * Package manager configuration
  * Automation scripts
- prompts/gen_tech_stack.md (reference)
  * Technology requirements
  * Tool versions

**AI Agent Behavior:**

- **Role:** DevOps engineer.
- **Plan:** Read the `blueprint/tech_stack.md` to understand the required technologies and versions. Read the user's preferred development mode (local/docker) - This should be provided as an argument or assumed as 'local' if not provided. Use `prompts/gen_dev_setup.md` to generate the appropriate setup guide and scripts.
- **Execution:** Generate `local_dev.md` (for local setup) or `docker-compose.yml` (for Docker setup). Generate a `Makefile` with common development commands. Output the generated files.

### ai-swe idea

Primary function: Project documentation generation. Use subcommands for specific sections.
Prompt Templates Used:
- See subcommands below.

**AI Agent Behavior (General for `ai-swe idea`):**

- **Role:** Software architect and product owner.
- **Plan:** Understand the overall project idea from `blueprint/idea_scratchpad.md` (if it exists) and any user input. Use the appropriate subcommand and corresponding prompt to generate the specific document.
- **Execution:** Generate the requested document (project idea, user stories, modules, tech stack, implementation plan, or architecture diagram). Ensure consistency between generated documents.

**Subcommands:**

*   `ai-swe idea project`: Generates the project idea document.
    *   Uses: `prompts/gen_project_idea.md`
    *   **Agent Plan:**  Read `blueprint/idea_scratchpad.md`, then use `prompts/gen_project_idea.md` to generate `blueprint/project_idea.md`.
*   `ai-swe idea stories`: Generates user stories.
    *   Uses: `prompts/gen_user_stories.md`
    *   **Agent Plan:** Read `blueprint/project_idea.md`, then use `prompts/gen_user_stories.md` to generate `blueprint/user_stories.md`.
*   `ai-swe idea modules`: Generates module analysis.
    *   Uses: `prompts/gen_modules.md`
    *   **Agent Plan:** Read `blueprint/project_idea.md` and `blueprint/user_stories.md`, then use `prompts/gen_modules.md` to generate `blueprint/modules.md`.
*   `ai-swe idea tech`: Generates the technology stack document.
    *   Uses: `prompts/gen_tech_stack.md`
    *   **Agent Plan:** Read `blueprint/project_idea.md` and `blueprint/modules.md`, then use `prompts/gen_tech_stack.md` to generate `blueprint/tech_stack.md`.
*   `ai-swe idea plan`: Generates the implementation plan.
    *   Uses: `prompts/gen_impl_plan.md`
    *   **Agent Plan:** Read `blueprint/project_idea.md`, `blueprint/user_stories.md`, `blueprint/modules.md`, and `blueprint/tech_stack.md`, then use `prompts/gen_impl_plan.md` to generate `blueprint/impl_plan.md`.
*   `ai-swe idea architecture`: Generates the architecture diagram.
    *   Uses: `prompts/gen_architecture.md`
    *   **Agent Plan:** Read `blueprint/modules.md` and `blueprint/tech_stack.md`, then use `prompts/gen_architecture.md` to generate architecture diagrams (e.g., in Mermaid format).
*   `ai-swe idea all`: Generates all project documentation.
    * **Agent Plan:** Execute the individual `ai-swe idea` subcommands in the logical order: `project`, `stories`, `modules`, `tech`, `plan`, `architecture`.

### ai-swe tasks

Primary function: Task generation and management
Prompt Templates Used:
- prompts/gen_tasks.md (primary)
  * Task breakdown
  * Sprint planning
- prompts/gen_user_stories.md (reference)
  * Feature requirements
- prompts/gen_modules.md (reference)
  * Technical requirements
- prompts/gen_impl_plan.md (reference)
  * Implementation details

**AI Agent Behavior:**

- **Role:** Project manager.
- **Plan:** Read the implementation plan (`blueprint/impl_plan.md`), user stories (`blueprint/user_stories.md`), and module analysis (`blueprint/modules.md`). Use `prompts/gen_tasks.md` to generate task breakdowns, sprint plans, and current task/sprint documents.
- **Execution:** Generate `impl_tasks.md`, `current_sprint.md`, and `current_task.md`. Manage task status and progress.

### ai-swe start task

Primary function: Task execution workflow
Prompt Templates Used:
- prompts/gen_tasks.md (primary)
  * Task validation
  * Sprint management
- prompts/gen_impl_plan.md (reference)
  * Implementation guidelines
- prompts/gen_user_stories.md (reference)
  * Feature context
- prompts/gen_modules.md (reference)
  * Technical context

**AI Agent Behavior:**

- **Role:** Development team lead.
- **Plan:** Select a task from `impl_tasks.md` or `current_sprint.md`. Gather all relevant context: user story, module requirements, implementation details. Set up the development environment (if necessary).
- **Execution:** Update the task status to "In Progress". Create a `current_task.md` file with all relevant information. Begin working on the task, providing regular updates.

### ai-swe status

Primary function: Project status validation
Prompt Templates Used:
- All `gen_*.md` templates for validation:
  * prompts/gen_project_idea.md (project alignment)
  * prompts/gen_user_stories.md (feature progress)
  * prompts/gen_modules.md (technical progress)
  * prompts/gen_tech_stack.md (technology validation)
  * prompts/gen_impl_plan.md (implementation progress)
  * prompts/gen_tasks.md (task status)
  * prompts/gen_dev_setup.md (environment status)
  * prompts/gen_architecture.md (architecture validation)

**AI Agent Behavior:**

- **Role:** Project auditor.
- **Plan:** Read all blueprint documents. Compare the current state of the project with the planned state. Identify any discrepancies, risks, or issues.
- **Execution:** Generate a status report summarizing the project's progress, including: Completed tasks and user stories. Tasks in progress. Upcoming tasks. Any identified risks or issues.

### ai-swe update [section]

Primary function: Updates a specific section of the blueprint.
Prompt Templates Used:
- Depends on the `[section]` argument. For example:
  * `ai-swe update idea`: Uses `prompts/gen_project_idea.md`
  * `ai-swe update stories`: Uses `prompts/gen_user_stories.md`
  * `ai-swe update modules`: Uses `prompts/gen_modules.md`
  * `ai-swe update tech`: Uses `prompts/gen_tech_stack.md`
  * `ai-swe update plan`: Uses `prompts/gen_impl_plan.md`
  * `ai-swe update tasks`: Uses `prompts/gen_tasks.md`
  * `ai-swe update architecture`: Uses `prompts/gen_architecture.md`

**AI Agent Behavior:**

- **Role:** Technical writer and project manager.
- **Plan:** Identify the section to be updated based on the `[section]` argument. Read the relevant existing blueprint document. Use the appropriate `gen_*.md` prompt to regenerate the section, incorporating any new information or changes. **Always check if the updates might necessitate changes in other requirements or files.**
- **Execution:** Update the specified section of the blueprint. Ensure consistency with other blueprint documents.

### ai-swe docs [library_name]

Primary function: Generates documentation for a third-party library.
Prompt Templates Used:
- prompts/gen_thirdparty.md

**AI Agent Behavior:**

- **Role:** Technical writer.
- **Plan:** Read the `blueprint/tech_stack.md` to identify third-party dependencies, or use the provided `[library_name]` argument. Use `prompts/gen_thirdparty.md` to generate documentation for the specified library.
- **Execution:** Generate a markdown file in `blueprint/docs/[library_name].md` with the library documentation.

### ai-swe tests [module/feature]

Primary function: Generates tests for module/feature.
Prompt Templates Used:
- prompts/gen_tasks.md (reference)

**AI Agent Behavior:**
- **Role:** QA engineer.
- **Plan:** Read the relevant module/feature from `blueprint/modules.md` or task from `blueprint/tasks.md`. Identify the acceptance criteria and technical requirements. Generate unit, integration, and/or end-to-end tests based on the information.
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

## Command Usage Flow

1. Initial Setup:
```
ai-swe init
ai-swe setup dev
```

2. Project Definition:
```
ai-swe idea project
ai-swe idea stories
ai-swe idea modules
ai-swe idea tech
ai-swe idea plan
ai-swe idea architecture

# OR, to generate all at once (original behavior):
ai-swe idea all
```

3. Task Management:
```
ai-swe tasks
ai-swe start task
ai-swe tests [module/feature]
```

4. Status Check:
```
ai-swe status
```
5. Update Blueprint
```
ai-swe update [section]
```
6. Generate Third-Party Documentation
```
ai-swe docs [library_name]