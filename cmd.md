# AI-SWE PromptKit Commands

These commands manage project blueprints and development workflow. They are **not** terminal commands. Each command uses specific prompt templates.

## Principles

- SOLID principles
- DRY practices
- KISS approach
- CLEAN architecture
- Modularity

## Commands

### `ai-swe init`

Generates and validates the initial project blueprint.

**Files Used:**

-   All `gen_*.md` templates in `prompts/`:
    -   `gen_project_idea.md`
    -   `gen_user_stories.md`
    -   `gen_modules.md`
    -   `gen_tech_stack.md`
    -   `gen_impl_plan.md`
    -   `gen_tasks.md`
    -   `gen_dev_setup.md`
    -   `gen_architecture.md`

**Behavior:**

1.  Creates the `blueprint` directory if it doesn't exist.
2.  Creates the `blueprint/idea_scratchpad.md` file if it doesn't exist.
3.  Generates initial blueprint files (`project_idea.md`, `user_stories.md`, etc.) in `blueprint/` but keep them blank.
4.  Reports inconsistencies or missing information.

### `ai-swe setup dev`

Suggests a development environment setup.

**Files Used:**

-   `blueprint/dev_setup.md` (primary)
-   `blueprint/tech_stack.md` (reference)

**Behavior:** Generates suggestions for `local_dev.md` (local setup) or `docker-compose.yml` (Docker setup), and a `Makefile`.

### `ai-swe scaffold`

Generates the project folder structure and sets up the development environment.

**Files Used:**

-   `blueprint/project_idea.md` (reference)
-   `blueprint/user_stories.md` (reference)
-   `blueprint/modules.md` (reference)
-   `blueprint/tech_stack.md` (reference)
-   `blueprint/impl_plan.md` (reference)
-   `blueprint/architecture.md` (reference)
-   `blueprint/docs/[library_name].md` (reference, if applicable)
-   `prompts/gen_dev_setup.md`
-   `prompts/gen_tasks.md`

**Behavior:**

1.  Creates the necessary project folder structure based on the project blueprint files (`project_idea.md`, `user_stories.md`, `modules.md`, `tech_stack.md`, `impl_plan.md`, and `architecture.md`).
2.  Prompts the user to select a package manager (e.g., npm, yarn, pnpm for JavaScript; pip, uv for Python) if applicable based on `tech_stack.md`.
3.  Invokes the `ai-swe setup dev` command to generate development environment setup suggestions (`local_dev.md` or `docker-compose.yml`, and `Makefile`).
4.  For third-party libraries specified in `tech_stack.md`, it refers to their documentation (using `ai-swe docs [library_name]`) to guide project setup.
5.  Creates a new task using `prompts/gen_tasks.md` to scaffold the necessary files in the project workspace. This task will be added to the task tracking system.

### `ai-swe idea`

Generates project documentation.

**Subcommands:**

-   `ai-swe idea project`: Generates `blueprint/project_idea.md` using `prompts/gen_project_idea.md`.
-   `ai-swe idea stories`: Generates `blueprint/user_stories.md` using `prompts/gen_user_stories.md`.
-   `ai-swe idea modules`: Generates `blueprint/modules.md` using `prompts/gen_modules.md`.
-   `ai-swe idea tech`: Generates `blueprint/tech_stack.md` using `prompts/gen_tech_stack.md`.
-   `ai-swe idea plan`: Generates `blueprint/impl_plan.md` using `prompts/gen_impl_plan.md`.
-   `ai-swe idea architecture`: Generates architecture diagram content using `prompts/gen_architecture.md`.
-   `ai-swe idea all`: Executes subcommands in order: `project`, `stories`, `modules`, `tech`, `plan`, `architecture`.

### `ai-swe tasks`

Generates tasks, plans sprints, and creates task tracking files. Tasks should be taken from the blueprint/tasks.md  and blueprint/impl_status.md file and track it to match other blueprint files

**Files Used:**

-   `prompts/gen_tasks.md`
-   `blueprint/user_stories.md` (reference)
-   `blueprint/modules.md` (reference)
-   `blueprint/impl_plan.md` (reference)
-   `blueprint/impl_status.md` (reference)
-   `blueprint/project_idea.md` (reference)

**Behavior:**

1.  Generates:
    -   `impl_tasks.md` (high-level overview)
    -   `current_sprint.md` (high-level overview)
    -   `current_task.md` (detailed task description)
    -   `issues.md` (high-level overview)
2.  Creates/updates files in `blueprint/task-tracking/`.



### `ai-swe start task`

Initiates workflow for the task specified in `blueprint/task-tracking/current_task.md`.

**Files Used:**

-   `blueprint/task-tracking/*` (primary)
-   `blueprint/tasks.md` (reference)
-   `blueprint/impl_plan.md` (reference if needed)
-   `blueprint/user_stories.md` (reference)
-   `blueprint/modules.md` (reference)

**Behavior:**

1.  Updates task status to "In Progress" in `blueprint/task-tracking/`. The command primarily uses data from the `blueprint/task-tracking/` directory.
2.  Creates/updates `blueprint/task-tracking/current_task.md` mostly just for reference. only create if the tasks status is completed and create new task
3.  change the mode to coding agent to start working on the task


### `ai-swe status`

Generates a status report, including `blueprint/impl_status.md`.

**Files Used:**

-   `prompts/gen_status.md`
-   All blueprint files for validation.
-   Generates: `blueprint/impl_status.md`

**Behavior:**

1.  Generates a status report.
2.  Creates/updates `blueprint/impl_status.md`.

### `ai-swe update [section]`

Updates a specified section of the blueprint.

**Files Used:** Depends on `[section]`. Examples:

-   `ai-swe update idea`: `prompts/gen_project_idea.md` to update `blueprint/project_idea.md`
-   `ai-swe update stories`: `prompts/gen_user_stories.md` to update `blueprint/user_stories.md`
-   `ai-swe update modules`: `prompts/gen_modules.md` to update `blueprint/modules.md`
-   `ai-swe update tech`: `prompts/gen_tech_stack.md` to update `blueprint/tech_stack.md`
-   `ai-swe update plan`: `prompts/gen_impl_plan.md` to update `blueprint/impl_plan.md`
-   `ai-swe update tasks`: `prompts/gen_tasks.md` to update `blueprint/tasks.md`
-   `ai-swe update architecture`: `prompts/gen_architecture.md` to update `blueprint/architecture.md`

**Behavior:** Updates the section, ensuring consistency with other documents.

### `ai-swe docs [library_name]`

Generates documentation for a specified third-party library.

**Files Used:**

-   `prompts/gen_thirdparty.md`

**Behavior:** Generates `blueprint/docs/[library_name].md`.

### `ai-swe tests [module/feature]`

Generates tests for a specified module or feature.

**Files Used:**

-   `blueprint/tasks.md` (reference)
-   `blueprint/user_stories.md` (reference)
-   `blueprint/modules.md` (reference)

**Behavior:** Generates test files.

## Template Relationships

### Primary Templates

-   `gen_project_idea.md`: Project concept
-   `gen_user_stories.md`: Features
-   `gen_modules.md`: Architecture
-   `gen_tech_stack.md`: Technologies
-   `gen_impl_plan.md`: Implementation
-   `gen_tasks.md`: Tasks
-   `gen_dev_setup.md`: Development environment
-   `gen_architecture.md`: Diagrams
-   `gen_thirdparty.md`: Third-party docs

### Dependencies

1.  **Project Documentation:** `idea` (all) → `user_stories` → `modules` → `tech_stack` → `impl_plan` → `architecture`
2.  **Task Management:** `impl_plan` → `tasks` → `user_stories`/`modules` (reference)
3.  **Development Setup:** `tech_stack` → `dev_setup`
4.  **Third-Party Docs:** `tech_stack` → `gen_thirdparty.md`
5.  **Status Reporting:** `gen_status.md` → blueprint files → `blueprint/impl_status.md`