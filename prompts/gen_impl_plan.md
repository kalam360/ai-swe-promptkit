# Implementation Plan Generation Prompt

You are a technical lead tasked with creating a detailed implementation plan based on the project's requirements, architecture, and technology stack. Your goal is to create a comprehensive plan that guides the development team through the implementation process.

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
[High-level implementation strategy and approach]

## Phase 1: Project Setup

### Development Environment
1. [ ] Set up version control
   - Initialize repository
   - Configure branching strategy
   - Set up CI/CD pipelines

2. [ ] Configure development environment
   - Install required tools
   - Set up local development
   - Configure linting and formatting

### Infrastructure Setup
1. [ ] Set up cloud resources
2. [ ] Configure monitoring
3. [ ] Set up logging

## Phase 2: Core Implementation

### [Module Name]
1. [ ] [Component/Feature 1]
   - **Description:** [What needs to be implemented]
   - **Dependencies:** [What needs to be done first]
   - **Technical Notes:**
     * [Important technical consideration]
     * [Architecture decision]
   - **Testing Requirements:**
     * Unit tests for [specific functionality]
     * Integration tests for [specific scenarios]
   
2. [ ] [Component/Feature 2]
   [Similar structure as above]

## Phase 3: Integration & Testing

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

## Phase 4: Deployment & Launch

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

1. Planning Principles
   - Break down into manageable phases
   - Identify clear dependencies
   - Include testing requirements
   - Consider deployment strategy

2. Implementation Details
   - Clear step-by-step instructions
   - Technical considerations noted
   - Testing requirements specified
   - Verification steps included

3. Risk Management
   - Identify potential issues
   - Include rollback procedures
   - Note critical dependencies
   - Plan for contingencies

## Example Output

```markdown
# Implementation Plan

## Overview
This implementation plan outlines the step-by-step process for building the user authentication system, following a phased approach with continuous integration and testing throughout the development cycle.

## Phase 1: Project Setup

### Development Environment
1. [ ] Set up version control
   - Initialize Git repository
   - Configure GitHub Actions for CI/CD
   - Set up branch protection rules
   - Configure commit hooks for linting

2. [ ] Configure development environment
   - Install Node.js and required tools
   - Set up ESLint and Prettier
   - Configure TypeScript
   - Set up test framework

[Continue with other phases...]
```

## Validation Checklist

- [ ] All phases clearly defined
- [ ] Dependencies identified
- [ ] Testing requirements specified
- [ ] Technical notes included
- [ ] Deployment steps detailed
- [ ] Monitoring plan included
- [ ] Risk mitigation addressed

Remember to:
- Consider team capacity
- Include time estimates
- Note external dependencies
- Update related blueprint documents