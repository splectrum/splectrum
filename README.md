# SPlectrum in a Nutshell

This overview is structured in three core blocks: the foundational components, the platform logical components, and the application focus domains. For detailed implementation status, see [Functional Components](./FUNCTIONAL-COMPONENTS.md).

## SPlectrum Foundational Components

The foundational layer contains the technical components of the platform.

| Area | Component | Current Status | Comments |
|------|-----------|----------------|----------|
| **JavaScript** | Node.js | ✅ Exists | Server-side JavaScript with JIT compilation and event loop concurrency |
| | Browser JS | ✅ Exists | Client-side JavaScript enabling unified development across contexts |
| | JIT Adaptability | ✅ Exists | Dynamic API generation and runtime modification capabilities |
| | Data Interoperability | ✅ Exists | Natural JS Object ↔ JSON ↔ AVRO transformation |
| **UI Components** | Terminal UI | ✅ Exists | Command parsing and online help for CLI operations |
| | Browser UI | 🔧 Partial | React/AVRO integration for web interface |
| | Mobile/PWA | ❌ Missing | Progressive Web App capabilities |
| **AVRO Schema and RPC** | Schema Definition | 🔧 Partial | Currently implemented with command-line-args |
| | Validation | 🔧 Partial | Input/output validation being implemented in browser UI work |
| | Documentation | 🔧 Partial | Auto-generated docs from schemas, currently implemented with command-line-args |
| | RPC | 🔧 Partial | AVRO RPC setup being implemented in browser UI work |
| **Streaming Native** | Kafka Compatible Data Record | ✅ Exists | Shared internal streaming data structure |
| | Data Change Streaming | 🔧 Partial | Consume / publish immutable data change records |
| **Functional Execution** | Execution Pipeline Record | ✅ Exists | Step to step functional, procedural step internal |
| | Stateless Execution Engine | ✅ Exists | Execution requires no persistent state |
| **Peer to Peer** | Bare Runtime | ❌ Missing | Minimal runtime, ideal for P2P applications |
| | Pear Stack | ❌ Missing | Bare based P2P runtime with true P2P capabilities |

## SPlectrum Platform Logical Components

The logical layer contains the design methodologies and approaches. The platform follows a **strict boundaries, internal freedom** design philosophy where constraints are moved to well-defined boundaries thereby maximising internal freedom.

| Area | Component | Current Status | Comments |
|-----------------|-----------|----------------|----------|
| **API First-Class Citizen** | Item Help | ✅ Exists | Current help system operational, needs AVRO schema integration |
| | API Discovery | ❌ Missing | Global `-h` flag with modules/apps list, API browsing capabilities |
| | Advanced API Management | 🗺️ Roadmap | API search, API registry, API versioning |
| **API Expression Contexts** | Scripting | ✅ Exists | Current implementation functional |
| | Continuation Syntax | 🗺️ Roadmap | Language design for fluent workflow composition |
| **TDC (Test Driven Creation)** | TDD Implementation | ✅ Exists | Uses functional execution audit for testing |
| | Continuous Improvement | 🗺️ Roadmap | Defect handling within expectation framework |
| | Test Driven Creation | 🗺️ Roadmap | Natural language, DSL engine, API creation |
| **Collaborative AI** | Human-AI Creative Partnership | ✅ Exists | Shared context, human-in-the-loop design principles |
| | Shared Ways of Working | ✅ Exists | Shared workflows and issue type defined workflows |
| | Strict Workflow Creation | ✅ Exists | Workflows transferable to event driven choreography |
| **Event Driven Choreography** | Strict Workflow Execution | 🗺️ Roadmap | Automated execution of defined workflow patterns **(deterministic, no AI required)** |
| | AI Issue Resolution | 🗺️ Roadmap | Autonomous issue handling and resolution **(AI within strict test/validation boundaries)** |
| **AI Autonomy** | Self-Directed Operation | 🗺️ Roadmap | Independent decision-making within validated boundaries **(creative problem definition and solution)** |
| | Autonomous Validation | 🗺️ Roadmap | Self-checking and quality assurance capabilities **(self-defined success criteria)** |
| | Creative Problem Solving | 🗺️ Roadmap | Novel solution generation within constraints **(true innovation and exploration)** |

## SPlectrum Application Focus

*Real-world application domains enabled by the platform capabilities*

| Domain | Description |
|--------|-------------|
| **Private P2P** | Family and private group applications where trust is inherent and privacy is paramount. Home automation systems that operate without external servers, shared photo libraries within families, private communications, and collaborative tools for small trusted groups. These networks prioritize privacy, control, and independence from external infrastructure. |
| **Public P2P** | Mass participation applications designed for open communities while maintaining decentralized infrastructure. Blockchain-integrated solutions, community platforms, content sharing networks, and collaborative applications that benefit from distributed participation without central control points. |
| **Business&nbsp;P2P** | Enterprise applications that create ringfenced networks for specific employee groups or business functions. Department-specific tools, project collaboration networks, and business applications that maintain organizational boundaries while eliminating central server dependencies and reducing infrastructure costs. |