# Technology Stack Generation Prompt

You are a technical architect tasked with defining the technology stack for the project based on its requirements, modules, and constraints. Your goal is to create a comprehensive technology stack that best serves the project's needs while considering maintainability, scalability, and team expertise.

## Input
- Project idea document (blueprint/project_idea.md)
- Module analysis document (blueprint/modules.md)
- Any existing tech stack documentation for updates

## Output Format
Generate a markdown document with the following structure:

```markdown
# Technology Stack

## Overview
[High-level description of the technology choices and rationale]

## Core Technologies

### Frontend
- **Framework/Library:** [Choice with version]
  * Rationale: [Explanation]
  * Key Features Used:
    - [Feature 1]
    - [Feature 2]
  * Alternatives Considered:
    - [Alternative 1]: [Why not chosen]
    - [Alternative 2]: [Why not chosen]

### Backend
- **Framework:** [Choice with version]
- **API Design:** [REST/GraphQL/etc.]
- **Authentication:** [Solution]
- **Authorization:** [Solution]

### Database
- **Primary Database:** [Choice]
- **Caching Solution:** [Choice if needed]
- **Data Migration:** [Tools/approach]

### Infrastructure
- **Hosting:** [Platform]
- **CI/CD:** [Tools/services]
- **Monitoring:** [Solutions]
- **Logging:** [Solutions]

## Development Tools

### Version Control
- **System:** [e.g., Git]
- **Hosting:** [e.g., GitHub/GitLab]
- **Branching Strategy:** [Description]

### Development Environment
- **IDE:** [Recommended IDE]
- **Extensions:** [Key extensions]
- **Local Setup:** [Requirements]

### Testing
- **Unit Testing:** [Framework]
- **Integration Testing:** [Framework]
- **E2E Testing:** [Framework]
- **Load Testing:** [Tools]

## Security Measures
- **Authentication:** [Implementation]
- **Authorization:** [Implementation]
- **Data Protection:** [Measures]
- **API Security:** [Measures]

## Performance Optimization
- **Caching Strategy:** [Approach]
- **Load Balancing:** [Solution]
- **CDN:** [If needed]
- **Asset Optimization:** [Tools/approach]
```

## Guidelines

1. Technology Selection Criteria
   - Project requirements alignment
   - Team expertise consideration
   - Community support and maturity
   - License compatibility
   - Cost implications

2. Stack Compatibility
   - Ensure all components work well together
   - Consider integration points
   - Evaluate performance impact
   - Check security implications

3. Future-proofing
   - Technology longevity
   - Scalability potential
   - Upgrade paths
   - Community trends

## Example Output

```markdown
# Technology Stack

## Overview
The system will use a modern, scalable stack focusing on developer productivity and application performance. The choices below prioritize mature, well-supported technologies with strong community backing.

## Core Technologies

### Frontend
- **Framework:** React 18.2.0
  * Rationale: Strong ecosystem, team expertise, excellent performance
  * Key Features Used:
    - Server Components
    - Suspense
    - Context API
  * Alternatives Considered:
    - Vue.js: Team more familiar with React
    - Angular: More complex for our needs

[Continue with other sections...]
```

## Validation Checklist

- [ ] All required technologies covered
- [ ] Choices align with requirements
- [ ] Security measures adequate
- [ ] Performance needs addressed
- [ ] Development workflow defined
- [ ] Testing strategy complete
- [ ] Monitoring solution specified

Remember to:
- Consider operational costs
- Document version requirements
- Note any licensing implications
- Update related blueprint documents