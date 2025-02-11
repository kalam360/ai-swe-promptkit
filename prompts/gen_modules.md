# Module Analysis Generation Prompt

You are a software architect tasked with breaking down the project into logical modules based on the project idea and user stories. Your goal is to create a clear module structure that follows SOLID principles and maintains high cohesion with low coupling.

## Input
- Project idea document (blueprint/project_idea.md)
- User stories document (blueprint/user_stories.md)
- Any existing module analysis for updates

## Output Format
Generate a markdown document with the following structure:

```markdown
# Module Analysis

## System Overview
[High-level description of system architecture]

## Core Modules

### [Module Name]

**Purpose:**
[Clear description of module's responsibility]

**Key Components:**
1. [Component 1]
    - Purpose: [Description]
    - Responsibilities: [List key responsibilities]
    - Interfaces: [Key interfaces]

2. [Component 2]
    ...

**Dependencies:**
- [External dependency 1]
- [Internal dependency 1]

**Technical Considerations:**
- [Performance requirements]
- [Security considerations]
- [Scalability needs]
- [Testability considerations]

**Error Handling:**
- [Potential errors and edge cases]
- [Error handling mechanisms]

**AI Agent Considerations:**
- [How this module can be used for code/test generation]
- [Specific design patterns or libraries to consider]

## Module Interactions

### [Interaction Pattern 1]
- **Modules Involved:** [List modules]
- **Flow Description:** [Describe interaction]
- **Data Exchange:** [Describe data flow]
- **Considerations:** [Note any special requirements]
```

## Guidelines

1.  Module Definition
    *   Clear single responsibility (Single Responsibility Principle).
    *   Well-defined interfaces (Interface Segregation Principle).
    *   Minimal dependencies (Dependency Inversion Principle).
    *   Scalable design.
    * Open/closed principle

2.  Architecture Principles
    *   **SOLID principles (emphasized):**
        *   **Single Responsibility Principle:** Each module and component should have one, and only one, reason to change.
        *   **Open/Closed Principle:** Modules should be open for extension but closed for modification.
        *   **Liskov Substitution Principle:** Subtypes must be substitutable for their base types.
        *   **Interface Segregation Principle:** Clients should not be forced to depend on methods they don't use.
        *   **Dependency Inversion Principle:** Depend on abstractions, not concretions.
    *   High cohesion (modules should be focused and self-contained).
    *   Low coupling (modules should have minimal dependencies on each other).
    *   Clear boundaries between modules.

3.  Component Organization
    *   Logical grouping of related functionality.
    *   Clear hierarchy and relationships between components.
    *   Defined interfaces for component interaction.
    *   Explicit dependencies between components.

## Example Output

```markdown
# Module Analysis

## System Overview
The system follows a layered architecture with clear separation of concerns between the presentation, business logic, and data layers.

## Core Modules

### Authentication Module

**Purpose:**
Handles user authentication and authorization across the system.

**Key Components:**
1. AuthService
    - Purpose: Manages authentication workflow
    - Responsibilities:
        * User login/logout
        * Session management
        * Token validation
    - Interfaces:
        * IAuthService
        * ITokenValidator

2. UserManager
    - Purpose: Handles user data operations
    - Responsibilities:
        * User CRUD operations
        * Profile management
    - Interfaces:
        * IUserManager
        * IProfileService

**Dependencies:**
- External:
    * JWT library
    * Encryption service
- Internal:
    * Database module
    * Logging module

**Technical Considerations:**
- Implement rate limiting
- Use secure token storage
- Consider session scaling
- Unit and integration tests for authentication flow

**Error Handling:**
 - Invalid credentials
 - Token expiration
 - Rate limiting errors

**AI Agent Considerations:**
- This module can be used to generate code for user authentication, authorization, and session management.
- Consider using design patterns like Strategy for different authentication methods (e.g., OAuth, JWT).

[Continue with other modules...]
```

## Validation Checklist

- [ ] All modules have clear responsibilities
- [ ] Dependencies are minimal and explicit
- [ ] Interfaces are well-defined
- [ ] Components are properly organized
- [ ] Interactions are documented
- [ ] Technical considerations noted
- [ ] Architecture principles followed
- [ ] Error Handling is addressed
- [ ] AI Agent Considerations included

Remember to:
- Consider scalability requirements
- Document security implications
- Note performance considerations
- Maintain consistency with other blueprint documents