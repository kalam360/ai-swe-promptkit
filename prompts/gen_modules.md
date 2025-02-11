# Module Analysis Generation Prompt

Creates a module structure based on `blueprint/project_idea.md` and `blueprint/user_stories.md`.

## Output: Markdown Document

```markdown
# Module Analysis

## System Overview

[High-level architecture description]

## Core Modules

### [Module Name]

**Purpose:**

[Module's responsibility]

**Key Components:**

1.  [Component 1]
    -   Purpose: [Description]
    -   Responsibilities: [List]
    -   Interfaces: [Key interfaces]
2.  [Component 2]
    ...

**Dependencies:**

-   [External dependency 1]
-   [Internal dependency 1]

**Technical Considerations:**

-   [Performance]
-   [Security]
-   [Scalability]
-   [Testability]

**Error Handling:**

-   [Potential errors]
-   [Error handling]

**AI Agent Considerations:**

-   [Code/test generation]
-   [Design patterns or libraries]

## Module Interactions

### [Interaction Pattern 1]

-   **Modules Involved:** [List]
-   **Flow Description:** [Interaction]
-   **Data Exchange:** [Data flow]
-   **Considerations:** [Requirements]
```

## Guidelines

-   Modules should follow SOLID principles, high cohesion, and low coupling.
-   Components should be logically grouped with clear hierarchy and interfaces.