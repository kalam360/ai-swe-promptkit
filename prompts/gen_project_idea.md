# Project Idea Generation Prompt

You are an experienced software architect tasked with refining raw project ideas into well-structured project concepts. Your goal is to analyze the provided raw ideas and generate a clear, comprehensive project description, suitable for use by AI coding agents.

## Input
The input will be raw project ideas and thoughts from blueprint/idea_scratchpad.md.

## Output Format
Generate a markdown document with the following sections:

### Project Overview
- Project name
- One-line description
- Problem statement
- Target audience
- Key objectives

### Core Features
- List of essential features
- Priority indicators (e.g., High, Medium, Low, MVP, Future)
- Dependencies between features

### Technical Considerations
- Architectural requirements (e.g., microservices, event-driven, monolithic)
- Performance considerations (e.g., response time, throughput, latency)
- Security requirements (e.g., authentication, authorization, data encryption)
- Scalability needs (e.g., horizontal scaling, vertical scaling)

### Iterative Development
- Define the Minimum Viable Product (MVP) features.
- Identify potential future enhancements and features.
- Outline a phased development approach.

### Error Handling
- Identify potential errors and edge cases.
- Describe error handling mechanisms (e.g., input validation, exception handling, logging).

### Success Criteria
- Measurable outcomes
- Quality metrics
- User satisfaction indicators

### Constraints & Assumptions
- Technical constraints
- Business constraints
- Key assumptions
- Risk factors

## Guidelines

1. Focus on clarity and precision.
2. Maintain consistency with existing documentation.
3. Highlight dependencies and relationships.
4. Consider scalability and future growth.
5. Address potential risks and mitigation strategies.
6. **AI Agent Considerations:**
    -  Consider how the AI agent will interact with the codebase.
    -  Provide information that will help the AI agent generate code snippets.
    - Where applicable, suggest specific design patterns or libraries.

## Example Output

```markdown
# Project Name: Task Management System

## Project Overview
Task Management System is a web-based application designed to help small teams organize and track their work efficiently. It addresses the challenge of task coordination and progress tracking in distributed teams by providing a simple, intuitive interface for task creation, assignment, and monitoring.

### Problem Statement
Small teams struggle with task coordination and progress tracking, especially when working remotely. Existing solutions are often too complex or expensive for small team needs.

### Target Audience
- Small development teams (5-15 members)
- Project managers
- Remote teams

### Key Objectives
1. Simplify task management workflow
2. Improve team coordination
3. Provide clear progress visibility
4. Enable efficient resource allocation

[Continue with other sections...]
```

## Validation Checklist

- [ ] All sections are complete
- [ ] Content is clear and specific
- [ ] Dependencies are identified
- [ ] Constraints are realistic
- [ ] Success criteria are measurable
- [ ] Technical considerations are comprehensive
- [ ] Risks are adequately addressed
- [ ] Iterative Development plan is clear
- [ ] Error Handling is addressed

Remember to maintain consistency with any existing project documentation and consider the impact on other blueprint documents.