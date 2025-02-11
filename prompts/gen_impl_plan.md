# Implementation Plan Generation Prompt

Creates a plan based on `blueprint/project_idea.md`, `blueprint/user_stories.md`, `blueprint/modules.md`, `blueprint/tech_stack.md`, and existing plans.

## Output: Markdown Document

```markdown
# Implementation Plan

## Overview

[High-level strategy, emphasizing iterative development and agile principles]

## Phases

### Phase 1: Inception

-   **Goals:** [Project goals, scope, basic understanding]
-   **Activities:**
    -   [ ] Set up infrastructure (version control, CI/CD)
    -   [ ] Define initial architecture
    -   [ ] Create initial user stories, prioritize MVP

### Phase 2: Elaboration

-   **Goals:** [Refine architecture, address risks, define user stories]
-   **Activities:**
    -   [ ] Design key components
    -   [ ] Develop proof-of-concepts for high-risk areas
    -   [ ] Refine user stories and acceptance criteria
    -   [ ] Create module analysis

### Phase 3: Construction

-   **Goals:** [Develop software, iterative development, continuous testing]
-   **Activities:**
    -   [ ] Implement user stories in sprints
    -   [ ] Code reviews
    -   [ ] Unit, integration, performance testing
    -   [ ] Refactor

    #### Sprint 1

    -   **Goal:** [Sprint goal, aligned with user story priorities]
        ##### [Module Name]
        1.  [ ] [Component/Feature 1]
            -   **Description:** [Implementation]
            -   **User Story:** [Link]
            -   **Priority:** [High/Medium/Low]
            -   **Dependencies:** [What needs to be done first]
            -   **Time Estimate:** [Effort]
            -   **Technical Notes:**
                -   [Technical consideration]
                -   [Architecture decision]
            -   **Testing Requirements:**
                -   Unit tests for [functionality]
                -   Integration tests for [scenarios]
            -   **AI Agent:**
                -   [Assistance with code generation, testing, configuration]

        2.  [ ] [Component/Feature 2]
            [Similar structure]

    #### Sprint 2

    -   **Goal:** [Sprint goal]
        ...

### Phase 4: Transition

-   **Goals:** [Deploy, user acceptance, maintenance]
-   **Activities:**
    -   [ ] Deploy to staging
    -   [ ] User acceptance testing (UAT)
    -   [ ] Deploy to production
    -   [ ] Monitor performance and stability
    -   [ ] Address post-deployment issues

## Integration & Testing (Ongoing)

### Integration Testing

1.  [ ] [Integration Test Suite 1]
    -   **Scope:** [What's tested]
    -   **Prerequisites:** [What's needed]
    -   **Test Cases:** [Scenarios]

### Performance Testing

1.  [ ] [Performance Test Suite]
    -   **Metrics:** [What to measure]
    -   **Benchmarks:** [Expected results]
    -   **Tools:** [Testing tools]

## Deployment & Launch

### Staging Deployment

1.  [ ] [Deployment Step 1]
    -   **Process:** [What to do]
    -   **Verification:** [How to verify]
    -   **Rollback:** [How to rollback]

### Production Launch

1.  [ ] [Launch Step 1]
    -   **Process:** [What to do]
    -   **Verification:** [How to verify]
    -   **Monitoring:** [What to monitor]
```

## Guidelines

-   Break down work into phases/sprints, identify dependencies, include testing, consider deployment.
-   Prioritize tasks, estimate effort.
-   Provide instructions, note technical considerations, specify testing, include verification steps.
-   Identify risks, include rollback procedures, note dependencies, plan for contingencies.