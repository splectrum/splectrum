# Architecture & Design

This section contains the technical architecture and design principles of the SPlectrum ecosystem.

## Core Patterns

Technical patterns that define how SPlectrum works:

- [**Unified App/Module Model**](./core-patterns/unified-app-module.md) - Revolutionary insight: modules are just stateless apps
- [**Development & Runtime Architecture**](./core-patterns/development-runtime.md) - SPlectrum Engine and cross-app services
- [**Event Choreography**](./core-patterns/event-choreography.md) - Inbox/outbox pattern for decoupled communication
- [**Component Interaction**](./core-patterns/component-interaction.md) - How components work together

## Design Principles

Architectural philosophy and approach:

- [**Complexity Navigation**](./design-principles/complexity-navigation.md) - Managing complexity through architecture
- [**Single Concern Repositories**](./design-principles/single-concern-repos.md) - One repository, one purpose
- [**Repository Taxonomy**](./design-principles/repository-taxonomy.md) - Classification of repository types

## Key Insights

- **Streaming Native**: Everything is a stream of immutable events
- **AVRO Foundation**: Schema-first design using Apache AVRO
- **Container Authority**: Containers as the source of truth
- **Event-Driven**: Choreography over orchestration