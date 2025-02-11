# Technology Stack Generation Prompt

Defines the tech stack based on `blueprint/project_idea.md`, `blueprint/modules.md`, and existing documentation.

## Output: Markdown Document

```markdown
# Technology Stack

## Overview

[High-level description and rationale]

## Core Technologies

### Frontend

-   **Framework/Library:** [Choice with version]
    -   Rationale: [Explanation - performance, security, scalability]
    -   Key Features Used:
        -   [Feature 1]
        -   [Feature 2]
    -   Alternatives Considered:
        -   [Alternative 1]: [Why not chosen]
        -   [Alternative 2]: [Why not chosen]

### Backend

-   **Framework:** [Choice with version]
-   **API Design:** [REST/GraphQL/etc.]
    -   Rationale: [Why this choice?]
-   **Authentication:** [Solution]
-   **Authorization:** [Solution]

### Database

-   **Primary Database:** [Choice]
    -   Rationale: [Data model, scalability, performance]
-   **Caching Solution:** [Choice if needed]
    -   Rationale: [Caching strategy]
-   **Data Migration:** [Tools/approach]

### Infrastructure

-   **Hosting:** [Platform]
    -   Rationale: [Cost, scalability, management]
-   **CI/CD:** [Tools/services]
-   **Monitoring:** [Solutions]
-   **Logging:** [Solutions]

## Development Tools

### Version Control

-   **System:** [e.g., Git]
-   **Hosting:** [e.g., GitHub/GitLab]
-   **Branching Strategy:** [Description]

### Development Environment

-   **IDE:** [Recommended IDE]
-   **Extensions:** [Key extensions]
-   **Local Setup:** [Requirements]

### Testing

-   **Unit Testing:** [Framework]
-   **Integration Testing:** [Framework]
-   **E2E Testing:** [Framework]
-   **Load Testing:** [Tools]

## Security Measures

-   **Authentication:** [Implementation]
-   **Authorization:** [Implementation]
-   **Data Protection:** [Measures]
-   **API Security:** [Measures]
-   **Vulnerability Scanning:** [Tools/processes]

## Performance Optimization

-   **Caching Strategy:** [Approach]
-   **Load Balancing:** [Solution]
-   **CDN:** [If needed]
-   **Asset Optimization:** [Tools/approach]

## AI Agent & DevSecOps

- [How technologies can be used for code generation, configuration, and automated security checks.]
```

## Guidelines
- Consider project requirements, team expertise, community support, licenses, costs, performance, security, and scalability.
- Ensure stack compatibility.
- Consider technology longevity and scalability.