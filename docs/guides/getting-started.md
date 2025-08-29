# Getting Started with SPlectrum

This guide helps you quickly understand and start working with the SPlectrum ecosystem.

## Understanding the Ecosystem

SPlectrum is a multi-organization ecosystem for building P2P-native applications:

```mermaid
graph LR
    SP[SPlectrum Engine] --> CA[Carambah Composition]
    CA --> IM[InfoMetish Packaging]
    IM --> P2P[P2P Deployment]
    
    SE[Sesameh AI] -.-> SP
    SE -.-> CA
    
    classDef engineStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef composeStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px
    classDef packageStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef aiStyle fill:#e8f5e9,stroke:#1b5e20,stroke-width:2px
    
    class SP engineStyle
    class CA composeStyle
    class IM packageStyle
    class SE aiStyle
```

## Core Concepts

### 1. Everything is a Stream
- Applications process streams of events
- Events are immutable AVRO records
- Choreography through inbox/outbox patterns

### 2. Unified App/Module Architecture
- Modules are just stateless apps
- Apps can use other apps as modules
- No artificial distinction between apps and libraries

### 3. AI-First Development
- Collaborate with AI to create solutions
- AI handles implementation details
- You focus on what to build, not how

## First Steps

1. **Explore the Architecture**: Read the [unified app/module model](../architecture/core-patterns/unified-app-module.md)
2. **Understand Events**: Learn about [event choreography](../architecture/core-patterns/event-choreography.md)
3. **See Bootstrapping**: Check [implementation strategy](../implementation/bootstrapping/splectrum-evolution.md)

## Next: Create Your First App

Continue to [Creating Apps](./creating-apps.md) to build your first SPlectrum application.