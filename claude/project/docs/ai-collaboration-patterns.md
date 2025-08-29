# AI Collaboration Patterns

This guide describes how to effectively collaborate with AI when working in the SPlectrum repository.

## Expression Modes

When working with AI in this repository, you can express intent through multiple modes:

### Natural Language
- Describe what you want in plain English
- Focus on outcomes, not implementation details
- Example: "Create a service that validates AVRO schemas before processing"

### Visual Flows
- Collaborate with AI to create Mermaid diagrams
- Start with rough sketches, refine together
- Example: "Help me diagram the event flow between components"

### Domain-Specific Language (DSL)
- Use SPlectrum's DSL when precision is needed
- AI understands and can generate DSL
- Example: Define specific event schemas or API contracts

### Mixed Modes
- Combine approaches for best results
- Example: Natural language description + visual diagram + DSL for contracts

## Workflow Patterns

### Interactive Pattern (Primary)
1. **Define Intent**: Express what the solution should do
2. **AI Proposes**: Implementation using SPlectrum patterns
3. **Review & Refine**: Focus on requirements, not code details
4. **AI Implements**: Following TDD principles
5. **Validate**: Ensure quality gates pass

### Event-Driven Pattern
- **Describe Events**: What triggers what
- **AI Maps Flow**: Creates choreography
- **Review Interactions**: Ensure loose coupling
- **AI Implements**: Inbox/outbox patterns

## Best Practices for AI Collaboration

### 1. Start with Why
- Explain the problem before the solution
- Provide context about the larger system
- Share constraints and requirements

### 2. Use Repository Patterns
- Reference existing patterns in the codebase
- Ask AI to follow established conventions
- Example: "Follow the inbox/outbox pattern like in [component]"

### 3. Iterative Refinement
- Start broad, refine details
- Use visual diagrams to validate understanding
- Don't hesitate to correct and redirect

### 4. Leverage AI Strengths
- **Pattern Recognition**: "Find similar patterns in the codebase"
- **Code Generation**: "Implement this following our TDD approach"
- **Documentation**: "Create visual documentation for this flow"
- **Refactoring**: "Improve this while maintaining the interface"

## Communication Templates

### For New Features
```
I need to [what you want to achieve]
It should [key requirements]
Similar to [reference existing pattern if applicable]
Constraints: [any limitations]
```

### For Debugging
```
Expected: [what should happen]
Actual: [what's happening]
Context: [relevant system state]
Tried: [what you've attempted]
```

### For Architecture Decisions
```
Goal: [what we're trying to achieve]
Options considered: [different approaches]
Trade-offs: [pros and cons]
Recommendation?: [ask for AI input]
```

## Mental Model Alignment

### Share Context Liberally
- Current system state
- Recent changes
- Future direction
- Team decisions

### Use Consistent Terminology
- Refer to components by their proper names
- Use SPlectrum domain language
- Reference specific files/patterns

### Validate Understanding
- Ask AI to explain back in diagrams
- Request examples
- Verify against existing patterns

## Collaborative Documentation

When creating documentation with AI:
1. Start with structure (use our templates)
2. Fill in content together
3. Generate diagrams interactively
4. Review for consistency with standards
5. Ensure examples work

## Anti-patterns to Avoid

- ❌ Asking for code without context
- ❌ Accepting first suggestion without review
- ❌ Ignoring established patterns
- ❌ Skipping visual validation
- ❌ Working in isolation from system context

## Success Metrics

Good AI collaboration results in:
- Clear, visual documentation
- Code that follows repository patterns
- Solutions that integrate smoothly
- Faster iteration cycles
- Shared understanding captured in artifacts