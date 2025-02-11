# AI-SWE PromptKit

A blueprint management system that works as a Git submodule, automatically maintaining project documentation and managing task workflow through simple Cline chat commands.

## Overview

The AI-SWE PromptKit helps you:
- Document and refine project ideas
- Generate comprehensive documentation
- Create and manage detailed tasks
- Track implementation progress
- Maintain consistency between code and documentation

All project documentation and tasks are centralized in a `blueprint/` folder, with automatic updates based on your codebase.

## Getting Started

1. Add as a Git submodule:
```bash
git submodule add https://github.com/kalam360/ai-swe-promptkit.git
```

2. Initialize your project and generate initial documentation:
```
ai-swe init
ai-swe idea all
```

3. Generate tasks:
```
ai-swe tasks
```

4. Start working:
```
ai-swe start task
```

## Project Structure

```
your-project/
├── ai-swe-promptkit/          # This toolkit as a submodule
│   ├── prompts/              # Document generation templates
│   │   ├── gen_project_idea.md
│   │   ├── gen_user_stories.md
│   │   ├── gen_modules.md
│   │   ├── gen_tech_stack.md
│   │   ├── gen_impl_plan.md
│   │   └── gen_tasks.md
│   └── cmd.md                # Command documentation
└── blueprint/                # Your project documentation
    ├── idea_scratchpad.md    # Raw project ideas
    ├── project_idea.md       # Refined project concept
    ├── user_stories.md       # User stories
    ├── modules.md            # Module breakdown
    ├── tech_stack.md         # Technology choices
    ├── impl_plan.md          # Implementation plan
    ├── project_status.md     # Current status
    └── tasks/                # Task tracking
        ├── impl_tasks.md     # All implementation tasks
        ├── current_sprint.md # Current sprint tasks
        ├── current_task.md   # Active task details
        └── issues.md         # Critical issues
```

## Key Features

- **Simple Commands**: Just 5 core commands to remember
- **Automatic Updates**: Documentation stays in sync with code
- **Smart Generation**: One command triggers multiple document updates
- **Comprehensive Tasks**: Tasks include full context from documentation
- **Sprint Management**: Automated sprint planning and tracking

## Commands

See [cmd.md](cmd.md) for detailed documentation. Core commands include:

```
ai-swe init        # Setup/verify project structure
ai-swe idea all    # Generate all blueprint documents
ai-swe idea [sub]  # Generate specific blueprint section (project, stories, modules, tech, plan, architecture)
ai-swe tasks       # Generate comprehensive task breakdown
ai-swe start task  # Begin working on next task
ai-swe status      # Check project progress
ai-swe update [section] # Update a specific section of the blueprint
ai-swe docs [library_name] # Generate documentation for a third party library
```

## How It Works

1. **Project Setup**:
   - Add as Git submodule
   - Run "ai-swe init"
   - System sets up blueprint structure

2. **Documentation**:
   - Write ideas with "ai-swe idea"
   - System generates all related documents
   - Documents stay in sync with code

3. **Task Management**:
   - Generate tasks from documentation
   - Tasks include full context
   - Automated sprint planning
   - Smart task prioritization

4. **Task Execution**:
   - Start next task with "ai-swe start task"
   - Get full task context
   - System tracks progress
   - Handles sprint transitions

## Task Workflow

1. **Task Generation**:
   - System analyzes all documentation
   - Creates detailed tasks with context
   - Organizes into sprints
   - Identifies critical issues

2. **Task Execution**:
   - Complete current task
   - System selects next task based on:
     * Sprint priority
     * Critical issues
     * Dependencies
   - Provides full context for task

3. **Sprint Management**:
   - Track sprint progress
   - Automatic sprint planning
   - Critical issue handling
   - Task prioritization

## Best Practices

1. **Task Management**:
   - Complete current task before starting new
   - Address critical issues promptly
   - Review sprint progress regularly
   - Keep task status updated

2. **Documentation**:
   - Keep idea_scratchpad.md updated
   - Let system generate task details
   - Review generated content
   - Maintain consistency

## Contributing

Contributions are welcome! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

- Documentation: [Full documentation](docs/README.md)
- Issues: [GitHub Issues](https://github.com/yourusername/ai-swe-promptkit/issues)
- Discussions: [GitHub Discussions](https://github.com/yourusername/ai-swe-promptkit/discussions)

## Acknowledgments

- Designed for seamless integration as a Git submodule
- Built on software engineering best practices
- Optimized for efficient task management