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

## Module Interactions

### [Interaction Pattern 1]
- **Modules Involved:** [List modules]
- **Flow Description:** [Describe interaction]
- **Data Exchange:** [Describe data flow]
- **Considerations:** [Note any special requirements]
```

## Guidelines

1. Module Definition
   - Clear single responsibility
   - Well-defined interfaces
   - Minimal dependencies
   - Scalable design

2. Architecture Principles
   - SOLID principles
   - High cohesion
   - Low coupling
   - Clear boundaries

3. Component Organization
   - Logical grouping
   - Clear hierarchy
   - Defined interfaces
   - Explicit dependencies

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

Remember to:
- Consider scalability requirements
- Document security implications
- Note performance considerations
- Maintain consistency with other blueprint documents