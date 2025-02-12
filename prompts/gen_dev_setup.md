# Development Setup Generation Prompt

Generates development setup guides and automation scripts based on `blueprint/tech_stack.md`, user's preferred mode (local/docker), and existing documentation.

## Output: Markdown and Scripts

### Local Development Guide (`local_dev.md`)

```markdown
# Local Development Guide

## Prerequisites

-   Required tools and versions
-   System requirements
-   Environment setup

## Package Managers

[List and justify, e.g.:]

-   Frontend: pnpm
-   Backend: uv
-   System: brew/apt

## Environment Variables

-   List required variables and purpose.
-   Instructions for setting them (e.g., `.env` files, shell commands).
-   Example:

    ```
    DATABASE_URL=postgres://user:password@host:port/database
    API_KEY=your_secret_api_key
    ```

## Environment Setup

1.  Install Prerequisites

    ```bash
    [Installation commands]
    ```

2.  Configure Environment

    ```bash
    [Configuration commands]
    ```

3.  Setup Development Tools

    ```bash
    [Tool setup commands]
    ```

## Running the Project

1.  Backend Setup

    ```bash
    [Backend setup commands]
    ```

2.  Frontend Setup

    ```bash
    [Frontend setup commands]
    ```

3.  Database Setup

    ```bash
    [Database setup commands]
    ```

## Development Workflow

-   Code formatting
-   Testing
-   Building
-   Debugging

## Troubleshooting

-   Common issues and solutions
-   Links to documentation

## AI Agent

-   [Assistance with setup]
-   [Automated commands/scripts]
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
- Consider user preference (local/docker), provide mode-specific instructions, fallbacks, and trade-offs.
- Choose package managers based on needs, performance, compatibility, and versions.
- Create automation scripts following KISS, with intuitive commands, error handling, and documentation.
- Configure the environment, handling dependencies, environment variables, tools, and debugging.
- Ask user for cli to manage the project like should setup dev use, like `uv venv`, `uv sync` , `uv run ` etch for managing python project or pnpm for managing frontend node projects. 