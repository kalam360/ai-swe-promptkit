# AI-SWE Status Generation Prompt (gen_status.md)

## Purpose

This prompt is used to generate a Markdown status report (`impl_status.md`) that tracks the progress of a software project. The report uses checkboxes to indicate the status of features, modules, and tasks.

## Input

The AI agent should read the following files to gather information:

- `blueprint/tasks.md`: Contains a list of tasks.
- `blueprint/user_stories.md`: Contains a list of user stories (features).
- `blueprint/modules.md`: Contains a list of modules.
- `blueprint/task-tracking/*`: (Optional) If this directory exists and contains files (e.g., `impl_tasks.md`, `current_sprint.md`), read them to get more granular task status information.

## Output

Generate a Markdown file named `impl_status.md` in the `blueprint` directory. The file should have the following structure:

```markdown
# Implementation Status

## Features

- [ ] [Feature 1 Description] (todo)
- [ ] [Feature 2 Description] (todo)
- [x] [Feature 3 Description] (done)
- [ ] [Feature 4 Description] (in progress)
...

## Modules

- [ ] [Module 1 Description] (todo)
- [x] [Module 2 Description] (done)
- [ ] [Module 3 Description] (in progress)
...

## Tasks

- [ ] [Task 1 Description] (todo)
- [ ] [Task 2 Description] (todo)
- [x] [Task 3 Description] (done)
- [ ] [Task 4 Description] (in progress)
...

**(Optional) Add more detailed sections based on files found in `blueprint/task-tracking/` if they provide additional status information.**
```

**Status Indicators:**

- `[ ]`: Todo
- `[x]`: Done
- `[ ]`: In progress (Use a space between the brackets for "in progress")

## Example (Partial)

If `blueprint/user_stories.md` contains:

```markdown
As a user, I want to be able to log in.
As a user, I want to be able to view my profile.
As a user, I want to be able to update my profile.
```

And `blueprint/tasks.md` contains:

```
Implement user login functionality.
Create user profile page.
Implement profile update feature.
Add database schema for user profiles.
```

And `blueprint/modules.md` contains:

```
Authentication Module
User Profile Module
```
And `blueprint/task-tracking/impl_tasks.md` contains:
```
- [x] Implement user login functionality.
- [ ] Create user profile page.
- [ ] Implement profile update feature.
```

Then, a *partial* `impl_status.md` might look like:

```markdown
# Implementation Status

## Features

- [x] As a user, I want to be able to log in. (done)
- [ ] As a user, I want to be able to view my profile. (in progress)
- [ ] As a user, I want to be able to update my profile. (todo)

## Modules

- [x] Authentication Module (done)
- [ ] User Profile Module (in progress)

## Tasks

- [x] Implement user login functionality. (done)
- [ ] Create user profile page. (in progress)
- [ ] Implement profile update feature. (todo)
- [ ] Add database schema for user profiles. (todo)
```

## Notes

- Prioritize information from `blueprint/task-tracking/*` for task status if available.
- Ensure the status indicators are correctly used.
- The output should be a valid Markdown file.
- Be concise and clear in the descriptions.