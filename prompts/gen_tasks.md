# Tasks Generation and Management Prompt

Generates task descriptions and manages workflow based on `blueprint/impl_plan.md`, `blueprint/user_stories.md`, `blueprint/modules.md`, `blueprint/project_status.md`, and existing documents.

## Output: Markdown Documents

### Implementation Tasks (`impl_tasks.md`)

```markdown
# Implementation Tasks

## [Module/Feature Name]

### Task: [Task Name]

-   **ID:** [Unique identifier]
-   **Type:** [Feature/Bug/Technical Debt/etc.]
-   **Priority:** [High/Medium/Low]
-   **Status:** [Not Started/In Progress/Review/Done]
-   **Estimated Time:** [Time estimate]
-   **Dependencies:** [List]
-   **Assigned To:** [Developer/Team]

**Description:**

[Detailed description]

**User Story Reference:**

-   [Link to user story]
-   [Acceptance criteria]

**Technical Requirements:**

-   [Module requirements]
-   [Architecture constraints]
-   [Guidelines]

**Acceptance Criteria:**

1.  [Criterion 1]
2.  [Criterion 2]
3.  [Criterion 3]

**Testing Requirements:**

-   [ ] Unit tests for [functionality]
-   [ ] Integration tests for [scenarios]
-   [ ] Performance tests (if applicable)

**Resources:**

-   [Documentation]
-   [References]
-   [External resources]

**AI Agent:**

-   [Assistance with code/test generation]
-   [Specific instructions]
```

### Current Sprint (`current_sprint.md`)

```markdown
# Current Sprint

## Sprint Goal

[Sprint objective]

## Sprint Duration

-   Start Date: [Date]
-   End Date: [Date]

## Tasks in Progress

1.  [Task ID] - [Task Name]
    -   **Owner:** [Developer]
    -   **Status:** [Current status]
    -   **Blockers:** [Detailed description]
    -   **Progress:** [% complete]
    -   **Notes:** [Updates]

## Upcoming Tasks

1.  [Task ID] - [Task Name]
    -   **Priority:** [Level]
    -   **Dependencies:** [Dependencies]
    -   **Estimated Start:** [Date]

## Completed Tasks

1.  [Task ID] - [Task Name]
    -   **Completed:** [Date]
    -   **Review Status:** [Reviewed/Pending/Changes Requested]
    -   **Notes:** [Notes]

## Sprint Metrics

-   Total Tasks: [Number]
-   Completed: [Number]
-   In Progress: [Number]
-   Blocked: [Number]
-   Remaining: [Number]
```

### Current Task (`current_task.md`)

```markdown
# Current Task

## Task Details

-   **ID:** [Task ID]
-   **Name:** [Task Name]
-   **Status:** [In Progress]
-   **Started:** [Start Date/Time]
-   **Assigned To:** [Developer/Team]

## Context

### User Story

[Related user story]

### Module Requirements

[Technical requirements]

### Implementation Details

[Guidelines]

## Acceptance Criteria

1.  [ ] [Criterion 1]
2.  [ ] [Criterion 2]
3.  [ ] [Criterion 3]

## Technical Notes

-   [Architecture considerations]
-   [Design patterns]
-   [Code organization]

## Dependencies

-   **Required First:**
    -   [Completed dependency 1]
    -   [Completed dependency 2]
-   **Blocks:**
    -   [Dependent task 1]
    -   [Dependent task 2]

## Progress Updates

-   [Timestamp] [Update]
-   [Timestamp] [Update]

## Blockers

-   [ ] [Blocker 1] - [Resolution Plan/Status]
-   [ ] [Blocker 2] - [Resolution Plan/Status]
```

### Issues (`issues.md`)

```markdown
# Issues Tracking

## Critical Issues

### Issue: [Issue Name]

-   **ID:** [Identifier]
-   **Type:** [Bug/Performance/Security/etc.]
-   **Priority:** [Critical/High/Medium/Low]
-   **Status:** [Open/In Progress/Under Review]
-   **Reported:** [Date]
-   **Affects:** [Components/features]

**Description:**

[Detailed description]

**Impact:**

-   [Business impact]
-   [Technical impact]
-   [User impact]

**Resolution Plan:**

1.  [Step 1]
2.  [Step 2]
3.  [Step 3]

**Related Tasks:**

-   [Task ID] - [Task Name]
```
## Guidelines
- Tasks should have clear descriptions, context, acceptance criteria, dependencies, and assignments.
- Sprint planning should consider workload, priorities, scope, capacity, and blockers.
- Current task management should include context, progress tracking, blocker identification, and updates.
- Issue handling should include impact assessment, prioritization, resolution planning, and task linkage.