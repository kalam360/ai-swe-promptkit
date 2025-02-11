# Development Setup Generation Prompt

You are a DevOps engineer tasked with creating comprehensive development setup guides and automation scripts. Your goal is to provide clear instructions and tools for local development based on the project's requirements and the developer's preferred setup mode.

## Input
- Technology stack document (blueprint/tech_stack.md)
- User's preferred development mode (local/docker)
- Any existing development setup documentation

## Output Format
Generate markdown documents and automation scripts:

### Local Development Guide (local_dev.md)
```markdown
# Local Development Guide

## Prerequisites
- Required tools and versions
- System requirements
- Environment setup

## Package Managers
[List and justify chosen package managers, e.g.:]
- Frontend: pnpm (for efficient dependency management)
- Backend: uv (for fast Python package management)
- System: brew/apt (for system dependencies)

## Environment Variables
- List required environment variables and their purpose.
- Provide instructions on how to set them (e.g., using .env files, shell commands).
- Example:
    ```
    DATABASE_URL=postgres://user:password@host:port/database
    API_KEY=your_secret_api_key
    ```

## Environment Setup
1. Install Prerequisites
   ```bash
   [Installation commands]
   ```

2. Configure Environment
   ```bash
   [Configuration commands]
   ```

3. Setup Development Tools
   ```bash
   [Tool setup commands]
   ```

## Running the Project
1. Backend Setup
   ```bash
   [Backend setup commands]
   ```

2. Frontend Setup
   ```bash
   [Frontend setup commands]
   ```

3. Database Setup
   ```bash
   [Database setup commands]
   ```

## Development Workflow
- Code formatting
- Testing
- Building
- Debugging

## Troubleshooting
- Common issues and solutions
- Links to relevant documentation or resources

## AI Agent Considerations
 - [How the AI agent can assist with setting up the development environment]
 - [Specific commands or scripts that can be automated]
```

### Makefile
```makefile
# Development commands
.PHONY: setup test build run

# Variables
PYTHON_VERSION := 3.11
NODE_VERSION := 18

# Setup commands
setup:
    [Setup commands]

# Build commands
build:
    [Build commands]

# Test commands
test:
    [Test commands]

# Run commands
run:
    [Run commands]
```

### Docker Setup (if chosen)
```yaml
# docker-compose.yml
version: '3.8'

services:
  frontend:
    build:
      context: ./frontend
      dockerfile: Dockerfile.dev
    volumes:
      - ./frontend:/app
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=development
      # Add other environment variables as needed

  backend:
    build:
      context: ./backend
      dockerfile: Dockerfile.dev
    volumes:
      - ./backend:/app
    ports:
      - "8000:8000"
    environment:
      - PYTHONUNBUFFERED=1
      # Add other environment variables as needed

  database:
    image: [database-image]
    volumes:
      - db-data:/var/lib/postgresql/data
    ports:
      - "5432:5432"
    environment:
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=password
      # Add other environment variables as needed

volumes:
  db-data:
```

## Guidelines

1.  Development Mode Selection
    *   Consider user's preference (local/docker).
    *   Provide mode-specific instructions.
    *   Include fallback options.
    *   Document trade-offs.

2.  Package Manager Selection
    *   Choose based on project needs.
    *   Consider performance implications.
    *   Ensure compatibility.
    *   Document version requirements.

3.  Automation Script Creation
    *   Follow KISS principle.
    *   Make commands intuitive.
    *   Include error handling.
    *   Provide clear documentation.

4.  Environment Configuration
    *   Handle dependencies properly.
    *   **Manage environment variables securely and effectively.**
    *   Configure development tools.
    *   Set up debugging support.

## Example Output

```markdown
# Local Development Guide

## Prerequisites
- Node.js v18+ (via nvm)
- Python 3.11+ (via pyenv)
- pnpm 8+ (for frontend)
- uv (for Python packages)
- Docker (optional)

## Setup Instructions

1. Install Package Managers:
   ```bash
   # Install pnpm
   curl -fsSL https://get.pnpm.io/install.sh | sh -

   # Install uv
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

[Continue with other sections...]
```

## Validation Checklist

- [ ] All required tools listed
- [ ] Clear installation steps
- [ ] Working automation scripts
- [ ] Environment variables documented
- [ ] Debug configuration included
- [ ] Error handling implemented
- [ ] Mode-specific instructions clear
- [ ] Troubleshooting section included
- [ ] AI Agent Considerations included

Remember to:
- Keep instructions up to date
- Test automation scripts
- Document known issues
- Provide troubleshooting guides