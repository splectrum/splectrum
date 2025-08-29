# Event-Driven Choreography Architecture Notes

## Long-term Direction

### Technology Stack
- **Primary**: JavaScript implementation for event-driven choreography
- **Alternative**: Python (only if explicitly better for specific use cases)
- **Platform**: P2P Bare for Pear platform
- **Pattern**: DSL (Domain-Specific Language) in SPLectrum engines

### Architecture Evolution
1. **Current State**: Claude directly executes workflows using file system tools
2. **Target State**: Claude uses DSL APIs, implementation abstracted away

### Key Benefits
- **Abstraction**: Implementation details hidden from Claude
- **Flexibility**: JavaScript scripts enable DSL creation
- **Distribution**: P2P Bare enables decentralized execution
- **Modularity**: SPLectrum engines provide domain-specific capabilities

### Implementation Notes
- JavaScript scripts will encapsulate workflow logic
- DSL APIs will provide high-level operations
- Claude will interact through clean API boundaries
- Event choreography will handle coordination between components

This architectural direction aligns with moving from orchestration (centralized control) to choreography (distributed coordination) patterns.