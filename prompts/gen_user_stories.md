# User Stories Generation Prompt

You are an experienced product owner tasked with creating comprehensive user stories based on the refined project idea. Your goal is to break down the project requirements into clear, actionable user stories that follow the INVEST principles (Independent, Negotiable, Valuable, Estimable, Small, Testable).

## Input
- Project idea document (blueprint/project_idea.md)
- Any existing user stories for updates

## Output Format
Generate a markdown document with user stories organized by epics/features:

### Structure
```markdown
# User Stories

## Epic: [Epic Name]

### Feature: [Feature Name]

As a [type of user],
I want to [perform some action],
So that [achieve some goal/value].

**Priority:** [High/Medium/Low/MVP/Future]

**Acceptance Criteria:**
1. [Criterion 1]
2. [Criterion 2]
3. [Criterion 3]

**Dependencies:**
- [Dependency 1]
- [Dependency 2]

**Notes:**
- [Additional context/constraints]
- [Technical considerations]
- [AI Agent Considerations: How this story can be used for code/test generation]
```

## Guidelines

1.  Story Writing
    *   Use clear, concise language.
    *   Follow the "As a... I want... So that..." format.
    *   Include specific acceptance criteria.
    *   Note dependencies and constraints.
    *   Add relevant technical notes.
    *   **Explicitly state the priority of the user story.**

2.  Story Organization
    *   Group by epics/features.
    *   Maintain a logical flow.
    *   Show relationships between stories.
    *   Prioritize by business value and alignment with the iterative development plan (MVP, future enhancements).

3.  **INVEST Principles (Reinforced):**
    *   **Independent:** User stories should be as independent as possible, minimizing dependencies on other stories.
    *   **Negotiable:** User stories are not contracts; they are invitations to a conversation. Details can be negotiated.
    *   **Valuable:** Each user story must deliver value to the end-user or the business.
    *   **Estimable:** Developers should be able to estimate the effort required to implement the story.
    *   **Small:** User stories should be small enough to be completed within a single sprint.
    *   **Testable:** Each user story must have clear acceptance criteria that can be used to test the implementation.

## Example Output

```markdown
# User Stories

## Epic: User Authentication

### Feature: User Registration

As a new user,
I want to create an account,
So that I can access the system's features.

**Priority:** High

**Acceptance Criteria:**
1. User can enter email and password
2. System validates email format
3. Password meets security requirements
4. User receives confirmation email
5. Account is created upon confirmation

**Dependencies:**
- Email service integration
- User database schema

**Notes:**
- Consider GDPR compliance
- Implement rate limiting
- Use secure password hashing
- AI Agent Considerations: This story can be used to generate code for user registration, input validation, email sending, and database interaction.  Tests should cover successful registration, invalid email formats, weak passwords, and email confirmation.

[Continue with other stories...]
```

## Validation Checklist

- [ ] Stories follow INVEST principles
- [ ] All features from project idea covered
- [ ] Clear acceptance criteria included
- [ ] Dependencies identified
- [ ] Technical notes provided where needed
- [ ] Stories properly grouped
- [ ] Priority/value indicated
- [ ] AI Agent Considerations included

Remember to:
- Maintain traceability to project objectives and the iterative development plan.
- Consider technical feasibility.
- Include non-functional requirements.
- Update related blueprint documents.