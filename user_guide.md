# AI-SWE PromptKit User Guide

This guide explains how to use the AI-SWE PromptKit at different stages of your software development project.

## 1. Introduction

The AI-SWE PromptKit is a tool designed to streamline the software development process by leveraging AI-powered prompts to generate project documentation, manage tasks, and set up development environments. It follows principles like SOLID, DRY, KISS, CLEAN architecture, and modularity to ensure high-quality results.

## 2. Getting Started

### 2.1. Installation

The AI-SWE PromptKit primarily uses prompts and doesn't require extensive installation. Ensure you have a compatible environment for running the `ai-swe` commands (details on this environment are assumed to be provided separately).

### 2.2. Initialization

-   **`ai-swe init`**: This command validates the project structure and ensures consistency between blueprint documents. It checks for the existence and basic structure of all `gen_*.md` templates in the `prompts/` directory.
    ```bash
    ai-swe init
```

## 3. Project Lifecycle

This section details how to use the PromptKit during different phases of a project.

### 3.1. Starting a New Project

-   **`ai-swe idea all`**: This command generates the initial project documentation, including the project idea, user stories, modules, tech stack, implementation plan, and architecture diagrams. It's the recommended starting point for new projects.
    ```bash
    ai-swe idea all
```
    Alternatively, you can use individual subcommands for finer control:
    ```bash
    ai-swe idea project
    ai-swe idea stories
    ai-swe idea modules
    ai-swe idea tech
    ai-swe idea plan
    ai-swe idea architecture
```

-   **`ai-swe setup dev`**: This command sets up the development environment based on your preferred mode (local or Docker). It generates configuration files and scripts for your chosen environment.  It uses information from `prompts/gen_dev_setup.md` and `prompts/gen_tech_stack.md`.
    ```bash
    ai-swe setup dev
```

### 3.2. Resuming Work on an Existing Project

-   **`ai-swe status`**: This command provides an overview of the project's current state, including completed tasks, tasks in progress, upcoming tasks, and any identified risks or issues.
    ```bash
    ai-swe status
```

-   **`ai-swe tasks`**: This command displays existing tasks and sprint plans.
    ```bash
    ai-swe tasks
```

-   **`ai-swe start task`**: This command allows you to select a task and begin working on it. It updates the task status and creates a `current_task.md` file with relevant information.
    ```bash
    ai-swe start task
    ```

### 3.3. Integrating into an Existing Codebase

To integrate the AI-SWE PromptKit into an existing codebase:

1.  **Create Blueprint Directory:** Manually create a `blueprint` directory in your project's root.
2.  **Populate Blueprint (Option A - Manual):**  You can manually create the necessary blueprint files (e.g., `project_idea.md`, `user_stories.md`, etc.) within the `blueprint` directory, reflecting the current state of your project.
3.  **Populate Blueprint (Option B -  `ai-swe idea`):**  You can use the `ai-swe idea` subcommands to generate specific parts of the blueprint based on your existing code.  For example, you might use `ai-swe idea tech` to document your existing technology stack.  You'll likely need to adapt the generated output to match your project precisely.
4.  **Validate:** Run `ai-swe init` to validate the structure and consistency of your blueprint documents.
5. **Adapt Existing Project:** You may need to adapt your existing project structure and workflow to fully leverage the PromptKit's features, such as task management and status updates.

### 3.4. Development Phase

-   **`ai-swe tasks`**: Use this command to manage tasks, view sprint plans, and track progress.
    ```bash
    ai-swe tasks
    ```

-   **`ai-swe start task`**: Select and start working on a specific task.
    ```bash
    ai-swe start task
    ```

-   **`ai-swe tests [module/feature]`**: Generate tests for a specific module or feature.
    ```bash
    ai-swe tests [module/feature]
    ```

-   **`ai-swe update [section]`**: Update a specific section of the blueprint (e.g., `ai-swe update stories`, `ai-swe update plan`).  Be mindful that updating one section might require updates to other related sections.
    ```bash
    ai-swe update stories
    ```

### 3.5. Documentation

-   **`ai-swe docs [library_name]`**: Generate documentation for a specific third-party library used in your project.
    ```bash
    ai-swe docs mylibrary
    ```

## 4. Command Reference

| Command                       | Description                                                                                                                                                                                                                                                           |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ai-swe init`                 | Validates the project structure and blueprint consistency.                                                                                                                                                                                                           |
| `ai-swe setup dev`            | Sets up the development environment (local or Docker).                                                                                                                                                                                                                |
| `ai-swe idea [subcommand]`    | Generates project documentation. Subcommands: `project`, `stories`, `modules`, `tech`, `plan`, `architecture`, `all`.                                                                                                                                               |
| `ai-swe tasks`                | Manages tasks and sprints.                                                                                                                                                                                                                                            |
| `ai-swe start task`           | Starts a task.                                                                                                                                                                                                                                                        |
| `ai-swe status`               | Provides a project status overview.                                                                                                                                                                                                                                   |
| `ai-swe update [section]`     | Updates a specific section of the blueprint (e.g., `idea`, `stories`, `modules`, `tech`, `plan`, `tasks`, `architecture`).                                                                                                                                          |
| `ai-swe docs [library_name]` | Generates documentation for a third-party library.                                                                                                                                                                                                                   |
| `ai-swe tests [module/feature]`| Generates tests.                                                                                                          |

## 5. Troubleshooting

This section will be populated with common issues and solutions as they are identified.
