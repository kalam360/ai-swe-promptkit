# User Stories Generation Prompt

Generates user stories based on `blueprint/project_idea.md` and existing stories.

## Output: Markdown Document

### Structure

```markdown
# User Stories

## Epic: [Epic Name]

### Feature: [Feature Name]

As a [user type],
I want to [action],
So that [goal/value].

**Priority:** [High/Medium/Low/MVP/Future]

**Acceptance Criteria:**

1.  [Criterion 1]
2.  [Criterion 2]
3.  [Criterion 3]

**Dependencies:**

-   [Dependency 1]
-   [Dependency 2]

**Notes:**

-   [Context/constraints]
-   [Technical considerations]
-   [AI Agent: code/test generation]
```

## Guidelines

-   Use clear, concise language.
-   Follow "As a... I want... So that..." format.
-   Include acceptance criteria, dependencies, technical notes, and priority.
-   Group by epics/features.
-   Prioritize by business value and iterative development plan.