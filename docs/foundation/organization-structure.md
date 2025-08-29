# SPlectrum Organizations Map

## The Quartet Architecture

The project is structured around four core organizations, originally designed as a quartet, now extended:

### Bootstrapping Context
**Current State**: Working from spl1 seed repository (all-in-one prototype) approaching component extraction readiness.

**Extraction Plan**: spl1 → Coordinated extraction (SPlectrum Dev SE + InfoMetish zip wrapper) → Multi-target expansion → Full bootstrap validation for both organizations

### SPlectrum - Execution Engine
- **Purpose**: Core execution environment and tool integration
- **Repository Types**: 
  - DSL execution engine components
  - API wrappers (prefixed with `api-`) around third-party tools
  - DSL applications (prefixed with `app-`) - unified development for both stateful apps and stateless modules
  - Platform-agnostic runtime environment
  - Script execution and orchestration
- **Key Characteristic**: Everything that exposes SPlectrum APIs lives here

### InfoMetish - Packaging & Deployment
- **Purpose**: Platform-specific packaging and deployment
- **Repository Types**: 
  - Container-based deployments (DEFAULT - authoritative source)
  - P2P packaging and distribution (using Pear platform)
  - Plain install packages (traditional OS installations)
  - Generic/vanilla configurations
  - Platform-specific deployment templates
  - Self-extracting archives for distribution
- **Key Characteristic**: Container registry as authoritative source with ready execution environments

### Sesameh - Behavioral Intelligence
- **Purpose**: AI-driven intelligence and collaborative creation
- **Repository Types**: 
  - Claude CAI behavioral components
  - Collaborative AI workflows (minds not hands)
  - TDD-first workflow definitions
  - Quality gate specifications
  - Success criteria templates
  - AI-driven orchestration and adaptation modules
  - Intelligent decision-making systems
  - System optimization and learning algorithms
- **Key Characteristic**: Enables collaborative AI creation where humans define and AI implements

### Carambah - Solution Composition
- **Purpose**: High-level solution assembly and component composition
- **Repository Types**: 
  - Simple component setups (single SPlectrum engine or tool)
  - Complex vanilla solutions (multi-component orchestrations)
  - Compositions of SPlectrum engines
  - Compositions of 3rd party tools (wrapped with SPlectrum APIs)
  - Mixed compositions (engines + containers + P2P + tools)
  - Business logic and workflow definitions
- **Key Characteristic**: Environment-agnostic compositions using vanilla dev configs

## Extended Organizations

### bare-for-pear
- **Purpose**: Maintain JavaScript modules compatible with Bare runtime (Pear platform)
- **Repository Types**:
  - Node.js library conversions for Bare runtime
  - Starting with: `commandline-args` and `commandline-usage`
  - P2P networking foundations using Pear platform
- **Key Characteristic**: Enables P2P capabilities through Bare JavaScript runtime (not Node.js)

## Inter-Organization Relationships

- **SPlectrum** provides the execution foundation and API wrappers for all components
- **InfoMetish** packages any composition for deployment (P2P, containers, plain)
- **Sesameh** adds intelligence to any composition
- **Carambah** composes components (from simple to complex) with vanilla configs
- **bare-for-pear** provides Bare runtime compatibility that InfoMetish uses for P2P packaging

### Composition Flow
1. **SPlectrum** provides engines and API-wrapped tools
2. **Carambah** composes these into solutions (vanilla/dev config)
3. **InfoMetish** packages compositions for target platforms
4. **Sesameh** can add intelligence at any layer

## Naming Conventions

### Repository Prefixes
- `api-`: API wrappers around external tools (in SPlectrum) - includes AVRO schemas
- `app-`: DSL applications (in SPlectrum) - unified template for both stateful apps and stateless modules - includes AVRO schemas
- **Module Deployment**: Same `app-*` repositories can be packaged as stateless modules for code-area installation
- Platform prefixes in InfoMetish (e.g., `k8s-`, `linux-`)
- Solution prefixes in Carambah based on use case

### Schema Management
- AVRO schemas live with their APIs and Apps
- No centralized schema registry - maintains API/App cohesion
- Each api-* and app-* repo contains its own schema definitions