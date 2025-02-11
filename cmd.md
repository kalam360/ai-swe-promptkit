# AI-SWE PromptKit Commands for Cline

## Overview

These commands manage project blueprints and development workflow. Each command is linked to specific prompt templates that guide its execution.

## Command to Prompt Template Mapping

### ai-swe init
Primary function: Project initialization and validation
Prompt Templates Used:
- All gen_*.md templates for structure validation:
  * prompts/gen_project_idea.md
  * prompts/gen_user_stories.md
  * prompts/gen_modules.md
  * prompts/gen_tech_stack.md
  * prompts/gen_impl_plan.md
  * prompts/gen_tasks.md
  * prompts/gen_dev_setup.md

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

### ai-swe idea
Primary function: Project documentation
Prompt Templates Used:
1. prompts/gen_project_idea.md (primary)
   * Project concept refinement
   * Core requirements
2. prompts/gen_user_stories.md (auto-triggered)
   * Feature requirements
   * User needs
3. prompts/gen_modules.md (auto-triggered)
   * System architecture
   * Component design
4. prompts/gen_tech_stack.md (auto-triggered)
   * Technology selection
   * Tool requirements
5. prompts/gen_impl_plan.md (auto-triggered)
   * Implementation strategy
   * Development phases

### ai-swe tasks
Primary function: Task generation and management
Prompt Templates Used:
1. prompts/gen_tasks.md (primary)
   * Task breakdown
   * Sprint planning
2. prompts/gen_user_stories.md (reference)
   * Feature requirements
3. prompts/gen_modules.md (reference)
   * Technical requirements
4. prompts/gen_impl_plan.md (reference)
   * Implementation details

### ai-swe start task
Primary function: Task execution workflow
Prompt Templates Used:
1. prompts/gen_tasks.md (primary)
   * Task validation
   * Sprint management
2. prompts/gen_impl_plan.md (reference)
   * Implementation guidelines
3. prompts/gen_user_stories.md (reference)
   * Feature context
4. prompts/gen_modules.md (reference)
   * Technical context

### ai-swe status
Primary function: Project status validation
Prompt Templates Used:
- All gen_*.md templates for validation:
  * prompts/gen_project_idea.md (project alignment)
  * prompts/gen_user_stories.md (feature progress)
  * prompts/gen_modules.md (technical progress)
  * prompts/gen_tech_stack.md (technology validation)
  * prompts/gen_impl_plan.md (implementation progress)
  * prompts/gen_tasks.md (task status)
  * prompts/gen_dev_setup.md (environment status)

## Template Relationships

### Primary Templates
- gen_project_idea.md: Project concept and requirements
- gen_user_stories.md: Feature specifications
- gen_modules.md: System architecture
- gen_tech_stack.md: Technology choices
- gen_impl_plan.md: Implementation strategy
- gen_tasks.md: Task management
- gen_dev_setup.md: Development environment

### Template Dependencies
1. Project Documentation Flow:
   idea → user_stories → modules → tech_stack → impl_plan

2. Task Management Flow:
   impl_plan → tasks → user_stories/modules (reference)

3. Development Setup Flow:
   tech_stack → dev_setup

## Command Usage Flow

1. Initial Setup:
```
ai-swe init
ai-swe setup dev
```

2. Project Definition:
```
ai-swe idea
```
(Automatically triggers documentation generation)

3. Task Management:
```
ai-swe tasks
ai-swe start task
```

4. Status Check:
```
ai-swe status
```

## Best Practices

- Each command references appropriate templates
- Templates maintain consistency through relationships
- Commands trigger necessary template chains
- Status validates against all templates

Remember: All commands and templates enforce:
- SOLID principles
- DRY practices
- KISS approach
- CLEAN architecture
- Modularity