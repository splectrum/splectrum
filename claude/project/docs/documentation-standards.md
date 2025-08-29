# Documentation Standards

This guide defines the documentation standards and practices for the SPlectrum repository.

## Design Principles

All documentation in this repository follows these core principles:

- **Concise**: Essential information only - no fluff
- **Practical**: Real examples over theory
- **Visual**: Diagrams preferred over walls of text
- **Evolutionary**: Documentation grows with the project

## Documentation Structure

```
docs/
├── README.md                    # Entry point, navigation
├── architecture/
│   ├── overview.md             # 1-page visual summary
│   ├── components.md           # Component descriptions
│   └── patterns.md             # Key patterns (inbox/outbox, etc)
├── guides/
│   ├── getting-started.md      # Quick start
│   ├── ai-collaboration.md     # Working with AI
│   └── development.md          # Development workflow
├── reference/
│   ├── organizations.md        # Organization details
│   ├── api-standards.md        # API/App conventions
│   └── quality-gates.md        # TDD approach
└── evolution/
    ├── roadmap.md              # Where we're going
    └── decisions.md            # Key design decisions
```

## Writing Style Guidelines

### Tone and Voice
- Direct and actionable
- Technical but accessible
- Assume intelligent readers who value their time

### Structure
1. **Title**: Clear, descriptive
2. **Purpose**: One-sentence summary
3. **Content**: Organized with clear headings
4. **Examples**: Show, don't just tell
5. **Next Steps**: Where to go from here

### Example Template
```markdown
# [Feature/Component Name]

[One-sentence description of what this is]

## Purpose
[Why this exists and what problem it solves]

## How It Works
[Visual diagram if applicable]
[Concise explanation]

## Example
\```javascript
// Show real, working code
\```

## Related
- Link to related components
- Link to patterns used
```

## Visual-First Approach

1. **Lead with diagrams** when explaining architecture or flow
2. **Use consistent visual language** (see visual-documentation-guide.md)
3. **Provide text alternatives** for accessibility
4. **Keep diagrams simple** - if it needs extensive explanation, simplify it

## Documentation Evolution Strategy

### Phase 1: Foundation
- Core concepts clearly defined
- Basic architecture documented
- Key patterns explained

### Phase 2: Implementation
- API examples added
- Integration patterns documented
- First use cases illustrated

### Phase 3: Ecosystem
- Component catalog built
- Solution templates created
- Best practices evolved from experience

## Quality Checklist

Before committing documentation:
- [ ] Follows the concise principle (can you remove 30% of words?)
- [ ] Includes practical examples
- [ ] Has visual representation where applicable
- [ ] Links to related documentation
- [ ] Tested that all code examples work
- [ ] Reviewed for clarity by fresh eyes

## Tools and Formats

- **Markdown**: Primary format for all documentation
- **Mermaid**: For diagrams (GitHub native rendering)
- **ASCII Art**: For simple, portable diagrams
- **Code blocks**: With syntax highlighting and working examples

## Maintenance

- Documentation is updated alongside code changes
- Broken links checked regularly
- Examples tested with each release
- Community feedback incorporated

## Anti-patterns to Avoid

- ❌ Walls of text without structure
- ❌ Theory without practical examples
- ❌ Out-of-date code snippets
- ❌ Complex diagrams that need extensive explanation
- ❌ Documentation for documentation's sake
- ❌ Assuming deep context without providing links