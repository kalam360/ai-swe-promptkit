# AI-SWE Status Generation Prompt (`gen_status.md`)

Generates `blueprint/impl_status.md` to track project progress using checkboxes for features, modules, and tasks.

Reads:

-   `blueprint/tasks.md`
-   `blueprint/user_stories.md`
-   `blueprint/modules.md`
-   `blueprint/task-tracking/*` (optional)

Output (`blueprint/impl_status.md`):

```markdown
# Implementation Status

## Features

-   [ ] [Feature 1] (todo)
-   [ ] [Feature 2] (todo)
-   [x] [Feature 3] (done)
-   [ ] [Feature 4] (in progress)
    ...

## Modules

-   [ ] [Module 1] (todo)
-   [x] [Module 2] (done)
-   [ ] [Module 3] (in progress)
    ...

## Tasks

-   [ ] [Task 1] (todo)
-   [ ] [Task 2] (todo)
-   [x] [Task 3] (done)
-   [ ] [Task 4] (in progress)
    ...

**(Optional) Add details from `blueprint/task-tracking/`**
```

**Status:**

-   `[ ]`: Todo
-   `[x]`: Done
-   `[ ]`: In progress

## Notes

-   Prioritize `blueprint/task-tracking/*` for task status.
-   Use correct status indicators.
- Output valid Markdown.