# SPlectrum Overview

## SPlectrum: AI-Friendly Application Development Platform

**SPlectrum is an application development platform designed to make creating applications accessible through natural human-AI collaboration, built on a foundation of open architecture, well-documented APIs, and comprehensive quality frameworks.**

#### 🔧 **Open Architecture & APIs as First-Class Citizens**
Everything is designed to be extensible, composable, and interoperable. No vendor lock-in, no proprietary constraints. All functionality is exposed through clean, consistent APIs with formal interfaces.

#### 📊 **AVRO Schema & RPC Foundation**
Apache AVRO provides the schema foundation for all data exchange and RPC calls, ensuring type safety and compatibility across distributed systems. AVRO's versatility extends to UI development through React components using AVRO for schema validation and RPC (library browsified), with opportunities to extend to mobile through PWA.

#### 🚀 **Unified API Architecture: DSL → Schema → Transport**
The DSL engine enables creation of custom APIs that naturally express domain requirements. These custom APIs receive the same first-class treatment as platform APIs - AVRO schema backing, validation, dual-mode access (formal + programmatic continuation syntax). AVRO RPC then opens all APIs (platform and custom) to a myriad of local and remote transport protocols as standard.

**The Power**: Create APIs that perfectly fit your domain, with enterprise-grade rigor and universal transport compatibility built-in.

#### ✅ **Strict Test-Driven Development (TDD)**
Quality gates and testing define every workflow. TDD isn't just encouraged - it's built into the platform's DNA and essential for AI collaboration.

#### 🤖 **AI-Friendly Collaborative Design**
Built specifically to enable seamless human-AI collaboration through APIs as first-class citizens, strict TDD workflows, and uniform language environment. AI can easily reason about and generate distributed functionality using formal API contracts and fluent programmatic expressions. The further aim of the collaborative approach is to continuously increase AI autonomy and to ensure that the collaborative approach remains highly creative.

---

## SPlectrum: Springboard to Decentralisation

The AI collaborative platform will be used to explore how familiar distributed application patterns can be transformed into decentralised equivalents. The platform is built in JavaScript and will migrate to Bare runtime for P2P, so it can run on Pear P2P stack. The strengths of the SPlectrum platform leaves it well equipped to tackle the challenges of decentralisation.

### Target Explorations

**Private P2P Networks**: Family and private group applications where trust is inherent and privacy is paramount. Home automation systems that operate without external servers, shared photo libraries within families, private communications, and collaborative tools for small trusted groups. These networks prioritize privacy, control, and independence from external infrastructure.

**Public P2P Networks**: Mass participation applications designed for open communities while maintaining decentralized infrastructure. Blockchain-integrated solutions, community platforms, content sharing networks, and collaborative applications that benefit from distributed participation without central control points.

**Business P2P Networks**: Enterprise applications that create ringfenced networks for specific employee groups or business functions. Department-specific tools, project collaboration networks, and business applications that maintain organizational boundaries while eliminating central server dependencies and reducing infrastructure costs.

## Documentation, Organization Structure & Key Repositories

### 📄 **Project Documentation** ([`docs/`](./docs/))
Comprehensive technical documentation covering vision, architecture, implementation guides, and references for the entire SPlectrum ecosystem.

The SPlectrum ecosystem is organized around five specialized organizations, each addressing specific concerns:

### 🚀 **SPlectrum** - Execution Engine & Tool Integration
Core execution environment with DSL engine, unified API architecture, and streaming capabilities. Everything that exposes SPlectrum APIs lives here.

**Key Repository:** [https://github.com/SPlectrum/spl1](https://github.com/SPlectrum/spl1) - Primary execution engine implementation

### 📦 **InfoMetish** - Packaging & Deployment  
Platform-specific packaging and deployment with container registry as authoritative source. Handles P2P packaging, container deployments, and traditional installations.

**Key Repository:** [https://github.com/InfoMetish/InfoMetis](https://github.com/InfoMetish/InfoMetis) - Container registry and deployment orchestration

### 🤖 **Sesameh** - AI-Driven Behavioral Intelligence
Collaborative AI creation enabling human-AI partnership where humans define and AI implements. Quality gates, TDD workflows, and intelligent decision-making systems.

**Key Repository:** [https://github.com/Sesameh/claude-swift](https://github.com/Sesameh/claude-swift) - Collaborative AI development workflows

### 🔧 **Carambah** - Solution Composition
High-level solution assembly from simple component setups to complex vanilla solutions. Environment-agnostic compositions using vanilla dev configs.

**Key Repository:** [https://github.com/Carambah/carambah](https://github.com/Carambah/carambah) - Solution composition engine

### ⚡ **bare-for-pear** - P2P Runtime Compatibility
JavaScript module conversions for Bare runtime (not Node.js), enabling true P2P networking capabilities through Pear platform integration.

**Status:** In development - foundational P2P networking modules

### How Organizations Work Together

```
SPlectrum (APIs & Engines) → Carambah (Compositions) → InfoMetish (Packaging) → Deployment
                    ↑                                           ↑
              Sesameh (AI Intelligence)              bare-for-pear (P2P Runtime)
```

1. **SPlectrum** provides execution foundations and API wrappers
2. **Carambah** composes these into complete solutions  
3. **InfoMetish** packages compositions for target platforms
4. **Sesameh** adds intelligence at any layer
5. **bare-for-pear** enables P2P capabilities across the ecosystem

## Documentation Overview

### 📚 **Project Documentation** ([`docs/`](./docs/))

#### [Foundation](./docs/foundation/) - Vision & Organization
- **Project Vision**: Why SPlectrum exists and core goals
- **Organization Structure**: Five specialized organizations working together
- **AI Collaboration Model**: Human-AI partnership principles

#### [Architecture](./docs/architecture/) - Technical Design
- **Core Patterns**: Unified app/module, event choreography
- **Design Principles**: Single concern, complexity navigation
- **CCAI Evolutionary Paradigm**: Seed-to-split lifecycle for organic growth

#### [Implementation](./docs/implementation/) - Building SPlectrum
- **Bootstrapping Strategies**: Getting started with development
- **Development Practices**: Quality gates and TDD workflows
- **Phase-Based Development**: Roadmap execution approach

#### [Guides](./docs/guides/) - Practical Tutorials
- **Getting Started**: Step-by-step introduction
- **Creating Applications**: Building with SPlectrum
- **Working with AI**: Effective collaboration patterns

#### [Reference](./docs/reference/) - Standards & Quick Lookups
- **Visual Style Guide**: Colors, diagrams, and branding
- **API Conventions**: Consistent interface design
- **Technical Specifications**: Detailed reference materials

## Operational Documentation Overview

### 🤖 **AI Workflow Operations** ([`claude/`](./claude/))

#### Ways of Working (`claude/wow/` → [`claude-swift`](https://github.com/Sesameh/claude-swift))
- **Workflow System**: SESSION_START, INBOX, COMMIT, VERSION_TRANSITION
- **Operational Rules**: Step-by-step execution and collaboration patterns
- **Audit Logging**: Complete trail of all operations

#### Project Configuration (`claude/project/`)
- **Version Management**: Target versions and release planning
- **Issue & Milestone Caching**: GitHub integration and tracking
- **Documentation Standards**: Writing style and AI collaboration guidelines

#### Task Management (`claude/inbox/`, `claude/outbox/`)
- **Cross-Repository Communication**: OUTBOX/INBOX workflow patterns
- **Task Processing**: Converting tasks to GitHub issues
- **Workflow Integration**: Seamless AI-assisted development

### Key Operational Workflows
- **`start sesame`**: Initialize new development sessions
- **`inbox sesame`**: Process cross-repository tasks
- **`commit sesame`**: Intelligent commits with issue closure
- **`version sesame`**: Version planning and milestone management

---

*Building the future of decentralized applications through collaborative AI and P2P networking.*

**Private P2P Networks**: Family and private group applications where trust is inherent and privacy is paramount. Home automation systems that operate without external servers, shared photo libraries within families, private communications, and collaborative tools for small trusted groups. These networks prioritize privacy, control, and independence from external infrastructure.

**Public P2P Networks**: Mass participation applications designed for open communities while maintaining decentralized infrastructure. Blockchain-integrated solutions, community platforms, content sharing networks, and collaborative applications that benefit from distributed participation without central control points.

**Business P2P Networks**: Enterprise applications that create ringfenced networks for specific employee groups or business functions. Department-specific tools, project collaboration networks, and business applications that maintain organizational boundaries while eliminating central server dependencies and reducing infrastructure costs.

---

*Building the future of decentralized applications through collaborative AI and P2P networking.*