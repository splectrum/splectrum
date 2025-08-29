# SPlectrum Project Overview

## Vision

Create the tools to enable P2P networks where distributed applications run in their own peer-to-peer environment, contributing a solution to decentralized processing that extends beyond existing blockchain decentralization.

## Core Ambition

Transform how distributed applications are built and deployed by:
- Providing tools to easily create custom P2P networks
- Enabling applications to run natively in peer-to-peer environments
- Extending blockchain's decentralization philosophy to general-purpose computing
- Leveraging a native streaming application engine (SPlectrum) at its heart
- Embracing AI-enhanced automation throughout the development and deployment lifecycle
- Shifting from manual coding to collaborative AI creation (collaboration of minds, not hands)

## Technical Foundation

### SPlectrum DSL Engine
- **Domain-Specific Language (DSL)** engine at the core
- **Unified API Architecture**: All tools and apps accessed through standardized SPlectrum APIs
- **AVRO-based**: Apache AVRO provides the schema foundation for all data exchange
- **Unified Repository Architecture**:
  - **APIs**: Tool interfaces for system capabilities (stateless wrappers around external tools)
  - **Apps**: Application interfaces for business logic (stateful execution environment)
  - **Modules**: Stateless packaging of apps - same structure as apps but deployed without state
  - **Development Runtime**: Every app repository requires SPlectrum Engine (SE) as development runtime
  - **Cross-App Services**: Common capabilities (testing, deployment, validation) provided through cross-app invocation
  - **Key Insight**: Modules are equivalent to 'stateless apps' - same development template, same naming convention ([package]/[api]/[method]), enabling unified development with flexible deployment
- **AI-Friendly Design**: Uniform language environment enables AI to easily reason about and generate functionality
- **Stateless Execution**: Each request is independent with full audit trail
- **Error Replay Capability**: Error packages can recreate exact execution context
- **Data Layer Auditing**: Complete tracking of all data interactions

### Native Streaming Architecture
- **Kafka-Compatible Structure**: Uses Kafka record JSON format (headers, data, etc.)
- **Streaming Paradigm**: Consumes and publishes in Kafka patterns
- **Immutable Records**: Leverages Kafka's append-only, immutable record design
- **Functional Programming Friendly**: Immutability enables pure functions and composable transformations
- **Folder-Based Development**: Dev implementation uses folder structures
- **Topic Compatibility**: Can integrate with Kafka topics via database layer
- **Streaming-First Design**: Not request/response but continuous data flows

## Goals

### Initial Target Use Cases
- **Home Automation Without Central Servers**: Enable P2P home automation networks where devices communicate directly
- **Blockchain-Integrated Solutions**: Build applications that leverage both P2P networking and blockchain technology
- **Serverless Distributed Applications**: Remove dependency on central infrastructure

### Technical Goals
[Additional technical objectives]

## Core Principles

- **TDD-First**: Test-Driven Development as foundation for automation and quality
- **Quality Gate Driven**: Success criteria and tests define all workflows
- **Decentralization First**: Every component should enhance distributed processing
- **Streaming Native**: Built on streaming paradigms from the ground up
- **AI-Enhanced**: Automation and intelligence integrated throughout
- **Developer Friendly**: Tools that make P2P development accessible
- **Schema-Driven**: AVRO schemas define all data contracts and interfaces
- **Uniform APIs**: Consistent interface patterns across all tools and apps
- **DSL-Powered**: Domain-specific abstractions for P2P application development
- **Stateless & Auditable**: Full execution and data layer audit trails
- **Functional Programming**: Immutable data enables pure functions and composability

## Bootstrapping Strategy

### Seed Repo Evolution
- **Challenge**: SPlectrum needs SPlectrum to build SPlectrum (circular dependency)
- **Solution**: Seed repo strategy - all-in-one prototypes evolving to component separation
- **Journey**: hello-splectrum → spl0 (hand-coded) → spl1 (collaborative AI) → component extraction
- **Current Status**: spl1 approaching readiness for Development SE extraction

### Component Extraction Roadmap
1. **Coordinated Extraction** - SPlectrum (Dev SE + apps) + InfoMetish (zip wrapper) from spl1
2. **Multi-Target Expansion** - InfoMetish adds containers, P2P, OS installers
3. **Bootstrap Validation** - Complete self-hosting capability for both organizations

**Key Insight**: spl1 IS the bootstrap - contains seeds for both SPlectrum AND InfoMetish, working prototype that builds all separated components.

## Project Scope

### Authoritative Source Strategy
- **Container Registry**: Primary distribution mechanism and authoritative source
- **GitHub**: Source code repositories across all organizations
- **Containers**: Include ready execution environments with all required assets
- **Benefits**: Version control, dependency management, and complete runtime packaging

### Container Assets Beyond Code
- Complete test suites ready for execution
- Carambah solutions for complex API scenarios
- Runtime dependencies and configurations
- Documentation and examples
- Any asset of value for the complete solution

### What's Included
[Core components and boundaries]

### What's Not Included
[Explicit exclusions]

## Success Metrics

[How do we measure success?]