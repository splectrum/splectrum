# Single Concern Repositories

## Core Principle

Repositories should maintain single concern/responsibility, enabling natural serialization of work without the overhead of branch management.

## Why This Works

### 1. Natural Work Serialization
- Single concern = focused scope
- Focused scope = less conflict potential
- Less conflicts = serialized work is efficient
- No need for parallel branches

### 2. Reality of Parallel Development
- Even human teams struggle with parallel changes to core files
- Merge conflicts are expensive (time and cognitive load)
- "Parallel" often becomes "serialized with extra steps"
- True parallelism happens across repos, not within

### 3. AI Collaboration Benefits
- AI can work extremely fast in serial
- No context switching between branches
- Clear linear history
- Immediate feedback from quality gates

## Architecture Implications

### Repository Design
- Each repo has ONE primary concern
- Related functionality split across repos when sensible
- Communication via inbox/outbox events
- Composition happens at higher levels (Carambah)

### Examples
- ❌ `monolithic-app` with auth, API, UI, database
- ✅ `api-auth`, `api-users`, `app-ui`, `api-database`

### Parallelism Strategy
- **Within repo**: Serial execution (no branches)
- **Across repos**: True parallel work
- **Integration**: Event-driven choreography

### The File Operations Analogy
Just like file operations in concurrent programming:
- **Each repository = A file**: Single point of serialization
- **Event choreography = Thread pool**: Parallel execution across files
- **Inbox/outbox = Message passing**: Safe communication
- **No locks needed**: Each repo processes serially
- **System-wide parallelism**: Multiple repos process simultaneously

This gives us the best of both worlds:
- Safe, predictable operations within each repo
- Massive parallelism across the system
- No complex synchronization mechanisms
- Natural load distribution

## Benefits

1. **Simplicity**: No branch management overhead
2. **Speed**: Direct commits with instant feedback
3. **Clarity**: Linear history tells clear story
4. **AI-Friendly**: Optimal for automated development
5. **Human-Friendly**: Reduced cognitive load

## Trade-offs Acknowledged

- Requires thoughtful repository boundaries
- Initial setup has more repos to manage
- Cross-repo changes need coordination

BUT: These are one-time design costs vs. ongoing branch management overhead.