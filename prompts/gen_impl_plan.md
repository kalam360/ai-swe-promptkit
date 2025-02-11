# Implementation Plan Generation Prompt

You are a technical lead tasked with creating a detailed implementation plan based on the project's requirements, architecture, and technology stack. Your goal is to create a comprehensive plan that guides the development team (including AI coding agents) through the implementation process, following an iterative and agile approach.

## Input
- Project idea document (blueprint/project_idea.md)
- User stories document (blueprint/user_stories.md)
- Module analysis document (blueprint/modules.md)
- Technology stack document (blueprint/tech_stack.md)
- Any existing implementation plan for updates

## Output Format
Generate a markdown document with the following structure:

```markdown
# Implementation Plan

## Overview
[High-level implementation strategy and approach, emphasizing iterative development and agile principles]

## Phases

### Phase 1: Inception
- **Goals:** [Define the overall project goals and scope, establish a basic understanding of the system]
- **Activities:**
  * [ ] Set up project infrastructure (version control, CI/CD)
  * [ ] Define initial architecture
  * [ ] Create initial user stories and prioritize for MVP

### Phase 2: Elaboration
- **Goals:** [Refine the architecture, address key risks, define the majority of user stories]
- **Activities:**
    * [ ] Design key system components
    * [ ] Develop proof-of-concepts for high-risk areas
    * [ ] Refine user stories and acceptance criteria
    * [ ] Create detailed module analysis

### Phase 3: Construction
- **Goals:** [Develop the working software, focusing on iterative development and continuous testing]
- **Activities:**
  * [ ] Implement user stories in sprints
  * [ ] Conduct regular code reviews
  * [ ] Perform unit, integration, and performance testing
  * [ ] Refactor code as needed

    #### Sprint 1
    - **Goal:** [Specific goal for this sprint, aligned with user story priorities]
        ##### [Module Name]
        1. [ ] [Component/Feature 1]
            - **Description:** [What needs to be implemented]
            - **User Story:** [Link to the relevant user story]
            - **Priority:** [High/Medium/Low]
            - **Dependencies:** [What needs to be done first]
            - **Time Estimate:** [Estimated effort in hours/days]
            - **Technical Notes:**
                * [Important technical consideration]
                * [Architecture decision]
            - **Testing Requirements:**
                * Unit tests for [specific functionality]
                * Integration tests for [specific scenarios]
            - **AI Agent Considerations:**
                * [How the AI agent can assist with code generation, testing, or configuration]

        2. [ ] [Component/Feature 2]
            [Similar structure as above]

    #### Sprint 2
     - **Goal:** [Specific goal for this sprint]
        ...

### Phase 4: Transition
- **Goals:** [Deploy the software to production, ensure user acceptance, and transition to ongoing maintenance]
- **Activities:**
  * [ ] Deploy to staging environment
  * [ ] Conduct user acceptance testing (UAT)
  * [ ] Deploy to production environment
  * [ ] Monitor system performance and stability
  * [ ] Address any post-deployment issues

## Integration & Testing (Ongoing throughout Construction)

### Integration Testing
1. [ ] [Integration Test Suite 1]
   - **Scope:** [What's being tested]
   - **Prerequisites:** [What needs to be ready]
   - **Test Cases:** [Key scenarios]

### Performance Testing
1. [ ] [Performance Test Suite]
   - **Metrics:** [What to measure]
   - **Benchmarks:** [Expected results]
   - **Tools:** [Testing tools to use]

## Deployment & Launch

### Staging Deployment
1. [ ] [Deployment Step 1]
   - **Process:** [What to do]
   - **Verification:** [How to verify]
   - **Rollback:** [How to rollback]

### Production Launch
1. [ ] [Launch Step 1]
   - **Process:** [What to do]
   - **Verification:** [How to verify]
   - **Monitoring:** [What to monitor]
```

## Guidelines

1.  Planning Principles
    *   Break down work into manageable phases and sprints.
    *   Identify clear dependencies between tasks.
    *   Include comprehensive testing requirements.
    *   Consider deployment strategy early on.
    *   **Prioritize tasks based on user story priority and risk.**
    *   **Estimate effort for each task.**

2.  Implementation Details
    *   Provide clear, step-by-step instructions.
    *   Note technical considerations and architecture decisions.
    *   Specify testing requirements for each component/feature.
    *   Include verification steps for each deployment stage.

3.  Risk Management
    *   Identify potential issues and risks.
    *   Include rollback procedures for deployments.
    *   Note critical dependencies.
    *   Plan for contingencies.

## Example Output

```markdown
# Implementation Plan

## Overview
This implementation plan outlines the step-by-step process for building the user authentication system, following a phased, iterative approach with continuous integration and testing throughout the development cycle. We will use an agile methodology with two-week sprints.

## Phases
### Phase 1: Inception
 - **Goals:** Define project scope, establish basic system understanding, set up infrastructure.
 - **Activities:**
    * [ ] Set up Git repository and CI/CD pipeline with GitHub Actions.
    * [ ] Define initial architecture (layered architecture with REST API).
    * [ ] Create initial user stories for user registration, login, and profile management. Prioritize registration and login for MVP.

### Phase 2: Elaboration
 - **Goals**: Refine architecture, address risks (authentication security), define user stories.
 - **Activities:**
    * [ ] Design authentication and authorization modules.
    * [ ] Develop proof-of-concept for JWT-based authentication.
    * [ ] Refine user stories with detailed acceptance criteria.
    * [ ] Create module analysis document.

### Phase 3: Construction

    #### Sprint 1
    - **Goal:** Implement user registration functionality.
        ##### Authentication Module
        1. [ ] User Registration Component
            - **Description:** Implement the user registration endpoint and service.
            - **User Story:** As a new user, I want to create an account, so that I can access the system's features.
            - **Priority:** High
            - **Dependencies:** None
            - **Time Estimate:** 3 days
            - **Technical Notes:**
                * Use bcrypt for password hashing.
                * Implement email validation.
            - **Testing Requirements:**
                * Unit tests for registration service (valid/invalid input, password hashing).
                * Integration tests for database interaction.
            - **AI Agent Considerations:**
                * The AI agent can generate code for the registration endpoint, service, and database interaction based on the user story and technical notes. It can also generate unit and integration tests.

[Continue with other phases and sprints...]
```

## Validation Checklist

- [ ] All phases clearly defined (Inception, Elaboration, Construction, Transition)
- [ ] Dependencies identified
- [ ] Testing requirements specified
- [ ] Technical notes included
- [ ] Deployment steps detailed
- [ ] Monitoring plan included
- [ ] Risk mitigation addressed
- [ ] Time estimates included
- [ ] User story priorities linked to tasks
- [ ] AI Agent Considerations included

Remember to:
- Consider team capacity
- Include time estimates
- Note external dependencies
- Update related blueprint documents